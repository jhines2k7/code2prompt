Project Path: bumble-for-jobs/

I'd like your help improving the performance of this codebase. It works correctly, but we need it to be faster and more efficient. Analyze the code thoroughly with this goal in mind:

Source Tree:
```
bumble-for-jobs
├── chat.json
├── generate_resume.py
├── jesus_sanders_resume.py
├── models.py
├── worker.py
├── say_hello.py
├── server.py
├── careers.json
├── get_scheduled_queue.py
├── requirements.txt
├── jobs.py
└── logs

``` 

`bumble-for-jobs/models.py`:

```````py
from datetime import datetime
from pydantic import BaseModel
from typing import List, Optional, Dict, Union, Literal
from openai.types import FileObject
from pydantic import BaseModel, EmailStr, UUID4

class Message(BaseModel):
  id: str
  content: str
  sender_id: str
  receiver_id: str
  date: str
  read: bool
  read_time: Optional[str]
  message_type: str
  status: str

class Chat(BaseModel):
  id: str
  job_posting_id: str
  messages: List[Message] = []
    
class JobPosting(BaseModel):
  id: str
  title: str
  city: Union[str, None] = ''
  state: Union[str, None] = ''
  description: str
  responsibilities: Union[List[str], Dict[str, Optional[str]], Dict[str, List[str]], None, str]
  required_skills: Union[List[str], Dict[str, Optional[str]], Dict[str, List[str]], None, str]
  soft_skills: Union[List[str], Dict[str, Optional[str]], Dict[str, List[str]], None, str]
  benefits: Union[List[str], Dict[str, Optional[str]], Dict[str, List[str]], None, str]  
  file: FileObject
  employer_id: str

class CompatibilityAnalysis(BaseModel):
  id: str
  education: int
  years_of_professional_experience: int
  relevant_skills: int
  soft_skills: int
  industry_knowledge: int
  achievements_and_accomplishments: int
  certifications_and_additional_training: int
  career_trajectory: int
  leadership_and_specialized_experience: int
  adaptability_and_learning_ability: int
  technical_projects_or_portfolio: int
  normalized_score: int
  job_posting: JobPosting
  full_analysis: str

class JWTClaims(BaseModel):
  csrf: str
  exp: int
  fresh: bool
  iat: int
  jti: str
  nbf: int
  roles: Optional[List[str]] = None
  state: Optional[str] = ''
  sub: EmailStr
  type: str
  user_id: Optional[str] = ''

class JobSeeker(BaseModel):
  id: str
  username: str
  liked: List[CompatibilityAnalysis] = []
  disliked: List[CompatibilityAnalysis] = []
  resumes: List[FileObject] = []
  compatibility_analysis_list: List[CompatibilityAnalysis] = []
  city: str
  state: str
  email: Optional[str]
  password: Optional[str]
  roles: Optional[List[str]]
  access_claims: Optional[JWTClaims] = None
  refresh_claims: Optional[JWTClaims] = None

class Employer(BaseModel):
  id: str
  first_name: str
  last_name: str
  company_name: str
  job_postings: List[JobPosting] = []
  liked: List[CompatibilityAnalysis] = []
  disliked: List[CompatibilityAnalysis] = []
  city: str
  state: str
  email: Optional[str]
  roles: Optional[List[str]]
  password: Optional[str]
  access_claims: Optional[JWTClaims] = None
  refresh_claims: Optional[JWTClaims] = None
```````

`bumble-for-jobs/worker.py`:

```````py
from rq import Worker, Queue, Connection
from redis import Redis

# Connect to Redis
redis_conn = Redis()

# Use the connection to create a queue
with Connection(redis_conn):
  q = Queue('bumble-for-jobs')

  # Create a worker that listens to 'my_queue'
  worker = Worker(q)

  # Start the worker
  worker.work()
```````

`bumble-for-jobs/server.py`:

```````py
from crypt import methods
from datetime import timedelta
from math import e
import os
import random
import threading
from typing import Container
import uuid
import shelve
import time
import logging
import mimetypes
import magic
import json
import sys
import argparse
import urllib.parse
import hmac
import hashlib
import base64

from itertools import groupby
from operator import itemgetter
from datetime import datetime, timezone
from faker import Faker
from flask import Flask, jsonify, request
from flask_socketio import SocketIO, join_room, emit
from numpy import rec
from openai import OpenAI
from openai.types import FileObject
from flask_cors import CORS
from models import Chat, CompatibilityAnalysis, Employer, JobPosting, JobSeeker, Chat, JWTClaims, Message
from azure.cosmos import CosmosClient
from azure.cosmos.exceptions import CosmosResourceNotFoundError, CosmosHttpResponseError
from randomuser import RandomUser
from healthcheck import HealthCheck
from flask_jwt_extended import JWTManager, create_refresh_token, create_access_token, jwt_required
from flask_jwt_extended import get_jwt_identity, get_jwt, decode_token
from flask_sqlalchemy import SQLAlchemy
from werkzeug.security import generate_password_hash, check_password_hash
from werkzeug.middleware.proxy_fix import ProxyFix
from dotenv import load_dotenv
from redis import Redis
from rq import Queue
from jobs import run_compatibility_analysis

# Create a parser for the command-line arguments
# e.g. python your_script.py --env .env.prod
parser = argparse.ArgumentParser(description='Loads variables from the specified .env file and prints them.')
parser.add_argument('--env', type=str, default='.env.dev', help='The .env file to load')
args = parser.parse_args()
# Load the .env file specified in the command-line arguments
load_dotenv(args.env)
# HTTP_PROVIDER = os.getenv("HTTP_PROVIDER")

health = HealthCheck()

# basedir = os.path.abspath(os.path.dirname(__file__))

app = Flask(__name__)
app.config['SECRET_KEY'] = os.getenv("SECRET_KEY")
# app.config['JWT_SECRET_KEY'] = os.getenv("JWT_SECRET_KEY")
# app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///' + os.path.join(basedir, 'authentication.db')
# app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False

app.add_url_rule("/healthcheck", "healthcheck", view_func=lambda: health.run())

app.wsgi_app = ProxyFix(
    app.wsgi_app, x_for=1, x_proto=1
)

CORS(app)
socketio = SocketIO(app, async_mode='gevent', cors_allowed_origins='*')

# db = SQLAlchemy(app)
jwt = JWTManager(app)

# User model
"""
class User(db.Model):
  id = db.Column(db.Integer, primary_key=True)
  username = db.Column(db.String(80), unique=True, nullable=False)
  password_hash = db.Column(db.String(128))
  role = db.Column(db.String(80))

  def set_password(self, password):
    self.password_hash = generate_password_hash(password)

  def check_password(self, password):
    return check_password_hash(self.password_hash, password)

# Create the database
def create_tables():
  db.create_all()
"""
logging.basicConfig(
  stream=sys.stderr,
  level=logging.INFO,
  format='%(levelname)s:%(asctime)s:%(message)s'
)

logger = logging.getLogger(__name__)

redis_conn = Redis()
redis_q = Queue('bumble-for-jobs', connection=redis_conn)
logger.info(f"REDIS PING: {redis_conn.ping()}")

KEYFILE = os.getenv("KEYFILE")
CERTFILE = os.getenv("CERTFILE")
COSMOS_DB_URL = os.getenv("COSMOS_DB_URL")
COSMOS_DB_CREDENTIAL = os.getenv("COSMOS_DB_CREDENTIAL")
COSMOS_DB_NAME = os.getenv("COSMOS_DB_NAME")
COSMOS_EMPLOYER_CONTAINER_NAME = os.getenv("COSMOS_EMPLOYER_CONTAINER_NAME")
COSMOS_EMPLOYER_PARTITION_KEY_PATH = os.getenv("COSMOS_EMPLOYER_PARTITION_KEY_PATH")
COSMOS_JOB_SEEKER_CONTAINER_NAME = os.getenv("COSMOS_JOB_SEEKER_CONTAINER_NAME")
COSMOS_JOB_SEEKER_PARTITION_KEY_PATH = os.getenv("COSMOS_JOB_SEEKER_PARTITION_KEY_PATH")
COMPATIBILITY_EXPERT_ID = os.getenv("COMPATIBILITY_EXPERT_ID")
BREAKDOWN_EXPERT_ID = os.getenv("BREAKDOWN_EXPERT_ID")
OPENAI_API_KEY = os.getenv("OPENAI_API_KEY")

client = OpenAI(api_key=OPENAI_API_KEY)
cosmos_client = CosmosClient(url=COSMOS_DB_URL, credential=COSMOS_DB_CREDENTIAL)
cosmos_database = cosmos_client.get_database_client(COSMOS_DB_NAME)

@socketio.on('connect')
def connect():
  logger.info('Client connected')

def get_authorization_header(master_key, verb, resource_type, resource_id, date):
  key = base64.b64decode(master_key)
  text = f"{verb.lower()}\n{resource_type.lower()}\n{resource_id}\n{date.lower()}\n\n"
  body = text.encode("utf-8")
  signature = hmac.new(key, body, hashlib.sha256).digest()
  signature = base64.b64encode(signature).decode("utf-8")

  auth_header = urllib.parse.quote(f"type=master&ver=1.0&sig={signature}")
  return auth_header

def role_required(required_role):
  def wrapper(fn):
    @jwt_required()
    def decorator(*args, **kwargs):
      claims = get_jwt()
      jwt_claims = JWTClaims(**claims)
      logger.info(f"jwt_claims: {jwt_claims.model_dump_json()}")
      if required_role not in jwt_claims.roles:
        return jsonify(msg="Insufficient role"), 403
      return fn(*args, **kwargs)
    return decorator
  return wrapper
"""
@app.route('/create-database', methods=['POST'])
def create_database():
  with app.app_context():
    db.create_all()
  
  return jsonify(msg="Database created"), 200
"""
@jwt.token_in_blocklist_loader
def check_if_token_revoked(jwt_header, jwt_payload):
  claims = JWTClaims(**jwt_payload)

  user = None
  if 'JOB_SEEKER' in claims.roles:
    job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
    item = job_seeker_container.read_item(item=str(claims.user_id), partition_key=claims.state)
    user = JobSeeker(**item)
  else:
    employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
    item = employer_container.read_item(item=str(claims.user_id), partition_key=claims.state)
    user = Employer(**item)

  return user.refresh_claims is None

@app.route('/token/revoke', methods=['POST'])
@role_required('ADMIN')
def revoke_token():
  user_id = request.json.get('user_id')
  state = request.json.get('state')
  user = None
  try:
    container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
    item = container.read_item(item=user_id, partition_key=state)
    user = JobSeeker(**item)
  except CosmosResourceNotFoundError as e:
    container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
    item = container.read_item(item=user_id, partition_key=state)
    user = Employer(**item)

  if user:
    user.access_claims = None
    user.refresh_claims = None

    container.upsert_item(body=user.model_dump())

  return jsonify(msg=f"Token revoked for {user_id}"), 200

def prune_expired_tokens():
  container = cosmos_database.get_container_client("token_blocklist")
  query = '''
    SELECT * 
    FROM c 
    WHERE c.expires > GetCurrentDateTime()
  '''
  items = list(container.query_items(
    query=query,
    enable_cross_partition_query=True
  ))

  # for token in items:
  #   token = Token(**token)
  #   container.delete_item(item=token.id, partition_key=token.user_id)

@app.route('/token/refresh', methods=['POST'])
@jwt_required(refresh=True)
def refresh():
  identity = get_jwt_identity()

  access_claims = JWTClaims(**get_jwt())

  additional_claims = {"user_id": access_claims.user_id, "roles": access_claims.roles, "state": access_claims.state}
  new_access_token = create_access_token(identity=identity, additional_claims=additional_claims)

  if 'JOB_SEEKER' in access_claims.roles:
    job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
    item = job_seeker_container.read_item(item=str(access_claims.user_id), partition_key=access_claims.state)
    job_seeker = JobSeeker(**item)
    job_seeker.access_claims = access_claims
    job_seeker_container.upsert_item(body=job_seeker.model_dump())
  else:
    employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
    item = employer_container.read_item(item=str(access_claims.user_id), partition_key=access_claims.state)
    employer = Employer(**item)
    employer.access_claims = access_claims
    employer_container.upsert_item(body=employer.model_dump())
  
  return jsonify(access_token=new_access_token)

@app.route('/logout', methods=['POST'])
@jwt_required()
def logout():
  claims = JWTClaims(**get_jwt())

  if 'JOB_SEEKER' in claims.roles:
    job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
    item = job_seeker_container.read_item(item=str(claims.user_id), partition_key=claims.state)
    job_seeker = JobSeeker(**item)
    job_seeker.access_claims = None
    job_seeker.refresh_claims = None
    job_seeker_container.upsert_item(body=job_seeker.model_dump())
  else:
    employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
    item = employer_container.read_item(item=str(claims.user_id), partition_key=claims.state)
    employer = Employer(**item)
    employer.access_claims = None
    employer.refresh_claims = None
    employer_container.upsert_item(body=employer.model_dump())
  
  return jsonify(msg="Access and refresh tokens revoked"), 200

# Example usage of the role_required decorator
@app.route('/employer-only', methods=['GET'], endpoint='employer_only')
@role_required('EMPLOYER')  # Only allow users with the 'EMPLOYER' role
def employer_only_route():
  return jsonify(msg="Welcome, employer!")

@app.route('/chat', methods=['GET'])
@jwt_required()
def get_chat():
  job_seeker_id = request.args.get('job_seeker_id')
  employer_id = request.args.get('employer_id')
  job_post_id = request.args.get('job_post_id')

  chat_id = f"{job_seeker_id}-{employer_id}-{job_post_id}"

  employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)  
  query = '''
    SELECT job_post.title
    FROM c
    JOIN job_post IN c.job_postings
    WHERE job_post.id = @job_posting_id
  '''
  parameters = [
    {"name": "@job_posting_id", "value": job_post_id}
  ]
  job_title = list(employer_container.query_items(
    query=query,
    parameters=parameters,
    enable_cross_partition_query=True
  ))[0]['title']

  # Check if the conversation exists
  container = cosmos_database.get_container_client("chats")
  chat = None
  try:
    item = container.read_item(item=chat_id, partition_key=job_post_id)
    chat = Chat(**item)
    logger.info(f"Chat thread found")
  except CosmosResourceNotFoundError as e:
    logger.error(f"Error: {e}")
    logger.info(f"Chat not found, creating a new chat between job_seeker: {job_seeker_id} and employer: {employer_id} for job: {job_post_id}")
    chat = Chat(id=chat_id, job_posting_id=job_post_id)
    container.create_item(body=chat.model_dump())
    logger.info(f"Chat created: {chat.model_dump_json()}")
  
  claims = JWTClaims(**get_jwt())
  receiver_id = job_seeker_id if claims.user_id == employer_id else employer_id
  
  return jsonify(chat=chat.model_dump(), job_title=job_title, receiver_id=receiver_id), 200

@socketio.on('join_chat')
def join_chat(data):
  chat_id = data['chat_id']
  join_room(chat_id)
  emit('chat_joined', {'chat_id': chat_id})

@socketio.on('message_sent')
def send_message(data):
  chat_id = data['chat_id']
  job_post_id = data['job_post_id']

  container = cosmos_database.get_container_client("chats")
  chat = Chat(**container.read_item(item=chat_id, partition_key=job_post_id))
  message_id = str(uuid.uuid4())
  logger.info(f"message data: {data['message']}")
  message = Message(**data['message'], id=message_id)
  logger.info(f"message: {message.model_dump()}")

  chat.messages.append(message.model_dump())

  container.upsert_item(body=chat.model_dump())

  emit('new_message', 
       { 'message': message.model_dump(), 'chat_id': chat_id, 'job_post_id': job_post_id }, 
       include_self=False, room=chat_id)

@socketio.on('message_received')
def receive_message(data):
  chat_id = data['chat_id']
  job_post_id = data['job_post_id']

  container = cosmos_database.get_container_client("chats")
  chat = Chat(**container.read_item(item=chat_id, partition_key=job_post_id))

  # find the message in the chat and update the status
  for message in chat.messages:
    if message.id == data['message']['id']:
      message.status = 'read'
      message.read_time = datetime.now().isoformat()
      message.read = True
      break
  
  container.upsert_item(body=chat.model_dump())

# User login route
@app.route('/login', methods=['POST'])
def login():
  logger.info("Logging in user")
  if not request.is_json:
    return jsonify(msg="Missing JSON in request"), 400
  
  email = request.json.get('email')
  password = request.json.get('password')

  user = None
  logger.info("Querying the job seeker database")
  job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
  query = "SELECT * FROM c WHERE c.email = @email"
  parameters = [
    {"name": "@email", "value": email}
  ]
  items = list(job_seeker_container.query_items(
    query=query,
    parameters=parameters,
    enable_cross_partition_query=True
  ))

  if len(items) > 0:
    user = JobSeeker(**items[0])
    logger.info("User found")
  else:
    logger.info("Job seeker not found. Querying the employer database")
    employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
    query = "SELECT * FROM c WHERE c.email = @email"
    parameters = [
      {"name": "@email", "value": email}
    ]
    items = list(employer_container.query_items(
      query=query,
      parameters=parameters,
      enable_cross_partition_query=True
    ))

    if len(items) > 0:
      user = Employer(**items[0])
      logger.info("Employer user found")

  if user and check_password_hash(user.password, password):
    additional_claims = {"user_id": user.id, "roles": user.roles, "state": user.state}
    logger.info("Creating access token")
    # Create the tokens
    access_token = create_access_token(identity=email, additional_claims=additional_claims)
    refresh_token = create_refresh_token(identity=email, additional_claims=additional_claims)
    
    # Decode tokens to store jti and expiration
    decoded_access_token = decode_token(access_token)
    user.access_claims = JWTClaims(**decoded_access_token)
    decoded_refresh_token = decode_token(refresh_token)
    user.refresh_claims = JWTClaims(**decoded_refresh_token)

    if 'JOB_SEEKER' in user.roles:
      job_seeker_container.upsert_item(body=user.model_dump())
    else:
      employer_container.upsert_item(body=user.model_dump())
    
    return jsonify(access_token=access_token, refresh_token=refresh_token), 200
  else:
    return jsonify(msg="Bad username or password"), 401

# A protected route
@app.route('/protected', methods=['GET'])
@jwt_required()
def protected():
  current_user = get_jwt_identity()
  logger.info(f"current_user: {current_user}")
  claims = JWTClaims(**get_jwt())
  return jsonify(logged_in_as=current_user, claims=claims.model_dump()), 200

@app.route('/mark-job-seeker-compatibility-analysis/<compatibility_analysis_id>', methods=['PUT'], endpoint='')
@role_required('EMPLOYER')
def mark_job_seeker_compatibility_analysis(compatibility_analysis_id):
  job_seeker_id = request.args.get('job_seeker_id')
  job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)

  query = '''
    SELECT compatibility_analysis, c.id as job_seeker_id, c.username as username
    FROM c
    JOIN compatibility_analysis IN c.compatibility_analysis_list
    WHERE compatibility_analysis.id = @compatibility_analysis_id
  '''
  item = list(job_seeker_container.query_items(
    query=query,
    parameters=[
      {"name": "@compatibility_analysis_id", "value": compatibility_analysis_id}
    ],
    enable_cross_partition_query=True
  ))[0]

  compatibility_analysis = CompatibilityAnalysis(**item['compatibility_analysis'])

  claims = JWTClaims(**get_jwt())

  employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
  item = employer_container.read_item(item=str(claims.user_id), partition_key=claims.state)

  employer = Employer(**item)

  employer.liked.append(compatibility_analysis)

  job_seekers = get_job_seekers_by_job_post(compatibility_analysis.job_posting.id)

  


  return jsonify(
    user_id=claims.user_id, 
    compatibility_analysis_id=compatibility_analysis_id, 
    next=next.id), 200


@app.route('/mark-compatibility-analysis/<compatibility_analysis_id>', methods=['PUT'], endpoint='mark_compatibility_analysis')
@role_required('JOB_SEEKER')
def mark_compatibility_analysis(compatibility_analysis_id):
  claims = JWTClaims(**get_jwt())

  like = request.args.get('like')

  job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
  item = job_seeker_container.read_item(item=claims.user_id, partition_key=claims.state)
  job_seeker = JobSeeker(**item)

  #find the compatibility analysis in the job seeker's list and move it to the liked list
  for analysis in job_seeker.compatibility_analysis_list:
    if analysis.id == compatibility_analysis_id:
      job_seeker.compatibility_analysis_list.remove(analysis)
      if like == 'Y':
        job_seeker.liked.append(analysis)
      else:
        job_seeker.disliked.append(analysis)
      break

  job_seeker_container.upsert_item(body=job_seeker.model_dump())

  if len(job_seeker.compatibility_analysis_list) == 0:
    return jsonify(msg="No more compatibility analyses"), 204
  
  next = random.choice(job_seeker.compatibility_analysis_list)

  return jsonify(
    user_id=claims.user_id, 
    compatibility_analysis_id=compatibility_analysis_id, 
    next=next.id), 200

@app.route('/job-posts', methods=['GET'], endpoint='get_job_posts')
@role_required('JOB_SEEKER')
def get_job_posts():
  claims = JWTClaims(**get_jwt())
  
  page = int(request.args.get('page'))

  jobseeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
  item = jobseeker_container.read_item(item=str(str(claims.user_id)), partition_key=claims.state)
  jobseeker = JobSeeker(**item)
  
  job_posts = []
  analysis_list = None
  
  logger.info(f"request.args.get('liked'): {request.args.get('liked')}")

  if request.args.get('liked') == 'true':
    analysis_list = jobseeker.liked
  else:
    analysis_list = jobseeker.compatibility_analysis_list

  logger.info(f"analysis_list: {len(analysis_list)}")
  
  for analysis in analysis_list:
    city = analysis.job_posting.city
    state = analysis.job_posting.state
    location = "N/A" if city is None or state is None else f"{city}, {state}"

    job_posts.append({
      "id": analysis.id,
      "normalized_score": analysis.normalized_score,
      "job_title": analysis.job_posting.title,
      "location": location
    })

  items_per_page = 10
  pages = len(job_posts) // items_per_page + 1

  job_posts = job_posts[(page-1)*items_per_page:page*items_per_page]
  
  return jsonify(job_posts=job_posts, pages=pages), 200

@app.route('/job-post-listing', methods=['GET'], endpoint='get_job_post_listing')
@role_required('EMPLOYER')
def get_job_post_listing():
  claims = JWTClaims(**get_jwt())
  employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
  item = employer_container.read_item(item=str(claims.user_id), partition_key=claims.state)
  employer = Employer(**item)
  # get job_posting_ids from list of job_postings
  job_post_ids = [job_post.id for job_post in employer.job_postings]
  logger.info(f"job_post_ids: {job_post_ids}")

  job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)

  query = '''
    SELECT ca.job_posting.id, ca.job_posting.title, ca.job_posting.city as city, ca.job_posting.state as state
    FROM c
    JOIN ca IN c.compatibility_analysis_list
    WHERE ca.job_posting.id IN ({})
  '''.format(', '.join(['@value{}'.format(i) for i in range(len(job_post_ids))]))

  # Construct the parameters
  parameters = [
    {"name": "@value{}".format(i), "value": val}
    for i, val in enumerate(job_post_ids)
  ]

  items = list(job_seeker_container.query_items(
    query=query,
    parameters=parameters,
    enable_cross_partition_query=True
  ))

  items_sorted = sorted(items, key=lambda x: (x['id'], x['title']))

  job_post_listing = []

  for (id, title, city, state), group in groupby(items_sorted, key=lambda x: (x['id'], x['title'], x['city'], x['state'])):
    location = "N/A" if city is None or state is None else f"{city}, {state}"

    job_post_listing.append({
      "id": id,
      "title": title,
      "location": location,
      "count": sum(1 for _ in group)
    })

  return jsonify(job_post_listing), 200

@app.route('/job-seekers/<job_post_id>', methods=['GET'], endpoint='get_job_seekers_by_job_post')
@role_required('EMPLOYER')
def get_job_seekers_by_job_post(job_post_id):
  job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)

  query = '''
    SELECT ca.job_posting.id, ca.normalized_score, c.username, ca.job_posting.title, ca.id AS analysis_id, c.city, c.state
    FROM c 
    JOIN ca IN c.compatibility_analysis_list 
    WHERE ca.job_posting.id = @job_posting_id
  '''
  # WHERE ca.job_posting.id IN ({})
  # .format(', '.join(['@value{}'.format(i) for i in range(len(job_posting_ids))]))

  # Construct the parameters
  parameters = [
    {"name": "@job_posting_id", "value": job_post_id}
  ]

  # parameters = [
  #   {"name": "@value{}".format(i), "value": val}
  #   for i, val in enumerate(job_posting_ids)
  # ]
  
  # parameters=[
  #   {"name": "@jobPostingIds", "value": job_posting_ids}
  #   # {"name": "@minScore", "value": 20}
  # ]

  job_seekers = list(job_seeker_container.query_items(
    query=query,
    parameters=parameters,
    enable_cross_partition_query=True
  ))

  return jsonify(job_seekers=job_seekers), 200

@app.route('/compatibility-analysis/<id>', methods=['GET'], endpoint='get_compatibility_analysis')
@role_required('EMPLOYER')
def get_compatibility_analysis(id):
  job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)

  # write a query to get the compatibility analysis from a list on the job seeker
  query = '''
    SELECT compatibility_analysis, c.id as job_seeker_id, c.username as username
    FROM c
    JOIN compatibility_analysis IN c.compatibility_analysis_list
    WHERE compatibility_analysis.id = @compatibility_analysis_id
  '''
  item = list(job_seeker_container.query_items(
    query=query,
    parameters=[
      {"name": "@compatibility_analysis_id", "value": id}
    ],
    enable_cross_partition_query=True
  ))[0]

  compatibility_analysis = CompatibilityAnalysis(**item['compatibility_analysis'])
  username = item['username']
  job_seeker_id = item['job_seeker_id']
  job_posting = compatibility_analysis.job_posting
  filename = job_posting.file.filename
  full_analysis = compatibility_analysis.full_analysis
  normalized_score = compatibility_analysis.normalized_score

  delattr(compatibility_analysis, 'job_posting')
  delattr(compatibility_analysis, 'full_analysis')
  delattr(compatibility_analysis, 'id')
  delattr(compatibility_analysis, 'normalized_score')

  return jsonify(
    compatibility_analysis=compatibility_analysis.model_dump(), 
    job_title=job_posting.title,
    job_post_id=job_posting.id,
    employer_id=job_posting.employer_id,
    job_seeker_id=job_seeker_id,
    full_analysis=full_analysis,
    filename=filename,
    username=username,
    normalized_score=normalized_score
  ), 200

@app.route('/job-seeker-compatibility-analysis/<compatibility_analysis_id>', methods=['GET'], endpoint='get_job_seeker_compatibility_analysis')
@role_required('JOB_SEEKER')
def get_job_seeker_compatibility_analysis(compatibility_analysis_id):
  job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)

  # write a query to get the compatibility analysis from a list on the job seeker
  query = '''
    SELECT VALUE a
    FROM c
    JOIN a IN c.compatibility_analysis_list
    WHERE a.id = @compatibility_analysis_id
  '''

  item = list(job_seeker_container.query_items(
    query=query,
    parameters=[
      {"name": "@compatibility_analysis_id", "value": compatibility_analysis_id}
    ],
    enable_cross_partition_query=True
  ))

  if len(item) == 0:
    return jsonify(error="No compatibility analysis found"), 404
  
  compatibility_analysis = CompatibilityAnalysis(**item[0])

  claims = JWTClaims(**get_jwt())

  return jsonify(
    job_post=compatibility_analysis.job_posting.model_dump(),
    job_seeker_id=claims.user_id,
    normalized_score=compatibility_analysis.normalized_score
  ), 200

@app.route("/upload/resume", methods=["POST"], endpoint='upload_resume')
@role_required('JOB_SEEKER')
def upload_resume():
  # Handle file upload
  file = request.files["file"]

  try:
    claims = JWTClaims(**get_jwt())
    directory = f"uploads/resumes/{str(claims.user_id)}"
    # create a directory for the job seeker if it doesn't exist
    if not os.path.exists(directory):
      os.makedirs(directory)

    resume_file = handle_file_upload(file, directory)
    logger.info(f"Resume FileObject: {resume_file.model_dump()}")

    job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
    results = job_seeker_container.read_item(item=str(claims.user_id), partition_key=claims.state)

    job_seeker = JobSeeker(**results)
    job_seeker.resumes.append(resume_file)
    
    job_seeker_container.upsert_item(body=job_seeker.model_dump())

    employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
    items = list(employer_container.query_items(
      query="SELECT job_posting FROM employer JOIN job_posting IN employer.job_postings",
      enable_cross_partition_query=True
    ))

    for item in items:
      job_posting = JobPosting(**item['job_posting'])

      # logger.info(f"Generating a compatibility analysis for {job_seeker.email}: for {job_posting.title} with id {job_posting.id}")
      job = redis_q.enqueue(run_compatibility_analysis, args=(resume_file, job_posting, claims,), timeout=300)

      logger.info(f"Generating compatibility index for: {job_seeker.email} for job posting: {job_posting.title} with RQ JOB_ID: {job.id}")

    return jsonify(
      file_id=resume_file.id,
      file_name=file.filename,
      file_type=magic.from_file(f"{directory}/{file.filename}", mime=True)
    ), 200
  except Exception as e:
    logger.error(f"Error: {e}")
    return jsonify(error=e), 400

@app.route("/upload/job-post", methods=["POST"], endpoint='upload_job_post')
@role_required('EMPLOYER')
def upload_job_post():
  file = request.files["file"]
  
  claims = JWTClaims(**get_jwt())
  
  directory = f"uploads/job-posts/{str(claims.user_id)}"

  # create a directory for the employer if it doesn't exist
  if not os.path.exists(directory):
    os.makedirs(directory)

  try:
    file_path = f"{directory}/{file.filename}"

    job_posting_file = handle_file_upload(file, directory)    

    employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
    item = employer_container.read_item(item=str(claims.user_id), partition_key=claims.state)

    employer = Employer(**item)

    thread = threading.Thread(target=create_job_posting_breakdown, args=(job_posting_file, employer,))
    thread.start()

    return jsonify(
      file_id=job_posting_file.id,
      file_name=file.filename,
      file_type=magic.from_file(file_path, mime=True),
    ), 200
  except Exception as e:
    logger.error(f"Error: {e}")
    return jsonify(
      error=e
    ), 400

@app.route("/create-job-seekers", methods=["POST"])
def create_job_seekers():
  job_seekers = []

  random_users = RandomUser.generate_users(30, {'nat': 'us'})

  for user in random_users:
    job_seeker = JobSeeker(
      id=str(uuid.uuid4()),
      username=user.get_username(),
      city=user.get_city(),
      state=user.get_state(),
      email=user.get_email(),
      password=generate_password_hash("password"),
      roles=['JOB_SEEKER']
    )

    job_seekers.append(job_seeker.model_dump())

    job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
    job_seeker_container.create_item(body=job_seeker.model_dump())

  return jsonify(job_seekers=job_seekers), 200

@app.route("/job-seeker", methods=["PUT"], endpoint='update_job_seeker')
@role_required('JOB_SEEKER')
def update_job_seeker():
  claims = JWTClaims(**get_jwt())

  job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
  item = job_seeker_container.read_item(item=str(claims.user_id), partition_key=claims.state)
  job_seeker = JobSeeker(**item)
  logger.info(f"job_seeker: {job_seeker.model_dump()}")
  job_seeker.password = generate_password_hash(request.json.get('password'))
  job_seeker.role.append('JOB_SEEKER')

  job_seeker_container.upsert_item(body=job_seeker.model_dump())

  return jsonify(job_seeker=job_seeker.model_dump()), 200

@app.route("/create-employers", methods=["POST"])
def create_employers():
  fake = Faker()
  employers = []

  random_users = RandomUser.generate_users(5, {'nat': 'us'})

  for user in random_users:
    employer = Employer(
      id=str(uuid.uuid4()),
      first_name=user.get_first_name(),
      last_name=user.get_last_name(),
      company_name=fake.company(),
      city=user.get_city(),
      state=user.get_state(),
      email=user.get_email()
    )

    employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
    employer_container.create_item(body=employer.model_dump())

    employers.append(employer.model_dump())

  return jsonify(employers=employers), 200

def handle_file_upload(file, directory):
  # get mimetype from extension
  expected_mime_type, _ = mimetypes.guess_type(file.filename)
  logger.info(f"expected_mime_type: {expected_mime_type}")
  
  # file.save(directory)
  file.save(os.path.join(directory, file.filename))

  file_path = f"{directory}/{file.filename}"

  logger.info(f"file_path: {file_path}")

  is_valid = validate_mime_type(file_path, expected_mime_type)

  if not is_valid:
    logger.error('Invalid file MIME type')
    # delete file
    os.remove(file_path)
    raise Exception('Invalid file MIME type')
  
  file_object = client.files.create(file=open(file_path, 'rb'), purpose='assistants')
 
  logger.info(f"openai_file file object: {file_object.model_dump_json()}")

  return file_object

def create_job_posting_breakdown(job_posting_file: FileObject, employer: Employer):
  user_prompt = """
    You've been given a job posting. Generate a json document from the information
    in the job posting. No extra commentary is necessary. Include only the json
    document in the response.
    """
  response = generate_response(user_prompt, str(uuid.uuid4()), "James", BREAKDOWN_EXPERT_ID, [job_posting_file.id])

  extracted_json = extract_json_from_response(response)
  logger.info(f"job posting extracted_json: {extracted_json}")

  job_posting = JobPosting(**extracted_json, id=str(uuid.uuid4()), file=job_posting_file, employer_id=employer.id)

  logger.info(f"job_posting: {job_posting.model_dump_json()}")

  logger.info(f"employer job postings before adding new posting:")
  for posting in employer.job_postings:
    logger.info(f"job posting: {posting.model_dump_json()}")

  employer.job_postings.append(job_posting)

  logger.info(f"employer job postings before adding new posting:")
  for posting in employer.job_postings:
    logger.info(f"job posting: {posting.model_dump_json()}")

  container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)

  container.upsert_item(body=employer.model_dump())

  return job_posting

def create_compatibility_analysis(resume_file: FileObject, job_posting: JobPosting, job_seeker: JobSeeker):
  user_prompt = """
    Create a compatibility index for a job applicant given a resume file and a job
    description file. Consider key factors from the resume and the job description.
    Assign a score to each factor based on how well the resume aligns with the job
    requirements. The evaluation should be basic and simplified, acknowledging that
    it won't capture all the nuances of the match but will provide a general idea of
    compatibility. Please include an analysis of the breakdown in your response.
    Also generate a single JSON object with a breakdown of the compatibility index
    score including the normalized score The normalized score should be rounded up to 
    the neareast whole number and the its key should be normalized_score. Snake case the keys.
    """

  id = str(uuid.uuid4())
  response = generate_response(user_prompt, id, "James", COMPATIBILITY_EXPERT_ID, [resume_file.id, job_posting.file.id])

  # employer_container = cosmos_database.get_container_client(COSMOS_EMPLOYER_CONTAINER_NAME)
  # query = "SELECT job_posting FROM c JOIN job_posting IN c.job_postings WHERE job_posting.file.id = @file_id"
  # results = employer_container.query_items(
  #   query=query,
  #   parameters=[
  #     dict(
  #       name="@file_id",
  #       value=job_posting_file.id,
  #     )
  #   ],
  #   partition_key='Bockenem',
  # )

  #loop through the results and create a JobPosting object
  # job_posting = None
  # for result in results:
  #   job_posting = JobPosting(**result['job_posting'])
  #   logger.info(f"job_posting: {job_posting.model_dump_json()}")

  extracted_json = extract_json_from_response(response)
  logger.info(f"combatibility index extracted_json: {extracted_json}")

  compatibilty_analysis = CompatibilityAnalysis(**extracted_json, full_analysis=response, id=id, job_posting=job_posting)
  logger.info(f"compatibilty_analysis: {compatibilty_analysis.model_dump_json()}")
  # call persistence here
  job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
  
  job_seeker.compatibility_analysis_list.append(compatibilty_analysis)
  job_seeker_container.upsert_item(body=job_seeker.model_dump())
  
def validate_mime_type(file_path, expected_mime_type):
  expected_mime_types = [
    'application/vnd.openxmlformats-officedocument.wordprocessingml.document',
    'application/msword',
    'application/pdf',
    'text/plain',
  ]

  if expected_mime_type not in expected_mime_types:
    return False

  # Check MIME type by reading file content
  actual_mime_type = magic.from_file(file_path, mime=True)
  logger.info(f"actual_mime_type: {actual_mime_type}")
  return actual_mime_type == expected_mime_type

# --------------------------------------------------------------
# Define compatibility expert assistant
# --------------------------------------------------------------
def create_compatibility_expert(categories):
  """
  You currently cannot set the temperature for Assistant via the API.
  """
  assistant = client.beta.assistants.create(
    name="Candidate Compatibility Expert",
    instructions=f"""You'll be given two files. A resume and a job description.
    Your task will be to analyze the candidate's resume and the job description, then
    calculate the compatibility index for the candidate in the role in the job description.
    Break down the evaluation based on the following categories: {', '.join(categories)}.
    Assign a score from 0 to 10 for each category based on the alignment of the candidate's
    resume with the job requirements. Sum these scores to provide an overall
    compatibility index and normalize the score to a 100 point scale. 
    Round the score up to the nearest whole number. Keep in mind
    the scoring details provided in the user prompt, and consider the nuances and
    limitations of this simplified scoring method. Also, provide a breakdown of the
    job description. Conclude with insights into the compatibility index, noting that
    it's a rough estimate and the actual suitability of the candidate for the role
    may vary based on unquantifiable aspects such as adaptability and learning potential.""",
    tools=[{"type": "retrieval"}],
    model="gpt-4-1106-preview"
  )

  logger.info(f"Assistant: {assistant.model_dump_json()}")
  # call persistence here

  return assistant

# --------------------------------------------------------------
# Create job description breakdown expert assistant
# --------------------------------------------------------------
def create_job_posting_breakdown_expert(keys, job_posting_file):
  """
  You currently cannot set the temperature for Assistant via the API.
  """
  assistant = client.beta.assistants.create(
    name="Job Description Breakdown Expert",
    instructions=f"""You'll be given a file containing a job description.
    Your task will be to analyze the job description, and generate a json document
    with the following keys: {', '.join(keys)} based on the information in the
    job description.""",
    tools=[{"type": "retrieval"}],
    model="gpt-4-1106-preview"
  )
  return assistant

def extract_json_from_response(response):
  # Extracting the JSON part (this would be adjusted based on the actual response format)
  json_start = response.find('```json') + len('```json')
  json_end = response.find('```', json_start)
  json_part = response[json_start:json_end].strip()

  # Parsing the JSON string to a Python dictionary
  try:
    json_object = json.loads(json_part)
  except json.JSONDecodeError:
    json_object = None

  return json_object

# --------------------------------------------------------------
# Thread management
# --------------------------------------------------------------
def check_if_thread_exists(shelf_id):
  with shelve.open("threads_db") as threads_shelf:
    return threads_shelf.get(shelf_id, None)

def store_thread(shelf_id, thread_id):
  with shelve.open("threads_db", writeback=True) as threads_shelf:
    threads_shelf[shelf_id] = thread_id

# --------------------------------------------------------------
# Run assistant
# --------------------------------------------------------------
def run_assistant(thread, assistant):
  # Run the assistant
  run = client.beta.threads.runs.create(
    thread_id=thread.id,
    assistant_id=assistant.id,
  )

  # Wait for completion
  while run.status != "completed":
    # Be nice to the API
    time.sleep(0.5)
    run = client.beta.threads.runs.retrieve(thread_id=thread.id, run_id=run.id)

  logger.info(f"Run: {run.model_dump_json()}")
  # call persistence here

  # Retrieve the Messages
  messages = client.beta.threads.messages.list(thread_id=thread.id)
  logger.info(f"Message: {messages.data[0].model_dump_json()}")
  # call persistence here

  new_message = messages.data[0].content[0].text.value
  
  logger.info(f"Generated message: {new_message}")
  
  return new_message

# --------------------------------------------------------------
# Generate response
# --------------------------------------------------------------
def generate_response(message_body, shelf_id, name, assistant_id, file_ids=None):
  # Check if there is already a thread_id for the wa_id
  thread_id = check_if_thread_exists(shelf_id)

  # If a thread doesn't exist, create one and store it
  if thread_id is None:
    print(f"Creating new thread for {name} with shelf_id {shelf_id}")
    thread = client.beta.threads.create()
    store_thread(shelf_id, thread.id)
    thread_id = thread.id

  # Otherwise, retrieve the existing thread
  else:
    print(f"Retrieving existing thread for {name} with shelf_id {shelf_id}")
    thread = client.beta.threads.retrieve(thread_id)

  logger.info(f"Thread: {thread.model_dump_json()}")
  # call persistence here

  # Add message to thread
  message = client.beta.threads.messages.create(
    thread_id=thread_id,
    role="user",
    content=message_body,
  )

  logger.info(f"Thread message: {message.model_dump_json()}")

  # Retrieve the Assistant
  # assistant = client.beta.assistants.retrieve(assistant_id)

  assistant = client.beta.assistants.update(
    assistant_id=assistant_id,
    file_ids=file_ids
  )

  logger.info(f"Assistant: {assistant.model_dump_json()}")
  # call persistence here

  # Run the assistant and get the new message
  # new_message = run_assistant(thread, assistant.id)
  # print(f"To {name}:", new_message)
  # return new_message
  return run_assistant(thread, assistant)

if __name__ == "__main__":
  from geventwebsocket.handler import WebSocketHandler
  from gevent.pywsgi import WSGIServer
  # from gevent import monkey
  # monkey.patch_all()

  logger.info('Starting server...')
  
  http_server = WSGIServer(('67.205.161.189', 8081),
                          app,
                          handler_class=WebSocketHandler)

  http_server.serve_forever()  

```````

`bumble-for-jobs/requirements.txt`:

```````txt
annotated-types==0.6.0
anyio==4.2.0
azure-core==1.30.0
azure-cosmos==4.5.1
bidict==0.22.1
blinker==1.7.0
certifi==2023.11.17
charset-normalizer==3.3.2
click==8.1.7
distro==1.9.0
dnspython==2.6.1
email_validator==2.1.1
Faker==22.6.0
Flask==3.0.1
Flask-Cors==4.0.0
Flask-JWT-Extended==4.6.0
Flask-SocketIO==5.3.6
Flask-SQLAlchemy==3.1.1
gevent==23.9.1
gevent-websocket==0.10.1
greenlet==3.0.3
h11==0.14.0
httpcore==1.0.2
httpx==0.26.0
idna==3.6
itsdangerous==2.1.2
Jinja2==3.1.3
lxml==5.1.0
MarkupSafe==2.1.4
numpy==1.26.3
openai==1.10.0
pandas==2.2.0
pandas-stubs==2.1.4.231227
py-healthcheck==1.10.1
pydantic==2.5.3
pydantic_core==2.14.6
PyJWT==2.8.0
python-dateutil==2.8.2
python-docx==1.1.0
python-dotenv==1.0.1
python-engineio==4.8.2
python-magic==0.4.27
python-socketio==5.11.0
pytz==2023.4
randomuser==1.6
redis==5.0.1
requests==2.31.0
rq==1.15.1
simple-websocket==1.0.0
six==1.16.0
sniffio==1.3.0
SQLAlchemy==2.0.25
tqdm==4.66.1
types-pytz==2023.4.0.20240130
typing_extensions==4.9.0
tzdata==2023.4
urllib3==2.2.0
Werkzeug==3.0.1
wsproto==1.2.0
zope.event==5.0
zope.interface==6.1

```````

`bumble-for-jobs/jobs.py`:

```````py
import argparse
import json
import logging
import os
import shelve
import time
import uuid
import sys

from openai import OpenAI
from models import CompatibilityAnalysis, JobPosting, JobSeeker, JWTClaims
from openai.types import FileObject
from dotenv import load_dotenv
from azure.cosmos import CosmosClient

# Create a parser for the command-line arguments
# e.g. python your_script.py --env .env.prod
parser = argparse.ArgumentParser(description='Loads variables from the specified .env file and prints them.')
parser.add_argument('--env', type=str, default='.env.dev', help='The .env file to load')
args = parser.parse_args()
# Load the .env file specified in the command-line arguments
load_dotenv(args.env)

OPENAI_API_KEY = os.getenv("OPENAI_API_KEY")
COSMOS_DB_URL = os.getenv("COSMOS_DB_URL")
COSMOS_DB_CREDENTIAL = os.getenv("COSMOS_DB_CREDENTIAL")
COSMOS_DB_NAME = os.getenv("COSMOS_DB_NAME")
COSMOS_EMPLOYER_CONTAINER_NAME = os.getenv("COSMOS_EMPLOYER_CONTAINER_NAME")
COSMOS_EMPLOYER_PARTITION_KEY_PATH = os.getenv("COSMOS_EMPLOYER_PARTITION_KEY_PATH")
COSMOS_JOB_SEEKER_CONTAINER_NAME = os.getenv("COSMOS_JOB_SEEKER_CONTAINER_NAME")
COSMOS_JOB_SEEKER_PARTITION_KEY_PATH = os.getenv("COSMOS_JOB_SEEKER_PARTITION_KEY_PATH")
COMPATIBILITY_EXPERT_ID = os.getenv("COMPATIBILITY_EXPERT_ID")

client = OpenAI(api_key=OPENAI_API_KEY)

cosmos_client = CosmosClient(url=COSMOS_DB_URL, credential=COSMOS_DB_CREDENTIAL)
cosmos_database = cosmos_client.get_database_client(COSMOS_DB_NAME)

logging.basicConfig(
  stream=sys.stderr,
  level=logging.INFO,
  format='%(levelname)s:%(asctime)s:%(message)s'
)

logger = logging.getLogger(__name__)

def run_compatibility_analysis(resume_file: FileObject, job_posting: JobPosting, jwt_claims: JWTClaims):
  user_prompt = """
    Create a compatibility index for a job applicant given a resume file and a job
    description file. Consider key factors from the resume and the job description.
    Assign a score to each factor based on how well the resume aligns with the job
    requirements. The evaluation should be basic and simplified, acknowledging that
    it won't capture all the nuances of the match but will provide a general idea of
    compatibility. Please include an analysis of the breakdown in your response.
    Also generate a single JSON object with a breakdown of the compatibility index
    score including the normalized score The normalized score should be rounded up to 
    the neareast whole number and the its key should be normalized_score. Snake case the keys.
    """

  job_seeker_container = cosmos_database.get_container_client(COSMOS_JOB_SEEKER_CONTAINER_NAME)
  results = job_seeker_container.read_item(item=jwt_claims.user_id, partition_key=jwt_claims.state)

  job_seeker = JobSeeker(**results)

  id = str(uuid.uuid4())
  response = generate_response(user_prompt, id, "James", COMPATIBILITY_EXPERT_ID, [resume_file.id, job_posting.file.id])

  extracted_json = extract_json_from_response(response)
  logger.info(f"combatibility index extracted_json: {extracted_json}")

  compatibilty_analysis = CompatibilityAnalysis(**extracted_json, full_analysis=response, id=id, job_posting=job_posting)
  logger.info(f"compatibilty_analysis: {compatibilty_analysis.model_dump_json()}")

  job_seeker.compatibility_analysis_list.append(compatibilty_analysis)
  job_seeker_container.upsert_item(body=job_seeker.model_dump())

# --------------------------------------------------------------
# Generate response
# --------------------------------------------------------------
def generate_response(message_body, shelf_id, name, assistant_id, file_ids=None):
  # Check if there is already a thread_id for the wa_id
  thread_id = check_if_thread_exists(shelf_id)

  # If a thread doesn't exist, create one and store it
  if thread_id is None:
    print(f"Creating new thread for {name} with shelf_id {shelf_id}")
    thread = client.beta.threads.create()
    store_thread(shelf_id, thread.id)
    thread_id = thread.id

  # Otherwise, retrieve the existing thread
  else:
    print(f"Retrieving existing thread for {name} with shelf_id {shelf_id}")
    thread = client.beta.threads.retrieve(thread_id)

  logger.info(f"Thread: {thread.model_dump_json()}")
  # call persistence here

  # Add message to thread
  message = client.beta.threads.messages.create(
    thread_id=thread_id,
    role="user",
    content=message_body,
  )

  logger.info(f"Thread message: {message.model_dump_json()}")

  # Retrieve the Assistant
  # assistant = client.beta.assistants.retrieve(assistant_id)

  assistant = client.beta.assistants.update(
    assistant_id=assistant_id,
    file_ids=file_ids
  )

  logger.info(f"Assistant: {assistant.model_dump_json()}")
  # call persistence here

  # Run the assistant and get the new message
  # new_message = run_assistant(thread, assistant.id)
  # print(f"To {name}:", new_message)
  # return new_message
  return run_assistant(thread, assistant)

# --------------------------------------------------------------
# Run assistant
# --------------------------------------------------------------
def run_assistant(thread, assistant):
  # Run the assistant
  run = client.beta.threads.runs.create(
    thread_id=thread.id,
    assistant_id=assistant.id,
  )

  # Wait for completion
  while run.status != "completed":
    # Be nice to the API
    time.sleep(0.5)
    run = client.beta.threads.runs.retrieve(thread_id=thread.id, run_id=run.id)

  logger.info(f"Run: {run.model_dump_json()}")
  # call persistence here

  # Retrieve the Messages
  messages = client.beta.threads.messages.list(thread_id=thread.id)
  logger.info(f"Message: {messages.data[0].model_dump_json()}")
  # call persistence here

  new_message = messages.data[0].content[0].text.value
  
  logger.info(f"Generated message: {new_message}")
  
  return new_message

# --------------------------------------------------------------
# Thread management
# --------------------------------------------------------------
def check_if_thread_exists(shelf_id):
  with shelve.open("threads_db") as threads_shelf:
    return threads_shelf.get(shelf_id, None)

def store_thread(shelf_id, thread_id):
  with shelve.open("threads_db", writeback=True) as threads_shelf:
    threads_shelf[shelf_id] = thread_id

def extract_json_from_response(response):
  # Extracting the JSON part (this would be adjusted based on the actual response format)
  json_start = response.find('```json') + len('```json')
  json_end = response.find('```', json_start)
  json_part = response[json_start:json_end].strip()

  # Parsing the JSON string to a Python dictionary
  try:
    json_object = json.loads(json_part)
  except json.JSONDecodeError:
    json_object = None

  return json_object
```````


When looking for optimization opportunities, consider:
- Algorithm complexity and big O analysis 
- Expensive operations like disk/network I/O
- Unnecessary iterations or computations
- Repeated calculations of the same value 
- Inefficient data structures or data types
- Opportunities to cache or memoize results
- Parallelization with threads/async 
- More efficient built-in functions or libraries
- Query or code paths that can be short-circuited
- Reducing memory allocations and copying
- Compiler or interpreter optimizations to leverage

For each potential improvement, provide:
1. File path and line number(s) 
2. Description of the issue/inefficiency
3. Estimated impact on performance 
4. Specific suggestions for optimization

Then update the code with your changes. Be sure to maintain readability and organization. Minor optimizations that significantly reduce clarity are not worth it.

Add benchmarks if possible to quantify the performance improvements. Document any new usage constraints (e.g. increased memory requirements).

Try to prioritize the changes that will have the largest impact on typical usage scenarios based on your understanding of the codebase. Let me know if you have any questions!