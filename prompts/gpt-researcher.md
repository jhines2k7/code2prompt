Project Path: ../gpt-researcher/

I'd like your help understanding this codebase. Please analyze the code thoroughly and provide an overview of the following aspects:

Source Tree:
```
gpt-researcher
├── README-zh_CN.md
├── poetry.lock
├── examples
│   └── sample_report.py
├── main.py
├── poetry.toml
├── LICENSE
├── gpt_researcher
│   ├── master
│   │   ├── agent.py
│   │   ├── __init__.py
│   │   ├── prompts.py
│   │   └── functions.py
│   ├── utils
│   │   ├── __init__.py
│   │   ├── validators.py
│   │   ├── enum.py
│   │   └── llm.py
│   ├── context
│   │   ├── retriever.py
│   │   ├── __init__.py
│   │   └── compression.py
│   ├── llm_provider
│   │   ├── google
│   │   │   ├── __init__.py
│   │   │   └── google.py
│   │   ├── __init__.py
│   │   ├── azureopenai
│   │   │   ├── azureopenai.py
│   │   │   └── __init__.py
│   │   └── openai
│   │       ├── __init__.py
│   │       └── openai.py
│   ├── scraper
│   │   ├── newspaper
│   │   │   ├── __init__.py
│   │   │   └── newspaper.py
│   │   ├── pymupdf
│   │   │   ├── pymupdf.py
│   │   │   └── __init__.py
│   │   ├── beautiful_soup
│   │   │   ├── __init__.py
│   │   │   └── beautiful_soup.py
│   │   ├── web_base_loader
│   │   │   ├── __init__.py
│   │   │   └── web_base_loader.py
│   │   ├── arxiv
│   │   │   ├── __init__.py
│   │   │   └── arxiv.py
│   │   ├── __init__.py
│   │   └── scraper.py
│   ├── __init__.py
│   ├── config
│   │   ├── config.py
│   │   └── __init__.py
│   ├── README.md
│   ├── memory
│   │   ├── __init__.py
│   │   └── embeddings.py
│   └── retrievers
│       ├── searx
│       │   ├── __init__.py
│       │   └── searx.py
│       ├── google
│       │   ├── __init__.py
│       │   └── google.py
│       ├── tavily_news
│       │   ├── tavily_news.py
│       │   └── __init__.py
│       ├── __init__.py
│       ├── tavily_search
│       │   ├── __init__.py
│       │   └── tavily_search.py
│       ├── bing
│       │   ├── __init__.py
│       │   └── bing.py
│       ├── duckduckgo
│       │   ├── __init__.py
│       │   └── duckduckgo.py
│       ├── serper
│       │   ├── serper.py
│       │   └── __init__.py
│       └── serpapi
│           ├── serpapi.py
│           └── __init__.py
├── docs
│   ├── docs
│   │   ├── contribute.md
│   │   ├── examples
│   │   │   ├── examples.md
│   │   │   └── examples.ipynb
│   │   ├── tavily-api
│   │   │   ├── python-sdk.md
│   │   │   ├── introduction.md
│   │   │   ├── langchain.md
│   │   │   ├── llamaindex.md
│   │   │   └── rest_api.md
│   │   ├── welcome.md
│   │   ├── gpt-researcher
│   │   │   ├── getting-started.md
│   │   │   ├── roadmap.md
│   │   │   ├── introduction.md
│   │   │   ├── pip-package.md
│   │   │   ├── agent_frameworks.md
│   │   │   ├── example.md
│   │   │   ├── config.md
│   │   │   └── troubleshooting.md
│   │   ├── reference
│   │   │   ├── sidebar.json
│   │   │   ├── processing
│   │   │   │   ├── text.md
│   │   │   │   └── html.md
│   │   │   └── config
│   │   │       ├── singleton.md
│   │   │       └── config.md
│   │   └── faq.md
│   ├── package.json
│   ├── sidebars.js
│   ├── src
│   │   ├── components
│   │   │   ├── HomepageFeatures.js
│   │   │   └── HomepageFeatures.module.css
│   │   ├── css
│   │   │   └── custom.css
│   │   └── pages
│   │       ├── index.module.css
│   │       └── index.js
│   ├── static
│   │   └── img
│   │       ├── favicon.ico
│   │       ├── leaderboard.png
│   │       ├── gptresearcher.png
│   │       ├── architecture.png
│   │       ├── banner1.jpg
│   │       ├── examples.png
│   │       └── tavily.png
│   ├── yarn.lock
│   ├── README.md
│   ├── blog
│   │   ├── authors.yml
│   │   ├── 2023-11-12-openai-assistant
│   │   │   ├── diagram-1.png
│   │   │   ├── diagram-assistant.jpeg
│   │   │   └── index.md
│   │   └── 2023-09-22-gpt-researcher
│   │       ├── planner.jpeg
│   │       ├── architecture.png
│   │       └── index.md
│   ├── pydoc-markdown.yml
│   ├── CNAME
│   ├── babel.config.js
│   └── docusaurus.config.js
├── frontend
│   ├── scripts.js
│   ├── static
│   │   ├── travelAgentAvatar.png
│   │   ├── favicon.ico
│   │   ├── mathAgentAvatar.png
│   │   ├── financeAgentAvatar.png
│   │   ├── computerSecurityanalystAvatar.png
│   │   ├── defaultAgentAvatar.JPG
│   │   ├── businessAnalystAgentAvatar.png
│   │   └── academicResearchAgentAvatar.png
│   ├── index.html
│   ├── styles.css
│   └── pdf_styles.css
├── docker-compose.yml
├── CONTRIBUTING.md
├── setup.py
├── README.md
├── CODE_OF_CONDUCT.md
├── pyproject.toml
├── Dockerfile
├── cli.py
├── scraping
│   ├── processing
│   │   ├── __init__.py
│   │   ├── text.py
│   │   └── html.py
│   ├── scrape_skills.py
│   ├── web_scrape.py
│   └── js
│       └── overlay.js
├── requirements.txt
└── backend
    ├── websocket_manager.py
    ├── __init__.py
    ├── server.py
    ├── report_type
    │   ├── __init__.py
    │   ├── detailed_report
    │   │   ├── __init__.py
    │   │   └── detailed_report.py
    │   └── basic_report
    │       ├── __init__.py
    │       └── basic_report.py
    └── utils.py

```



`../gpt-researcher/README-zh_CN.md`:

```````md
# 🔎 GPT Researcher
[![Official Website](https://img.shields.io/badge/Official%20Website-tavily.com-blue?style=flat&logo=world&logoColor=white)](https://tavily.com)
[![Discord Follow](https://dcbadge.vercel.app/api/server/2pFkc83fRq?style=flat)](https://discord.com/invite/2pFkc83fRq)
[![GitHub Repo stars](https://img.shields.io/github/stars/assafelovic/gpt-researcher?style=social)](https://github.com/assafelovic/gpt-researcher)
[![Twitter Follow](https://img.shields.io/twitter/follow/tavilyai?style=social)](https://twitter.com/tavilyai)

-  [English](README.md)
-  [中文](README-zh_CN.md)


**GPT Researcher 是一个智能体代理，专为各种任务的综合在线研究而设计。**

代理可以生成详细、正式且客观的研究报告，并提供自定义选项，专注于相关资源、结构框架和经验报告。受最近发表的[Plan-and-Solve](https://arxiv.org/abs/2305.04091) 和[RAG](https://arxiv.org/abs/2005.11401) 论文的启发，GPT Researcher 解决了速度、确定性和可靠性等问题，通过并行化的代理运行，而不是同步操作，提供了更稳定的性能和更高的速度。

**我们的使命是利用人工智能的力量，为个人和组织提供准确、客观和事实的信息。**

## 为什么选择GPT Researcher?

- 因为人工研究任务形成客观结论可能需要时间和经历，有时甚至需要数周才能找到正确的资源和信息。
- 目前的LLM是根据历史和过时的信息进行训练的，存在严重的幻觉风险，因此几乎无法胜任研究任务。
- 网络搜索的解决方案（例如 ChatGPT + Web 插件）仅考虑有限的资源和内容，在某些情况下会导致肤浅的结论或不客观的答案。
- 只使用部分资源可能会在确定研究问题或任务的正确结论时产生偏差。

## 架构
主要思想是运行“**计划者**”和“**执行**”代理，而**计划者**生成问题进行研究，“**执行**”代理根据每个生成的研究问题寻找最相关的信息。最后，“**计划者**”过滤和聚合所有相关信息并创建研究报告。<br /> <br /> 
代理同时利用 gpt3.5-turbo 和 gpt-4-turbo（128K 上下文）来完成一项研究任务。我们仅在必要时使用这两种方法对成本进行优化。**研究任务平均耗时约 3 分钟，成本约为 ~0.1 美元**。

<div align="center">
<img align="center" height="500" src="https://cowriter-images.s3.amazonaws.com/architecture.png">
</div>


详细说明:
* 根据研究搜索或任务创建特定领域的代理。
* 生成一组研究问题，这些问题共同形成答案对任何给定任务的客观意见。
* 针对每个研究问题，触发一个爬虫代理，从在线资源中搜索与给定任务相关的信息。
* 对于每一个抓取的资源，根据相关信息进行汇总，并跟踪其来源。
* 最后，对所有汇总的资料来源进行过滤和汇总，并生成最终研究报告。

## 演示
https://github.com/assafelovic/gpt-researcher/assets/13554167/a00c89a6-a295-4dd0-b58d-098a31c40fda

## 教程
 - [运行原理](https://docs.tavily.com/blog/building-gpt-researcher)
 - [如何安装](https://www.loom.com/share/04ebffb6ed2a4520a27c3e3addcdde20?sid=da1848e8-b1f1-42d1-93c3-5b0b9c3b24ea)
 - [现场演示](https://www.loom.com/share/6a3385db4e8747a1913dd85a7834846f?sid=a740fd5b-2aa3-457e-8fb7-86976f59f9b8)

## 特性
- 📝 生成研究问题、大纲、资源和课题报告
- 🌐 每项研究汇总超过20个网络资源，形成客观和真实的结论
- 🖥️ 包括易于使用的web界面 (HTML/CSS/JS)
- 🔍 支持JavaScript网络资源抓取功能
- 📂 追踪访问过和使用过的网络资源和来源
- 📄 将研究报告导出为PDF或其他格式...

## 📖 文档

请参阅[此处](https://docs.tavily.com/docs/gpt-researcher/getting-started)，了解完整文档：

- 入门（安装、设置环境、简单示例）
- 操作示例（演示、集成、docker 支持）
- 参考资料（API完整文档）
- Tavily 应用程序接口集成（核心概念的高级解释）

## 快速开始
> **步骤 0** - 安装 Python 3.11 或更高版本。[参见此处](https://www.tutorialsteacher.com/python/install-python) 获取详细指南。

<br />

> **步骤 1** - 下载项目

```bash
$ git clone https://github.com/assafelovic/gpt-researcher.git
$ cd gpt-researcher
```

<br />

> **步骤2** -安装依赖项
```bash
$ pip install -r requirements.txt
```
<br />

> **第 3 步** - 使用 OpenAI 密钥和 Tavily API 密钥创建 .env 文件，或直接导出该文件

```bash
$ export OPENAI_API_KEY={Your OpenAI API Key here}
```
```bash
$ export TAVILY_API_KEY={Your Tavily API Key here}
```

- **LLM，我们推荐使用 [OpenAI GPT](https://platform.openai.com/docs/guides/gpt)**，但您也可以使用 [Langchain Adapter](https://python.langchain.com/docs/guides/adapters/openai) 支持的任何其他 LLM 模型（包括开源），只需在 config/config.py 中更改 llm 模型和提供者即可。请按照 [这份指南](https://python.langchain.com/docs/integrations/llms/) 学习如何将 LLM 与 Langchain 集成。
- **对于搜索引擎，我们推荐使用 [Tavily Search API](https://app.tavily.com)（已针对 LLM 进行优化）**，但您也可以选择其他搜索引擎，只需将 config/config.py 中的搜索提供程序更改为 "duckduckgo"、"googleAPI"、"googleSerp "或 "searx "即可。然后在 config.py 文件中添加相应的 env API 密钥。
- **我们强烈建议使用 [OpenAI GPT](https://platform.openai.com/docs/guides/gpt) 模型和 [Tavily Search API](https://app.tavily.com) 以获得最佳性能。**
<br />

> **第 4 步** - 使用 FastAPI 运行代理

```bash
$ uvicorn main:app --reload
```
<br />

> **第 5 步** - 在任何浏览器上访问 http://localhost:8000，享受研究乐趣！

要了解如何开始使用 Docker 或了解有关功能和服务的更多信息，请访问 [documentation](https://docs.tavily.com) 页面。

## 🚀 贡献
我们非常欢迎您的贡献！如果您感兴趣，请查看 [contributing](CONTRIBUTING.md)。

如果您有兴趣加入我们的任务，请查看我们的 [路线图](https://trello.com/b/3O7KBePw/gpt-researcher-roadmap) 页面，并通过我们的 [Discord 社区](https://discord.gg/2pFkc83fRq) 联系我们。

## 🛡 免责声明

本项目 "GPT Researcher "是一个实验性应用程序，按 "现状 "提供，不做任何明示或暗示的保证。我们根据 MIT 许可分享用于学术目的的代码。本文不提供任何学术建议，也不建议在学术或研究论文中使用。

我们对客观研究主张的看法：
1.  我们抓取系统的全部目的是减少不正确的事实。如何解决？我们抓取的网站越多，错误数据的可能性就越小。我们每项研究都会收集20条信息，它们全部错误的可能性极低。
2. 我们的目标不是消除偏见，而是尽可能减少偏见。**作为一个社区，我们在这里探索最有效的人机互动**。
3. 在研究过程中，人们也容易产生偏见，因为大多数人对自己研究的课题都有自己的看法。这个工具可以搜罗到许多观点，并均匀地解释各种不同的观点，而有偏见的人是绝对读不到这些观点的。

**请注意，使用 GPT-4 语言模型可能会因使用令牌而产生高昂费用**。使用本项目即表示您承认有责任监控和管理自己的令牌使用情况及相关费用。强烈建议您定期检查 OpenAI API 的使用情况，并设置任何必要的限制或警报，以防止发生意外费用。
## ✉️ 支持 / 联系我们
- [社区讨论区](https://discord.gg/spBgZmm3Xe)
- 我们的邮箱: support@tavily.com

```````




`../gpt-researcher/poetry.lock`:

```````lock
# This file is automatically @generated by Poetry 1.8.2 and should not be changed by hand.

[[package]]
name = "aiofiles"
version = "23.2.1"
description = "File support for asyncio."
optional = false
python-versions = ">=3.7"
files = [
    {file = "aiofiles-23.2.1-py3-none-any.whl", hash = "sha256:19297512c647d4b27a2cf7c34caa7e405c0d60b5560618a29a9fe027b18b0107"},
    {file = "aiofiles-23.2.1.tar.gz", hash = "sha256:84ec2218d8419404abcb9f0c02df3f34c6e0a68ed41072acfb1cef5cbc29051a"},
]

[[package]]
name = "aiohttp"
version = "3.9.1"
description = "Async http client/server framework (asyncio)"
optional = false
python-versions = ">=3.8"
files = [
    {file = "aiohttp-3.9.1-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:e1f80197f8b0b846a8d5cf7b7ec6084493950d0882cc5537fb7b96a69e3c8590"},
    {file = "aiohttp-3.9.1-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:c72444d17777865734aa1a4d167794c34b63e5883abb90356a0364a28904e6c0"},
    {file = "aiohttp-3.9.1-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:9b05d5cbe9dafcdc733262c3a99ccf63d2f7ce02543620d2bd8db4d4f7a22f83"},
    {file = "aiohttp-3.9.1-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:5c4fa235d534b3547184831c624c0b7c1e262cd1de847d95085ec94c16fddcd5"},
    {file = "aiohttp-3.9.1-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:289ba9ae8e88d0ba16062ecf02dd730b34186ea3b1e7489046fc338bdc3361c4"},
    {file = "aiohttp-3.9.1-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:bff7e2811814fa2271be95ab6e84c9436d027a0e59665de60edf44e529a42c1f"},
    {file = "aiohttp-3.9.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:81b77f868814346662c96ab36b875d7814ebf82340d3284a31681085c051320f"},
    {file = "aiohttp-3.9.1-cp310-cp310-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:3b9c7426923bb7bd66d409da46c41e3fb40f5caf679da624439b9eba92043fa6"},
    {file = "aiohttp-3.9.1-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:8d44e7bf06b0c0a70a20f9100af9fcfd7f6d9d3913e37754c12d424179b4e48f"},
    {file = "aiohttp-3.9.1-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:22698f01ff5653fe66d16ffb7658f582a0ac084d7da1323e39fd9eab326a1f26"},
    {file = "aiohttp-3.9.1-cp310-cp310-musllinux_1_1_ppc64le.whl", hash = "sha256:ca7ca5abfbfe8d39e653870fbe8d7710be7a857f8a8386fc9de1aae2e02ce7e4"},
    {file = "aiohttp-3.9.1-cp310-cp310-musllinux_1_1_s390x.whl", hash = "sha256:8d7f98fde213f74561be1d6d3fa353656197f75d4edfbb3d94c9eb9b0fc47f5d"},
    {file = "aiohttp-3.9.1-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:5216b6082c624b55cfe79af5d538e499cd5f5b976820eac31951fb4325974501"},
    {file = "aiohttp-3.9.1-cp310-cp310-win32.whl", hash = "sha256:0e7ba7ff228c0d9a2cd66194e90f2bca6e0abca810b786901a569c0de082f489"},
    {file = "aiohttp-3.9.1-cp310-cp310-win_amd64.whl", hash = "sha256:c7e939f1ae428a86e4abbb9a7c4732bf4706048818dfd979e5e2839ce0159f23"},
    {file = "aiohttp-3.9.1-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:df9cf74b9bc03d586fc53ba470828d7b77ce51b0582d1d0b5b2fb673c0baa32d"},
    {file = "aiohttp-3.9.1-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:ecca113f19d5e74048c001934045a2b9368d77b0b17691d905af18bd1c21275e"},
    {file = "aiohttp-3.9.1-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:8cef8710fb849d97c533f259103f09bac167a008d7131d7b2b0e3a33269185c0"},
    {file = "aiohttp-3.9.1-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:bea94403a21eb94c93386d559bce297381609153e418a3ffc7d6bf772f59cc35"},
    {file = "aiohttp-3.9.1-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:91c742ca59045dce7ba76cab6e223e41d2c70d79e82c284a96411f8645e2afff"},
    {file = "aiohttp-3.9.1-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:6c93b7c2e52061f0925c3382d5cb8980e40f91c989563d3d32ca280069fd6a87"},
    {file = "aiohttp-3.9.1-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:ee2527134f95e106cc1653e9ac78846f3a2ec1004cf20ef4e02038035a74544d"},
    {file = "aiohttp-3.9.1-cp311-cp311-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:11ff168d752cb41e8492817e10fb4f85828f6a0142b9726a30c27c35a1835f01"},
    {file = "aiohttp-3.9.1-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:b8c3a67eb87394386847d188996920f33b01b32155f0a94f36ca0e0c635bf3e3"},
    {file = "aiohttp-3.9.1-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:c7b5d5d64e2a14e35a9240b33b89389e0035e6de8dbb7ffa50d10d8b65c57449"},
    {file = "aiohttp-3.9.1-cp311-cp311-musllinux_1_1_ppc64le.whl", hash = "sha256:69985d50a2b6f709412d944ffb2e97d0be154ea90600b7a921f95a87d6f108a2"},
    {file = "aiohttp-3.9.1-cp311-cp311-musllinux_1_1_s390x.whl", hash = "sha256:c9110c06eaaac7e1f5562caf481f18ccf8f6fdf4c3323feab28a93d34cc646bd"},
    {file = "aiohttp-3.9.1-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:d737e69d193dac7296365a6dcb73bbbf53bb760ab25a3727716bbd42022e8d7a"},
    {file = "aiohttp-3.9.1-cp311-cp311-win32.whl", hash = "sha256:4ee8caa925aebc1e64e98432d78ea8de67b2272252b0a931d2ac3bd876ad5544"},
    {file = "aiohttp-3.9.1-cp311-cp311-win_amd64.whl", hash = "sha256:a34086c5cc285be878622e0a6ab897a986a6e8bf5b67ecb377015f06ed316587"},
    {file = "aiohttp-3.9.1-cp312-cp312-macosx_10_9_universal2.whl", hash = "sha256:f800164276eec54e0af5c99feb9494c295118fc10a11b997bbb1348ba1a52065"},
    {file = "aiohttp-3.9.1-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:500f1c59906cd142d452074f3811614be04819a38ae2b3239a48b82649c08821"},
    {file = "aiohttp-3.9.1-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:0b0a6a36ed7e164c6df1e18ee47afbd1990ce47cb428739d6c99aaabfaf1b3af"},
    {file = "aiohttp-3.9.1-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:69da0f3ed3496808e8cbc5123a866c41c12c15baaaead96d256477edf168eb57"},
    {file = "aiohttp-3.9.1-cp312-cp312-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:176df045597e674fa950bf5ae536be85699e04cea68fa3a616cf75e413737eb5"},
    {file = "aiohttp-3.9.1-cp312-cp312-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:b796b44111f0cab6bbf66214186e44734b5baab949cb5fb56154142a92989aeb"},
    {file = "aiohttp-3.9.1-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:f27fdaadce22f2ef950fc10dcdf8048407c3b42b73779e48a4e76b3c35bca26c"},
    {file = "aiohttp-3.9.1-cp312-cp312-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:bcb6532b9814ea7c5a6a3299747c49de30e84472fa72821b07f5a9818bce0f66"},
    {file = "aiohttp-3.9.1-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:54631fb69a6e44b2ba522f7c22a6fb2667a02fd97d636048478db2fd8c4e98fe"},
    {file = "aiohttp-3.9.1-cp312-cp312-musllinux_1_1_i686.whl", hash = "sha256:4b4c452d0190c5a820d3f5c0f3cd8a28ace48c54053e24da9d6041bf81113183"},
    {file = "aiohttp-3.9.1-cp312-cp312-musllinux_1_1_ppc64le.whl", hash = "sha256:cae4c0c2ca800c793cae07ef3d40794625471040a87e1ba392039639ad61ab5b"},
    {file = "aiohttp-3.9.1-cp312-cp312-musllinux_1_1_s390x.whl", hash = "sha256:565760d6812b8d78d416c3c7cfdf5362fbe0d0d25b82fed75d0d29e18d7fc30f"},
    {file = "aiohttp-3.9.1-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:54311eb54f3a0c45efb9ed0d0a8f43d1bc6060d773f6973efd90037a51cd0a3f"},
    {file = "aiohttp-3.9.1-cp312-cp312-win32.whl", hash = "sha256:85c3e3c9cb1d480e0b9a64c658cd66b3cfb8e721636ab8b0e746e2d79a7a9eed"},
    {file = "aiohttp-3.9.1-cp312-cp312-win_amd64.whl", hash = "sha256:11cb254e397a82efb1805d12561e80124928e04e9c4483587ce7390b3866d213"},
    {file = "aiohttp-3.9.1-cp38-cp38-macosx_10_9_universal2.whl", hash = "sha256:8a22a34bc594d9d24621091d1b91511001a7eea91d6652ea495ce06e27381f70"},
    {file = "aiohttp-3.9.1-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:598db66eaf2e04aa0c8900a63b0101fdc5e6b8a7ddd805c56d86efb54eb66672"},
    {file = "aiohttp-3.9.1-cp38-cp38-macosx_11_0_arm64.whl", hash = "sha256:2c9376e2b09895c8ca8b95362283365eb5c03bdc8428ade80a864160605715f1"},
    {file = "aiohttp-3.9.1-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:41473de252e1797c2d2293804e389a6d6986ef37cbb4a25208de537ae32141dd"},
    {file = "aiohttp-3.9.1-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:9c5857612c9813796960c00767645cb5da815af16dafb32d70c72a8390bbf690"},
    {file = "aiohttp-3.9.1-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:ffcd828e37dc219a72c9012ec44ad2e7e3066bec6ff3aaa19e7d435dbf4032ca"},
    {file = "aiohttp-3.9.1-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:219a16763dc0294842188ac8a12262b5671817042b35d45e44fd0a697d8c8361"},
    {file = "aiohttp-3.9.1-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:f694dc8a6a3112059258a725a4ebe9acac5fe62f11c77ac4dcf896edfa78ca28"},
    {file = "aiohttp-3.9.1-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:bcc0ea8d5b74a41b621ad4a13d96c36079c81628ccc0b30cfb1603e3dfa3a014"},
    {file = "aiohttp-3.9.1-cp38-cp38-musllinux_1_1_i686.whl", hash = "sha256:90ec72d231169b4b8d6085be13023ece8fa9b1bb495e4398d847e25218e0f431"},
    {file = "aiohttp-3.9.1-cp38-cp38-musllinux_1_1_ppc64le.whl", hash = "sha256:cf2a0ac0615842b849f40c4d7f304986a242f1e68286dbf3bd7a835e4f83acfd"},
    {file = "aiohttp-3.9.1-cp38-cp38-musllinux_1_1_s390x.whl", hash = "sha256:0e49b08eafa4f5707ecfb321ab9592717a319e37938e301d462f79b4e860c32a"},
    {file = "aiohttp-3.9.1-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:2c59e0076ea31c08553e868cec02d22191c086f00b44610f8ab7363a11a5d9d8"},
    {file = "aiohttp-3.9.1-cp38-cp38-win32.whl", hash = "sha256:4831df72b053b1eed31eb00a2e1aff6896fb4485301d4ccb208cac264b648db4"},
    {file = "aiohttp-3.9.1-cp38-cp38-win_amd64.whl", hash = "sha256:3135713c5562731ee18f58d3ad1bf41e1d8883eb68b363f2ffde5b2ea4b84cc7"},
    {file = "aiohttp-3.9.1-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:cfeadf42840c1e870dc2042a232a8748e75a36b52d78968cda6736de55582766"},
    {file = "aiohttp-3.9.1-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:70907533db712f7aa791effb38efa96f044ce3d4e850e2d7691abd759f4f0ae0"},
    {file = "aiohttp-3.9.1-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:cdefe289681507187e375a5064c7599f52c40343a8701761c802c1853a504558"},
    {file = "aiohttp-3.9.1-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:d7481f581251bb5558ba9f635db70908819caa221fc79ee52a7f58392778c636"},
    {file = "aiohttp-3.9.1-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:49f0c1b3c2842556e5de35f122fc0f0b721334ceb6e78c3719693364d4af8499"},
    {file = "aiohttp-3.9.1-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:0d406b01a9f5a7e232d1b0d161b40c05275ffbcbd772dc18c1d5a570961a1ca4"},
    {file = "aiohttp-3.9.1-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:8d8e4450e7fe24d86e86b23cc209e0023177b6d59502e33807b732d2deb6975f"},
    {file = "aiohttp-3.9.1-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:3c0266cd6f005e99f3f51e583012de2778e65af6b73860038b968a0a8888487a"},
    {file = "aiohttp-3.9.1-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:ab221850108a4a063c5b8a70f00dd7a1975e5a1713f87f4ab26a46e5feac5a0e"},
    {file = "aiohttp-3.9.1-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:c88a15f272a0ad3d7773cf3a37cc7b7d077cbfc8e331675cf1346e849d97a4e5"},
    {file = "aiohttp-3.9.1-cp39-cp39-musllinux_1_1_ppc64le.whl", hash = "sha256:237533179d9747080bcaad4d02083ce295c0d2eab3e9e8ce103411a4312991a0"},
    {file = "aiohttp-3.9.1-cp39-cp39-musllinux_1_1_s390x.whl", hash = "sha256:02ab6006ec3c3463b528374c4cdce86434e7b89ad355e7bf29e2f16b46c7dd6f"},
    {file = "aiohttp-3.9.1-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:04fa38875e53eb7e354ece1607b1d2fdee2d175ea4e4d745f6ec9f751fe20c7c"},
    {file = "aiohttp-3.9.1-cp39-cp39-win32.whl", hash = "sha256:82eefaf1a996060602f3cc1112d93ba8b201dbf5d8fd9611227de2003dddb3b7"},
    {file = "aiohttp-3.9.1-cp39-cp39-win_amd64.whl", hash = "sha256:9b05d33ff8e6b269e30a7957bd3244ffbce2a7a35a81b81c382629b80af1a8bf"},
    {file = "aiohttp-3.9.1.tar.gz", hash = "sha256:8fc49a87ac269d4529da45871e2ffb6874e87779c3d0e2ccd813c0899221239d"},
]

[package.dependencies]
aiosignal = ">=1.1.2"
async-timeout = {version = ">=4.0,<5.0", markers = "python_version < \"3.11\""}
attrs = ">=17.3.0"
frozenlist = ">=1.1.1"
multidict = ">=4.5,<7.0"
yarl = ">=1.0,<2.0"

[package.extras]
speedups = ["Brotli", "aiodns", "brotlicffi"]

[[package]]
name = "aiosignal"
version = "1.3.1"
description = "aiosignal: a list of registered asynchronous callbacks"
optional = false
python-versions = ">=3.7"
files = [
    {file = "aiosignal-1.3.1-py3-none-any.whl", hash = "sha256:f8376fb07dd1e86a584e4fcdec80b36b7f81aac666ebc724e2c090300dd83b17"},
    {file = "aiosignal-1.3.1.tar.gz", hash = "sha256:54cd96e15e1649b75d6c87526a6ff0b6c1b0dd3459f43d9ca11d48c339b68cfc"},
]

[package.dependencies]
frozenlist = ">=1.1.0"

[[package]]
name = "annotated-types"
version = "0.6.0"
description = "Reusable constraint types to use with typing.Annotated"
optional = false
python-versions = ">=3.8"
files = [
    {file = "annotated_types-0.6.0-py3-none-any.whl", hash = "sha256:0641064de18ba7a25dee8f96403ebc39113d0cb953a01429249d5c7564666a43"},
    {file = "annotated_types-0.6.0.tar.gz", hash = "sha256:563339e807e53ffd9c267e99fc6d9ea23eb8443c08f112651963e24e22f84a5d"},
]

[[package]]
name = "anyio"
version = "3.7.1"
description = "High level compatibility layer for multiple asynchronous event loop implementations"
optional = false
python-versions = ">=3.7"
files = [
    {file = "anyio-3.7.1-py3-none-any.whl", hash = "sha256:91dee416e570e92c64041bd18b900d1d6fa78dff7048769ce5ac5ddad004fbb5"},
    {file = "anyio-3.7.1.tar.gz", hash = "sha256:44a3c9aba0f5defa43261a8b3efb97891f2bd7d804e0e1f56419befa1adfc780"},
]

[package.dependencies]
exceptiongroup = {version = "*", markers = "python_version < \"3.11\""}
idna = ">=2.8"
sniffio = ">=1.1"

[package.extras]
doc = ["Sphinx", "packaging", "sphinx-autodoc-typehints (>=1.2.0)", "sphinx-rtd-theme (>=1.2.2)", "sphinxcontrib-jquery"]
test = ["anyio[trio]", "coverage[toml] (>=4.5)", "hypothesis (>=4.0)", "mock (>=4)", "psutil (>=5.9)", "pytest (>=7.0)", "pytest-mock (>=3.6.1)", "trustme", "uvloop (>=0.17)"]
trio = ["trio (<0.22)"]

[[package]]
name = "arxiv"
version = "2.0.0"
description = "Python wrapper for the arXiv API: https://arxiv.org/help/api/"
optional = false
python-versions = ">=3.7"
files = [
    {file = "arxiv-2.0.0-py3-none-any.whl", hash = "sha256:d64dd4b020782b91c267bcd3b98a1b9542250ab135fb54a1e298e8364722210c"},
    {file = "arxiv-2.0.0.tar.gz", hash = "sha256:97f910dadf97169793ab3fcf12e75d23cb9dac4dc7c16de8b09492cde179da9f"},
]

[package.dependencies]
feedparser = "6.0.10"
requests = "2.31.0"

[[package]]
name = "async-timeout"
version = "4.0.3"
description = "Timeout context manager for asyncio programs"
optional = false
python-versions = ">=3.7"
files = [
    {file = "async-timeout-4.0.3.tar.gz", hash = "sha256:4640d96be84d82d02ed59ea2b7105a0f7b33abe8703703cd0ab0bf87c427522f"},
    {file = "async_timeout-4.0.3-py3-none-any.whl", hash = "sha256:7405140ff1230c310e51dc27b3145b9092d659ce68ff733fb0cefe3ee42be028"},
]

[[package]]
name = "attrs"
version = "23.1.0"
description = "Classes Without Boilerplate"
optional = false
python-versions = ">=3.7"
files = [
    {file = "attrs-23.1.0-py3-none-any.whl", hash = "sha256:1f28b4522cdc2fb4256ac1a020c78acf9cba2c6b461ccd2c126f3aa8e8335d04"},
    {file = "attrs-23.1.0.tar.gz", hash = "sha256:6279836d581513a26f1bf235f9acd333bc9115683f14f7e8fae46c98fc50e015"},
]

[package.extras]
cov = ["attrs[tests]", "coverage[toml] (>=5.3)"]
dev = ["attrs[docs,tests]", "pre-commit"]
docs = ["furo", "myst-parser", "sphinx", "sphinx-notfound-page", "sphinxcontrib-towncrier", "towncrier", "zope-interface"]
tests = ["attrs[tests-no-zope]", "zope-interface"]
tests-no-zope = ["cloudpickle", "hypothesis", "mypy (>=1.1.1)", "pympler", "pytest (>=4.3.0)", "pytest-mypy-plugins", "pytest-xdist[psutil]"]

[[package]]
name = "beautifulsoup4"
version = "4.12.2"
description = "Screen-scraping library"
optional = false
python-versions = ">=3.6.0"
files = [
    {file = "beautifulsoup4-4.12.2-py3-none-any.whl", hash = "sha256:bd2520ca0d9d7d12694a53d44ac482d181b4ec1888909b035a3dbf40d0f57d4a"},
    {file = "beautifulsoup4-4.12.2.tar.gz", hash = "sha256:492bbc69dca35d12daac71c4db1bfff0c876c00ef4a2ffacce226d4638eb72da"},
]

[package.dependencies]
soupsieve = ">1.2"

[package.extras]
html5lib = ["html5lib"]
lxml = ["lxml"]

[[package]]
name = "brotli"
version = "1.1.0"
description = "Python bindings for the Brotli compression library"
optional = false
python-versions = "*"
files = [
    {file = "Brotli-1.1.0-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:e1140c64812cb9b06c922e77f1c26a75ec5e3f0fb2bf92cc8c58720dec276752"},
    {file = "Brotli-1.1.0-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:c8fd5270e906eef71d4a8d19b7c6a43760c6abcfcc10c9101d14eb2357418de9"},
    {file = "Brotli-1.1.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:1ae56aca0402a0f9a3431cddda62ad71666ca9d4dc3a10a142b9dce2e3c0cda3"},
    {file = "Brotli-1.1.0-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:43ce1b9935bfa1ede40028054d7f48b5469cd02733a365eec8a329ffd342915d"},
    {file = "Brotli-1.1.0-cp310-cp310-manylinux_2_5_i686.manylinux1_i686.manylinux_2_12_i686.manylinux2010_i686.whl", hash = "sha256:7c4855522edb2e6ae7fdb58e07c3ba9111e7621a8956f481c68d5d979c93032e"},
    {file = "Brotli-1.1.0-cp310-cp310-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_12_x86_64.manylinux2010_x86_64.whl", hash = "sha256:38025d9f30cf4634f8309c6874ef871b841eb3c347e90b0851f63d1ded5212da"},
    {file = "Brotli-1.1.0-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:e6a904cb26bfefc2f0a6f240bdf5233be78cd2488900a2f846f3c3ac8489ab80"},
    {file = "Brotli-1.1.0-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:a37b8f0391212d29b3a91a799c8e4a2855e0576911cdfb2515487e30e322253d"},
    {file = "Brotli-1.1.0-cp310-cp310-musllinux_1_1_ppc64le.whl", hash = "sha256:e84799f09591700a4154154cab9787452925578841a94321d5ee8fb9a9a328f0"},
    {file = "Brotli-1.1.0-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:f66b5337fa213f1da0d9000bc8dc0cb5b896b726eefd9c6046f699b169c41b9e"},
    {file = "Brotli-1.1.0-cp310-cp310-win32.whl", hash = "sha256:be36e3d172dc816333f33520154d708a2657ea63762ec16b62ece02ab5e4daf2"},
    {file = "Brotli-1.1.0-cp310-cp310-win_amd64.whl", hash = "sha256:0c6244521dda65ea562d5a69b9a26120769b7a9fb3db2fe9545935ed6735b128"},
    {file = "Brotli-1.1.0-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:a3daabb76a78f829cafc365531c972016e4aa8d5b4bf60660ad8ecee19df7ccc"},
    {file = "Brotli-1.1.0-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:c8146669223164fc87a7e3de9f81e9423c67a79d6b3447994dfb9c95da16e2d6"},
    {file = "Brotli-1.1.0-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:30924eb4c57903d5a7526b08ef4a584acc22ab1ffa085faceb521521d2de32dd"},
    {file = "Brotli-1.1.0-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:ceb64bbc6eac5a140ca649003756940f8d6a7c444a68af170b3187623b43bebf"},
    {file = "Brotli-1.1.0-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:a469274ad18dc0e4d316eefa616d1d0c2ff9da369af19fa6f3daa4f09671fd61"},
    {file = "Brotli-1.1.0-cp311-cp311-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:524f35912131cc2cabb00edfd8d573b07f2d9f21fa824bd3fb19725a9cf06327"},
    {file = "Brotli-1.1.0-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:5b3cc074004d968722f51e550b41a27be656ec48f8afaeeb45ebf65b561481dd"},
    {file = "Brotli-1.1.0-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:19c116e796420b0cee3da1ccec3b764ed2952ccfcc298b55a10e5610ad7885f9"},
    {file = "Brotli-1.1.0-cp311-cp311-musllinux_1_1_ppc64le.whl", hash = "sha256:510b5b1bfbe20e1a7b3baf5fed9e9451873559a976c1a78eebaa3b86c57b4265"},
    {file = "Brotli-1.1.0-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:a1fd8a29719ccce974d523580987b7f8229aeace506952fa9ce1d53a033873c8"},
    {file = "Brotli-1.1.0-cp311-cp311-win32.whl", hash = "sha256:39da8adedf6942d76dc3e46653e52df937a3c4d6d18fdc94a7c29d263b1f5b50"},
    {file = "Brotli-1.1.0-cp311-cp311-win_amd64.whl", hash = "sha256:aac0411d20e345dc0920bdec5548e438e999ff68d77564d5e9463a7ca9d3e7b1"},
    {file = "Brotli-1.1.0-cp312-cp312-macosx_10_9_universal2.whl", hash = "sha256:316cc9b17edf613ac76b1f1f305d2a748f1b976b033b049a6ecdfd5612c70409"},
    {file = "Brotli-1.1.0-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:caf9ee9a5775f3111642d33b86237b05808dafcd6268faa492250e9b78046eb2"},
    {file = "Brotli-1.1.0-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:70051525001750221daa10907c77830bc889cb6d865cc0b813d9db7fefc21451"},
    {file = "Brotli-1.1.0-cp312-cp312-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:7f4bf76817c14aa98cc6697ac02f3972cb8c3da93e9ef16b9c66573a68014f91"},
    {file = "Brotli-1.1.0-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:d0c5516f0aed654134a2fc936325cc2e642f8a0e096d075209672eb321cff408"},
    {file = "Brotli-1.1.0-cp312-cp312-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:6c3020404e0b5eefd7c9485ccf8393cfb75ec38ce75586e046573c9dc29967a0"},
    {file = "Brotli-1.1.0-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:4ed11165dd45ce798d99a136808a794a748d5dc38511303239d4e2363c0695dc"},
    {file = "Brotli-1.1.0-cp312-cp312-musllinux_1_1_i686.whl", hash = "sha256:4093c631e96fdd49e0377a9c167bfd75b6d0bad2ace734c6eb20b348bc3ea180"},
    {file = "Brotli-1.1.0-cp312-cp312-musllinux_1_1_ppc64le.whl", hash = "sha256:7e4c4629ddad63006efa0ef968c8e4751c5868ff0b1c5c40f76524e894c50248"},
    {file = "Brotli-1.1.0-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:861bf317735688269936f755fa136a99d1ed526883859f86e41a5d43c61d8966"},
    {file = "Brotli-1.1.0-cp312-cp312-win32.whl", hash = "sha256:5f4d5ea15c9382135076d2fb28dde923352fe02951e66935a9efaac8f10e81b0"},
    {file = "Brotli-1.1.0-cp312-cp312-win_amd64.whl", hash = "sha256:906bc3a79de8c4ae5b86d3d75a8b77e44404b0f4261714306e3ad248d8ab0951"},
    {file = "Brotli-1.1.0-cp36-cp36m-macosx_10_9_x86_64.whl", hash = "sha256:a090ca607cbb6a34b0391776f0cb48062081f5f60ddcce5d11838e67a01928d1"},
    {file = "Brotli-1.1.0-cp36-cp36m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:2de9d02f5bda03d27ede52e8cfe7b865b066fa49258cbab568720aa5be80a47d"},
    {file = "Brotli-1.1.0-cp36-cp36m-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:2333e30a5e00fe0fe55903c8832e08ee9c3b1382aacf4db26664a16528d51b4b"},
    {file = "Brotli-1.1.0-cp36-cp36m-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:4d4a848d1837973bf0f4b5e54e3bec977d99be36a7895c61abb659301b02c112"},
    {file = "Brotli-1.1.0-cp36-cp36m-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:fdc3ff3bfccdc6b9cc7c342c03aa2400683f0cb891d46e94b64a197910dc4064"},
    {file = "Brotli-1.1.0-cp36-cp36m-musllinux_1_1_aarch64.whl", hash = "sha256:5eeb539606f18a0b232d4ba45adccde4125592f3f636a6182b4a8a436548b914"},
    {file = "Brotli-1.1.0-cp36-cp36m-musllinux_1_1_i686.whl", hash = "sha256:fd5f17ff8f14003595ab414e45fce13d073e0762394f957182e69035c9f3d7c2"},
    {file = "Brotli-1.1.0-cp36-cp36m-musllinux_1_1_ppc64le.whl", hash = "sha256:069a121ac97412d1fe506da790b3e69f52254b9df4eb665cd42460c837193354"},
    {file = "Brotli-1.1.0-cp36-cp36m-musllinux_1_1_x86_64.whl", hash = "sha256:e93dfc1a1165e385cc8239fab7c036fb2cd8093728cbd85097b284d7b99249a2"},
    {file = "Brotli-1.1.0-cp36-cp36m-win32.whl", hash = "sha256:a599669fd7c47233438a56936988a2478685e74854088ef5293802123b5b2460"},
    {file = "Brotli-1.1.0-cp36-cp36m-win_amd64.whl", hash = "sha256:d143fd47fad1db3d7c27a1b1d66162e855b5d50a89666af46e1679c496e8e579"},
    {file = "Brotli-1.1.0-cp37-cp37m-macosx_10_9_x86_64.whl", hash = "sha256:11d00ed0a83fa22d29bc6b64ef636c4552ebafcef57154b4ddd132f5638fbd1c"},
    {file = "Brotli-1.1.0-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:f733d788519c7e3e71f0855c96618720f5d3d60c3cb829d8bbb722dddce37985"},
    {file = "Brotli-1.1.0-cp37-cp37m-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:929811df5462e182b13920da56c6e0284af407d1de637d8e536c5cd00a7daf60"},
    {file = "Brotli-1.1.0-cp37-cp37m-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:0b63b949ff929fbc2d6d3ce0e924c9b93c9785d877a21a1b678877ffbbc4423a"},
    {file = "Brotli-1.1.0-cp37-cp37m-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:d192f0f30804e55db0d0e0a35d83a9fead0e9a359a9ed0285dbacea60cc10a84"},
    {file = "Brotli-1.1.0-cp37-cp37m-musllinux_1_1_aarch64.whl", hash = "sha256:f296c40e23065d0d6650c4aefe7470d2a25fffda489bcc3eb66083f3ac9f6643"},
    {file = "Brotli-1.1.0-cp37-cp37m-musllinux_1_1_i686.whl", hash = "sha256:919e32f147ae93a09fe064d77d5ebf4e35502a8df75c29fb05788528e330fe74"},
    {file = "Brotli-1.1.0-cp37-cp37m-musllinux_1_1_ppc64le.whl", hash = "sha256:23032ae55523cc7bccb4f6a0bf368cd25ad9bcdcc1990b64a647e7bbcce9cb5b"},
    {file = "Brotli-1.1.0-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:224e57f6eac61cc449f498cc5f0e1725ba2071a3d4f48d5d9dffba42db196438"},
    {file = "Brotli-1.1.0-cp37-cp37m-win32.whl", hash = "sha256:587ca6d3cef6e4e868102672d3bd9dc9698c309ba56d41c2b9c85bbb903cdb95"},
    {file = "Brotli-1.1.0-cp37-cp37m-win_amd64.whl", hash = "sha256:2954c1c23f81c2eaf0b0717d9380bd348578a94161a65b3a2afc62c86467dd68"},
    {file = "Brotli-1.1.0-cp38-cp38-macosx_10_9_universal2.whl", hash = "sha256:efa8b278894b14d6da122a72fefcebc28445f2d3f880ac59d46c90f4c13be9a3"},
    {file = "Brotli-1.1.0-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:03d20af184290887bdea3f0f78c4f737d126c74dc2f3ccadf07e54ceca3bf208"},
    {file = "Brotli-1.1.0-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:6172447e1b368dcbc458925e5ddaf9113477b0ed542df258d84fa28fc45ceea7"},
    {file = "Brotli-1.1.0-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:a743e5a28af5f70f9c080380a5f908d4d21d40e8f0e0c8901604d15cfa9ba751"},
    {file = "Brotli-1.1.0-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:0541e747cce78e24ea12d69176f6a7ddb690e62c425e01d31cc065e69ce55b48"},
    {file = "Brotli-1.1.0-cp38-cp38-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:cdbc1fc1bc0bff1cef838eafe581b55bfbffaed4ed0318b724d0b71d4d377619"},
    {file = "Brotli-1.1.0-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:890b5a14ce214389b2cc36ce82f3093f96f4cc730c1cffdbefff77a7c71f2a97"},
    {file = "Brotli-1.1.0-cp38-cp38-musllinux_1_1_i686.whl", hash = "sha256:1ab4fbee0b2d9098c74f3057b2bc055a8bd92ccf02f65944a241b4349229185a"},
    {file = "Brotli-1.1.0-cp38-cp38-musllinux_1_1_ppc64le.whl", hash = "sha256:141bd4d93984070e097521ed07e2575b46f817d08f9fa42b16b9b5f27b5ac088"},
    {file = "Brotli-1.1.0-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:fce1473f3ccc4187f75b4690cfc922628aed4d3dd013d047f95a9b3919a86596"},
    {file = "Brotli-1.1.0-cp38-cp38-win32.whl", hash = "sha256:db85ecf4e609a48f4b29055f1e144231b90edc90af7481aa731ba2d059226b1b"},
    {file = "Brotli-1.1.0-cp38-cp38-win_amd64.whl", hash = "sha256:3d7954194c36e304e1523f55d7042c59dc53ec20dd4e9ea9d151f1b62b4415c0"},
    {file = "Brotli-1.1.0-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:5fb2ce4b8045c78ebbc7b8f3c15062e435d47e7393cc57c25115cfd49883747a"},
    {file = "Brotli-1.1.0-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:7905193081db9bfa73b1219140b3d315831cbff0d8941f22da695832f0dd188f"},
    {file = "Brotli-1.1.0-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:a77def80806c421b4b0af06f45d65a136e7ac0bdca3c09d9e2ea4e515367c7e9"},
    {file = "Brotli-1.1.0-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:8dadd1314583ec0bf2d1379f7008ad627cd6336625d6679cf2f8e67081b83acf"},
    {file = "Brotli-1.1.0-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:901032ff242d479a0efa956d853d16875d42157f98951c0230f69e69f9c09bac"},
    {file = "Brotli-1.1.0-cp39-cp39-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:22fc2a8549ffe699bfba2256ab2ed0421a7b8fadff114a3d201794e45a9ff578"},
    {file = "Brotli-1.1.0-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:ae15b066e5ad21366600ebec29a7ccbc86812ed267e4b28e860b8ca16a2bc474"},
    {file = "Brotli-1.1.0-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:949f3b7c29912693cee0afcf09acd6ebc04c57af949d9bf77d6101ebb61e388c"},
    {file = "Brotli-1.1.0-cp39-cp39-musllinux_1_1_ppc64le.whl", hash = "sha256:89f4988c7203739d48c6f806f1e87a1d96e0806d44f0fba61dba81392c9e474d"},
    {file = "Brotli-1.1.0-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:de6551e370ef19f8de1807d0a9aa2cdfdce2e85ce88b122fe9f6b2b076837e59"},
    {file = "Brotli-1.1.0-cp39-cp39-win32.whl", hash = "sha256:f0d8a7a6b5983c2496e364b969f0e526647a06b075d034f3297dc66f3b360c64"},
    {file = "Brotli-1.1.0-cp39-cp39-win_amd64.whl", hash = "sha256:cdad5b9014d83ca68c25d2e9444e28e967ef16e80f6b436918c700c117a85467"},
    {file = "Brotli-1.1.0.tar.gz", hash = "sha256:81de08ac11bcb85841e440c13611c00b67d3bf82698314928d0b676362546724"},
]

[[package]]
name = "brotlicffi"
version = "1.1.0.0"
description = "Python CFFI bindings to the Brotli library"
optional = false
python-versions = ">=3.7"
files = [
    {file = "brotlicffi-1.1.0.0-cp37-abi3-macosx_10_9_x86_64.whl", hash = "sha256:9b7ae6bd1a3f0df532b6d67ff674099a96d22bc0948955cb338488c31bfb8851"},
    {file = "brotlicffi-1.1.0.0-cp37-abi3-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:19ffc919fa4fc6ace69286e0a23b3789b4219058313cf9b45625016bf7ff996b"},
    {file = "brotlicffi-1.1.0.0-cp37-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:9feb210d932ffe7798ee62e6145d3a757eb6233aa9a4e7db78dd3690d7755814"},
    {file = "brotlicffi-1.1.0.0-cp37-abi3-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:84763dbdef5dd5c24b75597a77e1b30c66604725707565188ba54bab4f114820"},
    {file = "brotlicffi-1.1.0.0-cp37-abi3-win32.whl", hash = "sha256:1b12b50e07c3911e1efa3a8971543e7648100713d4e0971b13631cce22c587eb"},
    {file = "brotlicffi-1.1.0.0-cp37-abi3-win_amd64.whl", hash = "sha256:994a4f0681bb6c6c3b0925530a1926b7a189d878e6e5e38fae8efa47c5d9c613"},
    {file = "brotlicffi-1.1.0.0-pp310-pypy310_pp73-macosx_10_9_x86_64.whl", hash = "sha256:2e4aeb0bd2540cb91b069dbdd54d458da8c4334ceaf2d25df2f4af576d6766ca"},
    {file = "brotlicffi-1.1.0.0-pp310-pypy310_pp73-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:4b7b0033b0d37bb33009fb2fef73310e432e76f688af76c156b3594389d81391"},
    {file = "brotlicffi-1.1.0.0-pp310-pypy310_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:54a07bb2374a1eba8ebb52b6fafffa2afd3c4df85ddd38fcc0511f2bb387c2a8"},
    {file = "brotlicffi-1.1.0.0-pp310-pypy310_pp73-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:7901a7dc4b88f1c1475de59ae9be59799db1007b7d059817948d8e4f12e24e35"},
    {file = "brotlicffi-1.1.0.0-pp310-pypy310_pp73-win_amd64.whl", hash = "sha256:ce01c7316aebc7fce59da734286148b1d1b9455f89cf2c8a4dfce7d41db55c2d"},
    {file = "brotlicffi-1.1.0.0-pp37-pypy37_pp73-macosx_10_9_x86_64.whl", hash = "sha256:246f1d1a90279bb6069de3de8d75a8856e073b8ff0b09dcca18ccc14cec85979"},
    {file = "brotlicffi-1.1.0.0-pp37-pypy37_pp73-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:cc4bc5d82bc56ebd8b514fb8350cfac4627d6b0743382e46d033976a5f80fab6"},
    {file = "brotlicffi-1.1.0.0-pp37-pypy37_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:37c26ecb14386a44b118ce36e546ce307f4810bc9598a6e6cb4f7fca725ae7e6"},
    {file = "brotlicffi-1.1.0.0-pp37-pypy37_pp73-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:ca72968ae4eaf6470498d5c2887073f7efe3b1e7d7ec8be11a06a79cc810e990"},
    {file = "brotlicffi-1.1.0.0-pp37-pypy37_pp73-win_amd64.whl", hash = "sha256:add0de5b9ad9e9aa293c3aa4e9deb2b61e99ad6c1634e01d01d98c03e6a354cc"},
    {file = "brotlicffi-1.1.0.0-pp38-pypy38_pp73-macosx_10_9_x86_64.whl", hash = "sha256:9b6068e0f3769992d6b622a1cd2e7835eae3cf8d9da123d7f51ca9c1e9c333e5"},
    {file = "brotlicffi-1.1.0.0-pp38-pypy38_pp73-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:8557a8559509b61e65083f8782329188a250102372576093c88930c875a69838"},
    {file = "brotlicffi-1.1.0.0-pp38-pypy38_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:2a7ae37e5d79c5bdfb5b4b99f2715a6035e6c5bf538c3746abc8e26694f92f33"},
    {file = "brotlicffi-1.1.0.0-pp38-pypy38_pp73-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:391151ec86bb1c683835980f4816272a87eaddc46bb91cbf44f62228b84d8cca"},
    {file = "brotlicffi-1.1.0.0-pp38-pypy38_pp73-win_amd64.whl", hash = "sha256:2f3711be9290f0453de8eed5275d93d286abe26b08ab4a35d7452caa1fef532f"},
    {file = "brotlicffi-1.1.0.0-pp39-pypy39_pp73-macosx_10_9_x86_64.whl", hash = "sha256:1a807d760763e398bbf2c6394ae9da5815901aa93ee0a37bca5efe78d4ee3171"},
    {file = "brotlicffi-1.1.0.0-pp39-pypy39_pp73-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:fa8ca0623b26c94fccc3a1fdd895be1743b838f3917300506d04aa3346fd2a14"},
    {file = "brotlicffi-1.1.0.0-pp39-pypy39_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:3de0cf28a53a3238b252aca9fed1593e9d36c1d116748013339f0949bfc84112"},
    {file = "brotlicffi-1.1.0.0-pp39-pypy39_pp73-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:6be5ec0e88a4925c91f3dea2bb0013b3a2accda6f77238f76a34a1ea532a1cb0"},
    {file = "brotlicffi-1.1.0.0-pp39-pypy39_pp73-win_amd64.whl", hash = "sha256:d9eb71bb1085d996244439154387266fd23d6ad37161f6f52f1cd41dd95a3808"},
    {file = "brotlicffi-1.1.0.0.tar.gz", hash = "sha256:b77827a689905143f87915310b93b273ab17888fd43ef350d4832c4a71083c13"},
]

[package.dependencies]
cffi = ">=1.0.0"

[[package]]
name = "cachetools"
version = "5.3.3"
description = "Extensible memoizing collections and decorators"
optional = false
python-versions = ">=3.7"
files = [
    {file = "cachetools-5.3.3-py3-none-any.whl", hash = "sha256:0abad1021d3f8325b2fc1d2e9c8b9c9d57b04c3932657a72465447332c24d945"},
    {file = "cachetools-5.3.3.tar.gz", hash = "sha256:ba29e2dfa0b8b556606f097407ed1aa62080ee108ab0dc5ec9d6a723a007d105"},
]

[[package]]
name = "certifi"
version = "2023.11.17"
description = "Python package for providing Mozilla's CA Bundle."
optional = false
python-versions = ">=3.6"
files = [
    {file = "certifi-2023.11.17-py3-none-any.whl", hash = "sha256:e036ab49d5b79556f99cfc2d9320b34cfbe5be05c5871b51de9329f0603b0474"},
    {file = "certifi-2023.11.17.tar.gz", hash = "sha256:9b469f3a900bf28dc19b8cfbf8019bf47f7fdd1a65a1d4ffb98fc14166beb4d1"},
]

[[package]]
name = "cffi"
version = "1.16.0"
description = "Foreign Function Interface for Python calling C code."
optional = false
python-versions = ">=3.8"
files = [
    {file = "cffi-1.16.0-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:6b3d6606d369fc1da4fd8c357d026317fbb9c9b75d36dc16e90e84c26854b088"},
    {file = "cffi-1.16.0-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:ac0f5edd2360eea2f1daa9e26a41db02dd4b0451b48f7c318e217ee092a213e9"},
    {file = "cffi-1.16.0-cp310-cp310-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:7e61e3e4fa664a8588aa25c883eab612a188c725755afff6289454d6362b9673"},
    {file = "cffi-1.16.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:a72e8961a86d19bdb45851d8f1f08b041ea37d2bd8d4fd19903bc3083d80c896"},
    {file = "cffi-1.16.0-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:5b50bf3f55561dac5438f8e70bfcdfd74543fd60df5fa5f62d94e5867deca684"},
    {file = "cffi-1.16.0-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:7651c50c8c5ef7bdb41108b7b8c5a83013bfaa8a935590c5d74627c047a583c7"},
    {file = "cffi-1.16.0-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:e4108df7fe9b707191e55f33efbcb2d81928e10cea45527879a4749cbe472614"},
    {file = "cffi-1.16.0-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:32c68ef735dbe5857c810328cb2481e24722a59a2003018885514d4c09af9743"},
    {file = "cffi-1.16.0-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:673739cb539f8cdaa07d92d02efa93c9ccf87e345b9a0b556e3ecc666718468d"},
    {file = "cffi-1.16.0-cp310-cp310-win32.whl", hash = "sha256:9f90389693731ff1f659e55c7d1640e2ec43ff725cc61b04b2f9c6d8d017df6a"},
    {file = "cffi-1.16.0-cp310-cp310-win_amd64.whl", hash = "sha256:e6024675e67af929088fda399b2094574609396b1decb609c55fa58b028a32a1"},
    {file = "cffi-1.16.0-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:b84834d0cf97e7d27dd5b7f3aca7b6e9263c56308ab9dc8aae9784abb774d404"},
    {file = "cffi-1.16.0-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:1b8ebc27c014c59692bb2664c7d13ce7a6e9a629be20e54e7271fa696ff2b417"},
    {file = "cffi-1.16.0-cp311-cp311-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:ee07e47c12890ef248766a6e55bd38ebfb2bb8edd4142d56db91b21ea68b7627"},
    {file = "cffi-1.16.0-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:d8a9d3ebe49f084ad71f9269834ceccbf398253c9fac910c4fd7053ff1386936"},
    {file = "cffi-1.16.0-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:e70f54f1796669ef691ca07d046cd81a29cb4deb1e5f942003f401c0c4a2695d"},
    {file = "cffi-1.16.0-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:5bf44d66cdf9e893637896c7faa22298baebcd18d1ddb6d2626a6e39793a1d56"},
    {file = "cffi-1.16.0-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:7b78010e7b97fef4bee1e896df8a4bbb6712b7f05b7ef630f9d1da00f6444d2e"},
    {file = "cffi-1.16.0-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:c6a164aa47843fb1b01e941d385aab7215563bb8816d80ff3a363a9f8448a8dc"},
    {file = "cffi-1.16.0-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:e09f3ff613345df5e8c3667da1d918f9149bd623cd9070c983c013792a9a62eb"},
    {file = "cffi-1.16.0-cp311-cp311-win32.whl", hash = "sha256:2c56b361916f390cd758a57f2e16233eb4f64bcbeee88a4881ea90fca14dc6ab"},
    {file = "cffi-1.16.0-cp311-cp311-win_amd64.whl", hash = "sha256:db8e577c19c0fda0beb7e0d4e09e0ba74b1e4c092e0e40bfa12fe05b6f6d75ba"},
    {file = "cffi-1.16.0-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:fa3a0128b152627161ce47201262d3140edb5a5c3da88d73a1b790a959126956"},
    {file = "cffi-1.16.0-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:68e7c44931cc171c54ccb702482e9fc723192e88d25a0e133edd7aff8fcd1f6e"},
    {file = "cffi-1.16.0-cp312-cp312-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:abd808f9c129ba2beda4cfc53bde801e5bcf9d6e0f22f095e45327c038bfe68e"},
    {file = "cffi-1.16.0-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:88e2b3c14bdb32e440be531ade29d3c50a1a59cd4e51b1dd8b0865c54ea5d2e2"},
    {file = "cffi-1.16.0-cp312-cp312-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:fcc8eb6d5902bb1cf6dc4f187ee3ea80a1eba0a89aba40a5cb20a5087d961357"},
    {file = "cffi-1.16.0-cp312-cp312-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:b7be2d771cdba2942e13215c4e340bfd76398e9227ad10402a8767ab1865d2e6"},
    {file = "cffi-1.16.0-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:e715596e683d2ce000574bae5d07bd522c781a822866c20495e52520564f0969"},
    {file = "cffi-1.16.0-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:2d92b25dbf6cae33f65005baf472d2c245c050b1ce709cc4588cdcdd5495b520"},
    {file = "cffi-1.16.0-cp312-cp312-win32.whl", hash = "sha256:b2ca4e77f9f47c55c194982e10f058db063937845bb2b7a86c84a6cfe0aefa8b"},
    {file = "cffi-1.16.0-cp312-cp312-win_amd64.whl", hash = "sha256:68678abf380b42ce21a5f2abde8efee05c114c2fdb2e9eef2efdb0257fba1235"},
    {file = "cffi-1.16.0-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:0c9ef6ff37e974b73c25eecc13952c55bceed9112be2d9d938ded8e856138bcc"},
    {file = "cffi-1.16.0-cp38-cp38-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:a09582f178759ee8128d9270cd1344154fd473bb77d94ce0aeb2a93ebf0feaf0"},
    {file = "cffi-1.16.0-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:e760191dd42581e023a68b758769e2da259b5d52e3103c6060ddc02c9edb8d7b"},
    {file = "cffi-1.16.0-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:80876338e19c951fdfed6198e70bc88f1c9758b94578d5a7c4c91a87af3cf31c"},
    {file = "cffi-1.16.0-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:a6a14b17d7e17fa0d207ac08642c8820f84f25ce17a442fd15e27ea18d67c59b"},
    {file = "cffi-1.16.0-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:6602bc8dc6f3a9e02b6c22c4fc1e47aa50f8f8e6d3f78a5e16ac33ef5fefa324"},
    {file = "cffi-1.16.0-cp38-cp38-win32.whl", hash = "sha256:131fd094d1065b19540c3d72594260f118b231090295d8c34e19a7bbcf2e860a"},
    {file = "cffi-1.16.0-cp38-cp38-win_amd64.whl", hash = "sha256:31d13b0f99e0836b7ff893d37af07366ebc90b678b6664c955b54561fc36ef36"},
    {file = "cffi-1.16.0-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:582215a0e9adbe0e379761260553ba11c58943e4bbe9c36430c4ca6ac74b15ed"},
    {file = "cffi-1.16.0-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:b29ebffcf550f9da55bec9e02ad430c992a87e5f512cd63388abb76f1036d8d2"},
    {file = "cffi-1.16.0-cp39-cp39-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:dc9b18bf40cc75f66f40a7379f6a9513244fe33c0e8aa72e2d56b0196a7ef872"},
    {file = "cffi-1.16.0-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:9cb4a35b3642fc5c005a6755a5d17c6c8b6bcb6981baf81cea8bfbc8903e8ba8"},
    {file = "cffi-1.16.0-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:b86851a328eedc692acf81fb05444bdf1891747c25af7529e39ddafaf68a4f3f"},
    {file = "cffi-1.16.0-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:c0f31130ebc2d37cdd8e44605fb5fa7ad59049298b3f745c74fa74c62fbfcfc4"},
    {file = "cffi-1.16.0-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:8f8e709127c6c77446a8c0a8c8bf3c8ee706a06cd44b1e827c3e6a2ee6b8c098"},
    {file = "cffi-1.16.0-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:748dcd1e3d3d7cd5443ef03ce8685043294ad6bd7c02a38d1bd367cfd968e000"},
    {file = "cffi-1.16.0-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:8895613bcc094d4a1b2dbe179d88d7fb4a15cee43c052e8885783fac397d91fe"},
    {file = "cffi-1.16.0-cp39-cp39-win32.whl", hash = "sha256:ed86a35631f7bfbb28e108dd96773b9d5a6ce4811cf6ea468bb6a359b256b1e4"},
    {file = "cffi-1.16.0-cp39-cp39-win_amd64.whl", hash = "sha256:3686dffb02459559c74dd3d81748269ffb0eb027c39a6fc99502de37d501faa8"},
    {file = "cffi-1.16.0.tar.gz", hash = "sha256:bcb3ef43e58665bbda2fb198698fcae6776483e0c4a631aa5647806c25e02cc0"},
]

[package.dependencies]
pycparser = "*"

[[package]]
name = "charset-normalizer"
version = "3.3.2"
description = "The Real First Universal Charset Detector. Open, modern and actively maintained alternative to Chardet."
optional = false
python-versions = ">=3.7.0"
files = [
    {file = "charset-normalizer-3.3.2.tar.gz", hash = "sha256:f30c3cb33b24454a82faecaf01b19c18562b1e89558fb6c56de4d9118a032fd5"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:25baf083bf6f6b341f4121c2f3c548875ee6f5339300e08be3f2b2ba1721cdd3"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:06435b539f889b1f6f4ac1758871aae42dc3a8c0e24ac9e60c2384973ad73027"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:9063e24fdb1e498ab71cb7419e24622516c4a04476b17a2dab57e8baa30d6e03"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:6897af51655e3691ff853668779c7bad41579facacf5fd7253b0133308cf000d"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:1d3193f4a680c64b4b6a9115943538edb896edc190f0b222e73761716519268e"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:cd70574b12bb8a4d2aaa0094515df2463cb429d8536cfb6c7ce983246983e5a6"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:8465322196c8b4d7ab6d1e049e4c5cb460d0394da4a27d23cc242fbf0034b6b5"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:a9a8e9031d613fd2009c182b69c7b2c1ef8239a0efb1df3f7c8da66d5dd3d537"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:beb58fe5cdb101e3a055192ac291b7a21e3b7ef4f67fa1d74e331a7f2124341c"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:e06ed3eb3218bc64786f7db41917d4e686cc4856944f53d5bdf83a6884432e12"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-musllinux_1_1_ppc64le.whl", hash = "sha256:2e81c7b9c8979ce92ed306c249d46894776a909505d8f5a4ba55b14206e3222f"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-musllinux_1_1_s390x.whl", hash = "sha256:572c3763a264ba47b3cf708a44ce965d98555f618ca42c926a9c1616d8f34269"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:fd1abc0d89e30cc4e02e4064dc67fcc51bd941eb395c502aac3ec19fab46b519"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-win32.whl", hash = "sha256:3d47fa203a7bd9c5b6cee4736ee84ca03b8ef23193c0d1ca99b5089f72645c73"},
    {file = "charset_normalizer-3.3.2-cp310-cp310-win_amd64.whl", hash = "sha256:10955842570876604d404661fbccbc9c7e684caf432c09c715ec38fbae45ae09"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:802fe99cca7457642125a8a88a084cef28ff0cf9407060f7b93dca5aa25480db"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:573f6eac48f4769d667c4442081b1794f52919e7edada77495aaed9236d13a96"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:549a3a73da901d5bc3ce8d24e0600d1fa85524c10287f6004fbab87672bf3e1e"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:f27273b60488abe721a075bcca6d7f3964f9f6f067c8c4c605743023d7d3944f"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:1ceae2f17a9c33cb48e3263960dc5fc8005351ee19db217e9b1bb15d28c02574"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:65f6f63034100ead094b8744b3b97965785388f308a64cf8d7c34f2f2e5be0c4"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:753f10e867343b4511128c6ed8c82f7bec3bd026875576dfd88483c5c73b2fd8"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:4a78b2b446bd7c934f5dcedc588903fb2f5eec172f3d29e52a9096a43722adfc"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:e537484df0d8f426ce2afb2d0f8e1c3d0b114b83f8850e5f2fbea0e797bd82ae"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:eb6904c354526e758fda7167b33005998fb68c46fbc10e013ca97f21ca5c8887"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-musllinux_1_1_ppc64le.whl", hash = "sha256:deb6be0ac38ece9ba87dea880e438f25ca3eddfac8b002a2ec3d9183a454e8ae"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-musllinux_1_1_s390x.whl", hash = "sha256:4ab2fe47fae9e0f9dee8c04187ce5d09f48eabe611be8259444906793ab7cbce"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:80402cd6ee291dcb72644d6eac93785fe2c8b9cb30893c1af5b8fdd753b9d40f"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-win32.whl", hash = "sha256:7cd13a2e3ddeed6913a65e66e94b51d80a041145a026c27e6bb76c31a853c6ab"},
    {file = "charset_normalizer-3.3.2-cp311-cp311-win_amd64.whl", hash = "sha256:663946639d296df6a2bb2aa51b60a2454ca1cb29835324c640dafb5ff2131a77"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-macosx_10_9_universal2.whl", hash = "sha256:0b2b64d2bb6d3fb9112bafa732def486049e63de9618b5843bcdd081d8144cd8"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:ddbb2551d7e0102e7252db79ba445cdab71b26640817ab1e3e3648dad515003b"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:55086ee1064215781fff39a1af09518bc9255b50d6333f2e4c74ca09fac6a8f6"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:8f4a014bc36d3c57402e2977dada34f9c12300af536839dc38c0beab8878f38a"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:a10af20b82360ab00827f916a6058451b723b4e65030c5a18577c8b2de5b3389"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:8d756e44e94489e49571086ef83b2bb8ce311e730092d2c34ca8f7d925cb20aa"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:90d558489962fd4918143277a773316e56c72da56ec7aa3dc3dbbe20fdfed15b"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:6ac7ffc7ad6d040517be39eb591cac5ff87416c2537df6ba3cba3bae290c0fed"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:7ed9e526742851e8d5cc9e6cf41427dfc6068d4f5a3bb03659444b4cabf6bc26"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-musllinux_1_1_i686.whl", hash = "sha256:8bdb58ff7ba23002a4c5808d608e4e6c687175724f54a5dade5fa8c67b604e4d"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-musllinux_1_1_ppc64le.whl", hash = "sha256:6b3251890fff30ee142c44144871185dbe13b11bab478a88887a639655be1068"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-musllinux_1_1_s390x.whl", hash = "sha256:b4a23f61ce87adf89be746c8a8974fe1c823c891d8f86eb218bb957c924bb143"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:efcb3f6676480691518c177e3b465bcddf57cea040302f9f4e6e191af91174d4"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-win32.whl", hash = "sha256:d965bba47ddeec8cd560687584e88cf699fd28f192ceb452d1d7ee807c5597b7"},
    {file = "charset_normalizer-3.3.2-cp312-cp312-win_amd64.whl", hash = "sha256:96b02a3dc4381e5494fad39be677abcb5e6634bf7b4fa83a6dd3112607547001"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-macosx_10_9_x86_64.whl", hash = "sha256:95f2a5796329323b8f0512e09dbb7a1860c46a39da62ecb2324f116fa8fdc85c"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:c002b4ffc0be611f0d9da932eb0f704fe2602a9a949d1f738e4c34c75b0863d5"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:a981a536974bbc7a512cf44ed14938cf01030a99e9b3a06dd59578882f06f985"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:3287761bc4ee9e33561a7e058c72ac0938c4f57fe49a09eae428fd88aafe7bb6"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:42cb296636fcc8b0644486d15c12376cb9fa75443e00fb25de0b8602e64c1714"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:0a55554a2fa0d408816b3b5cedf0045f4b8e1a6065aec45849de2d6f3f8e9786"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-musllinux_1_1_aarch64.whl", hash = "sha256:c083af607d2515612056a31f0a8d9e0fcb5876b7bfc0abad3ecd275bc4ebc2d5"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-musllinux_1_1_i686.whl", hash = "sha256:87d1351268731db79e0f8e745d92493ee2841c974128ef629dc518b937d9194c"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-musllinux_1_1_ppc64le.whl", hash = "sha256:bd8f7df7d12c2db9fab40bdd87a7c09b1530128315d047a086fa3ae3435cb3a8"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-musllinux_1_1_s390x.whl", hash = "sha256:c180f51afb394e165eafe4ac2936a14bee3eb10debc9d9e4db8958fe36afe711"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:8c622a5fe39a48f78944a87d4fb8a53ee07344641b0562c540d840748571b811"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-win32.whl", hash = "sha256:db364eca23f876da6f9e16c9da0df51aa4f104a972735574842618b8c6d999d4"},
    {file = "charset_normalizer-3.3.2-cp37-cp37m-win_amd64.whl", hash = "sha256:86216b5cee4b06df986d214f664305142d9c76df9b6512be2738aa72a2048f99"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-macosx_10_9_universal2.whl", hash = "sha256:6463effa3186ea09411d50efc7d85360b38d5f09b870c48e4600f63af490e56a"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:6c4caeef8fa63d06bd437cd4bdcf3ffefe6738fb1b25951440d80dc7df8c03ac"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-macosx_11_0_arm64.whl", hash = "sha256:37e55c8e51c236f95b033f6fb391d7d7970ba5fe7ff453dad675e88cf303377a"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:fb69256e180cb6c8a894fee62b3afebae785babc1ee98b81cdf68bbca1987f33"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:ae5f4161f18c61806f411a13b0310bea87f987c7d2ecdbdaad0e94eb2e404238"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:b2b0a0c0517616b6869869f8c581d4eb2dd83a4d79e0ebcb7d373ef9956aeb0a"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:45485e01ff4d3630ec0d9617310448a8702f70e9c01906b0d0118bdf9d124cf2"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:eb00ed941194665c332bf8e078baf037d6c35d7c4f3102ea2d4f16ca94a26dc8"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:2127566c664442652f024c837091890cb1942c30937add288223dc895793f898"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-musllinux_1_1_i686.whl", hash = "sha256:a50aebfa173e157099939b17f18600f72f84eed3049e743b68ad15bd69b6bf99"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-musllinux_1_1_ppc64le.whl", hash = "sha256:4d0d1650369165a14e14e1e47b372cfcb31d6ab44e6e33cb2d4e57265290044d"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-musllinux_1_1_s390x.whl", hash = "sha256:923c0c831b7cfcb071580d3f46c4baf50f174be571576556269530f4bbd79d04"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:06a81e93cd441c56a9b65d8e1d043daeb97a3d0856d177d5c90ba85acb3db087"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-win32.whl", hash = "sha256:6ef1d82a3af9d3eecdba2321dc1b3c238245d890843e040e41e470ffa64c3e25"},
    {file = "charset_normalizer-3.3.2-cp38-cp38-win_amd64.whl", hash = "sha256:eb8821e09e916165e160797a6c17edda0679379a4be5c716c260e836e122f54b"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:c235ebd9baae02f1b77bcea61bce332cb4331dc3617d254df3323aa01ab47bd4"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:5b4c145409bef602a690e7cfad0a15a55c13320ff7a3ad7ca59c13bb8ba4d45d"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:68d1f8a9e9e37c1223b656399be5d6b448dea850bed7d0f87a8311f1ff3dabb0"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:22afcb9f253dac0696b5a4be4a1c0f8762f8239e21b99680099abd9b2b1b2269"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:e27ad930a842b4c5eb8ac0016b0a54f5aebbe679340c26101df33424142c143c"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:1f79682fbe303db92bc2b1136016a38a42e835d932bab5b3b1bfcfbf0640e519"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:b261ccdec7821281dade748d088bb6e9b69e6d15b30652b74cbbac25e280b796"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:122c7fa62b130ed55f8f285bfd56d5f4b4a5b503609d181f9ad85e55c89f4185"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:d0eccceffcb53201b5bfebb52600a5fb483a20b61da9dbc885f8b103cbe7598c"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:9f96df6923e21816da7e0ad3fd47dd8f94b2a5ce594e00677c0013018b813458"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-musllinux_1_1_ppc64le.whl", hash = "sha256:7f04c839ed0b6b98b1a7501a002144b76c18fb1c1850c8b98d458ac269e26ed2"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-musllinux_1_1_s390x.whl", hash = "sha256:34d1c8da1e78d2e001f363791c98a272bb734000fcef47a491c1e3b0505657a8"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:ff8fa367d09b717b2a17a052544193ad76cd49979c805768879cb63d9ca50561"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-win32.whl", hash = "sha256:aed38f6e4fb3f5d6bf81bfa990a07806be9d83cf7bacef998ab1a9bd660a581f"},
    {file = "charset_normalizer-3.3.2-cp39-cp39-win_amd64.whl", hash = "sha256:b01b88d45a6fcb69667cd6d2f7a9aeb4bf53760d7fc536bf679ec94fe9f3ff3d"},
    {file = "charset_normalizer-3.3.2-py3-none-any.whl", hash = "sha256:3e4d1f6587322d2788836a99c69062fbb091331ec940e02d12d179c1d53e25fc"},
]

[[package]]
name = "click"
version = "8.1.7"
description = "Composable command line interface toolkit"
optional = false
python-versions = ">=3.7"
files = [
    {file = "click-8.1.7-py3-none-any.whl", hash = "sha256:ae74fb96c20a0277a1d615f1e4d73c8414f5a98db8b799a7931d1582f3390c28"},
    {file = "click-8.1.7.tar.gz", hash = "sha256:ca9853ad459e787e2192211578cc907e7594e294c7ccc834310722b41b9ca6de"},
]

[package.dependencies]
colorama = {version = "*", markers = "platform_system == \"Windows\""}

[[package]]
name = "colorama"
version = "0.4.6"
description = "Cross-platform colored terminal text."
optional = false
python-versions = "!=3.0.*,!=3.1.*,!=3.2.*,!=3.3.*,!=3.4.*,!=3.5.*,!=3.6.*,>=2.7"
files = [
    {file = "colorama-0.4.6-py2.py3-none-any.whl", hash = "sha256:4f1d9991f5acc0ca119f9d443620b77f9d6b33703e51011c16baf57afb285fc6"},
    {file = "colorama-0.4.6.tar.gz", hash = "sha256:08695f5cb7ed6e0531a20572697297273c47b8cae5a63ffc6d6ed5c201be6e44"},
]

[[package]]
name = "cssselect"
version = "1.2.0"
description = "cssselect parses CSS3 Selectors and translates them to XPath 1.0"
optional = false
python-versions = ">=3.7"
files = [
    {file = "cssselect-1.2.0-py2.py3-none-any.whl", hash = "sha256:da1885f0c10b60c03ed5eccbb6b68d6eff248d91976fcde348f395d54c9fd35e"},
    {file = "cssselect-1.2.0.tar.gz", hash = "sha256:666b19839cfaddb9ce9d36bfe4c969132c647b92fc9088c4e23f786b30f1b3dc"},
]

[[package]]
name = "cssselect2"
version = "0.7.0"
description = "CSS selectors for Python ElementTree"
optional = false
python-versions = ">=3.7"
files = [
    {file = "cssselect2-0.7.0-py3-none-any.whl", hash = "sha256:fd23a65bfd444595913f02fc71f6b286c29261e354c41d722ca7a261a49b5969"},
    {file = "cssselect2-0.7.0.tar.gz", hash = "sha256:1ccd984dab89fc68955043aca4e1b03e0cf29cad9880f6e28e3ba7a74b14aa5a"},
]

[package.dependencies]
tinycss2 = "*"
webencodings = "*"

[package.extras]
doc = ["sphinx", "sphinx_rtd_theme"]
test = ["flake8", "isort", "pytest"]

[[package]]
name = "curl-cffi"
version = "0.5.10"
description = "libcurl ffi bindings for Python, with impersonation support"
optional = false
python-versions = ">=3.7"
files = [
    {file = "curl_cffi-0.5.10-cp37-abi3-macosx_10_9_x86_64.whl", hash = "sha256:892603dab5e56fb72bfff7ae969136138971f63f63defe98232e1ec55cb0f1c6"},
    {file = "curl_cffi-0.5.10-cp37-abi3-macosx_11_0_arm64.whl", hash = "sha256:9937b8e13b1a6963c63e155b6621ec74649965105efedb919bc226fe731861cc"},
    {file = "curl_cffi-0.5.10-cp37-abi3-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:b537595b9610a4dd0927c09823925b4e32b1ce0fd04385bfc5bb72ab830720e6"},
    {file = "curl_cffi-0.5.10-cp37-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:1b2bc8822d23415f6533c8b750475e9bbc76764025fe1dcb5866dc033607fd7b"},
    {file = "curl_cffi-0.5.10-cp37-abi3-win_amd64.whl", hash = "sha256:f9a1874b860c4e8db49bdfd9b9d4dc39999a1397d271ec78624c35c838e9e92a"},
    {file = "curl_cffi-0.5.10.tar.gz", hash = "sha256:55bac4b73e2d80ceeaabea33270fc8ca6ace594128a46710242f2e688b4f8bfc"},
]

[package.dependencies]
cffi = ">=1.12.0"

[package.extras]
build = ["cibuildwheel", "wheel"]
dev = ["autoflake (==1.4)", "black (==22.8.0)", "coverage (==6.4.1)", "cryptography (==38.0.3)", "flake8 (==6.0.0)", "flake8-bugbear (==22.7.1)", "flake8-pie (==0.15.0)", "httpx (==0.23.1)", "isort (==5.10.1)", "mypy (==0.971)", "pytest (==7.1.2)", "pytest-asyncio (==0.19.0)", "pytest-trio (==0.7.0)", "trio (==0.21.0)", "trio-typing (==0.7.0)", "trustme (==0.9.0)", "types-certifi (==2021.10.8.2)", "uvicorn (==0.18.3)"]
test = ["cryptography (==38.0.3)", "httpx (==0.23.1)", "pytest (==7.1.2)", "pytest-asyncio (==0.19.0)", "pytest-trio (==0.7.0)", "trio (==0.21.0)", "trio-typing (==0.7.0)", "trustme (==0.9.0)", "types-certifi (==2021.10.8.2)", "uvicorn (==0.18.3)"]

[[package]]
name = "dataclasses-json"
version = "0.6.3"
description = "Easily serialize dataclasses to and from JSON."
optional = false
python-versions = ">=3.7,<4.0"
files = [
    {file = "dataclasses_json-0.6.3-py3-none-any.whl", hash = "sha256:4aeb343357997396f6bca1acae64e486c3a723d8f5c76301888abeccf0c45176"},
    {file = "dataclasses_json-0.6.3.tar.gz", hash = "sha256:35cb40aae824736fdf959801356641836365219cfe14caeb115c39136f775d2a"},
]

[package.dependencies]
marshmallow = ">=3.18.0,<4.0.0"
typing-inspect = ">=0.4.0,<1"

[[package]]
name = "distro"
version = "1.9.0"
description = "Distro - an OS platform information API"
optional = false
python-versions = ">=3.6"
files = [
    {file = "distro-1.9.0-py3-none-any.whl", hash = "sha256:7bffd925d65168f85027d8da9af6bddab658135b840670a223589bc0c8ef02b2"},
    {file = "distro-1.9.0.tar.gz", hash = "sha256:2fa77c6fd8940f116ee1d6b94a2f90b13b5ea8d019b98bc8bafdcabcdd9bdbed"},
]

[[package]]
name = "docopt"
version = "0.6.2"
description = "Pythonic argument parser, that will make you smile"
optional = false
python-versions = "*"
files = [
    {file = "docopt-0.6.2.tar.gz", hash = "sha256:49b3a825280bd66b3aa83585ef59c4a8c82f2c8a522dbe754a8bc8d08c85c491"},
]

[[package]]
name = "duckduckgo-search"
version = "4.1.1"
description = "Search for words, documents, images, news, maps and text translation using the DuckDuckGo.com search engine."
optional = false
python-versions = ">=3.8"
files = [
    {file = "duckduckgo_search-4.1.1-py3-none-any.whl", hash = "sha256:5b3b7d8dd0192510af79597bcfa267824a3a1006030615b7f8b66e1b9f4b4cb0"},
    {file = "duckduckgo_search-4.1.1.tar.gz", hash = "sha256:3f81872fc8cc54c0acd100f1ab3f4ba6580b696000100e56e8a7131c3963e2c8"},
]

[package.dependencies]
click = ">=8.1.7"
curl-cffi = ">=0.5.10"
lxml = ">=4.9.3"

[package.extras]
dev = ["pytest (>=7.4.2)", "pytest-asyncio (>=0.21.1)", "ruff (>=0.1.6)"]

[[package]]
name = "exceptiongroup"
version = "1.2.0"
description = "Backport of PEP 654 (exception groups)"
optional = false
python-versions = ">=3.7"
files = [
    {file = "exceptiongroup-1.2.0-py3-none-any.whl", hash = "sha256:4bfd3996ac73b41e9b9628b04e079f193850720ea5945fc96a08633c66912f14"},
    {file = "exceptiongroup-1.2.0.tar.gz", hash = "sha256:91f5c769735f051a4290d52edd0858999b57e5876e9f85937691bd4c9fa3ed68"},
]

[package.extras]
test = ["pytest (>=6)"]

[[package]]
name = "fastapi"
version = "0.104.1"
description = "FastAPI framework, high performance, easy to learn, fast to code, ready for production"
optional = false
python-versions = ">=3.8"
files = [
    {file = "fastapi-0.104.1-py3-none-any.whl", hash = "sha256:752dc31160cdbd0436bb93bad51560b57e525cbb1d4bbf6f4904ceee75548241"},
    {file = "fastapi-0.104.1.tar.gz", hash = "sha256:e5e4540a7c5e1dcfbbcf5b903c234feddcdcd881f191977a1c5dfd917487e7ae"},
]

[package.dependencies]
anyio = ">=3.7.1,<4.0.0"
pydantic = ">=1.7.4,<1.8 || >1.8,<1.8.1 || >1.8.1,<2.0.0 || >2.0.0,<2.0.1 || >2.0.1,<2.1.0 || >2.1.0,<3.0.0"
starlette = ">=0.27.0,<0.28.0"
typing-extensions = ">=4.8.0"

[package.extras]
all = ["email-validator (>=2.0.0)", "httpx (>=0.23.0)", "itsdangerous (>=1.1.0)", "jinja2 (>=2.11.2)", "orjson (>=3.2.1)", "pydantic-extra-types (>=2.0.0)", "pydantic-settings (>=2.0.0)", "python-multipart (>=0.0.5)", "pyyaml (>=5.3.1)", "ujson (>=4.0.1,!=4.0.2,!=4.1.0,!=4.2.0,!=4.3.0,!=5.0.0,!=5.1.0)", "uvicorn[standard] (>=0.12.0)"]

[[package]]
name = "feedfinder2"
version = "0.0.4"
description = "Find the feed URLs for a website."
optional = false
python-versions = "*"
files = [
    {file = "feedfinder2-0.0.4.tar.gz", hash = "sha256:3701ee01a6c85f8b865a049c30ba0b4608858c803fe8e30d1d289fdbe89d0efe"},
]

[package.dependencies]
beautifulsoup4 = "*"
requests = "*"
six = "*"

[[package]]
name = "feedparser"
version = "6.0.10"
description = "Universal feed parser, handles RSS 0.9x, RSS 1.0, RSS 2.0, CDF, Atom 0.3, and Atom 1.0 feeds"
optional = false
python-versions = ">=3.6"
files = [
    {file = "feedparser-6.0.10-py3-none-any.whl", hash = "sha256:79c257d526d13b944e965f6095700587f27388e50ea16fd245babe4dfae7024f"},
    {file = "feedparser-6.0.10.tar.gz", hash = "sha256:27da485f4637ce7163cdeab13a80312b93b7d0c1b775bef4a47629a3110bca51"},
]

[package.dependencies]
sgmllib3k = "*"

[[package]]
name = "filelock"
version = "3.13.1"
description = "A platform independent file lock."
optional = false
python-versions = ">=3.8"
files = [
    {file = "filelock-3.13.1-py3-none-any.whl", hash = "sha256:57dbda9b35157b05fb3e58ee91448612eb674172fab98ee235ccb0b5bee19a1c"},
    {file = "filelock-3.13.1.tar.gz", hash = "sha256:521f5f56c50f8426f5e03ad3b281b490a87ef15bc6c526f168290f0c7148d44e"},
]

[package.extras]
docs = ["furo (>=2023.9.10)", "sphinx (>=7.2.6)", "sphinx-autodoc-typehints (>=1.24)"]
testing = ["covdefaults (>=2.3)", "coverage (>=7.3.2)", "diff-cover (>=8)", "pytest (>=7.4.3)", "pytest-cov (>=4.1)", "pytest-mock (>=3.12)", "pytest-timeout (>=2.2)"]
typing = ["typing-extensions (>=4.8)"]

[[package]]
name = "fonttools"
version = "4.47.0"
description = "Tools to manipulate font files"
optional = false
python-versions = ">=3.8"
files = [
    {file = "fonttools-4.47.0-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:2d2404107626f97a221dc1a65b05396d2bb2ce38e435f64f26ed2369f68675d9"},
    {file = "fonttools-4.47.0-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:c01f409be619a9a0f5590389e37ccb58b47264939f0e8d58bfa1f3ba07d22671"},
    {file = "fonttools-4.47.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:d986b66ff722ef675b7ee22fbe5947a41f60a61a4da15579d5e276d897fbc7fa"},
    {file = "fonttools-4.47.0-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:e8acf6dd0434b211b3bd30d572d9e019831aae17a54016629fa8224783b22df8"},
    {file = "fonttools-4.47.0-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:495369c660e0c27233e3c572269cbe520f7f4978be675f990f4005937337d391"},
    {file = "fonttools-4.47.0-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:c59227d7ba5b232281c26ae04fac2c73a79ad0e236bca5c44aae904a18f14faf"},
    {file = "fonttools-4.47.0-cp310-cp310-win32.whl", hash = "sha256:59a6c8b71a245800e923cb684a2dc0eac19c56493e2f896218fcf2571ed28984"},
    {file = "fonttools-4.47.0-cp310-cp310-win_amd64.whl", hash = "sha256:52c82df66201f3a90db438d9d7b337c7c98139de598d0728fb99dab9fd0495ca"},
    {file = "fonttools-4.47.0-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:854421e328d47d70aa5abceacbe8eef231961b162c71cbe7ff3f47e235e2e5c5"},
    {file = "fonttools-4.47.0-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:511482df31cfea9f697930f61520f6541185fa5eeba2fa760fe72e8eee5af88b"},
    {file = "fonttools-4.47.0-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:ce0e2c88c8c985b7b9a7efcd06511fb0a1fe3ddd9a6cd2895ef1dbf9059719d7"},
    {file = "fonttools-4.47.0-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:e7a0a8848726956e9d9fb18c977a279013daadf0cbb6725d2015a6dd57527992"},
    {file = "fonttools-4.47.0-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:e869da810ae35afb3019baa0d0306cdbab4760a54909c89ad8904fa629991812"},
    {file = "fonttools-4.47.0-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:dd23848f877c3754f53a4903fb7a593ed100924f9b4bff7d5a4e2e8a7001ae11"},
    {file = "fonttools-4.47.0-cp311-cp311-win32.whl", hash = "sha256:bf1810635c00f7c45d93085611c995fc130009cec5abdc35b327156aa191f982"},
    {file = "fonttools-4.47.0-cp311-cp311-win_amd64.whl", hash = "sha256:61df4dee5d38ab65b26da8efd62d859a1eef7a34dcbc331299a28e24d04c59a7"},
    {file = "fonttools-4.47.0-cp312-cp312-macosx_10_9_universal2.whl", hash = "sha256:e3f4d61f3a8195eac784f1d0c16c0a3105382c1b9a74d99ac4ba421da39a8826"},
    {file = "fonttools-4.47.0-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:174995f7b057e799355b393e97f4f93ef1f2197cbfa945e988d49b2a09ecbce8"},
    {file = "fonttools-4.47.0-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:ea592e6a09b71cb7a7661dd93ac0b877a6228e2d677ebacbad0a4d118494c86d"},
    {file = "fonttools-4.47.0-cp312-cp312-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:40bdbe90b33897d9cc4a39f8e415b0fcdeae4c40a99374b8a4982f127ff5c767"},
    {file = "fonttools-4.47.0-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:843509ae9b93db5aaf1a6302085e30bddc1111d31e11d724584818f5b698f500"},
    {file = "fonttools-4.47.0-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:9acfa1cdc479e0dde528b61423855913d949a7f7fe09e276228298fef4589540"},
    {file = "fonttools-4.47.0-cp312-cp312-win32.whl", hash = "sha256:66c92ec7f95fd9732550ebedefcd190a8d81beaa97e89d523a0d17198a8bda4d"},
    {file = "fonttools-4.47.0-cp312-cp312-win_amd64.whl", hash = "sha256:e8fa20748de55d0021f83754b371432dca0439e02847962fc4c42a0e444c2d78"},
    {file = "fonttools-4.47.0-cp38-cp38-macosx_10_9_universal2.whl", hash = "sha256:c75e19971209fbbce891ebfd1b10c37320a5a28e8d438861c21d35305aedb81c"},
    {file = "fonttools-4.47.0-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:e79f1a3970d25f692bbb8c8c2637e621a66c0d60c109ab48d4a160f50856deff"},
    {file = "fonttools-4.47.0-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:562681188c62c024fe2c611b32e08b8de2afa00c0c4e72bed47c47c318e16d5c"},
    {file = "fonttools-4.47.0-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:a77a60315c33393b2bd29d538d1ef026060a63d3a49a9233b779261bad9c3f71"},
    {file = "fonttools-4.47.0-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:b4fabb8cc9422efae1a925160083fdcbab8fdc96a8483441eb7457235df625bd"},
    {file = "fonttools-4.47.0-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:2a78dba8c2a1e9d53a0fb5382979f024200dc86adc46a56cbb668a2249862fda"},
    {file = "fonttools-4.47.0-cp38-cp38-win32.whl", hash = "sha256:e6b968543fde4119231c12c2a953dcf83349590ca631ba8216a8edf9cd4d36a9"},
    {file = "fonttools-4.47.0-cp38-cp38-win_amd64.whl", hash = "sha256:4a9a51745c0439516d947480d4d884fa18bd1458e05b829e482b9269afa655bc"},
    {file = "fonttools-4.47.0-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:62d8ddb058b8e87018e5dc26f3258e2c30daad4c87262dfeb0e2617dd84750e6"},
    {file = "fonttools-4.47.0-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:5dde0eab40faaa5476133123f6a622a1cc3ac9b7af45d65690870620323308b4"},
    {file = "fonttools-4.47.0-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:f4da089f6dfdb822293bde576916492cd708c37c2501c3651adde39804630538"},
    {file = "fonttools-4.47.0-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:253bb46bab970e8aae254cebf2ae3db98a4ef6bd034707aa68a239027d2b198d"},
    {file = "fonttools-4.47.0-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:1193fb090061efa2f9e2d8d743ae9850c77b66746a3b32792324cdce65784154"},
    {file = "fonttools-4.47.0-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:084511482dd265bce6dca24c509894062f0117e4e6869384d853f46c0e6d43be"},
    {file = "fonttools-4.47.0-cp39-cp39-win32.whl", hash = "sha256:97620c4af36e4c849e52661492e31dc36916df12571cb900d16960ab8e92a980"},
    {file = "fonttools-4.47.0-cp39-cp39-win_amd64.whl", hash = "sha256:e77bdf52185bdaf63d39f3e1ac3212e6cfa3ab07d509b94557a8902ce9c13c82"},
    {file = "fonttools-4.47.0-py3-none-any.whl", hash = "sha256:d6477ba902dd2d7adda7f0fd3bfaeb92885d45993c9e1928c9f28fc3961415f7"},
    {file = "fonttools-4.47.0.tar.gz", hash = "sha256:ec13a10715eef0e031858c1c23bfaee6cba02b97558e4a7bfa089dba4a8c2ebf"},
]

[package.dependencies]
brotli = {version = ">=1.0.1", optional = true, markers = "platform_python_implementation == \"CPython\" and extra == \"woff\""}
brotlicffi = {version = ">=0.8.0", optional = true, markers = "platform_python_implementation != \"CPython\" and extra == \"woff\""}
zopfli = {version = ">=0.1.4", optional = true, markers = "extra == \"woff\""}

[package.extras]
all = ["brotli (>=1.0.1)", "brotlicffi (>=0.8.0)", "fs (>=2.2.0,<3)", "lxml (>=4.0,<5)", "lz4 (>=1.7.4.2)", "matplotlib", "munkres", "pycairo", "scipy", "skia-pathops (>=0.5.0)", "sympy", "uharfbuzz (>=0.23.0)", "unicodedata2 (>=15.1.0)", "xattr", "zopfli (>=0.1.4)"]
graphite = ["lz4 (>=1.7.4.2)"]
interpolatable = ["munkres", "pycairo", "scipy"]
lxml = ["lxml (>=4.0,<5)"]
pathops = ["skia-pathops (>=0.5.0)"]
plot = ["matplotlib"]
repacker = ["uharfbuzz (>=0.23.0)"]
symfont = ["sympy"]
type1 = ["xattr"]
ufo = ["fs (>=2.2.0,<3)"]
unicode = ["unicodedata2 (>=15.1.0)"]
woff = ["brotli (>=1.0.1)", "brotlicffi (>=0.8.0)", "zopfli (>=0.1.4)"]

[[package]]
name = "frozenlist"
version = "1.4.1"
description = "A list-like structure which implements collections.abc.MutableSequence"
optional = false
python-versions = ">=3.8"
files = [
    {file = "frozenlist-1.4.1-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:f9aa1878d1083b276b0196f2dfbe00c9b7e752475ed3b682025ff20c1c1f51ac"},
    {file = "frozenlist-1.4.1-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:29acab3f66f0f24674b7dc4736477bcd4bc3ad4b896f5f45379a67bce8b96868"},
    {file = "frozenlist-1.4.1-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:74fb4bee6880b529a0c6560885fce4dc95936920f9f20f53d99a213f7bf66776"},
    {file = "frozenlist-1.4.1-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:590344787a90ae57d62511dd7c736ed56b428f04cd8c161fcc5e7232c130c69a"},
    {file = "frozenlist-1.4.1-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:068b63f23b17df8569b7fdca5517edef76171cf3897eb68beb01341131fbd2ad"},
    {file = "frozenlist-1.4.1-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:5c849d495bf5154cd8da18a9eb15db127d4dba2968d88831aff6f0331ea9bd4c"},
    {file = "frozenlist-1.4.1-cp310-cp310-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:9750cc7fe1ae3b1611bb8cfc3f9ec11d532244235d75901fb6b8e42ce9229dfe"},
    {file = "frozenlist-1.4.1-cp310-cp310-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:a9b2de4cf0cdd5bd2dee4c4f63a653c61d2408055ab77b151c1957f221cabf2a"},
    {file = "frozenlist-1.4.1-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:0633c8d5337cb5c77acbccc6357ac49a1770b8c487e5b3505c57b949b4b82e98"},
    {file = "frozenlist-1.4.1-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:27657df69e8801be6c3638054e202a135c7f299267f1a55ed3a598934f6c0d75"},
    {file = "frozenlist-1.4.1-cp310-cp310-musllinux_1_1_ppc64le.whl", hash = "sha256:f9a3ea26252bd92f570600098783d1371354d89d5f6b7dfd87359d669f2109b5"},
    {file = "frozenlist-1.4.1-cp310-cp310-musllinux_1_1_s390x.whl", hash = "sha256:4f57dab5fe3407b6c0c1cc907ac98e8a189f9e418f3b6e54d65a718aaafe3950"},
    {file = "frozenlist-1.4.1-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:e02a0e11cf6597299b9f3bbd3f93d79217cb90cfd1411aec33848b13f5c656cc"},
    {file = "frozenlist-1.4.1-cp310-cp310-win32.whl", hash = "sha256:a828c57f00f729620a442881cc60e57cfcec6842ba38e1b19fd3e47ac0ff8dc1"},
    {file = "frozenlist-1.4.1-cp310-cp310-win_amd64.whl", hash = "sha256:f56e2333dda1fe0f909e7cc59f021eba0d2307bc6f012a1ccf2beca6ba362439"},
    {file = "frozenlist-1.4.1-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:a0cb6f11204443f27a1628b0e460f37fb30f624be6051d490fa7d7e26d4af3d0"},
    {file = "frozenlist-1.4.1-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:b46c8ae3a8f1f41a0d2ef350c0b6e65822d80772fe46b653ab6b6274f61d4a49"},
    {file = "frozenlist-1.4.1-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:fde5bd59ab5357e3853313127f4d3565fc7dad314a74d7b5d43c22c6a5ed2ced"},
    {file = "frozenlist-1.4.1-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:722e1124aec435320ae01ee3ac7bec11a5d47f25d0ed6328f2273d287bc3abb0"},
    {file = "frozenlist-1.4.1-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:2471c201b70d58a0f0c1f91261542a03d9a5e088ed3dc6c160d614c01649c106"},
    {file = "frozenlist-1.4.1-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:c757a9dd70d72b076d6f68efdbb9bc943665ae954dad2801b874c8c69e185068"},
    {file = "frozenlist-1.4.1-cp311-cp311-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:f146e0911cb2f1da549fc58fc7bcd2b836a44b79ef871980d605ec392ff6b0d2"},
    {file = "frozenlist-1.4.1-cp311-cp311-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:4f9c515e7914626b2a2e1e311794b4c35720a0be87af52b79ff8e1429fc25f19"},
    {file = "frozenlist-1.4.1-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:c302220494f5c1ebeb0912ea782bcd5e2f8308037b3c7553fad0e48ebad6ad82"},
    {file = "frozenlist-1.4.1-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:442acde1e068288a4ba7acfe05f5f343e19fac87bfc96d89eb886b0363e977ec"},
    {file = "frozenlist-1.4.1-cp311-cp311-musllinux_1_1_ppc64le.whl", hash = "sha256:1b280e6507ea8a4fa0c0a7150b4e526a8d113989e28eaaef946cc77ffd7efc0a"},
    {file = "frozenlist-1.4.1-cp311-cp311-musllinux_1_1_s390x.whl", hash = "sha256:fe1a06da377e3a1062ae5fe0926e12b84eceb8a50b350ddca72dc85015873f74"},
    {file = "frozenlist-1.4.1-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:db9e724bebd621d9beca794f2a4ff1d26eed5965b004a97f1f1685a173b869c2"},
    {file = "frozenlist-1.4.1-cp311-cp311-win32.whl", hash = "sha256:e774d53b1a477a67838a904131c4b0eef6b3d8a651f8b138b04f748fccfefe17"},
    {file = "frozenlist-1.4.1-cp311-cp311-win_amd64.whl", hash = "sha256:fb3c2db03683b5767dedb5769b8a40ebb47d6f7f45b1b3e3b4b51ec8ad9d9825"},
    {file = "frozenlist-1.4.1-cp312-cp312-macosx_10_9_universal2.whl", hash = "sha256:1979bc0aeb89b33b588c51c54ab0161791149f2461ea7c7c946d95d5f93b56ae"},
    {file = "frozenlist-1.4.1-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:cc7b01b3754ea68a62bd77ce6020afaffb44a590c2289089289363472d13aedb"},
    {file = "frozenlist-1.4.1-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:c9c92be9fd329ac801cc420e08452b70e7aeab94ea4233a4804f0915c14eba9b"},
    {file = "frozenlist-1.4.1-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:5c3894db91f5a489fc8fa6a9991820f368f0b3cbdb9cd8849547ccfab3392d86"},
    {file = "frozenlist-1.4.1-cp312-cp312-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:ba60bb19387e13597fb059f32cd4d59445d7b18b69a745b8f8e5db0346f33480"},
    {file = "frozenlist-1.4.1-cp312-cp312-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:8aefbba5f69d42246543407ed2461db31006b0f76c4e32dfd6f42215a2c41d09"},
    {file = "frozenlist-1.4.1-cp312-cp312-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:780d3a35680ced9ce682fbcf4cb9c2bad3136eeff760ab33707b71db84664e3a"},
    {file = "frozenlist-1.4.1-cp312-cp312-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:9acbb16f06fe7f52f441bb6f413ebae6c37baa6ef9edd49cdd567216da8600cd"},
    {file = "frozenlist-1.4.1-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:23b701e65c7b36e4bf15546a89279bd4d8675faabc287d06bbcfac7d3c33e1e6"},
    {file = "frozenlist-1.4.1-cp312-cp312-musllinux_1_1_i686.whl", hash = "sha256:3e0153a805a98f5ada7e09826255ba99fb4f7524bb81bf6b47fb702666484ae1"},
    {file = "frozenlist-1.4.1-cp312-cp312-musllinux_1_1_ppc64le.whl", hash = "sha256:dd9b1baec094d91bf36ec729445f7769d0d0cf6b64d04d86e45baf89e2b9059b"},
    {file = "frozenlist-1.4.1-cp312-cp312-musllinux_1_1_s390x.whl", hash = "sha256:1a4471094e146b6790f61b98616ab8e44f72661879cc63fa1049d13ef711e71e"},
    {file = "frozenlist-1.4.1-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:5667ed53d68d91920defdf4035d1cdaa3c3121dc0b113255124bcfada1cfa1b8"},
    {file = "frozenlist-1.4.1-cp312-cp312-win32.whl", hash = "sha256:beee944ae828747fd7cb216a70f120767fc9f4f00bacae8543c14a6831673f89"},
    {file = "frozenlist-1.4.1-cp312-cp312-win_amd64.whl", hash = "sha256:64536573d0a2cb6e625cf309984e2d873979709f2cf22839bf2d61790b448ad5"},
    {file = "frozenlist-1.4.1-cp38-cp38-macosx_10_9_universal2.whl", hash = "sha256:20b51fa3f588ff2fe658663db52a41a4f7aa6c04f6201449c6c7c476bd255c0d"},
    {file = "frozenlist-1.4.1-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:410478a0c562d1a5bcc2f7ea448359fcb050ed48b3c6f6f4f18c313a9bdb1826"},
    {file = "frozenlist-1.4.1-cp38-cp38-macosx_11_0_arm64.whl", hash = "sha256:c6321c9efe29975232da3bd0af0ad216800a47e93d763ce64f291917a381b8eb"},
    {file = "frozenlist-1.4.1-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:48f6a4533887e189dae092f1cf981f2e3885175f7a0f33c91fb5b7b682b6bab6"},
    {file = "frozenlist-1.4.1-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:6eb73fa5426ea69ee0e012fb59cdc76a15b1283d6e32e4f8dc4482ec67d1194d"},
    {file = "frozenlist-1.4.1-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:fbeb989b5cc29e8daf7f976b421c220f1b8c731cbf22b9130d8815418ea45887"},
    {file = "frozenlist-1.4.1-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:32453c1de775c889eb4e22f1197fe3bdfe457d16476ea407472b9442e6295f7a"},
    {file = "frozenlist-1.4.1-cp38-cp38-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:693945278a31f2086d9bf3df0fe8254bbeaef1fe71e1351c3bd730aa7d31c41b"},
    {file = "frozenlist-1.4.1-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:1d0ce09d36d53bbbe566fe296965b23b961764c0bcf3ce2fa45f463745c04701"},
    {file = "frozenlist-1.4.1-cp38-cp38-musllinux_1_1_i686.whl", hash = "sha256:3a670dc61eb0d0eb7080890c13de3066790f9049b47b0de04007090807c776b0"},
    {file = "frozenlist-1.4.1-cp38-cp38-musllinux_1_1_ppc64le.whl", hash = "sha256:dca69045298ce5c11fd539682cff879cc1e664c245d1c64da929813e54241d11"},
    {file = "frozenlist-1.4.1-cp38-cp38-musllinux_1_1_s390x.whl", hash = "sha256:a06339f38e9ed3a64e4c4e43aec7f59084033647f908e4259d279a52d3757d09"},
    {file = "frozenlist-1.4.1-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:b7f2f9f912dca3934c1baec2e4585a674ef16fe00218d833856408c48d5beee7"},
    {file = "frozenlist-1.4.1-cp38-cp38-win32.whl", hash = "sha256:e7004be74cbb7d9f34553a5ce5fb08be14fb33bc86f332fb71cbe5216362a497"},
    {file = "frozenlist-1.4.1-cp38-cp38-win_amd64.whl", hash = "sha256:5a7d70357e7cee13f470c7883a063aae5fe209a493c57d86eb7f5a6f910fae09"},
    {file = "frozenlist-1.4.1-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:bfa4a17e17ce9abf47a74ae02f32d014c5e9404b6d9ac7f729e01562bbee601e"},
    {file = "frozenlist-1.4.1-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:b7e3ed87d4138356775346e6845cccbe66cd9e207f3cd11d2f0b9fd13681359d"},
    {file = "frozenlist-1.4.1-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:c99169d4ff810155ca50b4da3b075cbde79752443117d89429595c2e8e37fed8"},
    {file = "frozenlist-1.4.1-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:edb678da49d9f72c9f6c609fbe41a5dfb9a9282f9e6a2253d5a91e0fc382d7c0"},
    {file = "frozenlist-1.4.1-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:6db4667b187a6742b33afbbaf05a7bc551ffcf1ced0000a571aedbb4aa42fc7b"},
    {file = "frozenlist-1.4.1-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:55fdc093b5a3cb41d420884cdaf37a1e74c3c37a31f46e66286d9145d2063bd0"},
    {file = "frozenlist-1.4.1-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:82e8211d69a4f4bc360ea22cd6555f8e61a1bd211d1d5d39d3d228b48c83a897"},
    {file = "frozenlist-1.4.1-cp39-cp39-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:89aa2c2eeb20957be2d950b85974b30a01a762f3308cd02bb15e1ad632e22dc7"},
    {file = "frozenlist-1.4.1-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:9d3e0c25a2350080e9319724dede4f31f43a6c9779be48021a7f4ebde8b2d742"},
    {file = "frozenlist-1.4.1-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:7268252af60904bf52c26173cbadc3a071cece75f873705419c8681f24d3edea"},
    {file = "frozenlist-1.4.1-cp39-cp39-musllinux_1_1_ppc64le.whl", hash = "sha256:0c250a29735d4f15321007fb02865f0e6b6a41a6b88f1f523ca1596ab5f50bd5"},
    {file = "frozenlist-1.4.1-cp39-cp39-musllinux_1_1_s390x.whl", hash = "sha256:96ec70beabbd3b10e8bfe52616a13561e58fe84c0101dd031dc78f250d5128b9"},
    {file = "frozenlist-1.4.1-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:23b2d7679b73fe0e5a4560b672a39f98dfc6f60df63823b0a9970525325b95f6"},
    {file = "frozenlist-1.4.1-cp39-cp39-win32.whl", hash = "sha256:a7496bfe1da7fb1a4e1cc23bb67c58fab69311cc7d32b5a99c2007b4b2a0e932"},
    {file = "frozenlist-1.4.1-cp39-cp39-win_amd64.whl", hash = "sha256:e6a20a581f9ce92d389a8c7d7c3dd47c81fd5d6e655c8dddf341e14aa48659d0"},
    {file = "frozenlist-1.4.1-py3-none-any.whl", hash = "sha256:04ced3e6a46b4cfffe20f9ae482818e34eba9b5fb0ce4056e4cc9b6e212d09b7"},
    {file = "frozenlist-1.4.1.tar.gz", hash = "sha256:c037a86e8513059a2613aaba4d817bb90b9d9b6b69aace3ce9c877e8c8ed402b"},
]

[[package]]
name = "google-ai-generativelanguage"
version = "0.4.0"
description = "Google Ai Generativelanguage API client library"
optional = false
python-versions = ">=3.7"
files = [
    {file = "google-ai-generativelanguage-0.4.0.tar.gz", hash = "sha256:c8199066c08f74c4e91290778329bb9f357ba1ea5d6f82de2bc0d10552bf4f8c"},
    {file = "google_ai_generativelanguage-0.4.0-py3-none-any.whl", hash = "sha256:e4c425376c1ee26c78acbc49a24f735f90ebfa81bf1a06495fae509a2433232c"},
]

[package.dependencies]
google-api-core = {version = ">=1.34.0,<2.0.dev0 || >=2.11.dev0,<3.0.0dev", extras = ["grpc"]}
proto-plus = ">=1.22.3,<2.0.0dev"
protobuf = ">=3.19.5,<3.20.0 || >3.20.0,<3.20.1 || >3.20.1,<4.21.0 || >4.21.0,<4.21.1 || >4.21.1,<4.21.2 || >4.21.2,<4.21.3 || >4.21.3,<4.21.4 || >4.21.4,<4.21.5 || >4.21.5,<5.0.0dev"

[[package]]
name = "google-api-core"
version = "2.18.0"
description = "Google API client core library"
optional = false
python-versions = ">=3.7"
files = [
    {file = "google-api-core-2.18.0.tar.gz", hash = "sha256:62d97417bfc674d6cef251e5c4d639a9655e00c45528c4364fbfebb478ce72a9"},
    {file = "google_api_core-2.18.0-py3-none-any.whl", hash = "sha256:5a63aa102e0049abe85b5b88cb9409234c1f70afcda21ce1e40b285b9629c1d6"},
]

[package.dependencies]
google-auth = ">=2.14.1,<3.0.dev0"
googleapis-common-protos = ">=1.56.2,<2.0.dev0"
grpcio = [
    {version = ">=1.49.1,<2.0dev", optional = true, markers = "python_version >= \"3.11\" and extra == \"grpc\""},
    {version = ">=1.33.2,<2.0dev", optional = true, markers = "python_version < \"3.11\" and extra == \"grpc\""},
]
grpcio-status = [
    {version = ">=1.49.1,<2.0.dev0", optional = true, markers = "python_version >= \"3.11\" and extra == \"grpc\""},
    {version = ">=1.33.2,<2.0.dev0", optional = true, markers = "python_version < \"3.11\" and extra == \"grpc\""},
]
proto-plus = ">=1.22.3,<2.0.0dev"
protobuf = ">=3.19.5,<3.20.0 || >3.20.0,<3.20.1 || >3.20.1,<4.21.0 || >4.21.0,<4.21.1 || >4.21.1,<4.21.2 || >4.21.2,<4.21.3 || >4.21.3,<4.21.4 || >4.21.4,<4.21.5 || >4.21.5,<5.0.0.dev0"
requests = ">=2.18.0,<3.0.0.dev0"

[package.extras]
grpc = ["grpcio (>=1.33.2,<2.0dev)", "grpcio (>=1.49.1,<2.0dev)", "grpcio-status (>=1.33.2,<2.0.dev0)", "grpcio-status (>=1.49.1,<2.0.dev0)"]
grpcgcp = ["grpcio-gcp (>=0.2.2,<1.0.dev0)"]
grpcio-gcp = ["grpcio-gcp (>=0.2.2,<1.0.dev0)"]

[[package]]
name = "google-auth"
version = "2.29.0"
description = "Google Authentication Library"
optional = false
python-versions = ">=3.7"
files = [
    {file = "google-auth-2.29.0.tar.gz", hash = "sha256:672dff332d073227550ffc7457868ac4218d6c500b155fe6cc17d2b13602c360"},
    {file = "google_auth-2.29.0-py2.py3-none-any.whl", hash = "sha256:d452ad095688cd52bae0ad6fafe027f6a6d6f560e810fec20914e17a09526415"},
]

[package.dependencies]
cachetools = ">=2.0.0,<6.0"
pyasn1-modules = ">=0.2.1"
rsa = ">=3.1.4,<5"

[package.extras]
aiohttp = ["aiohttp (>=3.6.2,<4.0.0.dev0)", "requests (>=2.20.0,<3.0.0.dev0)"]
enterprise-cert = ["cryptography (==36.0.2)", "pyopenssl (==22.0.0)"]
pyopenssl = ["cryptography (>=38.0.3)", "pyopenssl (>=20.0.0)"]
reauth = ["pyu2f (>=0.1.5)"]
requests = ["requests (>=2.20.0,<3.0.0.dev0)"]

[[package]]
name = "google-generativeai"
version = "0.4.1"
description = "Google Generative AI High level API client library and tools."
optional = false
python-versions = ">=3.9"
files = [
    {file = "google_generativeai-0.4.1-py3-none-any.whl", hash = "sha256:89be3c00c2e688108fccefc50f47f45fc9d37ecd53c1ade9d86b5d982919c24a"},
]

[package.dependencies]
google-ai-generativelanguage = "0.4.0"
google-api-core = "*"
google-auth = ">=2.15.0"
protobuf = "*"
pydantic = "*"
tqdm = "*"
typing-extensions = "*"

[package.extras]
dev = ["Pillow", "absl-py", "black", "ipython", "nose2", "pandas", "pytype", "pyyaml"]

[[package]]
name = "googleapis-common-protos"
version = "1.63.0"
description = "Common protobufs used in Google APIs"
optional = false
python-versions = ">=3.7"
files = [
    {file = "googleapis-common-protos-1.63.0.tar.gz", hash = "sha256:17ad01b11d5f1d0171c06d3ba5c04c54474e883b66b949722b4938ee2694ef4e"},
    {file = "googleapis_common_protos-1.63.0-py2.py3-none-any.whl", hash = "sha256:ae45f75702f7c08b541f750854a678bd8f534a1a6bace6afe975f1d0a82d6632"},
]

[package.dependencies]
protobuf = ">=3.19.5,<3.20.0 || >3.20.0,<3.20.1 || >3.20.1,<4.21.1 || >4.21.1,<4.21.2 || >4.21.2,<4.21.3 || >4.21.3,<4.21.4 || >4.21.4,<4.21.5 || >4.21.5,<5.0.0.dev0"

[package.extras]
grpc = ["grpcio (>=1.44.0,<2.0.0.dev0)"]

[[package]]
name = "greenlet"
version = "3.0.0"
description = "Lightweight in-process concurrent programming"
optional = false
python-versions = ">=3.7"
files = [
    {file = "greenlet-3.0.0-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:e09dea87cc91aea5500262993cbd484b41edf8af74f976719dd83fe724644cd6"},
    {file = "greenlet-3.0.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:f47932c434a3c8d3c86d865443fadc1fbf574e9b11d6650b656e602b1797908a"},
    {file = "greenlet-3.0.0-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:bdfaeecf8cc705d35d8e6de324bf58427d7eafb55f67050d8f28053a3d57118c"},
    {file = "greenlet-3.0.0-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:6a68d670c8f89ff65c82b936275369e532772eebc027c3be68c6b87ad05ca695"},
    {file = "greenlet-3.0.0-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:38ad562a104cd41e9d4644f46ea37167b93190c6d5e4048fcc4b80d34ecb278f"},
    {file = "greenlet-3.0.0-cp310-cp310-manylinux_2_24_x86_64.manylinux_2_28_x86_64.whl", hash = "sha256:02a807b2a58d5cdebb07050efe3d7deaf915468d112dfcf5e426d0564aa3aa4a"},
    {file = "greenlet-3.0.0-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:b1660a15a446206c8545edc292ab5c48b91ff732f91b3d3b30d9a915d5ec4779"},
    {file = "greenlet-3.0.0-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:813720bd57e193391dfe26f4871186cf460848b83df7e23e6bef698a7624b4c9"},
    {file = "greenlet-3.0.0-cp310-cp310-win_amd64.whl", hash = "sha256:aa15a2ec737cb609ed48902b45c5e4ff6044feb5dcdfcf6fa8482379190330d7"},
    {file = "greenlet-3.0.0-cp310-universal2-macosx_11_0_x86_64.whl", hash = "sha256:7709fd7bb02b31908dc8fd35bfd0a29fc24681d5cc9ac1d64ad07f8d2b7db62f"},
    {file = "greenlet-3.0.0-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:211ef8d174601b80e01436f4e6905aca341b15a566f35a10dd8d1e93f5dbb3b7"},
    {file = "greenlet-3.0.0-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:6512592cc49b2c6d9b19fbaa0312124cd4c4c8a90d28473f86f92685cc5fef8e"},
    {file = "greenlet-3.0.0-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:871b0a8835f9e9d461b7fdaa1b57e3492dd45398e87324c047469ce2fc9f516c"},
    {file = "greenlet-3.0.0-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:b505fcfc26f4148551826a96f7317e02c400665fa0883fe505d4fcaab1dabfdd"},
    {file = "greenlet-3.0.0-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:123910c58234a8d40eaab595bc56a5ae49bdd90122dde5bdc012c20595a94c14"},
    {file = "greenlet-3.0.0-cp311-cp311-manylinux_2_24_x86_64.manylinux_2_28_x86_64.whl", hash = "sha256:96d9ea57292f636ec851a9bb961a5cc0f9976900e16e5d5647f19aa36ba6366b"},
    {file = "greenlet-3.0.0-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:0b72b802496cccbd9b31acea72b6f87e7771ccfd7f7927437d592e5c92ed703c"},
    {file = "greenlet-3.0.0-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:527cd90ba3d8d7ae7dceb06fda619895768a46a1b4e423bdb24c1969823b8362"},
    {file = "greenlet-3.0.0-cp311-cp311-win_amd64.whl", hash = "sha256:37f60b3a42d8b5499be910d1267b24355c495064f271cfe74bf28b17b099133c"},
    {file = "greenlet-3.0.0-cp312-cp312-macosx_10_9_universal2.whl", hash = "sha256:1482fba7fbed96ea7842b5a7fc11d61727e8be75a077e603e8ab49d24e234383"},
    {file = "greenlet-3.0.0-cp312-cp312-macosx_13_0_arm64.whl", hash = "sha256:be557119bf467d37a8099d91fbf11b2de5eb1fd5fc5b91598407574848dc910f"},
    {file = "greenlet-3.0.0-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:73b2f1922a39d5d59cc0e597987300df3396b148a9bd10b76a058a2f2772fc04"},
    {file = "greenlet-3.0.0-cp312-cp312-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:d1e22c22f7826096ad503e9bb681b05b8c1f5a8138469b255eb91f26a76634f2"},
    {file = "greenlet-3.0.0-cp312-cp312-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:1d363666acc21d2c204dd8705c0e0457d7b2ee7a76cb16ffc099d6799744ac99"},
    {file = "greenlet-3.0.0-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:334ef6ed8337bd0b58bb0ae4f7f2dcc84c9f116e474bb4ec250a8bb9bd797a66"},
    {file = "greenlet-3.0.0-cp312-cp312-manylinux_2_24_x86_64.manylinux_2_28_x86_64.whl", hash = "sha256:6672fdde0fd1a60b44fb1751a7779c6db487e42b0cc65e7caa6aa686874e79fb"},
    {file = "greenlet-3.0.0-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:952256c2bc5b4ee8df8dfc54fc4de330970bf5d79253c863fb5e6761f00dda35"},
    {file = "greenlet-3.0.0-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:269d06fa0f9624455ce08ae0179430eea61085e3cf6457f05982b37fd2cefe17"},
    {file = "greenlet-3.0.0-cp312-cp312-win_amd64.whl", hash = "sha256:9adbd8ecf097e34ada8efde9b6fec4dd2a903b1e98037adf72d12993a1c80b51"},
    {file = "greenlet-3.0.0-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:c6b5ce7f40f0e2f8b88c28e6691ca6806814157ff05e794cdd161be928550f4c"},
    {file = "greenlet-3.0.0-cp37-cp37m-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:ecf94aa539e97a8411b5ea52fc6ccd8371be9550c4041011a091eb8b3ca1d810"},
    {file = "greenlet-3.0.0-cp37-cp37m-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:80dcd3c938cbcac986c5c92779db8e8ce51a89a849c135172c88ecbdc8c056b7"},
    {file = "greenlet-3.0.0-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:e52a712c38e5fb4fd68e00dc3caf00b60cb65634d50e32281a9d6431b33b4af1"},
    {file = "greenlet-3.0.0-cp37-cp37m-manylinux_2_24_x86_64.manylinux_2_28_x86_64.whl", hash = "sha256:d5539f6da3418c3dc002739cb2bb8d169056aa66e0c83f6bacae0cd3ac26b423"},
    {file = "greenlet-3.0.0-cp37-cp37m-musllinux_1_1_aarch64.whl", hash = "sha256:343675e0da2f3c69d3fb1e894ba0a1acf58f481f3b9372ce1eb465ef93cf6fed"},
    {file = "greenlet-3.0.0-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:abe1ef3d780de56defd0c77c5ba95e152f4e4c4e12d7e11dd8447d338b85a625"},
    {file = "greenlet-3.0.0-cp37-cp37m-win32.whl", hash = "sha256:e693e759e172fa1c2c90d35dea4acbdd1d609b6936115d3739148d5e4cd11947"},
    {file = "greenlet-3.0.0-cp37-cp37m-win_amd64.whl", hash = "sha256:bdd696947cd695924aecb3870660b7545a19851f93b9d327ef8236bfc49be705"},
    {file = "greenlet-3.0.0-cp37-universal2-macosx_11_0_x86_64.whl", hash = "sha256:cc3e2679ea13b4de79bdc44b25a0c4fcd5e94e21b8f290791744ac42d34a0353"},
    {file = "greenlet-3.0.0-cp38-cp38-macosx_11_0_universal2.whl", hash = "sha256:63acdc34c9cde42a6534518e32ce55c30f932b473c62c235a466469a710bfbf9"},
    {file = "greenlet-3.0.0-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:4a1a6244ff96343e9994e37e5b4839f09a0207d35ef6134dce5c20d260d0302c"},
    {file = "greenlet-3.0.0-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:b822fab253ac0f330ee807e7485769e3ac85d5eef827ca224feaaefa462dc0d0"},
    {file = "greenlet-3.0.0-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:8060b32d8586e912a7b7dac2d15b28dbbd63a174ab32f5bc6d107a1c4143f40b"},
    {file = "greenlet-3.0.0-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:621fcb346141ae08cb95424ebfc5b014361621b8132c48e538e34c3c93ac7365"},
    {file = "greenlet-3.0.0-cp38-cp38-manylinux_2_24_x86_64.manylinux_2_28_x86_64.whl", hash = "sha256:6bb36985f606a7c49916eff74ab99399cdfd09241c375d5a820bb855dfb4af9f"},
    {file = "greenlet-3.0.0-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:10b5582744abd9858947d163843d323d0b67be9432db50f8bf83031032bc218d"},
    {file = "greenlet-3.0.0-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:f351479a6914fd81a55c8e68963609f792d9b067fb8a60a042c585a621e0de4f"},
    {file = "greenlet-3.0.0-cp38-cp38-win32.whl", hash = "sha256:9de687479faec7db5b198cc365bc34addd256b0028956501f4d4d5e9ca2e240a"},
    {file = "greenlet-3.0.0-cp38-cp38-win_amd64.whl", hash = "sha256:3fd2b18432e7298fcbec3d39e1a0aa91ae9ea1c93356ec089421fabc3651572b"},
    {file = "greenlet-3.0.0-cp38-universal2-macosx_11_0_x86_64.whl", hash = "sha256:3c0d36f5adc6e6100aedbc976d7428a9f7194ea79911aa4bf471f44ee13a9464"},
    {file = "greenlet-3.0.0-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:4cd83fb8d8e17633ad534d9ac93719ef8937568d730ef07ac3a98cb520fd93e4"},
    {file = "greenlet-3.0.0-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:6a5b2d4cdaf1c71057ff823a19d850ed5c6c2d3686cb71f73ae4d6382aaa7a06"},
    {file = "greenlet-3.0.0-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:2e7dcdfad252f2ca83c685b0fa9fba00e4d8f243b73839229d56ee3d9d219314"},
    {file = "greenlet-3.0.0-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:c94e4e924d09b5a3e37b853fe5924a95eac058cb6f6fb437ebb588b7eda79870"},
    {file = "greenlet-3.0.0-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:ad6fb737e46b8bd63156b8f59ba6cdef46fe2b7db0c5804388a2d0519b8ddb99"},
    {file = "greenlet-3.0.0-cp39-cp39-manylinux_2_24_x86_64.manylinux_2_28_x86_64.whl", hash = "sha256:d55db1db455c59b46f794346efce896e754b8942817f46a1bada2d29446e305a"},
    {file = "greenlet-3.0.0-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:56867a3b3cf26dc8a0beecdb4459c59f4c47cdd5424618c08515f682e1d46692"},
    {file = "greenlet-3.0.0-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:9a812224a5fb17a538207e8cf8e86f517df2080c8ee0f8c1ed2bdaccd18f38f4"},
    {file = "greenlet-3.0.0-cp39-cp39-win32.whl", hash = "sha256:0d3f83ffb18dc57243e0151331e3c383b05e5b6c5029ac29f754745c800f8ed9"},
    {file = "greenlet-3.0.0-cp39-cp39-win_amd64.whl", hash = "sha256:831d6f35037cf18ca5e80a737a27d822d87cd922521d18ed3dbc8a6967be50ce"},
    {file = "greenlet-3.0.0-cp39-universal2-macosx_11_0_x86_64.whl", hash = "sha256:a048293392d4e058298710a54dfaefcefdf49d287cd33fb1f7d63d55426e4355"},
    {file = "greenlet-3.0.0.tar.gz", hash = "sha256:19834e3f91f485442adc1ee440171ec5d9a4840a1f7bd5ed97833544719ce10b"},
]

[package.extras]
docs = ["Sphinx"]
test = ["objgraph", "psutil"]

[[package]]
name = "grpcio"
version = "1.62.1"
description = "HTTP/2-based RPC framework"
optional = false
python-versions = ">=3.7"
files = [
    {file = "grpcio-1.62.1-cp310-cp310-linux_armv7l.whl", hash = "sha256:179bee6f5ed7b5f618844f760b6acf7e910988de77a4f75b95bbfaa8106f3c1e"},
    {file = "grpcio-1.62.1-cp310-cp310-macosx_12_0_universal2.whl", hash = "sha256:48611e4fa010e823ba2de8fd3f77c1322dd60cb0d180dc6630a7e157b205f7ea"},
    {file = "grpcio-1.62.1-cp310-cp310-manylinux_2_17_aarch64.whl", hash = "sha256:b2a0e71b0a2158aa4bce48be9f8f9eb45cbd17c78c7443616d00abbe2a509f6d"},
    {file = "grpcio-1.62.1-cp310-cp310-manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:fbe80577c7880911d3ad65e5ecc997416c98f354efeba2f8d0f9112a67ed65a5"},
    {file = "grpcio-1.62.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:58f6c693d446964e3292425e1d16e21a97a48ba9172f2d0df9d7b640acb99243"},
    {file = "grpcio-1.62.1-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:77c339403db5a20ef4fed02e4d1a9a3d9866bf9c0afc77a42234677313ea22f3"},
    {file = "grpcio-1.62.1-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:b5a4ea906db7dec694098435d84bf2854fe158eb3cd51e1107e571246d4d1d70"},
    {file = "grpcio-1.62.1-cp310-cp310-win32.whl", hash = "sha256:4187201a53f8561c015bc745b81a1b2d278967b8de35f3399b84b0695e281d5f"},
    {file = "grpcio-1.62.1-cp310-cp310-win_amd64.whl", hash = "sha256:844d1f3fb11bd1ed362d3fdc495d0770cfab75761836193af166fee113421d66"},
    {file = "grpcio-1.62.1-cp311-cp311-linux_armv7l.whl", hash = "sha256:833379943d1728a005e44103f17ecd73d058d37d95783eb8f0b28ddc1f54d7b2"},
    {file = "grpcio-1.62.1-cp311-cp311-macosx_10_10_universal2.whl", hash = "sha256:c7fcc6a32e7b7b58f5a7d27530669337a5d587d4066060bcb9dee7a8c833dfb7"},
    {file = "grpcio-1.62.1-cp311-cp311-manylinux_2_17_aarch64.whl", hash = "sha256:fa7d28eb4d50b7cbe75bb8b45ed0da9a1dc5b219a0af59449676a29c2eed9698"},
    {file = "grpcio-1.62.1-cp311-cp311-manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:48f7135c3de2f298b833be8b4ae20cafe37091634e91f61f5a7eb3d61ec6f660"},
    {file = "grpcio-1.62.1-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:71f11fd63365ade276c9d4a7b7df5c136f9030e3457107e1791b3737a9b9ed6a"},
    {file = "grpcio-1.62.1-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:4b49fd8fe9f9ac23b78437da94c54aa7e9996fbb220bac024a67469ce5d0825f"},
    {file = "grpcio-1.62.1-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:482ae2ae78679ba9ed5752099b32e5fe580443b4f798e1b71df412abf43375db"},
    {file = "grpcio-1.62.1-cp311-cp311-win32.whl", hash = "sha256:1faa02530b6c7426404372515fe5ddf66e199c2ee613f88f025c6f3bd816450c"},
    {file = "grpcio-1.62.1-cp311-cp311-win_amd64.whl", hash = "sha256:5bd90b8c395f39bc82a5fb32a0173e220e3f401ff697840f4003e15b96d1befc"},
    {file = "grpcio-1.62.1-cp312-cp312-linux_armv7l.whl", hash = "sha256:b134d5d71b4e0837fff574c00e49176051a1c532d26c052a1e43231f252d813b"},
    {file = "grpcio-1.62.1-cp312-cp312-macosx_10_10_universal2.whl", hash = "sha256:d1f6c96573dc09d50dbcbd91dbf71d5cf97640c9427c32584010fbbd4c0e0037"},
    {file = "grpcio-1.62.1-cp312-cp312-manylinux_2_17_aarch64.whl", hash = "sha256:359f821d4578f80f41909b9ee9b76fb249a21035a061a327f91c953493782c31"},
    {file = "grpcio-1.62.1-cp312-cp312-manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:a485f0c2010c696be269184bdb5ae72781344cb4e60db976c59d84dd6354fac9"},
    {file = "grpcio-1.62.1-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:b50b09b4dc01767163d67e1532f948264167cd27f49e9377e3556c3cba1268e1"},
    {file = "grpcio-1.62.1-cp312-cp312-musllinux_1_1_i686.whl", hash = "sha256:3227c667dccbe38f2c4d943238b887bac588d97c104815aecc62d2fd976e014b"},
    {file = "grpcio-1.62.1-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:3952b581eb121324853ce2b191dae08badb75cd493cb4e0243368aa9e61cfd41"},
    {file = "grpcio-1.62.1-cp312-cp312-win32.whl", hash = "sha256:83a17b303425104d6329c10eb34bba186ffa67161e63fa6cdae7776ff76df73f"},
    {file = "grpcio-1.62.1-cp312-cp312-win_amd64.whl", hash = "sha256:6696ffe440333a19d8d128e88d440f91fb92c75a80ce4b44d55800e656a3ef1d"},
    {file = "grpcio-1.62.1-cp37-cp37m-linux_armv7l.whl", hash = "sha256:e3393b0823f938253370ebef033c9fd23d27f3eae8eb9a8f6264900c7ea3fb5a"},
    {file = "grpcio-1.62.1-cp37-cp37m-macosx_10_10_universal2.whl", hash = "sha256:83e7ccb85a74beaeae2634f10eb858a0ed1a63081172649ff4261f929bacfd22"},
    {file = "grpcio-1.62.1-cp37-cp37m-manylinux_2_17_aarch64.whl", hash = "sha256:882020c87999d54667a284c7ddf065b359bd00251fcd70279ac486776dbf84ec"},
    {file = "grpcio-1.62.1-cp37-cp37m-manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:a10383035e864f386fe096fed5c47d27a2bf7173c56a6e26cffaaa5a361addb1"},
    {file = "grpcio-1.62.1-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:960edebedc6b9ada1ef58e1c71156f28689978188cd8cff3b646b57288a927d9"},
    {file = "grpcio-1.62.1-cp37-cp37m-musllinux_1_1_i686.whl", hash = "sha256:23e2e04b83f347d0aadde0c9b616f4726c3d76db04b438fd3904b289a725267f"},
    {file = "grpcio-1.62.1-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:978121758711916d34fe57c1f75b79cdfc73952f1481bb9583399331682d36f7"},
    {file = "grpcio-1.62.1-cp37-cp37m-win_amd64.whl", hash = "sha256:9084086190cc6d628f282e5615f987288b95457292e969b9205e45b442276407"},
    {file = "grpcio-1.62.1-cp38-cp38-linux_armv7l.whl", hash = "sha256:22bccdd7b23c420a27fd28540fb5dcbc97dc6be105f7698cb0e7d7a420d0e362"},
    {file = "grpcio-1.62.1-cp38-cp38-macosx_10_10_universal2.whl", hash = "sha256:8999bf1b57172dbc7c3e4bb3c732658e918f5c333b2942243f10d0d653953ba9"},
    {file = "grpcio-1.62.1-cp38-cp38-manylinux_2_17_aarch64.whl", hash = "sha256:d9e52558b8b8c2f4ac05ac86344a7417ccdd2b460a59616de49eb6933b07a0bd"},
    {file = "grpcio-1.62.1-cp38-cp38-manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:1714e7bc935780bc3de1b3fcbc7674209adf5208ff825799d579ffd6cd0bd505"},
    {file = "grpcio-1.62.1-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:c8842ccbd8c0e253c1f189088228f9b433f7a93b7196b9e5b6f87dba393f5d5d"},
    {file = "grpcio-1.62.1-cp38-cp38-musllinux_1_1_i686.whl", hash = "sha256:1f1e7b36bdff50103af95a80923bf1853f6823dd62f2d2a2524b66ed74103e49"},
    {file = "grpcio-1.62.1-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:bba97b8e8883a8038606480d6b6772289f4c907f6ba780fa1f7b7da7dfd76f06"},
    {file = "grpcio-1.62.1-cp38-cp38-win32.whl", hash = "sha256:a7f615270fe534548112a74e790cd9d4f5509d744dd718cd442bf016626c22e4"},
    {file = "grpcio-1.62.1-cp38-cp38-win_amd64.whl", hash = "sha256:e6c8c8693df718c5ecbc7babb12c69a4e3677fd11de8886f05ab22d4e6b1c43b"},
    {file = "grpcio-1.62.1-cp39-cp39-linux_armv7l.whl", hash = "sha256:73db2dc1b201d20ab7083e7041946910bb991e7e9761a0394bbc3c2632326483"},
    {file = "grpcio-1.62.1-cp39-cp39-macosx_10_10_universal2.whl", hash = "sha256:407b26b7f7bbd4f4751dbc9767a1f0716f9fe72d3d7e96bb3ccfc4aace07c8de"},
    {file = "grpcio-1.62.1-cp39-cp39-manylinux_2_17_aarch64.whl", hash = "sha256:f8de7c8cef9261a2d0a62edf2ccea3d741a523c6b8a6477a340a1f2e417658de"},
    {file = "grpcio-1.62.1-cp39-cp39-manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:9bd5c8a1af40ec305d001c60236308a67e25419003e9bb3ebfab5695a8d0b369"},
    {file = "grpcio-1.62.1-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:be0477cb31da67846a33b1a75c611f88bfbcd427fe17701b6317aefceee1b96f"},
    {file = "grpcio-1.62.1-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:60dcd824df166ba266ee0cfaf35a31406cd16ef602b49f5d4dfb21f014b0dedd"},
    {file = "grpcio-1.62.1-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:973c49086cabab773525f6077f95e5a993bfc03ba8fc32e32f2c279497780585"},
    {file = "grpcio-1.62.1-cp39-cp39-win32.whl", hash = "sha256:12859468e8918d3bd243d213cd6fd6ab07208195dc140763c00dfe901ce1e1b4"},
    {file = "grpcio-1.62.1-cp39-cp39-win_amd64.whl", hash = "sha256:b7209117bbeebdfa5d898205cc55153a51285757902dd73c47de498ad4d11332"},
    {file = "grpcio-1.62.1.tar.gz", hash = "sha256:6c455e008fa86d9e9a9d85bb76da4277c0d7d9668a3bfa70dbe86e9f3c759947"},
]

[package.extras]
protobuf = ["grpcio-tools (>=1.62.1)"]

[[package]]
name = "grpcio-status"
version = "1.62.1"
description = "Status proto mapping for gRPC"
optional = false
python-versions = ">=3.6"
files = [
    {file = "grpcio-status-1.62.1.tar.gz", hash = "sha256:3431c8abbab0054912c41df5c72f03ddf3b7a67be8a287bb3c18a3456f96ff77"},
    {file = "grpcio_status-1.62.1-py3-none-any.whl", hash = "sha256:af0c3ab85da31669f21749e8d53d669c061ebc6ce5637be49a46edcb7aa8ab17"},
]

[package.dependencies]
googleapis-common-protos = ">=1.5.5"
grpcio = ">=1.62.1"
protobuf = ">=4.21.6"

[[package]]
name = "h11"
version = "0.14.0"
description = "A pure-Python, bring-your-own-I/O implementation of HTTP/1.1"
optional = false
python-versions = ">=3.7"
files = [
    {file = "h11-0.14.0-py3-none-any.whl", hash = "sha256:e3fe4ac4b851c468cc8363d500db52c2ead036020723024a109d37346efaa761"},
    {file = "h11-0.14.0.tar.gz", hash = "sha256:8f19fbbe99e72420ff35c00b27a34cb9937e902a8b810e2c88300c6f0a3b699d"},
]

[[package]]
name = "html5lib"
version = "1.1"
description = "HTML parser based on the WHATWG HTML specification"
optional = false
python-versions = ">=2.7, !=3.0.*, !=3.1.*, !=3.2.*, !=3.3.*, !=3.4.*"
files = [
    {file = "html5lib-1.1-py2.py3-none-any.whl", hash = "sha256:0d78f8fde1c230e99fe37986a60526d7049ed4bf8a9fadbad5f00e22e58e041d"},
    {file = "html5lib-1.1.tar.gz", hash = "sha256:b2e5b40261e20f354d198eae92afc10d750afb487ed5e50f9c4eaf07c184146f"},
]

[package.dependencies]
six = ">=1.9"
webencodings = "*"

[package.extras]
all = ["chardet (>=2.2)", "genshi", "lxml"]
chardet = ["chardet (>=2.2)"]
genshi = ["genshi"]
lxml = ["lxml"]

[[package]]
name = "htmldocx"
version = "0.0.6"
description = "Convert html to docx"
optional = false
python-versions = ">=3.6"
files = [
    {file = "htmldocx-0.0.6-py3-none-any.whl", hash = "sha256:adf5e95ad8ba8121e606cf138c614de13327a1192a5782acdb4a0abdc23db1b7"},
    {file = "htmldocx-0.0.6.tar.gz", hash = "sha256:b4bcec895f86d7a50ffc7133ca24d85c24f3614db2b37d33a30d9d04654a5486"},
]

[package.dependencies]
beautifulsoup4 = ">=4.7.0"
python-docx = ">=0.8.10"

[[package]]
name = "httpcore"
version = "1.0.2"
description = "A minimal low-level HTTP client."
optional = false
python-versions = ">=3.8"
files = [
    {file = "httpcore-1.0.2-py3-none-any.whl", hash = "sha256:096cc05bca73b8e459a1fc3dcf585148f63e534eae4339559c9b8a8d6399acc7"},
    {file = "httpcore-1.0.2.tar.gz", hash = "sha256:9fc092e4799b26174648e54b74ed5f683132a464e95643b226e00c2ed2fa6535"},
]

[package.dependencies]
certifi = "*"
h11 = ">=0.13,<0.15"

[package.extras]
asyncio = ["anyio (>=4.0,<5.0)"]
http2 = ["h2 (>=3,<5)"]
socks = ["socksio (==1.*)"]
trio = ["trio (>=0.22.0,<0.23.0)"]

[[package]]
name = "httpx"
version = "0.26.0"
description = "The next generation HTTP client."
optional = false
python-versions = ">=3.8"
files = [
    {file = "httpx-0.26.0-py3-none-any.whl", hash = "sha256:8915f5a3627c4d47b73e8202457cb28f1266982d1159bd5779d86a80c0eab1cd"},
    {file = "httpx-0.26.0.tar.gz", hash = "sha256:451b55c30d5185ea6b23c2c793abf9bb237d2a7dfb901ced6ff69ad37ec1dfaf"},
]

[package.dependencies]
anyio = "*"
certifi = "*"
httpcore = "==1.*"
idna = "*"
sniffio = "*"

[package.extras]
brotli = ["brotli", "brotlicffi"]
cli = ["click (==8.*)", "pygments (==2.*)", "rich (>=10,<14)"]
http2 = ["h2 (>=3,<5)"]
socks = ["socksio (==1.*)"]

[[package]]
name = "idna"
version = "3.6"
description = "Internationalized Domain Names in Applications (IDNA)"
optional = false
python-versions = ">=3.5"
files = [
    {file = "idna-3.6-py3-none-any.whl", hash = "sha256:c05567e9c24a6b9faaa835c4821bad0590fbb9d5779e7caa6e1cc4978e7eb24f"},
    {file = "idna-3.6.tar.gz", hash = "sha256:9ecdbbd083b06798ae1e86adcbfe8ab1479cf864e4ee30fe4e46a003d12491ca"},
]

[[package]]
name = "jieba3k"
version = "0.35.1"
description = "Chinese Words Segementation Utilities"
optional = false
python-versions = "*"
files = [
    {file = "jieba3k-0.35.1.zip", hash = "sha256:980a4f2636b778d312518066be90c7697d410dd5a472385f5afced71a2db1c10"},
]

[[package]]
name = "jinja2"
version = "3.1.2"
description = "A very fast and expressive template engine."
optional = false
python-versions = ">=3.7"
files = [
    {file = "Jinja2-3.1.2-py3-none-any.whl", hash = "sha256:6088930bfe239f0e6710546ab9c19c9ef35e29792895fed6e6e31a023a182a61"},
    {file = "Jinja2-3.1.2.tar.gz", hash = "sha256:31351a702a408a9e7595a8fc6150fc3f43bb6bf7e319770cbc0db9df9437e852"},
]

[package.dependencies]
MarkupSafe = ">=2.0"

[package.extras]
i18n = ["Babel (>=2.7)"]

[[package]]
name = "joblib"
version = "1.3.2"
description = "Lightweight pipelining with Python functions"
optional = false
python-versions = ">=3.7"
files = [
    {file = "joblib-1.3.2-py3-none-any.whl", hash = "sha256:ef4331c65f239985f3f2220ecc87db222f08fd22097a3dd5698f693875f8cbb9"},
    {file = "joblib-1.3.2.tar.gz", hash = "sha256:92f865e621e17784e7955080b6d042489e3b8e294949cc44c6eac304f59772b1"},
]

[[package]]
name = "jsonpatch"
version = "1.33"
description = "Apply JSON-Patches (RFC 6902)"
optional = false
python-versions = ">=2.7, !=3.0.*, !=3.1.*, !=3.2.*, !=3.3.*, !=3.4.*, !=3.5.*, !=3.6.*"
files = [
    {file = "jsonpatch-1.33-py2.py3-none-any.whl", hash = "sha256:0ae28c0cd062bbd8b8ecc26d7d164fbbea9652a1a3693f3b956c1eae5145dade"},
    {file = "jsonpatch-1.33.tar.gz", hash = "sha256:9fcd4009c41e6d12348b4a0ff2563ba56a2923a7dfee731d004e212e1ee5030c"},
]

[package.dependencies]
jsonpointer = ">=1.9"

[[package]]
name = "jsonpointer"
version = "2.4"
description = "Identify specific nodes in a JSON document (RFC 6901)"
optional = false
python-versions = ">=2.7, !=3.0.*, !=3.1.*, !=3.2.*, !=3.3.*, !=3.4.*, !=3.5.*, !=3.6.*"
files = [
    {file = "jsonpointer-2.4-py2.py3-none-any.whl", hash = "sha256:15d51bba20eea3165644553647711d150376234112651b4f1811022aecad7d7a"},
    {file = "jsonpointer-2.4.tar.gz", hash = "sha256:585cee82b70211fa9e6043b7bb89db6e1aa49524340dde8ad6b63206ea689d88"},
]

[[package]]
name = "langchain"
version = "0.1.13"
description = "Building applications with LLMs through composability"
optional = false
python-versions = "<4.0,>=3.8.1"
files = [
    {file = "langchain-0.1.13-py3-none-any.whl", hash = "sha256:c87657021b777d6b07e55be379a28660a1cd148c31593569869dd6b0b4cab945"},
    {file = "langchain-0.1.13.tar.gz", hash = "sha256:db330aa79c33501cb1ed97ff465f7645813eaa6cfd742c61e19c2d48e4aaba18"},
]

[package.dependencies]
aiohttp = ">=3.8.3,<4.0.0"
async-timeout = {version = ">=4.0.0,<5.0.0", markers = "python_version < \"3.11\""}
dataclasses-json = ">=0.5.7,<0.7"
jsonpatch = ">=1.33,<2.0"
langchain-community = ">=0.0.29,<0.1"
langchain-core = ">=0.1.33,<0.2.0"
langchain-text-splitters = ">=0.0.1,<0.1"
langsmith = ">=0.1.17,<0.2.0"
numpy = ">=1,<2"
pydantic = ">=1,<3"
PyYAML = ">=5.3"
requests = ">=2,<3"
SQLAlchemy = ">=1.4,<3"
tenacity = ">=8.1.0,<9.0.0"

[package.extras]
azure = ["azure-ai-formrecognizer (>=3.2.1,<4.0.0)", "azure-ai-textanalytics (>=5.3.0,<6.0.0)", "azure-cognitiveservices-speech (>=1.28.0,<2.0.0)", "azure-core (>=1.26.4,<2.0.0)", "azure-cosmos (>=4.4.0b1,<5.0.0)", "azure-identity (>=1.12.0,<2.0.0)", "azure-search-documents (==11.4.0b8)", "openai (<2)"]
clarifai = ["clarifai (>=9.1.0)"]
cli = ["typer (>=0.9.0,<0.10.0)"]
cohere = ["cohere (>=4,<5)"]
docarray = ["docarray[hnswlib] (>=0.32.0,<0.33.0)"]
embeddings = ["sentence-transformers (>=2,<3)"]
extended-testing = ["aiosqlite (>=0.19.0,<0.20.0)", "aleph-alpha-client (>=2.15.0,<3.0.0)", "anthropic (>=0.3.11,<0.4.0)", "arxiv (>=1.4,<2.0)", "assemblyai (>=0.17.0,<0.18.0)", "atlassian-python-api (>=3.36.0,<4.0.0)", "beautifulsoup4 (>=4,<5)", "bibtexparser (>=1.4.0,<2.0.0)", "cassio (>=0.1.0,<0.2.0)", "chardet (>=5.1.0,<6.0.0)", "cohere (>=4,<5)", "couchbase (>=4.1.9,<5.0.0)", "dashvector (>=1.0.1,<2.0.0)", "databricks-vectorsearch (>=0.21,<0.22)", "datasets (>=2.15.0,<3.0.0)", "dgml-utils (>=0.3.0,<0.4.0)", "esprima (>=4.0.1,<5.0.0)", "faiss-cpu (>=1,<2)", "feedparser (>=6.0.10,<7.0.0)", "fireworks-ai (>=0.9.0,<0.10.0)", "geopandas (>=0.13.1,<0.14.0)", "gitpython (>=3.1.32,<4.0.0)", "google-cloud-documentai (>=2.20.1,<3.0.0)", "gql (>=3.4.1,<4.0.0)", "hologres-vector (>=0.0.6,<0.0.7)", "html2text (>=2020.1.16,<2021.0.0)", "javelin-sdk (>=0.1.8,<0.2.0)", "jinja2 (>=3,<4)", "jq (>=1.4.1,<2.0.0)", "jsonschema (>1)", "langchain-openai (>=0.0.2,<0.1)", "lxml (>=4.9.2,<5.0.0)", "markdownify (>=0.11.6,<0.12.0)", "motor (>=3.3.1,<4.0.0)", "msal (>=1.25.0,<2.0.0)", "mwparserfromhell (>=0.6.4,<0.7.0)", "mwxml (>=0.3.3,<0.4.0)", "newspaper3k (>=0.2.8,<0.3.0)", "numexpr (>=2.8.6,<3.0.0)", "openai (<2)", "openapi-pydantic (>=0.3.2,<0.4.0)", "pandas (>=2.0.1,<3.0.0)", "pdfminer-six (>=20221105,<20221106)", "pgvector (>=0.1.6,<0.2.0)", "praw (>=7.7.1,<8.0.0)", "psychicapi (>=0.8.0,<0.9.0)", "py-trello (>=0.19.0,<0.20.0)", "pymupdf (>=1.22.3,<2.0.0)", "pypdf (>=3.4.0,<4.0.0)", "pypdfium2 (>=4.10.0,<5.0.0)", "pyspark (>=3.4.0,<4.0.0)", "rank-bm25 (>=0.2.2,<0.3.0)", "rapidfuzz (>=3.1.1,<4.0.0)", "rapidocr-onnxruntime (>=1.3.2,<2.0.0)", "rdflib (==7.0.0)", "requests-toolbelt (>=1.0.0,<2.0.0)", "rspace_client (>=2.5.0,<3.0.0)", "scikit-learn (>=1.2.2,<2.0.0)", "sqlite-vss (>=0.1.2,<0.2.0)", "streamlit (>=1.18.0,<2.0.0)", "sympy (>=1.12,<2.0)", "telethon (>=1.28.5,<2.0.0)", "timescale-vector (>=0.0.1,<0.0.2)", "tqdm (>=4.48.0)", "upstash-redis (>=0.15.0,<0.16.0)", "xata (>=1.0.0a7,<2.0.0)", "xmltodict (>=0.13.0,<0.14.0)"]
javascript = ["esprima (>=4.0.1,<5.0.0)"]
llms = ["clarifai (>=9.1.0)", "cohere (>=4,<5)", "huggingface_hub (>=0,<1)", "manifest-ml (>=0.0.1,<0.0.2)", "nlpcloud (>=1,<2)", "openai (<2)", "openlm (>=0.0.5,<0.0.6)", "torch (>=1,<3)", "transformers (>=4,<5)"]
openai = ["openai (<2)", "tiktoken (>=0.3.2,<0.6.0)"]
qdrant = ["qdrant-client (>=1.3.1,<2.0.0)"]
text-helpers = ["chardet (>=5.1.0,<6.0.0)"]

[[package]]
name = "langchain-community"
version = "0.0.29"
description = "Community contributed LangChain integrations."
optional = false
python-versions = "<4.0,>=3.8.1"
files = [
    {file = "langchain_community-0.0.29-py3-none-any.whl", hash = "sha256:1652dddf257089b7b5066974b636262b4a5b680339f4539be133b14ae351e67d"},
    {file = "langchain_community-0.0.29.tar.gz", hash = "sha256:d88107fafa9fe2c5733da9630c68d9ee51cd33b1c88a4950e7a2d9a38f7e7aa3"},
]

[package.dependencies]
aiohttp = ">=3.8.3,<4.0.0"
dataclasses-json = ">=0.5.7,<0.7"
langchain-core = ">=0.1.33,<0.2.0"
langsmith = ">=0.1.0,<0.2.0"
numpy = ">=1,<2"
PyYAML = ">=5.3"
requests = ">=2,<3"
SQLAlchemy = ">=1.4,<3"
tenacity = ">=8.1.0,<9.0.0"

[package.extras]
cli = ["typer (>=0.9.0,<0.10.0)"]
extended-testing = ["aiosqlite (>=0.19.0,<0.20.0)", "aleph-alpha-client (>=2.15.0,<3.0.0)", "anthropic (>=0.3.11,<0.4.0)", "arxiv (>=1.4,<2.0)", "assemblyai (>=0.17.0,<0.18.0)", "atlassian-python-api (>=3.36.0,<4.0.0)", "azure-ai-documentintelligence (>=1.0.0b1,<2.0.0)", "beautifulsoup4 (>=4,<5)", "bibtexparser (>=1.4.0,<2.0.0)", "cassio (>=0.1.0,<0.2.0)", "chardet (>=5.1.0,<6.0.0)", "cloudpickle (>=2.0.0)", "cohere (>=4,<5)", "databricks-vectorsearch (>=0.21,<0.22)", "datasets (>=2.15.0,<3.0.0)", "dgml-utils (>=0.3.0,<0.4.0)", "elasticsearch (>=8.12.0,<9.0.0)", "esprima (>=4.0.1,<5.0.0)", "faiss-cpu (>=1,<2)", "feedparser (>=6.0.10,<7.0.0)", "fireworks-ai (>=0.9.0,<0.10.0)", "friendli-client (>=1.2.4,<2.0.0)", "geopandas (>=0.13.1,<0.14.0)", "gitpython (>=3.1.32,<4.0.0)", "google-cloud-documentai (>=2.20.1,<3.0.0)", "gql (>=3.4.1,<4.0.0)", "gradientai (>=1.4.0,<2.0.0)", "hdbcli (>=2.19.21,<3.0.0)", "hologres-vector (>=0.0.6,<0.0.7)", "html2text (>=2020.1.16,<2021.0.0)", "httpx (>=0.24.1,<0.25.0)", "javelin-sdk (>=0.1.8,<0.2.0)", "jinja2 (>=3,<4)", "jq (>=1.4.1,<2.0.0)", "jsonschema (>1)", "lxml (>=4.9.2,<5.0.0)", "markdownify (>=0.11.6,<0.12.0)", "motor (>=3.3.1,<4.0.0)", "msal (>=1.25.0,<2.0.0)", "mwparserfromhell (>=0.6.4,<0.7.0)", "mwxml (>=0.3.3,<0.4.0)", "newspaper3k (>=0.2.8,<0.3.0)", "numexpr (>=2.8.6,<3.0.0)", "nvidia-riva-client (>=2.14.0,<3.0.0)", "oci (>=2.119.1,<3.0.0)", "openai (<2)", "openapi-pydantic (>=0.3.2,<0.4.0)", "oracle-ads (>=2.9.1,<3.0.0)", "pandas (>=2.0.1,<3.0.0)", "pdfminer-six (>=20221105,<20221106)", "pgvector (>=0.1.6,<0.2.0)", "praw (>=7.7.1,<8.0.0)", "psychicapi (>=0.8.0,<0.9.0)", "py-trello (>=0.19.0,<0.20.0)", "pymupdf (>=1.22.3,<2.0.0)", "pypdf (>=3.4.0,<4.0.0)", "pypdfium2 (>=4.10.0,<5.0.0)", "pyspark (>=3.4.0,<4.0.0)", "rank-bm25 (>=0.2.2,<0.3.0)", "rapidfuzz (>=3.1.1,<4.0.0)", "rapidocr-onnxruntime (>=1.3.2,<2.0.0)", "rdflib (==7.0.0)", "requests-toolbelt (>=1.0.0,<2.0.0)", "rspace_client (>=2.5.0,<3.0.0)", "scikit-learn (>=1.2.2,<2.0.0)", "sqlite-vss (>=0.1.2,<0.2.0)", "streamlit (>=1.18.0,<2.0.0)", "sympy (>=1.12,<2.0)", "telethon (>=1.28.5,<2.0.0)", "tidb-vector (>=0.0.3,<1.0.0)", "timescale-vector (>=0.0.1,<0.0.2)", "tqdm (>=4.48.0)", "tree-sitter (>=0.20.2,<0.21.0)", "tree-sitter-languages (>=1.8.0,<2.0.0)", "upstash-redis (>=0.15.0,<0.16.0)", "xata (>=1.0.0a7,<2.0.0)", "xmltodict (>=0.13.0,<0.14.0)", "zhipuai (>=1.0.7,<2.0.0)"]

[[package]]
name = "langchain-core"
version = "0.1.33"
description = "Building applications with LLMs through composability"
optional = false
python-versions = "<4.0,>=3.8.1"
files = [
    {file = "langchain_core-0.1.33-py3-none-any.whl", hash = "sha256:cee7fbab114c74b7279a92c8a376b40344b0fa3d0f0af3143a858e3b7485bf13"},
    {file = "langchain_core-0.1.33.tar.gz", hash = "sha256:545eff3de83cc58231bd2b0c6d672323fc2077b94d326ba1a3219118af1d1a66"},
]

[package.dependencies]
anyio = ">=3,<5"
jsonpatch = ">=1.33,<2.0"
langsmith = ">=0.1.0,<0.2.0"
packaging = ">=23.2,<24.0"
pydantic = ">=1,<3"
PyYAML = ">=5.3"
requests = ">=2,<3"
tenacity = ">=8.1.0,<9.0.0"

[package.extras]
extended-testing = ["jinja2 (>=3,<4)"]

[[package]]
name = "langchain-google-genai"
version = "0.0.11"
description = "An integration package connecting Google's genai package and LangChain"
optional = false
python-versions = ">=3.9,<4.0"
files = [
    {file = "langchain_google_genai-0.0.11-py3-none-any.whl", hash = "sha256:7e42900bf6850f58a6f9088d885f450ca9a2653c17cee5c19f3599ac17a285bd"},
    {file = "langchain_google_genai-0.0.11.tar.gz", hash = "sha256:378b080e90d7ea1d6164b65847c5b1053346bb0781e629de9c2a3e4bb725317a"},
]

[package.dependencies]
google-generativeai = ">=0.4.1,<0.5.0"
langchain-core = ">=0.1,<0.2"

[package.extras]
images = ["pillow (>=10.1.0,<11.0.0)"]

[[package]]
name = "langchain-openai"
version = "0.1.0"
description = "An integration package connecting OpenAI and LangChain"
optional = false
python-versions = "<4.0,>=3.8.1"
files = [
    {file = "langchain_openai-0.1.0-py3-none-any.whl", hash = "sha256:3cb3da679da9bc33c20634a5a64e65e1f1d9f69a8b71e8622297d8c33623e8d6"},
    {file = "langchain_openai-0.1.0.tar.gz", hash = "sha256:96bb825be484a19cd0586725856bd159e3ed47d31ad95c6d160852abcb938ae2"},
]

[package.dependencies]
langchain-core = ">=0.1.33,<0.2.0"
openai = ">=1.10.0,<2.0.0"
tiktoken = ">=0.5.2,<1"

[[package]]
name = "langchain-text-splitters"
version = "0.0.1"
description = "LangChain text splitting utilities"
optional = false
python-versions = ">=3.8.1,<4.0"
files = [
    {file = "langchain_text_splitters-0.0.1-py3-none-any.whl", hash = "sha256:f5b802f873f5ff6a8b9259ff34d53ed989666ef4e1582e6d1adb3b5520e3839a"},
    {file = "langchain_text_splitters-0.0.1.tar.gz", hash = "sha256:ac459fa98799f5117ad5425a9330b21961321e30bc19a2a2f9f761ddadd62aa1"},
]

[package.dependencies]
langchain-core = ">=0.1.28,<0.2.0"

[package.extras]
extended-testing = ["lxml (>=5.1.0,<6.0.0)"]

[[package]]
name = "langsmith"
version = "0.1.31"
description = "Client library to connect to the LangSmith LLM Tracing and Evaluation Platform."
optional = false
python-versions = "<4.0,>=3.8.1"
files = [
    {file = "langsmith-0.1.31-py3-none-any.whl", hash = "sha256:5211a9dc00831db307eb843485a97096484b697b5d2cd1efaac34228e97ca087"},
    {file = "langsmith-0.1.31.tar.gz", hash = "sha256:efd54ccd44be7fda911bfdc0ead340473df2fdd07345c7252901834d0c4aa37e"},
]

[package.dependencies]
orjson = ">=3.9.14,<4.0.0"
pydantic = ">=1,<3"
requests = ">=2,<3"

[[package]]
name = "lxml"
version = "4.9.4"
description = "Powerful and Pythonic XML processing library combining libxml2/libxslt with the ElementTree API."
optional = false
python-versions = ">=2.7, !=3.0.*, !=3.1.*, !=3.2.*, !=3.3.*, != 3.4.*"
files = [
    {file = "lxml-4.9.4-cp27-cp27m-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:e214025e23db238805a600f1f37bf9f9a15413c7bf5f9d6ae194f84980c78722"},
    {file = "lxml-4.9.4-cp27-cp27m-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:ec53a09aee61d45e7dbe7e91252ff0491b6b5fee3d85b2d45b173d8ab453efc1"},
    {file = "lxml-4.9.4-cp27-cp27m-win32.whl", hash = "sha256:7d1d6c9e74c70ddf524e3c09d9dc0522aba9370708c2cb58680ea40174800013"},
    {file = "lxml-4.9.4-cp27-cp27m-win_amd64.whl", hash = "sha256:cb53669442895763e61df5c995f0e8361b61662f26c1b04ee82899c2789c8f69"},
    {file = "lxml-4.9.4-cp27-cp27mu-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:647bfe88b1997d7ae8d45dabc7c868d8cb0c8412a6e730a7651050b8c7289cf2"},
    {file = "lxml-4.9.4-cp27-cp27mu-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:4d973729ce04784906a19108054e1fd476bc85279a403ea1a72fdb051c76fa48"},
    {file = "lxml-4.9.4-cp310-cp310-macosx_11_0_x86_64.whl", hash = "sha256:056a17eaaf3da87a05523472ae84246f87ac2f29a53306466c22e60282e54ff8"},
    {file = "lxml-4.9.4-cp310-cp310-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_24_i686.whl", hash = "sha256:aaa5c173a26960fe67daa69aa93d6d6a1cd714a6eb13802d4e4bd1d24a530644"},
    {file = "lxml-4.9.4-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.manylinux_2_24_aarch64.whl", hash = "sha256:647459b23594f370c1c01768edaa0ba0959afc39caeeb793b43158bb9bb6a663"},
    {file = "lxml-4.9.4-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.manylinux_2_24_x86_64.whl", hash = "sha256:bdd9abccd0927673cffe601d2c6cdad1c9321bf3437a2f507d6b037ef91ea307"},
    {file = "lxml-4.9.4-cp310-cp310-manylinux_2_28_x86_64.whl", hash = "sha256:00e91573183ad273e242db5585b52670eddf92bacad095ce25c1e682da14ed91"},
    {file = "lxml-4.9.4-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:a602ed9bd2c7d85bd58592c28e101bd9ff9c718fbde06545a70945ffd5d11868"},
    {file = "lxml-4.9.4-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:de362ac8bc962408ad8fae28f3967ce1a262b5d63ab8cefb42662566737f1dc7"},
    {file = "lxml-4.9.4-cp310-cp310-win32.whl", hash = "sha256:33714fcf5af4ff7e70a49731a7cc8fd9ce910b9ac194f66eaa18c3cc0a4c02be"},
    {file = "lxml-4.9.4-cp310-cp310-win_amd64.whl", hash = "sha256:d3caa09e613ece43ac292fbed513a4bce170681a447d25ffcbc1b647d45a39c5"},
    {file = "lxml-4.9.4-cp311-cp311-macosx_11_0_universal2.whl", hash = "sha256:359a8b09d712df27849e0bcb62c6a3404e780b274b0b7e4c39a88826d1926c28"},
    {file = "lxml-4.9.4-cp311-cp311-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_24_i686.whl", hash = "sha256:43498ea734ccdfb92e1886dfedaebeb81178a241d39a79d5351ba2b671bff2b2"},
    {file = "lxml-4.9.4-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.manylinux_2_24_aarch64.whl", hash = "sha256:4855161013dfb2b762e02b3f4d4a21cc7c6aec13c69e3bffbf5022b3e708dd97"},
    {file = "lxml-4.9.4-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.manylinux_2_24_x86_64.whl", hash = "sha256:c71b5b860c5215fdbaa56f715bc218e45a98477f816b46cfde4a84d25b13274e"},
    {file = "lxml-4.9.4-cp311-cp311-manylinux_2_28_aarch64.whl", hash = "sha256:9a2b5915c333e4364367140443b59f09feae42184459b913f0f41b9fed55794a"},
    {file = "lxml-4.9.4-cp311-cp311-manylinux_2_28_x86_64.whl", hash = "sha256:d82411dbf4d3127b6cde7da0f9373e37ad3a43e89ef374965465928f01c2b979"},
    {file = "lxml-4.9.4-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:273473d34462ae6e97c0f4e517bd1bf9588aa67a1d47d93f760a1282640e24ac"},
    {file = "lxml-4.9.4-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:389d2b2e543b27962990ab529ac6720c3dded588cc6d0f6557eec153305a3622"},
    {file = "lxml-4.9.4-cp311-cp311-win32.whl", hash = "sha256:8aecb5a7f6f7f8fe9cac0bcadd39efaca8bbf8d1bf242e9f175cbe4c925116c3"},
    {file = "lxml-4.9.4-cp311-cp311-win_amd64.whl", hash = "sha256:c7721a3ef41591341388bb2265395ce522aba52f969d33dacd822da8f018aff8"},
    {file = "lxml-4.9.4-cp312-cp312-macosx_11_0_universal2.whl", hash = "sha256:dbcb2dc07308453db428a95a4d03259bd8caea97d7f0776842299f2d00c72fc8"},
    {file = "lxml-4.9.4-cp312-cp312-manylinux_2_28_aarch64.whl", hash = "sha256:01bf1df1db327e748dcb152d17389cf6d0a8c5d533ef9bab781e9d5037619229"},
    {file = "lxml-4.9.4-cp312-cp312-manylinux_2_28_x86_64.whl", hash = "sha256:e8f9f93a23634cfafbad6e46ad7d09e0f4a25a2400e4a64b1b7b7c0fbaa06d9d"},
    {file = "lxml-4.9.4-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:3f3f00a9061605725df1816f5713d10cd94636347ed651abdbc75828df302b20"},
    {file = "lxml-4.9.4-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:953dd5481bd6252bd480d6ec431f61d7d87fdcbbb71b0d2bdcfc6ae00bb6fb10"},
    {file = "lxml-4.9.4-cp312-cp312-win32.whl", hash = "sha256:266f655d1baff9c47b52f529b5f6bec33f66042f65f7c56adde3fcf2ed62ae8b"},
    {file = "lxml-4.9.4-cp312-cp312-win_amd64.whl", hash = "sha256:f1faee2a831fe249e1bae9cbc68d3cd8a30f7e37851deee4d7962b17c410dd56"},
    {file = "lxml-4.9.4-cp35-cp35m-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:23d891e5bdc12e2e506e7d225d6aa929e0a0368c9916c1fddefab88166e98b20"},
    {file = "lxml-4.9.4-cp35-cp35m-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:e96a1788f24d03e8d61679f9881a883ecdf9c445a38f9ae3f3f193ab6c591c66"},
    {file = "lxml-4.9.4-cp36-cp36m-macosx_11_0_x86_64.whl", hash = "sha256:5557461f83bb7cc718bc9ee1f7156d50e31747e5b38d79cf40f79ab1447afd2d"},
    {file = "lxml-4.9.4-cp36-cp36m-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_24_i686.whl", hash = "sha256:fdb325b7fba1e2c40b9b1db407f85642e32404131c08480dd652110fc908561b"},
    {file = "lxml-4.9.4-cp36-cp36m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:3d74d4a3c4b8f7a1f676cedf8e84bcc57705a6d7925e6daef7a1e54ae543a197"},
    {file = "lxml-4.9.4-cp36-cp36m-manylinux_2_17_x86_64.manylinux2014_x86_64.manylinux_2_24_x86_64.whl", hash = "sha256:ac7674d1638df129d9cb4503d20ffc3922bd463c865ef3cb412f2c926108e9a4"},
    {file = "lxml-4.9.4-cp36-cp36m-manylinux_2_28_x86_64.whl", hash = "sha256:ddd92e18b783aeb86ad2132d84a4b795fc5ec612e3545c1b687e7747e66e2b53"},
    {file = "lxml-4.9.4-cp36-cp36m-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:2bd9ac6e44f2db368ef8986f3989a4cad3de4cd55dbdda536e253000c801bcc7"},
    {file = "lxml-4.9.4-cp36-cp36m-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:bc354b1393dce46026ab13075f77b30e40b61b1a53e852e99d3cc5dd1af4bc85"},
    {file = "lxml-4.9.4-cp36-cp36m-musllinux_1_1_aarch64.whl", hash = "sha256:f836f39678cb47c9541f04d8ed4545719dc31ad850bf1832d6b4171e30d65d23"},
    {file = "lxml-4.9.4-cp36-cp36m-musllinux_1_1_x86_64.whl", hash = "sha256:9c131447768ed7bc05a02553d939e7f0e807e533441901dd504e217b76307745"},
    {file = "lxml-4.9.4-cp36-cp36m-win32.whl", hash = "sha256:bafa65e3acae612a7799ada439bd202403414ebe23f52e5b17f6ffc2eb98c2be"},
    {file = "lxml-4.9.4-cp36-cp36m-win_amd64.whl", hash = "sha256:6197c3f3c0b960ad033b9b7d611db11285bb461fc6b802c1dd50d04ad715c225"},
    {file = "lxml-4.9.4-cp37-cp37m-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_24_i686.whl", hash = "sha256:7b378847a09d6bd46047f5f3599cdc64fcb4cc5a5a2dd0a2af610361fbe77b16"},
    {file = "lxml-4.9.4-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.manylinux_2_24_aarch64.whl", hash = "sha256:1343df4e2e6e51182aad12162b23b0a4b3fd77f17527a78c53f0f23573663545"},
    {file = "lxml-4.9.4-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.manylinux_2_24_x86_64.whl", hash = "sha256:6dbdacf5752fbd78ccdb434698230c4f0f95df7dd956d5f205b5ed6911a1367c"},
    {file = "lxml-4.9.4-cp37-cp37m-manylinux_2_28_x86_64.whl", hash = "sha256:506becdf2ecaebaf7f7995f776394fcc8bd8a78022772de66677c84fb02dd33d"},
    {file = "lxml-4.9.4-cp37-cp37m-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:ca8e44b5ba3edb682ea4e6185b49661fc22b230cf811b9c13963c9f982d1d964"},
    {file = "lxml-4.9.4-cp37-cp37m-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:9d9d5726474cbbef279fd709008f91a49c4f758bec9c062dfbba88eab00e3ff9"},
    {file = "lxml-4.9.4-cp37-cp37m-musllinux_1_1_aarch64.whl", hash = "sha256:bbdd69e20fe2943b51e2841fc1e6a3c1de460d630f65bde12452d8c97209464d"},
    {file = "lxml-4.9.4-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:8671622256a0859f5089cbe0ce4693c2af407bc053dcc99aadff7f5310b4aa02"},
    {file = "lxml-4.9.4-cp37-cp37m-win32.whl", hash = "sha256:dd4fda67f5faaef4f9ee5383435048ee3e11ad996901225ad7615bc92245bc8e"},
    {file = "lxml-4.9.4-cp37-cp37m-win_amd64.whl", hash = "sha256:6bee9c2e501d835f91460b2c904bc359f8433e96799f5c2ff20feebd9bb1e590"},
    {file = "lxml-4.9.4-cp38-cp38-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_24_i686.whl", hash = "sha256:1f10f250430a4caf84115b1e0f23f3615566ca2369d1962f82bef40dd99cd81a"},
    {file = "lxml-4.9.4-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.manylinux_2_24_aarch64.whl", hash = "sha256:3b505f2bbff50d261176e67be24e8909e54b5d9d08b12d4946344066d66b3e43"},
    {file = "lxml-4.9.4-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.manylinux_2_24_x86_64.whl", hash = "sha256:1449f9451cd53e0fd0a7ec2ff5ede4686add13ac7a7bfa6988ff6d75cff3ebe2"},
    {file = "lxml-4.9.4-cp38-cp38-manylinux_2_28_x86_64.whl", hash = "sha256:4ece9cca4cd1c8ba889bfa67eae7f21d0d1a2e715b4d5045395113361e8c533d"},
    {file = "lxml-4.9.4-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:59bb5979f9941c61e907ee571732219fa4774d5a18f3fa5ff2df963f5dfaa6bc"},
    {file = "lxml-4.9.4-cp38-cp38-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:b1980dbcaad634fe78e710c8587383e6e3f61dbe146bcbfd13a9c8ab2d7b1192"},
    {file = "lxml-4.9.4-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:9ae6c3363261021144121427b1552b29e7b59de9d6a75bf51e03bc072efb3c37"},
    {file = "lxml-4.9.4-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:bcee502c649fa6351b44bb014b98c09cb00982a475a1912a9881ca28ab4f9cd9"},
    {file = "lxml-4.9.4-cp38-cp38-win32.whl", hash = "sha256:a8edae5253efa75c2fc79a90068fe540b197d1c7ab5803b800fccfe240eed33c"},
    {file = "lxml-4.9.4-cp38-cp38-win_amd64.whl", hash = "sha256:701847a7aaefef121c5c0d855b2affa5f9bd45196ef00266724a80e439220e46"},
    {file = "lxml-4.9.4-cp39-cp39-macosx_11_0_x86_64.whl", hash = "sha256:f610d980e3fccf4394ab3806de6065682982f3d27c12d4ce3ee46a8183d64a6a"},
    {file = "lxml-4.9.4-cp39-cp39-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_24_i686.whl", hash = "sha256:aa9b5abd07f71b081a33115d9758ef6077924082055005808f68feccb27616bd"},
    {file = "lxml-4.9.4-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.manylinux_2_24_aarch64.whl", hash = "sha256:365005e8b0718ea6d64b374423e870648ab47c3a905356ab6e5a5ff03962b9a9"},
    {file = "lxml-4.9.4-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.manylinux_2_24_x86_64.whl", hash = "sha256:16b9ec51cc2feab009e800f2c6327338d6ee4e752c76e95a35c4465e80390ccd"},
    {file = "lxml-4.9.4-cp39-cp39-manylinux_2_28_x86_64.whl", hash = "sha256:a905affe76f1802edcac554e3ccf68188bea16546071d7583fb1b693f9cf756b"},
    {file = "lxml-4.9.4-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:fd814847901df6e8de13ce69b84c31fc9b3fb591224d6762d0b256d510cbf382"},
    {file = "lxml-4.9.4-cp39-cp39-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:91bbf398ac8bb7d65a5a52127407c05f75a18d7015a270fdd94bbcb04e65d573"},
    {file = "lxml-4.9.4-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:f99768232f036b4776ce419d3244a04fe83784bce871b16d2c2e984c7fcea847"},
    {file = "lxml-4.9.4-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:bb5bd6212eb0edfd1e8f254585290ea1dadc3687dd8fd5e2fd9a87c31915cdab"},
    {file = "lxml-4.9.4-cp39-cp39-win32.whl", hash = "sha256:88f7c383071981c74ec1998ba9b437659e4fd02a3c4a4d3efc16774eb108d0ec"},
    {file = "lxml-4.9.4-cp39-cp39-win_amd64.whl", hash = "sha256:936e8880cc00f839aa4173f94466a8406a96ddce814651075f95837316369899"},
    {file = "lxml-4.9.4-pp310-pypy310_pp73-macosx_11_0_x86_64.whl", hash = "sha256:f6c35b2f87c004270fa2e703b872fcc984d714d430b305145c39d53074e1ffe0"},
    {file = "lxml-4.9.4-pp310-pypy310_pp73-manylinux_2_28_x86_64.whl", hash = "sha256:606d445feeb0856c2b424405236a01c71af7c97e5fe42fbc778634faef2b47e4"},
    {file = "lxml-4.9.4-pp310-pypy310_pp73-win_amd64.whl", hash = "sha256:a1bdcbebd4e13446a14de4dd1825f1e778e099f17f79718b4aeaf2403624b0f7"},
    {file = "lxml-4.9.4-pp37-pypy37_pp73-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_24_i686.whl", hash = "sha256:0a08c89b23117049ba171bf51d2f9c5f3abf507d65d016d6e0fa2f37e18c0fc5"},
    {file = "lxml-4.9.4-pp37-pypy37_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.manylinux_2_24_x86_64.whl", hash = "sha256:232fd30903d3123be4c435fb5159938c6225ee8607b635a4d3fca847003134ba"},
    {file = "lxml-4.9.4-pp37-pypy37_pp73-manylinux_2_28_x86_64.whl", hash = "sha256:231142459d32779b209aa4b4d460b175cadd604fed856f25c1571a9d78114771"},
    {file = "lxml-4.9.4-pp38-pypy38_pp73-macosx_11_0_x86_64.whl", hash = "sha256:520486f27f1d4ce9654154b4494cf9307b495527f3a2908ad4cb48e4f7ed7ef7"},
    {file = "lxml-4.9.4-pp38-pypy38_pp73-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_24_i686.whl", hash = "sha256:562778586949be7e0d7435fcb24aca4810913771f845d99145a6cee64d5b67ca"},
    {file = "lxml-4.9.4-pp38-pypy38_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.manylinux_2_24_x86_64.whl", hash = "sha256:a9e7c6d89c77bb2770c9491d988f26a4b161d05c8ca58f63fb1f1b6b9a74be45"},
    {file = "lxml-4.9.4-pp38-pypy38_pp73-manylinux_2_28_x86_64.whl", hash = "sha256:786d6b57026e7e04d184313c1359ac3d68002c33e4b1042ca58c362f1d09ff58"},
    {file = "lxml-4.9.4-pp38-pypy38_pp73-win_amd64.whl", hash = "sha256:95ae6c5a196e2f239150aa4a479967351df7f44800c93e5a975ec726fef005e2"},
    {file = "lxml-4.9.4-pp39-pypy39_pp73-macosx_11_0_x86_64.whl", hash = "sha256:9b556596c49fa1232b0fff4b0e69b9d4083a502e60e404b44341e2f8fb7187f5"},
    {file = "lxml-4.9.4-pp39-pypy39_pp73-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_24_i686.whl", hash = "sha256:cc02c06e9e320869d7d1bd323df6dd4281e78ac2e7f8526835d3d48c69060683"},
    {file = "lxml-4.9.4-pp39-pypy39_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.manylinux_2_24_x86_64.whl", hash = "sha256:857d6565f9aa3464764c2cb6a2e3c2e75e1970e877c188f4aeae45954a314e0c"},
    {file = "lxml-4.9.4-pp39-pypy39_pp73-manylinux_2_28_x86_64.whl", hash = "sha256:c42ae7e010d7d6bc51875d768110c10e8a59494855c3d4c348b068f5fb81fdcd"},
    {file = "lxml-4.9.4-pp39-pypy39_pp73-win_amd64.whl", hash = "sha256:f10250bb190fb0742e3e1958dd5c100524c2cc5096c67c8da51233f7448dc137"},
    {file = "lxml-4.9.4.tar.gz", hash = "sha256:b1541e50b78e15fa06a2670157a1962ef06591d4c998b998047fff5e3236880e"},
]

[package.extras]
cssselect = ["cssselect (>=0.7)"]
html5 = ["html5lib"]
htmlsoup = ["BeautifulSoup4"]
source = ["Cython (==0.29.37)"]

[[package]]
name = "markdown"
version = "3.5.1"
description = "Python implementation of John Gruber's Markdown."
optional = false
python-versions = ">=3.8"
files = [
    {file = "Markdown-3.5.1-py3-none-any.whl", hash = "sha256:5874b47d4ee3f0b14d764324d2c94c03ea66bee56f2d929da9f2508d65e722dc"},
    {file = "Markdown-3.5.1.tar.gz", hash = "sha256:b65d7beb248dc22f2e8a31fb706d93798093c308dc1aba295aedeb9d41a813bd"},
]

[package.extras]
docs = ["mdx-gh-links (>=0.2)", "mkdocs (>=1.5)", "mkdocs-gen-files", "mkdocs-literate-nav", "mkdocs-nature (>=0.6)", "mkdocs-section-index", "mkdocstrings[python]"]
testing = ["coverage", "pyyaml"]

[[package]]
name = "markdown2"
version = "2.4.12"
description = "A fast and complete Python implementation of Markdown"
optional = false
python-versions = ">=3.5, <4"
files = [
    {file = "markdown2-2.4.12-py2.py3-none-any.whl", hash = "sha256:98f47591006f0ace0644cbece03fed6f3845513286f6c6e9f8bcf6a575174e2c"},
    {file = "markdown2-2.4.12.tar.gz", hash = "sha256:1bc8692696954d597778e0e25713c14ca56d87992070dedd95c17eddaf709204"},
]

[package.extras]
all = ["pygments (>=2.7.3)", "wavedrom"]
code-syntax-highlighting = ["pygments (>=2.7.3)"]
wavedrom = ["wavedrom"]

[[package]]
name = "markupsafe"
version = "2.1.3"
description = "Safely add untrusted strings to HTML/XML markup."
optional = false
python-versions = ">=3.7"
files = [
    {file = "MarkupSafe-2.1.3-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:cd0f502fe016460680cd20aaa5a76d241d6f35a1c3350c474bac1273803893fa"},
    {file = "MarkupSafe-2.1.3-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:e09031c87a1e51556fdcb46e5bd4f59dfb743061cf93c4d6831bf894f125eb57"},
    {file = "MarkupSafe-2.1.3-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:68e78619a61ecf91e76aa3e6e8e33fc4894a2bebe93410754bd28fce0a8a4f9f"},
    {file = "MarkupSafe-2.1.3-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:65c1a9bcdadc6c28eecee2c119465aebff8f7a584dd719facdd9e825ec61ab52"},
    {file = "MarkupSafe-2.1.3-cp310-cp310-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:525808b8019e36eb524b8c68acdd63a37e75714eac50e988180b169d64480a00"},
    {file = "MarkupSafe-2.1.3-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:962f82a3086483f5e5f64dbad880d31038b698494799b097bc59c2edf392fce6"},
    {file = "MarkupSafe-2.1.3-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:aa7bd130efab1c280bed0f45501b7c8795f9fdbeb02e965371bbef3523627779"},
    {file = "MarkupSafe-2.1.3-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:c9c804664ebe8f83a211cace637506669e7890fec1b4195b505c214e50dd4eb7"},
    {file = "MarkupSafe-2.1.3-cp310-cp310-win32.whl", hash = "sha256:10bbfe99883db80bdbaff2dcf681dfc6533a614f700da1287707e8a5d78a8431"},
    {file = "MarkupSafe-2.1.3-cp310-cp310-win_amd64.whl", hash = "sha256:1577735524cdad32f9f694208aa75e422adba74f1baee7551620e43a3141f559"},
    {file = "MarkupSafe-2.1.3-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:ad9e82fb8f09ade1c3e1b996a6337afac2b8b9e365f926f5a61aacc71adc5b3c"},
    {file = "MarkupSafe-2.1.3-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:3c0fae6c3be832a0a0473ac912810b2877c8cb9d76ca48de1ed31e1c68386575"},
    {file = "MarkupSafe-2.1.3-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:b076b6226fb84157e3f7c971a47ff3a679d837cf338547532ab866c57930dbee"},
    {file = "MarkupSafe-2.1.3-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:bfce63a9e7834b12b87c64d6b155fdd9b3b96191b6bd334bf37db7ff1fe457f2"},
    {file = "MarkupSafe-2.1.3-cp311-cp311-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:338ae27d6b8745585f87218a3f23f1512dbf52c26c28e322dbe54bcede54ccb9"},
    {file = "MarkupSafe-2.1.3-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:e4dd52d80b8c83fdce44e12478ad2e85c64ea965e75d66dbeafb0a3e77308fcc"},
    {file = "MarkupSafe-2.1.3-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:df0be2b576a7abbf737b1575f048c23fb1d769f267ec4358296f31c2479db8f9"},
    {file = "MarkupSafe-2.1.3-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:5bbe06f8eeafd38e5d0a4894ffec89378b6c6a625ff57e3028921f8ff59318ac"},
    {file = "MarkupSafe-2.1.3-cp311-cp311-win32.whl", hash = "sha256:dd15ff04ffd7e05ffcb7fe79f1b98041b8ea30ae9234aed2a9168b5797c3effb"},
    {file = "MarkupSafe-2.1.3-cp311-cp311-win_amd64.whl", hash = "sha256:134da1eca9ec0ae528110ccc9e48041e0828d79f24121a1a146161103c76e686"},
    {file = "MarkupSafe-2.1.3-cp312-cp312-macosx_10_9_universal2.whl", hash = "sha256:f698de3fd0c4e6972b92290a45bd9b1536bffe8c6759c62471efaa8acb4c37bc"},
    {file = "MarkupSafe-2.1.3-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:aa57bd9cf8ae831a362185ee444e15a93ecb2e344c8e52e4d721ea3ab6ef1823"},
    {file = "MarkupSafe-2.1.3-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:ffcc3f7c66b5f5b7931a5aa68fc9cecc51e685ef90282f4a82f0f5e9b704ad11"},
    {file = "MarkupSafe-2.1.3-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:47d4f1c5f80fc62fdd7777d0d40a2e9dda0a05883ab11374334f6c4de38adffd"},
    {file = "MarkupSafe-2.1.3-cp312-cp312-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:1f67c7038d560d92149c060157d623c542173016c4babc0c1913cca0564b9939"},
    {file = "MarkupSafe-2.1.3-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:9aad3c1755095ce347e26488214ef77e0485a3c34a50c5a5e2471dff60b9dd9c"},
    {file = "MarkupSafe-2.1.3-cp312-cp312-musllinux_1_1_i686.whl", hash = "sha256:14ff806850827afd6b07a5f32bd917fb7f45b046ba40c57abdb636674a8b559c"},
    {file = "MarkupSafe-2.1.3-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:8f9293864fe09b8149f0cc42ce56e3f0e54de883a9de90cd427f191c346eb2e1"},
    {file = "MarkupSafe-2.1.3-cp312-cp312-win32.whl", hash = "sha256:715d3562f79d540f251b99ebd6d8baa547118974341db04f5ad06d5ea3eb8007"},
    {file = "MarkupSafe-2.1.3-cp312-cp312-win_amd64.whl", hash = "sha256:1b8dd8c3fd14349433c79fa8abeb573a55fc0fdd769133baac1f5e07abf54aeb"},
    {file = "MarkupSafe-2.1.3-cp37-cp37m-macosx_10_9_x86_64.whl", hash = "sha256:8e254ae696c88d98da6555f5ace2279cf7cd5b3f52be2b5cf97feafe883b58d2"},
    {file = "MarkupSafe-2.1.3-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:cb0932dc158471523c9637e807d9bfb93e06a95cbf010f1a38b98623b929ef2b"},
    {file = "MarkupSafe-2.1.3-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:9402b03f1a1b4dc4c19845e5c749e3ab82d5078d16a2a4c2cd2df62d57bb0707"},
    {file = "MarkupSafe-2.1.3-cp37-cp37m-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:ca379055a47383d02a5400cb0d110cef0a776fc644cda797db0c5696cfd7e18e"},
    {file = "MarkupSafe-2.1.3-cp37-cp37m-musllinux_1_1_aarch64.whl", hash = "sha256:b7ff0f54cb4ff66dd38bebd335a38e2c22c41a8ee45aa608efc890ac3e3931bc"},
    {file = "MarkupSafe-2.1.3-cp37-cp37m-musllinux_1_1_i686.whl", hash = "sha256:c011a4149cfbcf9f03994ec2edffcb8b1dc2d2aede7ca243746df97a5d41ce48"},
    {file = "MarkupSafe-2.1.3-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:56d9f2ecac662ca1611d183feb03a3fa4406469dafe241673d521dd5ae92a155"},
    {file = "MarkupSafe-2.1.3-cp37-cp37m-win32.whl", hash = "sha256:8758846a7e80910096950b67071243da3e5a20ed2546e6392603c096778d48e0"},
    {file = "MarkupSafe-2.1.3-cp37-cp37m-win_amd64.whl", hash = "sha256:787003c0ddb00500e49a10f2844fac87aa6ce977b90b0feaaf9de23c22508b24"},
    {file = "MarkupSafe-2.1.3-cp38-cp38-macosx_10_9_universal2.whl", hash = "sha256:2ef12179d3a291be237280175b542c07a36e7f60718296278d8593d21ca937d4"},
    {file = "MarkupSafe-2.1.3-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:2c1b19b3aaacc6e57b7e25710ff571c24d6c3613a45e905b1fde04d691b98ee0"},
    {file = "MarkupSafe-2.1.3-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:8afafd99945ead6e075b973fefa56379c5b5c53fd8937dad92c662da5d8fd5ee"},
    {file = "MarkupSafe-2.1.3-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:8c41976a29d078bb235fea9b2ecd3da465df42a562910f9022f1a03107bd02be"},
    {file = "MarkupSafe-2.1.3-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:d080e0a5eb2529460b30190fcfcc4199bd7f827663f858a226a81bc27beaa97e"},
    {file = "MarkupSafe-2.1.3-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:69c0f17e9f5a7afdf2cc9fb2d1ce6aabdb3bafb7f38017c0b77862bcec2bbad8"},
    {file = "MarkupSafe-2.1.3-cp38-cp38-musllinux_1_1_i686.whl", hash = "sha256:504b320cd4b7eff6f968eddf81127112db685e81f7e36e75f9f84f0df46041c3"},
    {file = "MarkupSafe-2.1.3-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:42de32b22b6b804f42c5d98be4f7e5e977ecdd9ee9b660fda1a3edf03b11792d"},
    {file = "MarkupSafe-2.1.3-cp38-cp38-win32.whl", hash = "sha256:ceb01949af7121f9fc39f7d27f91be8546f3fb112c608bc4029aef0bab86a2a5"},
    {file = "MarkupSafe-2.1.3-cp38-cp38-win_amd64.whl", hash = "sha256:1b40069d487e7edb2676d3fbdb2b0829ffa2cd63a2ec26c4938b2d34391b4ecc"},
    {file = "MarkupSafe-2.1.3-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:8023faf4e01efadfa183e863fefde0046de576c6f14659e8782065bcece22198"},
    {file = "MarkupSafe-2.1.3-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:6b2b56950d93e41f33b4223ead100ea0fe11f8e6ee5f641eb753ce4b77a7042b"},
    {file = "MarkupSafe-2.1.3-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:9dcdfd0eaf283af041973bff14a2e143b8bd64e069f4c383416ecd79a81aab58"},
    {file = "MarkupSafe-2.1.3-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:05fb21170423db021895e1ea1e1f3ab3adb85d1c2333cbc2310f2a26bc77272e"},
    {file = "MarkupSafe-2.1.3-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:282c2cb35b5b673bbcadb33a585408104df04f14b2d9b01d4c345a3b92861c2c"},
    {file = "MarkupSafe-2.1.3-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:ab4a0df41e7c16a1392727727e7998a467472d0ad65f3ad5e6e765015df08636"},
    {file = "MarkupSafe-2.1.3-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:7ef3cb2ebbf91e330e3bb937efada0edd9003683db6b57bb108c4001f37a02ea"},
    {file = "MarkupSafe-2.1.3-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:0a4e4a1aff6c7ac4cd55792abf96c915634c2b97e3cc1c7129578aa68ebd754e"},
    {file = "MarkupSafe-2.1.3-cp39-cp39-win32.whl", hash = "sha256:fec21693218efe39aa7f8599346e90c705afa52c5b31ae019b2e57e8f6542bb2"},
    {file = "MarkupSafe-2.1.3-cp39-cp39-win_amd64.whl", hash = "sha256:3fd4abcb888d15a94f32b75d8fd18ee162ca0c064f35b11134be77050296d6ba"},
    {file = "MarkupSafe-2.1.3.tar.gz", hash = "sha256:af598ed32d6ae86f1b747b82783958b1a4ab8f617b06fe68795c7f026abbdcad"},
]

[[package]]
name = "marshmallow"
version = "3.20.1"
description = "A lightweight library for converting complex datatypes to and from native Python datatypes."
optional = false
python-versions = ">=3.8"
files = [
    {file = "marshmallow-3.20.1-py3-none-any.whl", hash = "sha256:684939db93e80ad3561392f47be0230743131560a41c5110684c16e21ade0a5c"},
    {file = "marshmallow-3.20.1.tar.gz", hash = "sha256:5d2371bbe42000f2b3fb5eaa065224df7d8f8597bc19a1bbfa5bfe7fba8da889"},
]

[package.dependencies]
packaging = ">=17.0"

[package.extras]
dev = ["flake8 (==6.0.0)", "flake8-bugbear (==23.7.10)", "mypy (==1.4.1)", "pre-commit (>=2.4,<4.0)", "pytest", "pytz", "simplejson", "tox"]
docs = ["alabaster (==0.7.13)", "autodocsumm (==0.2.11)", "sphinx (==7.0.1)", "sphinx-issues (==3.0.1)", "sphinx-version-warning (==1.1.2)"]
lint = ["flake8 (==6.0.0)", "flake8-bugbear (==23.7.10)", "mypy (==1.4.1)", "pre-commit (>=2.4,<4.0)"]
tests = ["pytest", "pytz", "simplejson"]

[[package]]
name = "md2pdf"
version = "1.0.1"
description = "md2pdf, a Markdown to PDF conversion tool"
optional = false
python-versions = "*"
files = [
    {file = "md2pdf-1.0.1.tar.gz", hash = "sha256:3d5aab77dcd5b6f5827b193819ab1a8c1cec506ce5f6c777c3411b703352cd98"},
]

[package.dependencies]
docopt = "*"
markdown2 = "*"
WeasyPrint = "*"

[[package]]
name = "mistune"
version = "3.0.2"
description = "A sane and fast Markdown parser with useful plugins and renderers"
optional = false
python-versions = ">=3.7"
files = [
    {file = "mistune-3.0.2-py3-none-any.whl", hash = "sha256:71481854c30fdbc938963d3605b72501f5c10a9320ecd412c121c163a1c7d205"},
    {file = "mistune-3.0.2.tar.gz", hash = "sha256:fc7f93ded930c92394ef2cb6f04a8aabab4117a91449e72dcc8dfa646a508be8"},
]

[[package]]
name = "multidict"
version = "6.0.4"
description = "multidict implementation"
optional = false
python-versions = ">=3.7"
files = [
    {file = "multidict-6.0.4-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:0b1a97283e0c85772d613878028fec909f003993e1007eafa715b24b377cb9b8"},
    {file = "multidict-6.0.4-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:eeb6dcc05e911516ae3d1f207d4b0520d07f54484c49dfc294d6e7d63b734171"},
    {file = "multidict-6.0.4-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:d6d635d5209b82a3492508cf5b365f3446afb65ae7ebd755e70e18f287b0adf7"},
    {file = "multidict-6.0.4-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:c048099e4c9e9d615545e2001d3d8a4380bd403e1a0578734e0d31703d1b0c0b"},
    {file = "multidict-6.0.4-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:ea20853c6dbbb53ed34cb4d080382169b6f4554d394015f1bef35e881bf83547"},
    {file = "multidict-6.0.4-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:16d232d4e5396c2efbbf4f6d4df89bfa905eb0d4dc5b3549d872ab898451f569"},
    {file = "multidict-6.0.4-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:36c63aaa167f6c6b04ef2c85704e93af16c11d20de1d133e39de6a0e84582a93"},
    {file = "multidict-6.0.4-cp310-cp310-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:64bdf1086b6043bf519869678f5f2757f473dee970d7abf6da91ec00acb9cb98"},
    {file = "multidict-6.0.4-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:43644e38f42e3af682690876cff722d301ac585c5b9e1eacc013b7a3f7b696a0"},
    {file = "multidict-6.0.4-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:7582a1d1030e15422262de9f58711774e02fa80df0d1578995c76214f6954988"},
    {file = "multidict-6.0.4-cp310-cp310-musllinux_1_1_ppc64le.whl", hash = "sha256:ddff9c4e225a63a5afab9dd15590432c22e8057e1a9a13d28ed128ecf047bbdc"},
    {file = "multidict-6.0.4-cp310-cp310-musllinux_1_1_s390x.whl", hash = "sha256:ee2a1ece51b9b9e7752e742cfb661d2a29e7bcdba2d27e66e28a99f1890e4fa0"},
    {file = "multidict-6.0.4-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:a2e4369eb3d47d2034032a26c7a80fcb21a2cb22e1173d761a162f11e562caa5"},
    {file = "multidict-6.0.4-cp310-cp310-win32.whl", hash = "sha256:574b7eae1ab267e5f8285f0fe881f17efe4b98c39a40858247720935b893bba8"},
    {file = "multidict-6.0.4-cp310-cp310-win_amd64.whl", hash = "sha256:4dcbb0906e38440fa3e325df2359ac6cb043df8e58c965bb45f4e406ecb162cc"},
    {file = "multidict-6.0.4-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:0dfad7a5a1e39c53ed00d2dd0c2e36aed4650936dc18fd9a1826a5ae1cad6f03"},
    {file = "multidict-6.0.4-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:64da238a09d6039e3bd39bb3aee9c21a5e34f28bfa5aa22518581f910ff94af3"},
    {file = "multidict-6.0.4-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:ff959bee35038c4624250473988b24f846cbeb2c6639de3602c073f10410ceba"},
    {file = "multidict-6.0.4-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:01a3a55bd90018c9c080fbb0b9f4891db37d148a0a18722b42f94694f8b6d4c9"},
    {file = "multidict-6.0.4-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:c5cb09abb18c1ea940fb99360ea0396f34d46566f157122c92dfa069d3e0e982"},
    {file = "multidict-6.0.4-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:666daae833559deb2d609afa4490b85830ab0dfca811a98b70a205621a6109fe"},
    {file = "multidict-6.0.4-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:11bdf3f5e1518b24530b8241529d2050014c884cf18b6fc69c0c2b30ca248710"},
    {file = "multidict-6.0.4-cp311-cp311-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:7d18748f2d30f94f498e852c67d61261c643b349b9d2a581131725595c45ec6c"},
    {file = "multidict-6.0.4-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:458f37be2d9e4c95e2d8866a851663cbc76e865b78395090786f6cd9b3bbf4f4"},
    {file = "multidict-6.0.4-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:b1a2eeedcead3a41694130495593a559a668f382eee0727352b9a41e1c45759a"},
    {file = "multidict-6.0.4-cp311-cp311-musllinux_1_1_ppc64le.whl", hash = "sha256:7d6ae9d593ef8641544d6263c7fa6408cc90370c8cb2bbb65f8d43e5b0351d9c"},
    {file = "multidict-6.0.4-cp311-cp311-musllinux_1_1_s390x.whl", hash = "sha256:5979b5632c3e3534e42ca6ff856bb24b2e3071b37861c2c727ce220d80eee9ed"},
    {file = "multidict-6.0.4-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:dcfe792765fab89c365123c81046ad4103fcabbc4f56d1c1997e6715e8015461"},
    {file = "multidict-6.0.4-cp311-cp311-win32.whl", hash = "sha256:3601a3cece3819534b11d4efc1eb76047488fddd0c85a3948099d5da4d504636"},
    {file = "multidict-6.0.4-cp311-cp311-win_amd64.whl", hash = "sha256:81a4f0b34bd92df3da93315c6a59034df95866014ac08535fc819f043bfd51f0"},
    {file = "multidict-6.0.4-cp37-cp37m-macosx_10_9_x86_64.whl", hash = "sha256:67040058f37a2a51ed8ea8f6b0e6ee5bd78ca67f169ce6122f3e2ec80dfe9b78"},
    {file = "multidict-6.0.4-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:853888594621e6604c978ce2a0444a1e6e70c8d253ab65ba11657659dcc9100f"},
    {file = "multidict-6.0.4-cp37-cp37m-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:39ff62e7d0f26c248b15e364517a72932a611a9b75f35b45be078d81bdb86603"},
    {file = "multidict-6.0.4-cp37-cp37m-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:af048912e045a2dc732847d33821a9d84ba553f5c5f028adbd364dd4765092ac"},
    {file = "multidict-6.0.4-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:b1e8b901e607795ec06c9e42530788c45ac21ef3aaa11dbd0c69de543bfb79a9"},
    {file = "multidict-6.0.4-cp37-cp37m-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:62501642008a8b9871ddfccbf83e4222cf8ac0d5aeedf73da36153ef2ec222d2"},
    {file = "multidict-6.0.4-cp37-cp37m-musllinux_1_1_aarch64.whl", hash = "sha256:99b76c052e9f1bc0721f7541e5e8c05db3941eb9ebe7b8553c625ef88d6eefde"},
    {file = "multidict-6.0.4-cp37-cp37m-musllinux_1_1_i686.whl", hash = "sha256:509eac6cf09c794aa27bcacfd4d62c885cce62bef7b2c3e8b2e49d365b5003fe"},
    {file = "multidict-6.0.4-cp37-cp37m-musllinux_1_1_ppc64le.whl", hash = "sha256:21a12c4eb6ddc9952c415f24eef97e3e55ba3af61f67c7bc388dcdec1404a067"},
    {file = "multidict-6.0.4-cp37-cp37m-musllinux_1_1_s390x.whl", hash = "sha256:5cad9430ab3e2e4fa4a2ef4450f548768400a2ac635841bc2a56a2052cdbeb87"},
    {file = "multidict-6.0.4-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:ab55edc2e84460694295f401215f4a58597f8f7c9466faec545093045476327d"},
    {file = "multidict-6.0.4-cp37-cp37m-win32.whl", hash = "sha256:5a4dcf02b908c3b8b17a45fb0f15b695bf117a67b76b7ad18b73cf8e92608775"},
    {file = "multidict-6.0.4-cp37-cp37m-win_amd64.whl", hash = "sha256:6ed5f161328b7df384d71b07317f4d8656434e34591f20552c7bcef27b0ab88e"},
    {file = "multidict-6.0.4-cp38-cp38-macosx_10_9_universal2.whl", hash = "sha256:5fc1b16f586f049820c5c5b17bb4ee7583092fa0d1c4e28b5239181ff9532e0c"},
    {file = "multidict-6.0.4-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:1502e24330eb681bdaa3eb70d6358e818e8e8f908a22a1851dfd4e15bc2f8161"},
    {file = "multidict-6.0.4-cp38-cp38-macosx_11_0_arm64.whl", hash = "sha256:b692f419760c0e65d060959df05f2a531945af31fda0c8a3b3195d4efd06de11"},
    {file = "multidict-6.0.4-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:45e1ecb0379bfaab5eef059f50115b54571acfbe422a14f668fc8c27ba410e7e"},
    {file = "multidict-6.0.4-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:ddd3915998d93fbcd2566ddf9cf62cdb35c9e093075f862935573d265cf8f65d"},
    {file = "multidict-6.0.4-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:59d43b61c59d82f2effb39a93c48b845efe23a3852d201ed2d24ba830d0b4cf2"},
    {file = "multidict-6.0.4-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:cc8e1d0c705233c5dd0c5e6460fbad7827d5d36f310a0fadfd45cc3029762258"},
    {file = "multidict-6.0.4-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:d6aa0418fcc838522256761b3415822626f866758ee0bc6632c9486b179d0b52"},
    {file = "multidict-6.0.4-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:6748717bb10339c4760c1e63da040f5f29f5ed6e59d76daee30305894069a660"},
    {file = "multidict-6.0.4-cp38-cp38-musllinux_1_1_i686.whl", hash = "sha256:4d1a3d7ef5e96b1c9e92f973e43aa5e5b96c659c9bc3124acbbd81b0b9c8a951"},
    {file = "multidict-6.0.4-cp38-cp38-musllinux_1_1_ppc64le.whl", hash = "sha256:4372381634485bec7e46718edc71528024fcdc6f835baefe517b34a33c731d60"},
    {file = "multidict-6.0.4-cp38-cp38-musllinux_1_1_s390x.whl", hash = "sha256:fc35cb4676846ef752816d5be2193a1e8367b4c1397b74a565a9d0389c433a1d"},
    {file = "multidict-6.0.4-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:4b9d9e4e2b37daddb5c23ea33a3417901fa7c7b3dee2d855f63ee67a0b21e5b1"},
    {file = "multidict-6.0.4-cp38-cp38-win32.whl", hash = "sha256:e41b7e2b59679edfa309e8db64fdf22399eec4b0b24694e1b2104fb789207779"},
    {file = "multidict-6.0.4-cp38-cp38-win_amd64.whl", hash = "sha256:d6c254ba6e45d8e72739281ebc46ea5eb5f101234f3ce171f0e9f5cc86991480"},
    {file = "multidict-6.0.4-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:16ab77bbeb596e14212e7bab8429f24c1579234a3a462105cda4a66904998664"},
    {file = "multidict-6.0.4-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:bc779e9e6f7fda81b3f9aa58e3a6091d49ad528b11ed19f6621408806204ad35"},
    {file = "multidict-6.0.4-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:4ceef517eca3e03c1cceb22030a3e39cb399ac86bff4e426d4fc6ae49052cc60"},
    {file = "multidict-6.0.4-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:281af09f488903fde97923c7744bb001a9b23b039a909460d0f14edc7bf59706"},
    {file = "multidict-6.0.4-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:52f2dffc8acaba9a2f27174c41c9e57f60b907bb9f096b36b1a1f3be71c6284d"},
    {file = "multidict-6.0.4-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:b41156839806aecb3641f3208c0dafd3ac7775b9c4c422d82ee2a45c34ba81ca"},
    {file = "multidict-6.0.4-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:d5e3fc56f88cc98ef8139255cf8cd63eb2c586531e43310ff859d6bb3a6b51f1"},
    {file = "multidict-6.0.4-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:8316a77808c501004802f9beebde51c9f857054a0c871bd6da8280e718444449"},
    {file = "multidict-6.0.4-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:f70b98cd94886b49d91170ef23ec5c0e8ebb6f242d734ed7ed677b24d50c82cf"},
    {file = "multidict-6.0.4-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:bf6774e60d67a9efe02b3616fee22441d86fab4c6d335f9d2051d19d90a40063"},
    {file = "multidict-6.0.4-cp39-cp39-musllinux_1_1_ppc64le.whl", hash = "sha256:e69924bfcdda39b722ef4d9aa762b2dd38e4632b3641b1d9a57ca9cd18f2f83a"},
    {file = "multidict-6.0.4-cp39-cp39-musllinux_1_1_s390x.whl", hash = "sha256:6b181d8c23da913d4ff585afd1155a0e1194c0b50c54fcfe286f70cdaf2b7176"},
    {file = "multidict-6.0.4-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:52509b5be062d9eafc8170e53026fbc54cf3b32759a23d07fd935fb04fc22d95"},
    {file = "multidict-6.0.4-cp39-cp39-win32.whl", hash = "sha256:27c523fbfbdfd19c6867af7346332b62b586eed663887392cff78d614f9ec313"},
    {file = "multidict-6.0.4-cp39-cp39-win_amd64.whl", hash = "sha256:33029f5734336aa0d4c0384525da0387ef89148dc7191aae00ca5fb23d7aafc2"},
    {file = "multidict-6.0.4.tar.gz", hash = "sha256:3666906492efb76453c0e7b97f2cf459b0682e7402c0489a95484965dbc1da49"},
]

[[package]]
name = "mypy-extensions"
version = "1.0.0"
description = "Type system extensions for programs checked with the mypy type checker."
optional = false
python-versions = ">=3.5"
files = [
    {file = "mypy_extensions-1.0.0-py3-none-any.whl", hash = "sha256:4392f6c0eb8a5668a69e23d168ffa70f0be9ccfd32b5cc2d26a34ae5b844552d"},
    {file = "mypy_extensions-1.0.0.tar.gz", hash = "sha256:75dbf8955dc00442a438fc4d0666508a9a97b6bd41aa2f0ffe9d2f2725af0782"},
]

[[package]]
name = "newspaper3k"
version = "0.2.8"
description = "Simplified python article discovery & extraction."
optional = false
python-versions = "*"
files = [
    {file = "newspaper3k-0.2.8-py3-none-any.whl", hash = "sha256:44a864222633d3081113d1030615991c3dbba87239f6bbf59d91240f71a22e3e"},
    {file = "newspaper3k-0.2.8.tar.gz", hash = "sha256:9f1bd3e1fb48f400c715abf875cc7b0a67b7ddcd87f50c9aeeb8fcbbbd9004fb"},
]

[package.dependencies]
beautifulsoup4 = ">=4.4.1"
cssselect = ">=0.9.2"
feedfinder2 = ">=0.0.4"
feedparser = ">=5.2.1"
jieba3k = ">=0.35.1"
lxml = ">=3.6.0"
nltk = ">=3.2.1"
Pillow = ">=3.3.0"
python-dateutil = ">=2.5.3"
PyYAML = ">=3.11"
requests = ">=2.10.0"
tinysegmenter = "0.3"
tldextract = ">=2.0.1"

[[package]]
name = "nltk"
version = "3.8.1"
description = "Natural Language Toolkit"
optional = false
python-versions = ">=3.7"
files = [
    {file = "nltk-3.8.1-py3-none-any.whl", hash = "sha256:fd5c9109f976fa86bcadba8f91e47f5e9293bd034474752e92a520f81c93dda5"},
    {file = "nltk-3.8.1.zip", hash = "sha256:1834da3d0682cba4f2cede2f9aad6b0fafb6461ba451db0efb6f9c39798d64d3"},
]

[package.dependencies]
click = "*"
joblib = "*"
regex = ">=2021.8.3"
tqdm = "*"

[package.extras]
all = ["matplotlib", "numpy", "pyparsing", "python-crfsuite", "requests", "scikit-learn", "scipy", "twython"]
corenlp = ["requests"]
machine-learning = ["numpy", "python-crfsuite", "scikit-learn", "scipy"]
plot = ["matplotlib"]
tgrep = ["pyparsing"]
twitter = ["twython"]

[[package]]
name = "numpy"
version = "1.26.2"
description = "Fundamental package for array computing in Python"
optional = false
python-versions = ">=3.9"
files = [
    {file = "numpy-1.26.2-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:3703fc9258a4a122d17043e57b35e5ef1c5a5837c3db8be396c82e04c1cf9b0f"},
    {file = "numpy-1.26.2-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:cc392fdcbd21d4be6ae1bb4475a03ce3b025cd49a9be5345d76d7585aea69440"},
    {file = "numpy-1.26.2-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:36340109af8da8805d8851ef1d74761b3b88e81a9bd80b290bbfed61bd2b4f75"},
    {file = "numpy-1.26.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:bcc008217145b3d77abd3e4d5ef586e3bdfba8fe17940769f8aa09b99e856c00"},
    {file = "numpy-1.26.2-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:3ced40d4e9e18242f70dd02d739e44698df3dcb010d31f495ff00a31ef6014fe"},
    {file = "numpy-1.26.2-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:b272d4cecc32c9e19911891446b72e986157e6a1809b7b56518b4f3755267523"},
    {file = "numpy-1.26.2-cp310-cp310-win32.whl", hash = "sha256:22f8fc02fdbc829e7a8c578dd8d2e15a9074b630d4da29cda483337e300e3ee9"},
    {file = "numpy-1.26.2-cp310-cp310-win_amd64.whl", hash = "sha256:26c9d33f8e8b846d5a65dd068c14e04018d05533b348d9eaeef6c1bd787f9919"},
    {file = "numpy-1.26.2-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:b96e7b9c624ef3ae2ae0e04fa9b460f6b9f17ad8b4bec6d7756510f1f6c0c841"},
    {file = "numpy-1.26.2-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:aa18428111fb9a591d7a9cc1b48150097ba6a7e8299fb56bdf574df650e7d1f1"},
    {file = "numpy-1.26.2-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:06fa1ed84aa60ea6ef9f91ba57b5ed963c3729534e6e54055fc151fad0423f0a"},
    {file = "numpy-1.26.2-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:96ca5482c3dbdd051bcd1fce8034603d6ebfc125a7bd59f55b40d8f5d246832b"},
    {file = "numpy-1.26.2-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:854ab91a2906ef29dc3925a064fcd365c7b4da743f84b123002f6139bcb3f8a7"},
    {file = "numpy-1.26.2-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:f43740ab089277d403aa07567be138fc2a89d4d9892d113b76153e0e412409f8"},
    {file = "numpy-1.26.2-cp311-cp311-win32.whl", hash = "sha256:a2bbc29fcb1771cd7b7425f98b05307776a6baf43035d3b80c4b0f29e9545186"},
    {file = "numpy-1.26.2-cp311-cp311-win_amd64.whl", hash = "sha256:2b3fca8a5b00184828d12b073af4d0fc5fdd94b1632c2477526f6bd7842d700d"},
    {file = "numpy-1.26.2-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:a4cd6ed4a339c21f1d1b0fdf13426cb3b284555c27ac2f156dfdaaa7e16bfab0"},
    {file = "numpy-1.26.2-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:5d5244aabd6ed7f312268b9247be47343a654ebea52a60f002dc70c769048e75"},
    {file = "numpy-1.26.2-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:6a3cdb4d9c70e6b8c0814239ead47da00934666f668426fc6e94cce869e13fd7"},
    {file = "numpy-1.26.2-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:aa317b2325f7aa0a9471663e6093c210cb2ae9c0ad824732b307d2c51983d5b6"},
    {file = "numpy-1.26.2-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:174a8880739c16c925799c018f3f55b8130c1f7c8e75ab0a6fa9d41cab092fd6"},
    {file = "numpy-1.26.2-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:f79b231bf5c16b1f39c7f4875e1ded36abee1591e98742b05d8a0fb55d8a3eec"},
    {file = "numpy-1.26.2-cp312-cp312-win32.whl", hash = "sha256:4a06263321dfd3598cacb252f51e521a8cb4b6df471bb12a7ee5cbab20ea9167"},
    {file = "numpy-1.26.2-cp312-cp312-win_amd64.whl", hash = "sha256:b04f5dc6b3efdaab541f7857351aac359e6ae3c126e2edb376929bd3b7f92d7e"},
    {file = "numpy-1.26.2-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:4eb8df4bf8d3d90d091e0146f6c28492b0be84da3e409ebef54349f71ed271ef"},
    {file = "numpy-1.26.2-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:1a13860fdcd95de7cf58bd6f8bc5a5ef81c0b0625eb2c9a783948847abbef2c2"},
    {file = "numpy-1.26.2-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:64308ebc366a8ed63fd0bf426b6a9468060962f1a4339ab1074c228fa6ade8e3"},
    {file = "numpy-1.26.2-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:baf8aab04a2c0e859da118f0b38617e5ee65d75b83795055fb66c0d5e9e9b818"},
    {file = "numpy-1.26.2-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:d73a3abcac238250091b11caef9ad12413dab01669511779bc9b29261dd50210"},
    {file = "numpy-1.26.2-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:b361d369fc7e5e1714cf827b731ca32bff8d411212fccd29ad98ad622449cc36"},
    {file = "numpy-1.26.2-cp39-cp39-win32.whl", hash = "sha256:bd3f0091e845164a20bd5a326860c840fe2af79fa12e0469a12768a3ec578d80"},
    {file = "numpy-1.26.2-cp39-cp39-win_amd64.whl", hash = "sha256:2beef57fb031dcc0dc8fa4fe297a742027b954949cabb52a2a376c144e5e6060"},
    {file = "numpy-1.26.2-pp39-pypy39_pp73-macosx_10_9_x86_64.whl", hash = "sha256:1cc3d5029a30fb5f06704ad6b23b35e11309491c999838c31f124fee32107c79"},
    {file = "numpy-1.26.2-pp39-pypy39_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:94cc3c222bb9fb5a12e334d0479b97bb2df446fbe622b470928f5284ffca3f8d"},
    {file = "numpy-1.26.2-pp39-pypy39_pp73-win_amd64.whl", hash = "sha256:fe6b44fb8fcdf7eda4ef4461b97b3f63c466b27ab151bec2366db8b197387841"},
    {file = "numpy-1.26.2.tar.gz", hash = "sha256:f65738447676ab5777f11e6bbbdb8ce11b785e105f690bc45966574816b6d3ea"},
]

[[package]]
name = "openai"
version = "1.14.2"
description = "The official Python library for the openai API"
optional = false
python-versions = ">=3.7.1"
files = [
    {file = "openai-1.14.2-py3-none-any.whl", hash = "sha256:a48b3c4d635b603952189ac5a0c0c9b06c025b80eb2900396939f02bb2104ac3"},
    {file = "openai-1.14.2.tar.gz", hash = "sha256:e5642f7c02cf21994b08477d7bb2c1e46d8f335d72c26f0396c5f89b15b5b153"},
]

[package.dependencies]
anyio = ">=3.5.0,<5"
distro = ">=1.7.0,<2"
httpx = ">=0.23.0,<1"
pydantic = ">=1.9.0,<3"
sniffio = "*"
tqdm = ">4"
typing-extensions = ">=4.7,<5"

[package.extras]
datalib = ["numpy (>=1)", "pandas (>=1.2.3)", "pandas-stubs (>=1.1.0.11)"]

[[package]]
name = "orjson"
version = "3.9.15"
description = "Fast, correct Python JSON library supporting dataclasses, datetimes, and numpy"
optional = false
python-versions = ">=3.8"
files = [
    {file = "orjson-3.9.15-cp310-cp310-macosx_10_15_x86_64.macosx_11_0_arm64.macosx_10_15_universal2.whl", hash = "sha256:d61f7ce4727a9fa7680cd6f3986b0e2c732639f46a5e0156e550e35258aa313a"},
    {file = "orjson-3.9.15-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:4feeb41882e8aa17634b589533baafdceb387e01e117b1ec65534ec724023d04"},
    {file = "orjson-3.9.15-cp310-cp310-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:fbbeb3c9b2edb5fd044b2a070f127a0ac456ffd079cb82746fc84af01ef021a4"},
    {file = "orjson-3.9.15-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:b66bcc5670e8a6b78f0313bcb74774c8291f6f8aeef10fe70e910b8040f3ab75"},
    {file = "orjson-3.9.15-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:2973474811db7b35c30248d1129c64fd2bdf40d57d84beed2a9a379a6f57d0ab"},
    {file = "orjson-3.9.15-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:9fe41b6f72f52d3da4db524c8653e46243c8c92df826ab5ffaece2dba9cccd58"},
    {file = "orjson-3.9.15-cp310-cp310-musllinux_1_2_aarch64.whl", hash = "sha256:4228aace81781cc9d05a3ec3a6d2673a1ad0d8725b4e915f1089803e9efd2b99"},
    {file = "orjson-3.9.15-cp310-cp310-musllinux_1_2_x86_64.whl", hash = "sha256:6f7b65bfaf69493c73423ce9db66cfe9138b2f9ef62897486417a8fcb0a92bfe"},
    {file = "orjson-3.9.15-cp310-none-win32.whl", hash = "sha256:2d99e3c4c13a7b0fb3792cc04c2829c9db07838fb6973e578b85c1745e7d0ce7"},
    {file = "orjson-3.9.15-cp310-none-win_amd64.whl", hash = "sha256:b725da33e6e58e4a5d27958568484aa766e825e93aa20c26c91168be58e08cbb"},
    {file = "orjson-3.9.15-cp311-cp311-macosx_10_15_x86_64.macosx_11_0_arm64.macosx_10_15_universal2.whl", hash = "sha256:c8e8fe01e435005d4421f183038fc70ca85d2c1e490f51fb972db92af6e047c2"},
    {file = "orjson-3.9.15-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:87f1097acb569dde17f246faa268759a71a2cb8c96dd392cd25c668b104cad2f"},
    {file = "orjson-3.9.15-cp311-cp311-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:ff0f9913d82e1d1fadbd976424c316fbc4d9c525c81d047bbdd16bd27dd98cfc"},
    {file = "orjson-3.9.15-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:8055ec598605b0077e29652ccfe9372247474375e0e3f5775c91d9434e12d6b1"},
    {file = "orjson-3.9.15-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:d6768a327ea1ba44c9114dba5fdda4a214bdb70129065cd0807eb5f010bfcbb5"},
    {file = "orjson-3.9.15-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:12365576039b1a5a47df01aadb353b68223da413e2e7f98c02403061aad34bde"},
    {file = "orjson-3.9.15-cp311-cp311-musllinux_1_2_aarch64.whl", hash = "sha256:71c6b009d431b3839d7c14c3af86788b3cfac41e969e3e1c22f8a6ea13139404"},
    {file = "orjson-3.9.15-cp311-cp311-musllinux_1_2_x86_64.whl", hash = "sha256:e18668f1bd39e69b7fed19fa7cd1cd110a121ec25439328b5c89934e6d30d357"},
    {file = "orjson-3.9.15-cp311-none-win32.whl", hash = "sha256:62482873e0289cf7313461009bf62ac8b2e54bc6f00c6fabcde785709231a5d7"},
    {file = "orjson-3.9.15-cp311-none-win_amd64.whl", hash = "sha256:b3d336ed75d17c7b1af233a6561cf421dee41d9204aa3cfcc6c9c65cd5bb69a8"},
    {file = "orjson-3.9.15-cp312-cp312-macosx_10_15_x86_64.macosx_11_0_arm64.macosx_10_15_universal2.whl", hash = "sha256:82425dd5c7bd3adfe4e94c78e27e2fa02971750c2b7ffba648b0f5d5cc016a73"},
    {file = "orjson-3.9.15-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:2c51378d4a8255b2e7c1e5cc430644f0939539deddfa77f6fac7b56a9784160a"},
    {file = "orjson-3.9.15-cp312-cp312-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:6ae4e06be04dc00618247c4ae3f7c3e561d5bc19ab6941427f6d3722a0875ef7"},
    {file = "orjson-3.9.15-cp312-cp312-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:bcef128f970bb63ecf9a65f7beafd9b55e3aaf0efc271a4154050fc15cdb386e"},
    {file = "orjson-3.9.15-cp312-cp312-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:b72758f3ffc36ca566ba98a8e7f4f373b6c17c646ff8ad9b21ad10c29186f00d"},
    {file = "orjson-3.9.15-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:10c57bc7b946cf2efa67ac55766e41764b66d40cbd9489041e637c1304400494"},
    {file = "orjson-3.9.15-cp312-cp312-musllinux_1_2_aarch64.whl", hash = "sha256:946c3a1ef25338e78107fba746f299f926db408d34553b4754e90a7de1d44068"},
    {file = "orjson-3.9.15-cp312-cp312-musllinux_1_2_x86_64.whl", hash = "sha256:2f256d03957075fcb5923410058982aea85455d035607486ccb847f095442bda"},
    {file = "orjson-3.9.15-cp312-none-win_amd64.whl", hash = "sha256:5bb399e1b49db120653a31463b4a7b27cf2fbfe60469546baf681d1b39f4edf2"},
    {file = "orjson-3.9.15-cp38-cp38-macosx_10_15_x86_64.macosx_11_0_arm64.macosx_10_15_universal2.whl", hash = "sha256:b17f0f14a9c0ba55ff6279a922d1932e24b13fc218a3e968ecdbf791b3682b25"},
    {file = "orjson-3.9.15-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:7f6cbd8e6e446fb7e4ed5bac4661a29e43f38aeecbf60c4b900b825a353276a1"},
    {file = "orjson-3.9.15-cp38-cp38-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:76bc6356d07c1d9f4b782813094d0caf1703b729d876ab6a676f3aaa9a47e37c"},
    {file = "orjson-3.9.15-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:fdfa97090e2d6f73dced247a2f2d8004ac6449df6568f30e7fa1a045767c69a6"},
    {file = "orjson-3.9.15-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:7413070a3e927e4207d00bd65f42d1b780fb0d32d7b1d951f6dc6ade318e1b5a"},
    {file = "orjson-3.9.15-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:9cf1596680ac1f01839dba32d496136bdd5d8ffb858c280fa82bbfeb173bdd40"},
    {file = "orjson-3.9.15-cp38-cp38-musllinux_1_2_aarch64.whl", hash = "sha256:809d653c155e2cc4fd39ad69c08fdff7f4016c355ae4b88905219d3579e31eb7"},
    {file = "orjson-3.9.15-cp38-cp38-musllinux_1_2_x86_64.whl", hash = "sha256:920fa5a0c5175ab14b9c78f6f820b75804fb4984423ee4c4f1e6d748f8b22bc1"},
    {file = "orjson-3.9.15-cp38-none-win32.whl", hash = "sha256:2b5c0f532905e60cf22a511120e3719b85d9c25d0e1c2a8abb20c4dede3b05a5"},
    {file = "orjson-3.9.15-cp38-none-win_amd64.whl", hash = "sha256:67384f588f7f8daf040114337d34a5188346e3fae6c38b6a19a2fe8c663a2f9b"},
    {file = "orjson-3.9.15-cp39-cp39-macosx_10_15_x86_64.macosx_11_0_arm64.macosx_10_15_universal2.whl", hash = "sha256:6fc2fe4647927070df3d93f561d7e588a38865ea0040027662e3e541d592811e"},
    {file = "orjson-3.9.15-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:34cbcd216e7af5270f2ffa63a963346845eb71e174ea530867b7443892d77180"},
    {file = "orjson-3.9.15-cp39-cp39-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:f541587f5c558abd93cb0de491ce99a9ef8d1ae29dd6ab4dbb5a13281ae04cbd"},
    {file = "orjson-3.9.15-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:92255879280ef9c3c0bcb327c5a1b8ed694c290d61a6a532458264f887f052cb"},
    {file = "orjson-3.9.15-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:05a1f57fb601c426635fcae9ddbe90dfc1ed42245eb4c75e4960440cac667262"},
    {file = "orjson-3.9.15-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:ede0bde16cc6e9b96633df1631fbcd66491d1063667f260a4f2386a098393790"},
    {file = "orjson-3.9.15-cp39-cp39-musllinux_1_2_aarch64.whl", hash = "sha256:e88b97ef13910e5f87bcbc4dd7979a7de9ba8702b54d3204ac587e83639c0c2b"},
    {file = "orjson-3.9.15-cp39-cp39-musllinux_1_2_x86_64.whl", hash = "sha256:57d5d8cf9c27f7ef6bc56a5925c7fbc76b61288ab674eb352c26ac780caa5b10"},
    {file = "orjson-3.9.15-cp39-none-win32.whl", hash = "sha256:001f4eb0ecd8e9ebd295722d0cbedf0748680fb9998d3993abaed2f40587257a"},
    {file = "orjson-3.9.15-cp39-none-win_amd64.whl", hash = "sha256:ea0b183a5fe6b2b45f3b854b0d19c4e932d6f5934ae1f723b07cf9560edd4ec7"},
    {file = "orjson-3.9.15.tar.gz", hash = "sha256:95cae920959d772f30ab36d3b25f83bb0f3be671e986c72ce22f8fa700dae061"},
]

[[package]]
name = "outcome"
version = "1.3.0.post0"
description = "Capture the outcome of Python function calls."
optional = false
python-versions = ">=3.7"
files = [
    {file = "outcome-1.3.0.post0-py2.py3-none-any.whl", hash = "sha256:e771c5ce06d1415e356078d3bdd68523f284b4ce5419828922b6871e65eda82b"},
    {file = "outcome-1.3.0.post0.tar.gz", hash = "sha256:9dcf02e65f2971b80047b377468e72a268e15c0af3cf1238e6ff14f7f91143b8"},
]

[package.dependencies]
attrs = ">=19.2.0"

[[package]]
name = "packaging"
version = "23.2"
description = "Core utilities for Python packages"
optional = false
python-versions = ">=3.7"
files = [
    {file = "packaging-23.2-py3-none-any.whl", hash = "sha256:8c491190033a9af7e1d931d0b5dacc2ef47509b34dd0de67ed209b5203fc88c7"},
    {file = "packaging-23.2.tar.gz", hash = "sha256:048fb0e9405036518eaaf48a55953c750c11e1a1b68e0dd1a9d62ed0c092cfc5"},
]

[[package]]
name = "permchain"
version = "0.0.6"
description = "permchain"
optional = false
python-versions = ">=3.8.1,<4.0"
files = [
    {file = "permchain-0.0.6-py3-none-any.whl", hash = "sha256:420891760db90b5f5398e53ced5361f548712d79ac7957864c769a6534392c72"},
    {file = "permchain-0.0.6.tar.gz", hash = "sha256:505171943e068f567c0dc2f4692d8654d8444347a9e9965614033cd70d5982fd"},
]

[package.dependencies]
langchain = ">=0.0.335"

[[package]]
name = "pillow"
version = "10.1.0"
description = "Python Imaging Library (Fork)"
optional = false
python-versions = ">=3.8"
files = [
    {file = "Pillow-10.1.0-cp310-cp310-macosx_10_10_x86_64.whl", hash = "sha256:1ab05f3db77e98f93964697c8efc49c7954b08dd61cff526b7f2531a22410106"},
    {file = "Pillow-10.1.0-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:6932a7652464746fcb484f7fc3618e6503d2066d853f68a4bd97193a3996e273"},
    {file = "Pillow-10.1.0-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:a5f63b5a68daedc54c7c3464508d8c12075e56dcfbd42f8c1bf40169061ae666"},
    {file = "Pillow-10.1.0-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:c0949b55eb607898e28eaccb525ab104b2d86542a85c74baf3a6dc24002edec2"},
    {file = "Pillow-10.1.0-cp310-cp310-manylinux_2_28_aarch64.whl", hash = "sha256:ae88931f93214777c7a3aa0a8f92a683f83ecde27f65a45f95f22d289a69e593"},
    {file = "Pillow-10.1.0-cp310-cp310-manylinux_2_28_x86_64.whl", hash = "sha256:b0eb01ca85b2361b09480784a7931fc648ed8b7836f01fb9241141b968feb1db"},
    {file = "Pillow-10.1.0-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:d27b5997bdd2eb9fb199982bb7eb6164db0426904020dc38c10203187ae2ff2f"},
    {file = "Pillow-10.1.0-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:7df5608bc38bd37ef585ae9c38c9cd46d7c81498f086915b0f97255ea60c2818"},
    {file = "Pillow-10.1.0-cp310-cp310-win_amd64.whl", hash = "sha256:41f67248d92a5e0a2076d3517d8d4b1e41a97e2df10eb8f93106c89107f38b57"},
    {file = "Pillow-10.1.0-cp311-cp311-macosx_10_10_x86_64.whl", hash = "sha256:1fb29c07478e6c06a46b867e43b0bcdb241b44cc52be9bc25ce5944eed4648e7"},
    {file = "Pillow-10.1.0-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:2cdc65a46e74514ce742c2013cd4a2d12e8553e3a2563c64879f7c7e4d28bce7"},
    {file = "Pillow-10.1.0-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:50d08cd0a2ecd2a8657bd3d82c71efd5a58edb04d9308185d66c3a5a5bed9610"},
    {file = "Pillow-10.1.0-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:062a1610e3bc258bff2328ec43f34244fcec972ee0717200cb1425214fe5b839"},
    {file = "Pillow-10.1.0-cp311-cp311-manylinux_2_28_aarch64.whl", hash = "sha256:61f1a9d247317fa08a308daaa8ee7b3f760ab1809ca2da14ecc88ae4257d6172"},
    {file = "Pillow-10.1.0-cp311-cp311-manylinux_2_28_x86_64.whl", hash = "sha256:a646e48de237d860c36e0db37ecaecaa3619e6f3e9d5319e527ccbc8151df061"},
    {file = "Pillow-10.1.0-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:47e5bf85b80abc03be7455c95b6d6e4896a62f6541c1f2ce77a7d2bb832af262"},
    {file = "Pillow-10.1.0-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:a92386125e9ee90381c3369f57a2a50fa9e6aa8b1cf1d9c4b200d41a7dd8e992"},
    {file = "Pillow-10.1.0-cp311-cp311-win_amd64.whl", hash = "sha256:0f7c276c05a9767e877a0b4c5050c8bee6a6d960d7f0c11ebda6b99746068c2a"},
    {file = "Pillow-10.1.0-cp312-cp312-macosx_10_10_x86_64.whl", hash = "sha256:a89b8312d51715b510a4fe9fc13686283f376cfd5abca8cd1c65e4c76e21081b"},
    {file = "Pillow-10.1.0-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:00f438bb841382b15d7deb9a05cc946ee0f2c352653c7aa659e75e592f6fa17d"},
    {file = "Pillow-10.1.0-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:3d929a19f5469b3f4df33a3df2983db070ebb2088a1e145e18facbc28cae5b27"},
    {file = "Pillow-10.1.0-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:9a92109192b360634a4489c0c756364c0c3a2992906752165ecb50544c251312"},
    {file = "Pillow-10.1.0-cp312-cp312-manylinux_2_28_aarch64.whl", hash = "sha256:0248f86b3ea061e67817c47ecbe82c23f9dd5d5226200eb9090b3873d3ca32de"},
    {file = "Pillow-10.1.0-cp312-cp312-manylinux_2_28_x86_64.whl", hash = "sha256:9882a7451c680c12f232a422730f986a1fcd808da0fd428f08b671237237d651"},
    {file = "Pillow-10.1.0-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:1c3ac5423c8c1da5928aa12c6e258921956757d976405e9467c5f39d1d577a4b"},
    {file = "Pillow-10.1.0-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:806abdd8249ba3953c33742506fe414880bad78ac25cc9a9b1c6ae97bedd573f"},
    {file = "Pillow-10.1.0-cp312-cp312-win_amd64.whl", hash = "sha256:eaed6977fa73408b7b8a24e8b14e59e1668cfc0f4c40193ea7ced8e210adf996"},
    {file = "Pillow-10.1.0-cp38-cp38-macosx_10_10_x86_64.whl", hash = "sha256:fe1e26e1ffc38be097f0ba1d0d07fcade2bcfd1d023cda5b29935ae8052bd793"},
    {file = "Pillow-10.1.0-cp38-cp38-macosx_11_0_arm64.whl", hash = "sha256:7a7e3daa202beb61821c06d2517428e8e7c1aab08943e92ec9e5755c2fc9ba5e"},
    {file = "Pillow-10.1.0-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:24fadc71218ad2b8ffe437b54876c9382b4a29e030a05a9879f615091f42ffc2"},
    {file = "Pillow-10.1.0-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:fa1d323703cfdac2036af05191b969b910d8f115cf53093125e4058f62012c9a"},
    {file = "Pillow-10.1.0-cp38-cp38-manylinux_2_28_aarch64.whl", hash = "sha256:912e3812a1dbbc834da2b32299b124b5ddcb664ed354916fd1ed6f193f0e2d01"},
    {file = "Pillow-10.1.0-cp38-cp38-manylinux_2_28_x86_64.whl", hash = "sha256:7dbaa3c7de82ef37e7708521be41db5565004258ca76945ad74a8e998c30af8d"},
    {file = "Pillow-10.1.0-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:9d7bc666bd8c5a4225e7ac71f2f9d12466ec555e89092728ea0f5c0c2422ea80"},
    {file = "Pillow-10.1.0-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:baada14941c83079bf84c037e2d8b7506ce201e92e3d2fa0d1303507a8538212"},
    {file = "Pillow-10.1.0-cp38-cp38-win_amd64.whl", hash = "sha256:2ef6721c97894a7aa77723740a09547197533146fba8355e86d6d9a4a1056b14"},
    {file = "Pillow-10.1.0-cp39-cp39-macosx_10_10_x86_64.whl", hash = "sha256:0a026c188be3b443916179f5d04548092e253beb0c3e2ee0a4e2cdad72f66099"},
    {file = "Pillow-10.1.0-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:04f6f6149f266a100374ca3cc368b67fb27c4af9f1cc8cb6306d849dcdf12616"},
    {file = "Pillow-10.1.0-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:bb40c011447712d2e19cc261c82655f75f32cb724788df315ed992a4d65696bb"},
    {file = "Pillow-10.1.0-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:1a8413794b4ad9719346cd9306118450b7b00d9a15846451549314a58ac42219"},
    {file = "Pillow-10.1.0-cp39-cp39-manylinux_2_28_aarch64.whl", hash = "sha256:c9aeea7b63edb7884b031a35305629a7593272b54f429a9869a4f63a1bf04c34"},
    {file = "Pillow-10.1.0-cp39-cp39-manylinux_2_28_x86_64.whl", hash = "sha256:b4005fee46ed9be0b8fb42be0c20e79411533d1fd58edabebc0dd24626882cfd"},
    {file = "Pillow-10.1.0-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:4d0152565c6aa6ebbfb1e5d8624140a440f2b99bf7afaafbdbf6430426497f28"},
    {file = "Pillow-10.1.0-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:d921bc90b1defa55c9917ca6b6b71430e4286fc9e44c55ead78ca1a9f9eba5f2"},
    {file = "Pillow-10.1.0-cp39-cp39-win_amd64.whl", hash = "sha256:cfe96560c6ce2f4c07d6647af2d0f3c54cc33289894ebd88cfbb3bcd5391e256"},
    {file = "Pillow-10.1.0-pp310-pypy310_pp73-macosx_10_10_x86_64.whl", hash = "sha256:937bdc5a7f5343d1c97dc98149a0be7eb9704e937fe3dc7140e229ae4fc572a7"},
    {file = "Pillow-10.1.0-pp310-pypy310_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:b1c25762197144e211efb5f4e8ad656f36c8d214d390585d1d21281f46d556ba"},
    {file = "Pillow-10.1.0-pp310-pypy310_pp73-manylinux_2_28_x86_64.whl", hash = "sha256:afc8eef765d948543a4775f00b7b8c079b3321d6b675dde0d02afa2ee23000b4"},
    {file = "Pillow-10.1.0-pp310-pypy310_pp73-win_amd64.whl", hash = "sha256:883f216eac8712b83a63f41b76ddfb7b2afab1b74abbb413c5df6680f071a6b9"},
    {file = "Pillow-10.1.0-pp39-pypy39_pp73-macosx_10_10_x86_64.whl", hash = "sha256:b920e4d028f6442bea9a75b7491c063f0b9a3972520731ed26c83e254302eb1e"},
    {file = "Pillow-10.1.0-pp39-pypy39_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:1c41d960babf951e01a49c9746f92c5a7e0d939d1652d7ba30f6b3090f27e412"},
    {file = "Pillow-10.1.0-pp39-pypy39_pp73-manylinux_2_28_x86_64.whl", hash = "sha256:1fafabe50a6977ac70dfe829b2d5735fd54e190ab55259ec8aea4aaea412fa0b"},
    {file = "Pillow-10.1.0-pp39-pypy39_pp73-win_amd64.whl", hash = "sha256:3b834f4b16173e5b92ab6566f0473bfb09f939ba14b23b8da1f54fa63e4b623f"},
    {file = "Pillow-10.1.0.tar.gz", hash = "sha256:e6bf8de6c36ed96c86ea3b6e1d5273c53f46ef518a062464cd7ef5dd2cf92e38"},
]

[package.extras]
docs = ["furo", "olefile", "sphinx (>=2.4)", "sphinx-copybutton", "sphinx-inline-tabs", "sphinx-removed-in", "sphinxext-opengraph"]
tests = ["check-manifest", "coverage", "defusedxml", "markdown2", "olefile", "packaging", "pyroma", "pytest", "pytest-cov", "pytest-timeout"]

[[package]]
name = "playwright"
version = "1.39.0"
description = "A high-level API to automate web browsers"
optional = false
python-versions = ">=3.8"
files = [
    {file = "playwright-1.39.0-py3-none-macosx_10_13_x86_64.whl", hash = "sha256:384e195a6d09343f319031cf552e9cd601ede78fe9c082b9fa197537c5cbfe7a"},
    {file = "playwright-1.39.0-py3-none-macosx_11_0_arm64.whl", hash = "sha256:d2c3634411828d9273196ed6f69f2fa7645c89732b3c982dcf09ab03ed4c5d2b"},
    {file = "playwright-1.39.0-py3-none-macosx_11_0_universal2.whl", hash = "sha256:d2fd90f370599cf9a2c6a041bd79a5eeec62baf0e943c7c5c2079b29be476d2a"},
    {file = "playwright-1.39.0-py3-none-manylinux1_x86_64.whl", hash = "sha256:699a8e707ca5f3567aa28223ee1be7e42d2bf25eda7d3d86babda71e36e5f16f"},
    {file = "playwright-1.39.0-py3-none-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:654bb3ae0dc3c69ffddc0c38c127c3b8e93032d8cf3928e2c4f21890cb39514b"},
    {file = "playwright-1.39.0-py3-none-win32.whl", hash = "sha256:40ed7f2546c64f1bb3d22b2295b4d43ed5a2f0b7ea7599d93a72f723a1883e1e"},
    {file = "playwright-1.39.0-py3-none-win_amd64.whl", hash = "sha256:a420d814e21b05e1156747e2a9fae6c3cca2b46bb4a0226fb26ee65538ce09c9"},
]

[package.dependencies]
greenlet = "3.0.0"
pyee = "11.0.1"

[[package]]
name = "proto-plus"
version = "1.23.0"
description = "Beautiful, Pythonic protocol buffers."
optional = false
python-versions = ">=3.6"
files = [
    {file = "proto-plus-1.23.0.tar.gz", hash = "sha256:89075171ef11988b3fa157f5dbd8b9cf09d65fffee97e29ce403cd8defba19d2"},
    {file = "proto_plus-1.23.0-py3-none-any.whl", hash = "sha256:a829c79e619e1cf632de091013a4173deed13a55f326ef84f05af6f50ff4c82c"},
]

[package.dependencies]
protobuf = ">=3.19.0,<5.0.0dev"

[package.extras]
testing = ["google-api-core[grpc] (>=1.31.5)"]

[[package]]
name = "protobuf"
version = "4.25.3"
description = ""
optional = false
python-versions = ">=3.8"
files = [
    {file = "protobuf-4.25.3-cp310-abi3-win32.whl", hash = "sha256:d4198877797a83cbfe9bffa3803602bbe1625dc30d8a097365dbc762e5790faa"},
    {file = "protobuf-4.25.3-cp310-abi3-win_amd64.whl", hash = "sha256:209ba4cc916bab46f64e56b85b090607a676f66b473e6b762e6f1d9d591eb2e8"},
    {file = "protobuf-4.25.3-cp37-abi3-macosx_10_9_universal2.whl", hash = "sha256:f1279ab38ecbfae7e456a108c5c0681e4956d5b1090027c1de0f934dfdb4b35c"},
    {file = "protobuf-4.25.3-cp37-abi3-manylinux2014_aarch64.whl", hash = "sha256:e7cb0ae90dd83727f0c0718634ed56837bfeeee29a5f82a7514c03ee1364c019"},
    {file = "protobuf-4.25.3-cp37-abi3-manylinux2014_x86_64.whl", hash = "sha256:7c8daa26095f82482307bc717364e7c13f4f1c99659be82890dcfc215194554d"},
    {file = "protobuf-4.25.3-cp38-cp38-win32.whl", hash = "sha256:f4f118245c4a087776e0a8408be33cf09f6c547442c00395fbfb116fac2f8ac2"},
    {file = "protobuf-4.25.3-cp38-cp38-win_amd64.whl", hash = "sha256:c053062984e61144385022e53678fbded7aea14ebb3e0305ae3592fb219ccfa4"},
    {file = "protobuf-4.25.3-cp39-cp39-win32.whl", hash = "sha256:19b270aeaa0099f16d3ca02628546b8baefe2955bbe23224aaf856134eccf1e4"},
    {file = "protobuf-4.25.3-cp39-cp39-win_amd64.whl", hash = "sha256:e3c97a1555fd6388f857770ff8b9703083de6bf1f9274a002a332d65fbb56c8c"},
    {file = "protobuf-4.25.3-py3-none-any.whl", hash = "sha256:f0700d54bcf45424477e46a9f0944155b46fb0639d69728739c0e47bab83f2b9"},
    {file = "protobuf-4.25.3.tar.gz", hash = "sha256:25b5d0b42fd000320bd7830b349e3b696435f3b329810427a6bcce6a5492cc5c"},
]

[[package]]
name = "pyasn1"
version = "0.5.1"
description = "Pure-Python implementation of ASN.1 types and DER/BER/CER codecs (X.208)"
optional = false
python-versions = "!=3.0.*,!=3.1.*,!=3.2.*,!=3.3.*,!=3.4.*,!=3.5.*,>=2.7"
files = [
    {file = "pyasn1-0.5.1-py2.py3-none-any.whl", hash = "sha256:4439847c58d40b1d0a573d07e3856e95333f1976294494c325775aeca506eb58"},
    {file = "pyasn1-0.5.1.tar.gz", hash = "sha256:6d391a96e59b23130a5cfa74d6fd7f388dbbe26cc8f1edf39fdddf08d9d6676c"},
]

[[package]]
name = "pyasn1-modules"
version = "0.3.0"
description = "A collection of ASN.1-based protocols modules"
optional = false
python-versions = "!=3.0.*,!=3.1.*,!=3.2.*,!=3.3.*,!=3.4.*,!=3.5.*,>=2.7"
files = [
    {file = "pyasn1_modules-0.3.0-py2.py3-none-any.whl", hash = "sha256:d3ccd6ed470d9ffbc716be08bd90efbd44d0734bc9303818f7336070984a162d"},
    {file = "pyasn1_modules-0.3.0.tar.gz", hash = "sha256:5bd01446b736eb9d31512a30d46c1ac3395d676c6f3cafa4c03eb54b9925631c"},
]

[package.dependencies]
pyasn1 = ">=0.4.6,<0.6.0"

[[package]]
name = "pycparser"
version = "2.21"
description = "C parser in Python"
optional = false
python-versions = ">=2.7, !=3.0.*, !=3.1.*, !=3.2.*, !=3.3.*"
files = [
    {file = "pycparser-2.21-py2.py3-none-any.whl", hash = "sha256:8ee45429555515e1f6b185e78100aea234072576aa43ab53aefcae078162fca9"},
    {file = "pycparser-2.21.tar.gz", hash = "sha256:e644fdec12f7872f86c58ff790da456218b10f863970249516d60a5eaca77206"},
]

[[package]]
name = "pydantic"
version = "2.5.1"
description = "Data validation using Python type hints"
optional = false
python-versions = ">=3.7"
files = [
    {file = "pydantic-2.5.1-py3-none-any.whl", hash = "sha256:dc5244a8939e0d9a68f1f1b5f550b2e1c879912033b1becbedb315accc75441b"},
    {file = "pydantic-2.5.1.tar.gz", hash = "sha256:0b8be5413c06aadfbe56f6dc1d45c9ed25fd43264414c571135c97dd77c2bedb"},
]

[package.dependencies]
annotated-types = ">=0.4.0"
pydantic-core = "2.14.3"
typing-extensions = ">=4.6.1"

[package.extras]
email = ["email-validator (>=2.0.0)"]

[[package]]
name = "pydantic-core"
version = "2.14.3"
description = ""
optional = false
python-versions = ">=3.7"
files = [
    {file = "pydantic_core-2.14.3-cp310-cp310-macosx_10_7_x86_64.whl", hash = "sha256:ba44fad1d114539d6a1509966b20b74d2dec9a5b0ee12dd7fd0a1bb7b8785e5f"},
    {file = "pydantic_core-2.14.3-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:4a70d23eedd88a6484aa79a732a90e36701048a1509078d1b59578ef0ea2cdf5"},
    {file = "pydantic_core-2.14.3-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:7cc24728a1a9cef497697e53b3d085fb4d3bc0ef1ef4d9b424d9cf808f52c146"},
    {file = "pydantic_core-2.14.3-cp310-cp310-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:ab4a2381005769a4af2ffddae74d769e8a4aae42e970596208ec6d615c6fb080"},
    {file = "pydantic_core-2.14.3-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:905a12bf088d6fa20e094f9a477bf84bd823651d8b8384f59bcd50eaa92e6a52"},
    {file = "pydantic_core-2.14.3-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:38aed5a1bbc3025859f56d6a32f6e53ca173283cb95348e03480f333b1091e7d"},
    {file = "pydantic_core-2.14.3-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:1767bd3f6370458e60c1d3d7b1d9c2751cc1ad743434e8ec84625a610c8b9195"},
    {file = "pydantic_core-2.14.3-cp310-cp310-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:7cb0c397f29688a5bd2c0dbd44451bc44ebb9b22babc90f97db5ec3e5bb69977"},
    {file = "pydantic_core-2.14.3-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:9ff737f24b34ed26de62d481ef522f233d3c5927279f6b7229de9b0deb3f76b5"},
    {file = "pydantic_core-2.14.3-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:a1a39fecb5f0b19faee9a8a8176c805ed78ce45d760259a4ff3d21a7daa4dfc1"},
    {file = "pydantic_core-2.14.3-cp310-none-win32.whl", hash = "sha256:ccbf355b7276593c68fa824030e68cb29f630c50e20cb11ebb0ee450ae6b3d08"},
    {file = "pydantic_core-2.14.3-cp310-none-win_amd64.whl", hash = "sha256:536e1f58419e1ec35f6d1310c88496f0d60e4f182cacb773d38076f66a60b149"},
    {file = "pydantic_core-2.14.3-cp311-cp311-macosx_10_7_x86_64.whl", hash = "sha256:f1f46700402312bdc31912f6fc17f5ecaaaa3bafe5487c48f07c800052736289"},
    {file = "pydantic_core-2.14.3-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:88ec906eb2d92420f5b074f59cf9e50b3bb44f3cb70e6512099fdd4d88c2f87c"},
    {file = "pydantic_core-2.14.3-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:056ea7cc3c92a7d2a14b5bc9c9fa14efa794d9f05b9794206d089d06d3433dc7"},
    {file = "pydantic_core-2.14.3-cp311-cp311-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:076edc972b68a66870cec41a4efdd72a6b655c4098a232314b02d2bfa3bfa157"},
    {file = "pydantic_core-2.14.3-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:e71f666c3bf019f2490a47dddb44c3ccea2e69ac882f7495c68dc14d4065eac2"},
    {file = "pydantic_core-2.14.3-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:f518eac285c9632be337323eef9824a856f2680f943a9b68ac41d5f5bad7df7c"},
    {file = "pydantic_core-2.14.3-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:9dbab442a8d9ca918b4ed99db8d89d11b1f067a7dadb642476ad0889560dac79"},
    {file = "pydantic_core-2.14.3-cp311-cp311-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:0653fb9fc2fa6787f2fa08631314ab7fc8070307bd344bf9471d1b7207c24623"},
    {file = "pydantic_core-2.14.3-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:c54af5069da58ea643ad34ff32fd6bc4eebb8ae0fef9821cd8919063e0aeeaab"},
    {file = "pydantic_core-2.14.3-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:cc956f78651778ec1ab105196e90e0e5f5275884793ab67c60938c75bcca3989"},
    {file = "pydantic_core-2.14.3-cp311-none-win32.whl", hash = "sha256:5b73441a1159f1fb37353aaefb9e801ab35a07dd93cb8177504b25a317f4215a"},
    {file = "pydantic_core-2.14.3-cp311-none-win_amd64.whl", hash = "sha256:7349f99f1ef8b940b309179733f2cad2e6037a29560f1b03fdc6aa6be0a8d03c"},
    {file = "pydantic_core-2.14.3-cp311-none-win_arm64.whl", hash = "sha256:ec79dbe23702795944d2ae4c6925e35a075b88acd0d20acde7c77a817ebbce94"},
    {file = "pydantic_core-2.14.3-cp312-cp312-macosx_10_7_x86_64.whl", hash = "sha256:8f5624f0f67f2b9ecaa812e1dfd2e35b256487566585160c6c19268bf2ffeccc"},
    {file = "pydantic_core-2.14.3-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:6c2d118d1b6c9e2d577e215567eedbe11804c3aafa76d39ec1f8bc74e918fd07"},
    {file = "pydantic_core-2.14.3-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:fe863491664c6720d65ae438d4efaa5eca766565a53adb53bf14bc3246c72fe0"},
    {file = "pydantic_core-2.14.3-cp312-cp312-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:136bc7247e97a921a020abbd6ef3169af97569869cd6eff41b6a15a73c44ea9b"},
    {file = "pydantic_core-2.14.3-cp312-cp312-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:aeafc7f5bbddc46213707266cadc94439bfa87ecf699444de8be044d6d6eb26f"},
    {file = "pydantic_core-2.14.3-cp312-cp312-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:e16aaf788f1de5a85c8f8fcc9c1ca1dd7dd52b8ad30a7889ca31c7c7606615b8"},
    {file = "pydantic_core-2.14.3-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:f8fc652c354d3362e2932a79d5ac4bbd7170757a41a62c4fe0f057d29f10bebb"},
    {file = "pydantic_core-2.14.3-cp312-cp312-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:f1b92e72babfd56585c75caf44f0b15258c58e6be23bc33f90885cebffde3400"},
    {file = "pydantic_core-2.14.3-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:75f3f534f33651b73f4d3a16d0254de096f43737d51e981478d580f4b006b427"},
    {file = "pydantic_core-2.14.3-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:c9ffd823c46e05ef3eb28b821aa7bc501efa95ba8880b4a1380068e32c5bed47"},
    {file = "pydantic_core-2.14.3-cp312-none-win32.whl", hash = "sha256:12e05a76b223577a4696c76d7a6b36a0ccc491ffb3c6a8cf92d8001d93ddfd63"},
    {file = "pydantic_core-2.14.3-cp312-none-win_amd64.whl", hash = "sha256:1582f01eaf0537a696c846bea92082082b6bfc1103a88e777e983ea9fbdc2a0f"},
    {file = "pydantic_core-2.14.3-cp312-none-win_arm64.whl", hash = "sha256:96fb679c7ca12a512d36d01c174a4fbfd912b5535cc722eb2c010c7b44eceb8e"},
    {file = "pydantic_core-2.14.3-cp37-cp37m-macosx_10_7_x86_64.whl", hash = "sha256:71ed769b58d44e0bc2701aa59eb199b6665c16e8a5b8b4a84db01f71580ec448"},
    {file = "pydantic_core-2.14.3-cp37-cp37m-macosx_11_0_arm64.whl", hash = "sha256:5402ee0f61e7798ea93a01b0489520f2abfd9b57b76b82c93714c4318c66ca06"},
    {file = "pydantic_core-2.14.3-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:eaab9dc009e22726c62fe3b850b797e7f0e7ba76d245284d1064081f512c7226"},
    {file = "pydantic_core-2.14.3-cp37-cp37m-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:92486a04d54987054f8b4405a9af9d482e5100d6fe6374fc3303015983fc8bda"},
    {file = "pydantic_core-2.14.3-cp37-cp37m-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:cf08b43d1d5d1678f295f0431a4a7e1707d4652576e1d0f8914b5e0213bfeee5"},
    {file = "pydantic_core-2.14.3-cp37-cp37m-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:a8ca13480ce16daad0504be6ce893b0ee8ec34cd43b993b754198a89e2787f7e"},
    {file = "pydantic_core-2.14.3-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:44afa3c18d45053fe8d8228950ee4c8eaf3b5a7f3b64963fdeac19b8342c987f"},
    {file = "pydantic_core-2.14.3-cp37-cp37m-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:56814b41486e2d712a8bc02a7b1f17b87fa30999d2323bbd13cf0e52296813a1"},
    {file = "pydantic_core-2.14.3-cp37-cp37m-musllinux_1_1_aarch64.whl", hash = "sha256:c3dc2920cc96f9aa40c6dc54256e436cc95c0a15562eb7bd579e1811593c377e"},
    {file = "pydantic_core-2.14.3-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:e483b8b913fcd3b48badec54185c150cb7ab0e6487914b84dc7cde2365e0c892"},
    {file = "pydantic_core-2.14.3-cp37-none-win32.whl", hash = "sha256:364dba61494e48f01ef50ae430e392f67ee1ee27e048daeda0e9d21c3ab2d609"},
    {file = "pydantic_core-2.14.3-cp37-none-win_amd64.whl", hash = "sha256:a402ae1066be594701ac45661278dc4a466fb684258d1a2c434de54971b006ca"},
    {file = "pydantic_core-2.14.3-cp38-cp38-macosx_10_7_x86_64.whl", hash = "sha256:10904368261e4509c091cbcc067e5a88b070ed9a10f7ad78f3029c175487490f"},
    {file = "pydantic_core-2.14.3-cp38-cp38-macosx_11_0_arm64.whl", hash = "sha256:260692420028319e201b8649b13ac0988974eeafaaef95d0dfbf7120c38dc000"},
    {file = "pydantic_core-2.14.3-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:3c1bf1a7b05a65d3b37a9adea98e195e0081be6b17ca03a86f92aeb8b110f468"},
    {file = "pydantic_core-2.14.3-cp38-cp38-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:d7abd17a838a52140e3aeca271054e321226f52df7e0a9f0da8f91ea123afe98"},
    {file = "pydantic_core-2.14.3-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:a5c51460ede609fbb4fa883a8fe16e749964ddb459966d0518991ec02eb8dfb9"},
    {file = "pydantic_core-2.14.3-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:d06c78074646111fb01836585f1198367b17d57c9f427e07aaa9ff499003e58d"},
    {file = "pydantic_core-2.14.3-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:af452e69446fadf247f18ac5d153b1f7e61ef708f23ce85d8c52833748c58075"},
    {file = "pydantic_core-2.14.3-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:e3ad4968711fb379a67c8c755beb4dae8b721a83737737b7bcee27c05400b047"},
    {file = "pydantic_core-2.14.3-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:c5ea0153482e5b4d601c25465771c7267c99fddf5d3f3bdc238ef930e6d051cf"},
    {file = "pydantic_core-2.14.3-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:96eb10ef8920990e703da348bb25fedb8b8653b5966e4e078e5be382b430f9e0"},
    {file = "pydantic_core-2.14.3-cp38-none-win32.whl", hash = "sha256:ea1498ce4491236d1cffa0eee9ad0968b6ecb0c1cd711699c5677fc689905f00"},
    {file = "pydantic_core-2.14.3-cp38-none-win_amd64.whl", hash = "sha256:2bc736725f9bd18a60eec0ed6ef9b06b9785454c8d0105f2be16e4d6274e63d0"},
    {file = "pydantic_core-2.14.3-cp39-cp39-macosx_10_7_x86_64.whl", hash = "sha256:1ea992659c03c3ea811d55fc0a997bec9dde863a617cc7b25cfde69ef32e55af"},
    {file = "pydantic_core-2.14.3-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:d2b53e1f851a2b406bbb5ac58e16c4a5496038eddd856cc900278fa0da97f3fc"},
    {file = "pydantic_core-2.14.3-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:0c7f8e8a7cf8e81ca7d44bea4f181783630959d41b4b51d2f74bc50f348a090f"},
    {file = "pydantic_core-2.14.3-cp39-cp39-manylinux_2_17_armv7l.manylinux2014_armv7l.whl", hash = "sha256:8d3b9c91eeb372a64ec6686c1402afd40cc20f61a0866850f7d989b6bf39a41a"},
    {file = "pydantic_core-2.14.3-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:9ef3e2e407e4cad2df3c89488a761ed1f1c33f3b826a2ea9a411b0a7d1cccf1b"},
    {file = "pydantic_core-2.14.3-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:f86f20a9d5bee1a6ede0f2757b917bac6908cde0f5ad9fcb3606db1e2968bcf5"},
    {file = "pydantic_core-2.14.3-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:61beaa79d392d44dc19d6f11ccd824d3cccb865c4372157c40b92533f8d76dd0"},
    {file = "pydantic_core-2.14.3-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:d41df8e10b094640a6b234851b624b76a41552f637b9fb34dc720b9fe4ef3be4"},
    {file = "pydantic_core-2.14.3-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:2c08ac60c3caa31f825b5dbac47e4875bd4954d8f559650ad9e0b225eaf8ed0c"},
    {file = "pydantic_core-2.14.3-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:98d8b3932f1a369364606417ded5412c4ffb15bedbcf797c31317e55bd5d920e"},
    {file = "pydantic_core-2.14.3-cp39-none-win32.whl", hash = "sha256:caa94726791e316f0f63049ee00dff3b34a629b0d099f3b594770f7d0d8f1f56"},
    {file = "pydantic_core-2.14.3-cp39-none-win_amd64.whl", hash = "sha256:2494d20e4c22beac30150b4be3b8339bf2a02ab5580fa6553ca274bc08681a65"},
    {file = "pydantic_core-2.14.3-pp310-pypy310_pp73-macosx_10_7_x86_64.whl", hash = "sha256:fe272a72c7ed29f84c42fedd2d06c2f9858dc0c00dae3b34ba15d6d8ae0fbaaf"},
    {file = "pydantic_core-2.14.3-pp310-pypy310_pp73-macosx_11_0_arm64.whl", hash = "sha256:7e63a56eb7fdee1587d62f753ccd6d5fa24fbeea57a40d9d8beaef679a24bdd6"},
    {file = "pydantic_core-2.14.3-pp310-pypy310_pp73-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:b7692f539a26265cece1e27e366df5b976a6db6b1f825a9e0466395b314ee48b"},
    {file = "pydantic_core-2.14.3-pp310-pypy310_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:af46f0b7a1342b49f208fed31f5a83b8495bb14b652f621e0a6787d2f10f24ee"},
    {file = "pydantic_core-2.14.3-pp310-pypy310_pp73-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:6e2f9d76c00e805d47f19c7a96a14e4135238a7551a18bfd89bb757993fd0933"},
    {file = "pydantic_core-2.14.3-pp310-pypy310_pp73-musllinux_1_1_aarch64.whl", hash = "sha256:de52ddfa6e10e892d00f747bf7135d7007302ad82e243cf16d89dd77b03b649d"},
    {file = "pydantic_core-2.14.3-pp310-pypy310_pp73-musllinux_1_1_x86_64.whl", hash = "sha256:38113856c7fad8c19be7ddd57df0c3e77b1b2336459cb03ee3903ce9d5e236ce"},
    {file = "pydantic_core-2.14.3-pp310-pypy310_pp73-win_amd64.whl", hash = "sha256:354db020b1f8f11207b35360b92d95725621eb92656725c849a61e4b550f4acc"},
    {file = "pydantic_core-2.14.3-pp37-pypy37_pp73-macosx_10_7_x86_64.whl", hash = "sha256:76fc18653a5c95e5301a52d1b5afb27c9adc77175bf00f73e94f501caf0e05ad"},
    {file = "pydantic_core-2.14.3-pp37-pypy37_pp73-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:2646f8270f932d79ba61102a15ea19a50ae0d43b314e22b3f8f4b5fabbfa6e38"},
    {file = "pydantic_core-2.14.3-pp37-pypy37_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:37dad73a2f82975ed563d6a277fd9b50e5d9c79910c4aec787e2d63547202315"},
    {file = "pydantic_core-2.14.3-pp37-pypy37_pp73-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:113752a55a8eaece2e4ac96bc8817f134c2c23477e477d085ba89e3aa0f4dc44"},
    {file = "pydantic_core-2.14.3-pp37-pypy37_pp73-musllinux_1_1_aarch64.whl", hash = "sha256:8488e973547e8fb1b4193fd9faf5236cf1b7cd5e9e6dc7ff6b4d9afdc4c720cb"},
    {file = "pydantic_core-2.14.3-pp37-pypy37_pp73-musllinux_1_1_x86_64.whl", hash = "sha256:3d1dde10bd9962b1434053239b1d5490fc31a2b02d8950a5f731bc584c7a5a0f"},
    {file = "pydantic_core-2.14.3-pp38-pypy38_pp73-macosx_10_7_x86_64.whl", hash = "sha256:2c83892c7bf92b91d30faca53bb8ea21f9d7e39f0ae4008ef2c2f91116d0464a"},
    {file = "pydantic_core-2.14.3-pp38-pypy38_pp73-macosx_11_0_arm64.whl", hash = "sha256:849cff945284c577c5f621d2df76ca7b60f803cc8663ff01b778ad0af0e39bb9"},
    {file = "pydantic_core-2.14.3-pp38-pypy38_pp73-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:4aa89919fbd8a553cd7d03bf23d5bc5deee622e1b5db572121287f0e64979476"},
    {file = "pydantic_core-2.14.3-pp38-pypy38_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:bf15145b1f8056d12c67255cd3ce5d317cd4450d5ee747760d8d088d85d12a2d"},
    {file = "pydantic_core-2.14.3-pp38-pypy38_pp73-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:4cc6bb11f4e8e5ed91d78b9880774fbc0856cb226151b0a93b549c2b26a00c19"},
    {file = "pydantic_core-2.14.3-pp38-pypy38_pp73-musllinux_1_1_aarch64.whl", hash = "sha256:832d16f248ca0cc96929139734ec32d21c67669dcf8a9f3f733c85054429c012"},
    {file = "pydantic_core-2.14.3-pp38-pypy38_pp73-musllinux_1_1_x86_64.whl", hash = "sha256:b02b5e1f54c3396c48b665050464803c23c685716eb5d82a1d81bf81b5230da4"},
    {file = "pydantic_core-2.14.3-pp38-pypy38_pp73-win_amd64.whl", hash = "sha256:1f2d4516c32255782153e858f9a900ca6deadfb217fd3fb21bb2b60b4e04d04d"},
    {file = "pydantic_core-2.14.3-pp39-pypy39_pp73-macosx_10_7_x86_64.whl", hash = "sha256:0a3e51c2be472b7867eb0c5d025b91400c2b73a0823b89d4303a9097e2ec6655"},
    {file = "pydantic_core-2.14.3-pp39-pypy39_pp73-macosx_11_0_arm64.whl", hash = "sha256:df33902464410a1f1a0411a235f0a34e7e129f12cb6340daca0f9d1390f5fe10"},
    {file = "pydantic_core-2.14.3-pp39-pypy39_pp73-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:27828f0227b54804aac6fb077b6bb48e640b5435fdd7fbf0c274093a7b78b69c"},
    {file = "pydantic_core-2.14.3-pp39-pypy39_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:1e2979dc80246e18e348de51246d4c9b410186ffa3c50e77924bec436b1e36cb"},
    {file = "pydantic_core-2.14.3-pp39-pypy39_pp73-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:b28996872b48baf829ee75fa06998b607c66a4847ac838e6fd7473a6b2ab68e7"},
    {file = "pydantic_core-2.14.3-pp39-pypy39_pp73-musllinux_1_1_aarch64.whl", hash = "sha256:ca55c9671bb637ce13d18ef352fd32ae7aba21b4402f300a63f1fb1fd18e0364"},
    {file = "pydantic_core-2.14.3-pp39-pypy39_pp73-musllinux_1_1_x86_64.whl", hash = "sha256:aecd5ed096b0e5d93fb0367fd8f417cef38ea30b786f2501f6c34eabd9062c38"},
    {file = "pydantic_core-2.14.3-pp39-pypy39_pp73-win_amd64.whl", hash = "sha256:44aaf1a07ad0824e407dafc637a852e9a44d94664293bbe7d8ee549c356c8882"},
    {file = "pydantic_core-2.14.3.tar.gz", hash = "sha256:3ad083df8fe342d4d8d00cc1d3c1a23f0dc84fce416eb301e69f1ddbbe124d3f"},
]

[package.dependencies]
typing-extensions = ">=4.6.0,<4.7.0 || >4.7.0"

[[package]]
name = "pydyf"
version = "0.8.0"
description = "A low-level PDF generator."
optional = false
python-versions = ">=3.7"
files = [
    {file = "pydyf-0.8.0-py3-none-any.whl", hash = "sha256:901186a2e9f897108139426a6486f5225bdcc9b70be2ec965f25111e42f8ac5d"},
    {file = "pydyf-0.8.0.tar.gz", hash = "sha256:b22b1ef016141b54941ad66ed4e036a7bdff39c0b360993b283875c3f854dd9a"},
]

[package.extras]
doc = ["sphinx", "sphinx_rtd_theme"]
test = ["flake8", "isort", "pillow", "pytest"]

[[package]]
name = "pyee"
version = "11.0.1"
description = "A rough port of Node.js's EventEmitter to Python with a few tricks of its own"
optional = false
python-versions = ">=3.8"
files = [
    {file = "pyee-11.0.1-py3-none-any.whl", hash = "sha256:9bcc9647822234f42c228d88de63d0f9ffa881e87a87f9d36ddf5211f6ac977d"},
    {file = "pyee-11.0.1.tar.gz", hash = "sha256:a642c51e3885a33ead087286e35212783a4e9b8d6514a10a5db4e57ac57b2b29"},
]

[package.dependencies]
typing-extensions = "*"

[package.extras]
dev = ["black", "flake8", "flake8-black", "isort", "jupyter-console", "mkdocs", "mkdocs-include-markdown-plugin", "mkdocstrings[python]", "pytest", "pytest-asyncio", "pytest-trio", "toml", "tox", "trio", "trio", "trio-typing", "twine", "twisted", "validate-pyproject[all]"]

[[package]]
name = "pymupdf"
version = "1.23.6"
description = "A high performance Python library for data extraction, analysis, conversion & manipulation of PDF (and other) documents."
optional = false
python-versions = ">=3.8"
files = [
    {file = "PyMuPDF-1.23.6-cp310-none-macosx_10_9_x86_64.whl", hash = "sha256:c4eb71b88a22c1008f764b3121b36a9d25340f9920b870508356050a365d9ca1"},
    {file = "PyMuPDF-1.23.6-cp310-none-macosx_11_0_arm64.whl", hash = "sha256:3ce2d3678dbf822cff213b1902f2e59756313e543efd516a2b4f15bb0353bd6c"},
    {file = "PyMuPDF-1.23.6-cp310-none-manylinux2014_aarch64.whl", hash = "sha256:2e27857a15c8a810d0b66455b8c8a79013640b6267a9b4ea808a5fe1f47711f2"},
    {file = "PyMuPDF-1.23.6-cp310-none-manylinux2014_x86_64.whl", hash = "sha256:5cd05700c8f18c9dafef63ac2ed3b1099ca06017ca0c32deea13093cea1b8671"},
    {file = "PyMuPDF-1.23.6-cp310-none-win32.whl", hash = "sha256:951d280c1daafac2fd6a664b031f7f98b27eb2def55d39c92a19087bd8041c5d"},
    {file = "PyMuPDF-1.23.6-cp310-none-win_amd64.whl", hash = "sha256:19d1711d5908c4527ad2deef5af2d066649f3f9a12950faf30be5f7251d18abc"},
    {file = "PyMuPDF-1.23.6-cp311-none-macosx_10_9_x86_64.whl", hash = "sha256:3f0f9b76bc4f039e7587003cbd40684d93a98441549dd033cab38ca07d61988d"},
    {file = "PyMuPDF-1.23.6-cp311-none-macosx_11_0_arm64.whl", hash = "sha256:e047571d799b30459ad7ee0bc6e68900a7f6b928876f956c976f279808814e72"},
    {file = "PyMuPDF-1.23.6-cp311-none-manylinux2014_aarch64.whl", hash = "sha256:1cbcf05c06f314fdf3042ceee674e9a0ac7fae598347d5442e2138c6046d4e82"},
    {file = "PyMuPDF-1.23.6-cp311-none-manylinux2014_x86_64.whl", hash = "sha256:e33f8ec5ba7265fe78b30332840b8f454184addfa79f9c27f160f19789aa5ffd"},
    {file = "PyMuPDF-1.23.6-cp311-none-win32.whl", hash = "sha256:2c141f33e2733e48de8524dfd2de56d889feef0c7773b20a8cd216c03ab24793"},
    {file = "PyMuPDF-1.23.6-cp311-none-win_amd64.whl", hash = "sha256:8fd9c4ee1dd4744a515b9190d8ba9133348b0d94c362293ed77726aa1c13b0a6"},
    {file = "PyMuPDF-1.23.6-cp312-none-macosx_10_9_x86_64.whl", hash = "sha256:4d06751d5cd213e96f84f2faaa71a51cf4d641851e07579247ca1190121f173b"},
    {file = "PyMuPDF-1.23.6-cp312-none-macosx_11_0_arm64.whl", hash = "sha256:526b26a5207e923aab65877ad305644402851823a352cb92d362053426899354"},
    {file = "PyMuPDF-1.23.6-cp312-none-manylinux2014_aarch64.whl", hash = "sha256:0f852d125defc26716878b1796f4d68870e9065041d00cf46bde317fd8d30e68"},
    {file = "PyMuPDF-1.23.6-cp312-none-manylinux2014_x86_64.whl", hash = "sha256:5bdf7020b90987412381acc42427dd1b7a03d771ee9ec273de003e570164ec1a"},
    {file = "PyMuPDF-1.23.6-cp312-none-win32.whl", hash = "sha256:e2d64799c6d9a3735be9e162a5d11061c0b7fbcb1e5fc7446e0993d0f815a93a"},
    {file = "PyMuPDF-1.23.6-cp312-none-win_amd64.whl", hash = "sha256:c8ea81964c1433ea163ad4b53c56053a87a9ef6e1bd7a879d4d368a3988b60d1"},
    {file = "PyMuPDF-1.23.6-cp38-none-macosx_10_9_x86_64.whl", hash = "sha256:761501a4965264e81acdd8f2224f993020bf24474e9b34fcdb5805a6826eda1c"},
    {file = "PyMuPDF-1.23.6-cp38-none-macosx_11_0_arm64.whl", hash = "sha256:fd8388e82b6045807d19addf310d8119d32908e89f76cc8bbf8cf1ec36fce947"},
    {file = "PyMuPDF-1.23.6-cp38-none-manylinux2014_aarch64.whl", hash = "sha256:4ac9673a6d6ee7e80cb242dacb43f9ca097b502d9c5e44687dbdffc2bce7961a"},
    {file = "PyMuPDF-1.23.6-cp38-none-manylinux2014_x86_64.whl", hash = "sha256:6e319c1f49476e07b9a12017c2d031687617713f8a46b7adcec03c636ed04607"},
    {file = "PyMuPDF-1.23.6-cp38-none-win32.whl", hash = "sha256:1103eea4ab727e32b9cb93347b35f71562033018c333a7f3a17d115e980fea4a"},
    {file = "PyMuPDF-1.23.6-cp38-none-win_amd64.whl", hash = "sha256:991a37e1cba43775ce094da87cf0bf72172a5532a09644003276bc8bfdfe9f1a"},
    {file = "PyMuPDF-1.23.6-cp39-none-macosx_10_9_x86_64.whl", hash = "sha256:57725e15872f7ab67a9fb3e06e5384d1047b2121e85755c93a6d4266d3ca8983"},
    {file = "PyMuPDF-1.23.6-cp39-none-macosx_11_0_arm64.whl", hash = "sha256:224c341fe254adda97c8f06a4c5838cdbcf609fa89e70b1fb179752533378f2f"},
    {file = "PyMuPDF-1.23.6-cp39-none-manylinux2014_aarch64.whl", hash = "sha256:271bdf6059bb8347f9c9c6b721329bd353a933681b1fc62f43241b410e7ab7ae"},
    {file = "PyMuPDF-1.23.6-cp39-none-manylinux2014_x86_64.whl", hash = "sha256:57e22bea69690450197b34dcde16bd9fe0265ac4425b4033535ccc5c044246fb"},
    {file = "PyMuPDF-1.23.6-cp39-none-win32.whl", hash = "sha256:2885a26220a32fb45ea443443b72194bb7107d6862d8d546b59e4ad0c8a1f2c9"},
    {file = "PyMuPDF-1.23.6-cp39-none-win_amd64.whl", hash = "sha256:361cab1be45481bd3dc4e00ec82628ebc189b4f4b6fd9bd78a00cfeed54e0034"},
    {file = "PyMuPDF-1.23.6.tar.gz", hash = "sha256:618b8e884190ac1cca9df1c637f87669d2d532d421d4ee7e4763c848dc4f3a1e"},
]

[package.dependencies]
PyMuPDFb = "1.23.6"

[[package]]
name = "pymupdfb"
version = "1.23.6"
description = "MuPDF shared libraries for PyMuPDF."
optional = false
python-versions = ">=3.8"
files = [
    {file = "PyMuPDFb-1.23.6-py3-none-macosx_10_9_x86_64.whl", hash = "sha256:e5af77580aad3d1103aeec57009d156bfca429cecda14a17c573fcbe97bafb30"},
    {file = "PyMuPDFb-1.23.6-py3-none-macosx_11_0_arm64.whl", hash = "sha256:9925816cbe3e05e920f9be925e5752c2eef42b793885b62075bb0f6a69178598"},
    {file = "PyMuPDFb-1.23.6-py3-none-manylinux2014_aarch64.manylinux_2_17_aarch64.whl", hash = "sha256:009e2cff166059e13bf71f93919e688f46b8fc11d122433574cfb0cc9134690e"},
    {file = "PyMuPDFb-1.23.6-py3-none-manylinux2014_x86_64.manylinux_2_17_x86_64.whl", hash = "sha256:7132b30e6ad6ff2013344e3a481b2287fe0be3710d80694807dd6e0d8635f085"},
    {file = "PyMuPDFb-1.23.6-py3-none-win32.whl", hash = "sha256:9d24ddadc204e895bee5000ddc7507c801643548e59f5a56aad6d32981d17eeb"},
    {file = "PyMuPDFb-1.23.6-py3-none-win_amd64.whl", hash = "sha256:7bef75988e6979b10ca804cf9487f817aae43b0fff1c6e315b3b9ee0cf1cc32f"},
]

[[package]]
name = "pyphen"
version = "0.14.0"
description = "Pure Python module to hyphenate text"
optional = false
python-versions = ">=3.7"
files = [
    {file = "pyphen-0.14.0-py3-none-any.whl", hash = "sha256:414c9355958ca3c6a3ff233f65678c245b8ecb56418fb291e2b93499d61cd510"},
    {file = "pyphen-0.14.0.tar.gz", hash = "sha256:596c8b3be1c1a70411ba5f6517d9ccfe3083c758ae2b94a45f2707346d8e66fa"},
]

[package.extras]
doc = ["sphinx", "sphinx_rtd_theme"]
test = ["flake8", "isort", "pytest"]

[[package]]
name = "pysocks"
version = "1.7.1"
description = "A Python SOCKS client module. See https://github.com/Anorov/PySocks for more information."
optional = false
python-versions = ">=2.7, !=3.0.*, !=3.1.*, !=3.2.*, !=3.3.*"
files = [
    {file = "PySocks-1.7.1-py27-none-any.whl", hash = "sha256:08e69f092cc6dbe92a0fdd16eeb9b9ffbc13cadfe5ca4c7bd92ffb078b293299"},
    {file = "PySocks-1.7.1-py3-none-any.whl", hash = "sha256:2725bd0a9925919b9b51739eea5f9e2bae91e83288108a9ad338b2e3a4435ee5"},
    {file = "PySocks-1.7.1.tar.gz", hash = "sha256:3f8804571ebe159c380ac6de37643bb4685970655d3bba243530d6558b799aa0"},
]

[[package]]
name = "python-dateutil"
version = "2.9.0.post0"
description = "Extensions to the standard Python datetime module"
optional = false
python-versions = "!=3.0.*,!=3.1.*,!=3.2.*,>=2.7"
files = [
    {file = "python-dateutil-2.9.0.post0.tar.gz", hash = "sha256:37dd54208da7e1cd875388217d5e00ebd4179249f90fb72437e91a35459a0ad3"},
    {file = "python_dateutil-2.9.0.post0-py2.py3-none-any.whl", hash = "sha256:a8b2bc7bffae282281c8140a97d3aa9c14da0b136dfe83f850eea9a5f7470427"},
]

[package.dependencies]
six = ">=1.5"

[[package]]
name = "python-docx"
version = "1.1.0"
description = "Create, read, and update Microsoft Word .docx files."
optional = false
python-versions = ">=3.7"
files = [
    {file = "python-docx-1.1.0.tar.gz", hash = "sha256:5829b722141cf1ab79aedf0c34d9fe9924b29764584c0f2164eb2b02dcdf17c9"},
    {file = "python_docx-1.1.0-py3-none-any.whl", hash = "sha256:bac9773278098a1ddc43a52d84e22f5909c4a3080a624530b3ecb3771b07c6cd"},
]

[package.dependencies]
lxml = ">=3.1.0"
typing-extensions = "*"

[[package]]
name = "python-dotenv"
version = "1.0.0"
description = "Read key-value pairs from a .env file and set them as environment variables"
optional = false
python-versions = ">=3.8"
files = [
    {file = "python-dotenv-1.0.0.tar.gz", hash = "sha256:a8df96034aae6d2d50a4ebe8216326c61c3eb64836776504fcca410e5937a3ba"},
    {file = "python_dotenv-1.0.0-py3-none-any.whl", hash = "sha256:f5971a9226b701070a4bf2c38c89e5a3f0d64de8debda981d1db98583009122a"},
]

[package.extras]
cli = ["click (>=5.0)"]

[[package]]
name = "python-multipart"
version = "0.0.6"
description = "A streaming multipart parser for Python"
optional = false
python-versions = ">=3.7"
files = [
    {file = "python_multipart-0.0.6-py3-none-any.whl", hash = "sha256:ee698bab5ef148b0a760751c261902cd096e57e10558e11aca17646b74ee1c18"},
    {file = "python_multipart-0.0.6.tar.gz", hash = "sha256:e9925a80bb668529f1b67c7fdb0a5dacdd7cbfc6fb0bff3ea443fe22bdd62132"},
]

[package.extras]
dev = ["atomicwrites (==1.2.1)", "attrs (==19.2.0)", "coverage (==6.5.0)", "hatch", "invoke (==1.7.3)", "more-itertools (==4.3.0)", "pbr (==4.3.0)", "pluggy (==1.0.0)", "py (==1.11.0)", "pytest (==7.2.0)", "pytest-cov (==4.0.0)", "pytest-timeout (==2.1.0)", "pyyaml (==5.1)"]

[[package]]
name = "pyyaml"
version = "6.0.1"
description = "YAML parser and emitter for Python"
optional = false
python-versions = ">=3.6"
files = [
    {file = "PyYAML-6.0.1-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:d858aa552c999bc8a8d57426ed01e40bef403cd8ccdd0fc5f6f04a00414cac2a"},
    {file = "PyYAML-6.0.1-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:fd66fc5d0da6d9815ba2cebeb4205f95818ff4b79c3ebe268e75d961704af52f"},
    {file = "PyYAML-6.0.1-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:69b023b2b4daa7548bcfbd4aa3da05b3a74b772db9e23b982788168117739938"},
    {file = "PyYAML-6.0.1-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:81e0b275a9ecc9c0c0c07b4b90ba548307583c125f54d5b6946cfee6360c733d"},
    {file = "PyYAML-6.0.1-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:ba336e390cd8e4d1739f42dfe9bb83a3cc2e80f567d8805e11b46f4a943f5515"},
    {file = "PyYAML-6.0.1-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:326c013efe8048858a6d312ddd31d56e468118ad4cdeda36c719bf5bb6192290"},
    {file = "PyYAML-6.0.1-cp310-cp310-win32.whl", hash = "sha256:bd4af7373a854424dabd882decdc5579653d7868b8fb26dc7d0e99f823aa5924"},
    {file = "PyYAML-6.0.1-cp310-cp310-win_amd64.whl", hash = "sha256:fd1592b3fdf65fff2ad0004b5e363300ef59ced41c2e6b3a99d4089fa8c5435d"},
    {file = "PyYAML-6.0.1-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:6965a7bc3cf88e5a1c3bd2e0b5c22f8d677dc88a455344035f03399034eb3007"},
    {file = "PyYAML-6.0.1-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:f003ed9ad21d6a4713f0a9b5a7a0a79e08dd0f221aff4525a2be4c346ee60aab"},
    {file = "PyYAML-6.0.1-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:42f8152b8dbc4fe7d96729ec2b99c7097d656dc1213a3229ca5383f973a5ed6d"},
    {file = "PyYAML-6.0.1-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:062582fca9fabdd2c8b54a3ef1c978d786e0f6b3a1510e0ac93ef59e0ddae2bc"},
    {file = "PyYAML-6.0.1-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:d2b04aac4d386b172d5b9692e2d2da8de7bfb6c387fa4f801fbf6fb2e6ba4673"},
    {file = "PyYAML-6.0.1-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:e7d73685e87afe9f3b36c799222440d6cf362062f78be1013661b00c5c6f678b"},
    {file = "PyYAML-6.0.1-cp311-cp311-win32.whl", hash = "sha256:1635fd110e8d85d55237ab316b5b011de701ea0f29d07611174a1b42f1444741"},
    {file = "PyYAML-6.0.1-cp311-cp311-win_amd64.whl", hash = "sha256:bf07ee2fef7014951eeb99f56f39c9bb4af143d8aa3c21b1677805985307da34"},
    {file = "PyYAML-6.0.1-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:855fb52b0dc35af121542a76b9a84f8d1cd886ea97c84703eaa6d88e37a2ad28"},
    {file = "PyYAML-6.0.1-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:40df9b996c2b73138957fe23a16a4f0ba614f4c0efce1e9406a184b6d07fa3a9"},
    {file = "PyYAML-6.0.1-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:a08c6f0fe150303c1c6b71ebcd7213c2858041a7e01975da3a99aed1e7a378ef"},
    {file = "PyYAML-6.0.1-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:6c22bec3fbe2524cde73d7ada88f6566758a8f7227bfbf93a408a9d86bcc12a0"},
    {file = "PyYAML-6.0.1-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:8d4e9c88387b0f5c7d5f281e55304de64cf7f9c0021a3525bd3b1c542da3b0e4"},
    {file = "PyYAML-6.0.1-cp312-cp312-win32.whl", hash = "sha256:d483d2cdf104e7c9fa60c544d92981f12ad66a457afae824d146093b8c294c54"},
    {file = "PyYAML-6.0.1-cp312-cp312-win_amd64.whl", hash = "sha256:0d3304d8c0adc42be59c5f8a4d9e3d7379e6955ad754aa9d6ab7a398b59dd1df"},
    {file = "PyYAML-6.0.1-cp36-cp36m-macosx_10_9_x86_64.whl", hash = "sha256:50550eb667afee136e9a77d6dc71ae76a44df8b3e51e41b77f6de2932bfe0f47"},
    {file = "PyYAML-6.0.1-cp36-cp36m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:1fe35611261b29bd1de0070f0b2f47cb6ff71fa6595c077e42bd0c419fa27b98"},
    {file = "PyYAML-6.0.1-cp36-cp36m-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:704219a11b772aea0d8ecd7058d0082713c3562b4e271b849ad7dc4a5c90c13c"},
    {file = "PyYAML-6.0.1-cp36-cp36m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:afd7e57eddb1a54f0f1a974bc4391af8bcce0b444685d936840f125cf046d5bd"},
    {file = "PyYAML-6.0.1-cp36-cp36m-win32.whl", hash = "sha256:fca0e3a251908a499833aa292323f32437106001d436eca0e6e7833256674585"},
    {file = "PyYAML-6.0.1-cp36-cp36m-win_amd64.whl", hash = "sha256:f22ac1c3cac4dbc50079e965eba2c1058622631e526bd9afd45fedd49ba781fa"},
    {file = "PyYAML-6.0.1-cp37-cp37m-macosx_10_9_x86_64.whl", hash = "sha256:b1275ad35a5d18c62a7220633c913e1b42d44b46ee12554e5fd39c70a243d6a3"},
    {file = "PyYAML-6.0.1-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:18aeb1bf9a78867dc38b259769503436b7c72f7a1f1f4c93ff9a17de54319b27"},
    {file = "PyYAML-6.0.1-cp37-cp37m-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:596106435fa6ad000c2991a98fa58eeb8656ef2325d7e158344fb33864ed87e3"},
    {file = "PyYAML-6.0.1-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:baa90d3f661d43131ca170712d903e6295d1f7a0f595074f151c0aed377c9b9c"},
    {file = "PyYAML-6.0.1-cp37-cp37m-win32.whl", hash = "sha256:9046c58c4395dff28dd494285c82ba00b546adfc7ef001486fbf0324bc174fba"},
    {file = "PyYAML-6.0.1-cp37-cp37m-win_amd64.whl", hash = "sha256:4fb147e7a67ef577a588a0e2c17b6db51dda102c71de36f8549b6816a96e1867"},
    {file = "PyYAML-6.0.1-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:1d4c7e777c441b20e32f52bd377e0c409713e8bb1386e1099c2415f26e479595"},
    {file = "PyYAML-6.0.1-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:a0cd17c15d3bb3fa06978b4e8958dcdc6e0174ccea823003a106c7d4d7899ac5"},
    {file = "PyYAML-6.0.1-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:28c119d996beec18c05208a8bd78cbe4007878c6dd15091efb73a30e90539696"},
    {file = "PyYAML-6.0.1-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:7e07cbde391ba96ab58e532ff4803f79c4129397514e1413a7dc761ccd755735"},
    {file = "PyYAML-6.0.1-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:49a183be227561de579b4a36efbb21b3eab9651dd81b1858589f796549873dd6"},
    {file = "PyYAML-6.0.1-cp38-cp38-win32.whl", hash = "sha256:184c5108a2aca3c5b3d3bf9395d50893a7ab82a38004c8f61c258d4428e80206"},
    {file = "PyYAML-6.0.1-cp38-cp38-win_amd64.whl", hash = "sha256:1e2722cc9fbb45d9b87631ac70924c11d3a401b2d7f410cc0e3bbf249f2dca62"},
    {file = "PyYAML-6.0.1-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:9eb6caa9a297fc2c2fb8862bc5370d0303ddba53ba97e71f08023b6cd73d16a8"},
    {file = "PyYAML-6.0.1-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:c8098ddcc2a85b61647b2590f825f3db38891662cfc2fc776415143f599bb859"},
    {file = "PyYAML-6.0.1-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:5773183b6446b2c99bb77e77595dd486303b4faab2b086e7b17bc6bef28865f6"},
    {file = "PyYAML-6.0.1-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:b786eecbdf8499b9ca1d697215862083bd6d2a99965554781d0d8d1ad31e13a0"},
    {file = "PyYAML-6.0.1-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:bc1bf2925a1ecd43da378f4db9e4f799775d6367bdb94671027b73b393a7c42c"},
    {file = "PyYAML-6.0.1-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:04ac92ad1925b2cff1db0cfebffb6ffc43457495c9b3c39d3fcae417d7125dc5"},
    {file = "PyYAML-6.0.1-cp39-cp39-win32.whl", hash = "sha256:faca3bdcf85b2fc05d06ff3fbc1f83e1391b3e724afa3feba7d13eeab355484c"},
    {file = "PyYAML-6.0.1-cp39-cp39-win_amd64.whl", hash = "sha256:510c9deebc5c0225e8c96813043e62b680ba2f9c50a08d3724c7f28a747d1486"},
    {file = "PyYAML-6.0.1.tar.gz", hash = "sha256:bfdf460b1736c775f2ba9f6a92bca30bc2095067b8a9d77876d1fad6cc3b4a43"},
]

[[package]]
name = "regex"
version = "2023.12.25"
description = "Alternative regular expression module, to replace re."
optional = false
python-versions = ">=3.7"
files = [
    {file = "regex-2023.12.25-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:0694219a1d54336fd0445ea382d49d36882415c0134ee1e8332afd1529f0baa5"},
    {file = "regex-2023.12.25-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:b014333bd0217ad3d54c143de9d4b9a3ca1c5a29a6d0d554952ea071cff0f1f8"},
    {file = "regex-2023.12.25-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:d865984b3f71f6d0af64d0d88f5733521698f6c16f445bb09ce746c92c97c586"},
    {file = "regex-2023.12.25-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:1e0eabac536b4cc7f57a5f3d095bfa557860ab912f25965e08fe1545e2ed8b4c"},
    {file = "regex-2023.12.25-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:c25a8ad70e716f96e13a637802813f65d8a6760ef48672aa3502f4c24ea8b400"},
    {file = "regex-2023.12.25-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:a9b6d73353f777630626f403b0652055ebfe8ff142a44ec2cf18ae470395766e"},
    {file = "regex-2023.12.25-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:a9cc99d6946d750eb75827cb53c4371b8b0fe89c733a94b1573c9dd16ea6c9e4"},
    {file = "regex-2023.12.25-cp310-cp310-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:88d1f7bef20c721359d8675f7d9f8e414ec5003d8f642fdfd8087777ff7f94b5"},
    {file = "regex-2023.12.25-cp310-cp310-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_12_x86_64.manylinux2010_x86_64.whl", hash = "sha256:cb3fe77aec8f1995611f966d0c656fdce398317f850d0e6e7aebdfe61f40e1cd"},
    {file = "regex-2023.12.25-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:7aa47c2e9ea33a4a2a05f40fcd3ea36d73853a2aae7b4feab6fc85f8bf2c9704"},
    {file = "regex-2023.12.25-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:df26481f0c7a3f8739fecb3e81bc9da3fcfae34d6c094563b9d4670b047312e1"},
    {file = "regex-2023.12.25-cp310-cp310-musllinux_1_1_ppc64le.whl", hash = "sha256:c40281f7d70baf6e0db0c2f7472b31609f5bc2748fe7275ea65a0b4601d9b392"},
    {file = "regex-2023.12.25-cp310-cp310-musllinux_1_1_s390x.whl", hash = "sha256:d94a1db462d5690ebf6ae86d11c5e420042b9898af5dcf278bd97d6bda065423"},
    {file = "regex-2023.12.25-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:ba1b30765a55acf15dce3f364e4928b80858fa8f979ad41f862358939bdd1f2f"},
    {file = "regex-2023.12.25-cp310-cp310-win32.whl", hash = "sha256:150c39f5b964e4d7dba46a7962a088fbc91f06e606f023ce57bb347a3b2d4630"},
    {file = "regex-2023.12.25-cp310-cp310-win_amd64.whl", hash = "sha256:09da66917262d9481c719599116c7dc0c321ffcec4b1f510c4f8a066f8768105"},
    {file = "regex-2023.12.25-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:1b9d811f72210fa9306aeb88385b8f8bcef0dfbf3873410413c00aa94c56c2b6"},
    {file = "regex-2023.12.25-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:d902a43085a308cef32c0d3aea962524b725403fd9373dea18110904003bac97"},
    {file = "regex-2023.12.25-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:d166eafc19f4718df38887b2bbe1467a4f74a9830e8605089ea7a30dd4da8887"},
    {file = "regex-2023.12.25-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:c7ad32824b7f02bb3c9f80306d405a1d9b7bb89362d68b3c5a9be53836caebdb"},
    {file = "regex-2023.12.25-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:636ba0a77de609d6510235b7f0e77ec494d2657108f777e8765efc060094c98c"},
    {file = "regex-2023.12.25-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:0fda75704357805eb953a3ee15a2b240694a9a514548cd49b3c5124b4e2ad01b"},
    {file = "regex-2023.12.25-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:f72cbae7f6b01591f90814250e636065850c5926751af02bb48da94dfced7baa"},
    {file = "regex-2023.12.25-cp311-cp311-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:db2a0b1857f18b11e3b0e54ddfefc96af46b0896fb678c85f63fb8c37518b3e7"},
    {file = "regex-2023.12.25-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:7502534e55c7c36c0978c91ba6f61703faf7ce733715ca48f499d3dbbd7657e0"},
    {file = "regex-2023.12.25-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:e8c7e08bb566de4faaf11984af13f6bcf6a08f327b13631d41d62592681d24fe"},
    {file = "regex-2023.12.25-cp311-cp311-musllinux_1_1_ppc64le.whl", hash = "sha256:283fc8eed679758de38fe493b7d7d84a198b558942b03f017b1f94dda8efae80"},
    {file = "regex-2023.12.25-cp311-cp311-musllinux_1_1_s390x.whl", hash = "sha256:f44dd4d68697559d007462b0a3a1d9acd61d97072b71f6d1968daef26bc744bd"},
    {file = "regex-2023.12.25-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:67d3ccfc590e5e7197750fcb3a2915b416a53e2de847a728cfa60141054123d4"},
    {file = "regex-2023.12.25-cp311-cp311-win32.whl", hash = "sha256:68191f80a9bad283432385961d9efe09d783bcd36ed35a60fb1ff3f1ec2efe87"},
    {file = "regex-2023.12.25-cp311-cp311-win_amd64.whl", hash = "sha256:7d2af3f6b8419661a0c421584cfe8aaec1c0e435ce7e47ee2a97e344b98f794f"},
    {file = "regex-2023.12.25-cp312-cp312-macosx_10_9_universal2.whl", hash = "sha256:8a0ccf52bb37d1a700375a6b395bff5dd15c50acb745f7db30415bae3c2b0715"},
    {file = "regex-2023.12.25-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:c3c4a78615b7762740531c27cf46e2f388d8d727d0c0c739e72048beb26c8a9d"},
    {file = "regex-2023.12.25-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:ad83e7545b4ab69216cef4cc47e344d19622e28aabec61574b20257c65466d6a"},
    {file = "regex-2023.12.25-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:b7a635871143661feccce3979e1727c4e094f2bdfd3ec4b90dfd4f16f571a87a"},
    {file = "regex-2023.12.25-cp312-cp312-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:d498eea3f581fbe1b34b59c697512a8baef88212f92e4c7830fcc1499f5b45a5"},
    {file = "regex-2023.12.25-cp312-cp312-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:43f7cd5754d02a56ae4ebb91b33461dc67be8e3e0153f593c509e21d219c5060"},
    {file = "regex-2023.12.25-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:51f4b32f793812714fd5307222a7f77e739b9bc566dc94a18126aba3b92b98a3"},
    {file = "regex-2023.12.25-cp312-cp312-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:ba99d8077424501b9616b43a2d208095746fb1284fc5ba490139651f971d39d9"},
    {file = "regex-2023.12.25-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:4bfc2b16e3ba8850e0e262467275dd4d62f0d045e0e9eda2bc65078c0110a11f"},
    {file = "regex-2023.12.25-cp312-cp312-musllinux_1_1_i686.whl", hash = "sha256:8c2c19dae8a3eb0ea45a8448356ed561be843b13cbc34b840922ddf565498c1c"},
    {file = "regex-2023.12.25-cp312-cp312-musllinux_1_1_ppc64le.whl", hash = "sha256:60080bb3d8617d96f0fb7e19796384cc2467447ef1c491694850ebd3670bc457"},
    {file = "regex-2023.12.25-cp312-cp312-musllinux_1_1_s390x.whl", hash = "sha256:b77e27b79448e34c2c51c09836033056a0547aa360c45eeeb67803da7b0eedaf"},
    {file = "regex-2023.12.25-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:518440c991f514331f4850a63560321f833979d145d7d81186dbe2f19e27ae3d"},
    {file = "regex-2023.12.25-cp312-cp312-win32.whl", hash = "sha256:e2610e9406d3b0073636a3a2e80db05a02f0c3169b5632022b4e81c0364bcda5"},
    {file = "regex-2023.12.25-cp312-cp312-win_amd64.whl", hash = "sha256:cc37b9aeebab425f11f27e5e9e6cf580be7206c6582a64467a14dda211abc232"},
    {file = "regex-2023.12.25-cp37-cp37m-macosx_10_9_x86_64.whl", hash = "sha256:da695d75ac97cb1cd725adac136d25ca687da4536154cdc2815f576e4da11c69"},
    {file = "regex-2023.12.25-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:d126361607b33c4eb7b36debc173bf25d7805847346dd4d99b5499e1fef52bc7"},
    {file = "regex-2023.12.25-cp37-cp37m-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:4719bb05094d7d8563a450cf8738d2e1061420f79cfcc1fa7f0a44744c4d8f73"},
    {file = "regex-2023.12.25-cp37-cp37m-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:5dd58946bce44b53b06d94aa95560d0b243eb2fe64227cba50017a8d8b3cd3e2"},
    {file = "regex-2023.12.25-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:22a86d9fff2009302c440b9d799ef2fe322416d2d58fc124b926aa89365ec482"},
    {file = "regex-2023.12.25-cp37-cp37m-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:2aae8101919e8aa05ecfe6322b278f41ce2994c4a430303c4cd163fef746e04f"},
    {file = "regex-2023.12.25-cp37-cp37m-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_12_x86_64.manylinux2010_x86_64.whl", hash = "sha256:e692296c4cc2873967771345a876bcfc1c547e8dd695c6b89342488b0ea55cd8"},
    {file = "regex-2023.12.25-cp37-cp37m-musllinux_1_1_aarch64.whl", hash = "sha256:263ef5cc10979837f243950637fffb06e8daed7f1ac1e39d5910fd29929e489a"},
    {file = "regex-2023.12.25-cp37-cp37m-musllinux_1_1_i686.whl", hash = "sha256:d6f7e255e5fa94642a0724e35406e6cb7001c09d476ab5fce002f652b36d0c39"},
    {file = "regex-2023.12.25-cp37-cp37m-musllinux_1_1_ppc64le.whl", hash = "sha256:88ad44e220e22b63b0f8f81f007e8abbb92874d8ced66f32571ef8beb0643b2b"},
    {file = "regex-2023.12.25-cp37-cp37m-musllinux_1_1_s390x.whl", hash = "sha256:3a17d3ede18f9cedcbe23d2daa8a2cd6f59fe2bf082c567e43083bba3fb00347"},
    {file = "regex-2023.12.25-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:d15b274f9e15b1a0b7a45d2ac86d1f634d983ca40d6b886721626c47a400bf39"},
    {file = "regex-2023.12.25-cp37-cp37m-win32.whl", hash = "sha256:ed19b3a05ae0c97dd8f75a5d8f21f7723a8c33bbc555da6bbe1f96c470139d3c"},
    {file = "regex-2023.12.25-cp37-cp37m-win_amd64.whl", hash = "sha256:a6d1047952c0b8104a1d371f88f4ab62e6275567d4458c1e26e9627ad489b445"},
    {file = "regex-2023.12.25-cp38-cp38-macosx_10_9_universal2.whl", hash = "sha256:b43523d7bc2abd757119dbfb38af91b5735eea45537ec6ec3a5ec3f9562a1c53"},
    {file = "regex-2023.12.25-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:efb2d82f33b2212898f1659fb1c2e9ac30493ac41e4d53123da374c3b5541e64"},
    {file = "regex-2023.12.25-cp38-cp38-macosx_11_0_arm64.whl", hash = "sha256:b7fca9205b59c1a3d5031f7e64ed627a1074730a51c2a80e97653e3e9fa0d415"},
    {file = "regex-2023.12.25-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:086dd15e9435b393ae06f96ab69ab2d333f5d65cbe65ca5a3ef0ec9564dfe770"},
    {file = "regex-2023.12.25-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:e81469f7d01efed9b53740aedd26085f20d49da65f9c1f41e822a33992cb1590"},
    {file = "regex-2023.12.25-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:34e4af5b27232f68042aa40a91c3b9bb4da0eeb31b7632e0091afc4310afe6cb"},
    {file = "regex-2023.12.25-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:9852b76ab558e45b20bf1893b59af64a28bd3820b0c2efc80e0a70a4a3ea51c1"},
    {file = "regex-2023.12.25-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:ff100b203092af77d1a5a7abe085b3506b7eaaf9abf65b73b7d6905b6cb76988"},
    {file = "regex-2023.12.25-cp38-cp38-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_12_x86_64.manylinux2010_x86_64.whl", hash = "sha256:cc038b2d8b1470364b1888a98fd22d616fba2b6309c5b5f181ad4483e0017861"},
    {file = "regex-2023.12.25-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:094ba386bb5c01e54e14434d4caabf6583334090865b23ef58e0424a6286d3dc"},
    {file = "regex-2023.12.25-cp38-cp38-musllinux_1_1_i686.whl", hash = "sha256:5cd05d0f57846d8ba4b71d9c00f6f37d6b97d5e5ef8b3c3840426a475c8f70f4"},
    {file = "regex-2023.12.25-cp38-cp38-musllinux_1_1_ppc64le.whl", hash = "sha256:9aa1a67bbf0f957bbe096375887b2505f5d8ae16bf04488e8b0f334c36e31360"},
    {file = "regex-2023.12.25-cp38-cp38-musllinux_1_1_s390x.whl", hash = "sha256:98a2636994f943b871786c9e82bfe7883ecdaba2ef5df54e1450fa9869d1f756"},
    {file = "regex-2023.12.25-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:37f8e93a81fc5e5bd8db7e10e62dc64261bcd88f8d7e6640aaebe9bc180d9ce2"},
    {file = "regex-2023.12.25-cp38-cp38-win32.whl", hash = "sha256:d78bd484930c1da2b9679290a41cdb25cc127d783768a0369d6b449e72f88beb"},
    {file = "regex-2023.12.25-cp38-cp38-win_amd64.whl", hash = "sha256:b521dcecebc5b978b447f0f69b5b7f3840eac454862270406a39837ffae4e697"},
    {file = "regex-2023.12.25-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:f7bc09bc9c29ebead055bcba136a67378f03d66bf359e87d0f7c759d6d4ffa31"},
    {file = "regex-2023.12.25-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:e14b73607d6231f3cc4622809c196b540a6a44e903bcfad940779c80dffa7be7"},
    {file = "regex-2023.12.25-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:9eda5f7a50141291beda3edd00abc2d4a5b16c29c92daf8d5bd76934150f3edc"},
    {file = "regex-2023.12.25-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:cc6bb9aa69aacf0f6032c307da718f61a40cf970849e471254e0e91c56ffca95"},
    {file = "regex-2023.12.25-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:298dc6354d414bc921581be85695d18912bea163a8b23cac9a2562bbcd5088b1"},
    {file = "regex-2023.12.25-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:2f4e475a80ecbd15896a976aa0b386c5525d0ed34d5c600b6d3ebac0a67c7ddf"},
    {file = "regex-2023.12.25-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:531ac6cf22b53e0696f8e1d56ce2396311254eb806111ddd3922c9d937151dae"},
    {file = "regex-2023.12.25-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:22f3470f7524b6da61e2020672df2f3063676aff444db1daa283c2ea4ed259d6"},
    {file = "regex-2023.12.25-cp39-cp39-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_12_x86_64.manylinux2010_x86_64.whl", hash = "sha256:89723d2112697feaa320c9d351e5f5e7b841e83f8b143dba8e2d2b5f04e10923"},
    {file = "regex-2023.12.25-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:0ecf44ddf9171cd7566ef1768047f6e66975788258b1c6c6ca78098b95cf9a3d"},
    {file = "regex-2023.12.25-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:905466ad1702ed4acfd67a902af50b8db1feeb9781436372261808df7a2a7bca"},
    {file = "regex-2023.12.25-cp39-cp39-musllinux_1_1_ppc64le.whl", hash = "sha256:4558410b7a5607a645e9804a3e9dd509af12fb72b9825b13791a37cd417d73a5"},
    {file = "regex-2023.12.25-cp39-cp39-musllinux_1_1_s390x.whl", hash = "sha256:7e316026cc1095f2a3e8cc012822c99f413b702eaa2ca5408a513609488cb62f"},
    {file = "regex-2023.12.25-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:3b1de218d5375cd6ac4b5493e0b9f3df2be331e86520f23382f216c137913d20"},
    {file = "regex-2023.12.25-cp39-cp39-win32.whl", hash = "sha256:11a963f8e25ab5c61348d090bf1b07f1953929c13bd2309a0662e9ff680763c9"},
    {file = "regex-2023.12.25-cp39-cp39-win_amd64.whl", hash = "sha256:e693e233ac92ba83a87024e1d32b5f9ab15ca55ddd916d878146f4e3406b5c91"},
    {file = "regex-2023.12.25.tar.gz", hash = "sha256:29171aa128da69afdf4bde412d5bedc335f2ca8fcfe4489038577d05f16181e5"},
]

[[package]]
name = "requests"
version = "2.31.0"
description = "Python HTTP for Humans."
optional = false
python-versions = ">=3.7"
files = [
    {file = "requests-2.31.0-py3-none-any.whl", hash = "sha256:58cd2187c01e70e6e26505bca751777aa9f2ee0b7f4300988b709f44e013003f"},
    {file = "requests-2.31.0.tar.gz", hash = "sha256:942c5a758f98d790eaed1a29cb6eefc7ffb0d1cf7af05c3d2791656dbd6ad1e1"},
]

[package.dependencies]
certifi = ">=2017.4.17"
charset-normalizer = ">=2,<4"
idna = ">=2.5,<4"
urllib3 = ">=1.21.1,<3"

[package.extras]
socks = ["PySocks (>=1.5.6,!=1.5.7)"]
use-chardet-on-py3 = ["chardet (>=3.0.2,<6)"]

[[package]]
name = "requests-file"
version = "2.0.0"
description = "File transport adapter for Requests"
optional = false
python-versions = "*"
files = [
    {file = "requests-file-2.0.0.tar.gz", hash = "sha256:20c5931629c558fda566cacc10cfe2cd502433e628f568c34c80d96a0cc95972"},
    {file = "requests_file-2.0.0-py2.py3-none-any.whl", hash = "sha256:3e493d390adb44aa102ebea827a48717336d5268968c370eaf19abaf5cae13bf"},
]

[package.dependencies]
requests = ">=1.0.0"

[[package]]
name = "rsa"
version = "4.9"
description = "Pure-Python RSA implementation"
optional = false
python-versions = ">=3.6,<4"
files = [
    {file = "rsa-4.9-py3-none-any.whl", hash = "sha256:90260d9058e514786967344d0ef75fa8727eed8a7d2e43ce9f4bcf1b536174f7"},
    {file = "rsa-4.9.tar.gz", hash = "sha256:e38464a49c6c85d7f1351b0126661487a7e0a14a50f1675ec50eb34d4f20ef21"},
]

[package.dependencies]
pyasn1 = ">=0.1.3"

[[package]]
name = "selenium"
version = "4.15.2"
description = ""
optional = false
python-versions = ">=3.8"
files = [
    {file = "selenium-4.15.2-py3-none-any.whl", hash = "sha256:9e82cd1ac647fb73cf0d4a6e280284102aaa3c9d94f0fa6e6cc4b5db6a30afbf"},
    {file = "selenium-4.15.2.tar.gz", hash = "sha256:22eab5a1724c73d51b240a69ca702997b717eee4ba1f6065bf5d6b44dba01d48"},
]

[package.dependencies]
certifi = ">=2021.10.8"
trio = ">=0.17,<1.0"
trio-websocket = ">=0.9,<1.0"
urllib3 = {version = ">=1.26,<3", extras = ["socks"]}

[[package]]
name = "sgmllib3k"
version = "1.0.0"
description = "Py3k port of sgmllib."
optional = false
python-versions = "*"
files = [
    {file = "sgmllib3k-1.0.0.tar.gz", hash = "sha256:7868fb1c8bfa764c1ac563d3cf369c381d1325d36124933a726f29fcdaa812e9"},
]

[[package]]
name = "six"
version = "1.16.0"
description = "Python 2 and 3 compatibility utilities"
optional = false
python-versions = ">=2.7, !=3.0.*, !=3.1.*, !=3.2.*"
files = [
    {file = "six-1.16.0-py2.py3-none-any.whl", hash = "sha256:8abb2f1d86890a2dfb989f9a77cfcfd3e47c2a354b01111771326f8aa26e0254"},
    {file = "six-1.16.0.tar.gz", hash = "sha256:1e61c37477a1626458e36f7b1d82aa5c9b094fa4802892072e49de9c60c4c926"},
]

[[package]]
name = "sniffio"
version = "1.3.0"
description = "Sniff out which async library your code is running under"
optional = false
python-versions = ">=3.7"
files = [
    {file = "sniffio-1.3.0-py3-none-any.whl", hash = "sha256:eecefdce1e5bbfb7ad2eeaabf7c1eeb404d7757c379bd1f7e5cce9d8bf425384"},
    {file = "sniffio-1.3.0.tar.gz", hash = "sha256:e60305c5e5d314f5389259b7f22aaa33d8f7dee49763119234af3755c55b9101"},
]

[[package]]
name = "sortedcontainers"
version = "2.4.0"
description = "Sorted Containers -- Sorted List, Sorted Dict, Sorted Set"
optional = false
python-versions = "*"
files = [
    {file = "sortedcontainers-2.4.0-py2.py3-none-any.whl", hash = "sha256:a163dcaede0f1c021485e957a39245190e74249897e2ae4b2aa38595db237ee0"},
    {file = "sortedcontainers-2.4.0.tar.gz", hash = "sha256:25caa5a06cc30b6b83d11423433f65d1f9d76c4c6a0c90e3379eaa43b9bfdb88"},
]

[[package]]
name = "soupsieve"
version = "2.5"
description = "A modern CSS selector implementation for Beautiful Soup."
optional = false
python-versions = ">=3.8"
files = [
    {file = "soupsieve-2.5-py3-none-any.whl", hash = "sha256:eaa337ff55a1579b6549dc679565eac1e3d000563bcb1c8ab0d0fefbc0c2cdc7"},
    {file = "soupsieve-2.5.tar.gz", hash = "sha256:5663d5a7b3bfaeee0bc4372e7fc48f9cff4940b3eec54a6451cc5299f1097690"},
]

[[package]]
name = "sqlalchemy"
version = "2.0.28"
description = "Database Abstraction Library"
optional = false
python-versions = ">=3.7"
files = [
    {file = "SQLAlchemy-2.0.28-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:e0b148ab0438f72ad21cb004ce3bdaafd28465c4276af66df3b9ecd2037bf252"},
    {file = "SQLAlchemy-2.0.28-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:bbda76961eb8f27e6ad3c84d1dc56d5bc61ba8f02bd20fcf3450bd421c2fcc9c"},
    {file = "SQLAlchemy-2.0.28-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:feea693c452d85ea0015ebe3bb9cd15b6f49acc1a31c28b3c50f4db0f8fb1e71"},
    {file = "SQLAlchemy-2.0.28-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:5da98815f82dce0cb31fd1e873a0cb30934971d15b74e0d78cf21f9e1b05953f"},
    {file = "SQLAlchemy-2.0.28-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:4a5adf383c73f2d49ad15ff363a8748319ff84c371eed59ffd0127355d6ea1da"},
    {file = "SQLAlchemy-2.0.28-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:56856b871146bfead25fbcaed098269d90b744eea5cb32a952df00d542cdd368"},
    {file = "SQLAlchemy-2.0.28-cp310-cp310-win32.whl", hash = "sha256:943aa74a11f5806ab68278284a4ddd282d3fb348a0e96db9b42cb81bf731acdc"},
    {file = "SQLAlchemy-2.0.28-cp310-cp310-win_amd64.whl", hash = "sha256:c6c4da4843e0dabde41b8f2e8147438330924114f541949e6318358a56d1875a"},
    {file = "SQLAlchemy-2.0.28-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:46a3d4e7a472bfff2d28db838669fc437964e8af8df8ee1e4548e92710929adc"},
    {file = "SQLAlchemy-2.0.28-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:0d3dd67b5d69794cfe82862c002512683b3db038b99002171f624712fa71aeaa"},
    {file = "SQLAlchemy-2.0.28-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:c61e2e41656a673b777e2f0cbbe545323dbe0d32312f590b1bc09da1de6c2a02"},
    {file = "SQLAlchemy-2.0.28-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:0315d9125a38026227f559488fe7f7cee1bd2fbc19f9fd637739dc50bb6380b2"},
    {file = "SQLAlchemy-2.0.28-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:af8ce2d31679006e7b747d30a89cd3ac1ec304c3d4c20973f0f4ad58e2d1c4c9"},
    {file = "SQLAlchemy-2.0.28-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:81ba314a08c7ab701e621b7ad079c0c933c58cdef88593c59b90b996e8b58fa5"},
    {file = "SQLAlchemy-2.0.28-cp311-cp311-win32.whl", hash = "sha256:1ee8bd6d68578e517943f5ebff3afbd93fc65f7ef8f23becab9fa8fb315afb1d"},
    {file = "SQLAlchemy-2.0.28-cp311-cp311-win_amd64.whl", hash = "sha256:ad7acbe95bac70e4e687a4dc9ae3f7a2f467aa6597049eeb6d4a662ecd990bb6"},
    {file = "SQLAlchemy-2.0.28-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:d3499008ddec83127ab286c6f6ec82a34f39c9817f020f75eca96155f9765097"},
    {file = "SQLAlchemy-2.0.28-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:9b66fcd38659cab5d29e8de5409cdf91e9986817703e1078b2fdaad731ea66f5"},
    {file = "SQLAlchemy-2.0.28-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:bea30da1e76cb1acc5b72e204a920a3a7678d9d52f688f087dc08e54e2754c67"},
    {file = "SQLAlchemy-2.0.28-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:124202b4e0edea7f08a4db8c81cc7859012f90a0d14ba2bf07c099aff6e96462"},
    {file = "SQLAlchemy-2.0.28-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:e23b88c69497a6322b5796c0781400692eca1ae5532821b39ce81a48c395aae9"},
    {file = "SQLAlchemy-2.0.28-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:4b6303bfd78fb3221847723104d152e5972c22367ff66edf09120fcde5ddc2e2"},
    {file = "SQLAlchemy-2.0.28-cp312-cp312-win32.whl", hash = "sha256:a921002be69ac3ab2cf0c3017c4e6a3377f800f1fca7f254c13b5f1a2f10022c"},
    {file = "SQLAlchemy-2.0.28-cp312-cp312-win_amd64.whl", hash = "sha256:b4a2cf92995635b64876dc141af0ef089c6eea7e05898d8d8865e71a326c0385"},
    {file = "SQLAlchemy-2.0.28-cp37-cp37m-macosx_10_9_x86_64.whl", hash = "sha256:8e91b5e341f8c7f1e5020db8e5602f3ed045a29f8e27f7f565e0bdee3338f2c7"},
    {file = "SQLAlchemy-2.0.28-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:45c7b78dfc7278329f27be02c44abc0d69fe235495bb8e16ec7ef1b1a17952db"},
    {file = "SQLAlchemy-2.0.28-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:3eba73ef2c30695cb7eabcdb33bb3d0b878595737479e152468f3ba97a9c22a4"},
    {file = "SQLAlchemy-2.0.28-cp37-cp37m-musllinux_1_1_aarch64.whl", hash = "sha256:5df5d1dafb8eee89384fb7a1f79128118bc0ba50ce0db27a40750f6f91aa99d5"},
    {file = "SQLAlchemy-2.0.28-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:2858bbab1681ee5406650202950dc8f00e83b06a198741b7c656e63818633526"},
    {file = "SQLAlchemy-2.0.28-cp37-cp37m-win32.whl", hash = "sha256:9461802f2e965de5cff80c5a13bc945abea7edaa1d29360b485c3d2b56cdb075"},
    {file = "SQLAlchemy-2.0.28-cp37-cp37m-win_amd64.whl", hash = "sha256:a6bec1c010a6d65b3ed88c863d56b9ea5eeefdf62b5e39cafd08c65f5ce5198b"},
    {file = "SQLAlchemy-2.0.28-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:843a882cadebecc655a68bd9a5b8aa39b3c52f4a9a5572a3036fb1bb2ccdc197"},
    {file = "SQLAlchemy-2.0.28-cp38-cp38-macosx_11_0_arm64.whl", hash = "sha256:dbb990612c36163c6072723523d2be7c3eb1517bbdd63fe50449f56afafd1133"},
    {file = "SQLAlchemy-2.0.28-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:bd7e4baf9161d076b9a7e432fce06217b9bd90cfb8f1d543d6e8c4595627edb9"},
    {file = "SQLAlchemy-2.0.28-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:e0a5354cb4de9b64bccb6ea33162cb83e03dbefa0d892db88a672f5aad638a75"},
    {file = "SQLAlchemy-2.0.28-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:fffcc8edc508801ed2e6a4e7b0d150a62196fd28b4e16ab9f65192e8186102b6"},
    {file = "SQLAlchemy-2.0.28-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:aca7b6d99a4541b2ebab4494f6c8c2f947e0df4ac859ced575238e1d6ca5716b"},
    {file = "SQLAlchemy-2.0.28-cp38-cp38-win32.whl", hash = "sha256:8c7f10720fc34d14abad5b647bc8202202f4948498927d9f1b4df0fb1cf391b7"},
    {file = "SQLAlchemy-2.0.28-cp38-cp38-win_amd64.whl", hash = "sha256:243feb6882b06a2af68ecf4bec8813d99452a1b62ba2be917ce6283852cf701b"},
    {file = "SQLAlchemy-2.0.28-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:fc4974d3684f28b61b9a90fcb4c41fb340fd4b6a50c04365704a4da5a9603b05"},
    {file = "SQLAlchemy-2.0.28-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:87724e7ed2a936fdda2c05dbd99d395c91ea3c96f029a033a4a20e008dd876bf"},
    {file = "SQLAlchemy-2.0.28-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:68722e6a550f5de2e3cfe9da6afb9a7dd15ef7032afa5651b0f0c6b3adb8815d"},
    {file = "SQLAlchemy-2.0.28-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:328529f7c7f90adcd65aed06a161851f83f475c2f664a898af574893f55d9e53"},
    {file = "SQLAlchemy-2.0.28-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:df40c16a7e8be7413b885c9bf900d402918cc848be08a59b022478804ea076b8"},
    {file = "SQLAlchemy-2.0.28-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:426f2fa71331a64f5132369ede5171c52fd1df1bd9727ce621f38b5b24f48750"},
    {file = "SQLAlchemy-2.0.28-cp39-cp39-win32.whl", hash = "sha256:33157920b233bc542ce497a81a2e1452e685a11834c5763933b440fedd1d8e2d"},
    {file = "SQLAlchemy-2.0.28-cp39-cp39-win_amd64.whl", hash = "sha256:2f60843068e432311c886c5f03c4664acaef507cf716f6c60d5fde7265be9d7b"},
    {file = "SQLAlchemy-2.0.28-py3-none-any.whl", hash = "sha256:78bb7e8da0183a8301352d569900d9d3594c48ac21dc1c2ec6b3121ed8b6c986"},
    {file = "SQLAlchemy-2.0.28.tar.gz", hash = "sha256:dd53b6c4e6d960600fd6532b79ee28e2da489322fcf6648738134587faf767b6"},
]

[package.dependencies]
greenlet = {version = "!=0.4.17", markers = "platform_machine == \"aarch64\" or platform_machine == \"ppc64le\" or platform_machine == \"x86_64\" or platform_machine == \"amd64\" or platform_machine == \"AMD64\" or platform_machine == \"win32\" or platform_machine == \"WIN32\""}
typing-extensions = ">=4.6.0"

[package.extras]
aiomysql = ["aiomysql (>=0.2.0)", "greenlet (!=0.4.17)"]
aioodbc = ["aioodbc", "greenlet (!=0.4.17)"]
aiosqlite = ["aiosqlite", "greenlet (!=0.4.17)", "typing_extensions (!=3.10.0.1)"]
asyncio = ["greenlet (!=0.4.17)"]
asyncmy = ["asyncmy (>=0.2.3,!=0.2.4,!=0.2.6)", "greenlet (!=0.4.17)"]
mariadb-connector = ["mariadb (>=1.0.1,!=1.1.2,!=1.1.5)"]
mssql = ["pyodbc"]
mssql-pymssql = ["pymssql"]
mssql-pyodbc = ["pyodbc"]
mypy = ["mypy (>=0.910)"]
mysql = ["mysqlclient (>=1.4.0)"]
mysql-connector = ["mysql-connector-python"]
oracle = ["cx_oracle (>=8)"]
oracle-oracledb = ["oracledb (>=1.0.1)"]
postgresql = ["psycopg2 (>=2.7)"]
postgresql-asyncpg = ["asyncpg", "greenlet (!=0.4.17)"]
postgresql-pg8000 = ["pg8000 (>=1.29.1)"]
postgresql-psycopg = ["psycopg (>=3.0.7)"]
postgresql-psycopg2binary = ["psycopg2-binary"]
postgresql-psycopg2cffi = ["psycopg2cffi"]
postgresql-psycopgbinary = ["psycopg[binary] (>=3.0.7)"]
pymysql = ["pymysql"]
sqlcipher = ["sqlcipher3_binary"]

[[package]]
name = "starlette"
version = "0.27.0"
description = "The little ASGI library that shines."
optional = false
python-versions = ">=3.7"
files = [
    {file = "starlette-0.27.0-py3-none-any.whl", hash = "sha256:918416370e846586541235ccd38a474c08b80443ed31c578a418e2209b3eef91"},
    {file = "starlette-0.27.0.tar.gz", hash = "sha256:6a6b0d042acb8d469a01eba54e9cda6cbd24ac602c4cd016723117d6a7e73b75"},
]

[package.dependencies]
anyio = ">=3.4.0,<5"

[package.extras]
full = ["httpx (>=0.22.0)", "itsdangerous", "jinja2", "python-multipart", "pyyaml"]

[[package]]
name = "tavily-python"
version = "0.3.1"
description = "Python wrapper for the Tavily API"
optional = false
python-versions = ">=3.6"
files = [
    {file = "tavily-python-0.3.1.tar.gz", hash = "sha256:0c1bbc89560f145d7aa1355555ed850f909be2745f7556ea47759bef5ccf8b7c"},
    {file = "tavily_python-0.3.1-py3-none-any.whl", hash = "sha256:34616e6b3a86a3a043b6387d059e3652a7b9a8ac82ade865c047343391dee658"},
]

[package.dependencies]
requests = "*"
tiktoken = "0.5.2"

[[package]]
name = "tenacity"
version = "8.2.3"
description = "Retry code until it succeeds"
optional = false
python-versions = ">=3.7"
files = [
    {file = "tenacity-8.2.3-py3-none-any.whl", hash = "sha256:ce510e327a630c9e1beaf17d42e6ffacc88185044ad85cf74c0a8887c6a0f88c"},
    {file = "tenacity-8.2.3.tar.gz", hash = "sha256:5398ef0d78e63f40007c1fb4c0bff96e1911394d2fa8d194f77619c05ff6cc8a"},
]

[package.extras]
doc = ["reno", "sphinx", "tornado (>=4.5)"]

[[package]]
name = "tiktoken"
version = "0.5.2"
description = "tiktoken is a fast BPE tokeniser for use with OpenAI's models"
optional = false
python-versions = ">=3.8"
files = [
    {file = "tiktoken-0.5.2-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:8c4e654282ef05ec1bd06ead22141a9a1687991cef2c6a81bdd1284301abc71d"},
    {file = "tiktoken-0.5.2-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:7b3134aa24319f42c27718c6967f3c1916a38a715a0fa73d33717ba121231307"},
    {file = "tiktoken-0.5.2-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:6092e6e77730929c8c6a51bb0d7cfdf1b72b63c4d033d6258d1f2ee81052e9e5"},
    {file = "tiktoken-0.5.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:72ad8ae2a747622efae75837abba59be6c15a8f31b4ac3c6156bc56ec7a8e631"},
    {file = "tiktoken-0.5.2-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:51cba7c8711afa0b885445f0637f0fcc366740798c40b981f08c5f984e02c9d1"},
    {file = "tiktoken-0.5.2-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:3d8c7d2c9313f8e92e987d585ee2ba0f7c40a0de84f4805b093b634f792124f5"},
    {file = "tiktoken-0.5.2-cp310-cp310-win_amd64.whl", hash = "sha256:692eca18c5fd8d1e0dde767f895c17686faaa102f37640e884eecb6854e7cca7"},
    {file = "tiktoken-0.5.2-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:138d173abbf1ec75863ad68ca289d4da30caa3245f3c8d4bfb274c4d629a2f77"},
    {file = "tiktoken-0.5.2-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:7388fdd684690973fdc450b47dfd24d7f0cbe658f58a576169baef5ae4658607"},
    {file = "tiktoken-0.5.2-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:a114391790113bcff670c70c24e166a841f7ea8f47ee2fe0e71e08b49d0bf2d4"},
    {file = "tiktoken-0.5.2-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:ca96f001e69f6859dd52926d950cfcc610480e920e576183497ab954e645e6ac"},
    {file = "tiktoken-0.5.2-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:15fed1dd88e30dfadcdd8e53a8927f04e1f6f81ad08a5ca824858a593ab476c7"},
    {file = "tiktoken-0.5.2-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:93f8e692db5756f7ea8cb0cfca34638316dcf0841fb8469de8ed7f6a015ba0b0"},
    {file = "tiktoken-0.5.2-cp311-cp311-win_amd64.whl", hash = "sha256:bcae1c4c92df2ffc4fe9f475bf8148dbb0ee2404743168bbeb9dcc4b79dc1fdd"},
    {file = "tiktoken-0.5.2-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:b76a1e17d4eb4357d00f0622d9a48ffbb23401dcf36f9716d9bd9c8e79d421aa"},
    {file = "tiktoken-0.5.2-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:01d8b171bb5df4035580bc26d4f5339a6fd58d06f069091899d4a798ea279d3e"},
    {file = "tiktoken-0.5.2-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:42adf7d4fb1ed8de6e0ff2e794a6a15005f056a0d83d22d1d6755a39bffd9e7f"},
    {file = "tiktoken-0.5.2-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:4c3f894dbe0adb44609f3d532b8ea10820d61fdcb288b325a458dfc60fefb7db"},
    {file = "tiktoken-0.5.2-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:58ccfddb4e62f0df974e8f7e34a667981d9bb553a811256e617731bf1d007d19"},
    {file = "tiktoken-0.5.2-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:58902a8bad2de4268c2a701f1c844d22bfa3cbcc485b10e8e3e28a050179330b"},
    {file = "tiktoken-0.5.2-cp312-cp312-win_amd64.whl", hash = "sha256:5e39257826d0647fcac403d8fa0a474b30d02ec8ffc012cfaf13083e9b5e82c5"},
    {file = "tiktoken-0.5.2-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:8bde3b0fbf09a23072d39c1ede0e0821f759b4fa254a5f00078909158e90ae1f"},
    {file = "tiktoken-0.5.2-cp38-cp38-macosx_11_0_arm64.whl", hash = "sha256:2ddee082dcf1231ccf3a591d234935e6acf3e82ee28521fe99af9630bc8d2a60"},
    {file = "tiktoken-0.5.2-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:35c057a6a4e777b5966a7540481a75a31429fc1cb4c9da87b71c8b75b5143037"},
    {file = "tiktoken-0.5.2-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:4c4a049b87e28f1dc60509f8eb7790bc8d11f9a70d99b9dd18dfdd81a084ffe6"},
    {file = "tiktoken-0.5.2-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:5bf5ce759089f4f6521ea6ed89d8f988f7b396e9f4afb503b945f5c949c6bec2"},
    {file = "tiktoken-0.5.2-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:0c964f554af1a96884e01188f480dad3fc224c4bbcf7af75d4b74c4b74ae0125"},
    {file = "tiktoken-0.5.2-cp38-cp38-win_amd64.whl", hash = "sha256:368dd5726d2e8788e47ea04f32e20f72a2012a8a67af5b0b003d1e059f1d30a3"},
    {file = "tiktoken-0.5.2-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:a2deef9115b8cd55536c0a02c0203512f8deb2447f41585e6d929a0b878a0dd2"},
    {file = "tiktoken-0.5.2-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:2ed7d380195affbf886e2f8b92b14edfe13f4768ff5fc8de315adba5b773815e"},
    {file = "tiktoken-0.5.2-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:c76fce01309c8140ffe15eb34ded2bb94789614b7d1d09e206838fc173776a18"},
    {file = "tiktoken-0.5.2-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:60a5654d6a2e2d152637dd9a880b4482267dfc8a86ccf3ab1cec31a8c76bfae8"},
    {file = "tiktoken-0.5.2-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:41d4d3228e051b779245a8ddd21d4336f8975563e92375662f42d05a19bdff41"},
    {file = "tiktoken-0.5.2-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:a5c1cdec2c92fcde8c17a50814b525ae6a88e8e5b02030dc120b76e11db93f13"},
    {file = "tiktoken-0.5.2-cp39-cp39-win_amd64.whl", hash = "sha256:84ddb36faedb448a50b246e13d1b6ee3437f60b7169b723a4b2abad75e914f3e"},
    {file = "tiktoken-0.5.2.tar.gz", hash = "sha256:f54c581f134a8ea96ce2023ab221d4d4d81ab614efa0b2fbce926387deb56c80"},
]

[package.dependencies]
regex = ">=2022.1.18"
requests = ">=2.26.0"

[package.extras]
blobfile = ["blobfile (>=2)"]

[[package]]
name = "tinycss2"
version = "1.2.1"
description = "A tiny CSS parser"
optional = false
python-versions = ">=3.7"
files = [
    {file = "tinycss2-1.2.1-py3-none-any.whl", hash = "sha256:2b80a96d41e7c3914b8cda8bc7f705a4d9c49275616e886103dd839dfc847847"},
    {file = "tinycss2-1.2.1.tar.gz", hash = "sha256:8cff3a8f066c2ec677c06dbc7b45619804a6938478d9d73c284b29d14ecb0627"},
]

[package.dependencies]
webencodings = ">=0.4"

[package.extras]
doc = ["sphinx", "sphinx_rtd_theme"]
test = ["flake8", "isort", "pytest"]

[[package]]
name = "tinysegmenter"
version = "0.3"
description = "Very compact Japanese tokenizer"
optional = false
python-versions = "*"
files = [
    {file = "tinysegmenter-0.3.tar.gz", hash = "sha256:ed1f6d2e806a4758a73be589754384cbadadc7e1a414c81a166fc9adf2d40c6d"},
]

[[package]]
name = "tldextract"
version = "5.1.2"
description = "Accurately separates a URL's subdomain, domain, and public suffix, using the Public Suffix List (PSL). By default, this includes the public ICANN TLDs and their exceptions. You can optionally support the Public Suffix List's private domains as well."
optional = false
python-versions = ">=3.8"
files = [
    {file = "tldextract-5.1.2-py3-none-any.whl", hash = "sha256:4dfc4c277b6b97fa053899fcdb892d2dc27295851ab5fac4e07797b6a21b2e46"},
    {file = "tldextract-5.1.2.tar.gz", hash = "sha256:c9e17f756f05afb5abac04fe8f766e7e70f9fe387adb1859f0f52408ee060200"},
]

[package.dependencies]
filelock = ">=3.0.8"
idna = "*"
requests = ">=2.1.0"
requests-file = ">=1.4"

[package.extras]
release = ["build", "twine"]
testing = ["black", "mypy", "pytest", "pytest-gitignore", "pytest-mock", "responses", "ruff", "syrupy", "tox", "types-filelock", "types-requests"]

[[package]]
name = "tqdm"
version = "4.66.1"
description = "Fast, Extensible Progress Meter"
optional = false
python-versions = ">=3.7"
files = [
    {file = "tqdm-4.66.1-py3-none-any.whl", hash = "sha256:d302b3c5b53d47bce91fea46679d9c3c6508cf6332229aa1e7d8653723793386"},
    {file = "tqdm-4.66.1.tar.gz", hash = "sha256:d88e651f9db8d8551a62556d3cff9e3034274ca5d66e93197cf2490e2dcb69c7"},
]

[package.dependencies]
colorama = {version = "*", markers = "platform_system == \"Windows\""}

[package.extras]
dev = ["pytest (>=6)", "pytest-cov", "pytest-timeout", "pytest-xdist"]
notebook = ["ipywidgets (>=6)"]
slack = ["slack-sdk"]
telegram = ["requests"]

[[package]]
name = "trio"
version = "0.23.2"
description = "A friendly Python library for async concurrency and I/O"
optional = false
python-versions = ">=3.8"
files = [
    {file = "trio-0.23.2-py3-none-any.whl", hash = "sha256:5a0b566fa5d50cf231cfd6b08f3b03aa4179ff004b8f3144059587039e2b26d3"},
    {file = "trio-0.23.2.tar.gz", hash = "sha256:da1d35b9a2b17eb32cae2e763b16551f9aa6703634735024e32f325c9285069e"},
]

[package.dependencies]
attrs = ">=20.1.0"
cffi = {version = ">=1.14", markers = "os_name == \"nt\" and implementation_name != \"pypy\""}
exceptiongroup = {version = "*", markers = "python_version < \"3.11\""}
idna = "*"
outcome = "*"
sniffio = ">=1.3.0"
sortedcontainers = "*"

[[package]]
name = "trio-websocket"
version = "0.11.1"
description = "WebSocket library for Trio"
optional = false
python-versions = ">=3.7"
files = [
    {file = "trio-websocket-0.11.1.tar.gz", hash = "sha256:18c11793647703c158b1f6e62de638acada927344d534e3c7628eedcb746839f"},
    {file = "trio_websocket-0.11.1-py3-none-any.whl", hash = "sha256:520d046b0d030cf970b8b2b2e00c4c2245b3807853ecd44214acd33d74581638"},
]

[package.dependencies]
exceptiongroup = {version = "*", markers = "python_version < \"3.11\""}
trio = ">=0.11"
wsproto = ">=0.14"

[[package]]
name = "typing-extensions"
version = "4.9.0"
description = "Backported and Experimental Type Hints for Python 3.8+"
optional = false
python-versions = ">=3.8"
files = [
    {file = "typing_extensions-4.9.0-py3-none-any.whl", hash = "sha256:af72aea155e91adfc61c3ae9e0e342dbc0cba726d6cba4b6c72c1f34e47291cd"},
    {file = "typing_extensions-4.9.0.tar.gz", hash = "sha256:23478f88c37f27d76ac8aee6c905017a143b0b1b886c3c9f66bc2fd94f9f5783"},
]

[[package]]
name = "typing-inspect"
version = "0.9.0"
description = "Runtime inspection utilities for typing module."
optional = false
python-versions = "*"
files = [
    {file = "typing_inspect-0.9.0-py3-none-any.whl", hash = "sha256:9ee6fc59062311ef8547596ab6b955e1b8aa46242d854bfc78f4f6b0eff35f9f"},
    {file = "typing_inspect-0.9.0.tar.gz", hash = "sha256:b23fc42ff6f6ef6954e4852c1fb512cdd18dbea03134f91f856a95ccc9461f78"},
]

[package.dependencies]
mypy-extensions = ">=0.3.0"
typing-extensions = ">=3.7.4"

[[package]]
name = "urllib3"
version = "2.1.0"
description = "HTTP library with thread-safe connection pooling, file post, and more."
optional = false
python-versions = ">=3.8"
files = [
    {file = "urllib3-2.1.0-py3-none-any.whl", hash = "sha256:55901e917a5896a349ff771be919f8bd99aff50b79fe58fec595eb37bbc56bb3"},
    {file = "urllib3-2.1.0.tar.gz", hash = "sha256:df7aa8afb0148fa78488e7899b2c59b5f4ffcfa82e6c54ccb9dd37c1d7b52d54"},
]

[package.dependencies]
pysocks = {version = ">=1.5.6,<1.5.7 || >1.5.7,<2.0", optional = true, markers = "extra == \"socks\""}

[package.extras]
brotli = ["brotli (>=1.0.9)", "brotlicffi (>=0.8.0)"]
socks = ["pysocks (>=1.5.6,!=1.5.7,<2.0)"]
zstd = ["zstandard (>=0.18.0)"]

[[package]]
name = "uvicorn"
version = "0.24.0.post1"
description = "The lightning-fast ASGI server."
optional = false
python-versions = ">=3.8"
files = [
    {file = "uvicorn-0.24.0.post1-py3-none-any.whl", hash = "sha256:7c84fea70c619d4a710153482c0d230929af7bcf76c7bfa6de151f0a3a80121e"},
    {file = "uvicorn-0.24.0.post1.tar.gz", hash = "sha256:09c8e5a79dc466bdf28dead50093957db184de356fcdc48697bad3bde4c2588e"},
]

[package.dependencies]
click = ">=7.0"
h11 = ">=0.8"
typing-extensions = {version = ">=4.0", markers = "python_version < \"3.11\""}

[package.extras]
standard = ["colorama (>=0.4)", "httptools (>=0.5.0)", "python-dotenv (>=0.13)", "pyyaml (>=5.1)", "uvloop (>=0.14.0,!=0.15.0,!=0.15.1)", "watchfiles (>=0.13)", "websockets (>=10.4)"]

[[package]]
name = "weasyprint"
version = "60.2"
description = "The Awesome Document Factory"
optional = false
python-versions = ">=3.7"
files = [
    {file = "weasyprint-60.2-py3-none-any.whl", hash = "sha256:3e98eedcc1c5a14cb310c293c6d59a479f59a13f0d705ff07106482827fa5705"},
    {file = "weasyprint-60.2.tar.gz", hash = "sha256:0c0cdd617a78699262b80026e67fa1692e3802cfa966395436eeaf6f787dd126"},
]

[package.dependencies]
cffi = ">=0.6"
cssselect2 = ">=0.1"
fonttools = {version = ">=4.0.0", extras = ["woff"]}
html5lib = ">=1.1"
Pillow = ">=9.1.0"
pydyf = ">=0.8.0"
Pyphen = ">=0.9.1"
tinycss2 = ">=1.0.0"

[package.extras]
doc = ["sphinx", "sphinx_rtd_theme"]
test = ["flake8", "isort", "pytest"]

[[package]]
name = "webdriver-manager"
version = "4.0.1"
description = "Library provides the way to automatically manage drivers for different browsers"
optional = false
python-versions = ">=3.7"
files = [
    {file = "webdriver_manager-4.0.1-py2.py3-none-any.whl", hash = "sha256:d7970052295bb9cda2c1a24cf0b872dd2c41ababcc78f7b6b8dc37a41e979a7e"},
    {file = "webdriver_manager-4.0.1.tar.gz", hash = "sha256:25ec177c6a2ce9c02fb8046f1b2732701a9418d6a977967bb065d840a3175d87"},
]

[package.dependencies]
packaging = "*"
python-dotenv = "*"
requests = "*"

[[package]]
name = "webencodings"
version = "0.5.1"
description = "Character encoding aliases for legacy web content"
optional = false
python-versions = "*"
files = [
    {file = "webencodings-0.5.1-py2.py3-none-any.whl", hash = "sha256:a0af1213f3c2226497a97e2b3aa01a7e4bee4f403f95be16fc9acd2947514a78"},
    {file = "webencodings-0.5.1.tar.gz", hash = "sha256:b36a1c245f2d304965eb4e0a82848379241dc04b865afcc4aab16748587e1923"},
]

[[package]]
name = "wsproto"
version = "1.2.0"
description = "WebSockets state-machine based protocol implementation"
optional = false
python-versions = ">=3.7.0"
files = [
    {file = "wsproto-1.2.0-py3-none-any.whl", hash = "sha256:b9acddd652b585d75b20477888c56642fdade28bdfd3579aa24a4d2c037dd736"},
    {file = "wsproto-1.2.0.tar.gz", hash = "sha256:ad565f26ecb92588a3e43bc3d96164de84cd9902482b130d0ddbaa9664a85065"},
]

[package.dependencies]
h11 = ">=0.9.0,<1"

[[package]]
name = "yarl"
version = "1.9.4"
description = "Yet another URL library"
optional = false
python-versions = ">=3.7"
files = [
    {file = "yarl-1.9.4-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:a8c1df72eb746f4136fe9a2e72b0c9dc1da1cbd23b5372f94b5820ff8ae30e0e"},
    {file = "yarl-1.9.4-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:a3a6ed1d525bfb91b3fc9b690c5a21bb52de28c018530ad85093cc488bee2dd2"},
    {file = "yarl-1.9.4-cp310-cp310-macosx_11_0_arm64.whl", hash = "sha256:c38c9ddb6103ceae4e4498f9c08fac9b590c5c71b0370f98714768e22ac6fa66"},
    {file = "yarl-1.9.4-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:d9e09c9d74f4566e905a0b8fa668c58109f7624db96a2171f21747abc7524234"},
    {file = "yarl-1.9.4-cp310-cp310-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:b8477c1ee4bd47c57d49621a062121c3023609f7a13b8a46953eb6c9716ca392"},
    {file = "yarl-1.9.4-cp310-cp310-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:d5ff2c858f5f6a42c2a8e751100f237c5e869cbde669a724f2062d4c4ef93551"},
    {file = "yarl-1.9.4-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:357495293086c5b6d34ca9616a43d329317feab7917518bc97a08f9e55648455"},
    {file = "yarl-1.9.4-cp310-cp310-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:54525ae423d7b7a8ee81ba189f131054defdb122cde31ff17477951464c1691c"},
    {file = "yarl-1.9.4-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:801e9264d19643548651b9db361ce3287176671fb0117f96b5ac0ee1c3530d53"},
    {file = "yarl-1.9.4-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:e516dc8baf7b380e6c1c26792610230f37147bb754d6426462ab115a02944385"},
    {file = "yarl-1.9.4-cp310-cp310-musllinux_1_1_ppc64le.whl", hash = "sha256:7d5aaac37d19b2904bb9dfe12cdb08c8443e7ba7d2852894ad448d4b8f442863"},
    {file = "yarl-1.9.4-cp310-cp310-musllinux_1_1_s390x.whl", hash = "sha256:54beabb809ffcacbd9d28ac57b0db46e42a6e341a030293fb3185c409e626b8b"},
    {file = "yarl-1.9.4-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:bac8d525a8dbc2a1507ec731d2867025d11ceadcb4dd421423a5d42c56818541"},
    {file = "yarl-1.9.4-cp310-cp310-win32.whl", hash = "sha256:7855426dfbddac81896b6e533ebefc0af2f132d4a47340cee6d22cac7190022d"},
    {file = "yarl-1.9.4-cp310-cp310-win_amd64.whl", hash = "sha256:848cd2a1df56ddbffeb375535fb62c9d1645dde33ca4d51341378b3f5954429b"},
    {file = "yarl-1.9.4-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:35a2b9396879ce32754bd457d31a51ff0a9d426fd9e0e3c33394bf4b9036b099"},
    {file = "yarl-1.9.4-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:4c7d56b293cc071e82532f70adcbd8b61909eec973ae9d2d1f9b233f3d943f2c"},
    {file = "yarl-1.9.4-cp311-cp311-macosx_11_0_arm64.whl", hash = "sha256:d8a1c6c0be645c745a081c192e747c5de06e944a0d21245f4cf7c05e457c36e0"},
    {file = "yarl-1.9.4-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:4b3c1ffe10069f655ea2d731808e76e0f452fc6c749bea04781daf18e6039525"},
    {file = "yarl-1.9.4-cp311-cp311-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:549d19c84c55d11687ddbd47eeb348a89df9cb30e1993f1b128f4685cd0ebbf8"},
    {file = "yarl-1.9.4-cp311-cp311-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:a7409f968456111140c1c95301cadf071bd30a81cbd7ab829169fb9e3d72eae9"},
    {file = "yarl-1.9.4-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:e23a6d84d9d1738dbc6e38167776107e63307dfc8ad108e580548d1f2c587f42"},
    {file = "yarl-1.9.4-cp311-cp311-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:d8b889777de69897406c9fb0b76cdf2fd0f31267861ae7501d93003d55f54fbe"},
    {file = "yarl-1.9.4-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:03caa9507d3d3c83bca08650678e25364e1843b484f19986a527630ca376ecce"},
    {file = "yarl-1.9.4-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:4e9035df8d0880b2f1c7f5031f33f69e071dfe72ee9310cfc76f7b605958ceb9"},
    {file = "yarl-1.9.4-cp311-cp311-musllinux_1_1_ppc64le.whl", hash = "sha256:c0ec0ed476f77db9fb29bca17f0a8fcc7bc97ad4c6c1d8959c507decb22e8572"},
    {file = "yarl-1.9.4-cp311-cp311-musllinux_1_1_s390x.whl", hash = "sha256:ee04010f26d5102399bd17f8df8bc38dc7ccd7701dc77f4a68c5b8d733406958"},
    {file = "yarl-1.9.4-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:49a180c2e0743d5d6e0b4d1a9e5f633c62eca3f8a86ba5dd3c471060e352ca98"},
    {file = "yarl-1.9.4-cp311-cp311-win32.whl", hash = "sha256:81eb57278deb6098a5b62e88ad8281b2ba09f2f1147c4767522353eaa6260b31"},
    {file = "yarl-1.9.4-cp311-cp311-win_amd64.whl", hash = "sha256:d1d2532b340b692880261c15aee4dc94dd22ca5d61b9db9a8a361953d36410b1"},
    {file = "yarl-1.9.4-cp312-cp312-macosx_10_9_universal2.whl", hash = "sha256:0d2454f0aef65ea81037759be5ca9947539667eecebca092733b2eb43c965a81"},
    {file = "yarl-1.9.4-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:44d8ffbb9c06e5a7f529f38f53eda23e50d1ed33c6c869e01481d3fafa6b8142"},
    {file = "yarl-1.9.4-cp312-cp312-macosx_11_0_arm64.whl", hash = "sha256:aaaea1e536f98754a6e5c56091baa1b6ce2f2700cc4a00b0d49eca8dea471074"},
    {file = "yarl-1.9.4-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:3777ce5536d17989c91696db1d459574e9a9bd37660ea7ee4d3344579bb6f129"},
    {file = "yarl-1.9.4-cp312-cp312-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:9fc5fc1eeb029757349ad26bbc5880557389a03fa6ada41703db5e068881e5f2"},
    {file = "yarl-1.9.4-cp312-cp312-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:ea65804b5dc88dacd4a40279af0cdadcfe74b3e5b4c897aa0d81cf86927fee78"},
    {file = "yarl-1.9.4-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:aa102d6d280a5455ad6a0f9e6d769989638718e938a6a0a2ff3f4a7ff8c62cc4"},
    {file = "yarl-1.9.4-cp312-cp312-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:09efe4615ada057ba2d30df871d2f668af661e971dfeedf0c159927d48bbeff0"},
    {file = "yarl-1.9.4-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:008d3e808d03ef28542372d01057fd09168419cdc8f848efe2804f894ae03e51"},
    {file = "yarl-1.9.4-cp312-cp312-musllinux_1_1_i686.whl", hash = "sha256:6f5cb257bc2ec58f437da2b37a8cd48f666db96d47b8a3115c29f316313654ff"},
    {file = "yarl-1.9.4-cp312-cp312-musllinux_1_1_ppc64le.whl", hash = "sha256:992f18e0ea248ee03b5a6e8b3b4738850ae7dbb172cc41c966462801cbf62cf7"},
    {file = "yarl-1.9.4-cp312-cp312-musllinux_1_1_s390x.whl", hash = "sha256:0e9d124c191d5b881060a9e5060627694c3bdd1fe24c5eecc8d5d7d0eb6faabc"},
    {file = "yarl-1.9.4-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:3986b6f41ad22988e53d5778f91855dc0399b043fc8946d4f2e68af22ee9ff10"},
    {file = "yarl-1.9.4-cp312-cp312-win32.whl", hash = "sha256:4b21516d181cd77ebd06ce160ef8cc2a5e9ad35fb1c5930882baff5ac865eee7"},
    {file = "yarl-1.9.4-cp312-cp312-win_amd64.whl", hash = "sha256:a9bd00dc3bc395a662900f33f74feb3e757429e545d831eef5bb280252631984"},
    {file = "yarl-1.9.4-cp37-cp37m-macosx_10_9_x86_64.whl", hash = "sha256:63b20738b5aac74e239622d2fe30df4fca4942a86e31bf47a81a0e94c14df94f"},
    {file = "yarl-1.9.4-cp37-cp37m-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:d7d7f7de27b8944f1fee2c26a88b4dabc2409d2fea7a9ed3df79b67277644e17"},
    {file = "yarl-1.9.4-cp37-cp37m-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:c74018551e31269d56fab81a728f683667e7c28c04e807ba08f8c9e3bba32f14"},
    {file = "yarl-1.9.4-cp37-cp37m-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:ca06675212f94e7a610e85ca36948bb8fc023e458dd6c63ef71abfd482481aa5"},
    {file = "yarl-1.9.4-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:5aef935237d60a51a62b86249839b51345f47564208c6ee615ed2a40878dccdd"},
    {file = "yarl-1.9.4-cp37-cp37m-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:2b134fd795e2322b7684155b7855cc99409d10b2e408056db2b93b51a52accc7"},
    {file = "yarl-1.9.4-cp37-cp37m-musllinux_1_1_aarch64.whl", hash = "sha256:d25039a474c4c72a5ad4b52495056f843a7ff07b632c1b92ea9043a3d9950f6e"},
    {file = "yarl-1.9.4-cp37-cp37m-musllinux_1_1_i686.whl", hash = "sha256:f7d6b36dd2e029b6bcb8a13cf19664c7b8e19ab3a58e0fefbb5b8461447ed5ec"},
    {file = "yarl-1.9.4-cp37-cp37m-musllinux_1_1_ppc64le.whl", hash = "sha256:957b4774373cf6f709359e5c8c4a0af9f6d7875db657adb0feaf8d6cb3c3964c"},
    {file = "yarl-1.9.4-cp37-cp37m-musllinux_1_1_s390x.whl", hash = "sha256:d7eeb6d22331e2fd42fce928a81c697c9ee2d51400bd1a28803965883e13cead"},
    {file = "yarl-1.9.4-cp37-cp37m-musllinux_1_1_x86_64.whl", hash = "sha256:6a962e04b8f91f8c4e5917e518d17958e3bdee71fd1d8b88cdce74dd0ebbf434"},
    {file = "yarl-1.9.4-cp37-cp37m-win32.whl", hash = "sha256:f3bc6af6e2b8f92eced34ef6a96ffb248e863af20ef4fde9448cc8c9b858b749"},
    {file = "yarl-1.9.4-cp37-cp37m-win_amd64.whl", hash = "sha256:ad4d7a90a92e528aadf4965d685c17dacff3df282db1121136c382dc0b6014d2"},
    {file = "yarl-1.9.4-cp38-cp38-macosx_10_9_universal2.whl", hash = "sha256:ec61d826d80fc293ed46c9dd26995921e3a82146feacd952ef0757236fc137be"},
    {file = "yarl-1.9.4-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:8be9e837ea9113676e5754b43b940b50cce76d9ed7d2461df1af39a8ee674d9f"},
    {file = "yarl-1.9.4-cp38-cp38-macosx_11_0_arm64.whl", hash = "sha256:bef596fdaa8f26e3d66af846bbe77057237cb6e8efff8cd7cc8dff9a62278bbf"},
    {file = "yarl-1.9.4-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:2d47552b6e52c3319fede1b60b3de120fe83bde9b7bddad11a69fb0af7db32f1"},
    {file = "yarl-1.9.4-cp38-cp38-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:84fc30f71689d7fc9168b92788abc977dc8cefa806909565fc2951d02f6b7d57"},
    {file = "yarl-1.9.4-cp38-cp38-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:4aa9741085f635934f3a2583e16fcf62ba835719a8b2b28fb2917bb0537c1dfa"},
    {file = "yarl-1.9.4-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:206a55215e6d05dbc6c98ce598a59e6fbd0c493e2de4ea6cc2f4934d5a18d130"},
    {file = "yarl-1.9.4-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:07574b007ee20e5c375a8fe4a0789fad26db905f9813be0f9fef5a68080de559"},
    {file = "yarl-1.9.4-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:5a2e2433eb9344a163aced6a5f6c9222c0786e5a9e9cac2c89f0b28433f56e23"},
    {file = "yarl-1.9.4-cp38-cp38-musllinux_1_1_i686.whl", hash = "sha256:6ad6d10ed9b67a382b45f29ea028f92d25bc0bc1daf6c5b801b90b5aa70fb9ec"},
    {file = "yarl-1.9.4-cp38-cp38-musllinux_1_1_ppc64le.whl", hash = "sha256:6fe79f998a4052d79e1c30eeb7d6c1c1056ad33300f682465e1b4e9b5a188b78"},
    {file = "yarl-1.9.4-cp38-cp38-musllinux_1_1_s390x.whl", hash = "sha256:a825ec844298c791fd28ed14ed1bffc56a98d15b8c58a20e0e08c1f5f2bea1be"},
    {file = "yarl-1.9.4-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:8619d6915b3b0b34420cf9b2bb6d81ef59d984cb0fde7544e9ece32b4b3043c3"},
    {file = "yarl-1.9.4-cp38-cp38-win32.whl", hash = "sha256:686a0c2f85f83463272ddffd4deb5e591c98aac1897d65e92319f729c320eece"},
    {file = "yarl-1.9.4-cp38-cp38-win_amd64.whl", hash = "sha256:a00862fb23195b6b8322f7d781b0dc1d82cb3bcac346d1e38689370cc1cc398b"},
    {file = "yarl-1.9.4-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:604f31d97fa493083ea21bd9b92c419012531c4e17ea6da0f65cacdcf5d0bd27"},
    {file = "yarl-1.9.4-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:8a854227cf581330ffa2c4824d96e52ee621dd571078a252c25e3a3b3d94a1b1"},
    {file = "yarl-1.9.4-cp39-cp39-macosx_11_0_arm64.whl", hash = "sha256:ba6f52cbc7809cd8d74604cce9c14868306ae4aa0282016b641c661f981a6e91"},
    {file = "yarl-1.9.4-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:a6327976c7c2f4ee6816eff196e25385ccc02cb81427952414a64811037bbc8b"},
    {file = "yarl-1.9.4-cp39-cp39-manylinux_2_17_ppc64le.manylinux2014_ppc64le.whl", hash = "sha256:8397a3817d7dcdd14bb266283cd1d6fc7264a48c186b986f32e86d86d35fbac5"},
    {file = "yarl-1.9.4-cp39-cp39-manylinux_2_17_s390x.manylinux2014_s390x.whl", hash = "sha256:e0381b4ce23ff92f8170080c97678040fc5b08da85e9e292292aba67fdac6c34"},
    {file = "yarl-1.9.4-cp39-cp39-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:23d32a2594cb5d565d358a92e151315d1b2268bc10f4610d098f96b147370136"},
    {file = "yarl-1.9.4-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:ddb2a5c08a4eaaba605340fdee8fc08e406c56617566d9643ad8bf6852778fc7"},
    {file = "yarl-1.9.4-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:26a1dc6285e03f3cc9e839a2da83bcbf31dcb0d004c72d0730e755b33466c30e"},
    {file = "yarl-1.9.4-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:18580f672e44ce1238b82f7fb87d727c4a131f3a9d33a5e0e82b793362bf18b4"},
    {file = "yarl-1.9.4-cp39-cp39-musllinux_1_1_ppc64le.whl", hash = "sha256:29e0f83f37610f173eb7e7b5562dd71467993495e568e708d99e9d1944f561ec"},
    {file = "yarl-1.9.4-cp39-cp39-musllinux_1_1_s390x.whl", hash = "sha256:1f23e4fe1e8794f74b6027d7cf19dc25f8b63af1483d91d595d4a07eca1fb26c"},
    {file = "yarl-1.9.4-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:db8e58b9d79200c76956cefd14d5c90af54416ff5353c5bfd7cbe58818e26ef0"},
    {file = "yarl-1.9.4-cp39-cp39-win32.whl", hash = "sha256:c7224cab95645c7ab53791022ae77a4509472613e839dab722a72abe5a684575"},
    {file = "yarl-1.9.4-cp39-cp39-win_amd64.whl", hash = "sha256:824d6c50492add5da9374875ce72db7a0733b29c2394890aef23d533106e2b15"},
    {file = "yarl-1.9.4-py3-none-any.whl", hash = "sha256:928cecb0ef9d5a7946eb6ff58417ad2fe9375762382f1bf5c55e61645f2c43ad"},
    {file = "yarl-1.9.4.tar.gz", hash = "sha256:566db86717cf8080b99b58b083b773a908ae40f06681e87e589a976faf8246bf"},
]

[package.dependencies]
idna = ">=2.0"
multidict = ">=4.0"

[[package]]
name = "zopfli"
version = "0.2.3"
description = "Zopfli module for python"
optional = false
python-versions = ">=3.8"
files = [
    {file = "zopfli-0.2.3-cp310-cp310-macosx_10_9_universal2.whl", hash = "sha256:52438999888715a378fc6fe1477ab7813e9e9b58a27a38d2ad7be0e396b1ab2e"},
    {file = "zopfli-0.2.3-cp310-cp310-macosx_10_9_x86_64.whl", hash = "sha256:6020a3533c6c7be09db9e59c2a8f3f894bf5d8e95cc01890d82114c923317c57"},
    {file = "zopfli-0.2.3-cp310-cp310-manylinux_2_12_i686.manylinux2010_i686.whl", hash = "sha256:72349c78da402e6784bd9c5f4aff5cc7017bd969016ec07b656722f7f29fc975"},
    {file = "zopfli-0.2.3-cp310-cp310-manylinux_2_12_x86_64.manylinux2010_x86_64.whl", hash = "sha256:711d4fde9cb99e1a9158978e9d1624a37cdd170ff057f6340059514fcf38e808"},
    {file = "zopfli-0.2.3-cp310-cp310-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:ae890df6e5f1e8fa0697cafd848826decce0ac53e54e5a018fd97775e3a354c0"},
    {file = "zopfli-0.2.3-cp310-cp310-musllinux_1_1_aarch64.whl", hash = "sha256:40b830244e6458ef982b4a5ebb0f228986d481408bae557a95eeece2c5ede4e6"},
    {file = "zopfli-0.2.3-cp310-cp310-musllinux_1_1_i686.whl", hash = "sha256:7bc89b71d1c4677f708cc162f40a4560f78f5f4c6aa6d884b423df7d38e8ba0b"},
    {file = "zopfli-0.2.3-cp310-cp310-musllinux_1_1_x86_64.whl", hash = "sha256:f07997453e7777e19ef0a2445cc1b90e1bb90c623dd77554325932dea6350fee"},
    {file = "zopfli-0.2.3-cp310-cp310-win32.whl", hash = "sha256:978395a4ce5cc46db29a36cdb80549b564dc7706237abaca5aac328dd5842f65"},
    {file = "zopfli-0.2.3-cp310-cp310-win_amd64.whl", hash = "sha256:61a2fcc624e8b038d4fca84ba927dc3f31df53a7284692d46aa44d16fb3f47b2"},
    {file = "zopfli-0.2.3-cp311-cp311-macosx_10_9_universal2.whl", hash = "sha256:97d2f993142fed4f9c11c1766eb53409efe7298c755cf4599c171bfedcbaddae"},
    {file = "zopfli-0.2.3-cp311-cp311-macosx_10_9_x86_64.whl", hash = "sha256:92ca61eaa1df774908c173683e23c512189bf791a7ebb49fac61324658cff490"},
    {file = "zopfli-0.2.3-cp311-cp311-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:975d45745cf6c3e3b61127e0140dcf145fa515f2021f669bd82768937b7bb1fb"},
    {file = "zopfli-0.2.3-cp311-cp311-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:d0a8e556916088fadb098ddb6eed034d5c2df3b8fba7f2488e87e8c224002eca"},
    {file = "zopfli-0.2.3-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:61abe5f11400f9c6b22be578091e28dfb9f1a61efaaeaa2da66138b03ee93072"},
    {file = "zopfli-0.2.3-cp311-cp311-musllinux_1_1_aarch64.whl", hash = "sha256:b30a922b9d73f22da2b589b35e594dcc6d144eb38ad890c542f2b92902ba9892"},
    {file = "zopfli-0.2.3-cp311-cp311-musllinux_1_1_i686.whl", hash = "sha256:08d105a49576a9e629f53a710f0009c4bf0a1d8a3239a74e41d0944f26e28a61"},
    {file = "zopfli-0.2.3-cp311-cp311-musllinux_1_1_x86_64.whl", hash = "sha256:ad2a98890045d13b0cdc93c1637990c211dc877493469afc61a097a00a70cf22"},
    {file = "zopfli-0.2.3-cp311-cp311-win32.whl", hash = "sha256:27f2b58050f84fa059db7a6ec17d98b388c18f9783551e5f97605f790f25e155"},
    {file = "zopfli-0.2.3-cp311-cp311-win_amd64.whl", hash = "sha256:ff86a2cd6b9864027861a129d6d73231b6d463f0d364ca0fdca4492390357cba"},
    {file = "zopfli-0.2.3-cp312-cp312-macosx_10_9_universal2.whl", hash = "sha256:2073b07c3ec4fcbc895bb02565a90f9f31373233979f6be398e82eacbd1105f3"},
    {file = "zopfli-0.2.3-cp312-cp312-macosx_10_9_x86_64.whl", hash = "sha256:1f25f1bb6440ed90a1d458772fa6ce53632f5fb61e435b12ae6b9b39af98d758"},
    {file = "zopfli-0.2.3-cp312-cp312-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:39d8a73bee07cf7f2c73e08508bf788bfdf28a527da353b5d3e2a0ee4aaf770c"},
    {file = "zopfli-0.2.3-cp312-cp312-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:d40373db61883f6fc8b7040c9196a16f737e3063632afd15e8b3f25e871a30e8"},
    {file = "zopfli-0.2.3-cp312-cp312-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:31c467a300ba46f55aa0ea958ea388e350eefd039cf15764bf4cd737d5eeb8a6"},
    {file = "zopfli-0.2.3-cp312-cp312-musllinux_1_1_aarch64.whl", hash = "sha256:c3c61787a90439cf68f751b2a1ab789b0805876c0cd9b58398adc212d1eeace5"},
    {file = "zopfli-0.2.3-cp312-cp312-musllinux_1_1_i686.whl", hash = "sha256:3e4675ca4c7b1215b8a53cec1831cbdb6914f91ea2f183817a06fc7b38e27642"},
    {file = "zopfli-0.2.3-cp312-cp312-musllinux_1_1_x86_64.whl", hash = "sha256:f48de4818c10c539fdd01276512043ae4ae738e0301e9cace1dd38f4bcffad6a"},
    {file = "zopfli-0.2.3-cp312-cp312-win32.whl", hash = "sha256:7769f6ca73f37dff92159127bd25b0cc7d81d3feb819d355dc7ac01ad05c673d"},
    {file = "zopfli-0.2.3-cp312-cp312-win_amd64.whl", hash = "sha256:1c5fd29730024f5fb0e2623e3853ca422bd3cf57042389c8e0e771dc47f88084"},
    {file = "zopfli-0.2.3-cp38-cp38-macosx_10_9_universal2.whl", hash = "sha256:c6555293e42e7a9154940bb18613de2abce21a855780baff8a6c372e395c59b3"},
    {file = "zopfli-0.2.3-cp38-cp38-macosx_10_9_x86_64.whl", hash = "sha256:40665bf0bacc8b82652a1af4016648dd69f896afa59fc481c1d19a222aa746ea"},
    {file = "zopfli-0.2.3-cp38-cp38-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:7599ce108386d91a402969cba4f17247e33a594b21cbd662e008414ccb0b4cf7"},
    {file = "zopfli-0.2.3-cp38-cp38-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:dc59299eda2aaf57f0ee5c4b42ada0b80e3dc4c09c5bdda8ee9ae5cf93fafa9e"},
    {file = "zopfli-0.2.3-cp38-cp38-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:7ddcbc258bb5c07ebb7f6ee64c46d4e35c39c6abba2b3dfa72c0ea4daf9e65fc"},
    {file = "zopfli-0.2.3-cp38-cp38-musllinux_1_1_aarch64.whl", hash = "sha256:eef08c02295bb99c7fdca380c52e5454fa1c08025fb0bea2c7ae6c0e1e9c034b"},
    {file = "zopfli-0.2.3-cp38-cp38-musllinux_1_1_i686.whl", hash = "sha256:7ebb4e1b0f102d431830151041777c55700d12afd1e5adb5bcbce72037c1a10e"},
    {file = "zopfli-0.2.3-cp38-cp38-musllinux_1_1_x86_64.whl", hash = "sha256:9dcf7af42c11b3cf5d3fbf665799e10f54f66caea2020fe304602df83b9a1a69"},
    {file = "zopfli-0.2.3-cp38-cp38-win32.whl", hash = "sha256:0fbb6e7fc0da56835167e3c83a45b28e99ba14b671ecb8e51100ad03dfffc3d0"},
    {file = "zopfli-0.2.3-cp38-cp38-win_amd64.whl", hash = "sha256:ca9a6df3d11c2f8f0356c141523c4914a2850dd39fc213d968c0272db635eea9"},
    {file = "zopfli-0.2.3-cp39-cp39-macosx_10_9_universal2.whl", hash = "sha256:2770cf6b88e9985c79b90fd6d4c15d8dab0caa37c1c3b17773e61ce857eab586"},
    {file = "zopfli-0.2.3-cp39-cp39-macosx_10_9_x86_64.whl", hash = "sha256:5e52aaab3a93470cf0ff2bb2135a8628dda7b70f675c46f35b6a1b30e8e482f4"},
    {file = "zopfli-0.2.3-cp39-cp39-manylinux_2_17_aarch64.manylinux2014_aarch64.whl", hash = "sha256:082f030b2b7d6d4597ac517816e499c63b92130aa8f4f74a3788ebaa5770f974"},
    {file = "zopfli-0.2.3-cp39-cp39-manylinux_2_5_i686.manylinux1_i686.whl", hash = "sha256:0574372283befa5af98fb31407e1fe6822f2f9c437ef69e7fa260e49022d8a65"},
    {file = "zopfli-0.2.3-cp39-cp39-manylinux_2_5_x86_64.manylinux1_x86_64.whl", hash = "sha256:8293062567917201609b28b865289d5ddee55030c779fa9264caae4cc2e00fb3"},
    {file = "zopfli-0.2.3-cp39-cp39-musllinux_1_1_aarch64.whl", hash = "sha256:e4068d4d35b2e63898d22e1b7777d986b8f5d61fe83a77973730ce9cff1b4ba1"},
    {file = "zopfli-0.2.3-cp39-cp39-musllinux_1_1_i686.whl", hash = "sha256:2da6f30632cefda8ebe032fdcb69cf062f5a6435af9d32de82ccef320e0261f5"},
    {file = "zopfli-0.2.3-cp39-cp39-musllinux_1_1_x86_64.whl", hash = "sha256:e5f62ca9a947f09f531c721e2a3f2e0094523436b8eb5df18d71245c1924f89a"},
    {file = "zopfli-0.2.3-cp39-cp39-win32.whl", hash = "sha256:7463b42a2cee33f0a018bf8f1304da2379d6cb8111aa4e04d8f8590d0f1099e1"},
    {file = "zopfli-0.2.3-cp39-cp39-win_amd64.whl", hash = "sha256:22b1cfc398a87754730f7e268693c8eb480cb688fd645648fda85614a8b1c08c"},
    {file = "zopfli-0.2.3-pp310-pypy310_pp73-macosx_10_9_x86_64.whl", hash = "sha256:09ad5f8d7e0fe1975ca6d9fd5ad61c74233ae277982d3bc8814b599bbeb92f44"},
    {file = "zopfli-0.2.3-pp310-pypy310_pp73-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:78022777139ac973286219e9e085d9496fb6c935502d93a52bd1bed01dfc2002"},
    {file = "zopfli-0.2.3-pp310-pypy310_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:13d151d5c83980f384439c87a5511853890182c05d93444f3cb05e5ceed37d82"},
    {file = "zopfli-0.2.3-pp310-pypy310_pp73-win_amd64.whl", hash = "sha256:c1afe5ba0d957e462afbd3da116ac1a2a6d23e8a94436a95b692c5c324694a16"},
    {file = "zopfli-0.2.3-pp38-pypy38_pp73-macosx_10_9_x86_64.whl", hash = "sha256:81d61eba5a8e221b297a1dd27f1dae2785a14a5524cc1e144da53705cf90d5c4"},
    {file = "zopfli-0.2.3-pp38-pypy38_pp73-win_amd64.whl", hash = "sha256:f69b161b4d49e256ab285c6c6ee1cf217fda864a9b175d24fa0a0b8c2de9ff13"},
    {file = "zopfli-0.2.3-pp39-pypy39_pp73-macosx_10_9_x86_64.whl", hash = "sha256:57f93802e5ddb20647747ee4039a2e18a26e91bac4c41d3d75a2b2c97f270549"},
    {file = "zopfli-0.2.3-pp39-pypy39_pp73-manylinux_2_12_i686.manylinux2010_i686.manylinux_2_17_i686.manylinux2014_i686.whl", hash = "sha256:6225bbc33c4f803cdc1e71e3028af96dd0e1ed3cf061780d1bf05648df616a05"},
    {file = "zopfli-0.2.3-pp39-pypy39_pp73-manylinux_2_17_x86_64.manylinux2014_x86_64.whl", hash = "sha256:deffa15253a43a597e8ebf82ca1908bd70b3bf899da163b017d49ddd5e12732a"},
    {file = "zopfli-0.2.3-pp39-pypy39_pp73-win_amd64.whl", hash = "sha256:84321886cf3e80e086e0f6f7b765975343aafa61165315bb8db514d0bec2d887"},
    {file = "zopfli-0.2.3.zip", hash = "sha256:dbc9841bedd736041eb5e6982cd92da93bee145745f5422f3795f6f258cdc6ef"},
]

[package.extras]
test = ["pytest"]

[metadata]
lock-version = "2.0"
python-versions = ">=3.10,<4.0"
content-hash = "4b6f0cde8464ab9651f394cbbce6d27c780877a3ed04ef02a75761d5b559d762"

```````




`../gpt-researcher/examples/sample_report.py`:

```````py
from gpt_researcher import GPTResearcher
import asyncio


async def main():
    """
    This is a sample script that shows how to run a research report.
    """
    # Query
    query = "What happened in the latest burning man floods?"

    # Report Type
    report_type = "research_report"

    # Initialize the researcher
    researcher = GPTResearcher(query=query, report_type=report_type, config_path=None)
    # Conduct research on the given query
    await researcher.conduct_research()
    # Write the report
    report = await researcher.write_report()
    
    return report


if __name__ == "__main__":
    asyncio.run(main())

```````




`../gpt-researcher/main.py`:

```````py
from backend.server import app
from dotenv import load_dotenv
load_dotenv()

if __name__ == "__main__":
    import uvicorn

    uvicorn.run(app, host="0.0.0.0", port=8000)
```````




`../gpt-researcher/poetry.toml`:

```````toml
[virtualenvs]
in-project = true
```````




`../gpt-researcher/LICENSE`:

```````
MIT License

Copyright (c) 2024 Assaf Elovic

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

```````




`../gpt-researcher/gpt_researcher/master/agent.py`:

```````py
import asyncio
import time

from gpt_researcher.config import Config
from gpt_researcher.context.compression import ContextCompressor
from gpt_researcher.master.functions import *
from gpt_researcher.memory import Memory
from gpt_researcher.utils.enum import ReportType


class GPTResearcher:
    """
    GPT Researcher
    """

    def __init__(
        self,
        query: str,
        report_type: str = ReportType.ResearchReport.value,
        source_urls=None,
        config_path=None,
        websocket=None,
        agent=None,
        role=None,
        parent_query: str = "",
        subtopics: list = [],
        visited_urls: set = set()
    ):
        """
        Initialize the GPT Researcher class.
        Args:
            query: str,
            report_type: str
            source_urls
            config_path
            websocket
            agent
            role
            parent_query: str
            subtopics: list
            visited_urls: set
        """
        self.query = query
        self.agent = agent
        self.role = role
        self.report_type = report_type
        self.report_prompt = get_prompt_by_report_type(self.report_type)  # this validates the report type
        self.websocket = websocket
        self.cfg = Config(config_path)
        self.retriever = get_retriever(self.cfg.retriever)
        self.context = []
        self.source_urls = source_urls
        self.memory = Memory(self.cfg.embedding_provider)
        self.visited_urls = visited_urls

        # Only relevant for DETAILED REPORTS
        # --------------------------------------

        # Stores the main query of the detailed report
        self.parent_query = parent_query

        # Stores all the user provided subtopics
        self.subtopics = subtopics

    async def conduct_research(self):
        """
        Runs the GPT Researcher to conduct research
        """
        print(f"🔎 Running research for '{self.query}'...")
        
        # Generate Agent
        if not (self.agent and self.role):
            self.agent, self.role = await choose_agent(self.query, self.cfg)
        await stream_output("logs", self.agent, self.websocket)

        # If specified, the researcher will use the given urls as the context for the research.
        if self.source_urls:
            self.context = await self.get_context_by_urls(self.source_urls)
        else:
            self.context = await self.get_context_by_search(self.query)

        time.sleep(2)

    async def write_report(self, existing_headers: list = []):
        """
        Writes the report based on research conducted

        Returns:
            str: The report
        """
        # Write Research Report
        if self.report_type == "custom_report":
            self.role = self.cfg.agent_role if self.cfg.agent_role else self.role

        await stream_output("logs", f"✍️ Writing summary for research task: {self.query}...", self.websocket)

        if self.report_type == "custom_report":
            self.role = (
                self.cfg.agent_role if self.cfg.agent_role else self.role
            )
        elif self.report_type == "subtopic_report":
            report = await generate_report(
                query=self.query,
                context=self.context,
                agent_role_prompt=self.role,
                report_type=self.report_type,
                websocket=self.websocket,
                cfg=self.cfg,
                main_topic=self.parent_query,
                existing_headers=existing_headers
            )
        else:
            report = await generate_report(
                query=self.query,
                context=self.context,
                agent_role_prompt=self.role,
                report_type=self.report_type,
                websocket=self.websocket,
                cfg=self.cfg
            )

        return report

    async def get_context_by_urls(self, urls):
        """
            Scrapes and compresses the context from the given urls
        """
        new_search_urls = await self.get_new_urls(urls)
        await stream_output("logs",
                            f"🧠 I will conduct my research based on the following urls: {new_search_urls}...",
                            self.websocket)
        scraped_sites = scrape_urls(new_search_urls, self.cfg)
        return await self.get_similar_content_by_query(self.query, scraped_sites)

    async def get_context_by_search(self, query):
        """
           Generates the context for the research task by searching the query and scraping the results
        Returns:
            context: List of context
        """
        context = []
        # Generate Sub-Queries including original query
        sub_queries = await get_sub_queries(query, self.role, self.cfg, self.parent_query, self.report_type) + [query]
        await stream_output("logs",
                            f"🧠 I will conduct my research based on the following queries: {sub_queries}...",
                            self.websocket)

        # Using asyncio.gather to process the sub_queries asynchronously
        context = await asyncio.gather(*[self.process_sub_query(sub_query) for sub_query in sub_queries])
        return context

    async def process_sub_query(self, sub_query: str):
        """Takes in a sub query and scrapes urls based on it and gathers context.

        Args:
            sub_query (str): The sub-query generated from the original query

        Returns:
            str: The context gathered from search
        """
        await stream_output("logs", f"\n🔎 Running research for '{sub_query}'...", self.websocket)

        scraped_sites = await self.scrape_sites_by_query(sub_query)
        content = await self.get_similar_content_by_query(sub_query, scraped_sites)

        if content:
            await stream_output("logs", f"📃 {content}", self.websocket)
        else:
            await stream_output("logs", f"🤷 No content found for '{sub_query}'...", self.websocket)
        return content

    async def get_new_urls(self, url_set_input):
        """ Gets the new urls from the given url set.
        Args: url_set_input (set[str]): The url set to get the new urls from
        Returns: list[str]: The new urls from the given url set
        """

        new_urls = []
        for url in url_set_input:
            if url not in self.visited_urls:
                await stream_output("logs", f"✅ Adding source url to research: {url}\n", self.websocket)

                self.visited_urls.add(url)
                new_urls.append(url)

        return new_urls

    async def scrape_sites_by_query(self, sub_query):
        """
        Runs a sub-query
        Args:
            sub_query:

        Returns:
            Summary
        """
        # Get Urls
        retriever = self.retriever(sub_query)
        search_results = retriever.search(
            max_results=self.cfg.max_search_results_per_query)
        new_search_urls = await self.get_new_urls([url.get("href") for url in search_results])

        # Scrape Urls
        # await stream_output("logs", f"📝Scraping urls {new_search_urls}...\n", self.websocket)
        await stream_output("logs", f"🤔 Researching for relevant information...\n", self.websocket)
        scraped_content_results = scrape_urls(new_search_urls, self.cfg)
        return scraped_content_results

    async def get_similar_content_by_query(self, query, pages):
        await stream_output("logs", f"📝 Getting relevant content based on query: {query}...", self.websocket)
        # Summarize Raw Data
        context_compressor = ContextCompressor(
            documents=pages, embeddings=self.memory.get_embeddings())
        # Run Tasks
        return context_compressor.get_context(query, max_results=8)

    ########################################################################################

    # DETAILED REPORT

    async def write_introduction(self):
        # Construct Report Introduction from main topic research
        introduction = await get_report_introduction(self.query, self.context, self.role, self.cfg, self.websocket)

        return introduction

    async def get_subtopics(self):
        """
        This async function generates subtopics based on user input and other parameters.

        Returns:
          The `get_subtopics` function is returning the `subtopics` that are generated by the
        `construct_subtopics` function.
        """
        await stream_output("logs", f"🤔 Generating subtopics...", self.websocket)

        subtopics = await construct_subtopics(
            task=self.query,
            data=self.context,
            config=self.cfg,
            # This is a list of user provided subtopics
            subtopics=self.subtopics,
        )

        await stream_output("logs", f"📋Subtopics: {subtopics}", self.websocket)

        return subtopics

```````




`../gpt-researcher/gpt_researcher/master/__init__.py`:

```````py
from .agent import GPTResearcher

__all__ = ['GPTResearcher']
```````




`../gpt-researcher/gpt_researcher/master/prompts.py`:

```````py
from datetime import datetime, timezone
import warnings
from gpt_researcher.utils.enum import ReportType


def generate_search_queries_prompt(question: str, parent_query: str, report_type: str, max_iterations: int=3,):
    """ Generates the search queries prompt for the given question.
    Args: 
        question (str): The question to generate the search queries prompt for
        parent_query (str): The main question (only relevant for detailed reports)
        report_type (str): The report type
        max_iterations (int): The maximum number of search queries to generate
    
    Returns: str: The search queries prompt for the given question
    """
    
    if report_type == ReportType.DetailedReport.value:
        task = f"{parent_query} : {question}"
    else:
        task = question

    return f'Write {max_iterations} google search queries to search online that form an objective opinion from the following task: "{task}"' \
           f'Use the current date if needed: {datetime.now().strftime("%B %d, %Y")}.\n' \
           f'Also include in the queries specified task details such as locations, names, etc.\n' \
           f'You must respond with a list of strings in the following format: ["query 1", "query 2", "query 3"].'


def generate_report_prompt(question, context, report_format="apa", total_words=1000):
    """ Generates the report prompt for the given question and research summary.
    Args: question (str): The question to generate the report prompt for
            research_summary (str): The research summary to generate the report prompt for
    Returns: str: The report prompt for the given question and research summary
    """

    return f'Information: """{context}"""\n\n' \
           f'Using the above information, answer the following' \
           f' query or task: "{question}" in a detailed report --' \
           " The report should focus on the answer to the query, should be well structured, informative," \
           f" in depth and comprehensive, with facts and numbers if available and a minimum of {total_words} words.\n" \
           "You should strive to write the report as long as you can using all relevant and necessary information provided.\n" \
           "You must write the report with markdown syntax.\n " \
           f"Use an unbiased and journalistic tone. \n" \
           "You MUST determine your own concrete and valid opinion based on the given information. Do NOT deter to general and meaningless conclusions.\n" \
           f"You MUST write all used source urls at the end of the report as references, and make sure to not add duplicated sources, but only one reference for each.\n" \
           "Every url should be hyperlinked: [url website](url)"\
           """
            Additionally, you MUST include hyperlinks to the relevant URLs wherever they are referenced in the report : 
        
            eg:    
                # Report Header
                
                This is a sample text. ([url website](url))
            """\
            f"You MUST write the report in {report_format} format.\n " \
            f"Cite search results using inline notations. Only cite the most \
            relevant results that answer the query accurately. Place these citations at the end \
            of the sentence or paragraph that reference them.\n"\
            f"Please do your best, this is very important to my career. " \
            f"Assume that the current date is {datetime.now().strftime('%B %d, %Y')}"


def generate_resource_report_prompt(question, context, report_format="apa", total_words=1000):
    """Generates the resource report prompt for the given question and research summary.

    Args:
        question (str): The question to generate the resource report prompt for.
        context (str): The research summary to generate the resource report prompt for.

    Returns:
        str: The resource report prompt for the given question and research summary.
    """
    return f'"""{context}"""\n\nBased on the above information, generate a bibliography recommendation report for the following' \
           f' question or topic: "{question}". The report should provide a detailed analysis of each recommended resource,' \
           ' explaining how each source can contribute to finding answers to the research question.\n' \
           'Focus on the relevance, reliability, and significance of each source.\n' \
           'Ensure that the report is well-structured, informative, in-depth, and follows Markdown syntax.\n' \
           'Include relevant facts, figures, and numbers whenever available.\n' \
           'The report should have a minimum length of 700 words.\n' \
        'You MUST include all relevant source urls.'\
        'Every url should be hyperlinked: [url website](url)'


def generate_custom_report_prompt(query_prompt, context, report_format="apa", total_words=1000):
    return f'"{context}"\n\n{query_prompt}'


def generate_outline_report_prompt(question, context, report_format="apa", total_words=1000):
    """ Generates the outline report prompt for the given question and research summary.
    Args: question (str): The question to generate the outline report prompt for
            research_summary (str): The research summary to generate the outline report prompt for
    Returns: str: The outline report prompt for the given question and research summary
    """

    return f'"""{context}""" Using the above information, generate an outline for a research report in Markdown syntax' \
           f' for the following question or topic: "{question}". The outline should provide a well-structured framework' \
           ' for the research report, including the main sections, subsections, and key points to be covered.' \
           ' The research report should be detailed, informative, in-depth, and a minimum of 1,200 words.' \
           ' Use appropriate Markdown syntax to format the outline and ensure readability.'


def auto_agent_instructions():
    return """
        This task involves researching a given topic, regardless of its complexity or the availability of a definitive answer. The research is conducted by a specific server, defined by its type and role, with each server requiring distinct instructions.
        Agent
        The server is determined by the field of the topic and the specific name of the server that could be utilized to research the topic provided. Agents are categorized by their area of expertise, and each server type is associated with a corresponding emoji.

        examples:
        task: "should I invest in apple stocks?"
        response: 
        {
            "server": "💰 Finance Agent",
            "agent_role_prompt: "You are a seasoned finance analyst AI assistant. Your primary goal is to compose comprehensive, astute, impartial, and methodically arranged financial reports based on provided data and trends."
        }
        task: "could reselling sneakers become profitable?"
        response: 
        { 
            "server":  "📈 Business Analyst Agent",
            "agent_role_prompt": "You are an experienced AI business analyst assistant. Your main objective is to produce comprehensive, insightful, impartial, and systematically structured business reports based on provided business data, market trends, and strategic analysis."
        }
        task: "what are the most interesting sites in Tel Aviv?"
        response:
        {
            "server:  "🌍 Travel Agent",
            "agent_role_prompt": "You are a world-travelled AI tour guide assistant. Your main purpose is to draft engaging, insightful, unbiased, and well-structured travel reports on given locations, including history, attractions, and cultural insights."
        }
    """


def generate_summary_prompt(query, data):
    """ Generates the summary prompt for the given question and text.
    Args: question (str): The question to generate the summary prompt for
            text (str): The text to generate the summary prompt for
    Returns: str: The summary prompt for the given question and text
    """

    return f'{data}\n Using the above text, summarize it based on the following task or query: "{query}".\n If the ' \
           f'query cannot be answered using the text, YOU MUST summarize the text in short.\n Include all factual ' \
           f'information such as numbers, stats, quotes, etc if available. '


################################################################################################

# DETAILED REPORT PROMPTS

def generate_subtopics_prompt() -> str:
    return """
                Provided the main topic:
                
                {task}
                
                and research data:
                
                {data}
                
                - Construct a list of subtopics which indicate the headers of a report document to be generated on the task. 
                - These are a possible list of subtopics : {subtopics}.
                - There should NOT be any duplicate subtopics.
                - Limit the number of subtopics to a maximum of {max_subtopics}
                - Finally order the subtopics by their tasks, in a relevant and meaningful order which is presentable in a detailed report
                
                "IMPORTANT!":
                - Every subtopic MUST be relevant to the main topic and provided research data ONLY!
                
                {format_instructions}
            """


def generate_subtopic_report_prompt(
    current_subtopic,
    existing_headers,
    main_topic,
    context,
    report_format="apa",
    total_words=1000,
) -> str:

    return f"""
    "Context":
    "{context}"
    
    "Main Topic and Subtopic":
    Using the latest information available, construct a detailed report on the subtopic: {current_subtopic} under the main topic: {main_topic}.
    You must limit the number of subsections to a maximum of 5.
    
    "Content Focus":
    - The report should focus on answering the question, be well-structured, informative, in-depth, and include facts and numbers if available.
    - Use markdown syntax and follow the {report_format.upper()} format.
    
    "Structure and Formatting":
    - As this sub-report will be part of a larger report, include only the main body divided into suitable subtopics without any introduction, conclusion, or reference section.
    
    - Include hyperlinks to relevant URLs wherever referenced in the report, for example:
    
        # Report Header
        
        This is a sample text. ([url website](url))
    
    "Existing Subtopic Reports":
    - This is a list of existing subtopic reports and their section headers:
    
        {existing_headers}.
    
    - Do not use any of the above headers or related details to avoid duplicates. Use smaller Markdown headers (e.g., H2 or H3) for content structure, avoiding the largest header (H1) as it will be used for the larger report's heading.
    
    "Date":
    Assume the current date is {datetime.now(timezone.utc).strftime('%B %d, %Y')} if required.
    
    "IMPORTANT!":
    - The focus MUST be on the main topic! You MUST Leave out any information un-related to it!
    - Must NOT have any introduction, conclusion, summary or reference section.
    """


def generate_report_introduction(question: str, research_summary: str = "") -> str:
    return f"""{research_summary}\n 
        Using the above latest information, Prepare a detailed report introduction on the topic -- {question}.
        - The introduction should be succinct, well-structured, informative with markdown syntax.
        - As this introduction will be part of a larger report, do NOT include any other sections, which are generally present in a report.
        - The introduction should be preceded by an H1 heading with a suitable topic for the entire report.
        - You must include hyperlinks with markdown syntax ([url website](url)) related to the sentences wherever necessary.
        Assume that the current date is {datetime.now(timezone.utc).strftime('%B %d, %Y')} if required.
    """


report_type_mapping = {
    ReportType.ResearchReport.value: generate_report_prompt,
    ReportType.ResourceReport.value: generate_resource_report_prompt,
    ReportType.OutlineReport.value: generate_outline_report_prompt,
    ReportType.CustomReport.value: generate_custom_report_prompt,
    ReportType.SubtopicReport.value: generate_subtopic_report_prompt
}


def get_prompt_by_report_type(report_type):
    prompt_by_type = report_type_mapping.get(report_type)
    default_report_type = ReportType.ResearchReport.value
    if not prompt_by_type:
        warnings.warn(f"Invalid report type: {report_type}.\n"
                        f"Please use one of the following: {', '.join([enum_value for enum_value in report_type_mapping.keys()])}\n"
                        f"Using default report type: {default_report_type} prompt.",
                        UserWarning)
        prompt_by_type = report_type_mapping.get(default_report_type)
    return prompt_by_type

```````




`../gpt-researcher/gpt_researcher/master/functions.py`:

```````py
import asyncio
import json

import markdown

from gpt_researcher.master.prompts import *
from gpt_researcher.scraper.scraper import Scraper
from gpt_researcher.utils.llm import *

def get_retriever(retriever):
    """
    Gets the retriever
    Args:
        retriever: retriever name

    Returns:
        retriever: Retriever class

    """
    match retriever:
        case "tavily":
            from gpt_researcher.retrievers import TavilySearch
            retriever = TavilySearch
        case "tavily_news":
            from gpt_researcher.retrievers import TavilyNews
            retriever = TavilyNews
        case "google":
            from gpt_researcher.retrievers import GoogleSearch
            retriever = GoogleSearch
        case "searx":
            from gpt_researcher.retrievers import SearxSearch
            retriever = SearxSearch
        case "serpapi":
            raise NotImplementedError(
                "SerpApiSearch is not fully implemented yet.")
            from gpt_researcher.retrievers import SerpApiSearch
            retriever = SerpApiSearch
        case "googleSerp":
            from gpt_researcher.retrievers import SerperSearch
            retriever = SerperSearch
        case "duckduckgo":
            from gpt_researcher.retrievers import Duckduckgo
            retriever = Duckduckgo
        case "BingSearch":
            from gpt_researcher.retrievers import BingSearch
            retriever = BingSearch

        case _:
            raise Exception("Retriever not found.")

    return retriever


async def choose_agent(query, cfg):
    """
    Chooses the agent automatically
    Args:
        query: original query
        cfg: Config

    Returns:
        agent: Agent name
        agent_role_prompt: Agent role prompt
    """
    try:
        response = await create_chat_completion(
            model=cfg.smart_llm_model,
            messages=[
                {"role": "system", "content": f"{auto_agent_instructions()}"},
                {"role": "user", "content": f"task: {query}"}],
            temperature=0,
            llm_provider=cfg.llm_provider
        )
        agent_dict = json.loads(response)
        return agent_dict["server"], agent_dict["agent_role_prompt"]
    except Exception as e:
        return "Default Agent", "You are an AI critical thinker research assistant. Your sole purpose is to write well written, critically acclaimed, objective and structured reports on given text."


async def get_sub_queries(query: str, agent_role_prompt: str, cfg, parent_query: str, report_type:str):
    """
    Gets the sub queries
    Args:
        query: original query
        agent_role_prompt: agent role prompt
        cfg: Config

    Returns:
        sub_queries: List of sub queries

    """
    max_research_iterations = cfg.max_iterations if cfg.max_iterations else 1
    response = await create_chat_completion(
        model=cfg.smart_llm_model,
        messages=[
            {"role": "system", "content": f"{agent_role_prompt}"},
            {"role": "user", "content": generate_search_queries_prompt(query, parent_query, report_type, max_iterations=max_research_iterations)}],
        temperature=0,
        llm_provider=cfg.llm_provider
    )
    sub_queries = json.loads(response)
    return sub_queries


def scrape_urls(urls, cfg=None):
    """
    Scrapes the urls
    Args:
        urls: List of urls
        cfg: Config (optional)

    Returns:
        text: str

    """
    content = []
    user_agent = cfg.user_agent if cfg else "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/119.0.0.0 Safari/537.36 Edg/119.0.0.0"
    try:
        content = Scraper(urls, user_agent, cfg.scraper).run()
    except Exception as e:
        print(f"{Fore.RED}Error in scrape_urls: {e}{Style.RESET_ALL}")
    return content


async def summarize(query, content, agent_role_prompt, cfg, websocket=None):
    """
    Asynchronously summarizes a list of URLs.

    Args:
        query (str): The search query.
        content (list): List of dictionaries with 'url' and 'raw_content'.
        agent_role_prompt (str): The role prompt for the agent.
        cfg (object): Configuration object.

    Returns:
        list: A list of dictionaries with 'url' and 'summary'.
    """

    # Function to handle each summarization task for a chunk
    async def handle_task(url, chunk):
        summary = await summarize_url(query, chunk, agent_role_prompt, cfg)
        if summary:
            await stream_output("logs", f"🌐 Summarizing url: {url}", websocket)
            await stream_output("logs", f"📃 {summary}", websocket)
        return url, summary

    # Function to split raw content into chunks of 10,000 words
    def chunk_content(raw_content, chunk_size=10000):
        words = raw_content.split()
        for i in range(0, len(words), chunk_size):
            yield ' '.join(words[i:i+chunk_size])

    # Process each item one by one, but process chunks in parallel
    concatenated_summaries = []
    for item in content:
        url = item['url']
        raw_content = item['raw_content']

        # Create tasks for all chunks of the current URL
        chunk_tasks = [handle_task(url, chunk)
                       for chunk in chunk_content(raw_content)]

        # Run chunk tasks concurrently
        chunk_summaries = await asyncio.gather(*chunk_tasks)

        # Aggregate and concatenate summaries for the current URL
        summaries = [summary for _, summary in chunk_summaries if summary]
        concatenated_summary = ' '.join(summaries)
        concatenated_summaries.append(
            {'url': url, 'summary': concatenated_summary})

    return concatenated_summaries


async def summarize_url(query, raw_data, agent_role_prompt, cfg):
    """
    Summarizes the text
    Args:
        query:
        raw_data:
        agent_role_prompt:
        cfg:

    Returns:
        summary: str

    """
    summary = ""
    try:
        summary = await create_chat_completion(
            model=cfg.fast_llm_model,
            messages=[
                {"role": "system", "content": f"{agent_role_prompt}"},
                {"role": "user", "content": f"{generate_summary_prompt(query, raw_data)}"}],
            temperature=0,
            llm_provider=cfg.llm_provider
        )
    except Exception as e:
        print(f"{Fore.RED}Error in summarize: {e}{Style.RESET_ALL}")
    return summary


async def generate_report(
    query,
    context,
    agent_role_prompt,
    report_type,
    websocket,
    cfg,
    main_topic: str = "",
    existing_headers: list = []
):
    """
    generates the final report
    Args:
        query:
        context:
        agent_role_prompt:
        report_type:
        websocket:
        cfg:
        main_topic:
        existing_headers:

    Returns:
        report:

    """
    generate_prompt = get_prompt_by_report_type(report_type)
    report = ""

    if report_type == "subtopic_report":
        content = f"{generate_prompt(query, existing_headers, main_topic, context, cfg.report_format, cfg.total_words)}"
    else:
        content = (
            f"{generate_prompt(query, context, cfg.report_format, cfg.total_words)}")

    try:
        report = await create_chat_completion(
            model=cfg.smart_llm_model,
            messages=[
                {"role": "system", "content": f"{agent_role_prompt}"},
                {"role": "user", "content": content}],
            temperature=0,
            llm_provider=cfg.llm_provider,
            stream=True,
            websocket=websocket,
            max_tokens=cfg.smart_token_limit
        )
    except Exception as e:
        print(f"{Fore.RED}Error in generate_report: {e}{Style.RESET_ALL}")

    return report


async def stream_output(type, output, websocket=None, logging=True):
    """
    Streams output to the websocket
    Args:
        type:
        output:

    Returns:
        None
    """
    if not websocket or logging:
        print(output)

    if websocket:
        await websocket.send_json({"type": type, "output": output})

async def get_report_introduction(query, context, role, config, websocket=None):
    try:
        introduction = await create_chat_completion(
            model=config.smart_llm_model,
            messages=[
                {"role": "system", "content": f"{role}"},
                {"role": "user", "content": generate_report_introduction(query, context)}],
            temperature=0,
            llm_provider=config.llm_provider,
            stream=True,
            websocket=websocket,
            max_tokens=config.smart_token_limit
        )
        
        return introduction
    except Exception as e:
        print(f"{Fore.RED}Error in generating report introduction: {e}{Style.RESET_ALL}")

    return ""
    
def extract_headers(markdown_text: str):
    # Function to extract headers from markdown text

    headers = []
    parsed_md = markdown.markdown(markdown_text)  # Parse markdown text
    lines = parsed_md.split("\n")  # Split text into lines

    stack = []  # Initialize stack to keep track of nested headers
    for line in lines:
        if line.startswith("<h") and len(line) > 1:  # Check if the line starts with an HTML header tag
            level = int(line[2])  # Extract header level
            header_text = line[
                line.index(">") + 1: line.rindex("<")
            ]  # Extract header text

            # Pop headers from the stack with higher or equal level
            while stack and stack[-1]["level"] >= level:
                stack.pop()

            header = {
                "level": level,
                "text": header_text,
            }  # Create header dictionary
            if stack:
                stack[-1].setdefault("children", []).append(
                    header
                )  # Append as child if parent exists
            else:
                # Append as top-level header if no parent exists
                headers.append(header)

            stack.append(header)  # Push header onto the stack

    return headers  # Return the list of headers


def table_of_contents(markdown_text: str):
    try:
        # Function to generate table of contents recursively
        def generate_table_of_contents(headers, indent_level=0):
            toc = ""  # Initialize table of contents string
            for header in headers:
                toc += (
                    " " * (indent_level * 4) + "- " + header["text"] + "\n"
                )  # Add header text with indentation
                if "children" in header:  # If header has children
                    toc += generate_table_of_contents(
                        header["children"], indent_level + 1
                    )  # Generate TOC for children
            return toc  # Return the generated table of contents

        # Extract headers from markdown text
        headers = extract_headers(markdown_text)
        toc = "## Table of Contents\n\n" + generate_table_of_contents(
            headers
        )  # Generate table of contents

        return toc  # Return the generated table of contents

    except Exception as e:
        print("table_of_contents Exception : ", e)  # Print exception if any
        return markdown_text  # Return original markdown text if an exception occurs

def add_source_urls(report_markdown: str, visited_urls: set):
    """
    This function takes a Markdown report and a set of visited URLs as input parameters.
    
    Args:
      report_markdown (str): The `add_source_urls` function takes in two parameters:
      visited_urls (set): Visited_urls is a set that contains URLs that have already been visited. This
    parameter is used to keep track of which URLs have already been included in the report_markdown to
    avoid duplication.
    """
    try:
        url_markdown = "\n\n\n## References\n\n"

        url_markdown += "".join(f"- [{url}]({url})\n" for url in visited_urls)

        updated_markdown_report = report_markdown + url_markdown

        return updated_markdown_report

    except Exception as e:
        print(f"Encountered exception in adding source urls : {e}")
        return report_markdown
```````




`../gpt-researcher/gpt_researcher/utils/validators.py`:

```````py
from typing import List

from pydantic import BaseModel, Field

class Subtopic(BaseModel):
    task: str = Field(description="Task name", min_length=1)

class Subtopics(BaseModel):
    subtopics: List[Subtopic] = []

```````




`../gpt-researcher/gpt_researcher/utils/enum.py`:

```````py
from enum import Enum
class ReportType(Enum):
    ResearchReport = 'research_report'
    ResourceReport = 'resource_report'
    OutlineReport = 'outline_report'
    CustomReport = 'custom_report'
    DetailedReport = 'detailed_report'
    SubtopicReport = 'subtopic_report'

```````




`../gpt-researcher/gpt_researcher/utils/llm.py`:

```````py
# libraries
from __future__ import annotations

import json
import logging
from typing import Optional

from colorama import Fore, Style
from fastapi import WebSocket
from langchain.output_parsers import PydanticOutputParser
from langchain.prompts import PromptTemplate
from langchain_openai import ChatOpenAI

from gpt_researcher.master.prompts import auto_agent_instructions, generate_subtopics_prompt

from .validators import Subtopics


def get_provider(llm_provider):
    match llm_provider:
        case "openai":
            from ..llm_provider import OpenAIProvider
            llm_provider = OpenAIProvider
        case "azureopenai":
            from ..llm_provider import AzureOpenAIProvider
            llm_provider = AzureOpenAIProvider
        case "google":
            from ..llm_provider import GoogleProvider
            llm_provider = GoogleProvider

        case _:
            raise Exception("LLM provider not found.")

    return llm_provider


async def create_chat_completion(
        messages: list,  # type: ignore
        model: Optional[str] = None,
        temperature: float = 1.0,
        max_tokens: Optional[int] = None,
        llm_provider: Optional[str] = None,
        stream: Optional[bool] = False,
        websocket: WebSocket | None = None,
) -> str:
    """Create a chat completion using the OpenAI API
    Args:
        messages (list[dict[str, str]]): The messages to send to the chat completion
        model (str, optional): The model to use. Defaults to None.
        temperature (float, optional): The temperature to use. Defaults to 0.9.
        max_tokens (int, optional): The max tokens to use. Defaults to None.
        stream (bool, optional): Whether to stream the response. Defaults to False.
        llm_provider (str, optional): The LLM Provider to use.
        webocket (WebSocket): The websocket used in the currect request
    Returns:
        str: The response from the chat completion
    """

    # validate input
    if model is None:
        raise ValueError("Model cannot be None")
    if max_tokens is not None and max_tokens > 8001:
        raise ValueError(
            f"Max tokens cannot be more than 8001, but got {max_tokens}")

    # Get the provider from supported providers
    ProviderClass = get_provider(llm_provider)
    provider = ProviderClass(
        model,
        temperature,
        max_tokens
    )

    # create response
    for _ in range(10):  # maximum of 10 attempts
        response = await provider.get_chat_response(
            messages, stream, websocket
        )
        return response

    logging.error("Failed to get response from OpenAI API")
    raise RuntimeError("Failed to get response from OpenAI API")


def choose_agent(smart_llm_model: str, llm_provider: str, task: str) -> dict:
    """Determines what server should be used
    Args:
        task (str): The research question the user asked
        smart_llm_model (str): the llm model to be used
        llm_provider (str): the llm provider used
    Returns:
        server - The server that will be used
        agent_role_prompt (str): The prompt for the server
    """
    try:
        response = create_chat_completion(
            model=smart_llm_model,
            messages=[
                {"role": "system", "content": f"{auto_agent_instructions()}"},
                {"role": "user", "content": f"task: {task}"}],
            temperature=0,
            llm_provider=llm_provider
        )
        agent_dict = json.loads(response)
        print(f"Agent: {agent_dict.get('server')}")
        return agent_dict
    except Exception as e:
        print(f"{Fore.RED}Error in choose_agent: {e}{Style.RESET_ALL}")
        return {"server": "Default Agent",
                "agent_role_prompt": "You are an AI critical thinker research assistant. Your sole purpose is to write well written, critically acclaimed, objective and structured reports on given text."}


async def construct_subtopics(task: str, data: str, config, subtopics: list = []) -> list:
    try:
        parser = PydanticOutputParser(pydantic_object=Subtopics)

        prompt = PromptTemplate(
            template=generate_subtopics_prompt(),
            input_variables=["task", "data", "subtopics", "max_subtopics"],
            partial_variables={
                "format_instructions": parser.get_format_instructions()},
        )

        print(f"\n🤖 Calling {config.smart_llm_model}...\n")

        if config.llm_provider == "openai":
            model = ChatOpenAI(model=config.smart_llm_model)
        elif config.llm_provider == "azureopenai":
            from langchain_openai import AzureChatOpenAI
            model = AzureChatOpenAI(model=config.smart_llm_model)
        else:
            return []

        chain = prompt | model | parser

        output = chain.invoke({
            "task": task,
            "data": data,
            "subtopics": subtopics,
            "max_subtopics": config.max_subtopics
        })

        return output

    except Exception as e:
        print("Exception in parsing subtopics : ", e)
        return subtopics
```````




`../gpt-researcher/gpt_researcher/context/retriever.py`:

```````py
import os
from enum import Enum
from typing import Any, Dict, List, Optional

from langchain.callbacks.manager import CallbackManagerForRetrieverRun
from langchain.schema import Document
from langchain.schema.retriever import BaseRetriever


class SearchAPIRetriever(BaseRetriever):
    """Search API retriever."""
    pages: List[Dict] = []

    def _get_relevant_documents(
        self, query: str, *, run_manager: CallbackManagerForRetrieverRun
    ) -> List[Document]:

        docs = [
            Document(
                page_content=page.get("raw_content", ""),
                metadata={
                    "title": page.get("title", ""),
                    "source": page.get("url", ""),
                },
            )
            for page in self.pages
        ]

        return docs

```````




`../gpt-researcher/gpt_researcher/context/__init__.py`:

```````py
from .compression import ContextCompressor
from .retriever import SearchAPIRetriever

__all__ = ['ContextCompressor', 'SearchAPIRetriever']

```````




`../gpt-researcher/gpt_researcher/context/compression.py`:

```````py
from .retriever import SearchAPIRetriever
from langchain.retrievers import (
    ContextualCompressionRetriever,
)
from langchain.retrievers.document_compressors import (
    DocumentCompressorPipeline,
    EmbeddingsFilter,
)
from langchain.text_splitter import RecursiveCharacterTextSplitter


class ContextCompressor:
    def __init__(self, documents, embeddings, max_results=5, **kwargs):
        self.max_results = max_results
        self.documents = documents
        self.kwargs = kwargs
        self.embeddings = embeddings
        self.similarity_threshold = 0.38

    def _get_contextual_retriever(self):
        splitter = RecursiveCharacterTextSplitter(chunk_size=1000, chunk_overlap=100)
        relevance_filter = EmbeddingsFilter(embeddings=self.embeddings,
                                            similarity_threshold=self.similarity_threshold)
        pipeline_compressor = DocumentCompressorPipeline(
            transformers=[splitter, relevance_filter]
        )
        base_retriever = SearchAPIRetriever(
            pages=self.documents
        )
        contextual_retriever = ContextualCompressionRetriever(
            base_compressor=pipeline_compressor, base_retriever=base_retriever
        )
        return contextual_retriever

    def _pretty_print_docs(self, docs, top_n):
        return f"\n".join(f"Source: {d.metadata.get('source')}\n"
                          f"Title: {d.metadata.get('title')}\n"
                          f"Content: {d.page_content}\n"
                          for i, d in enumerate(docs) if i < top_n)

    def get_context(self, query, max_results=5):
        compressed_docs = self._get_contextual_retriever()
        relevant_docs = compressed_docs.get_relevant_documents(query)
        return self._pretty_print_docs(relevant_docs, max_results)
```````




`../gpt-researcher/gpt_researcher/llm_provider/google/google.py`:

```````py
import os

from colorama import Fore, Style
from langchain_core.messages import HumanMessage, SystemMessage
from langchain_google_genai import ChatGoogleGenerativeAI


class GoogleProvider:

    def __init__(
        self,
        model,
        temperature,
        max_tokens
    ):
        # May be extended to support more google models in the future
        self.model = "gemini-pro"
        self.temperature = temperature
        self.max_tokens = max_tokens
        self.api_key = self.get_api_key()
        self.llm = self.get_llm_model()

    def get_api_key(self):
        """
        Gets the GEMINI_API_KEY
        Returns:

        """
        try:
            api_key = os.environ["GEMINI_API_KEY"]
        except:
            raise Exception(
                "GEMINI API key not found. Please set the GEMINI_API_KEY environment variable.")
        return api_key

    def get_llm_model(self):
        # Initializing the chat model
        llm = ChatGoogleGenerativeAI(
            convert_system_message_to_human=True,
            model=self.model,
            temperature=self.temperature,
            max_output_tokens=self.max_tokens,
            google_api_key=self.api_key
        )

        return llm

    def convert_messages(self, messages):
        """
        The function `convert_messages` converts messages based on their role into either SystemMessage
        or HumanMessage objects.
        
        Args:
          messages: It looks like the code snippet you provided is a function called `convert_messages`
        that takes a list of messages as input and converts each message based on its role into either a
        `SystemMessage` or a `HumanMessage`.
        
        Returns:
          The `convert_messages` function is returning a list of converted messages based on the input
        `messages`. The function checks the role of each message in the input list and creates a new
        `SystemMessage` object if the role is "system" or a new `HumanMessage` object if the role is
        "user". The function then returns a list of these converted messages.
        """
        converted_messages = []
        for message in messages:
            if message["role"] == "system":
                converted_messages.append(
                    SystemMessage(content=message["content"]))
            elif message["role"] == "user":
                converted_messages.append(
                    HumanMessage(content=message["content"]))

        return converted_messages

    async def get_chat_response(self, messages, stream, websocket=None):
        if not stream:
            # Getting output from the model chain using ainvoke for asynchronous invoking
            converted_messages = self.convert_messages(messages)
            output = await self.llm.ainvoke(converted_messages)

            return output.content

        else:
            return await self.stream_response(messages, websocket)

    async def stream_response(self, messages, websocket=None):
        paragraph = ""
        response = ""

        # Streaming the response using the chain astream method from langchain
        async for chunk in self.llm.astream(messages):
            content = chunk.content
            if content is not None:
                response += content
                paragraph += content
                if "\n" in paragraph:
                    if websocket is not None:
                        await websocket.send_json({"type": "report", "output": paragraph})
                    else:
                        print(f"{Fore.GREEN}{paragraph}{Style.RESET_ALL}")
                    paragraph = ""

        return response

```````




`../gpt-researcher/gpt_researcher/llm_provider/__init__.py`:

```````py
from .google.google import GoogleProvider
from .openai.openai import OpenAIProvider
from .azureopenai.azureopenai import AzureOpenAIProvider

__all__ = [
    "GoogleProvider",
    "OpenAIProvider",
    "AzureOpenAIProvider"
]

```````




`../gpt-researcher/gpt_researcher/llm_provider/azureopenai/azureopenai.py`:

```````py
import os

from colorama import Fore, Style
from langchain_openai import AzureChatOpenAI

'''
Please note:
Needs additional env vars such as: 
    AZURE_OPENAI_ENDPOINT  e.g. https://xxxx.openai.azure.com/",
    AZURE_OPENAI_API_KEY e.g "xxxxxxxxxxxxxxxxxxxxx",
    OPENAI_API_VERSION, e.g. "2024-03-01-preview" but needs to updated over time as API verison updates,
    AZURE_EMBEDDING_MODEL e.g. "ada2" The Azure OpenAI embedding model deployment name.

config.py settings for Azure OpenAI should look like:
    self.embedding_provider = os.getenv('EMBEDDING_PROVIDER', 'azureopenai')
    self.llm_provider = os.getenv('LLM_PROVIDER', "azureopenai")
    self.fast_llm_model = os.getenv('FAST_LLM_MODEL', "gpt-3.5-turbo-16k") #Deployment name of your GPT3.5T model as per azure OpenAI studio deployment section
    self.smart_llm_model = os.getenv('SMART_LLM_MODEL', "gpt4")  #Deployment name of your GPT4 1106-Preview+ (GPT4T) model as per azure OpenAI studio deployment section
'''
class AzureOpenAIProvider:

    def __init__(
        self,
        deployment_name,
        temperature,
        max_tokens
    ):
        self.deployment_name = deployment_name
        self.temperature = temperature
        self.max_tokens = max_tokens
        self.api_key = self.get_api_key()
        self.llm = self.get_llm_model()

    def get_api_key(self):
        """
        Gets the OpenAI API key
        Returns:

        """
        try:
            api_key = os.environ["AZURE_OPENAI_API_KEY"]
        except:
            raise Exception(
                "Azure OpenAI API key not found. Please set the AZURE_OPENAI_API_KEY environment variable.")
        return api_key

    def get_llm_model(self):
        # Initializing the chat model
        llm = AzureChatOpenAI(
            deployment_name=self.deployment_name,
            temperature=self.temperature,
            max_tokens=self.max_tokens,
            api_key=self.api_key
        )

        return llm

    async def get_chat_response(self, messages, stream, websocket=None):
        if not stream:
            # Getting output from the model chain using ainvoke for asynchronous invoking
            output = await self.llm.ainvoke(messages)

            return output.content

        else:
            return await self.stream_response(messages, websocket)

    async def stream_response(self, messages, websocket=None):
        paragraph = ""
        response = ""

        # Streaming the response using the chain astream method from langchain
        async for chunk in self.llm.astream(messages):
            content = chunk.content
            if content is not None:
                response += content
                paragraph += content
                if "\n" in paragraph:
                    if websocket is not None:
                        await websocket.send_json({"type": "report", "output": paragraph})
                    else:
                        print(f"{Fore.GREEN}{paragraph}{Style.RESET_ALL}")
                    paragraph = ""
                    
        return response

```````




`../gpt-researcher/gpt_researcher/llm_provider/openai/openai.py`:

```````py
import os

from colorama import Fore, Style
from langchain_openai import ChatOpenAI


class OpenAIProvider:

    def __init__(
        self,
        model,
        temperature,
        max_tokens
    ):
        self.model = model
        self.temperature = temperature
        self.max_tokens = max_tokens
        self.api_key = self.get_api_key()
        self.llm = self.get_llm_model()

    def get_api_key(self):
        """
        Gets the OpenAI API key
        Returns:

        """
        try:
            api_key = os.environ["OPENAI_API_KEY"]
        except:
            raise Exception(
                "OpenAI API key not found. Please set the OPENAI_API_KEY environment variable.")
        return api_key

    def get_llm_model(self):
        # Initializing the chat model
        llm = ChatOpenAI(
            model=self.model,
            temperature=self.temperature,
            max_tokens=self.max_tokens,
            api_key=self.api_key
        )

        return llm

    async def get_chat_response(self, messages, stream, websocket=None):
        if not stream:
            # Getting output from the model chain using ainvoke for asynchronous invoking
            output = await self.llm.ainvoke(messages)

            return output.content

        else:
            return await self.stream_response(messages, websocket)

    async def stream_response(self, messages, websocket=None):
        paragraph = ""
        response = ""

        # Streaming the response using the chain astream method from langchain
        async for chunk in self.llm.astream(messages):
            content = chunk.content
            if content is not None:
                response += content
                paragraph += content
                if "\n" in paragraph:
                    if websocket is not None:
                        await websocket.send_json({"type": "report", "output": paragraph})
                    else:
                        print(f"{Fore.GREEN}{paragraph}{Style.RESET_ALL}")
                    paragraph = ""
                    
        return response

```````




`../gpt-researcher/gpt_researcher/scraper/newspaper/newspaper.py`:

```````py
from newspaper import Article


class NewspaperScraper:

    def __init__(self, link, session=None):
        self.link = link
        self.session = session

    def scrape(self) -> str:
        """
        This Python function scrapes an article from a given link, extracts the title and text content,
        and returns them concatenated with a colon.
        
        Returns:
          The `scrape` method returns a string that contains the title of the article followed by a
        colon and the text of the article. If the title or text is not present, an empty string is
        returned. If an exception occurs during the scraping process, an error message is printed and an
        empty string is returned.
        """
        try:
            article = Article(
                self.link,
                language="en",
                memoize_articles=False,
                fetch_images=False,
            )
            article.download()
            article.parse()

            title = article.title
            text = article.text

            # If title, summary are not present then return None
            if not (title and text):
                return ""

            return f"{title} : {text}"

        except Exception as e:
            print("Error! : " + str(e))
            return ""

```````




`../gpt-researcher/gpt_researcher/scraper/pymupdf/pymupdf.py`:

```````py
from langchain_community.document_loaders import PyMuPDFLoader


class PyMuPDFScraper:

    def __init__(self, link, session=None):
        self.link = link
        self.session = session

    def scrape(self) -> str:
        """
        The `scrape` function uses PyMuPDFLoader to load a document from a given link and returns it as
        a string.
        
        Returns:
          The `scrape` method is returning a string representation of the `doc` object, which is loaded
        using PyMuPDFLoader from the provided link.
        """
        loader = PyMuPDFLoader(self.link)
        doc = loader.load()
        return str(doc)

```````




`../gpt-researcher/gpt_researcher/scraper/beautiful_soup/beautiful_soup.py`:

```````py
from bs4 import BeautifulSoup


class BeautifulSoupScraper:

    def __init__(self, link, session=None):
        self.link = link
        self.session = session

    def scrape(self):
        """
        This function scrapes content from a webpage by making a GET request, parsing the HTML using
        BeautifulSoup, and extracting script and style elements before returning the cleaned content.
        
        Returns:
          The `scrape` method is returning the cleaned and extracted content from the webpage specified
        by the `self.link` attribute. The method fetches the webpage content, removes script and style
        tags, extracts the text content, and returns the cleaned content as a string. If any exception
        occurs during the process, an error message is printed and an empty string is returned.
        """
        try:
            response = self.session.get(self.link, timeout=4)
            soup = BeautifulSoup(
                response.content, "lxml", from_encoding=response.encoding
            )

            for script_or_style in soup(["script", "style"]):
                script_or_style.extract()

            raw_content = self.get_content_from_url(soup)
            lines = (line.strip() for line in raw_content.splitlines())
            chunks = (phrase.strip() for line in lines for phrase in line.split("  "))
            content = "\n".join(chunk for chunk in chunks if chunk)
            return content

        except Exception as e:
            print("Error! : " + str(e))
            return ""
        
    def get_content_from_url(self, soup):
        """Get the text from the soup

        Args:
            soup (BeautifulSoup): The soup to get the text from

        Returns:
            str: The text from the soup
        """
        text = ""
        tags = ["p", "h1", "h2", "h3", "h4", "h5"]
        for element in soup.find_all(tags):  # Find all the <p> elements
            text += element.text + "\n"
        return text

```````




`../gpt-researcher/gpt_researcher/scraper/web_base_loader/web_base_loader.py`:

```````py
from langchain_community.document_loaders import WebBaseLoader


class WebBaseLoaderScraper:

    def __init__(self, link, session=None):
        self.link = link
        self.session = session

    def scrape(self) -> str:
        """
        This Python function scrapes content from a webpage using a WebBaseLoader object and returns the
        concatenated page content.
        
        Returns:
          The `scrape` method is returning a string variable named `content` which contains the
        concatenated page content from the documents loaded by the `WebBaseLoader`. If an exception
        occurs during the process, an error message is printed and an empty string is returned.
        """
        try:
            loader = WebBaseLoader(self.link)
            loader.requests_kwargs = {"verify": False}
            docs = loader.load()
            content = ""

            for doc in docs:
                content += doc.page_content

            return content

        except Exception as e:
            print("Error! : " + str(e))
            return ""

```````




`../gpt-researcher/gpt_researcher/scraper/arxiv/arxiv.py`:

```````py
from langchain_community.retrievers import ArxivRetriever


class ArxivScraper:

    def __init__(self, link, session=None):
        self.link = link
        self.session = session

    def scrape(self):
        """
        The function scrapes relevant documents from Arxiv based on a given link and returns the content
        of the first document.
        
        Returns:
          The code is returning the page content of the first document retrieved by the ArxivRetriever
        for a given query extracted from the link.
        """
        query = self.link.split("/")[-1]
        retriever = ArxivRetriever(load_max_docs=2, doc_content_chars_max=None)
        docs = retriever.get_relevant_documents(query=query)
        return docs[0].page_content

```````




`../gpt-researcher/gpt_researcher/scraper/__init__.py`:

```````py

from .beautiful_soup.beautiful_soup import BeautifulSoupScraper
from .newspaper.newspaper import NewspaperScraper
from .web_base_loader.web_base_loader import WebBaseLoaderScraper
from .arxiv.arxiv import ArxivScraper
from .pymupdf.pymupdf import PyMuPDFScraper

__all__ = [
    "BeautifulSoupScraper",
    "NewspaperScraper",
    "WebBaseLoaderScraper",
    "ArxivScraper",
    "PyMuPDFScraper"
]
```````




`../gpt-researcher/gpt_researcher/scraper/scraper.py`:

```````py
from concurrent.futures.thread import ThreadPoolExecutor
from functools import partial

import requests

from gpt_researcher.scraper import (
    ArxivScraper,
    BeautifulSoupScraper,
    NewspaperScraper,
    PyMuPDFScraper,
    WebBaseLoaderScraper,
)


class Scraper:
    """
    Scraper class to extract the content from the links
    """

    def __init__(self, urls, user_agent, scraper):
        """
        Initialize the Scraper class.
        Args:
            urls:
        """
        self.urls = urls
        self.session = requests.Session()
        self.session.headers.update({"User-Agent": user_agent})
        self.scraper = scraper

    def run(self):
        """
        Extracts the content from the links
        """
        partial_extract = partial(self.extract_data_from_link, session=self.session)
        with ThreadPoolExecutor(max_workers=20) as executor:
            contents = executor.map(partial_extract, self.urls)
        res = [content for content in contents if content["raw_content"] is not None]
        return res

    def extract_data_from_link(self, link, session):
        """
        Extracts the data from the link
        """
        content = ""
        try:
            Scraper = self.get_scraper(link)
            scraper = Scraper(link, session)
            content = scraper.scrape()

            if len(content) < 100:
                return {"url": link, "raw_content": None}
            return {"url": link, "raw_content": content}
        except Exception as e:
            return {"url": link, "raw_content": None}

    def get_scraper(self, link):
        """
        The function `get_scraper` determines the appropriate scraper class based on the provided link
        or a default scraper if none matches.

        Args:
          link: The `get_scraper` method takes a `link` parameter which is a URL link to a webpage or a
        PDF file. Based on the type of content the link points to, the method determines the appropriate
        scraper class to use for extracting data from that content.

        Returns:
          The `get_scraper` method returns the scraper class based on the provided link. The method
        checks the link to determine the appropriate scraper class to use based on predefined mappings
        in the `SCRAPER_CLASSES` dictionary. If the link ends with ".pdf", it selects the
        `PyMuPDFScraper` class. If the link contains "arxiv.org", it selects the `ArxivScraper
        """

        SCRAPER_CLASSES = {
            "pdf": PyMuPDFScraper,
            "arxiv": ArxivScraper,
            "newspaper": NewspaperScraper,
            "bs": BeautifulSoupScraper,
            "web_base_loader": WebBaseLoaderScraper,
        }

        scraper_key = None

        if link.endswith(".pdf"):
            scraper_key = "pdf"
        elif "arxiv.org" in link:
            scraper_key = "arxiv"
        else:
            scraper_key = self.scraper

        scraper_class = SCRAPER_CLASSES.get(scraper_key)
        if scraper_class is None:
            raise Exception("Scraper not found.")

        return scraper_class

```````




`../gpt-researcher/gpt_researcher/__init__.py`:

```````py
from .master import GPTResearcher
from .config import Config

__all__ = ['GPTResearcher', 'Config']

```````




`../gpt-researcher/gpt_researcher/config/config.py`:

```````py
# config file
import json
import os


class Config:
    """Config class for GPT Researcher."""

    def __init__(self, config_file: str = None):
        """Initialize the config class."""
        self.config_file = config_file if config_file else os.getenv('CONFIG_FILE')
        self.retriever = os.getenv('SEARCH_RETRIEVER', "tavily")
        self.embedding_provider = os.getenv('EMBEDDING_PROVIDER', 'openai')
        self.llm_provider = os.getenv('LLM_PROVIDER', "openai")
        self.fast_llm_model = os.getenv('FAST_LLM_MODEL', "gpt-3.5-turbo-16k")
        self.smart_llm_model = os.getenv('SMART_LLM_MODEL', "gpt-4-1106-preview")
        self.fast_token_limit = int(os.getenv('FAST_TOKEN_LIMIT', 2000))
        self.smart_token_limit = int(os.getenv('SMART_TOKEN_LIMIT', 4000))
        self.browse_chunk_max_length = int(os.getenv('BROWSE_CHUNK_MAX_LENGTH', 8192))
        self.summary_token_limit = int(os.getenv('SUMMARY_TOKEN_LIMIT', 700))
        self.temperature = float(os.getenv('TEMPERATURE', 0.55))
        self.user_agent = os.getenv('USER_AGENT', "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 "
                                                   "(KHTML, like Gecko) Chrome/119.0.0.0 Safari/537.36 Edg/119.0.0.0")
        self.max_search_results_per_query = int(os.getenv('MAX_SEARCH_RESULTS_PER_QUERY', 5))
        self.memory_backend = os.getenv('MEMORY_BACKEND', "local")
        self.total_words = int(os.getenv('TOTAL_WORDS', 1000))
        self.report_format = os.getenv('REPORT_FORMAT', "APA")
        self.max_iterations = int(os.getenv('MAX_ITERATIONS', 3))
        self.agent_role = os.getenv('AGENT_ROLE', None)
        self.scraper = os.getenv("SCRAPER", "bs")
        self.max_subtopics = os.getenv("MAX_SUBTOPICS", 3)

        self.load_config_file()

    def load_config_file(self) -> None:
        """Load the config file."""
        if self.config_file is None:
            return None
        with open(self.config_file, "r") as f:
            config = json.load(f)
        for key, value in config.items():
            self.__dict__[key] = value


```````




`../gpt-researcher/gpt_researcher/config/__init__.py`:

```````py
from .config import Config

__all__ = ['Config']
```````




`../gpt-researcher/gpt_researcher/README.md`:

```````md
# 🔎 GPT Researcher
[![Official Website](https://img.shields.io/badge/Official%20Website-tavily.com-blue?style=for-the-badge&logo=world&logoColor=white)](https://tavily.com)
[![Discord Follow](https://dcbadge.vercel.app/api/server/2pFkc83fRq?style=for-the-badge)](https://discord.com/invite/2pFkc83fRq)

[![GitHub Repo stars](https://img.shields.io/github/stars/assafelovic/gpt-researcher?style=social)](https://github.com/assafelovic/gpt-researcher)
[![Twitter Follow](https://img.shields.io/twitter/follow/tavilyai?style=social)](https://twitter.com/tavilyai)
[![PyPI version](https://badge.fury.io/py/gpt-researcher.svg)](https://badge.fury.io/py/gpt-researcher)

**GPT Researcher is an autonomous agent designed for comprehensive online research on a variety of tasks.** 

The agent can produce detailed, factual and unbiased research reports, with customization options for focusing on relevant resources, outlines, and lessons. Inspired by the recent [Plan-and-Solve](https://arxiv.org/abs/2305.04091) and [RAG](https://arxiv.org/abs/2005.11401) papers, GPT Researcher addresses issues of speed, determinism and reliability, offering a more stable performance and increased speed through parallelized agent work, as opposed to synchronous operations.

**Our mission is to empower individuals and organizations with accurate, unbiased, and factual information by leveraging the power of AI.**

#### PIP Package
> **Step 0** - Install Python 3.11 or later. [See here](https://www.tutorialsteacher.com/python/install-python) for a step-by-step guide.
> **Step 1** - install GPT Researcher package [PyPI page](https://pypi.org/project/gpt-researcher/)
```bash
$ pip install gpt-researcher
```
> **Step 2** - Create .env file with your OpenAI Key and Tavily API key or simply export it
```bash
$ export OPENAI_API_KEY={Your OpenAI API Key here}
```
```bash
$ export TAVILY_API_KEY={Your Tavily API Key here}
```
> **Step 3** - Start Coding using GPT Researcher in your own code, example:
```python
from gpt_researcher import GPTResearcher
import asyncio


async def get_report(query: str, report_type: str) -> str:
    researcher = GPTResearcher(query, report_type)
    report = await researcher.run()
    return report

if __name__ == "__main__":
    query = "what team may win the NBA finals?"
    report_type = "research_report"

    report = asyncio.run(get_report(query, report_type))
    print(report)

```



```````




`../gpt-researcher/gpt_researcher/memory/__init__.py`:

```````py
from .embeddings import Memory

```````




`../gpt-researcher/gpt_researcher/memory/embeddings.py`:

```````py
from langchain_community.vectorstores import FAISS
import os


class Memory:
    def __init__(self, embedding_provider, **kwargs):

        _embeddings = None
        match embedding_provider:
            case "ollama":
                from langchain.embeddings import OllamaEmbeddings
                _embeddings = OllamaEmbeddings(model="llama2")
            case "openai":
                from langchain_openai import OpenAIEmbeddings
                _embeddings = OpenAIEmbeddings()
            case "azureopenai":
                from langchain_openai import AzureOpenAIEmbeddings
                _embeddings = AzureOpenAIEmbeddings(deployment=os.environ["AZURE_EMBEDDING_MODEL"], chunk_size=16)
            case "huggingface":
                from langchain.embeddings import HuggingFaceEmbeddings
                _embeddings = HuggingFaceEmbeddings()

            case _:
                raise Exception("Embedding provider not found.")

        self._embeddings = _embeddings

    def get_embeddings(self):
        return self._embeddings

```````




`../gpt-researcher/gpt_researcher/retrievers/searx/searx.py`:

```````py
# Tavily API Retriever

# libraries
import os
from tavily import TavilyClient
from langchain_community.utilities import SearxSearchWrapper


class SearxSearch():
    """
    Tavily API Retriever
    """
    def __init__(self, query):
        """
        Initializes the TavilySearch object
        Args:
            query:
        """
        self.query = query
        self.api_key = self.get_api_key()
        self.client = TavilyClient(self.api_key)

    def get_api_key(self):
        """
        Gets the Tavily API key
        Returns:

        """
        # Get the API key
        try:
            api_key = os.environ["SEARX_URL"]
        except:
            raise Exception("Searx URL key not found. Please set the SEARX_URL environment variable. "
                            "You can get your key from https://searx.space/")
        return api_key

    def search(self, max_results=7):
        """
        Searches the query
        Returns:

        """
        searx = SearxSearchWrapper(searx_host=os.environ["SEARX_URL"])
        results = searx.results(self.query, max_results)
        # Normalizing results to match the format of the other search APIs
        search_response = [{"href": obj["link"], "body": obj["snippet"]} for obj in results]
        return search_response

```````




`../gpt-researcher/gpt_researcher/retrievers/google/google.py`:

```````py
# Tavily API Retriever

# libraries
import os
import requests
import json
from tavily import TavilyClient


class GoogleSearch:
    """
    Tavily API Retriever
    """
    def __init__(self, query):
        """
        Initializes the TavilySearch object
        Args:
            query:
        """
        self.query = query
        self.api_key = self.get_api_key() #GOOGLE_API_KEY
        self.cx_key = self.get_cx_key() #GOOGLE_CX_KEY
        self.client = TavilyClient(self.api_key)

    def get_api_key(self):
        """
        Gets the Tavily API key
        Returns:

        """
        # Get the API key
        try:
            api_key = os.environ["GOOGLE_API_KEY"]
        except:
            raise Exception("Google API key not found. Please set the GOOGLE_API_KEY environment variable. "
                            "You can get a key at https://developers.google.com/custom-search/v1/overview")
        return api_key

    def get_cx_key(self):
        """
        Gets the Tavily API key
        Returns:

        """
        # Get the API key
        try:
            api_key = os.environ["GOOGLE_CX_KEY"]
        except:
            raise Exception("Google CX key not found. Please set the GOOGLE_CX_KEY environment variable. "
                            "You can get a key at https://developers.google.com/custom-search/v1/overview")
        return api_key

    def search(self, max_results=7):
        """
        Searches the query
        Returns:

        """
        """Useful for general internet search queries using the Google API."""
        print("Searching with query {0}...".format(self.query))
        url = f"https://www.googleapis.com/customsearch/v1?key={self.api_key}&cx={self.cx_key}&q={self.query}&start=1"
        resp = requests.get(url)

        if resp is None:
            return
        try:
            search_results = json.loads(resp.text)
        except Exception:
            return
        if search_results is None:
            return

        results = search_results.get("items", [])
        search_results = []

        # Normalizing results to match the format of the other search APIs
        for result in results:
            # skip youtube results
            if "youtube.com" in result["link"]:
                continue
            search_result = {
                "title": result["title"],
                "href": result["link"],
                "body": result["snippet"],
            }
            search_results.append(search_result)

        return search_results

```````




`../gpt-researcher/gpt_researcher/retrievers/tavily_news/tavily_news.py`:

```````py
# Tavily API Retriever

# libraries
import os
from tavily import TavilyClient


class TavilyNews():
    """
    Tavily News API Retriever
    Retrieve news articles from the Tavily News API
    """
    def __init__(self, query):
        """
        Initializes the TavilySearch object
        Args:
            query:
        """
        self.query = query
        self.api_key = self.get_api_key()
        self.client = TavilyClient(self.api_key)

    def get_api_key(self):
        """
        Gets the Tavily API key
        Returns:

        """
        # Get the API key
        try:
            api_key = os.environ["TAVILY_API_KEY"]
        except:
            raise Exception("Tavily API key not found. Please set the TAVILY_API_KEY environment variable. "
                            "You can get a key at https://app.tavily.com")
        return api_key

    def search(self, max_results=7):
        """
        Searches the query
        Returns:

        """
        # Search the query
        results = self.client.search(self.query, search_depth="advanced", topic="news", max_results=max_results)
        # Return the results
        search_response = [{"href": obj["url"], "body": obj["content"]} for obj in results.get("results", [])]
        return search_response

```````




`../gpt-researcher/gpt_researcher/retrievers/__init__.py`:

```````py
from .tavily_search.tavily_search import TavilySearch
from .tavily_news.tavily_news import TavilyNews
from .duckduckgo.duckduckgo import Duckduckgo
from .google.google import GoogleSearch
from .serper.serper import SerperSearch
from .serpapi.serpapi import SerpApiSearch
from .searx.searx import SearxSearch
from .bing.bing import BingSearch

__all__ = [
    "TavilySearch",
    "TavilyNews",
    "Duckduckgo",
    "SerperSearch",
    "SerpApiSearch",
    "GoogleSearch",
    "SearxSearch",
    "BingSearch"
]

```````




`../gpt-researcher/gpt_researcher/retrievers/tavily_search/tavily_search.py`:

```````py
# Tavily API Retriever

# libraries
import os
from tavily import TavilyClient
from duckduckgo_search import DDGS


class TavilySearch():
    """
    Tavily API Retriever
    """
    def __init__(self, query):
        """
        Initializes the TavilySearch object
        Args:
            query:
        """
        self.query = query
        self.api_key = self.get_api_key()
        self.client = TavilyClient(self.api_key)

    def get_api_key(self):
        """
        Gets the Tavily API key
        Returns:

        """
        # Get the API key
        try:
            api_key = os.environ["TAVILY_API_KEY"]
        except:
            raise Exception("Tavily API key not found. Please set the TAVILY_API_KEY environment variable. "
                            "You can get a key at https://app.tavily.com")
        return api_key

    def search(self, max_results=7):
        """
        Searches the query
        Returns:

        """
        try:
            # Search the query
            results = self.client.search(self.query, search_depth="advanced", max_results=max_results)
            # Return the results
            search_response = [{"href": obj["url"], "body": obj["content"]} for obj in results.get("results", [])]
        except Exception as e: # Fallback in case overload on Tavily Search API
            print(f"Error: {e}")
            ddg = DDGS()
            search_response = ddg.text(self.query, region='wt-wt', max_results=max_results)
        return search_response

```````




`../gpt-researcher/gpt_researcher/retrievers/bing/bing.py`:

```````py
# Bing Search Retriever

# libraries
import os
import requests
import json


class BingSearch():
    """
    Bing Search Retriever
    """
    def __init__(self, query):
        """
        Initializes the BingSearch object
        Args:
            query:
        """
        self.query = query
        self.api_key = self.get_api_key()

    def get_api_key(self):
        """
        Gets the Bing API key
        Returns:

        """
        try:
            api_key = os.environ["BING_API_KEY"]
        except:
            raise Exception("Bing API key not found. Please set the BING_API_KEY environment variable.")
        return api_key

    def search(self, max_results=7):
        """
        Searches the query
        Returns:

        """
        print("Searching with query {0}...".format(self.query))
        """Useful for general internet search queries using the Bing API."""


        # Search the query
        url = "https://api.bing.microsoft.com/v7.0/search"

        headers = {
        'Ocp-Apim-Subscription-Key': self.api_key,
        'Content-Type': 'application/json'
        }
        params = {
            "responseFilter" : "Webpages",
            "q": self.query,
            "count": max_results,
            "setLang": "en-GB",
            "textDecorations": False,
            "textFormat": "HTML",
            "safeSearch": "Strict"
        }
        
        resp = requests.get(url, headers=headers, params=params)

        # Preprocess the results
        if resp is None:
            return
        try:
            search_results = json.loads(resp.text)
        except Exception:
            return
        if search_results is None:
            return

        results = search_results["webPages"]["value"]
        search_results = []

        # Normalize the results to match the format of the other search APIs
        for result in results:
            # skip youtube results
            if "youtube.com" in result["url"]:
                continue
            search_result = {
                "title": result["name"],
                "href": result["url"],
                "body": result["snippet"],
            }
            search_results.append(search_result)

        return search_results

```````




`../gpt-researcher/gpt_researcher/retrievers/duckduckgo/duckduckgo.py`:

```````py
from itertools import islice
from duckduckgo_search import DDGS


class Duckduckgo:
    """
    Duckduckgo API Retriever
    """
    def __init__(self, query):
        self.ddg = DDGS()
        self.query = query

    def search(self, max_results=5):
        """
        Performs the search
        :param query:
        :param max_results:
        :return:
        """
        ddgs_gen = self.ddg.text(self.query, region='wt-wt', max_results=max_results)
        return ddgs_gen
```````




`../gpt-researcher/gpt_researcher/retrievers/serper/serper.py`:

```````py
# Google Serper Retriever

# libraries
import os
import requests
import json


class SerperSearch():
    """
    Google Serper Retriever
    """
    def __init__(self, query):
        """
        Initializes the SerperSearch object
        Args:
            query:
        """
        self.query = query
        self.api_key = self.get_api_key()

    def get_api_key(self):
        """
        Gets the Serper API key
        Returns:

        """
        try:
            api_key = os.environ["SERPER_API_KEY"]
        except:
            raise Exception("Serper API key not found. Please set the SERPER_API_KEY environment variable. "
                            "You can get a key at https://serper.dev/")
        return api_key

    def search(self, max_results=7):
        """
        Searches the query
        Returns:

        """
        print("Searching with query {0}...".format(self.query))
        """Useful for general internet search queries using the Serp API."""


        # Search the query (see https://serper.dev/playground for the format)
        url = "https://google.serper.dev/search"

        headers = {
        'X-API-KEY': self.api_key,
        'Content-Type': 'application/json'
        }
        data = json.dumps({"q": self.query})

        resp = requests.request("POST", url, headers=headers, data=data)

        # Preprocess the results
        if resp is None:
            return
        try:
            search_results = json.loads(resp.text)
        except Exception:
            return
        if search_results is None:
            return

        results = search_results["organic"]
        search_results = []

        # Normalize the results to match the format of the other search APIs
        for result in results:
            # skip youtube results
            if "youtube.com" in result["link"]:
                continue
            search_result = {
                "title": result["title"],
                "href": result["link"],
                "body": result["snippet"],
            }
            search_results.append(search_result)

        return search_results

```````




`../gpt-researcher/gpt_researcher/retrievers/serpapi/serpapi.py`:

```````py
# SerpApi Retriever

# libraries
import os
import requests
import json


class SerpApiSearch():
    """
    SerpApi Retriever
    """
    def __init__(self, query):
        """
        Initializes the SerpApiSearch object
        Args:
            query:
        """
        raise NotImplementedError("SerpApiSearch is not fully implemented yet.")
        self.query = query
        self.api_key = self.get_api_key()

    def get_api_key(self):
        """
        Gets the SerpApi API key
        Returns:

        """
        try:
            api_key = os.environ["SERPAPI_API_KEY"]
        except:
            raise Exception("SerpApi API key not found. Please set the SERPAPI_API_KEY environment variable. "
                            "You can get a key at https://serpapi.com/")
        return api_key

    def search(self, max_results=7):
        """
        Searches the query
        Returns:

        """
        print("Searching with query {0}...".format(self.query))
        """Useful for general internet search queries using SerpApi."""


        # Perform the search
        # TODO: query needs to be url encoded, so the code won't work as is.
        # Encoding should look something like this (but this is untested):
        # url_encoded_query = self.query.replace(" ", "+")
        url = "https://serpapi.com/search.json?engine=google&q=" + self.query + "&api_key=" + self.api_key
        resp = requests.request("GET", url)

        # Preprocess the results
        if resp is None:
            return
        try:
            search_results = json.loads(resp.text)
        except Exception:
            return
        if search_results is None:
            return

        results = search_results["organic_results"]
        search_results = []

        # Normalize the results to match the format of the other search APIs
        for result in results:
            # skip youtube results
            if "youtube.com" in result["link"]:
                continue
            search_result = {
                "title": result["title"],
                "href": result["link"],
                "body": result["snippet"],
            }
            search_results.append(search_result)

        return search_results

```````




`../gpt-researcher/docs/docs/contribute.md`:

```````md
# Contribute

We highly welcome contributions! Please check out [contributing](https://github.com/assafelovic/gpt-researcher/blob/master/CONTRIBUTING.md) if you're interested.

Please check out our [roadmap](https://trello.com/b/3O7KBePw/gpt-researcher-roadmap) page and reach out to us via our [Discord community](https://discord.gg/2pFkc83fRq) if you're interested in joining our mission.
```````




`../gpt-researcher/docs/docs/examples/examples.md`:

```````md
# Examples

### Getting Started
```python
# install tavily
!pip install tavily-python
```

```python  
# import and connect
from tavily import TavilyClient
client = TavilyClient(api_key="")
```
```python  
# simple query using tavily's advanced search
client.search("What happened in the latest burning man floods?", search_depth="advanced")
```
### Response
```commandline
{'query': 'What happened in the latest burning man floods?',
 'follow_up_questions': ['How severe were the floods at Burning Man?',
  'What were the impacts of the floods?',
  'How did the organizers handle the floods at Burning Man?'],
 'answer': None,
 'images': None,
 'results': [{'content': "This year’s rains opened the floodgates for Burning Man criticism  Give Newsletters Site search Vox main menu Filed under: The Burning Man flameout, explained Climate change — and schadenfreude\xa0— finally caught up to the survivalist cosplayers. Share this story Share  Has Burning Man finally lost its glamour?  September 1, after most of the scheduled events and live performances were canceled due to the weather, Burning Man organizers closed routes in and out of the area, forcing attendees to stay behindShare Attendees look at a rainbow over flooding on a desert plain on September 1, 2023, after heavy rains turned the annual Burning Man festival site in Nevada's Black Rock desert into a mud...",
   'url': 'https://www.vox.com/culture/2023/9/6/23861675/burning-man-2023-mud-stranded-climate-change-playa-foot',
   'score': 0.9797,
   'raw_content': None},
  {'content': 'Tens of thousands of Burning Man festivalgoers are slowly making their way home from the Nevada desert after muddy conditions from heavy rains made it nearly impossible to leave over the weekend.  according to burningman.org.  Though the death at this year\'s Burning Man is still being investigated, a social media hoax was blamed for spreading rumors that it\'s due to a breakout of Ebola.  "Thank goodness this community knows how to take care of each other," the Instagram page for Burning Man Information Radio wrote on a post predicting more rain.News Burning Man attendees make mass exodus after being stranded in the mud at festival A caravan of festivalgoers were backed up as much as eight hours when they were finally allowed to leave...',
   'url': 'https://www.today.com/news/what-is-burning-man-flood-death-rcna103231',
   'score': 0.9691,
   'raw_content': None},
  {'content': '“It was a perfect, typical Burning Man weather until Friday — then the rain started coming down hard," said Phillip Martin, 37. "Then it turned into Mud Fest."  After more than a half-inch (1.3 centimeters) of rain fell Friday, flooding turned the playa to foot-deep mud — closing roads and forcing burners to lean on each other for help.  ABC News Video Live Shows Election 2024 538 Stream on No longer stranded, tens of thousands clean up and head home after Burning Man floods  Mark Fromson, 54, who goes by the name “Stuffy” on the playa, had been staying in an RV, but the rains forced him to find shelter at another camp, where fellow burners provided him food and cover.RENO, Nev. -- The traffic jam leaving the Burning Man festival eased up considerably Tuesday as the exodus from the mud-caked Nevada desert entered another day following massive rain that left tens of thousands of partygoers stranded for days.',
   'url': 'https://abcnews.go.com/US/wireStory/wait-times-exit-burning-man-drop-after-flooding-102936473',
   'score': 0.9648,
   'raw_content': None},
  {'content': 'Burning Man hit by heavy rains, now mud soaked.People there told to conserve food and water as they shelter in place.(Video: Josh Keppel) pic.twitter.com/DuBj0Ejtb8  More on this story Burning Man revelers begin exodus from festival after road reopens Officials investigate death at Burning Man as thousands stranded by floods  Burning Man festival-goers trapped in desert as rain turns site to mud Tens of thousands of ‘burners’ urged to conserve food and water as rain and flash floods sweep Nevada  Burning Man festivalgoers surrounded by mud in Nevada desert – video Burning Man attendees roadblocked by climate activists: ‘They have a privileged mindset’Last year, Burning Man drew approximately 80,000 people. This year, only about 60,000 were expected - with many citing the usual heat and dust and eight-hour traffic jams when they tried to leave.',
   'url': 'https://www.theguardian.com/culture/2023/sep/02/burning-man-festival-mud-trapped-shelter-in-place',
   'score': 0.9618,
   'raw_content': None},
  {'content': 'Skip links Live Navigation menu Live Death at Burning Man investigated in US, thousands stranded by flooding  Attendees trudged through mud, many barefoot or wearing plastic bags on their feet. The revellers were urged to shelter in place and conserve food, water and other supplies.  Thousands of festivalgoers remain stranded as organisers close vehicular traffic to the festival site following storm flooding in Nevada’s desert.  Authorities in Nevada are investigating a death at the site of the Burning Man festival, where thousands of attendees remained stranded after flooding from storms swept through the Nevada desert in3 Sep 2023. Authorities in Nevada are investigating a death at the site of the Burning Man festival, where thousands of attendees remained stranded after flooding from storms swept through the ...',
   'url': 'https://www.aljazeera.com/news/2023/9/3/death-under-investigation-after-storm-flooding-at-burning-man-festival',
   'score': 0.9612,
   'raw_content': None}],
 'response_time': 6.23}
```

### Sample 1: Research Report using Tavily and GPT-4 with Langchain
```python
# install lanchain
!pip install langchain
```

```python
# set up openai api key
openai_api_key = ""
```
```python
# libraries
from langchain.adapters.openai import convert_openai_messages
from langchain_community.chat_models import ChatOpenAI

# setup query
query = "What happened in the latest burning man floods?"

# run tavily search
content = client.search(query, search_depth="advanced")["results"]

# setup prompt
prompt = [{
    "role": "system",
    "content":  f'You are an AI critical thinker research assistant. '\
                f'Your sole purpose is to write well written, critically acclaimed,'\
                f'objective and structured reports on given text.'
}, {
    "role": "user",
    "content": f'Information: """{content}"""\n\n' \
               f'Using the above information, answer the following'\
               f'query: "{query}" in a detailed report --'\
               f'Please use MLA format and markdown syntax.'
}]

# run gpt-4
lc_messages = convert_openai_messages(prompt)
report = ChatOpenAI(model='gpt-4',openai_api_key=openai_api_key).invoke(lc_messages).content

# print report
print(report)
```
### Response
```commandline
# The Burning Man Festival 2023: A Festival Turned Mud Fest

**Abstract:** The Burning Man Festival of 2023 in Nevada’s Black Rock desert will be remembered for a significant event: a heavy rainfall that turned the festival site into a muddy mess, testing the community spirit of the annual event attendees and stranding tens of thousands of festival-goers. 

**Keywords:** Burning Man Festival, flooding, rainfall, mud, community spirit, Nevada, Black Rock desert, stranded attendees, shelter

---
## 1. Introduction

The Burning Man Festival, an annual event known for its art installations, free spirit, and community ethos, faced an unprecedented challenge in 2023 due to heavy rains that flooded the festival site, turning it into a foot-deep mud pit[^1^][^2^]. The festival, held in Nevada's Black Rock desert, is known for its harsh weather conditions, including heat and dust, but this was the first time the event was affected to such an extent by rainfall[^4^].

## 2. Impact of the Rain

The heavy rains started on Friday, and more than a half-inch of rain fell, leading to flooding that turned the playa into a foot-deep mud pit[^2^]. The roads were closed due to the muddy conditions, stranding tens of thousands of festival-goers[^2^][^5^]. The burners, as the attendees are known, were forced to lean on each other for help[^2^].

## 3. Community Spirit Tested

The unexpected weather conditions put the Burning Man community spirit to the test[^1^]. Festival-goers found themselves sheltering in place, conserving food and water, and helping each other out[^3^]. For instance, Mark Fromson, who had been staying in an RV, was forced to find shelter at another camp due to the rains, where fellow burners provided him with food and cover[^2^].

## 4. Exodus After Rain

Despite the challenges, the festival-goers made the best of the situation. Once the rain stopped and things dried up a bit, the party quickly resumed[^3^]. A day later than scheduled, the massive wooden effigy known as the Man was set ablaze[^5^]. As the situation improved, thousands of Burning Man attendees began their mass exodus from the festival site[^5^].

## 5. Conclusion

The Burning Man Festival of 2023 will be remembered for the community spirit shown by the attendees in the face of heavy rainfall and flooding. Although the event was marred by the weather, the festival-goers managed to make the best of the situation, demonstrating the resilience and camaraderie that the Burning Man Festival is known for.

---
**References**

[^1^]: "Attendees walk through a muddy desert plain..." NPR. 2023. https://www.npr.org/2023/09/02/1197441202/burning-man-festival-rains-floods-stranded-nevada.

[^2^]: “'It was a perfect, typical Burning Man weather until Friday...'" ABC News. 2023. https://abcnews.go.com/US/wireStory/wait-times-exit-burning-man-drop-after-flooding-102936473.

[^3^]: "The latest on the Burning Man flooding..." WUNC. 2023. https://www.wunc.org/2023-09-03/the-latest-on-the-burning-man-flooding.

[^4^]: "Burning Man hit by heavy rains, now mud soaked..." The Guardian. 2023. https://www.theguardian.com/culture/2023/sep/02/burning-man-festival-mud-trapped-shelter-in-place.

[^5^]: "One day later than scheduled, the massive wooden effigy known as the Man was set ablaze..." CNN. 2023. https://www.cnn.com/2023/09/05/us/burning-man-storms-shelter-exodus-tuesday/index.html.
```

```````




`../gpt-researcher/docs/docs/examples/examples.ipynb`:

```````ipynb
{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "6ab73899",
   "metadata": {},
   "source": [
    "# Tavily Samples"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "013eda36",
   "metadata": {},
   "source": [
    "## Setup"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "8ad25551",
   "metadata": {
    "ExecuteTime": {
     "end_time": "2023-11-08T15:57:13.339729Z",
     "start_time": "2023-11-08T15:57:11.156595Z"
    }
   },
   "outputs": [],
   "source": [
    "# install tavily\n",
    "!pip install tavily-python"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "id": "c0722950",
   "metadata": {
    "ExecuteTime": {
     "end_time": "2023-11-08T16:01:01.318977Z",
     "start_time": "2023-11-08T16:01:01.314688Z"
    }
   },
   "outputs": [],
   "source": [
    "# import and connect\n",
    "from tavily import TavilyClient\n",
    "client = TavilyClient(api_key=\"\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "id": "9328a188",
   "metadata": {
    "ExecuteTime": {
     "end_time": "2023-11-08T16:02:25.587726Z",
     "start_time": "2023-11-08T16:02:18.663961Z"
    },
    "scrolled": true
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "{'query': 'What happend in the latest burning man floods?',\n",
       " 'follow_up_questions': ['How severe were the floods at Burning Man?',\n",
       "  'What were the impacts of the floods?',\n",
       "  'How did the organizers handle the floods at Burning Man?'],\n",
       " 'answer': None,\n",
       " 'images': None,\n",
       " 'results': [{'content': \"This year’s rains opened the floodgates for Burning Man criticism  Give Newsletters Site search Vox main menu Filed under: The Burning Man flameout, explained Climate change — and schadenfreude\\xa0— finally caught up to the survivalist cosplayers. Share this story Share  Has Burning Man finally lost its glamour?  September 1, after most of the scheduled events and live performances were canceled due to the weather, Burning Man organizers closed routes in and out of the area, forcing attendees to stay behindShare Attendees look at a rainbow over flooding on a desert plain on September 1, 2023, after heavy rains turned the annual Burning Man festival site in Nevada's Black Rock desert into a mud...\",\n",
       "   'url': 'https://www.vox.com/culture/2023/9/6/23861675/burning-man-2023-mud-stranded-climate-change-playa-foot',\n",
       "   'score': 0.9797,\n",
       "   'raw_content': None},\n",
       "  {'content': 'Tens of thousands of Burning Man festivalgoers are slowly making their way home from the Nevada desert after muddy conditions from heavy rains made it nearly impossible to leave over the weekend.  according to burningman.org.  Though the death at this year\\'s Burning Man is still being investigated, a social media hoax was blamed for spreading rumors that it\\'s due to a breakout of Ebola.  \"Thank goodness this community knows how to take care of each other,\" the Instagram page for Burning Man Information Radio wrote on a post predicting more rain.News Burning Man attendees make mass exodus after being stranded in the mud at festival A caravan of festivalgoers were backed up as much as eight hours when they were finally allowed to leave...',\n",
       "   'url': 'https://www.today.com/news/what-is-burning-man-flood-death-rcna103231',\n",
       "   'score': 0.9691,\n",
       "   'raw_content': None},\n",
       "  {'content': '“It was a perfect, typical Burning Man weather until Friday — then the rain started coming down hard,\" said Phillip Martin, 37. \"Then it turned into Mud Fest.\"  After more than a half-inch (1.3 centimeters) of rain fell Friday, flooding turned the playa to foot-deep mud — closing roads and forcing burners to lean on each other for help.  ABC News Video Live Shows Election 2024 538 Stream on No longer stranded, tens of thousands clean up and head home after Burning Man floods  Mark Fromson, 54, who goes by the name “Stuffy” on the playa, had been staying in an RV, but the rains forced him to find shelter at another camp, where fellow burners provided him food and cover.RENO, Nev. -- The traffic jam leaving the Burning Man festival eased up considerably Tuesday as the exodus from the mud-caked Nevada desert entered another day following massive rain that left tens of thousands of partygoers stranded for days.',\n",
       "   'url': 'https://abcnews.go.com/US/wireStory/wait-times-exit-burning-man-drop-after-flooding-102936473',\n",
       "   'score': 0.9648,\n",
       "   'raw_content': None},\n",
       "  {'content': 'Burning Man hit by heavy rains, now mud soaked.People there told to conserve food and water as they shelter in place.(Video: Josh Keppel) pic.twitter.com/DuBj0Ejtb8  More on this story Burning Man revelers begin exodus from festival after road reopens Officials investigate death at Burning Man as thousands stranded by floods  Burning Man festival-goers trapped in desert as rain turns site to mud Tens of thousands of ‘burners’ urged to conserve food and water as rain and flash floods sweep Nevada  Burning Man festivalgoers surrounded by mud in Nevada desert – video Burning Man attendees roadblocked by climate activists: ‘They have a privileged mindset’Last year, Burning Man drew approximately 80,000 people. This year, only about 60,000 were expected - with many citing the usual heat and dust and eight-hour traffic jams when they tried to leave.',\n",
       "   'url': 'https://www.theguardian.com/culture/2023/sep/02/burning-man-festival-mud-trapped-shelter-in-place',\n",
       "   'score': 0.9618,\n",
       "   'raw_content': None},\n",
       "  {'content': 'Skip links Live Navigation menu Live Death at Burning Man investigated in US, thousands stranded by flooding  Attendees trudged through mud, many barefoot or wearing plastic bags on their feet. The revellers were urged to shelter in place and conserve food, water and other supplies.  Thousands of festivalgoers remain stranded as organisers close vehicular traffic to the festival site following storm flooding in Nevada’s desert.  Authorities in Nevada are investigating a death at the site of the Burning Man festival, where thousands of attendees remained stranded after flooding from storms swept through the Nevada desert in3 Sep 2023. Authorities in Nevada are investigating a death at the site of the Burning Man festival, where thousands of attendees remained stranded after flooding from storms swept through the ...',\n",
       "   'url': 'https://www.aljazeera.com/news/2023/9/3/death-under-investigation-after-storm-flooding-at-burning-man-festival',\n",
       "   'score': 0.9612,\n",
       "   'raw_content': None}],\n",
       " 'response_time': 6.23}"
      ]
     },
     "execution_count": 5,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# simple query using tavily's advanced search\n",
    "client.search(\"What happend in the latest burning man floods?\", search_depth=\"advanced\")"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "e98ea835",
   "metadata": {},
   "source": [
    "## Sample 1: Reseach Report using Tavily and GPT-4 with Langchain"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "b7b05128",
   "metadata": {},
   "outputs": [],
   "source": [
    "# install lanchain\n",
    "!pip install langchain"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 12,
   "id": "b2246f61",
   "metadata": {
    "ExecuteTime": {
     "end_time": "2023-11-08T16:57:59.797466Z",
     "start_time": "2023-11-08T16:57:59.793194Z"
    }
   },
   "outputs": [],
   "source": [
    "# set up openai api key\n",
    "openai_api_key = \"\""
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 13,
   "id": "c574f1b8",
   "metadata": {
    "ExecuteTime": {
     "end_time": "2023-11-08T16:59:03.572367Z",
     "start_time": "2023-11-08T16:58:01.823114Z"
    }
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "# The Burning Man Festival 2023: A Festival Turned Mud Fest\n",
      "\n",
      "**Abstract:** The Burning Man Festival of 2023 in Nevada’s Black Rock desert will be remembered for a significant event: a heavy rainfall that turned the festival site into a muddy mess, testing the community spirit of the annual event attendees and stranding tens of thousands of festival-goers. \n",
      "\n",
      "**Keywords:** Burning Man Festival, flooding, rainfall, mud, community spirit, Nevada, Black Rock desert, stranded attendees, shelter\n",
      "\n",
      "---\n",
      "## 1. Introduction\n",
      "\n",
      "The Burning Man Festival, an annual event known for its art installations, free spirit, and community ethos, faced an unprecedented challenge in 2023 due to heavy rains that flooded the festival site, turning it into a foot-deep mud pit[^1^][^2^]. The festival, held in Nevada's Black Rock desert, is known for its harsh weather conditions, including heat and dust, but this was the first time the event was affected to such an extent by rainfall[^4^].\n",
      "\n",
      "## 2. Impact of the Rain\n",
      "\n",
      "The heavy rains started on Friday, and more than a half-inch of rain fell, leading to flooding that turned the playa into a foot-deep mud pit[^2^]. The roads were closed due to the muddy conditions, stranding tens of thousands of festival-goers[^2^][^5^]. The burners, as the attendees are known, were forced to lean on each other for help[^2^].\n",
      "\n",
      "## 3. Community Spirit Tested\n",
      "\n",
      "The unexpected weather conditions put the Burning Man community spirit to the test[^1^]. Festival-goers found themselves sheltering in place, conserving food and water, and helping each other out[^3^]. For instance, Mark Fromson, who had been staying in an RV, was forced to find shelter at another camp due to the rains, where fellow burners provided him with food and cover[^2^].\n",
      "\n",
      "## 4. Exodus After Rain\n",
      "\n",
      "Despite the challenges, the festival-goers made the best of the situation. Once the rain stopped and things dried up a bit, the party quickly resumed[^3^]. A day later than scheduled, the massive wooden effigy known as the Man was set ablaze[^5^]. As the situation improved, thousands of Burning Man attendees began their mass exodus from the festival site[^5^].\n",
      "\n",
      "## 5. Conclusion\n",
      "\n",
      "The Burning Man Festival of 2023 will be remembered for the community spirit shown by the attendees in the face of heavy rainfall and flooding. Although the event was marred by the weather, the festival-goers managed to make the best of the situation, demonstrating the resilience and camaraderie that the Burning Man Festival is known for.\n",
      "\n",
      "---\n",
      "**References**\n",
      "\n",
      "[^1^]: \"Attendees walk through a muddy desert plain...\" NPR. 2023. https://www.npr.org/2023/09/02/1197441202/burning-man-festival-rains-floods-stranded-nevada.\n",
      "\n",
      "[^2^]: “'It was a perfect, typical Burning Man weather until Friday...'\" ABC News. 2023. https://abcnews.go.com/US/wireStory/wait-times-exit-burning-man-drop-after-flooding-102936473.\n",
      "\n",
      "[^3^]: \"The latest on the Burning Man flooding...\" WUNC. 2023. https://www.wunc.org/2023-09-03/the-latest-on-the-burning-man-flooding.\n",
      "\n",
      "[^4^]: \"Burning Man hit by heavy rains, now mud soaked...\" The Guardian. 2023. https://www.theguardian.com/culture/2023/sep/02/burning-man-festival-mud-trapped-shelter-in-place.\n",
      "\n",
      "[^5^]: \"One day later than scheduled, the massive wooden effigy known as the Man was set ablaze...\" CNN. 2023. https://www.cnn.com/2023/09/05/us/burning-man-storms-shelter-exodus-tuesday/index.html.\n"
     ]
    }
   ],
   "source": [
    "# libraries\n",
    "from langchain.adapters.openai import convert_openai_messages\n",
    "from langchain_community.chat_models import ChatOpenAI\n",
    "\n",
    "# setup query\n",
    "query = \"What happend in the latest burning man floods?\"\n",
    "\n",
    "# run tavily search\n",
    "content = client.search(query, search_depth=\"advanced\")[\"results\"]\n",
    "\n",
    "# setup prompt\n",
    "prompt = [{\n",
    "    \"role\": \"system\",\n",
    "    \"content\":  f'You are an AI critical thinker research assistant. '\\\n",
    "                f'Your sole purpose is to write well written, critically acclaimed,'\\\n",
    "                f'objective and structured reports on given text.'\n",
    "}, {\n",
    "    \"role\": \"user\",\n",
    "    \"content\": f'Information: \"\"\"{content}\"\"\"\\n\\n' \\\n",
    "               f'Using the above information, answer the following'\\\n",
    "               f'query: \"{query}\" in a detailed report --'\\\n",
    "               f'Please use MLA format and markdown syntax.'\n",
    "}]\n",
    "\n",
    "# run gpt-4\n",
    "lc_messages = convert_openai_messages(prompt)\n",
    "report = ChatOpenAI(model='gpt-4',openai_api_key=openai_api_key).invoke(lc_messages).content\n",
    "\n",
    "# print report\n",
    "print(report)\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "c679fbfe",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.10.6"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}

```````




`../gpt-researcher/docs/docs/tavily-api/python-sdk.md`:

```````md

# Python SDK
The [Python library](https://github.com/assafelovic/tavily-python) allows for easy interaction with the Tavily API, offering both basic and advanced search functionalities directly from your Python programs. Easily integrate smart search capabilities into your applications, harnessing Tavily's powerful search features.

## Installing 📦

```bash
pip install tavily-python
```
## Usage 🛠️
The search API has two search depth options: **basic** and **advanced**. The basic search is optimized for performance leading to faster response time. The advanced may take longer (around 5-10 seconds response time) but optimizes for quality. 

Look out for the response **content** field. Using the 'advanced' search depth will highly improve the retrieved content to be only the most related content from each site based on a relevance score. The main search method can be used as seen below:
##
```python
from tavily import TavilyClient
tavily = TavilyClient(api_key="YOUR_API_KEY")
# For basic search:
response = tavily.search(query="Should I invest in Apple in 2024?")
# For advanced search:
response = tavily.search(query="Should I invest in Apple in 2024?", search_depth="advanced")
# Get the search results as context to pass an LLM:
context = [{"url": obj["url"], "content": obj["content"]} for obj in response.results]
```
In addition, you can use other powerful methods based on your application use case as seen below:

```python
# You can easily get search result context based on any max tokens straight into your RAG.
# The response is a string of the context within the max_token limit.
tavily.get_search_context(query="What happened in the burning man floods?", search_depth="advanced", max_tokens=1500)

# You can also get a simple answer to a question including relevant sources all with a simple function call:
tavily.qna_search(query="Where does Messi play right now?")
```

## API Methods 📚

### Client
The Client class is the entry point to interacting with the Tavily API. Kickstart your journey by instantiating it with your API key.

### Methods
* **search**(query, **kwargs)
  * The **search_depth** can be either **basic** or **advanced**. The **basic** type offers a quick response, while the **advanced** type gives in-depth, quality results.
  * Additional parameters can be provided as keyword arguments. See below for a list of all available parameters.
  * Returns a JSON with all related response fields.
* **get_search_context**(query, search_depth [Optional], max_tokens [Optional], **kwargs): 
  * Performs a search and returns a string of content and sources within token limit. 
  * Useful for getting only related content from retrieved websites without having to deal with context extraction and token management.
  * Max tokens defaults to 4,000. Search Depth defaults to basic.
  * Returns a string of the most relevant content including sources that fit within the defined token limit.
* **qna_search**(query, search_depth [Optional], **kwargs): 
  * Performs a search and returns a string containing an answer to the original query including relevant sources
  * Optimal to be used as a tool for AI agents.
  * Search depth defaults to advanced for best answer results.
  * Returns a string of a short answer and related sources.

### Keyword Arguments 🖊️

* **search_depth (str)**: The depth of the search. It can be "basic" or "advanced". Default is "basic" for basic_search and "advanced" for advanced_search.

* **max_results (int)**: The number of maximum search results to return. Default is 5.

* **include_images (bool)**: Include a list of query related images in the response. Default is False.

* **include_answer (bool)**: Include a short answer to original query in the search results. Default is False.

* **include_raw_content (bool)**: Include cleaned and parsed HTML of each site search results. Default is False.

* **include_domains (list)**: A list of domains to specifically include in the search results. Default is None, which includes all domains.

* **exclude_domains (list)**: A list of domains to specifically exclude from the search results. Default is None, which doesn't exclude any domains.

### Response Example
To learn more see [REST API](https://app.tavily.com/documentation/api) documentation.
## Error Handling ⚠️

In case of an unsuccessful HTTP request, a HTTPError will be raised.

## License 📝

This project is licensed under the terms of the MIT license.

## Contact 💌

For questions, support, or to learn more, please visit [Tavily](http://tavily.com) 🌍.


```````




`../gpt-researcher/docs/docs/tavily-api/introduction.md`:

```````md
# Introduction

Tavily Search API is a search engine optimized for LLMs and RAG, aimed at efficient, quick and persistent search results. Unlike other search APIs such as Serp or Google, Tavily focuses on optimizing search for AI developers and autonomous AI agents. We take care of all the burden in searching, scraping, filtering and extracting the most relevant information from online sources. All in a single API call! 

The search API can also be used return answers to questions (for use cases such as multi-agent frameworks like autogen) and can complete comprehensive research tasks in seconds. Moreover, Tavily leverages proprietary financial, code, news, and other data internal data sources to complement online information. 

To try our API in action, you can now use GPT Researcher on our hosted version [here](https://app.tavily.com/chat) or on our [API Playground](https://app.tavily.com/playground).

## Why Choose Tavily Search API?

1. **Purpose-Built**: Tailored just for LLM Agents, we ensure the search results are optimized for [RAG](https://towardsdatascience.com/retrieval-augmented-generation-intuitively-and-exhaustively-explain-6a39d6fe6fc9). We take care of all the burden in searching, scraping, filtering and extracting information from online sources. All in a single API call! Simply pass the returned search results as context to your LLM.
2. **Versatility**: Beyond just fetching results, Tavily Search API offers precision. With customizable search depths, domain management, and parsing html content controls, you're in the driver's seat.
3. **Performance**: Committed to rapidity and efficiency, our API guarantees real-time and trusted information. Please note that we're just getting started, so performance may vary and improve over time.
4. **Integration-friendly**: We appreciate the essence of adaptability. That's why integrating our API with your existing setup is a breeze. You can choose our Python library or a simple API call or any of our supported partners such as [Langchain](https://python.langchain.com/docs/integrations/tools/tavily_search) and [LLamaIndex](https://llamahub.ai/l/tools-tavily).
5. **Transparent & Informative**: Our detailed documentation ensures you're never left in the dark. From setup basics to nuanced features, we've got you covered.

## How does the Search API work?
Current search APIs such as Google, Serp and Bing retrieve search results based on user query. However, the results are sometimes irrelevant to the goal of the search, and return simple site URLs and snippets of content which are not always relevant. Because of this, any developer would need to then scrape the sites for relevant content, filter irrelevant information, optimize the content to fit LLM context limits, and more. This tasks is a burden and requires skills to get right.

Tavily Search API aggregates over 20+ sites per a single API call, and uses proprietary AI to score, filter and rank the top most relevant sources and content to your task, query or goal. 
In addition, Tavily allows developers to add custom fields such as context and limit response tokens to enable the optimal search experience for LLMs.

Tavily can also help your AI agent make better decisions such as suggesting follow up search queries or including a short answer for cross agent communication.

Remember: With LLM hallucinations, it's crucial to optimize for RAG with the right context and information.

## Getting Started
1. **Sign Up**: Begin by [signing up](https://app.tavily.com) on our platform.
2. **Obtain Your Unique Key**: Once registered, a unique Tavily API key is generated, ensuring you a seamless connection with our services.
3. **Test Drive in the API Playground**: Before diving in, familiarize yourself by testing out endpoints in our interactive [API playground](https://app.tavily.com/playground). 
4. **Explore & Learn**: Dive into our [Python SDK](/docs/tavily-api/python-sdk) or [REST API](/docs/tavily-api/rest_api) documentation to get familiar with the various features. The documentation offers a comprehensive rundown of functionalities, supplemented with practical sample inputs and outputs.
5. **Sample Use - Research Assistant**: Want a real-world application? Check out our [Research Assistant](https://app.tavily.com/chat) — a prime example that showcases how the API can optimize your AI content generation with factual and unbiased results.
6. **Stay up to date**: Join our [Community](https://discord.gg/rkYFaa8yHy) to get latest updates on our continuous improvements and development

🙋‍♂️ Got questions? Stumbled upon an issue? Or simply intrigued? Don't hesitate! Our support team is always on standby, eager to assist. Join us, dive deep, and redefine your search experience! **[Contact us](mailto:support@tavily.com)**

```````




`../gpt-researcher/docs/docs/tavily-api/langchain.md`:

```````md
# Langchain

We're excited to partner with Langchain as their recommended search tool! 🚀
See the [Langchain blog](https://blog.langchain.dev/weblangchain/) for more details.

Tavily API can now empower your Langchain application with real time online information optimized for RAG.

### How to use Tavily API with Langchain
```python
import os
from langchain.utilities.tavily_search import TavilySearchAPIWrapper
from langchain.agents import initialize_agent, AgentType
from langchain_community.chat_models import ChatOpenAI
from langchain.tools.tavily_search import TavilySearchResults

# set up API key
os.environ["TAVILY_API_KEY"] = "..."

# set up the agent
llm = ChatOpenAI(model_name="gpt-4", temperature=0.7)
search = TavilySearchAPIWrapper()
tavily_tool = TavilySearchResults(api_wrapper=search)

# initialize the agent
agent_chain = initialize_agent(
    [tavily_tool],
    llm,
    agent=AgentType.STRUCTURED_CHAT_ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True,
)

# run the agent
agent_chain.run(
    "What happened in the latest burning man floods?",
)
```

#### Result:
```commandline
    
    
    > Entering new AgentExecutor chain...
    Thought: I'm not aware of the current situation regarding the Burning Man event. I'll need to search for recent news about any flooding that might have affected it.
    Action:
    ```
    {
      "action": "tavily_search_results_json",
      "action_input": {"query": "Burning Man floods latest news"}
    }
    ```
    Observation: [{'url': 'https://www.theguardian.com/culture/2023/sep/03/burning-man-nevada-festival-floods', 'content': 'More on this story\nMore on this story\nBurning Man revelers begin exodus from festival after road reopens\nBurning Man festival-goers trapped in desert as rain turns site to mud\n\nOfficials investigate death at Burning Man as thousands stranded by floods\n\nBurning Man festivalgoers surrounded by mud in Nevada desert – video\nBurning Man attendees roadblocked by climate activists: ‘They have a privileged mindset’\n\nin our favor. We will let you know. It could be sooner, and it could be later,” said an update on the Burning Man website on Saturday evening.'}, {'url': 'https://www.npr.org/2023/09/03/1197497458/the-latest-on-the-burning-man-flooding', 'content': "National\nThe latest on the Burning Man flooding\nClaudia Peschiutta\n\nClaudia Peschiutta\nAuthorities are investigating a death at the Burning Man festival in the Nevada desert after tens of thousands of people are stuck in camps because of rain.\nSCOTT DETROW, HOST:\n\nDETROW: Well, that's NPR's Claudia Peschiutta covered and caked in a lot of mud at Burning Man. Thanks for talking to us.\nPESCHIUTTA: Confirmed.\nDETROW: Stay dry as much as you can.\n\nwith NPR's Claudia Peschiutta, who's at her first burn, and she told me it's muddy where she is, but that she and her camp family have been making the best of things."}, {'url': 'https://www.npr.org/2023/09/03/1197497458/the-latest-on-the-burning-man-flooding', 'content': "National\nThe latest on the Burning Man flooding\nClaudia Peschiutta\n\nClaudia Peschiutta\nAuthorities are investigating a death at the Burning Man festival in the Nevada desert after tens of thousands of people are stuck in camps because of rain.\nSCOTT DETROW, HOST:\n\nDETROW: Well, that's NPR's Claudia Peschiutta covered and caked in a lot of mud at Burning Man. Thanks for talking to us.\nPESCHIUTTA: Confirmed.\nDETROW: Stay dry as much as you can.\n\nwith NPR's Claudia Peschiutta, who's at her first burn, and she told me it's muddy where she is, but that she and her camp family have been making the best of things."}, {'url': 'https://abcnews.go.com/US/burning-man-flooding-happened-stranded-festivalgoers/story?id=102908331', 'content': 'Tens of thousands of Burning Man attendees are now able to leave the festival after a downpour and massive flooding left them stranded over the weekend.\n\nIn 2013, according to a blog post in the "Burning Man Journal," a rainstorm similarly rolled in, unexpectedly "trapping 160 people on the playa overnight."\n\nABC News\nVideo\nLive\nShows\nElection 2024\n538\nStream on\nBurning Man flooding: What happened to stranded festivalgoers?\nSome 64,000 people were still on site Monday as the exodus began.\n\nBurning Man has been hosted for over 30 years, according to a statement from the organizers.'}, {'url': 'https://www.today.com/news/what-is-burning-man-flood-death-rcna103231', 'content': 'Tens of thousands of Burning Man festivalgoers are slowly making their way home from the Nevada desert after muddy conditions from heavy rains made it nearly impossible to leave over the weekend.\n\naccording to burningman.org.\n\nPresident Biden was notified of the situation and, according to a spokesperson, administration officials monitored and received updates on the latest details.\nWhy are people stranded at Burning Man?\n\n"Thank goodness this community knows how to take care of each other," the Instagram page for Burning Man Information Radio wrote on a post predicting more rain.'}]
    Thought:The latest Burning Man event was severely affected by heavy rainfall that led to flooding. This resulted in tens of thousands of festival attendees getting stuck in their camps due to the muddy conditions. As a result, the exodus from the festival was delayed. An unfortunate incident also occurred, with a death being investigated at the festival. The situation was severe enough that President Biden was informed about it and administration officials were monitoring it. However, it seems that the festival goers were able to handle the situation well, as the Burning Man community is known for looking out for each other. This is not the first time a rainstorm has disrupted the Burning Man event; a similar incident occurred in 2013 where a sudden storm trapped people overnight. 
    Action:
    ```
    {
      "action": "Final Answer",
      "action_input": "The latest Burning Man event was severely affected by heavy rainfall that led to flooding. This resulted in tens of thousands of festival attendees getting stuck in their camps due to the muddy conditions, delaying their exit from the festival. An unfortunate incident also occurred, with a death being investigated at the festival. The situation was severe enough that President Biden was informed about it and administration officials were monitoring it. However, the festival goers were able to handle the situation well, as the Burning Man community is known for looking out for each other. This is not the first time a rainstorm has disrupted the Burning Man event; a similar incident occurred in 2013 when a sudden storm trapped people overnight."
    }
    ```
    
    > Finished chain.





    'The latest Burning Man event was severely affected by heavy rainfall that led to flooding. This resulted in tens of thousands of festival attendees getting stuck in their camps due to the muddy conditions, delaying their exit from the festival. An unfortunate incident also occurred, with a death being investigated at the festival. The situation was severe enough that President Biden was informed about it and administration officials were monitoring it. However, the festival goers were able to handle the situation well, as the Burning Man community is known for looking out for each other. This is not the first time a rainstorm has disrupted the Burning Man event; a similar incident occurred in 2013 when a sudden storm trapped people overnight.'
```


```````




`../gpt-researcher/docs/docs/tavily-api/llamaindex.md`:

```````md
# LlamaIndex

This tool has a more extensive example usage documented in a Jupyter notebook [here](https://github.com/emptycrown/llama-hub/tree/main/llama_hub/tools/notebooks/tavily.ipynb)

Here's an example usage of the TavilyToolSpec.

```python
from llama_hub.tools.tavily_research import TavilyToolSpec
from llama_index.agent import OpenAIAgent

tavily_tool = TavilyToolSpec(
    api_key='your-key',
)
agent = OpenAIAgent.from_tools(tavily_tool.to_tool_list())

agent.chat('What happened in the latest Burning Man festival?')
```

`search`: Search for relevant dynamic data based on a query. Returns a list of urls and their relevant content.


This loader is designed to be used as a way to load data as a Tool in an Agent. See [here](https://github.com/emptycrown/llama-hub/tree/main) for examples.
```````




`../gpt-researcher/docs/docs/tavily-api/rest_api.md`:

```````md
# Rest API

## Overview

Tavily Search is a robust search API tailored specifically for LLM Agents. It seamlessly integrates with diverse data sources to ensure a superior, relevant search experience.

## Features

* **Curated Results**: Provides top-tier results sorted by relevance across multiple sources.
* **Speed & Efficiency**: Optimized for performance, delivering real-time results.
* **Customizable**: Easily refine search results based on various criteria.
* **Easy Integration**: Simple to integrate with existing applications.

## Base URL

`https://api.tavily.com/`


## Endpoints

### POST `/search`

Search for data based on a query.

#### Parameters
- **api_key** (required): Your unique API key.
- **query** (required): The search query string.
- **search_depth** (optional): The depth of the search. It can be **basic** or **advanced**. Default is **basic** for quick results and **advanced** for indepth high quality results but longer response time. Advanced calls equals 2 requests.
- **include_images** (optional): Include a list of query related images in the response. Default is False.
- **include_answer** (optional): Include answers in the search results. Default is False.
- **include_raw_content** (optional): Include raw content in the search results. Default is False.
- **max_results** (optional): The number of maximum search results to return. Default is 5.
- **include_domains** (optional): A list of domains to specifically include in the search results. Default is None, which includes all domains.
- **exclude_domains** (optional): A list of domains to specifically exclude from the search results. Default is None, which doesn't exclude any domains.

## Example Request

```json
{
  "api_key": "your api key",
  "query": "your search query",
  "search_depth": "basic",
  "include_answer": false,
  "include_images": true,
  "include_raw_content": false,
  "max_results": 5,
  "include_domains": [],
  "exclude_domains": []
}
```

### Response

- **answer**: The answer to your search query.
- **query**: Your search query.
- **response_time**: Your search result response time.
- **images**: A list of query related image urls.
- **follow_up_questions**: A list of suggested research follow up questions related to original query.
- **results**: A list of sorted search results ranked by relevancy. 
  - **title**: The title of the search result url.
  - **url**: The url of the search result.
  - **content**: The most query related content from the scraped url. We use proprietary AI and algorithms to extract only the most relevant content from each url, to optimize for context quality and size.
  - **raw_content**: The parsed and cleaned HTML of the site. For now includes parsed text only.
  - **score**: The relevance score of the search result.

## Example Response

```json
{
    "answer": "Your search result answer",
    "query": "Your search query",
    "response_time": "Your search result response time",
    "follow_up_questions": [
        "follow up question 1",
        "follow up question 2",
        "..."
    ],
    "images": [
      "image url 1",
      "..."
    ]
    "results": [
        {
            "title": "website's title",
            "url": "https://your-search-result-url.com",
            "content": "website's content",
            "raw_content": "website's parsed raw content",
            "score": "tavily's smart relevance score"
        },{},{},{}
    ]
}
```

### Error Codes

- **400**: Bad Request — Your request is invalid.
- **401**: Unauthorized — Your API key is wrong.
- **403**: Forbidden — The endpoint requested is hidden for administrators only.
- **404**: Not Found — The specified endpoint could not be found.
- **405**: Method Not Allowed — You tried to access an endpoint with an invalid method.
- **429**: Too Many Requests — You're requesting too many results! Slow down!
- **500**: Internal Server Error — We had a problem with our server. Try again later.
- **503**: Service Unavailable — We're temporarily offline for maintenance. Please try again later.
- **504**: Gateway Timeout — We're temporarily offline for maintenance. Please try again later.

## Authentication

Tavily Search uses API keys to allow access to the API. You can register a new API key at [https://tavily.com](https://tavily.com).

## Rate Limiting

Tavily Search API has a rate limit of 20 requests per minute.

## Support

For questions, support, or to learn more, please visit [https://tavily.com](https://tavily.com).


```````




`../gpt-researcher/docs/docs/welcome.md`:

```````md
# Introduction

Hey there! 👋

We're a team of AI researchers and developers who are passionate about building the next generation of AI assistants. 
Our mission is to empower individuals and organizations with accurate, unbiased, and factual information.

### GPT Researcher
In this digital age, quickly accessing relevant and trustworthy information is more crucial than ever. However, we've learned that none of today's search engines provide a suitable tool that provides factual, explicit and objective answers without the need to continuously click and explore multiple sites for a given research task. 

This is why we've built the trending open source **[GPT Researcher](https://github.com/assafelovic/gpt-researcher)**. GPT Researcher is an autonomous agent that takes care of the tedious task of research for you, by scraping, filtering and aggregating over 20+ web sources per a single research task. 

To learn more about GPT Researcher, check out the [documentation page](/docs/gpt-researcher/introduction).

### Tavily Search API
Building an AI agent that leverages realtime online information is not a simple task. Scraping doesn't scale and requires expertise to refine, current search engine APIs don't provide explicit information to queries but simply potential related articles (which are not always related), and are not very customziable for AI agent needs. This is why we're excited to introduce the first search engine for AI agents - **Tavily Search API**.

Tavily Search API is a search engine optimized for LLMs, aimed at efficient, quick and persistent search results. Unlike other search APIs such as Serp or Google, Tavily focuses on optimizing search for AI developers and autonomous AI agents. We take care of all the burden in searching, scraping, filtering and extracting the most relevant information from online sources. All in a single API call! 

To learn how to build your AI application with Tavily Search API, check out the [documentation page](/docs/tavily-api/introduction).

To try our API in action, you can now use GPT Researcher on our hosted version [here](https://app.tavily.com/chat) or on our [API Playground](https://app.tavily.com/playground).

If you're an AI developer looking to integrate your application with our API or seek increased API limits, **[please reach out!](mailto:support@tavily.com)**

```````




`../gpt-researcher/docs/docs/gpt-researcher/getting-started.md`:

```````md
# Getting Started
> **Step 0** - Install Python 3.11 or later. [See here](https://www.tutorialsteacher.com/python/install-python) for a step-by-step guide.

> **Step 1** - Download the project and navigate to its directory

```bash
$ git clone https://github.com/assafelovic/gpt-researcher.git
$ cd gpt-researcher
```

> **Step 3** - Set up API keys using two methods: exporting them directly or storing them in a `.env` file.

For Linux/Temporary Windows Setup, use the export method:

```bash
export OPENAI_API_KEY={Your OpenAI API Key here}
export TAVILY_API_KEY={Your Tavily API Key here}
```

For a more permanent setup, create a `.env` file in the current `gpt-researcher` folder and input the keys as follows:

```bash
OPENAI_API_KEY={Your OpenAI API Key here}
TAVILY_API_KEY={Your Tavily API Key here}
```

- **For LLM, we recommend [OpenAI GPT](https://platform.openai.com/docs/guides/gpt)**, but you can use any other LLM model (including open sources) supported by [Langchain Adapter](https://python.langchain.com/docs/guides/adapters/openai), simply change the llm model and provider in config/config.py. 
- **For search engine, we recommend [Tavily Search API](https://app.tavily.com)**, but you can also refer to other search engines of your choice by changing the search provider in config/config.py to `"duckduckgo"`, `"googleAPI"`, `"bing"`, `"googleSerp"`, or `"searx"`. Then add the corresponding env API key as seen in the config.py file.

## Quickstart

> **Step 1** - Install dependencies

```bash
$ pip install -r requirements.txt
```

> **Step 2** - Run the agent with FastAPI

```bash
$ uvicorn main:app --reload
```

> **Step 3** - Go to http://localhost:8000 on any browser and enjoy researching!

## Using Virtual Environment or Poetry
Select either based on your familiarity with each:

### Virtual Environment

#### *Establishing the Virtual Environment with Activate/Deactivate configuration*

Create a virtual environment using the `venv` package with the environment name `<your_name>`, for example, `env`. Execute the following command in the PowerShell/CMD terminal:

```bash
python -m venv env
```

To activate the virtual environment, use the following activation script in PowerShell/CMD terminal:

```bash
.\env\Scripts\activate
```

To deactivate the virtual environment, run the following deactivation script in PowerShell/CMD terminal:

```bash
deactivate
```

#### *Install the dependencies for a Virtual environment*

After activating the `env` environment, install dependencies using the `requirements.txt` file with the following command:

```bash
python -m pip install -r requirements.txt
```

<br />

### Poetry

#### *Establishing the Poetry dependencies and virtual environment with Poetry version `~1.7.1`*

Install project dependencies and simultaneously create a virtual environment for the specified project. By executing this command, Poetry reads the project's "pyproject.toml" file to determine the required dependencies and their versions, ensuring a consistent and isolated development environment. The virtual environment allows for a clean separation of project-specific dependencies, preventing conflicts with system-wide packages and enabling more straightforward dependency management throughout the project's lifecycle.

```bash
poetry install
```

#### *Activate the virtual environment associated with a Poetry project*

By running this command, the user enters a shell session within the isolated environment associated with the project, providing a dedicated space for development and execution. This virtual environment ensures that the project dependencies are encapsulated, avoiding conflicts with system-wide packages. Activating the Poetry shell is essential for seamlessly working on a project, as it ensures that the correct versions of dependencies are used and provides a controlled environment conducive to efficient development and testing.

```bash
poetry shell
```

### *Run the app*
> Launch the FastAPI application agent on a *Virtual Environment or Poetry* setup by executing the following command:
```bash
python -m uvicorn main:app --reload
```
> Visit http://localhost:8000 in any web browser and explore your research!

<br />


## Try it with Docker

> **Step 1** - Install Docker

Follow instructions at https://docs.docker.com/engine/install/

> **Step 2** - Create .env file with your OpenAI Key or simply export it

```bash
$ export OPENAI_API_KEY={Your API Key here}
$ export TAVILY_API_KEY={Your Tavily API Key here}
```

> **Step 3** - Run the application

```bash
$ docker-compose up
```

> **Step 4** - Go to http://localhost:8000 on any browser and enjoy researching!

```````




`../gpt-researcher/docs/docs/gpt-researcher/roadmap.md`:

```````md
# Roadmap

We're constantly working on additional features and improvements to our products and services. We're also working on new products and services to help you build better AI applications using GPT Researcher.

Our vision is to build the #1 autonomous research agent for AI developers and researchers, and we're excited to have you join us on this journey!

The roadmap is prioritized based on the following goals: Performance, Quality, Modularity and Conversational flexibility. The roadmap is public and can be found [here](https://trello.com/b/3O7KBePw/gpt-researcher-roadmap). 

Interested in collaborating or contributing? Check out our [contributing page](/docs/contribute) for more information.
```````




`../gpt-researcher/docs/docs/gpt-researcher/introduction.md`:

```````md
# Introduction

**GPT Researcher is an autonomous agent designed for comprehensive online research on a variety of tasks.** 

The agent can produce detailed, factual and unbiased research reports, with customization options for focusing on relevant resources, outlines, and lessons. Inspired by the recent [Plan-and-Solve](https://arxiv.org/abs/2305.04091) and [RAG](https://arxiv.org/abs/2005.11401) papers, GPT Researcher addresses issues of speed, determinism and reliability, offering a more stable performance and increased speed through parallelized agent work, as opposed to synchronous operations.

## Why GPT Researcher?

- To form objective conclusions for manual research tasks can take time, sometimes weeks to find the right resources and information.
- Current LLMs are trained on past and outdated information, with heavy risks of hallucinations, making them almost irrelevant for research tasks.
- Solutions that enable web search (such as ChatGPT + Web Plugin), only consider limited resources and content that in some cases result in superficial conclusions or biased answers.
- Using only a selection of resources can create bias in determining the right conclusions for research questions or tasks. 

## Architecture
The main idea is to run "planner" and "execution" agents, whereas the planner generates questions to research, and the execution agents seek the most related information based on each generated research question. Finally, the planner filters and aggregates all related information and creates a research report. <br /> <br /> 
The agents leverage both gpt3.5-turbo and gpt-4-turbo (128K context) to complete a research task. We optimize for costs using each only when necessary. **The average research task takes around 3 minutes to complete, and costs ~$0.1.**

<div align="center">
<img align="center" height="500" src="https://cowriter-images.s3.amazonaws.com/architecture.png" />
</div>


More specifically:
* Create a domain specific agent based on research query or task.
* Generate a set of research questions that together form an objective opinion on any given task. 
* For each research question, trigger a crawler agent that scrapes online resources for information relevant to the given task.
* For each scraped resources, summarize based on relevant information and keep track of its sources.
* Finally, filter and aggregate all summarized sources and generate a final research report.

## Demo
<iframe height="400" width="700" src="https://github.com/assafelovic/gpt-researcher/assets/13554167/a00c89a6-a295-4dd0-b58d-098a31c40fda" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## Tutorials
 - [How it Works](https://medium.com/better-programming/how-i-built-an-autonomous-ai-agent-for-online-research-93435a97c6c)
 - [How to Install](https://www.loom.com/share/04ebffb6ed2a4520a27c3e3addcdde20?sid=da1848e8-b1f1-42d1-93c3-5b0b9c3b24ea)
 - [Live Demo](https://www.loom.com/share/6a3385db4e8747a1913dd85a7834846f?sid=a740fd5b-2aa3-457e-8fb7-86976f59f9b8)

## Features
- 📝 Generate research, outlines, resources and lessons reports
- 📜 Can generate long and detailed research reports (over 2K words)
- 🌐 Aggregates over 20 web sources per research to form objective and factual conclusions
- 🖥️ Includes an easy-to-use web interface (HTML/CSS/JS)
- 🔍 Scrapes web sources with javascript support
- 📂 Keeps track and context of visited and used web sources
- 📄 Export research reports to PDF, Word and more...


## Disclaimer

This project, GPT Researcher, is an experimental application and is provided "as-is" without any warranty, express or implied. We are sharing codes for academic purposes under the MIT license. Nothing herein is academic advice, and NOT a recommendation to use in academic or research papers.

Our view on unbiased research claims:
1. The whole point of our scraping system is to reduce incorrect fact. How? The more sites we scrape the less chances of incorrect data. We are scraping 20 per research, the chances that they are all wrong is extremely low.
2. We do not aim to eliminate biases; we aim to reduce it as much as possible. **We are here as a community to figure out the most effective human/llm interactions.**
3. In research, people also tend towards biases as most have already opinions on the topics they research about. This tool scrapes many opinions and will evenly explain diverse views that a biased person would never have read.

**Please note that the use of the GPT-4 language model can be expensive due to its token usage.** By utilizing this project, you acknowledge that you are responsible for monitoring and managing your own token usage and the associated costs. It is highly recommended to check your OpenAI API usage regularly and set up any necessary limits or alerts to prevent unexpected charges.

```````




`../gpt-researcher/docs/docs/gpt-researcher/pip-package.md`:

```````md
# PIP Package

🌟 **Exciting News!** Now, you can integrate `gpt-researcher` with your apps seamlessly!

## Steps to Install GPT Researcher 🛠️

Follow these easy steps to get started:

0. **Pre-requisite**: Ensure Python 3.10+ is installed on your machine 💻
1. **Install gpt-researcher**: Grab the official package from [PyPi](https://pypi.org/project/gpt-researcher/).
```bash
pip install gpt-researcher
```
2. **Environment Variables:** Create a .env file with your OpenAI API key or simply export it
```bash
export OPENAI_API_KEY={Your OpenAI API Key here}
```
```bash
export TAVILY_API_KEY={Your Tavily API Key here}
```
3. **Start using GPT Researcher in your own codebase**

## Example Usage 📝
```python
from gpt_researcher import GPTResearcher
import asyncio


async def get_report(query: str, report_type: str) -> str:
    researcher = GPTResearcher(query, report_type)
    report = await researcher.run()
    return report

if __name__ == "__main__":
    query = "what team may win the NBA finals?"
    report_type = "research_report"

    report = asyncio.run(get_report(query, report_type))
    print(report)
```

## Specific Examples 🌐
### Example 1: Research Report 📚
```python
query = "Latest developments in renewable energy technologies"
report_type = "research_report"
```
### Example 2: Resource Report 📋
```python
query = "List of top AI conferences in 2023"
report_type = "resource_report"
```

### Example 3: Outline Report 📝
```python
query = "Outline for an article on the impact of AI in education"
report_type = "outline_report"
```

## Integration with Web Frameworks 🌍
### FastAPI Example
```python
from fastapi import FastAPI
from gpt_researcher import GPTResearcher
import asyncio

app = FastAPI()

@app.get("/report/{report_type}")
async def get_report(report_type: str, query: str):
    researcher = GPTResearcher(query, report_type)
    report = await researcher.run()
    return {"report": report}

# Run the server
# uvicorn main:app --reload
```

### Flask Example
```python
from flask import Flask, request
from gpt_researcher import GPTResearcher
import asyncio

app = Flask(__name__)

@app.route('/report/<report_type>', methods=['GET'])
def get_report(report_type):
    query = request.args.get('query')
    report = asyncio.run(GPTResearcher(query, report_type).run())
    return report

# Run the server
# flask run
```


```````




`../gpt-researcher/docs/docs/gpt-researcher/agent_frameworks.md`:

```````md
# Agent Frameworks

We are strong advocates for the future of AI agents, envisioning a world where autonomous agents communicate and collaborate as a cohesive team to undertake and complete complex tasks.

We hold the belief that research is a pivotal element in successfully tackling these complex tasks, ensuring superior outcomes.

Consider the scenario of developing a coding agent responsible for coding tasks using the latest API documentation and best practices. It would be wise to integrate an agent specializing in research to curate the most recent and relevant documentation, before crafting a technical design that would subsequently be handed off to the coding assistant tasked with generating the code. This approach is applicable across various sectors, including finance, business analysis, healthcare, marketing, and legal, among others.

One agent framework that we're excited about is [PermChain](https://github.com/langchain-ai/permchain), built by the amazing team at [Langchain](https://www.langchain.com/).
PermChain is a Python library for building stateful, multi-actor applications with LLMs. It extends the [LangChain Expression Language](https://python.langchain.com/docs/expression_language/) with the ability to coordinate multiple chains (or actors) across multiple steps of computation.

What's great about PermChain is that it follows an event driven architecture, enabling each agent to both subscribe to and publish topics, which can subsequently trigger actions among other agents within the chain. 

We've added an example for leveraging [GPT Researcher with PermChain](https://github.com/assafelovic/gpt-researcher/tree/master/examples/permchain_agents) which can be found in `/example/permchain_agents/`.

The example demonstrates a generic use case for an editorial agent team that works together to complete a research report on a given task.

## The Agent Team
The research team is made up of 3 agents:
- Researcher agent (gpt-researcher) - This agent is in charge of finding and summarizing relevant research papers.
- Editor agent - This agent is in charge of validating the correctness of the report given a set of criteria.
- Reviser agent - This agent is in charge of revising the report until it is satisfactory.

## How it works
The research agent (gpt-researcher) is in charge of finding and summarizing relevant research papers. It does this by using the following process:
- Search for relevant research papers using a search engine
- Extract the relevant information from the research papers
- Summarize the information into a report
- Send the report to the editor agent for validation
- Send the report to the reviser agent for revision
- Repeat until the report is satisfactory

## How to run
1. Install required packages:
    ```bash
    pip install -r requirements.txt
    ```
2. Run the application:
    ```bash
    python test.py
    ```
   
The agent team can be easily extended to business use cases such as generating marketing campaigns based on a specific report, or generating code based on collected documentation.

We're working on supporting more and more agent framework examples which can be found in `/examples/`
```````




`../gpt-researcher/docs/docs/gpt-researcher/example.md`:

```````md
# Agent Example

If you're interested in using GPT Researcher as a standalone agent, you can easily import it into any existing Python project. Below, is an example of calling the agent to generate a research report:

```python
from gpt_researcher import GPTResearcher
import asyncio

# It is best to define global constants at the top of your script
QUERY = "What happened in the latest burning man floods?"
REPORT_TYPE = "research_report"

async def fetch_report(query, report_type):
    """
    Fetch a research report based on the provided query and report type.
    """
    researcher = GPTResearcher(query=query, report_type=report_type, config_path=None)
    report = await researcher.run()
    return report

async def generate_research_report():
    """
    This is a sample script that executes an async main function to run a research report.
    """
    report = await fetch_report(QUERY, REPORT_TYPE)
    print(report)

if __name__ == "__main__":
    asyncio.run(generate_research_report())
```

You can further enhance this example to use the returned report as context for generating valuable content such as news article, marketing content, email templates, newsletters, etc.

You can also use GPT Researcher to gather information about code documentation, business analysis, financial information and more. All of which can be used to complete much more complex tasks that require factual and high quality realtime information.
```````




`../gpt-researcher/docs/docs/gpt-researcher/config.md`:

```````md
# Customization

The config.py enables you to customize GPT Researcher to your specific needs and preferences.

Thanks to our amazing community and contributions, GPT Researcher supports multiple LLMs and Retrievers.
In addition, GPT Researcher can be tailored to various report formats (such as APA), word count, research iterations depth, etc.

GPT Researcher defaults to our recommended suite of integrations: [OpenAI](https://platform.openai.com/docs/overview) for LLM calls and [Tavily API](https://app.tavily.com) for retrieving realtime online information.

As seen below, OpenAI still stands as the superior LLM. We assume it will stay this way for some time, and that prices will only continue to decrease, while performance and speed increase over time.

<div style={{ marginBottom: '10px' }}>
<img align="center" height="350" src="/img/leaderboard.png" />
</div>

It may not come as a surprise that our default search engine is [Tavily](https://app.tavily.com). We're aimed at building our search engine to tailor the exact needs of searching and aggregating for the most factual and unbiased information for research tasks.
We highly recommend using it with GPT Researcher, and more generally with LLM applications that are built with RAG. To learn more about our search API [see here](/docs/tavily-api/introduction)

Here is an example of the default config.py file found in `/gpt_researcher/config/`:

```python
def __init__(self, config_file: str = None):
    self.config_file = config_file
    self.retriever = "tavily"
    self.llm_provider = "openai"
    self.fast_llm_model = "gpt-3.5-turbo-16k"
    self.smart_llm_model = "gpt-4-1106-preview"
    self.fast_token_limit = 2000
    self.smart_token_limit = 4000
    self.browse_chunk_max_length = 8192
    self.summary_token_limit = 700
    self.temperature = 0.6
    self.user_agent = "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko)" \
                      " Chrome/119.0.0.0 Safari/537.36 Edg/119.0.0.0"
    self.memory_backend = "local"
    self.total_words = 1000
    self.report_format = "apa"
    self.max_iterations = 1

    self.load_config_file()
```

Please note that you can also include your own external JSON file by adding the path in the `config_file` param.

To learn more about additional LLM support you can check out the [Langchain Adapter](https://python.langchain.com/docs/guides/adapters/openai) and [Langchain supported LLMs](https://python.langchain.com/docs/integrations/llms/) documentation. Simply pass different provider names in the `llm_provider` config param.

You can also change the search engine by modifying the `retriever` param to others such as `duckduckgo`, `googleAPI`, `googleSerp`, `searx` and more. 

Please note that you might need to sign up and obtain an API key for any of the other supported retrievers and LLM providers.
```````




`../gpt-researcher/docs/docs/gpt-researcher/troubleshooting.md`:

```````md
# Troubleshooting
We're constantly working to provide a more stable version. If you're running into any issues, please first check out the resolved issues or ask us via our [Discord community](https://discord.gg/2pFkc83fRq).

**model: gpt-4 does not exist**
This relates to not having permission to use gpt-4 yet. Based on OpenAI, it will be [widely available for all by end of July](https://help.openai.com/en/articles/7102672-how-can-i-access-gpt-4).

**cannot load library 'gobject-2.0-0'**

The issue relates to the library WeasyPrint (which is used to generate PDFs from the research report). Please follow this guide to resolve it: https://doc.courtbouillon.org/weasyprint/stable/first_steps.html

**Error processing the url**

We're using [Selenium](https://www.selenium.dev) for site scraping. Some sites fail to be scraped. In these cases, restart and try running again.


**Chrome version issues**

Many users have an issue with their chromedriver because the latest chrome browser version doesn't have a compatible chrome driver yet.

To downgrade your Chrome web browser using [slimjet](https://www.slimjet.com/chrome/google-chrome-old-version.php), follow these steps. First, visit the website and scroll down to find the list of available older Chrome versions. Choose the version you wish to install
making sure it's compatible with your operating system.
Once you've selected the desired version, click on the corresponding link to download the installer. Before proceeding with the installation, it's crucial to uninstall your current version of Chrome to avoid conflicts.

It's important to check if the version you downgrade to, has a chromedriver available in the official [chrome driver website](https://chromedriver.chromium.org/downloads)

**If none of the above work, you can [try out our hosted beta](https://app.tavily.com)**
```````




`../gpt-researcher/docs/docs/reference/sidebar.json`:

```````json
{
  "items": [
    {
      "items": [
        "reference/config/config",
        "reference/config/singleton"
      ],
      "label": "config",
      "type": "category"
    },
    {
      "items": [
        "reference/processing/html",
        "reference/processing/text"
      ],
      "label": "processing",
      "type": "category"
    }
  ],
  "label": "Reference",
  "type": "category"
}
```````




`../gpt-researcher/docs/docs/reference/processing/text.md`:

```````md
---
sidebar_label: text
title: processing.text
---

Text processing functions

#### split\_text

```python
def split_text(text: str,
               max_length: int = 8192) -> Generator[str, None, None]
```

Split text into chunks of a maximum length

**Arguments**:

- `text` _str_ - The text to split
- `max_length` _int, optional_ - The maximum length of each chunk. Defaults to 8192.
  

**Yields**:

- `str` - The next chunk of text
  

**Raises**:

- `ValueError` - If the text is longer than the maximum length

#### summarize\_text

```python
def summarize_text(url: str,
                   text: str,
                   question: str,
                   driver: Optional[WebDriver] = None) -> str
```

Summarize text using the OpenAI API

**Arguments**:

- `url` _str_ - The url of the text
- `text` _str_ - The text to summarize
- `question` _str_ - The question to ask the model
- `driver` _WebDriver_ - The webdriver to use to scroll the page
  

**Returns**:

- `str` - The summary of the text

#### scroll\_to\_percentage

```python
def scroll_to_percentage(driver: WebDriver, ratio: float) -> None
```

Scroll to a percentage of the page

**Arguments**:

- `driver` _WebDriver_ - The webdriver to use
- `ratio` _float_ - The percentage to scroll to
  

**Raises**:

- `ValueError` - If the ratio is not between 0 and 1

#### create\_message

```python
def create_message(chunk: str, question: str) -> Dict[str, str]
```

Create a message for the chat completion

**Arguments**:

- `chunk` _str_ - The chunk of text to summarize
- `question` _str_ - The question to answer
  

**Returns**:

  Dict[str, str]: The message to send to the chat completion

#### write\_to\_file

```python
def write_to_file(filename: str, text: str) -> None
```

Write text to a file

**Arguments**:

- `text` _str_ - The text to write
- `filename` _str_ - The filename to write to


```````




`../gpt-researcher/docs/docs/reference/processing/html.md`:

```````md
---
sidebar_label: html
title: processing.html
---

HTML processing functions

#### extract\_hyperlinks

```python
def extract_hyperlinks(soup: BeautifulSoup,
                       base_url: str) -> list[tuple[str, str]]
```

Extract hyperlinks from a BeautifulSoup object

**Arguments**:

- `soup` _BeautifulSoup_ - The BeautifulSoup object
- `base_url` _str_ - The base URL
  

**Returns**:

  List[Tuple[str, str]]: The extracted hyperlinks

#### format\_hyperlinks

```python
def format_hyperlinks(hyperlinks: list[tuple[str, str]]) -> list[str]
```

Format hyperlinks to be displayed to the user

**Arguments**:

- `hyperlinks` _List[Tuple[str, str]]_ - The hyperlinks to format
  

**Returns**:

- `List[str]` - The formatted hyperlinks


```````




`../gpt-researcher/docs/docs/reference/config/singleton.md`:

```````md
---
sidebar_label: singleton
title: config.singleton
---

The singleton metaclass for ensuring only one instance of a class.

## Singleton Objects

```python
class Singleton(abc.ABCMeta, type)
```

Singleton metaclass for ensuring only one instance of a class.

#### \_\_call\_\_

```python
def __call__(cls, *args, **kwargs)
```

Call method for the singleton metaclass.

## AbstractSingleton Objects

```python
class AbstractSingleton(abc.ABC, metaclass=Singleton)
```

Abstract singleton class for ensuring only one instance of a class.


```````




`../gpt-researcher/docs/docs/reference/config/config.md`:

```````md
---
sidebar_label: config
title: config.config
---

Configuration class to store the state of bools for different scripts access.

## Config Objects

```python
class Config(metaclass=Singleton)
```

Configuration class to store the state of bools for different scripts access.

#### \_\_init\_\_

```python
def __init__() -> None
```

Initialize the Config class

#### set\_fast\_llm\_model

```python
def set_fast_llm_model(value: str) -> None
```

Set the fast LLM model value.

#### set\_smart\_llm\_model

```python
def set_smart_llm_model(value: str) -> None
```

Set the smart LLM model value.

#### set\_fast\_token\_limit

```python
def set_fast_token_limit(value: int) -> None
```

Set the fast token limit value.

#### set\_smart\_token\_limit

```python
def set_smart_token_limit(value: int) -> None
```

Set the smart token limit value.

#### set\_browse\_chunk\_max\_length

```python
def set_browse_chunk_max_length(value: int) -> None
```

Set the browse_website command chunk max length value.

#### set\_openai\_api\_key

```python
def set_openai_api_key(value: str) -> None
```

Set the OpenAI API key value.

#### set\_debug\_mode

```python
def set_debug_mode(value: bool) -> None
```

Set the debug mode value.

## APIKeyError Objects

```python
class APIKeyError(Exception)
```

Exception raised when an API key is not set in config.py or as an environment variable.

#### check\_openai\_api\_key

```python
def check_openai_api_key(cfg) -> None
```

Check if the OpenAI API key is set in config.py or as an environment variable.

#### check\_tavily\_api\_key

```python
def check_tavily_api_key(cfg) -> None
```

Check if the Tavily Search API key is set in config.py or as an environment variable.

#### check\_google\_api\_key

```python
def check_google_api_key(cfg) -> None
```

Check if the Google API key is set in config.py or as an environment variable.

#### check\_serp\_api\_key

```python
def check_serp_api_key(cfg) -> None
```

Check if the SERP API key is set in config.py or as an environment variable.

#### check\_searx\_url

```python
def check_searx_url(cfg) -> None
```

Check if the Searx URL is set in config.py or as an environment variable.


```````




`../gpt-researcher/docs/docs/faq.md`:

```````md
# Frequently Asked Questions

### How do I get started?
It really depends on what you're aiming for. 

If you're looking to connect your AI application to the internet with our tailored API, check out the [Tavily API](/docs/tavily-api/introduction) documentation. 
If you're looking to build and deploy our open source autonomous research agent GPT Researcher, please see [GPT Researcher](/docs/gpt-researcher/introduction) documentation.
You can also check out demos and examples for inspiration [here](/docs/examples/examples).
### What is GPT Researcher?
GPT Researcher is a popular open source autonomous research agent that takes care of the tedious task of research for you, by scraping, filtering and aggregating over 20+ web sources per a single research task.

GPT Researcher is built with best practices for leveraging LLMs (prompt engineering, RAG, chains, embeddings, etc), and is optimized for quick and efficient research. It is also fully customizable and can be tailored to your specific needs.

To learn more about GPT Researcher, check out the [documentation page](/docs/gpt-researcher/introduction).
### How much does each research run cost?
A research task using GPT Researcher costs around $0.01 per a single run (for GPT-4 usage). We're constantly optimizing LLM calls to reduce costs and improve performance. 
### How do you ensure the report is factual and accurate?
we do our best to ensure that the information we provide is factual and accurate. We do this by using multiple sources, and by using proprietary AI to score and rank the most relevant and accurate information. We also use proprietary AI to filter out irrelevant information and sources.

Lastly, by using RAG and other techniques, we ensure that the information is relevant to the context of the research task, leading to more accurate generative AI content and reduced hallucinations.

### What is Tavily API?
Tavily search API is a search engine optimized for LLMs, aimed at efficient, quick and persistent search results. Unlike other search APIs such as Serp or Google, Tavily focuses on optimizing search for AI developers and autonomous AI agents. We take care of all the burden in searching, scraping, filtering and extracting the most relevant information from online sources. All in a single API call!

The search API can also be used return answers to questions (for use cases such as multi-agent frameworks like autogen) and can complete comprehensive research tasks in seconds. Moreover, Tavily leverages proprietary financial, code, news, and other data internal data sources to complement online information.

To learn more about Tavily search API, check out the [documentation page](/docs/tavily-api/introduction).

To try the API in action, you can now use our hosted version [here](https://app.tavily.com/chat) or on our [API Playground](https://app.tavily.com/playground).
### How is Tavily different from other search APIs?
Current search APIs such as Google, Serp and Bing retrieve search results based on user query. However, the results are sometimes irrelevant to the goal of the search, and return simple site URLs and snippets of content which are not always relevant. Because of this, any developer would need to then scrape the sites for relevant content, filter irrelevant information, optimize the content to fit LLM context limits, and more. This tasks is a burden and requires skills to get right.

Tavily Search API aggregates over 20+ sites per a single API call, and uses  AI to score, filter and rank the top most relevant sources and content to your task, query or goal. In addition, Tavily allows developers to add custom fields such as context and limit response tokens to enable the optimal search experience for LLMs.
proprietary
Lastly, Tavily indexes and ranks search results based on factors such as trusted sources, content quality, and more. This allows for a more accurate and relevant search experience for AI agents.

Remember: With LLM hallucinations, it's crucial to optimize for RAG with the right context and information.
### What is Tavily API pricing?
Tavily is free to use for up to 1,000 API calls. Check out our [pricing page](https://tavily.com/#pricing) for more information.

At the moment we don't have a pricing model, since we're still in beta and focused on building the best product for our users. We're always open to feedback and suggestions, so please reach out if you have any ideas!
### What are your plans for the future?
We're constantly working on improving our products and services. We're currently working on improving our search API together with design partners, and adding more data sources to our search engine. We're also working on improving our research agent GPT Researcher, and adding more features to it while growing our amazing open source community.

If you're interested in our roadmap or looking to collaborate, check out our [roadmap page](https://trello.com/b/3O7KBePw/gpt-researcher-roadmap). 

Feel free to [contact us](mailto:support@tavily.com) if you have any further questions or suggestions!
```````




`../gpt-researcher/docs/package.json`:

```````json
{
  "name": "website",
  "version": "0.0.0",
  "private": true,
  "resolutions" :{
    "nth-check":"2.0.1",
    "trim":"0.0.3",
    "got": "11.8.5",
    "node-forge": "1.3.0",
    "minimatch": "3.0.5",
    "loader-utils": "2.0.4",
    "eta": "2.0.0",
    "@sideway/formula": "3.0.1",
    "http-cache-semantics": "4.1.1"
   },
  "scripts": {
    "docusaurus": "docusaurus",
    "start": "docusaurus start",
    "build": "docusaurus build",
    "swizzle": "docusaurus swizzle",
    "deploy": "docusaurus deploy",
    "clear": "docusaurus clear",
    "serve": "docusaurus serve",
    "write-translations": "docusaurus write-translations",
    "write-heading-ids": "docusaurus write-heading-ids"
  },
  "dependencies": {
    "@docusaurus/core": "0.0.0-4193",
    "@docusaurus/preset-classic": "0.0.0-4193",
    "@easyops-cn/docusaurus-search-local": "^0.21.1",
    "@mdx-js/react": "^1.6.21",
    "@svgr/webpack": "^5.5.0",
    "clsx": "^1.1.1",
    "file-loader": "^6.2.0",
    "hast-util-is-element": "1.1.0",
    "react": "^17.0.1",
    "react-dom": "^17.0.1",
    "rehype-katex": "4",
    "remark-math": "3",
    "trim": "^0.0.3",
    "url-loader": "^4.1.1",
    "minimatch": "3.0.5"
  },
  "browserslist": {
    "production": [
      ">0.5%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}

```````




`../gpt-researcher/docs/sidebars.js`:

```````js
/**
 * Creating a sidebar enables you to:
 - create an ordered group of docs
 - render a sidebar for each doc of that group
 - provide next/previous navigation

 The sidebars can be generated from the filesystem, or explicitly defined here.

 Create as many sidebars as you want.
 */

 module.exports = {
  docsSidebar: [
    'welcome',
    {
      type: 'category',
      label: 'GPT Researcher',
      collapsible: true,
      collapsed: false,
      items: [
        'gpt-researcher/introduction',
        'gpt-researcher/getting-started',
        'gpt-researcher/config',
         'gpt-researcher/example',
         'gpt-researcher/agent_frameworks',
        'gpt-researcher/pip-package',
        'gpt-researcher/troubleshooting',
      ],
    },
    {
      type: 'category',
      label: 'Tavily API',
      collapsible: true,
      collapsed: false,
      items: [
        'tavily-api/introduction',
        'tavily-api/python-sdk',
        'tavily-api/rest_api',
        'tavily-api/langchain',
        'tavily-api/llamaindex',
        //{'Topics': [{type: 'autogenerated', dirName: 'tavily-api/Topics'}]},
      ],
    },
    //{'GPT Researcher': [{type: 'autogenerated', dirName: 'gpt-researcher'}]},
    //{'Tavily API': [{type: 'autogenerated', dirName: 'tavily-api'}]},
    {'Examples': [{type: 'autogenerated', dirName: 'examples'}]},
    'contribute',
  ],
  // pydoc-markdown auto-generated markdowns from docstrings
  referenceSideBar: [require("./docs/reference/sidebar.json")]
};

```````




`../gpt-researcher/docs/src/components/HomepageFeatures.js`:

```````js
import React from 'react';
import clsx from 'clsx';
import { Link } from 'react-router-dom';
import styles from './HomepageFeatures.module.css';

const FeatureList = [
  {
    title: 'GPT Researcher',
    Svg: require('../../static/img/gptresearcher.png').default,
    docLink: './docs/gpt-researcher/getting-started',
    description: (
      <>
        GPT Researcher is an open source autonomous agent designed for comprehensive online research on a variety of tasks.
      </>
    ),
  },
  {
    title: 'Tavily Search API',
    Svg: require('../../static/img/tavily.png').default,
    docLink: './docs/tavily-api/introduction',
    description: (
      <>
        Tavily Search API is a search engine optimized for LLMs, optimized for a factual, efficient, and persistent search experience
      </>
    ),
  },
  {
    title: 'Examples and Demos',
    Svg: require('../../static/img/examples.png').default,
    docLink: './docs/examples/examples',
    description: (
      <>
          Check out Tavily API in action across multiple frameworks and use cases
      </>
    ),
  },
];

function Feature({Svg, title, description, docLink}) {
  return (
    <div className={clsx('col col--4')}>
      <div className="text--center">
        {/*<Svg className={styles.featureSvg} alt={title} />*/}
        <img src={Svg} alt={title} height="60"/>
      </div>
      <div className="text--center padding-horiz--md">
        <Link to={docLink}>
            <h3>{title}</h3>
        </Link>
        <p>{description}</p>
      </div>
    </div>
  );
}

export default function HomepageFeatures() {
  return (
    <section className={styles.features}>
      <div className="container">
        <div className="row">
          {FeatureList.map((props, idx) => (
            <Feature key={idx} {...props} />
          ))}
        </div>
      </div>
    </section>
  );
}

```````




`../gpt-researcher/docs/src/components/HomepageFeatures.module.css`:

```````css
/* stylelint-disable docusaurus/copyright-header */

.features {
  display: flex;
  align-items: center;
  padding: 2rem 0;
  width: 100%;
}

.featureSvg {
  height: 120px;
  width: 200px;
}

```````




`../gpt-researcher/docs/src/css/custom.css`:

```````css
:root {
  --ifm-font-size-base: 17px;
  --ifm-code-font-size: 90%;

  --ifm-color-primary: #0c4da2;
  --ifm-color-primary-dark: rgb(11, 69, 146);
  --ifm-color-primary-darker: #0a418a;
  --ifm-color-primary-darkest: #083671;
  --ifm-color-primary-light: #0d55b2;
  --ifm-color-primary-lighter: #0e59ba;
  --ifm-color-primary-lightest: #1064d3;

  --ifm-color-emphasis-300: #1064d3;
  --ifm-link-color: #1064d3;
  --ifm-menu-color-active: #1064d3;
}

.docusaurus-highlight-code-line {
background-color: rgba(0, 0, 0, 0.1);
display: block;
margin: 0 calc(-1 * var(--ifm-pre-padding));
padding: 0 var(--ifm-pre-padding);
}
html[data-theme='dark'] .docusaurus-highlight-code-line {
background-color: rgb(0, 0, 0, 0.3);
}

.admonition-content a {
text-decoration: underline;
font-weight: 600;
color: inherit;
}

a {
font-weight: 600;
}

blockquote {
  /* samsung blue with lots of transparency */
  background-color: #0c4da224;
}
@media (prefers-color-scheme: dark) {
:root {
  --ifm-hero-text-color: white;
}
}
@media (prefers-color-scheme: dark) {
.hero.hero--primary { --ifm-hero-text-color: white;}
}

@media (prefers-color-scheme: dark) {
blockquote {
  --ifm-color-emphasis-300: var(--ifm-color-primary);
  /* border-left: 6px solid var(--ifm-color-emphasis-300); */
}
}
@media (prefers-color-scheme: dark) {
code {
  /* background-color: rgb(41, 45, 62); */
}
}


/* Docusaurus still defaults to their green! */
@media (prefers-color-scheme: dark) {
.react-toggle-thumb {
  border-color: var(--ifm-color-primary) !important;
}
}


.header-github-link:hover {
opacity: 0.6;
}

.header-github-link:before {
content: '';
width: 24px;
height: 24px;
display: flex;
background: url("data:image/svg+xml,%3Csvg viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12'/%3E%3C/svg%3E")
  no-repeat;
}

html[data-theme='dark'] .header-github-link:before {
background: url("data:image/svg+xml,%3Csvg viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath fill='white' d='M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12'/%3E%3C/svg%3E")
  no-repeat;
}

```````




`../gpt-researcher/docs/src/pages/index.module.css`:

```````css
/* stylelint-disable docusaurus/copyright-header */

/**
 * CSS files with the .module.css suffix will be treated as CSS modules
 * and scoped locally.
 */

.heroBanner {
  padding: 4rem 0;
  text-align: center;
  position: relative;
  overflow: hidden;
}

@media screen and (max-width: 966px) {
  .heroBanner {
    padding: 2rem;
  }
}

.buttons {
  display: flex;
  align-items: center;
  justify-content: center;
}

```````




`../gpt-researcher/docs/src/pages/index.js`:

```````js
import React from 'react';
import clsx from 'clsx';
import Layout from '@theme/Layout';
import Link from '@docusaurus/Link';
import useDocusaurusContext from '@docusaurus/useDocusaurusContext';
import styles from './index.module.css';
import HomepageFeatures from '../components/HomepageFeatures';

function HomepageHeader() {
  const {siteConfig} = useDocusaurusContext();
  return (
    <header className={clsx('hero hero--primary', styles.heroBanner)}>
      <div className="container">
        <h1 className="hero__title">{siteConfig.title}</h1>
        <p className="hero__subtitle">{siteConfig.tagline}</p>
        <div className={styles.buttons}>
          <Link
            className="button button--secondary button--lg"
            to="/docs/welcome">
            Getting Started - 5 min ⏱️
          </Link>
        </div>
      </div>
    </header>
  );
}

export default function Home() {
  const {siteConfig} = useDocusaurusContext();
  return (
    <Layout
      title={`Tavily Documentation`}
      description="Tavily is the leading search engine optimized for AI agents - powered by LLMs.">
      <HomepageHeader />
      <main>
        <HomepageFeatures />
      </main>
    </Layout>
  );
}

```````




`../gpt-researcher/docs/yarn.lock`:

```````lock
# THIS IS AN AUTOGENERATED FILE. DO NOT EDIT THIS FILE DIRECTLY.
# yarn lockfile v1


"@algolia/autocomplete-core@1.7.2":
  version "1.7.2"
  resolved "https://registry.npmmirror.com/@algolia/autocomplete-core/-/autocomplete-core-1.7.2.tgz#8abbed88082f611997538760dffcb43b33b1fd1d"
  integrity sha512-eclwUDC6qfApNnEfu1uWcL/rudQsn59tjEoUYZYE2JSXZrHLRjBUGMxiCoknobU2Pva8ejb0eRxpIYDtVVqdsw==
  dependencies:
    "@algolia/autocomplete-shared" "1.7.2"

"@algolia/autocomplete-preset-algolia@1.7.2":
  version "1.7.2"
  resolved "https://registry.npmmirror.com/@algolia/autocomplete-preset-algolia/-/autocomplete-preset-algolia-1.7.2.tgz#9cd4f64b3d64399657ee2dc2b7e0a939e0713a26"
  integrity sha512-+RYEG6B0QiGGfRb2G3MtPfyrl0dALF3cQNTWBzBX6p5o01vCCGTTinAm2UKG3tfc2CnOMAtnPLkzNZyJUpnVJw==
  dependencies:
    "@algolia/autocomplete-shared" "1.7.2"

"@algolia/autocomplete-shared@1.7.2":
  version "1.7.2"
  resolved "https://registry.npmmirror.com/@algolia/autocomplete-shared/-/autocomplete-shared-1.7.2.tgz#daa23280e78d3b42ae9564d12470ae034db51a89"
  integrity sha512-QCckjiC7xXHIUaIL3ektBtjJ0w7tTA3iqKcAE/Hjn1lZ5omp7i3Y4e09rAr9ZybqirL7AbxCLLq0Ra5DDPKeug==

"@algolia/cache-browser-local-storage@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/cache-browser-local-storage/-/cache-browser-local-storage-4.14.2.tgz#d5b1b90130ca87c6321de876e167df9ec6524936"
  integrity sha512-FRweBkK/ywO+GKYfAWbrepewQsPTIEirhi1BdykX9mxvBPtGNKccYAxvGdDCumU1jL4r3cayio4psfzKMejBlA==
  dependencies:
    "@algolia/cache-common" "4.14.2"

"@algolia/cache-common@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/cache-common/-/cache-common-4.14.2.tgz#b946b6103c922f0c06006fb6929163ed2c67d598"
  integrity sha512-SbvAlG9VqNanCErr44q6lEKD2qoK4XtFNx9Qn8FK26ePCI8I9yU7pYB+eM/cZdS9SzQCRJBbHUumVr4bsQ4uxg==

"@algolia/cache-in-memory@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/cache-in-memory/-/cache-in-memory-4.14.2.tgz#88e4a21474f9ac05331c2fa3ceb929684a395a24"
  integrity sha512-HrOukWoop9XB/VFojPv1R5SVXowgI56T9pmezd/djh2JnVN/vXswhXV51RKy4nCpqxyHt/aGFSq2qkDvj6KiuQ==
  dependencies:
    "@algolia/cache-common" "4.14.2"

"@algolia/client-account@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/client-account/-/client-account-4.14.2.tgz#b76ac1ba9ea71e8c3f77a1805b48350dc0728a16"
  integrity sha512-WHtriQqGyibbb/Rx71YY43T0cXqyelEU0lB2QMBRXvD2X0iyeGl4qMxocgEIcbHyK7uqE7hKgjT8aBrHqhgc1w==
  dependencies:
    "@algolia/client-common" "4.14.2"
    "@algolia/client-search" "4.14.2"
    "@algolia/transporter" "4.14.2"

"@algolia/client-analytics@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/client-analytics/-/client-analytics-4.14.2.tgz#ca04dcaf9a78ee5c92c5cb5e9c74cf031eb2f1fb"
  integrity sha512-yBvBv2mw+HX5a+aeR0dkvUbFZsiC4FKSnfqk9rrfX+QrlNOKEhCG0tJzjiOggRW4EcNqRmaTULIYvIzQVL2KYQ==
  dependencies:
    "@algolia/client-common" "4.14.2"
    "@algolia/client-search" "4.14.2"
    "@algolia/requester-common" "4.14.2"
    "@algolia/transporter" "4.14.2"

"@algolia/client-common@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/client-common/-/client-common-4.14.2.tgz#e1324e167ffa8af60f3e8bcd122110fd0bfd1300"
  integrity sha512-43o4fslNLcktgtDMVaT5XwlzsDPzlqvqesRi4MjQz2x4/Sxm7zYg5LRYFol1BIhG6EwxKvSUq8HcC/KxJu3J0Q==
  dependencies:
    "@algolia/requester-common" "4.14.2"
    "@algolia/transporter" "4.14.2"

"@algolia/client-personalization@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/client-personalization/-/client-personalization-4.14.2.tgz#656bbb6157a3dd1a4be7de65e457fda136c404ec"
  integrity sha512-ACCoLi0cL8CBZ1W/2juehSltrw2iqsQBnfiu/Rbl9W2yE6o2ZUb97+sqN/jBqYNQBS+o0ekTMKNkQjHHAcEXNw==
  dependencies:
    "@algolia/client-common" "4.14.2"
    "@algolia/requester-common" "4.14.2"
    "@algolia/transporter" "4.14.2"

"@algolia/client-search@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/client-search/-/client-search-4.14.2.tgz#357bdb7e640163f0e33bad231dfcc21f67dc2e92"
  integrity sha512-L5zScdOmcZ6NGiVbLKTvP02UbxZ0njd5Vq9nJAmPFtjffUSOGEp11BmD2oMJ5QvARgx2XbX4KzTTNS5ECYIMWw==
  dependencies:
    "@algolia/client-common" "4.14.2"
    "@algolia/requester-common" "4.14.2"
    "@algolia/transporter" "4.14.2"

"@algolia/events@^4.0.1":
  version "4.0.1"
  resolved "https://registry.npmmirror.com/@algolia/events/-/events-4.0.1.tgz#fd39e7477e7bc703d7f893b556f676c032af3950"
  integrity sha512-FQzvOCgoFXAbf5Y6mYozw2aj5KCJoA3m4heImceldzPSMbdyS4atVjJzXKMsfX3wnZTFYwkkt8/z8UesLHlSBQ==

"@algolia/logger-common@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/logger-common/-/logger-common-4.14.2.tgz#b74b3a92431f92665519d95942c246793ec390ee"
  integrity sha512-/JGlYvdV++IcMHBnVFsqEisTiOeEr6cUJtpjz8zc0A9c31JrtLm318Njc72p14Pnkw3A/5lHHh+QxpJ6WFTmsA==

"@algolia/logger-console@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/logger-console/-/logger-console-4.14.2.tgz#ec49cb47408f5811d4792598683923a800abce7b"
  integrity sha512-8S2PlpdshbkwlLCSAB5f8c91xyc84VM9Ar9EdfE9UmX+NrKNYnWR1maXXVDQQoto07G1Ol/tYFnFVhUZq0xV/g==
  dependencies:
    "@algolia/logger-common" "4.14.2"

"@algolia/requester-browser-xhr@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/requester-browser-xhr/-/requester-browser-xhr-4.14.2.tgz#a2cd4d9d8d90d53109cc7f3682dc6ebf20f798f2"
  integrity sha512-CEh//xYz/WfxHFh7pcMjQNWgpl4wFB85lUMRyVwaDPibNzQRVcV33YS+63fShFWc2+42YEipFGH2iPzlpszmDw==
  dependencies:
    "@algolia/requester-common" "4.14.2"

"@algolia/requester-common@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/requester-common/-/requester-common-4.14.2.tgz#bc4e9e5ee16c953c0ecacbfb334a33c30c28b1a1"
  integrity sha512-73YQsBOKa5fvVV3My7iZHu1sUqmjjfs9TteFWwPwDmnad7T0VTCopttcsM3OjLxZFtBnX61Xxl2T2gmG2O4ehg==

"@algolia/requester-node-http@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/requester-node-http/-/requester-node-http-4.14.2.tgz#7c1223a1785decaab1def64c83dade6bea45e115"
  integrity sha512-oDbb02kd1o5GTEld4pETlPZLY0e+gOSWjWMJHWTgDXbv9rm/o2cF7japO6Vj1ENnrqWvLBmW1OzV9g6FUFhFXg==
  dependencies:
    "@algolia/requester-common" "4.14.2"

"@algolia/transporter@4.14.2":
  version "4.14.2"
  resolved "https://registry.npmmirror.com/@algolia/transporter/-/transporter-4.14.2.tgz#77c069047fb1a4359ee6a51f51829508e44a1e3d"
  integrity sha512-t89dfQb2T9MFQHidjHcfhh6iGMNwvuKUvojAj+JsrHAGbuSy7yE4BylhLX6R0Q1xYRoC4Vvv+O5qIw/LdnQfsQ==
  dependencies:
    "@algolia/cache-common" "4.14.2"
    "@algolia/logger-common" "4.14.2"
    "@algolia/requester-common" "4.14.2"

"@ampproject/remapping@^2.1.0":
  version "2.2.0"
  resolved "https://registry.npmmirror.com/@ampproject/remapping/-/remapping-2.2.0.tgz#56c133824780de3174aed5ab6834f3026790154d"
  integrity sha512-qRmjj8nj9qmLTQXXmaR1cck3UXSRMPrbsLJAasZpF+t3riI71BXed5ebIOYwQntykeZuhjsdweEc9BxH5Jc26w==
  dependencies:
    "@jridgewell/gen-mapping" "^0.1.0"
    "@jridgewell/trace-mapping" "^0.3.9"

"@babel/code-frame@^7.0.0", "@babel/code-frame@^7.10.4", "@babel/code-frame@^7.18.6", "@babel/code-frame@^7.8.3":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/code-frame/-/code-frame-7.18.6.tgz#3b25d38c89600baa2dcc219edfa88a74eb2c427a"
  integrity sha512-TDCmlK5eOvH+eH7cdAFlNXeVJqWIQ7gW9tY1GJIpUtFb6CmjVyq2VM3u71bOyR8CRihcCgMUYoDNyLXao3+70Q==
  dependencies:
    "@babel/highlight" "^7.18.6"

"@babel/code-frame@^7.22.13":
  version "7.22.13"
  resolved "https://registry.yarnpkg.com/@babel/code-frame/-/code-frame-7.22.13.tgz#e3c1c099402598483b7a8c46a721d1038803755e"
  integrity sha512-XktuhWlJ5g+3TJXc5upd9Ks1HutSArik6jf2eAjYFyIOf4ej3RN+184cZbzDvbPnuTJIUhPKKJE3cIsYTiAT3w==
  dependencies:
    "@babel/highlight" "^7.22.13"
    chalk "^2.4.2"

"@babel/compat-data@^7.17.7", "@babel/compat-data@^7.20.0", "@babel/compat-data@^7.20.1":
  version "7.20.1"
  resolved "https://registry.npmmirror.com/@babel/compat-data/-/compat-data-7.20.1.tgz#f2e6ef7790d8c8dbf03d379502dcc246dcce0b30"
  integrity sha512-EWZ4mE2diW3QALKvDMiXnbZpRvlj+nayZ112nK93SnhqOtpdsbVD4W+2tEoT3YNBAG9RBR0ISY758ZkOgsn6pQ==

"@babel/core@7.12.9":
  version "7.12.9"
  resolved "https://registry.npmmirror.com/@babel/core/-/core-7.12.9.tgz#fd450c4ec10cdbb980e2928b7aa7a28484593fc8"
  integrity sha512-gTXYh3M5wb7FRXQy+FErKFAv90BnlOuNn1QkCK2lREoPAjrQCO49+HVSrFoe5uakFAF5eenS75KbO2vQiLrTMQ==
  dependencies:
    "@babel/code-frame" "^7.10.4"
    "@babel/generator" "^7.12.5"
    "@babel/helper-module-transforms" "^7.12.1"
    "@babel/helpers" "^7.12.5"
    "@babel/parser" "^7.12.7"
    "@babel/template" "^7.12.7"
    "@babel/traverse" "^7.12.9"
    "@babel/types" "^7.12.7"
    convert-source-map "^1.7.0"
    debug "^4.1.0"
    gensync "^1.0.0-beta.1"
    json5 "^2.1.2"
    lodash "^4.17.19"
    resolve "^1.3.2"
    semver "^5.4.1"
    source-map "^0.5.0"

"@babel/core@^7.12.16", "@babel/core@^7.12.3", "@babel/core@^7.19.6":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/core/-/core-7.20.2.tgz#8dc9b1620a673f92d3624bd926dc49a52cf25b92"
  integrity sha512-w7DbG8DtMrJcFOi4VrLm+8QM4az8Mo+PuLBKLp2zrYRCow8W/f9xiXm5sN53C8HksCyDQwCKha9JiDoIyPjT2g==
  dependencies:
    "@ampproject/remapping" "^2.1.0"
    "@babel/code-frame" "^7.18.6"
    "@babel/generator" "^7.20.2"
    "@babel/helper-compilation-targets" "^7.20.0"
    "@babel/helper-module-transforms" "^7.20.2"
    "@babel/helpers" "^7.20.1"
    "@babel/parser" "^7.20.2"
    "@babel/template" "^7.18.10"
    "@babel/traverse" "^7.20.1"
    "@babel/types" "^7.20.2"
    convert-source-map "^1.7.0"
    debug "^4.1.0"
    gensync "^1.0.0-beta.2"
    json5 "^2.2.1"
    semver "^6.3.0"

"@babel/generator@^7.12.15", "@babel/generator@^7.12.5", "@babel/generator@^7.20.2":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/generator/-/generator-7.20.2.tgz#c2e89e22613a039285c1e7b749e2cd0b30b9a481"
  integrity sha512-SD75PMIK6i9H8G/tfGvB4KKl4Nw6Ssos9nGgYwxbgyTP0iX/Z55DveoH86rmUB/YHTQQ+ZC0F7xxaY8l2OF44Q==
  dependencies:
    "@babel/types" "^7.20.2"
    "@jridgewell/gen-mapping" "^0.3.2"
    jsesc "^2.5.1"

"@babel/generator@^7.23.0":
  version "7.23.0"
  resolved "https://registry.yarnpkg.com/@babel/generator/-/generator-7.23.0.tgz#df5c386e2218be505b34837acbcb874d7a983420"
  integrity sha512-lN85QRR+5IbYrMWM6Y4pE/noaQtg4pNiqeNGX60eqOfo6gtEj6uw/JagelB8vVztSd7R6M5n1+PQkDbHbBRU4g==
  dependencies:
    "@babel/types" "^7.23.0"
    "@jridgewell/gen-mapping" "^0.3.2"
    "@jridgewell/trace-mapping" "^0.3.17"
    jsesc "^2.5.1"

"@babel/helper-annotate-as-pure@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/helper-annotate-as-pure/-/helper-annotate-as-pure-7.18.6.tgz#eaa49f6f80d5a33f9a5dd2276e6d6e451be0a6bb"
  integrity sha512-duORpUiYrEpzKIop6iNbjnwKLAKnJ47csTyRACyEmWj0QdUrm5aqNJGHSSEQSUAvNW0ojX0dOmK9dZduvkfeXA==
  dependencies:
    "@babel/types" "^7.18.6"

"@babel/helper-builder-binary-assignment-operator-visitor@^7.18.6":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/helper-builder-binary-assignment-operator-visitor/-/helper-builder-binary-assignment-operator-visitor-7.18.9.tgz#acd4edfd7a566d1d51ea975dff38fd52906981bb"
  integrity sha512-yFQ0YCHoIqarl8BCRwBL8ulYUaZpz3bNsA7oFepAzee+8/+ImtADXNOmO5vJvsPff3qi+hvpkY/NYBTrBQgdNw==
  dependencies:
    "@babel/helper-explode-assignable-expression" "^7.18.6"
    "@babel/types" "^7.18.9"

"@babel/helper-compilation-targets@^7.17.7", "@babel/helper-compilation-targets@^7.18.9", "@babel/helper-compilation-targets@^7.20.0":
  version "7.20.0"
  resolved "https://registry.npmmirror.com/@babel/helper-compilation-targets/-/helper-compilation-targets-7.20.0.tgz#6bf5374d424e1b3922822f1d9bdaa43b1a139d0a"
  integrity sha512-0jp//vDGp9e8hZzBc6N/KwA5ZK3Wsm/pfm4CrY7vzegkVxc65SgSn6wYOnwHe9Js9HRQ1YTCKLGPzDtaS3RoLQ==
  dependencies:
    "@babel/compat-data" "^7.20.0"
    "@babel/helper-validator-option" "^7.18.6"
    browserslist "^4.21.3"
    semver "^6.3.0"

"@babel/helper-create-class-features-plugin@^7.18.6", "@babel/helper-create-class-features-plugin@^7.20.2":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/helper-create-class-features-plugin/-/helper-create-class-features-plugin-7.20.2.tgz#3c08a5b5417c7f07b5cf3dfb6dc79cbec682e8c2"
  integrity sha512-k22GoYRAHPYr9I+Gvy2ZQlAe5mGy8BqWst2wRt8cwIufWTxrsVshhIBvYNqC80N0GSFWTsqRVexOtfzlgOEDvA==
  dependencies:
    "@babel/helper-annotate-as-pure" "^7.18.6"
    "@babel/helper-environment-visitor" "^7.18.9"
    "@babel/helper-function-name" "^7.19.0"
    "@babel/helper-member-expression-to-functions" "^7.18.9"
    "@babel/helper-optimise-call-expression" "^7.18.6"
    "@babel/helper-replace-supers" "^7.19.1"
    "@babel/helper-split-export-declaration" "^7.18.6"

"@babel/helper-create-regexp-features-plugin@^7.18.6", "@babel/helper-create-regexp-features-plugin@^7.19.0":
  version "7.19.0"
  resolved "https://registry.npmmirror.com/@babel/helper-create-regexp-features-plugin/-/helper-create-regexp-features-plugin-7.19.0.tgz#7976aca61c0984202baca73d84e2337a5424a41b"
  integrity sha512-htnV+mHX32DF81amCDrwIDr8nrp1PTm+3wfBN9/v8QJOLEioOCOG7qNyq0nHeFiWbT3Eb7gsPwEmV64UCQ1jzw==
  dependencies:
    "@babel/helper-annotate-as-pure" "^7.18.6"
    regexpu-core "^5.1.0"

"@babel/helper-define-polyfill-provider@^0.3.3":
  version "0.3.3"
  resolved "https://registry.npmmirror.com/@babel/helper-define-polyfill-provider/-/helper-define-polyfill-provider-0.3.3.tgz#8612e55be5d51f0cd1f36b4a5a83924e89884b7a"
  integrity sha512-z5aQKU4IzbqCC1XH0nAqfsFLMVSo22SBKUc0BxGrLkolTdPTructy0ToNnlO2zA4j9Q/7pjMZf0DSY+DSTYzww==
  dependencies:
    "@babel/helper-compilation-targets" "^7.17.7"
    "@babel/helper-plugin-utils" "^7.16.7"
    debug "^4.1.1"
    lodash.debounce "^4.0.8"
    resolve "^1.14.2"
    semver "^6.1.2"

"@babel/helper-environment-visitor@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/helper-environment-visitor/-/helper-environment-visitor-7.18.9.tgz#0c0cee9b35d2ca190478756865bb3528422f51be"
  integrity sha512-3r/aACDJ3fhQ/EVgFy0hpj8oHyHpQc+LPtJoY9SzTThAsStm4Ptegq92vqKoE3vD706ZVFWITnMnxucw+S9Ipg==

"@babel/helper-environment-visitor@^7.22.20":
  version "7.22.20"
  resolved "https://registry.yarnpkg.com/@babel/helper-environment-visitor/-/helper-environment-visitor-7.22.20.tgz#96159db61d34a29dba454c959f5ae4a649ba9167"
  integrity sha512-zfedSIzFhat/gFhWfHtgWvlec0nqB9YEIVrpuwjruLlXfUSnA8cJB0miHKwqDnQ7d32aKo2xt88/xZptwxbfhA==

"@babel/helper-explode-assignable-expression@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/helper-explode-assignable-expression/-/helper-explode-assignable-expression-7.18.6.tgz#41f8228ef0a6f1a036b8dfdfec7ce94f9a6bc096"
  integrity sha512-eyAYAsQmB80jNfg4baAtLeWAQHfHFiR483rzFK+BhETlGZaQC9bsfrugfXDCbRHLQbIA7U5NxhhOxN7p/dWIcg==
  dependencies:
    "@babel/types" "^7.18.6"

"@babel/helper-function-name@^7.18.9", "@babel/helper-function-name@^7.19.0":
  version "7.19.0"
  resolved "https://registry.npmmirror.com/@babel/helper-function-name/-/helper-function-name-7.19.0.tgz#941574ed5390682e872e52d3f38ce9d1bef4648c"
  integrity sha512-WAwHBINyrpqywkUH0nTnNgI5ina5TFn85HKS0pbPDfxFfhyR/aNQEn4hGi1P1JyT//I0t4OgXUlofzWILRvS5w==
  dependencies:
    "@babel/template" "^7.18.10"
    "@babel/types" "^7.19.0"

"@babel/helper-function-name@^7.23.0":
  version "7.23.0"
  resolved "https://registry.yarnpkg.com/@babel/helper-function-name/-/helper-function-name-7.23.0.tgz#1f9a3cdbd5b2698a670c30d2735f9af95ed52759"
  integrity sha512-OErEqsrxjZTJciZ4Oo+eoZqeW9UIiOcuYKRJA4ZAgV9myA+pOXhhmpfNCKjEH/auVfEYVFJ6y1Tc4r0eIApqiw==
  dependencies:
    "@babel/template" "^7.22.15"
    "@babel/types" "^7.23.0"

"@babel/helper-hoist-variables@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/helper-hoist-variables/-/helper-hoist-variables-7.18.6.tgz#d4d2c8fb4baeaa5c68b99cc8245c56554f926678"
  integrity sha512-UlJQPkFqFULIcyW5sbzgbkxn2FKRgwWiRexcuaR8RNJRy8+LLveqPjwZV/bwrLZCN0eUHD/x8D0heK1ozuoo6Q==
  dependencies:
    "@babel/types" "^7.18.6"

"@babel/helper-hoist-variables@^7.22.5":
  version "7.22.5"
  resolved "https://registry.yarnpkg.com/@babel/helper-hoist-variables/-/helper-hoist-variables-7.22.5.tgz#c01a007dac05c085914e8fb652b339db50d823bb"
  integrity sha512-wGjk9QZVzvknA6yKIUURb8zY3grXCcOZt+/7Wcy8O2uctxhplmUPkOdlgoNhmdVee2c92JXbf1xpMtVNbfoxRw==
  dependencies:
    "@babel/types" "^7.22.5"

"@babel/helper-member-expression-to-functions@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/helper-member-expression-to-functions/-/helper-member-expression-to-functions-7.18.9.tgz#1531661e8375af843ad37ac692c132841e2fd815"
  integrity sha512-RxifAh2ZoVU67PyKIO4AMi1wTenGfMR/O/ae0CCRqwgBAt5v7xjdtRw7UoSbsreKrQn5t7r89eruK/9JjYHuDg==
  dependencies:
    "@babel/types" "^7.18.9"

"@babel/helper-module-imports@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/helper-module-imports/-/helper-module-imports-7.18.6.tgz#1e3ebdbbd08aad1437b428c50204db13c5a3ca6e"
  integrity sha512-0NFvs3VkuSYbFi1x2Vd6tKrywq+z/cLeYC/RJNFrIX/30Bf5aiGYbtvGXolEktzJH8o5E5KJ3tT+nkxuuZFVlA==
  dependencies:
    "@babel/types" "^7.18.6"

"@babel/helper-module-transforms@^7.12.1", "@babel/helper-module-transforms@^7.18.6", "@babel/helper-module-transforms@^7.19.6", "@babel/helper-module-transforms@^7.20.2":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/helper-module-transforms/-/helper-module-transforms-7.20.2.tgz#ac53da669501edd37e658602a21ba14c08748712"
  integrity sha512-zvBKyJXRbmK07XhMuujYoJ48B5yvvmM6+wcpv6Ivj4Yg6qO7NOZOSnvZN9CRl1zz1Z4cKf8YejmCMh8clOoOeA==
  dependencies:
    "@babel/helper-environment-visitor" "^7.18.9"
    "@babel/helper-module-imports" "^7.18.6"
    "@babel/helper-simple-access" "^7.20.2"
    "@babel/helper-split-export-declaration" "^7.18.6"
    "@babel/helper-validator-identifier" "^7.19.1"
    "@babel/template" "^7.18.10"
    "@babel/traverse" "^7.20.1"
    "@babel/types" "^7.20.2"

"@babel/helper-optimise-call-expression@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/helper-optimise-call-expression/-/helper-optimise-call-expression-7.18.6.tgz#9369aa943ee7da47edab2cb4e838acf09d290ffe"
  integrity sha512-HP59oD9/fEHQkdcbgFCnbmgH5vIQTJbxh2yf+CdM89/glUNnuzr87Q8GIjGEnOktTROemO0Pe0iPAYbqZuOUiA==
  dependencies:
    "@babel/types" "^7.18.6"

"@babel/helper-plugin-utils@7.10.4":
  version "7.10.4"
  resolved "https://registry.npmmirror.com/@babel/helper-plugin-utils/-/helper-plugin-utils-7.10.4.tgz#2f75a831269d4f677de49986dff59927533cf375"
  integrity sha512-O4KCvQA6lLiMU9l2eawBPMf1xPP8xPfB3iEQw150hOVTqj/rfXz0ThTb4HEzqQfs2Bmo5Ay8BzxfzVtBrr9dVg==

"@babel/helper-plugin-utils@^7.0.0", "@babel/helper-plugin-utils@^7.10.4", "@babel/helper-plugin-utils@^7.12.13", "@babel/helper-plugin-utils@^7.14.5", "@babel/helper-plugin-utils@^7.16.7", "@babel/helper-plugin-utils@^7.18.6", "@babel/helper-plugin-utils@^7.18.9", "@babel/helper-plugin-utils@^7.19.0", "@babel/helper-plugin-utils@^7.20.2", "@babel/helper-plugin-utils@^7.8.0", "@babel/helper-plugin-utils@^7.8.3":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/helper-plugin-utils/-/helper-plugin-utils-7.20.2.tgz#d1b9000752b18d0877cff85a5c376ce5c3121629"
  integrity sha512-8RvlJG2mj4huQ4pZ+rU9lqKi9ZKiRmuvGuM2HlWmkmgOhbs6zEAw6IEiJ5cQqGbDzGZOhwuOQNtZMi/ENLjZoQ==

"@babel/helper-remap-async-to-generator@^7.18.6", "@babel/helper-remap-async-to-generator@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/helper-remap-async-to-generator/-/helper-remap-async-to-generator-7.18.9.tgz#997458a0e3357080e54e1d79ec347f8a8cd28519"
  integrity sha512-dI7q50YKd8BAv3VEfgg7PS7yD3Rtbi2J1XMXaalXO0W0164hYLnh8zpjRS0mte9MfVp/tltvr/cfdXPvJr1opA==
  dependencies:
    "@babel/helper-annotate-as-pure" "^7.18.6"
    "@babel/helper-environment-visitor" "^7.18.9"
    "@babel/helper-wrap-function" "^7.18.9"
    "@babel/types" "^7.18.9"

"@babel/helper-replace-supers@^7.18.6", "@babel/helper-replace-supers@^7.19.1":
  version "7.19.1"
  resolved "https://registry.npmmirror.com/@babel/helper-replace-supers/-/helper-replace-supers-7.19.1.tgz#e1592a9b4b368aa6bdb8784a711e0bcbf0612b78"
  integrity sha512-T7ahH7wV0Hfs46SFh5Jz3s0B6+o8g3c+7TMxu7xKfmHikg7EAZ3I2Qk9LFhjxXq8sL7UkP5JflezNwoZa8WvWw==
  dependencies:
    "@babel/helper-environment-visitor" "^7.18.9"
    "@babel/helper-member-expression-to-functions" "^7.18.9"
    "@babel/helper-optimise-call-expression" "^7.18.6"
    "@babel/traverse" "^7.19.1"
    "@babel/types" "^7.19.0"

"@babel/helper-simple-access@^7.19.4", "@babel/helper-simple-access@^7.20.2":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/helper-simple-access/-/helper-simple-access-7.20.2.tgz#0ab452687fe0c2cfb1e2b9e0015de07fc2d62dd9"
  integrity sha512-+0woI/WPq59IrqDYbVGfshjT5Dmk/nnbdpcF8SnMhhXObpTq2KNBdLFRFrkVdbDOyUmHBCxzm5FHV1rACIkIbA==
  dependencies:
    "@babel/types" "^7.20.2"

"@babel/helper-skip-transparent-expression-wrappers@^7.18.9":
  version "7.20.0"
  resolved "https://registry.npmmirror.com/@babel/helper-skip-transparent-expression-wrappers/-/helper-skip-transparent-expression-wrappers-7.20.0.tgz#fbe4c52f60518cab8140d77101f0e63a8a230684"
  integrity sha512-5y1JYeNKfvnT8sZcK9DVRtpTbGiomYIHviSP3OQWmDPU3DeH4a1ZlT/N2lyQ5P8egjcRaT/Y9aNqUxK0WsnIIg==
  dependencies:
    "@babel/types" "^7.20.0"

"@babel/helper-split-export-declaration@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/helper-split-export-declaration/-/helper-split-export-declaration-7.18.6.tgz#7367949bc75b20c6d5a5d4a97bba2824ae8ef075"
  integrity sha512-bde1etTx6ZyTmobl9LLMMQsaizFVZrquTEHOqKeQESMKo4PlObf+8+JA25ZsIpZhT/WEd39+vOdLXAFG/nELpA==
  dependencies:
    "@babel/types" "^7.18.6"

"@babel/helper-split-export-declaration@^7.22.6":
  version "7.22.6"
  resolved "https://registry.yarnpkg.com/@babel/helper-split-export-declaration/-/helper-split-export-declaration-7.22.6.tgz#322c61b7310c0997fe4c323955667f18fcefb91c"
  integrity sha512-AsUnxuLhRYsisFiaJwvp1QF+I3KjD5FOxut14q/GzovUe6orHLesW2C7d754kRm53h5gqrz6sFl6sxc4BVtE/g==
  dependencies:
    "@babel/types" "^7.22.5"

"@babel/helper-string-parser@^7.19.4":
  version "7.19.4"
  resolved "https://registry.npmmirror.com/@babel/helper-string-parser/-/helper-string-parser-7.19.4.tgz#38d3acb654b4701a9b77fb0615a96f775c3a9e63"
  integrity sha512-nHtDoQcuqFmwYNYPz3Rah5ph2p8PFeFCsZk9A/48dPc/rGocJ5J3hAAZ7pb76VWX3fZKu+uEr/FhH5jLx7umrw==

"@babel/helper-string-parser@^7.22.5":
  version "7.22.5"
  resolved "https://registry.yarnpkg.com/@babel/helper-string-parser/-/helper-string-parser-7.22.5.tgz#533f36457a25814cf1df6488523ad547d784a99f"
  integrity sha512-mM4COjgZox8U+JcXQwPijIZLElkgEpO5rsERVDJTc2qfCDfERyob6k5WegS14SX18IIjv+XD+GrqNumY5JRCDw==

"@babel/helper-validator-identifier@^7.18.6", "@babel/helper-validator-identifier@^7.19.1":
  version "7.19.1"
  resolved "https://registry.npmmirror.com/@babel/helper-validator-identifier/-/helper-validator-identifier-7.19.1.tgz#7eea834cf32901ffdc1a7ee555e2f9c27e249ca2"
  integrity sha512-awrNfaMtnHUr653GgGEs++LlAvW6w+DcPrOliSMXWCKo597CwL5Acf/wWdNkf/tfEQE3mjkeD1YOVZOUV/od1w==

"@babel/helper-validator-identifier@^7.22.20":
  version "7.22.20"
  resolved "https://registry.yarnpkg.com/@babel/helper-validator-identifier/-/helper-validator-identifier-7.22.20.tgz#c4ae002c61d2879e724581d96665583dbc1dc0e0"
  integrity sha512-Y4OZ+ytlatR8AI+8KZfKuL5urKp7qey08ha31L8b3BwewJAoJamTzyvxPR/5D+KkdJCGPq/+8TukHBlY10FX9A==

"@babel/helper-validator-option@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/helper-validator-option/-/helper-validator-option-7.18.6.tgz#bf0d2b5a509b1f336099e4ff36e1a63aa5db4db8"
  integrity sha512-XO7gESt5ouv/LRJdrVjkShckw6STTaB7l9BrpBaAHDeF5YZT+01PCwmR0SJHnkW6i8OwW/EVWRShfi4j2x+KQw==

"@babel/helper-wrap-function@^7.18.9":
  version "7.19.0"
  resolved "https://registry.npmmirror.com/@babel/helper-wrap-function/-/helper-wrap-function-7.19.0.tgz#89f18335cff1152373222f76a4b37799636ae8b1"
  integrity sha512-txX8aN8CZyYGTwcLhlk87KRqncAzhh5TpQamZUa0/u3an36NtDpUP6bQgBCBcLeBs09R/OwQu3OjK0k/HwfNDg==
  dependencies:
    "@babel/helper-function-name" "^7.19.0"
    "@babel/template" "^7.18.10"
    "@babel/traverse" "^7.19.0"
    "@babel/types" "^7.19.0"

"@babel/helpers@^7.12.5", "@babel/helpers@^7.20.1":
  version "7.20.1"
  resolved "https://registry.npmmirror.com/@babel/helpers/-/helpers-7.20.1.tgz#2ab7a0fcb0a03b5bf76629196ed63c2d7311f4c9"
  integrity sha512-J77mUVaDTUJFZ5BpP6mMn6OIl3rEWymk2ZxDBQJUG3P+PbmyMcF3bYWvz0ma69Af1oobDqT/iAsvzhB58xhQUg==
  dependencies:
    "@babel/template" "^7.18.10"
    "@babel/traverse" "^7.20.1"
    "@babel/types" "^7.20.0"

"@babel/highlight@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/highlight/-/highlight-7.18.6.tgz#81158601e93e2563795adcbfbdf5d64be3f2ecdf"
  integrity sha512-u7stbOuYjaPezCuLj29hNW1v64M2Md2qupEKP1fHc7WdOA3DgLh37suiSrZYY7haUB7iBeQZ9P1uiRF359do3g==
  dependencies:
    "@babel/helper-validator-identifier" "^7.18.6"
    chalk "^2.0.0"
    js-tokens "^4.0.0"

"@babel/highlight@^7.22.13":
  version "7.22.20"
  resolved "https://registry.yarnpkg.com/@babel/highlight/-/highlight-7.22.20.tgz#4ca92b71d80554b01427815e06f2df965b9c1f54"
  integrity sha512-dkdMCN3py0+ksCgYmGG8jKeGA/8Tk+gJwSYYlFGxG5lmhfKNoAy004YpLxpS1W2J8m/EK2Ew+yOs9pVRwO89mg==
  dependencies:
    "@babel/helper-validator-identifier" "^7.22.20"
    chalk "^2.4.2"
    js-tokens "^4.0.0"

"@babel/parser@^7.12.16", "@babel/parser@^7.12.7", "@babel/parser@^7.18.10", "@babel/parser@^7.20.2":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/parser/-/parser-7.20.2.tgz#9aeb9b92f64412b5f81064d46f6a1ac0881337f4"
  integrity sha512-afk318kh2uKbo7BEj2QtEi8HVCGrwHUffrYDy7dgVcSa2j9lY3LDjPzcyGdpX7xgm35aWqvciZJ4WKmdF/SxYg==

"@babel/parser@^7.22.15", "@babel/parser@^7.23.0":
  version "7.23.0"
  resolved "https://registry.yarnpkg.com/@babel/parser/-/parser-7.23.0.tgz#da950e622420bf96ca0d0f2909cdddac3acd8719"
  integrity sha512-vvPKKdMemU85V9WE/l5wZEmImpCtLqbnTvqDS2U1fJ96KrxoW7KrXhNsNCblQlg8Ck4b85yxdTyelsMUgFUXiw==

"@babel/plugin-bugfix-safari-id-destructuring-collision-in-function-expression@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-bugfix-safari-id-destructuring-collision-in-function-expression/-/plugin-bugfix-safari-id-destructuring-collision-in-function-expression-7.18.6.tgz#da5b8f9a580acdfbe53494dba45ea389fb09a4d2"
  integrity sha512-Dgxsyg54Fx1d4Nge8UnvTrED63vrwOdPmyvPzlNN/boaliRP54pm3pGzZD1SJUwrBA+Cs/xdG8kXX6Mn/RfISQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-bugfix-v8-spread-parameters-in-optional-chaining@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/plugin-bugfix-v8-spread-parameters-in-optional-chaining/-/plugin-bugfix-v8-spread-parameters-in-optional-chaining-7.18.9.tgz#a11af19aa373d68d561f08e0a57242350ed0ec50"
  integrity sha512-AHrP9jadvH7qlOj6PINbgSuphjQUAK7AOT7DPjBo9EHoLhQTnnK5u45e1Hd4DbSQEO9nqPWtQ89r+XEOWFScKg==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.9"
    "@babel/helper-skip-transparent-expression-wrappers" "^7.18.9"
    "@babel/plugin-proposal-optional-chaining" "^7.18.9"

"@babel/plugin-proposal-async-generator-functions@^7.20.1":
  version "7.20.1"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-async-generator-functions/-/plugin-proposal-async-generator-functions-7.20.1.tgz#352f02baa5d69f4e7529bdac39aaa02d41146af9"
  integrity sha512-Gh5rchzSwE4kC+o/6T8waD0WHEQIsDmjltY8WnWRXHUdH8axZhuH86Ov9M72YhJfDrZseQwuuWaaIT/TmePp3g==
  dependencies:
    "@babel/helper-environment-visitor" "^7.18.9"
    "@babel/helper-plugin-utils" "^7.19.0"
    "@babel/helper-remap-async-to-generator" "^7.18.9"
    "@babel/plugin-syntax-async-generators" "^7.8.4"

"@babel/plugin-proposal-class-properties@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-class-properties/-/plugin-proposal-class-properties-7.18.6.tgz#b110f59741895f7ec21a6fff696ec46265c446a3"
  integrity sha512-cumfXOF0+nzZrrN8Rf0t7M+tF6sZc7vhQwYQck9q1/5w2OExlD+b4v4RpMJFaV1Z7WcDRgO6FqvxqxGlwo+RHQ==
  dependencies:
    "@babel/helper-create-class-features-plugin" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-proposal-class-static-block@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-class-static-block/-/plugin-proposal-class-static-block-7.18.6.tgz#8aa81d403ab72d3962fc06c26e222dacfc9b9020"
  integrity sha512-+I3oIiNxrCpup3Gi8n5IGMwj0gOCAjcJUSQEcotNnCCPMEnixawOQ+KeJPlgfjzx+FKQ1QSyZOWe7wmoJp7vhw==
  dependencies:
    "@babel/helper-create-class-features-plugin" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/plugin-syntax-class-static-block" "^7.14.5"

"@babel/plugin-proposal-dynamic-import@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-dynamic-import/-/plugin-proposal-dynamic-import-7.18.6.tgz#72bcf8d408799f547d759298c3c27c7e7faa4d94"
  integrity sha512-1auuwmK+Rz13SJj36R+jqFPMJWyKEDd7lLSdOj4oJK0UTgGueSAtkrCvz9ewmgyU/P941Rv2fQwZJN8s6QruXw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/plugin-syntax-dynamic-import" "^7.8.3"

"@babel/plugin-proposal-export-namespace-from@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-export-namespace-from/-/plugin-proposal-export-namespace-from-7.18.9.tgz#5f7313ab348cdb19d590145f9247540e94761203"
  integrity sha512-k1NtHyOMvlDDFeb9G5PhUXuGj8m/wiwojgQVEhJ/fsVsMCpLyOP4h0uGEjYJKrRI+EVPlb5Jk+Gt9P97lOGwtA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.9"
    "@babel/plugin-syntax-export-namespace-from" "^7.8.3"

"@babel/plugin-proposal-json-strings@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-json-strings/-/plugin-proposal-json-strings-7.18.6.tgz#7e8788c1811c393aff762817e7dbf1ebd0c05f0b"
  integrity sha512-lr1peyn9kOdbYc0xr0OdHTZ5FMqS6Di+H0Fz2I/JwMzGmzJETNeOFq2pBySw6X/KFL5EWDjlJuMsUGRFb8fQgQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/plugin-syntax-json-strings" "^7.8.3"

"@babel/plugin-proposal-logical-assignment-operators@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-logical-assignment-operators/-/plugin-proposal-logical-assignment-operators-7.18.9.tgz#8148cbb350483bf6220af06fa6db3690e14b2e23"
  integrity sha512-128YbMpjCrP35IOExw2Fq+x55LMP42DzhOhX2aNNIdI9avSWl2PI0yuBWarr3RYpZBSPtabfadkH2yeRiMD61Q==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.9"
    "@babel/plugin-syntax-logical-assignment-operators" "^7.10.4"

"@babel/plugin-proposal-nullish-coalescing-operator@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-nullish-coalescing-operator/-/plugin-proposal-nullish-coalescing-operator-7.18.6.tgz#fdd940a99a740e577d6c753ab6fbb43fdb9467e1"
  integrity sha512-wQxQzxYeJqHcfppzBDnm1yAY0jSRkUXR2z8RePZYrKwMKgMlE8+Z6LUno+bd6LvbGh8Gltvy74+9pIYkr+XkKA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/plugin-syntax-nullish-coalescing-operator" "^7.8.3"

"@babel/plugin-proposal-numeric-separator@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-numeric-separator/-/plugin-proposal-numeric-separator-7.18.6.tgz#899b14fbafe87f053d2c5ff05b36029c62e13c75"
  integrity sha512-ozlZFogPqoLm8WBr5Z8UckIoE4YQ5KESVcNudyXOR8uqIkliTEgJ3RoketfG6pmzLdeZF0H/wjE9/cCEitBl7Q==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/plugin-syntax-numeric-separator" "^7.10.4"

"@babel/plugin-proposal-object-rest-spread@7.12.1":
  version "7.12.1"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-object-rest-spread/-/plugin-proposal-object-rest-spread-7.12.1.tgz#def9bd03cea0f9b72283dac0ec22d289c7691069"
  integrity sha512-s6SowJIjzlhx8o7lsFx5zmY4At6CTtDvgNQDdPzkBQucle58A6b/TTeEBYtyDgmcXjUTM+vE8YOGHZzzbc/ioA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.10.4"
    "@babel/plugin-syntax-object-rest-spread" "^7.8.0"
    "@babel/plugin-transform-parameters" "^7.12.1"

"@babel/plugin-proposal-object-rest-spread@^7.20.2":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-object-rest-spread/-/plugin-proposal-object-rest-spread-7.20.2.tgz#a556f59d555f06961df1e572bb5eca864c84022d"
  integrity sha512-Ks6uej9WFK+fvIMesSqbAto5dD8Dz4VuuFvGJFKgIGSkJuRGcrwGECPA1fDgQK3/DbExBJpEkTeYeB8geIFCSQ==
  dependencies:
    "@babel/compat-data" "^7.20.1"
    "@babel/helper-compilation-targets" "^7.20.0"
    "@babel/helper-plugin-utils" "^7.20.2"
    "@babel/plugin-syntax-object-rest-spread" "^7.8.3"
    "@babel/plugin-transform-parameters" "^7.20.1"

"@babel/plugin-proposal-optional-catch-binding@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-optional-catch-binding/-/plugin-proposal-optional-catch-binding-7.18.6.tgz#f9400d0e6a3ea93ba9ef70b09e72dd6da638a2cb"
  integrity sha512-Q40HEhs9DJQyaZfUjjn6vE8Cv4GmMHCYuMGIWUnlxH6400VGxOuwWsPt4FxXxJkC/5eOzgn0z21M9gMT4MOhbw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/plugin-syntax-optional-catch-binding" "^7.8.3"

"@babel/plugin-proposal-optional-chaining@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-optional-chaining/-/plugin-proposal-optional-chaining-7.18.9.tgz#e8e8fe0723f2563960e4bf5e9690933691915993"
  integrity sha512-v5nwt4IqBXihxGsW2QmCWMDS3B3bzGIk/EQVZz2ei7f3NJl8NzAJVvUmpDW5q1CRNY+Beb/k58UAH1Km1N411w==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.9"
    "@babel/helper-skip-transparent-expression-wrappers" "^7.18.9"
    "@babel/plugin-syntax-optional-chaining" "^7.8.3"

"@babel/plugin-proposal-private-methods@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-private-methods/-/plugin-proposal-private-methods-7.18.6.tgz#5209de7d213457548a98436fa2882f52f4be6bea"
  integrity sha512-nutsvktDItsNn4rpGItSNV2sz1XwS+nfU0Rg8aCx3W3NOKVzdMjJRu0O5OkgDp3ZGICSTbgRpxZoWsxoKRvbeA==
  dependencies:
    "@babel/helper-create-class-features-plugin" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-proposal-private-property-in-object@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-private-property-in-object/-/plugin-proposal-private-property-in-object-7.18.6.tgz#a64137b232f0aca3733a67eb1a144c192389c503"
  integrity sha512-9Rysx7FOctvT5ouj5JODjAFAkgGoudQuLPamZb0v1TGLpapdNaftzifU8NTWQm0IRjqoYypdrSmyWgkocDQ8Dw==
  dependencies:
    "@babel/helper-annotate-as-pure" "^7.18.6"
    "@babel/helper-create-class-features-plugin" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/plugin-syntax-private-property-in-object" "^7.14.5"

"@babel/plugin-proposal-unicode-property-regex@^7.18.6", "@babel/plugin-proposal-unicode-property-regex@^7.4.4":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-proposal-unicode-property-regex/-/plugin-proposal-unicode-property-regex-7.18.6.tgz#af613d2cd5e643643b65cded64207b15c85cb78e"
  integrity sha512-2BShG/d5yoZyXZfVePH91urL5wTG6ASZU9M4o03lKK8u8UW1y08OMttBSOADTcJrnPMpvDXRG3G8fyLh4ovs8w==
  dependencies:
    "@babel/helper-create-regexp-features-plugin" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-syntax-async-generators@^7.8.4":
  version "7.8.4"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-async-generators/-/plugin-syntax-async-generators-7.8.4.tgz#a983fb1aeb2ec3f6ed042a210f640e90e786fe0d"
  integrity sha512-tycmZxkGfZaxhMRbXlPXuVFpdWlXpir2W4AMhSJgRKzk/eDlIXOhb2LHWoLpDF7TEHylV5zNhykX6KAgHJmTNw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.8.0"

"@babel/plugin-syntax-class-properties@^7.12.13":
  version "7.12.13"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-class-properties/-/plugin-syntax-class-properties-7.12.13.tgz#b5c987274c4a3a82b89714796931a6b53544ae10"
  integrity sha512-fm4idjKla0YahUNgFNLCB0qySdsoPiZP3iQE3rky0mBUtMZ23yDJ9SJdg6dXTSDnulOVqiF3Hgr9nbXvXTQZYA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.12.13"

"@babel/plugin-syntax-class-static-block@^7.14.5":
  version "7.14.5"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-class-static-block/-/plugin-syntax-class-static-block-7.14.5.tgz#195df89b146b4b78b3bf897fd7a257c84659d406"
  integrity sha512-b+YyPmr6ldyNnM6sqYeMWE+bgJcJpO6yS4QD7ymxgH34GBPNDM/THBh8iunyvKIZztiwLH4CJZ0RxTk9emgpjw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.14.5"

"@babel/plugin-syntax-dynamic-import@^7.8.3":
  version "7.8.3"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-dynamic-import/-/plugin-syntax-dynamic-import-7.8.3.tgz#62bf98b2da3cd21d626154fc96ee5b3cb68eacb3"
  integrity sha512-5gdGbFon+PszYzqs83S3E5mpi7/y/8M9eC90MRTZfduQOYW76ig6SOSPNe41IG5LoP3FGBn2N0RjVDSQiS94kQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.8.0"

"@babel/plugin-syntax-export-namespace-from@^7.8.3":
  version "7.8.3"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-export-namespace-from/-/plugin-syntax-export-namespace-from-7.8.3.tgz#028964a9ba80dbc094c915c487ad7c4e7a66465a"
  integrity sha512-MXf5laXo6c1IbEbegDmzGPwGNTsHZmEy6QGznu5Sh2UCWvueywb2ee+CCE4zQiZstxU9BMoQO9i6zUFSY0Kj0Q==
  dependencies:
    "@babel/helper-plugin-utils" "^7.8.3"

"@babel/plugin-syntax-import-assertions@^7.20.0":
  version "7.20.0"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-import-assertions/-/plugin-syntax-import-assertions-7.20.0.tgz#bb50e0d4bea0957235390641209394e87bdb9cc4"
  integrity sha512-IUh1vakzNoWalR8ch/areW7qFopR2AEw03JlG7BbrDqmQ4X3q9uuipQwSGrUn7oGiemKjtSLDhNtQHzMHr1JdQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.19.0"

"@babel/plugin-syntax-json-strings@^7.8.3":
  version "7.8.3"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-json-strings/-/plugin-syntax-json-strings-7.8.3.tgz#01ca21b668cd8218c9e640cb6dd88c5412b2c96a"
  integrity sha512-lY6kdGpWHvjoe2vk4WrAapEuBR69EMxZl+RoGRhrFGNYVK8mOPAW8VfbT/ZgrFbXlDNiiaxQnAtgVCZ6jv30EA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.8.0"

"@babel/plugin-syntax-jsx@7.12.1":
  version "7.12.1"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-jsx/-/plugin-syntax-jsx-7.12.1.tgz#9d9d357cc818aa7ae7935917c1257f67677a0926"
  integrity sha512-1yRi7yAtB0ETgxdY9ti/p2TivUxJkTdhu/ZbF9MshVGqOx1TdB3b7xCXs49Fupgg50N45KcAsRP/ZqWjs9SRjg==
  dependencies:
    "@babel/helper-plugin-utils" "^7.10.4"

"@babel/plugin-syntax-jsx@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-jsx/-/plugin-syntax-jsx-7.18.6.tgz#a8feef63b010150abd97f1649ec296e849943ca0"
  integrity sha512-6mmljtAedFGTWu2p/8WIORGwy+61PLgOMPOdazc7YoJ9ZCWUyFy3A6CpPkRKLKD1ToAesxX8KGEViAiLo9N+7Q==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-syntax-logical-assignment-operators@^7.10.4":
  version "7.10.4"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-logical-assignment-operators/-/plugin-syntax-logical-assignment-operators-7.10.4.tgz#ca91ef46303530448b906652bac2e9fe9941f699"
  integrity sha512-d8waShlpFDinQ5MtvGU9xDAOzKH47+FFoney2baFIoMr952hKOLp1HR7VszoZvOsV/4+RRszNY7D17ba0te0ig==
  dependencies:
    "@babel/helper-plugin-utils" "^7.10.4"

"@babel/plugin-syntax-nullish-coalescing-operator@^7.8.3":
  version "7.8.3"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-nullish-coalescing-operator/-/plugin-syntax-nullish-coalescing-operator-7.8.3.tgz#167ed70368886081f74b5c36c65a88c03b66d1a9"
  integrity sha512-aSff4zPII1u2QD7y+F8oDsz19ew4IGEJg9SVW+bqwpwtfFleiQDMdzA/R+UlWDzfnHFCxxleFT0PMIrR36XLNQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.8.0"

"@babel/plugin-syntax-numeric-separator@^7.10.4":
  version "7.10.4"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-numeric-separator/-/plugin-syntax-numeric-separator-7.10.4.tgz#b9b070b3e33570cd9fd07ba7fa91c0dd37b9af97"
  integrity sha512-9H6YdfkcK/uOnY/K7/aA2xpzaAgkQn37yzWUMRK7OaPOqOpGS1+n0H5hxT9AUw9EsSjPW8SVyMJwYRtWs3X3ug==
  dependencies:
    "@babel/helper-plugin-utils" "^7.10.4"

"@babel/plugin-syntax-object-rest-spread@7.8.3", "@babel/plugin-syntax-object-rest-spread@^7.8.0", "@babel/plugin-syntax-object-rest-spread@^7.8.3":
  version "7.8.3"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-object-rest-spread/-/plugin-syntax-object-rest-spread-7.8.3.tgz#60e225edcbd98a640332a2e72dd3e66f1af55871"
  integrity sha512-XoqMijGZb9y3y2XskN+P1wUGiVwWZ5JmoDRwx5+3GmEplNyVM2s2Dg8ILFQm8rWM48orGy5YpI5Bl8U1y7ydlA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.8.0"

"@babel/plugin-syntax-optional-catch-binding@^7.8.3":
  version "7.8.3"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-optional-catch-binding/-/plugin-syntax-optional-catch-binding-7.8.3.tgz#6111a265bcfb020eb9efd0fdfd7d26402b9ed6c1"
  integrity sha512-6VPD0Pc1lpTqw0aKoeRTMiB+kWhAoT24PA+ksWSBrFtl5SIRVpZlwN3NNPQjehA2E/91FV3RjLWoVTglWcSV3Q==
  dependencies:
    "@babel/helper-plugin-utils" "^7.8.0"

"@babel/plugin-syntax-optional-chaining@^7.8.3":
  version "7.8.3"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-optional-chaining/-/plugin-syntax-optional-chaining-7.8.3.tgz#4f69c2ab95167e0180cd5336613f8c5788f7d48a"
  integrity sha512-KoK9ErH1MBlCPxV0VANkXW2/dw4vlbGDrFgz8bmUsBGYkFRcbRwMh6cIJubdPrkxRwuGdtCk0v/wPTKbQgBjkg==
  dependencies:
    "@babel/helper-plugin-utils" "^7.8.0"

"@babel/plugin-syntax-private-property-in-object@^7.14.5":
  version "7.14.5"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-private-property-in-object/-/plugin-syntax-private-property-in-object-7.14.5.tgz#0dc6671ec0ea22b6e94a1114f857970cd39de1ad"
  integrity sha512-0wVnp9dxJ72ZUJDV27ZfbSj6iHLoytYZmh3rFcxNnvsJF3ktkzLDZPy/mA17HGsaQT3/DQsWYX1f1QGWkCoVUg==
  dependencies:
    "@babel/helper-plugin-utils" "^7.14.5"

"@babel/plugin-syntax-top-level-await@^7.14.5":
  version "7.14.5"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-top-level-await/-/plugin-syntax-top-level-await-7.14.5.tgz#c1cfdadc35a646240001f06138247b741c34d94c"
  integrity sha512-hx++upLv5U1rgYfwe1xBQUhRmU41NEvpUvrp8jkrSCdvGSnM5/qdRMtylJ6PG5OFkBaHkbTAKTnd3/YyESRHFw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.14.5"

"@babel/plugin-syntax-typescript@^7.20.0":
  version "7.20.0"
  resolved "https://registry.npmmirror.com/@babel/plugin-syntax-typescript/-/plugin-syntax-typescript-7.20.0.tgz#4e9a0cfc769c85689b77a2e642d24e9f697fc8c7"
  integrity sha512-rd9TkG+u1CExzS4SM1BlMEhMXwFLKVjOAFFCDx9PbX5ycJWDoWMcwdJH9RhkPu1dOgn5TrxLot/Gx6lWFuAUNQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.19.0"

"@babel/plugin-transform-arrow-functions@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-arrow-functions/-/plugin-transform-arrow-functions-7.18.6.tgz#19063fcf8771ec7b31d742339dac62433d0611fe"
  integrity sha512-9S9X9RUefzrsHZmKMbDXxweEH+YlE8JJEuat9FdvW9Qh1cw7W64jELCtWNkPBPX5En45uy28KGvA/AySqUh8CQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-async-to-generator@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-async-to-generator/-/plugin-transform-async-to-generator-7.18.6.tgz#ccda3d1ab9d5ced5265fdb13f1882d5476c71615"
  integrity sha512-ARE5wZLKnTgPW7/1ftQmSi1CmkqqHo2DNmtztFhvgtOWSDfq0Cq9/9L+KnZNYSNrydBekhW3rwShduf59RoXag==
  dependencies:
    "@babel/helper-module-imports" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/helper-remap-async-to-generator" "^7.18.6"

"@babel/plugin-transform-block-scoped-functions@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-block-scoped-functions/-/plugin-transform-block-scoped-functions-7.18.6.tgz#9187bf4ba302635b9d70d986ad70f038726216a8"
  integrity sha512-ExUcOqpPWnliRcPqves5HJcJOvHvIIWfuS4sroBUenPuMdmW+SMHDakmtS7qOo13sVppmUijqeTv7qqGsvURpQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-block-scoping@^7.20.2":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-block-scoping/-/plugin-transform-block-scoping-7.20.2.tgz#f59b1767e6385c663fd0bce655db6ca9c8b236ed"
  integrity sha512-y5V15+04ry69OV2wULmwhEA6jwSWXO1TwAtIwiPXcvHcoOQUqpyMVd2bDsQJMW8AurjulIyUV8kDqtjSwHy1uQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.20.2"

"@babel/plugin-transform-classes@^7.20.2":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-classes/-/plugin-transform-classes-7.20.2.tgz#c0033cf1916ccf78202d04be4281d161f6709bb2"
  integrity sha512-9rbPp0lCVVoagvtEyQKSo5L8oo0nQS/iif+lwlAz29MccX2642vWDlSZK+2T2buxbopotId2ld7zZAzRfz9j1g==
  dependencies:
    "@babel/helper-annotate-as-pure" "^7.18.6"
    "@babel/helper-compilation-targets" "^7.20.0"
    "@babel/helper-environment-visitor" "^7.18.9"
    "@babel/helper-function-name" "^7.19.0"
    "@babel/helper-optimise-call-expression" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.20.2"
    "@babel/helper-replace-supers" "^7.19.1"
    "@babel/helper-split-export-declaration" "^7.18.6"
    globals "^11.1.0"

"@babel/plugin-transform-computed-properties@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-computed-properties/-/plugin-transform-computed-properties-7.18.9.tgz#2357a8224d402dad623caf6259b611e56aec746e"
  integrity sha512-+i0ZU1bCDymKakLxn5srGHrsAPRELC2WIbzwjLhHW9SIE1cPYkLCL0NlnXMZaM1vhfgA2+M7hySk42VBvrkBRw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.9"

"@babel/plugin-transform-destructuring@^7.20.2":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-destructuring/-/plugin-transform-destructuring-7.20.2.tgz#c23741cfa44ddd35f5e53896e88c75331b8b2792"
  integrity sha512-mENM+ZHrvEgxLTBXUiQ621rRXZes3KWUv6NdQlrnr1TkWVw+hUjQBZuP2X32qKlrlG2BzgR95gkuCRSkJl8vIw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.20.2"

"@babel/plugin-transform-dotall-regex@^7.18.6", "@babel/plugin-transform-dotall-regex@^7.4.4":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-dotall-regex/-/plugin-transform-dotall-regex-7.18.6.tgz#b286b3e7aae6c7b861e45bed0a2fafd6b1a4fef8"
  integrity sha512-6S3jpun1eEbAxq7TdjLotAsl4WpQI9DxfkycRcKrjhQYzU87qpXdknpBg/e+TdcMehqGnLFi7tnFUBR02Vq6wg==
  dependencies:
    "@babel/helper-create-regexp-features-plugin" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-duplicate-keys@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-duplicate-keys/-/plugin-transform-duplicate-keys-7.18.9.tgz#687f15ee3cdad6d85191eb2a372c4528eaa0ae0e"
  integrity sha512-d2bmXCtZXYc59/0SanQKbiWINadaJXqtvIQIzd4+hNwkWBgyCd5F/2t1kXoUdvPMrxzPvhK6EMQRROxsue+mfw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.9"

"@babel/plugin-transform-exponentiation-operator@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-exponentiation-operator/-/plugin-transform-exponentiation-operator-7.18.6.tgz#421c705f4521888c65e91fdd1af951bfefd4dacd"
  integrity sha512-wzEtc0+2c88FVR34aQmiz56dxEkxr2g8DQb/KfaFa1JYXOFVsbhvAonFN6PwVWj++fKmku8NP80plJ5Et4wqHw==
  dependencies:
    "@babel/helper-builder-binary-assignment-operator-visitor" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-for-of@^7.18.8":
  version "7.18.8"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-for-of/-/plugin-transform-for-of-7.18.8.tgz#6ef8a50b244eb6a0bdbad0c7c61877e4e30097c1"
  integrity sha512-yEfTRnjuskWYo0k1mHUqrVWaZwrdq8AYbfrpqULOJOaucGSp4mNMVps+YtA8byoevxS/urwU75vyhQIxcCgiBQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-function-name@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-function-name/-/plugin-transform-function-name-7.18.9.tgz#cc354f8234e62968946c61a46d6365440fc764e0"
  integrity sha512-WvIBoRPaJQ5yVHzcnJFor7oS5Ls0PYixlTYE63lCj2RtdQEl15M68FXQlxnG6wdraJIXRdR7KI+hQ7q/9QjrCQ==
  dependencies:
    "@babel/helper-compilation-targets" "^7.18.9"
    "@babel/helper-function-name" "^7.18.9"
    "@babel/helper-plugin-utils" "^7.18.9"

"@babel/plugin-transform-literals@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-literals/-/plugin-transform-literals-7.18.9.tgz#72796fdbef80e56fba3c6a699d54f0de557444bc"
  integrity sha512-IFQDSRoTPnrAIrI5zoZv73IFeZu2dhu6irxQjY9rNjTT53VmKg9fenjvoiOWOkJ6mm4jKVPtdMzBY98Fp4Z4cg==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.9"

"@babel/plugin-transform-member-expression-literals@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-member-expression-literals/-/plugin-transform-member-expression-literals-7.18.6.tgz#ac9fdc1a118620ac49b7e7a5d2dc177a1bfee88e"
  integrity sha512-qSF1ihLGO3q+/g48k85tUjD033C29TNTVB2paCwZPVmOsjn9pClvYYrM2VeJpBY2bcNkuny0YUyTNRyRxJ54KA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-modules-amd@^7.19.6":
  version "7.19.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-modules-amd/-/plugin-transform-modules-amd-7.19.6.tgz#aca391801ae55d19c4d8d2ebfeaa33df5f2a2cbd"
  integrity sha512-uG3od2mXvAtIFQIh0xrpLH6r5fpSQN04gIVovl+ODLdUMANokxQLZnPBHcjmv3GxRjnqwLuHvppjjcelqUFZvg==
  dependencies:
    "@babel/helper-module-transforms" "^7.19.6"
    "@babel/helper-plugin-utils" "^7.19.0"

"@babel/plugin-transform-modules-commonjs@^7.19.6":
  version "7.19.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-modules-commonjs/-/plugin-transform-modules-commonjs-7.19.6.tgz#25b32feef24df8038fc1ec56038917eacb0b730c"
  integrity sha512-8PIa1ym4XRTKuSsOUXqDG0YaOlEuTVvHMe5JCfgBMOtHvJKw/4NGovEGN33viISshG/rZNVrACiBmPQLvWN8xQ==
  dependencies:
    "@babel/helper-module-transforms" "^7.19.6"
    "@babel/helper-plugin-utils" "^7.19.0"
    "@babel/helper-simple-access" "^7.19.4"

"@babel/plugin-transform-modules-systemjs@^7.19.6":
  version "7.19.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-modules-systemjs/-/plugin-transform-modules-systemjs-7.19.6.tgz#59e2a84064b5736a4471b1aa7b13d4431d327e0d"
  integrity sha512-fqGLBepcc3kErfR9R3DnVpURmckXP7gj7bAlrTQyBxrigFqszZCkFkcoxzCp2v32XmwXLvbw+8Yq9/b+QqksjQ==
  dependencies:
    "@babel/helper-hoist-variables" "^7.18.6"
    "@babel/helper-module-transforms" "^7.19.6"
    "@babel/helper-plugin-utils" "^7.19.0"
    "@babel/helper-validator-identifier" "^7.19.1"

"@babel/plugin-transform-modules-umd@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-modules-umd/-/plugin-transform-modules-umd-7.18.6.tgz#81d3832d6034b75b54e62821ba58f28ed0aab4b9"
  integrity sha512-dcegErExVeXcRqNtkRU/z8WlBLnvD4MRnHgNs3MytRO1Mn1sHRyhbcpYbVMGclAqOjdW+9cfkdZno9dFdfKLfQ==
  dependencies:
    "@babel/helper-module-transforms" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-named-capturing-groups-regex@^7.19.1":
  version "7.19.1"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-named-capturing-groups-regex/-/plugin-transform-named-capturing-groups-regex-7.19.1.tgz#ec7455bab6cd8fb05c525a94876f435a48128888"
  integrity sha512-oWk9l9WItWBQYS4FgXD4Uyy5kq898lvkXpXQxoJEY1RnvPk4R/Dvu2ebXU9q8lP+rlMwUQTFf2Ok6d78ODa0kw==
  dependencies:
    "@babel/helper-create-regexp-features-plugin" "^7.19.0"
    "@babel/helper-plugin-utils" "^7.19.0"

"@babel/plugin-transform-new-target@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-new-target/-/plugin-transform-new-target-7.18.6.tgz#d128f376ae200477f37c4ddfcc722a8a1b3246a8"
  integrity sha512-DjwFA/9Iu3Z+vrAn+8pBUGcjhxKguSMlsFqeCKbhb9BAV756v0krzVK04CRDi/4aqmk8BsHb4a/gFcaA5joXRw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-object-super@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-object-super/-/plugin-transform-object-super-7.18.6.tgz#fb3c6ccdd15939b6ff7939944b51971ddc35912c"
  integrity sha512-uvGz6zk+pZoS1aTZrOvrbj6Pp/kK2mp45t2B+bTDre2UgsZZ8EZLSJtUg7m/no0zOJUWgFONpB7Zv9W2tSaFlA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/helper-replace-supers" "^7.18.6"

"@babel/plugin-transform-parameters@^7.12.1", "@babel/plugin-transform-parameters@^7.20.1":
  version "7.20.1"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-parameters/-/plugin-transform-parameters-7.20.1.tgz#9a5aa370fdcce36f110455e9369db7afca0f9eeb"
  integrity sha512-nDvKLrAvl+kf6BOy1UJ3MGwzzfTMgppxwiD2Jb4LO3xjYyZq30oQzDNJbCQpMdG9+j2IXHoiMrw5Cm/L6ZoxXQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.19.0"

"@babel/plugin-transform-property-literals@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-property-literals/-/plugin-transform-property-literals-7.18.6.tgz#e22498903a483448e94e032e9bbb9c5ccbfc93a3"
  integrity sha512-cYcs6qlgafTud3PAzrrRNbQtfpQ8+y/+M5tKmksS9+M1ckbH6kzY8MrexEM9mcA6JDsukE19iIRvAyYl463sMg==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-react-constant-elements@^7.12.1", "@babel/plugin-transform-react-constant-elements@^7.18.12":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-react-constant-elements/-/plugin-transform-react-constant-elements-7.20.2.tgz#3f02c784e0b711970d7d8ccc96c4359d64e27ac7"
  integrity sha512-KS/G8YI8uwMGKErLFOHS/ekhqdHhpEloxs43NecQHVgo2QuQSyJhGIY1fL8UGl9wy5ItVwwoUL4YxVqsplGq2g==
  dependencies:
    "@babel/helper-plugin-utils" "^7.20.2"

"@babel/plugin-transform-react-display-name@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-react-display-name/-/plugin-transform-react-display-name-7.18.6.tgz#8b1125f919ef36ebdfff061d664e266c666b9415"
  integrity sha512-TV4sQ+T013n61uMoygyMRm+xf04Bd5oqFpv2jAEQwSZ8NwQA7zeRPg1LMVg2PWi3zWBz+CLKD+v5bcpZ/BS0aA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-react-jsx-development@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-react-jsx-development/-/plugin-transform-react-jsx-development-7.18.6.tgz#dbe5c972811e49c7405b630e4d0d2e1380c0ddc5"
  integrity sha512-SA6HEjwYFKF7WDjWcMcMGUimmw/nhNRDWxr+KaLSCrkD/LMDBvWRmHAYgE1HDeF8KUuI8OAu+RT6EOtKxSW2qA==
  dependencies:
    "@babel/plugin-transform-react-jsx" "^7.18.6"

"@babel/plugin-transform-react-jsx@^7.18.6":
  version "7.19.0"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-react-jsx/-/plugin-transform-react-jsx-7.19.0.tgz#b3cbb7c3a00b92ec8ae1027910e331ba5c500eb9"
  integrity sha512-UVEvX3tXie3Szm3emi1+G63jyw1w5IcMY0FSKM+CRnKRI5Mr1YbCNgsSTwoTwKphQEG9P+QqmuRFneJPZuHNhg==
  dependencies:
    "@babel/helper-annotate-as-pure" "^7.18.6"
    "@babel/helper-module-imports" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.19.0"
    "@babel/plugin-syntax-jsx" "^7.18.6"
    "@babel/types" "^7.19.0"

"@babel/plugin-transform-react-pure-annotations@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-react-pure-annotations/-/plugin-transform-react-pure-annotations-7.18.6.tgz#561af267f19f3e5d59291f9950fd7b9663d0d844"
  integrity sha512-I8VfEPg9r2TRDdvnHgPepTKvuRomzA8+u+nhY7qSI1fR2hRNebasZEETLyM5mAUr0Ku56OkXJ0I7NHJnO6cJiQ==
  dependencies:
    "@babel/helper-annotate-as-pure" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-regenerator@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-regenerator/-/plugin-transform-regenerator-7.18.6.tgz#585c66cb84d4b4bf72519a34cfce761b8676ca73"
  integrity sha512-poqRI2+qiSdeldcz4wTSTXBRryoq3Gc70ye7m7UD5Ww0nE29IXqMl6r7Nd15WBgRd74vloEMlShtH6CKxVzfmQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"
    regenerator-transform "^0.15.0"

"@babel/plugin-transform-reserved-words@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-reserved-words/-/plugin-transform-reserved-words-7.18.6.tgz#b1abd8ebf8edaa5f7fe6bbb8d2133d23b6a6f76a"
  integrity sha512-oX/4MyMoypzHjFrT1CdivfKZ+XvIPMFXwwxHp/r0Ddy2Vuomt4HDFGmft1TAY2yiTKiNSsh3kjBAzcM8kSdsjA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-runtime@^7.15.0":
  version "7.19.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-runtime/-/plugin-transform-runtime-7.19.6.tgz#9d2a9dbf4e12644d6f46e5e75bfbf02b5d6e9194"
  integrity sha512-PRH37lz4JU156lYFW1p8OxE5i7d6Sl/zV58ooyr+q1J1lnQPyg5tIiXlIwNVhJaY4W3TmOtdc8jqdXQcB1v5Yw==
  dependencies:
    "@babel/helper-module-imports" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.19.0"
    babel-plugin-polyfill-corejs2 "^0.3.3"
    babel-plugin-polyfill-corejs3 "^0.6.0"
    babel-plugin-polyfill-regenerator "^0.4.1"
    semver "^6.3.0"

"@babel/plugin-transform-shorthand-properties@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-shorthand-properties/-/plugin-transform-shorthand-properties-7.18.6.tgz#6d6df7983d67b195289be24909e3f12a8f664dc9"
  integrity sha512-eCLXXJqv8okzg86ywZJbRn19YJHU4XUa55oz2wbHhaQVn/MM+XhukiT7SYqp/7o00dg52Rj51Ny+Ecw4oyoygw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-spread@^7.19.0":
  version "7.19.0"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-spread/-/plugin-transform-spread-7.19.0.tgz#dd60b4620c2fec806d60cfaae364ec2188d593b6"
  integrity sha512-RsuMk7j6n+r752EtzyScnWkQyuJdli6LdO5Klv8Yx0OfPVTcQkIUfS8clx5e9yHXzlnhOZF3CbQ8C2uP5j074w==
  dependencies:
    "@babel/helper-plugin-utils" "^7.19.0"
    "@babel/helper-skip-transparent-expression-wrappers" "^7.18.9"

"@babel/plugin-transform-sticky-regex@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-sticky-regex/-/plugin-transform-sticky-regex-7.18.6.tgz#c6706eb2b1524028e317720339583ad0f444adcc"
  integrity sha512-kfiDrDQ+PBsQDO85yj1icueWMfGfJFKN1KCkndygtu/C9+XUfydLC8Iv5UYJqRwy4zk8EcplRxEOeLyjq1gm6Q==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/plugin-transform-template-literals@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-template-literals/-/plugin-transform-template-literals-7.18.9.tgz#04ec6f10acdaa81846689d63fae117dd9c243a5e"
  integrity sha512-S8cOWfT82gTezpYOiVaGHrCbhlHgKhQt8XH5ES46P2XWmX92yisoZywf5km75wv5sYcXDUCLMmMxOLCtthDgMA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.9"

"@babel/plugin-transform-typeof-symbol@^7.18.9":
  version "7.18.9"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-typeof-symbol/-/plugin-transform-typeof-symbol-7.18.9.tgz#c8cea68263e45addcd6afc9091429f80925762c0"
  integrity sha512-SRfwTtF11G2aemAZWivL7PD+C9z52v9EvMqH9BuYbabyPuKUvSWks3oCg6041pT925L4zVFqaVBeECwsmlguEw==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.9"

"@babel/plugin-transform-typescript@^7.18.6":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-typescript/-/plugin-transform-typescript-7.20.2.tgz#91515527b376fc122ba83b13d70b01af8fe98f3f"
  integrity sha512-jvS+ngBfrnTUBfOQq8NfGnSbF9BrqlR6hjJ2yVxMkmO5nL/cdifNbI30EfjRlN4g5wYWNnMPyj5Sa6R1pbLeag==
  dependencies:
    "@babel/helper-create-class-features-plugin" "^7.20.2"
    "@babel/helper-plugin-utils" "^7.20.2"
    "@babel/plugin-syntax-typescript" "^7.20.0"

"@babel/plugin-transform-unicode-escapes@^7.18.10":
  version "7.18.10"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-unicode-escapes/-/plugin-transform-unicode-escapes-7.18.10.tgz#1ecfb0eda83d09bbcb77c09970c2dd55832aa246"
  integrity sha512-kKAdAI+YzPgGY/ftStBFXTI1LZFju38rYThnfMykS+IXy8BVx+res7s2fxf1l8I35DV2T97ezo6+SGrXz6B3iQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.9"

"@babel/plugin-transform-unicode-regex@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/plugin-transform-unicode-regex/-/plugin-transform-unicode-regex-7.18.6.tgz#194317225d8c201bbae103364ffe9e2cea36cdca"
  integrity sha512-gE7A6Lt7YLnNOL3Pb9BNeZvi+d8l7tcRrG4+pwJjK9hD2xX4mEvjlQW60G9EEmfXVYRPv9VRQcyegIVHCql/AA==
  dependencies:
    "@babel/helper-create-regexp-features-plugin" "^7.18.6"
    "@babel/helper-plugin-utils" "^7.18.6"

"@babel/preset-env@^7.12.1", "@babel/preset-env@^7.15.6", "@babel/preset-env@^7.19.4":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/preset-env/-/preset-env-7.20.2.tgz#9b1642aa47bb9f43a86f9630011780dab7f86506"
  integrity sha512-1G0efQEWR1EHkKvKHqbG+IN/QdgwfByUpM5V5QroDzGV2t3S/WXNQd693cHiHTlCFMpr9B6FkPFXDA2lQcKoDg==
  dependencies:
    "@babel/compat-data" "^7.20.1"
    "@babel/helper-compilation-targets" "^7.20.0"
    "@babel/helper-plugin-utils" "^7.20.2"
    "@babel/helper-validator-option" "^7.18.6"
    "@babel/plugin-bugfix-safari-id-destructuring-collision-in-function-expression" "^7.18.6"
    "@babel/plugin-bugfix-v8-spread-parameters-in-optional-chaining" "^7.18.9"
    "@babel/plugin-proposal-async-generator-functions" "^7.20.1"
    "@babel/plugin-proposal-class-properties" "^7.18.6"
    "@babel/plugin-proposal-class-static-block" "^7.18.6"
    "@babel/plugin-proposal-dynamic-import" "^7.18.6"
    "@babel/plugin-proposal-export-namespace-from" "^7.18.9"
    "@babel/plugin-proposal-json-strings" "^7.18.6"
    "@babel/plugin-proposal-logical-assignment-operators" "^7.18.9"
    "@babel/plugin-proposal-nullish-coalescing-operator" "^7.18.6"
    "@babel/plugin-proposal-numeric-separator" "^7.18.6"
    "@babel/plugin-proposal-object-rest-spread" "^7.20.2"
    "@babel/plugin-proposal-optional-catch-binding" "^7.18.6"
    "@babel/plugin-proposal-optional-chaining" "^7.18.9"
    "@babel/plugin-proposal-private-methods" "^7.18.6"
    "@babel/plugin-proposal-private-property-in-object" "^7.18.6"
    "@babel/plugin-proposal-unicode-property-regex" "^7.18.6"
    "@babel/plugin-syntax-async-generators" "^7.8.4"
    "@babel/plugin-syntax-class-properties" "^7.12.13"
    "@babel/plugin-syntax-class-static-block" "^7.14.5"
    "@babel/plugin-syntax-dynamic-import" "^7.8.3"
    "@babel/plugin-syntax-export-namespace-from" "^7.8.3"
    "@babel/plugin-syntax-import-assertions" "^7.20.0"
    "@babel/plugin-syntax-json-strings" "^7.8.3"
    "@babel/plugin-syntax-logical-assignment-operators" "^7.10.4"
    "@babel/plugin-syntax-nullish-coalescing-operator" "^7.8.3"
    "@babel/plugin-syntax-numeric-separator" "^7.10.4"
    "@babel/plugin-syntax-object-rest-spread" "^7.8.3"
    "@babel/plugin-syntax-optional-catch-binding" "^7.8.3"
    "@babel/plugin-syntax-optional-chaining" "^7.8.3"
    "@babel/plugin-syntax-private-property-in-object" "^7.14.5"
    "@babel/plugin-syntax-top-level-await" "^7.14.5"
    "@babel/plugin-transform-arrow-functions" "^7.18.6"
    "@babel/plugin-transform-async-to-generator" "^7.18.6"
    "@babel/plugin-transform-block-scoped-functions" "^7.18.6"
    "@babel/plugin-transform-block-scoping" "^7.20.2"
    "@babel/plugin-transform-classes" "^7.20.2"
    "@babel/plugin-transform-computed-properties" "^7.18.9"
    "@babel/plugin-transform-destructuring" "^7.20.2"
    "@babel/plugin-transform-dotall-regex" "^7.18.6"
    "@babel/plugin-transform-duplicate-keys" "^7.18.9"
    "@babel/plugin-transform-exponentiation-operator" "^7.18.6"
    "@babel/plugin-transform-for-of" "^7.18.8"
    "@babel/plugin-transform-function-name" "^7.18.9"
    "@babel/plugin-transform-literals" "^7.18.9"
    "@babel/plugin-transform-member-expression-literals" "^7.18.6"
    "@babel/plugin-transform-modules-amd" "^7.19.6"
    "@babel/plugin-transform-modules-commonjs" "^7.19.6"
    "@babel/plugin-transform-modules-systemjs" "^7.19.6"
    "@babel/plugin-transform-modules-umd" "^7.18.6"
    "@babel/plugin-transform-named-capturing-groups-regex" "^7.19.1"
    "@babel/plugin-transform-new-target" "^7.18.6"
    "@babel/plugin-transform-object-super" "^7.18.6"
    "@babel/plugin-transform-parameters" "^7.20.1"
    "@babel/plugin-transform-property-literals" "^7.18.6"
    "@babel/plugin-transform-regenerator" "^7.18.6"
    "@babel/plugin-transform-reserved-words" "^7.18.6"
    "@babel/plugin-transform-shorthand-properties" "^7.18.6"
    "@babel/plugin-transform-spread" "^7.19.0"
    "@babel/plugin-transform-sticky-regex" "^7.18.6"
    "@babel/plugin-transform-template-literals" "^7.18.9"
    "@babel/plugin-transform-typeof-symbol" "^7.18.9"
    "@babel/plugin-transform-unicode-escapes" "^7.18.10"
    "@babel/plugin-transform-unicode-regex" "^7.18.6"
    "@babel/preset-modules" "^0.1.5"
    "@babel/types" "^7.20.2"
    babel-plugin-polyfill-corejs2 "^0.3.3"
    babel-plugin-polyfill-corejs3 "^0.6.0"
    babel-plugin-polyfill-regenerator "^0.4.1"
    core-js-compat "^3.25.1"
    semver "^6.3.0"

"@babel/preset-modules@^0.1.5":
  version "0.1.5"
  resolved "https://registry.npmmirror.com/@babel/preset-modules/-/preset-modules-0.1.5.tgz#ef939d6e7f268827e1841638dc6ff95515e115d9"
  integrity sha512-A57th6YRG7oR3cq/yt/Y84MvGgE0eJG2F1JLhKuyG+jFxEgrd/HAMJatiFtmOiZurz+0DkrvbheCLaV5f2JfjA==
  dependencies:
    "@babel/helper-plugin-utils" "^7.0.0"
    "@babel/plugin-proposal-unicode-property-regex" "^7.4.4"
    "@babel/plugin-transform-dotall-regex" "^7.4.4"
    "@babel/types" "^7.4.4"
    esutils "^2.0.2"

"@babel/preset-react@^7.12.13", "@babel/preset-react@^7.12.5", "@babel/preset-react@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/preset-react/-/preset-react-7.18.6.tgz#979f76d6277048dc19094c217b507f3ad517dd2d"
  integrity sha512-zXr6atUmyYdiWRVLOZahakYmOBHtWc2WGCkP8PYTgZi0iJXDY2CN180TdrIW4OGOAdLc7TifzDIvtx6izaRIzg==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/helper-validator-option" "^7.18.6"
    "@babel/plugin-transform-react-display-name" "^7.18.6"
    "@babel/plugin-transform-react-jsx" "^7.18.6"
    "@babel/plugin-transform-react-jsx-development" "^7.18.6"
    "@babel/plugin-transform-react-pure-annotations" "^7.18.6"

"@babel/preset-typescript@^7.12.16", "@babel/preset-typescript@^7.18.6":
  version "7.18.6"
  resolved "https://registry.npmmirror.com/@babel/preset-typescript/-/preset-typescript-7.18.6.tgz#ce64be3e63eddc44240c6358daefac17b3186399"
  integrity sha512-s9ik86kXBAnD760aybBucdpnLsAt0jK1xqJn2juOn9lkOvSHV60os5hxoVJsPzMQxvnUJFAlkont2DvvaYEBtQ==
  dependencies:
    "@babel/helper-plugin-utils" "^7.18.6"
    "@babel/helper-validator-option" "^7.18.6"
    "@babel/plugin-transform-typescript" "^7.18.6"

"@babel/runtime-corejs3@^7.15.4":
  version "7.20.1"
  resolved "https://registry.npmmirror.com/@babel/runtime-corejs3/-/runtime-corejs3-7.20.1.tgz#d0775a49bb5fba77e42cbb7276c9955c7b05af8d"
  integrity sha512-CGulbEDcg/ND1Im7fUNRZdGXmX2MTWVVZacQi/6DiKE5HNwZ3aVTm5PV4lO8HHz0B2h8WQyvKKjbX5XgTtydsg==
  dependencies:
    core-js-pure "^3.25.1"
    regenerator-runtime "^0.13.10"

"@babel/runtime@^7.1.2", "@babel/runtime@^7.10.2", "@babel/runtime@^7.10.3", "@babel/runtime@^7.12.13", "@babel/runtime@^7.15.4", "@babel/runtime@^7.8.4":
  version "7.20.1"
  resolved "https://registry.npmmirror.com/@babel/runtime/-/runtime-7.20.1.tgz#1148bb33ab252b165a06698fde7576092a78b4a9"
  integrity sha512-mrzLkl6U9YLF8qpqI7TB82PESyEGjm/0Ly91jG575eVxMMlb8fYfOXFZIJ8XfLrJZQbm7dlKry2bJmXBUEkdFg==
  dependencies:
    regenerator-runtime "^0.13.10"

"@babel/template@^7.12.7", "@babel/template@^7.18.10":
  version "7.18.10"
  resolved "https://registry.npmmirror.com/@babel/template/-/template-7.18.10.tgz#6f9134835970d1dbf0835c0d100c9f38de0c5e71"
  integrity sha512-TI+rCtooWHr3QJ27kJxfjutghu44DLnasDMwpDqCXVTal9RLp3RSYNh4NdBrRP2cQAoG9A8juOQl6P6oZG4JxA==
  dependencies:
    "@babel/code-frame" "^7.18.6"
    "@babel/parser" "^7.18.10"
    "@babel/types" "^7.18.10"

"@babel/template@^7.22.15":
  version "7.22.15"
  resolved "https://registry.yarnpkg.com/@babel/template/-/template-7.22.15.tgz#09576efc3830f0430f4548ef971dde1350ef2f38"
  integrity sha512-QPErUVm4uyJa60rkI73qneDacvdvzxshT3kksGqlGWYdOTIUOwJ7RDUL8sGqslY1uXWSL6xMFKEXDS3ox2uF0w==
  dependencies:
    "@babel/code-frame" "^7.22.13"
    "@babel/parser" "^7.22.15"
    "@babel/types" "^7.22.15"

"@babel/traverse@^7.12.13", "@babel/traverse@^7.12.9", "@babel/traverse@^7.19.0", "@babel/traverse@^7.19.1", "@babel/traverse@^7.20.1":
  version "7.23.2"
  resolved "https://registry.yarnpkg.com/@babel/traverse/-/traverse-7.23.2.tgz#329c7a06735e144a506bdb2cad0268b7f46f4ad8"
  integrity sha512-azpe59SQ48qG6nu2CzcMLbxUudtN+dOM9kDbUqGq3HXUJRlo7i8fvPoxQUzYgLZ4cMVmuZgm8vvBpNeRhd6XSw==
  dependencies:
    "@babel/code-frame" "^7.22.13"
    "@babel/generator" "^7.23.0"
    "@babel/helper-environment-visitor" "^7.22.20"
    "@babel/helper-function-name" "^7.23.0"
    "@babel/helper-hoist-variables" "^7.22.5"
    "@babel/helper-split-export-declaration" "^7.22.6"
    "@babel/parser" "^7.23.0"
    "@babel/types" "^7.23.0"
    debug "^4.1.0"
    globals "^11.1.0"

"@babel/types@^7.12.6", "@babel/types@^7.12.7", "@babel/types@^7.18.10", "@babel/types@^7.18.6", "@babel/types@^7.18.9", "@babel/types@^7.19.0", "@babel/types@^7.20.0", "@babel/types@^7.20.2", "@babel/types@^7.4.4":
  version "7.20.2"
  resolved "https://registry.npmmirror.com/@babel/types/-/types-7.20.2.tgz#67ac09266606190f496322dbaff360fdaa5e7842"
  integrity sha512-FnnvsNWgZCr232sqtXggapvlkk/tuwR/qhGzcmxI0GXLCjmPYQPzio2FbdlWuY6y1sHFfQKk+rRbUZ9VStQMog==
  dependencies:
    "@babel/helper-string-parser" "^7.19.4"
    "@babel/helper-validator-identifier" "^7.19.1"
    to-fast-properties "^2.0.0"

"@babel/types@^7.22.15", "@babel/types@^7.22.5", "@babel/types@^7.23.0":
  version "7.23.0"
  resolved "https://registry.yarnpkg.com/@babel/types/-/types-7.23.0.tgz#8c1f020c9df0e737e4e247c0619f58c68458aaeb"
  integrity sha512-0oIyUfKoI3mSqMvsxBdclDwxXKXAUA8v/apZbc+iSyARYou1o8ZGDxbUYyLFoW2arqS2jDGqJuZvv1d/io1axg==
  dependencies:
    "@babel/helper-string-parser" "^7.22.5"
    "@babel/helper-validator-identifier" "^7.22.20"
    to-fast-properties "^2.0.0"

"@docsearch/css@3.3.0":
  version "3.3.0"
  resolved "https://registry.npmmirror.com/@docsearch/css/-/css-3.3.0.tgz#d698e48302d12240d7c2f7452ccb2d2239a8cd80"
  integrity sha512-rODCdDtGyudLj+Va8b6w6Y85KE85bXRsps/R4Yjwt5vueXKXZQKYw0aA9knxLBT6a/bI/GMrAcmCR75KYOM6hg==

"@docsearch/react@^3.0.0-alpha.39":
  version "3.3.0"
  resolved "https://registry.npmmirror.com/@docsearch/react/-/react-3.3.0.tgz#b8ac8e7f49b9bf2f96d34c24bc1cfd097ec0eead"
  integrity sha512-fhS5adZkae2SSdMYEMVg6pxI5a/cE+tW16ki1V0/ur4Fdok3hBRkmN/H8VvlXnxzggkQIIRIVvYPn00JPjen3A==
  dependencies:
    "@algolia/autocomplete-core" "1.7.2"
    "@algolia/autocomplete-preset-algolia" "1.7.2"
    "@docsearch/css" "3.3.0"
    algoliasearch "^4.0.0"

"@docusaurus/core@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/core/-/core-0.0.0-4193.tgz#1fe5ac8ab7b062411dd8e413617cc9a1e4c4d15c"
  integrity sha512-mC3YLaFgK8JqW3E7b2lCtIlQOVnzqOP0FwtI0+ilkx9v9F+DfgNQzJJ7Kk2RIXeDKu0e2AnjS7YBmRUwpgHRRg==
  dependencies:
    "@babel/core" "^7.12.16"
    "@babel/generator" "^7.12.15"
    "@babel/plugin-syntax-dynamic-import" "^7.8.3"
    "@babel/plugin-transform-runtime" "^7.15.0"
    "@babel/preset-env" "^7.15.6"
    "@babel/preset-react" "^7.12.13"
    "@babel/preset-typescript" "^7.12.16"
    "@babel/runtime" "^7.15.4"
    "@babel/runtime-corejs3" "^7.15.4"
    "@babel/traverse" "^7.12.13"
    "@docusaurus/cssnano-preset" "0.0.0-4193"
    "@docusaurus/react-loadable" "5.5.2"
    "@docusaurus/types" "0.0.0-4193"
    "@docusaurus/utils" "0.0.0-4193"
    "@docusaurus/utils-common" "0.0.0-4193"
    "@docusaurus/utils-validation" "0.0.0-4193"
    "@slorber/static-site-generator-webpack-plugin" "^4.0.0"
    "@svgr/webpack" "^5.5.0"
    autoprefixer "^10.3.5"
    babel-loader "^8.2.2"
    babel-plugin-dynamic-import-node "2.3.0"
    boxen "^5.0.1"
    chalk "^4.1.2"
    chokidar "^3.5.2"
    clean-css "^5.1.5"
    commander "^5.1.0"
    copy-webpack-plugin "^9.0.1"
    core-js "^3.18.0"
    css-loader "^5.1.1"
    css-minimizer-webpack-plugin "^3.0.2"
    cssnano "^5.0.8"
    del "^6.0.0"
    detect-port "^1.3.0"
    escape-html "^1.0.3"
    eta "^1.12.3"
    file-loader "^6.2.0"
    fs-extra "^10.0.0"
    github-slugger "^1.4.0"
    globby "^11.0.2"
    html-minifier-terser "^6.0.2"
    html-tags "^3.1.0"
    html-webpack-plugin "^5.4.0"
    import-fresh "^3.3.0"
    is-root "^2.1.0"
    leven "^3.1.0"
    lodash "^4.17.20"
    mini-css-extract-plugin "^1.6.0"
    nprogress "^0.2.0"
    postcss "^8.3.7"
    postcss-loader "^6.1.1"
    prompts "^2.4.1"
    react-dev-utils "12.0.0-next.47"
    react-error-overlay "^6.0.9"
    react-helmet "^6.1.0"
    react-loadable "npm:@docusaurus/react-loadable@5.5.2"
    react-loadable-ssr-addon-v5-slorber "^1.0.1"
    react-router "^5.2.0"
    react-router-config "^5.1.1"
    react-router-dom "^5.2.0"
    remark-admonitions "^1.2.1"
    resolve-pathname "^3.0.0"
    rtl-detect "^1.0.4"
    semver "^7.3.4"
    serve-handler "^6.1.3"
    shelljs "^0.8.4"
    std-env "^2.2.1"
    strip-ansi "^6.0.0"
    terser-webpack-plugin "^5.2.4"
    tslib "^2.3.1"
    update-notifier "^5.1.0"
    url-loader "^4.1.1"
    wait-on "^6.0.0"
    webpack "^5.61.0"
    webpack-bundle-analyzer "^4.4.2"
    webpack-dev-server "^4.4.0"
    webpack-merge "^5.8.0"
    webpackbar "^5.0.0-3"

"@docusaurus/cssnano-preset@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/cssnano-preset/-/cssnano-preset-0.0.0-4193.tgz#94fe5fbccf976e67781876dafe1e9d7d3cb77ae6"
  integrity sha512-aB8JNvHU/BW6YnBk7p9HljTOp0DIIVbeCa4WCS3Brp8U6MfM1XlMLqcBUWcCXl4dnvNGhIPKdCDToTdKm0M2MA==
  dependencies:
    cssnano-preset-advanced "^5.1.4"
    postcss "^8.3.7"
    postcss-sort-media-queries "^4.1.0"

"@docusaurus/logger@2.2.0":
  version "2.2.0"
  resolved "https://registry.npmmirror.com/@docusaurus/logger/-/logger-2.2.0.tgz#ea2f7feda7b8675485933b87f06d9c976d17423f"
  integrity sha512-DF3j1cA5y2nNsu/vk8AG7xwpZu6f5MKkPPMaaIbgXLnWGfm6+wkOeW7kNrxnM95YOhKUkJUophX69nGUnLsm0A==
  dependencies:
    chalk "^4.1.2"
    tslib "^2.4.0"

"@docusaurus/mdx-loader@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/mdx-loader/-/mdx-loader-0.0.0-4193.tgz#b43a00cd71f365a1ada793e613bab994dc105868"
  integrity sha512-EN/Q/GDMirYsxdQ+ElhqWCfKQer2MQNrmKUYc+e+4lZeAUDT9E6M7HinGoImtYQbZpN5uSjDnzTYP793DGsMjQ==
  dependencies:
    "@babel/parser" "^7.12.16"
    "@babel/traverse" "^7.12.13"
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/utils" "0.0.0-4193"
    "@mdx-js/mdx" "^1.6.21"
    "@mdx-js/react" "^1.6.21"
    chalk "^4.1.2"
    escape-html "^1.0.3"
    file-loader "^6.2.0"
    fs-extra "^10.0.0"
    github-slugger "^1.4.0"
    gray-matter "^4.0.3"
    mdast-util-to-string "^2.0.0"
    remark-emoji "^2.1.0"
    stringify-object "^3.3.0"
    unist-util-visit "^2.0.2"
    url-loader "^4.1.1"
    webpack "^5.61.0"

"@docusaurus/plugin-content-blog@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/plugin-content-blog/-/plugin-content-blog-0.0.0-4193.tgz#3868117e9cbed96ef74286ece3af93ecf73eae0f"
  integrity sha512-5GLRK3ftr1QmcBEQokn7frauAh6g9Jsc3tQUeMUR2iWZk7C96rAfVMrY3W5Jv+6gfgGzbTG+AKAUD9e3gcGHfg==
  dependencies:
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/mdx-loader" "0.0.0-4193"
    "@docusaurus/types" "0.0.0-4193"
    "@docusaurus/utils" "0.0.0-4193"
    "@docusaurus/utils-validation" "0.0.0-4193"
    chalk "^4.1.2"
    escape-string-regexp "^4.0.0"
    feed "^4.2.2"
    fs-extra "^10.0.0"
    globby "^11.0.2"
    js-yaml "^4.0.0"
    loader-utils "^2.0.0"
    lodash "^4.17.20"
    reading-time "^1.5.0"
    remark-admonitions "^1.2.1"
    tslib "^2.3.1"
    utility-types "^3.10.0"
    webpack "^5.61.0"

"@docusaurus/plugin-content-docs@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/plugin-content-docs/-/plugin-content-docs-0.0.0-4193.tgz#e22cac31dccd9dc763303bc2ec4b32c718babf6c"
  integrity sha512-UDccCvOk/vIKtbLwkWz8oI8SWrJXmKrkI1IKO038EfcJT2OAA/Gy96jar659Z2c1bqS9QurJ5M2RHA3JBS6xrg==
  dependencies:
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/mdx-loader" "0.0.0-4193"
    "@docusaurus/types" "0.0.0-4193"
    "@docusaurus/utils" "0.0.0-4193"
    "@docusaurus/utils-validation" "0.0.0-4193"
    chalk "^4.1.2"
    combine-promises "^1.1.0"
    escape-string-regexp "^4.0.0"
    fs-extra "^10.0.0"
    globby "^11.0.2"
    import-fresh "^3.2.2"
    js-yaml "^4.0.0"
    loader-utils "^2.0.0"
    lodash "^4.17.20"
    remark-admonitions "^1.2.1"
    shelljs "^0.8.4"
    tslib "^2.3.1"
    utility-types "^3.10.0"
    webpack "^5.61.0"

"@docusaurus/plugin-content-pages@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/plugin-content-pages/-/plugin-content-pages-0.0.0-4193.tgz#84fdbb23e49f974ed2bbd6b2d88acbc77f305daa"
  integrity sha512-E/vP3vGGEWtswFbUco+5elM5O/vch6vB1Lq5Zwq6ybtumalF1kXa67ZN8dlMspI4nhAPv45ZTZPT8UlRLrlqaQ==
  dependencies:
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/mdx-loader" "0.0.0-4193"
    "@docusaurus/types" "0.0.0-4193"
    "@docusaurus/utils" "0.0.0-4193"
    "@docusaurus/utils-validation" "0.0.0-4193"
    globby "^11.0.2"
    lodash "^4.17.20"
    remark-admonitions "^1.2.1"
    tslib "^2.3.1"
    webpack "^5.61.0"

"@docusaurus/plugin-debug@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/plugin-debug/-/plugin-debug-0.0.0-4193.tgz#2719e82483ee3fae33641262d67d59d97efab405"
  integrity sha512-3+rkYliCSVKNaRR/AXatbk4xpvIax7VtEtjGBTz7T6lxo8CujqOcw+j8R2HxlQSC0PgmkKnTLMDP1umZuqnIHg==
  dependencies:
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/types" "0.0.0-4193"
    "@docusaurus/utils" "0.0.0-4193"
    fs-extra "^10.0.0"
    react-json-view "^1.21.3"
    tslib "^2.3.1"

"@docusaurus/plugin-google-analytics@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/plugin-google-analytics/-/plugin-google-analytics-0.0.0-4193.tgz#feb41af7f18b400c483331fd239bb0a677358853"
  integrity sha512-wWZbr3nSFh7hEWTCmef3eih5S1s4z5+jJTCCZsq+gkHK4b9V9u81BvESB4N7T6dxt9vNEKIoYEb58iuYzUkLbw==
  dependencies:
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/utils-validation" "0.0.0-4193"

"@docusaurus/plugin-google-gtag@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/plugin-google-gtag/-/plugin-google-gtag-0.0.0-4193.tgz#8a1ba67649a30cdae512c5daae723b50a8247d21"
  integrity sha512-k7JYw7PvfarFJLDUcSOSzb3MTOL5/yi6ZIs3mTBpAaC7U+MTGVLVejVuoMKAprbtAg2RUZq5unGnBoji7xaDyQ==
  dependencies:
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/utils-validation" "0.0.0-4193"

"@docusaurus/plugin-sitemap@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/plugin-sitemap/-/plugin-sitemap-0.0.0-4193.tgz#9e2a806b2263fa40e90fa61439738709232b0942"
  integrity sha512-819ln3gj/ozT/BioQl2OrOcRvj5hvxta7h0m7TW/UbAZVx6X9QNAN9TZd49dyuTF/7y3JswU/7BxbeeOT6c/4Q==
  dependencies:
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/types" "0.0.0-4193"
    "@docusaurus/utils" "0.0.0-4193"
    "@docusaurus/utils-common" "0.0.0-4193"
    "@docusaurus/utils-validation" "0.0.0-4193"
    fs-extra "^10.0.0"
    sitemap "^7.0.0"
    tslib "^2.3.1"

"@docusaurus/preset-classic@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/preset-classic/-/preset-classic-0.0.0-4193.tgz#ebd5a074fe3fff7e5bb2f42d7edf580941500849"
  integrity sha512-R4hGzXQvCXVeH6+AbgnXBNoNagZ9Wc3WikS/MUAuu5F1vY44U2nFZo6rCDeJgupAGdqjIicA10acSUVTMslbXw==
  dependencies:
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/plugin-content-blog" "0.0.0-4193"
    "@docusaurus/plugin-content-docs" "0.0.0-4193"
    "@docusaurus/plugin-content-pages" "0.0.0-4193"
    "@docusaurus/plugin-debug" "0.0.0-4193"
    "@docusaurus/plugin-google-analytics" "0.0.0-4193"
    "@docusaurus/plugin-google-gtag" "0.0.0-4193"
    "@docusaurus/plugin-sitemap" "0.0.0-4193"
    "@docusaurus/theme-classic" "0.0.0-4193"
    "@docusaurus/theme-search-algolia" "0.0.0-4193"

"@docusaurus/react-loadable@5.5.2", "react-loadable@npm:@docusaurus/react-loadable@5.5.2":
  version "5.5.2"
  resolved "https://registry.npmmirror.com/@docusaurus/react-loadable/-/react-loadable-5.5.2.tgz#81aae0db81ecafbdaee3651f12804580868fa6ce"
  integrity sha512-A3dYjdBGuy0IGT+wyLIGIKLRE+sAk1iNk0f1HjNDysO7u8lhL4N3VEm+FAubmJbAztn94F7MxBTPmnixbiyFdQ==
  dependencies:
    "@types/react" "*"
    prop-types "^15.6.2"

"@docusaurus/theme-classic@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/theme-classic/-/theme-classic-0.0.0-4193.tgz#416cf10789cc9e5ccf340287eaadcffe538b16d5"
  integrity sha512-jPu5EkknsnqAyFNV5AYtM9+GOfZ3l3rVJYiGRNy/v/VvmBTqoWUVXm8Xylf79yMFEOjlGgFObfR58IPThZvvXw==
  dependencies:
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/plugin-content-blog" "0.0.0-4193"
    "@docusaurus/plugin-content-docs" "0.0.0-4193"
    "@docusaurus/plugin-content-pages" "0.0.0-4193"
    "@docusaurus/theme-common" "0.0.0-4193"
    "@docusaurus/types" "0.0.0-4193"
    "@docusaurus/utils" "0.0.0-4193"
    "@docusaurus/utils-validation" "0.0.0-4193"
    "@mdx-js/mdx" "^1.6.21"
    "@mdx-js/react" "^1.6.21"
    chalk "^4.1.2"
    clsx "^1.1.1"
    copy-text-to-clipboard "^3.0.1"
    fs-extra "^10.0.0"
    globby "^11.0.2"
    infima "0.2.0-alpha.34"
    lodash "^4.17.20"
    postcss "^8.3.7"
    prism-react-renderer "^1.2.1"
    prismjs "^1.23.0"
    prop-types "^15.7.2"
    react-router-dom "^5.2.0"
    rtlcss "^3.3.0"

"@docusaurus/theme-common@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/theme-common/-/theme-common-0.0.0-4193.tgz#73f6cfa73c868cf03b6cb5d15084bb05616034b5"
  integrity sha512-6yJEVlKrm9KIgMo1pmsAA5EL7FcrpeMPfkwhChAH0W5s6i4aQENrefQcEXBBBIv1KbNx4uNUG779plvnoSfNWA==
  dependencies:
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/plugin-content-blog" "0.0.0-4193"
    "@docusaurus/plugin-content-docs" "0.0.0-4193"
    "@docusaurus/plugin-content-pages" "0.0.0-4193"
    "@docusaurus/types" "0.0.0-4193"
    clsx "^1.1.1"
    fs-extra "^10.0.0"
    parse-numeric-range "^1.3.0"
    tslib "^2.3.1"
    utility-types "^3.10.0"

"@docusaurus/theme-search-algolia@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/theme-search-algolia/-/theme-search-algolia-0.0.0-4193.tgz#35bb8940c33d4d3c3dcaff7ea2f16344289abf81"
  integrity sha512-we2Z7nhZy5bgoYqF8ZXJO2jt8rBsqnDgXoRPkzoaacQww3CO3+Ez9Q+Dcpxy7lunNY3fShv+9SC13K9yClCUEQ==
  dependencies:
    "@docsearch/react" "^3.0.0-alpha.39"
    "@docusaurus/core" "0.0.0-4193"
    "@docusaurus/theme-common" "0.0.0-4193"
    "@docusaurus/utils" "0.0.0-4193"
    "@docusaurus/utils-validation" "0.0.0-4193"
    algoliasearch "^4.10.5"
    algoliasearch-helper "^3.5.5"
    clsx "^1.1.1"
    eta "^1.12.3"
    lodash "^4.17.20"

"@docusaurus/types@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/types/-/types-0.0.0-4193.tgz#6f1b9430ff27b40cb32892074934491363e6b8c5"
  integrity sha512-2y+D3yYzEbBAmK74Me4g3pVe1sSRXZDDyKzf/Ojb729F7lYx9dvUTj0I/YlNDcPg5FUKCorfnV+3RfsyDb8lKA==
  dependencies:
    commander "^5.1.0"
    joi "^17.4.2"
    querystring "0.2.0"
    utility-types "^3.10.0"
    webpack "^5.61.0"
    webpack-merge "^5.8.0"

"@docusaurus/utils-common@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/utils-common/-/utils-common-0.0.0-4193.tgz#2631c645e5b6e3b8fb799d80ed032f6a8e2842d6"
  integrity sha512-31kHFbhubA8cKZIjztNBsIUBbD+gHInHfVuvzBdcOnZgFfTdL9sUrROmjGnAAopAoJ/YyO5bsu5GGnrn/hexDA==
  dependencies:
    "@docusaurus/types" "0.0.0-4193"
    tslib "^2.3.1"

"@docusaurus/utils-validation@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/utils-validation/-/utils-validation-0.0.0-4193.tgz#96f7af723a971411635c5c51a38c391bd9699523"
  integrity sha512-ppVmx3KOHKyxta51O76VAVLttR46ItigEVpbaw5nfxs8muGKXmddWQ2lA78ga1zTDzwLT/7d18kngn46Qva+dw==
  dependencies:
    "@docusaurus/utils" "0.0.0-4193"
    chalk "^4.1.2"
    joi "^17.4.2"
    tslib "^2.3.1"

"@docusaurus/utils-validation@^2.0.0-beta.4":
  version "2.2.0"
  resolved "https://registry.npmmirror.com/@docusaurus/utils-validation/-/utils-validation-2.2.0.tgz#04d4d103137ad0145883971d3aa497f4a1315f25"
  integrity sha512-I1hcsG3yoCkasOL5qQAYAfnmVoLei7apugT6m4crQjmDGxq+UkiRrq55UqmDDyZlac/6ax/JC0p+usZ6W4nVyg==
  dependencies:
    "@docusaurus/logger" "2.2.0"
    "@docusaurus/utils" "2.2.0"
    joi "^17.6.0"
    js-yaml "^4.1.0"
    tslib "^2.4.0"

"@docusaurus/utils@0.0.0-4193":
  version "0.0.0-4193"
  resolved "https://registry.npmmirror.com/@docusaurus/utils/-/utils-0.0.0-4193.tgz#cf4e7367cf926bf2ac8e3039088d60a49537e4e3"
  integrity sha512-c+1c735JzKqE2pRAkHnKyz81a6RE5HcVL3J1tpw9ACKjMyDq1qv3XeYa/ZKv/09qi/FI2QiZ32eiYHMXNZE1Sw==
  dependencies:
    "@docusaurus/types" "0.0.0-4193"
    "@mdx-js/runtime" "^1.6.22"
    "@types/github-slugger" "^1.3.0"
    chalk "^4.1.2"
    escape-string-regexp "^4.0.0"
    fs-extra "^10.0.0"
    globby "^11.0.4"
    gray-matter "^4.0.3"
    lodash "^4.17.20"
    micromatch "^4.0.4"
    remark-mdx-remove-exports "^1.6.22"
    remark-mdx-remove-imports "^1.6.22"
    resolve-pathname "^3.0.0"
    tslib "^2.3.1"

"@docusaurus/utils@2.2.0", "@docusaurus/utils@^2.0.0-beta.4":
  version "2.2.0"
  resolved "https://registry.npmmirror.com/@docusaurus/utils/-/utils-2.2.0.tgz#3d6f9b7a69168d5c92d371bf21c556a4f50d1da6"
  integrity sha512-oNk3cjvx7Tt1Lgh/aeZAmFpGV2pDr5nHKrBVx6hTkzGhrnMuQqLt6UPlQjdYQ3QHXwyF/ZtZMO1D5Pfi0lu7SA==
  dependencies:
    "@docusaurus/logger" "2.2.0"
    "@svgr/webpack" "^6.2.1"
    file-loader "^6.2.0"
    fs-extra "^10.1.0"
    github-slugger "^1.4.0"
    globby "^11.1.0"
    gray-matter "^4.0.3"
    js-yaml "^4.1.0"
    lodash "^4.17.21"
    micromatch "^4.0.5"
    resolve-pathname "^3.0.0"
    shelljs "^0.8.5"
    tslib "^2.4.0"
    url-loader "^4.1.1"
    webpack "^5.73.0"

"@easyops-cn/autocomplete.js@^0.38.1":
  version "0.38.1"
  resolved "https://registry.npmmirror.com/@easyops-cn/autocomplete.js/-/autocomplete.js-0.38.1.tgz#46dff5795a9a032fa9b9250fdf63ca6c61c07629"
  integrity sha512-drg76jS6syilOUmVNkyo1c7ZEBPcPuK+aJA7AksM5ZIIbV57DMHCywiCr+uHyv8BE5jUTU98j/H7gVrkHrWW3Q==
  dependencies:
    cssesc "^3.0.0"
    immediate "^3.2.3"

"@easyops-cn/docusaurus-search-local@^0.21.1":
  version "0.21.4"
  resolved "https://registry.npmmirror.com/@easyops-cn/docusaurus-search-local/-/docusaurus-search-local-0.21.4.tgz#d5df409e5f80503bcd62def991dbd230e58ee3c5"
  integrity sha512-sUYxRKLfN/rInn1awf3Z6M5lefk9gSsrQp/6nKUTgaJI/NUmvZY8Hk3nRk0BPIHK8jjjzm+gWOhz8O0SBq8ihw==
  dependencies:
    "@docusaurus/utils" "^2.0.0-beta.4"
    "@docusaurus/utils-validation" "^2.0.0-beta.4"
    "@easyops-cn/autocomplete.js" "^0.38.1"
    cheerio "^1.0.0-rc.3"
    clsx "^1.1.1"
    debug "^4.2.0"
    fs-extra "^9.0.1"
    klaw-sync "^6.0.0"
    lunr "^2.3.9"
    lunr-languages "^1.4.0"
    mark.js "^8.11.1"
    tslib "^2.2.0"

"@hapi/hoek@^9.0.0":
  version "9.3.0"
  resolved "https://registry.npmmirror.com/@hapi/hoek/-/hoek-9.3.0.tgz#8368869dcb735be2e7f5cb7647de78e167a251fb"
  integrity sha512-/c6rf4UJlmHlC9b5BaNvzAcFv7HZ2QHaV0D4/HNlBdvFnvQq8RI4kYdhyPCl7Xj+oWvTWQ8ujhqS53LIgAe6KQ==

"@hapi/topo@^5.0.0":
  version "5.1.0"
  resolved "https://registry.npmmirror.com/@hapi/topo/-/topo-5.1.0.tgz#dc448e332c6c6e37a4dc02fd84ba8d44b9afb012"
  integrity sha512-foQZKJig7Ob0BMAYBfcJk8d77QtOe7Wo4ox7ff1lQYoNNAb6jwcY1ncdoy2e9wQZzvNy7ODZCYJkK8kzmcAnAg==
  dependencies:
    "@hapi/hoek" "^9.0.0"

"@jridgewell/gen-mapping@^0.1.0":
  version "0.1.1"
  resolved "https://registry.npmmirror.com/@jridgewell/gen-mapping/-/gen-mapping-0.1.1.tgz#e5d2e450306a9491e3bd77e323e38d7aff315996"
  integrity sha512-sQXCasFk+U8lWYEe66WxRDOE9PjVz4vSM51fTu3Hw+ClTpUSQb718772vH3pyS5pShp6lvQM7SxgIDXXXmOX7w==
  dependencies:
    "@jridgewell/set-array" "^1.0.0"
    "@jridgewell/sourcemap-codec" "^1.4.10"

"@jridgewell/gen-mapping@^0.3.0", "@jridgewell/gen-mapping@^0.3.2":
  version "0.3.2"
  resolved "https://registry.npmmirror.com/@jridgewell/gen-mapping/-/gen-mapping-0.3.2.tgz#c1aedc61e853f2bb9f5dfe6d4442d3b565b253b9"
  integrity sha512-mh65xKQAzI6iBcFzwv28KVWSmCkdRBWoOh+bYQGW3+6OZvbbN3TqMGo5hqYxQniRcH9F2VZIoJCm4pa3BPDK/A==
  dependencies:
    "@jridgewell/set-array" "^1.0.1"
    "@jridgewell/sourcemap-codec" "^1.4.10"
    "@jridgewell/trace-mapping" "^0.3.9"

"@jridgewell/resolve-uri@3.1.0":
  version "3.1.0"
  resolved "https://registry.npmmirror.com/@jridgewell/resolve-uri/-/resolve-uri-3.1.0.tgz#2203b118c157721addfe69d47b70465463066d78"
  integrity sha512-F2msla3tad+Mfht5cJq7LSXcdudKTWCVYUgw6pLFOOHSTtZlj6SWNYAp+AhuqLmWdBO2X5hPrLcu8cVP8fy28w==

"@jridgewell/resolve-uri@^3.1.0":
  version "3.1.1"
  resolved "https://registry.yarnpkg.com/@jridgewell/resolve-uri/-/resolve-uri-3.1.1.tgz#c08679063f279615a3326583ba3a90d1d82cc721"
  integrity sha512-dSYZh7HhCDtCKm4QakX0xFpsRDqjjtZf/kjI/v3T3Nwt5r8/qz/M19F9ySyOqU94SXBmeG9ttTul+YnR4LOxFA==

"@jridgewell/set-array@^1.0.0", "@jridgewell/set-array@^1.0.1":
  version "1.1.2"
  resolved "https://registry.npmmirror.com/@jridgewell/set-array/-/set-array-1.1.2.tgz#7c6cf998d6d20b914c0a55a91ae928ff25965e72"
  integrity sha512-xnkseuNADM0gt2bs+BvhO0p78Mk762YnZdsuzFV018NoG1Sj1SCQvpSqa7XUaTam5vAGasABV9qXASMKnFMwMw==

"@jridgewell/source-map@^0.3.2":
  version "0.3.2"
  resolved "https://registry.npmmirror.com/@jridgewell/source-map/-/source-map-0.3.2.tgz#f45351aaed4527a298512ec72f81040c998580fb"
  integrity sha512-m7O9o2uR8k2ObDysZYzdfhb08VuEml5oWGiosa1VdaPZ/A6QyPkAJuwN0Q1lhULOf6B7MtQmHENS743hWtCrgw==
  dependencies:
    "@jridgewell/gen-mapping" "^0.3.0"
    "@jridgewell/trace-mapping" "^0.3.9"

"@jridgewell/sourcemap-codec@1.4.14", "@jridgewell/sourcemap-codec@^1.4.10":
  version "1.4.14"
  resolved "https://registry.npmmirror.com/@jridgewell/sourcemap-codec/-/sourcemap-codec-1.4.14.tgz#add4c98d341472a289190b424efbdb096991bb24"
  integrity sha512-XPSJHWmi394fuUuzDnGz1wiKqWfo1yXecHQMRf2l6hztTO+nPru658AyDngaBe7isIxEkRsPR3FZh+s7iVa4Uw==

"@jridgewell/sourcemap-codec@^1.4.14":
  version "1.4.15"
  resolved "https://registry.yarnpkg.com/@jridgewell/sourcemap-codec/-/sourcemap-codec-1.4.15.tgz#d7c6e6755c78567a951e04ab52ef0fd26de59f32"
  integrity sha512-eF2rxCRulEKXHTRiDrDy6erMYWqNw4LPdQ8UQA4huuxaQsVeRPFl2oM8oDGxMFhJUWZf9McpLtJasDDZb/Bpeg==

"@jridgewell/trace-mapping@^0.3.14", "@jridgewell/trace-mapping@^0.3.9":
  version "0.3.17"
  resolved "https://registry.npmmirror.com/@jridgewell/trace-mapping/-/trace-mapping-0.3.17.tgz#793041277af9073b0951a7fe0f0d8c4c98c36985"
  integrity sha512-MCNzAp77qzKca9+W/+I0+sEpaUnZoeasnghNeVc41VZCEKaCH73Vq3BZZ/SzWIgrqE4H4ceI+p+b6C0mHf9T4g==
  dependencies:
    "@jridgewell/resolve-uri" "3.1.0"
    "@jridgewell/sourcemap-codec" "1.4.14"

"@jridgewell/trace-mapping@^0.3.17":
  version "0.3.20"
  resolved "https://registry.yarnpkg.com/@jridgewell/trace-mapping/-/trace-mapping-0.3.20.tgz#72e45707cf240fa6b081d0366f8265b0cd10197f"
  integrity sha512-R8LcPeWZol2zR8mmH3JeKQ6QRCFb7XgUhV9ZlGhHLGyg4wpPiPZNQOOWhFZhxKw8u//yTbNGI42Bx/3paXEQ+Q==
  dependencies:
    "@jridgewell/resolve-uri" "^3.1.0"
    "@jridgewell/sourcemap-codec" "^1.4.14"

"@leichtgewicht/ip-codec@^2.0.1":
  version "2.0.4"
  resolved "https://registry.npmmirror.com/@leichtgewicht/ip-codec/-/ip-codec-2.0.4.tgz#b2ac626d6cb9c8718ab459166d4bb405b8ffa78b"
  integrity sha512-Hcv+nVC0kZnQ3tD9GVu5xSMR4VVYOteQIr/hwFPVEvPdlXqgGEuRjiheChHgdM+JyqdgNcmzZOX/tnl0JOiI7A==

"@mdx-js/mdx@1.6.22", "@mdx-js/mdx@^1.6.21":
  version "1.6.22"
  resolved "https://registry.npmmirror.com/@mdx-js/mdx/-/mdx-1.6.22.tgz#8a723157bf90e78f17dc0f27995398e6c731f1ba"
  integrity sha512-AMxuLxPz2j5/6TpF/XSdKpQP1NlG0z11dFOlq+2IP/lSgl11GY8ji6S/rgsViN/L0BDvHvUMruRb7ub+24LUYA==
  dependencies:
    "@babel/core" "7.12.9"
    "@babel/plugin-syntax-jsx" "7.12.1"
    "@babel/plugin-syntax-object-rest-spread" "7.8.3"
    "@mdx-js/util" "1.6.22"
    babel-plugin-apply-mdx-type-prop "1.6.22"
    babel-plugin-extract-import-names "1.6.22"
    camelcase-css "2.0.1"
    detab "2.0.4"
    hast-util-raw "6.0.1"
    lodash.uniq "4.5.0"
    mdast-util-to-hast "10.0.1"
    remark-footnotes "2.0.0"
    remark-mdx "1.6.22"
    remark-parse "8.0.3"
    remark-squeeze-paragraphs "4.0.0"
    style-to-object "0.3.0"
    unified "9.2.0"
    unist-builder "2.0.3"
    unist-util-visit "2.0.3"

"@mdx-js/react@1.6.22", "@mdx-js/react@^1.6.21":
  version "1.6.22"
  resolved "https://registry.npmmirror.com/@mdx-js/react/-/react-1.6.22.tgz#ae09b4744fddc74714ee9f9d6f17a66e77c43573"
  integrity sha512-TDoPum4SHdfPiGSAaRBw7ECyI8VaHpK8GJugbJIJuqyh6kzw9ZLJZW3HGL3NNrJGxcAixUvqROm+YuQOo5eXtg==

"@mdx-js/runtime@^1.6.22":
  version "1.6.22"
  resolved "https://registry.npmmirror.com/@mdx-js/runtime/-/runtime-1.6.22.tgz#3edd388bf68a519ffa1aaf9c446b548165102345"
  integrity sha512-p17spaO2+55VLCuxXA3LVHC4phRx60NR2XMdZ+qgVU1lKvEX4y88dmFNOzGDCPLJ03IZyKrJ/rPWWRiBrd9JrQ==
  dependencies:
    "@mdx-js/mdx" "1.6.22"
    "@mdx-js/react" "1.6.22"
    buble-jsx-only "^0.19.8"

"@mdx-js/util@1.6.22":
  version "1.6.22"
  resolved "https://registry.npmmirror.com/@mdx-js/util/-/util-1.6.22.tgz#219dfd89ae5b97a8801f015323ffa4b62f45718b"
  integrity sha512-H1rQc1ZOHANWBvPcW+JpGwr+juXSxM8Q8YCkm3GhZd8REu1fHR3z99CErO1p9pkcfcxZnMdIZdIsXkOHY0NilA==

"@nodelib/fs.scandir@2.1.5":
  version "2.1.5"
  resolved "https://registry.npmmirror.com/@nodelib/fs.scandir/-/fs.scandir-2.1.5.tgz#7619c2eb21b25483f6d167548b4cfd5a7488c3d5"
  integrity sha512-vq24Bq3ym5HEQm2NKCr3yXDwjc7vTsEThRDnkp2DK9p1uqLR+DHurm/NOTo0KG7HYHU7eppKZj3MyqYuMBf62g==
  dependencies:
    "@nodelib/fs.stat" "2.0.5"
    run-parallel "^1.1.9"

"@nodelib/fs.stat@2.0.5", "@nodelib/fs.stat@^2.0.2":
  version "2.0.5"
  resolved "https://registry.npmmirror.com/@nodelib/fs.stat/-/fs.stat-2.0.5.tgz#5bd262af94e9d25bd1e71b05deed44876a222e8b"
  integrity sha512-RkhPPp2zrqDAQA/2jNhnztcPAlv64XdhIp7a7454A5ovI7Bukxgt7MX7udwAu3zg1DcpPU0rz3VV1SeaqvY4+A==

"@nodelib/fs.walk@^1.2.3":
  version "1.2.8"
  resolved "https://registry.npmmirror.com/@nodelib/fs.walk/-/fs.walk-1.2.8.tgz#e95737e8bb6746ddedf69c556953494f196fe69a"
  integrity sha512-oGB+UxlgWcgQkgwo8GcEGwemoTFt3FIO9ababBmaGwXIoBKZ+GTy0pP185beGg7Llih/NSHSV2XAs1lnznocSg==
  dependencies:
    "@nodelib/fs.scandir" "2.1.5"
    fastq "^1.6.0"

"@polka/url@^1.0.0-next.20":
  version "1.0.0-next.21"
  resolved "https://registry.npmmirror.com/@polka/url/-/url-1.0.0-next.21.tgz#5de5a2385a35309427f6011992b544514d559aa1"
  integrity sha512-a5Sab1C4/icpTZVzZc5Ghpz88yQtGOyNqYXcZgOssB2uuAr+wF/MvN6bgtW32q7HHrvBki+BsZ0OuNv6EV3K9g==

"@sideway/address@^4.1.3":
  version "4.1.4"
  resolved "https://registry.npmmirror.com/@sideway/address/-/address-4.1.4.tgz#03dccebc6ea47fdc226f7d3d1ad512955d4783f0"
  integrity sha512-7vwq+rOHVWjyXxVlR76Agnvhy8I9rpzjosTESvmhNeXOXdZZB15Fl+TI9x1SiHZH5Jv2wTGduSxFDIaq0m3DUw==
  dependencies:
    "@hapi/hoek" "^9.0.0"

"@sideway/formula@3.0.1", "@sideway/formula@^3.0.0":
  version "3.0.1"
  resolved "https://registry.yarnpkg.com/@sideway/formula/-/formula-3.0.1.tgz#80fcbcbaf7ce031e0ef2dd29b1bfc7c3f583611f"
  integrity sha512-/poHZJJVjx3L+zVD6g9KgHfYnb443oi7wLu/XKojDviHy6HOEOA6z1Trk5aR1dGcmPenJEgb2sK2I80LeS3MIg==

"@sideway/pinpoint@^2.0.0":
  version "2.0.0"
  resolved "https://registry.npmmirror.com/@sideway/pinpoint/-/pinpoint-2.0.0.tgz#cff8ffadc372ad29fd3f78277aeb29e632cc70df"
  integrity sha512-RNiOoTPkptFtSVzQevY/yWtZwf/RxyVnPy/OcA9HBM3MlGDnBEYL5B41H0MTn0Uec8Hi+2qUtTfG2WWZBmMejQ==

"@sindresorhus/is@^4.0.0":
  version "4.6.0"
  resolved "https://registry.npmmirror.com/@sindresorhus/is/-/is-4.6.0.tgz#3c7c9c46e678feefe7a2e5bb609d3dbd665ffb3f"
  integrity sha512-t09vSN3MdfsyCHoFcTRCH/iUtG7OJ0CsjzB8cjAmKc/va/kIgeDI/TxsigdncE/4be734m0cvIYwNaV4i2XqAw==

"@slorber/static-site-generator-webpack-plugin@^4.0.0":
  version "4.0.7"
  resolved "https://registry.npmmirror.com/@slorber/static-site-generator-webpack-plugin/-/static-site-generator-webpack-plugin-4.0.7.tgz#fc1678bddefab014e2145cbe25b3ce4e1cfc36f3"
  integrity sha512-Ug7x6z5lwrz0WqdnNFOMYrDQNTPAprvHLSh6+/fmml3qUiz6l5eq+2MzLKWtn/q5K5NpSiFsZTP/fck/3vjSxA==
  dependencies:
    eval "^0.1.8"
    p-map "^4.0.0"
    webpack-sources "^3.2.2"

"@svgr/babel-plugin-add-jsx-attribute@^5.4.0":
  version "5.4.0"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-add-jsx-attribute/-/babel-plugin-add-jsx-attribute-5.4.0.tgz#81ef61947bb268eb9d50523446f9c638fb355906"
  integrity sha512-ZFf2gs/8/6B8PnSofI0inYXr2SDNTDScPXhN7k5EqD4aZ3gi6u+rbmZHVB8IM3wDyx8ntKACZbtXSm7oZGRqVg==

"@svgr/babel-plugin-add-jsx-attribute@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-add-jsx-attribute/-/babel-plugin-add-jsx-attribute-6.5.1.tgz#74a5d648bd0347bda99d82409d87b8ca80b9a1ba"
  integrity sha512-9PYGcXrAxitycIjRmZB+Q0JaN07GZIWaTBIGQzfaZv+qr1n8X1XUEJ5rZ/vx6OVD9RRYlrNnXWExQXcmZeD/BQ==

"@svgr/babel-plugin-remove-jsx-attribute@*":
  version "6.5.0"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-remove-jsx-attribute/-/babel-plugin-remove-jsx-attribute-6.5.0.tgz#652bfd4ed0a0699843585cda96faeb09d6e1306e"
  integrity sha512-8zYdkym7qNyfXpWvu4yq46k41pyNM9SOstoWhKlm+IfdCE1DdnRKeMUPsWIEO/DEkaWxJ8T9esNdG3QwQ93jBA==

"@svgr/babel-plugin-remove-jsx-attribute@^5.4.0":
  version "5.4.0"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-remove-jsx-attribute/-/babel-plugin-remove-jsx-attribute-5.4.0.tgz#6b2c770c95c874654fd5e1d5ef475b78a0a962ef"
  integrity sha512-yaS4o2PgUtwLFGTKbsiAy6D0o3ugcUhWK0Z45umJ66EPWunAz9fuFw2gJuje6wqQvQWOTJvIahUwndOXb7QCPg==

"@svgr/babel-plugin-remove-jsx-empty-expression@*":
  version "6.5.0"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-remove-jsx-empty-expression/-/babel-plugin-remove-jsx-empty-expression-6.5.0.tgz#4b78994ab7d39032c729903fc2dd5c0fa4565cb8"
  integrity sha512-NFdxMq3xA42Kb1UbzCVxplUc0iqSyM9X8kopImvFnB+uSDdzIHOdbs1op8ofAvVRtbg4oZiyRl3fTYeKcOe9Iw==

"@svgr/babel-plugin-remove-jsx-empty-expression@^5.0.1":
  version "5.0.1"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-remove-jsx-empty-expression/-/babel-plugin-remove-jsx-empty-expression-5.0.1.tgz#25621a8915ed7ad70da6cea3d0a6dbc2ea933efd"
  integrity sha512-LA72+88A11ND/yFIMzyuLRSMJ+tRKeYKeQ+mR3DcAZ5I4h5CPWN9AHyUzJbWSYp/u2u0xhmgOe0+E41+GjEueA==

"@svgr/babel-plugin-replace-jsx-attribute-value@^5.0.1":
  version "5.0.1"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-replace-jsx-attribute-value/-/babel-plugin-replace-jsx-attribute-value-5.0.1.tgz#0b221fc57f9fcd10e91fe219e2cd0dd03145a897"
  integrity sha512-PoiE6ZD2Eiy5mK+fjHqwGOS+IXX0wq/YDtNyIgOrc6ejFnxN4b13pRpiIPbtPwHEc+NT2KCjteAcq33/F1Y9KQ==

"@svgr/babel-plugin-replace-jsx-attribute-value@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-replace-jsx-attribute-value/-/babel-plugin-replace-jsx-attribute-value-6.5.1.tgz#fb9d22ea26d2bc5e0a44b763d4c46d5d3f596c60"
  integrity sha512-8DPaVVE3fd5JKuIC29dqyMB54sA6mfgki2H2+swh+zNJoynC8pMPzOkidqHOSc6Wj032fhl8Z0TVn1GiPpAiJg==

"@svgr/babel-plugin-svg-dynamic-title@^5.4.0":
  version "5.4.0"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-svg-dynamic-title/-/babel-plugin-svg-dynamic-title-5.4.0.tgz#139b546dd0c3186b6e5db4fefc26cb0baea729d7"
  integrity sha512-zSOZH8PdZOpuG1ZVx/cLVePB2ibo3WPpqo7gFIjLV9a0QsuQAzJiwwqmuEdTaW2pegyBE17Uu15mOgOcgabQZg==

"@svgr/babel-plugin-svg-dynamic-title@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-svg-dynamic-title/-/babel-plugin-svg-dynamic-title-6.5.1.tgz#01b2024a2b53ffaa5efceaa0bf3e1d5a4c520ce4"
  integrity sha512-FwOEi0Il72iAzlkaHrlemVurgSQRDFbk0OC8dSvD5fSBPHltNh7JtLsxmZUhjYBZo2PpcU/RJvvi6Q0l7O7ogw==

"@svgr/babel-plugin-svg-em-dimensions@^5.4.0":
  version "5.4.0"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-svg-em-dimensions/-/babel-plugin-svg-em-dimensions-5.4.0.tgz#6543f69526632a133ce5cabab965deeaea2234a0"
  integrity sha512-cPzDbDA5oT/sPXDCUYoVXEmm3VIoAWAPT6mSPTJNbQaBNUuEKVKyGH93oDY4e42PYHRW67N5alJx/eEol20abw==

"@svgr/babel-plugin-svg-em-dimensions@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-svg-em-dimensions/-/babel-plugin-svg-em-dimensions-6.5.1.tgz#dd3fa9f5b24eb4f93bcf121c3d40ff5facecb217"
  integrity sha512-gWGsiwjb4tw+ITOJ86ndY/DZZ6cuXMNE/SjcDRg+HLuCmwpcjOktwRF9WgAiycTqJD/QXqL2f8IzE2Rzh7aVXA==

"@svgr/babel-plugin-transform-react-native-svg@^5.4.0":
  version "5.4.0"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-transform-react-native-svg/-/babel-plugin-transform-react-native-svg-5.4.0.tgz#00bf9a7a73f1cad3948cdab1f8dfb774750f8c80"
  integrity sha512-3eYP/SaopZ41GHwXma7Rmxcv9uRslRDTY1estspeB1w1ueZWd/tPlMfEOoccYpEMZU3jD4OU7YitnXcF5hLW2Q==

"@svgr/babel-plugin-transform-react-native-svg@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-transform-react-native-svg/-/babel-plugin-transform-react-native-svg-6.5.1.tgz#1d8e945a03df65b601551097d8f5e34351d3d305"
  integrity sha512-2jT3nTayyYP7kI6aGutkyfJ7UMGtuguD72OjeGLwVNyfPRBD8zQthlvL+fAbAKk5n9ZNcvFkp/b1lZ7VsYqVJg==

"@svgr/babel-plugin-transform-svg-component@^5.5.0":
  version "5.5.0"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-transform-svg-component/-/babel-plugin-transform-svg-component-5.5.0.tgz#583a5e2a193e214da2f3afeb0b9e8d3250126b4a"
  integrity sha512-q4jSH1UUvbrsOtlo/tKcgSeiCHRSBdXoIoqX1pgcKK/aU3JD27wmMKwGtpB8qRYUYoyXvfGxUVKchLuR5pB3rQ==

"@svgr/babel-plugin-transform-svg-component@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/babel-plugin-transform-svg-component/-/babel-plugin-transform-svg-component-6.5.1.tgz#48620b9e590e25ff95a80f811544218d27f8a250"
  integrity sha512-a1p6LF5Jt33O3rZoVRBqdxL350oge54iZWHNI6LJB5tQ7EelvD/Mb1mfBiZNAan0dt4i3VArkFRjA4iObuNykQ==

"@svgr/babel-preset@^5.5.0":
  version "5.5.0"
  resolved "https://registry.npmmirror.com/@svgr/babel-preset/-/babel-preset-5.5.0.tgz#8af54f3e0a8add7b1e2b0fcd5a882c55393df327"
  integrity sha512-4FiXBjvQ+z2j7yASeGPEi8VD/5rrGQk4Xrq3EdJmoZgz/tpqChpo5hgXDvmEauwtvOc52q8ghhZK4Oy7qph4ig==
  dependencies:
    "@svgr/babel-plugin-add-jsx-attribute" "^5.4.0"
    "@svgr/babel-plugin-remove-jsx-attribute" "^5.4.0"
    "@svgr/babel-plugin-remove-jsx-empty-expression" "^5.0.1"
    "@svgr/babel-plugin-replace-jsx-attribute-value" "^5.0.1"
    "@svgr/babel-plugin-svg-dynamic-title" "^5.4.0"
    "@svgr/babel-plugin-svg-em-dimensions" "^5.4.0"
    "@svgr/babel-plugin-transform-react-native-svg" "^5.4.0"
    "@svgr/babel-plugin-transform-svg-component" "^5.5.0"

"@svgr/babel-preset@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/babel-preset/-/babel-preset-6.5.1.tgz#b90de7979c8843c5c580c7e2ec71f024b49eb828"
  integrity sha512-6127fvO/FF2oi5EzSQOAjo1LE3OtNVh11R+/8FXa+mHx1ptAaS4cknIjnUA7e6j6fwGGJ17NzaTJFUwOV2zwCw==
  dependencies:
    "@svgr/babel-plugin-add-jsx-attribute" "^6.5.1"
    "@svgr/babel-plugin-remove-jsx-attribute" "*"
    "@svgr/babel-plugin-remove-jsx-empty-expression" "*"
    "@svgr/babel-plugin-replace-jsx-attribute-value" "^6.5.1"
    "@svgr/babel-plugin-svg-dynamic-title" "^6.5.1"
    "@svgr/babel-plugin-svg-em-dimensions" "^6.5.1"
    "@svgr/babel-plugin-transform-react-native-svg" "^6.5.1"
    "@svgr/babel-plugin-transform-svg-component" "^6.5.1"

"@svgr/core@^5.5.0":
  version "5.5.0"
  resolved "https://registry.npmmirror.com/@svgr/core/-/core-5.5.0.tgz#82e826b8715d71083120fe8f2492ec7d7874a579"
  integrity sha512-q52VOcsJPvV3jO1wkPtzTuKlvX7Y3xIcWRpCMtBF3MrteZJtBfQw/+u0B1BHy5ColpQc1/YVTrPEtSYIMNZlrQ==
  dependencies:
    "@svgr/plugin-jsx" "^5.5.0"
    camelcase "^6.2.0"
    cosmiconfig "^7.0.0"

"@svgr/core@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/core/-/core-6.5.1.tgz#d3e8aa9dbe3fbd747f9ee4282c1c77a27410488a"
  integrity sha512-/xdLSWxK5QkqG524ONSjvg3V/FkNyCv538OIBdQqPNaAta3AsXj/Bd2FbvR87yMbXO2hFSWiAe/Q6IkVPDw+mw==
  dependencies:
    "@babel/core" "^7.19.6"
    "@svgr/babel-preset" "^6.5.1"
    "@svgr/plugin-jsx" "^6.5.1"
    camelcase "^6.2.0"
    cosmiconfig "^7.0.1"

"@svgr/hast-util-to-babel-ast@^5.5.0":
  version "5.5.0"
  resolved "https://registry.npmmirror.com/@svgr/hast-util-to-babel-ast/-/hast-util-to-babel-ast-5.5.0.tgz#5ee52a9c2533f73e63f8f22b779f93cd432a5461"
  integrity sha512-cAaR/CAiZRB8GP32N+1jocovUtvlj0+e65TB50/6Lcime+EA49m/8l+P2ko+XPJ4dw3xaPS3jOL4F2X4KWxoeQ==
  dependencies:
    "@babel/types" "^7.12.6"

"@svgr/hast-util-to-babel-ast@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/hast-util-to-babel-ast/-/hast-util-to-babel-ast-6.5.1.tgz#81800bd09b5bcdb968bf6ee7c863d2288fdb80d2"
  integrity sha512-1hnUxxjd83EAxbL4a0JDJoD3Dao3hmjvyvyEV8PzWmLK3B9m9NPlW7GKjFyoWE8nM7HnXzPcmmSyOW8yOddSXw==
  dependencies:
    "@babel/types" "^7.20.0"
    entities "^4.4.0"

"@svgr/plugin-jsx@^5.5.0":
  version "5.5.0"
  resolved "https://registry.npmmirror.com/@svgr/plugin-jsx/-/plugin-jsx-5.5.0.tgz#1aa8cd798a1db7173ac043466d7b52236b369000"
  integrity sha512-V/wVh33j12hGh05IDg8GpIUXbjAPnTdPTKuP4VNLggnwaHMPNQNae2pRnyTAILWCQdz5GyMqtO488g7CKM8CBA==
  dependencies:
    "@babel/core" "^7.12.3"
    "@svgr/babel-preset" "^5.5.0"
    "@svgr/hast-util-to-babel-ast" "^5.5.0"
    svg-parser "^2.0.2"

"@svgr/plugin-jsx@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/plugin-jsx/-/plugin-jsx-6.5.1.tgz#0e30d1878e771ca753c94e69581c7971542a7072"
  integrity sha512-+UdQxI3jgtSjCykNSlEMuy1jSRQlGC7pqBCPvkG/2dATdWo082zHTTK3uhnAju2/6XpE6B5mZ3z4Z8Ns01S8Gw==
  dependencies:
    "@babel/core" "^7.19.6"
    "@svgr/babel-preset" "^6.5.1"
    "@svgr/hast-util-to-babel-ast" "^6.5.1"
    svg-parser "^2.0.4"

"@svgr/plugin-svgo@^5.5.0":
  version "5.5.0"
  resolved "https://registry.npmmirror.com/@svgr/plugin-svgo/-/plugin-svgo-5.5.0.tgz#02da55d85320549324e201c7b2e53bf431fcc246"
  integrity sha512-r5swKk46GuQl4RrVejVwpeeJaydoxkdwkM1mBKOgJLBUJPGaLci6ylg/IjhrRsREKDkr4kbMWdgOtbXEh0fyLQ==
  dependencies:
    cosmiconfig "^7.0.0"
    deepmerge "^4.2.2"
    svgo "^1.2.2"

"@svgr/plugin-svgo@^6.5.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/plugin-svgo/-/plugin-svgo-6.5.1.tgz#0f91910e988fc0b842f88e0960c2862e022abe84"
  integrity sha512-omvZKf8ixP9z6GWgwbtmP9qQMPX4ODXi+wzbVZgomNFsUIlHA1sf4fThdwTWSsZGgvGAG6yE+b/F5gWUkcZ/iQ==
  dependencies:
    cosmiconfig "^7.0.1"
    deepmerge "^4.2.2"
    svgo "^2.8.0"

"@svgr/webpack@^5.5.0":
  version "5.5.0"
  resolved "https://registry.npmmirror.com/@svgr/webpack/-/webpack-5.5.0.tgz#aae858ee579f5fa8ce6c3166ef56c6a1b381b640"
  integrity sha512-DOBOK255wfQxguUta2INKkzPj6AIS6iafZYiYmHn6W3pHlycSRRlvWKCfLDG10fXfLWqE3DJHgRUOyJYmARa7g==
  dependencies:
    "@babel/core" "^7.12.3"
    "@babel/plugin-transform-react-constant-elements" "^7.12.1"
    "@babel/preset-env" "^7.12.1"
    "@babel/preset-react" "^7.12.5"
    "@svgr/core" "^5.5.0"
    "@svgr/plugin-jsx" "^5.5.0"
    "@svgr/plugin-svgo" "^5.5.0"
    loader-utils "^2.0.0"

"@svgr/webpack@^6.2.1":
  version "6.5.1"
  resolved "https://registry.npmmirror.com/@svgr/webpack/-/webpack-6.5.1.tgz#ecf027814fc1cb2decc29dc92f39c3cf691e40e8"
  integrity sha512-cQ/AsnBkXPkEK8cLbv4Dm7JGXq2XrumKnL1dRpJD9rIO2fTIlJI9a1uCciYG1F2aUsox/hJQyNGbt3soDxSRkA==
  dependencies:
    "@babel/core" "^7.19.6"
    "@babel/plugin-transform-react-constant-elements" "^7.18.12"
    "@babel/preset-env" "^7.19.4"
    "@babel/preset-react" "^7.18.6"
    "@babel/preset-typescript" "^7.18.6"
    "@svgr/core" "^6.5.1"
    "@svgr/plugin-jsx" "^6.5.1"
    "@svgr/plugin-svgo" "^6.5.1"

"@szmarczak/http-timer@^4.0.5":
  version "4.0.6"
  resolved "https://registry.npmmirror.com/@szmarczak/http-timer/-/http-timer-4.0.6.tgz#b4a914bb62e7c272d4e5989fe4440f812ab1d807"
  integrity sha512-4BAffykYOgO+5nzBWYwE3W90sBgLJoUPRWWcL8wlyiM8IB8ipJz3UMJ9KXQd1RKQXpKp8Tutn80HZtWsu2u76w==
  dependencies:
    defer-to-connect "^2.0.0"

"@trysound/sax@0.2.0":
  version "0.2.0"
  resolved "https://registry.npmmirror.com/@trysound/sax/-/sax-0.2.0.tgz#cccaab758af56761eb7bf37af6f03f326dd798ad"
  integrity sha512-L7z9BgrNEcYyUYtF+HaEfiS5ebkh9jXqbszz7pC0hRBPaatV0XjSD3+eHrpqFemQfgwiFF0QPIarnIihIDn7OA==

"@types/body-parser@*":
  version "1.19.2"
  resolved "https://registry.npmmirror.com/@types/body-parser/-/body-parser-1.19.2.tgz#aea2059e28b7658639081347ac4fab3de166e6f0"
  integrity sha512-ALYone6pm6QmwZoAgeyNksccT9Q4AWZQ6PvfwR37GT6r6FWUPguq6sUmNGSMV2Wr761oQoBxwGGa6DR5o1DC9g==
  dependencies:
    "@types/connect" "*"
    "@types/node" "*"

"@types/bonjour@^3.5.9":
  version "3.5.10"
  resolved "https://registry.npmmirror.com/@types/bonjour/-/bonjour-3.5.10.tgz#0f6aadfe00ea414edc86f5d106357cda9701e275"
  integrity sha512-p7ienRMiS41Nu2/igbJxxLDWrSZ0WxM8UQgCeO9KhoVF7cOVFkrKsiDr1EsJIla8vV3oEEjGcz11jc5yimhzZw==
  dependencies:
    "@types/node" "*"

"@types/cacheable-request@^6.0.1":
  version "6.0.2"
  resolved "https://registry.npmmirror.com/@types/cacheable-request/-/cacheable-request-6.0.2.tgz#c324da0197de0a98a2312156536ae262429ff6b9"
  integrity sha512-B3xVo+dlKM6nnKTcmm5ZtY/OL8bOAOd2Olee9M1zft65ox50OzjEHW91sDiU9j6cvW8Ejg1/Qkf4xd2kugApUA==
  dependencies:
    "@types/http-cache-semantics" "*"
    "@types/keyv" "*"
    "@types/node" "*"
    "@types/responselike" "*"

"@types/connect-history-api-fallback@^1.3.5":
  version "1.3.5"
  resolved "https://registry.npmmirror.com/@types/connect-history-api-fallback/-/connect-history-api-fallback-1.3.5.tgz#d1f7a8a09d0ed5a57aee5ae9c18ab9b803205dae"
  integrity sha512-h8QJa8xSb1WD4fpKBDcATDNGXghFj6/3GRWG6dhmRcu0RX1Ubasur2Uvx5aeEwlf0MwblEC2bMzzMQntxnw/Cw==
  dependencies:
    "@types/express-serve-static-core" "*"
    "@types/node" "*"

"@types/connect@*":
  version "3.4.35"
  resolved "https://registry.npmmirror.com/@types/connect/-/connect-3.4.35.tgz#5fcf6ae445e4021d1fc2219a4873cc73a3bb2ad1"
  integrity sha512-cdeYyv4KWoEgpBISTxWvqYsVy444DOqehiF3fM3ne10AmJ62RSyNkUnxMJXHQWRQQX2eR94m5y1IZyDwBjV9FQ==
  dependencies:
    "@types/node" "*"

"@types/eslint-scope@^3.7.3":
  version "3.7.4"
  resolved "https://registry.npmmirror.com/@types/eslint-scope/-/eslint-scope-3.7.4.tgz#37fc1223f0786c39627068a12e94d6e6fc61de16"
  integrity sha512-9K4zoImiZc3HlIp6AVUDE4CWYx22a+lhSZMYNpbjW04+YF0KWj4pJXnEMjdnFTiQibFFmElcsasJXDbdI/EPhA==
  dependencies:
    "@types/eslint" "*"
    "@types/estree" "*"

"@types/eslint@*":
  version "8.4.10"
  resolved "https://registry.npmmirror.com/@types/eslint/-/eslint-8.4.10.tgz#19731b9685c19ed1552da7052b6f668ed7eb64bb"
  integrity sha512-Sl/HOqN8NKPmhWo2VBEPm0nvHnu2LL3v9vKo8MEq0EtbJ4eVzGPl41VNPvn5E1i5poMk4/XD8UriLHpJvEP/Nw==
  dependencies:
    "@types/estree" "*"
    "@types/json-schema" "*"

"@types/estree@*":
  version "1.0.0"
  resolved "https://registry.npmmirror.com/@types/estree/-/estree-1.0.0.tgz#5fb2e536c1ae9bf35366eed879e827fa59ca41c2"
  integrity sha512-WulqXMDUTYAXCjZnk6JtIHPigp55cVtDgDrO2gHRwhyJto21+1zbVCtOYB2L1F9w4qCQ0rOGWBnBe0FNTiEJIQ==

"@types/estree@^0.0.51":
  version "0.0.51"
  resolved "https://registry.npmmirror.com/@types/estree/-/estree-0.0.51.tgz#cfd70924a25a3fd32b218e5e420e6897e1ac4f40"
  integrity sha512-CuPgU6f3eT/XgKKPqKd/gLZV1Xmvf1a2R5POBOGQa6uv82xpls89HU5zKeVoyR8XzHd1RGNOlQlvUe3CFkjWNQ==

"@types/express-serve-static-core@*", "@types/express-serve-static-core@^4.17.18":
  version "4.17.31"
  resolved "https://registry.npmmirror.com/@types/express-serve-static-core/-/express-serve-static-core-4.17.31.tgz#a1139efeab4e7323834bb0226e62ac019f474b2f"
  integrity sha512-DxMhY+NAsTwMMFHBTtJFNp5qiHKJ7TeqOo23zVEM9alT1Ml27Q3xcTH0xwxn7Q0BbMcVEJOs/7aQtUWupUQN3Q==
  dependencies:
    "@types/node" "*"
    "@types/qs" "*"
    "@types/range-parser" "*"

"@types/express@*", "@types/express@^4.17.13":
  version "4.17.14"
  resolved "https://registry.npmmirror.com/@types/express/-/express-4.17.14.tgz#143ea0557249bc1b3b54f15db4c81c3d4eb3569c"
  integrity sha512-TEbt+vaPFQ+xpxFLFssxUDXj5cWCxZJjIcB7Yg0k0GMHGtgtQgpvx/MUQUeAkNbA9AAGrwkAsoeItdTgS7FMyg==
  dependencies:
    "@types/body-parser" "*"
    "@types/express-serve-static-core" "^4.17.18"
    "@types/qs" "*"
    "@types/serve-static" "*"

"@types/github-slugger@^1.3.0":
  version "1.3.0"
  resolved "https://registry.npmmirror.com/@types/github-slugger/-/github-slugger-1.3.0.tgz#16ab393b30d8ae2a111ac748a015ac05a1fc5524"
  integrity sha512-J/rMZa7RqiH/rT29TEVZO4nBoDP9XJOjnbbIofg7GQKs4JIduEO3WLpte+6WeUz/TcrXKlY+bM7FYrp8yFB+3g==

"@types/hast@^2.0.0":
  version "2.3.4"
  resolved "https://registry.npmmirror.com/@types/hast/-/hast-2.3.4.tgz#8aa5ef92c117d20d974a82bdfb6a648b08c0bafc"
  integrity sha512-wLEm0QvaoawEDoTRwzTXp4b4jpwiJDvR5KMnFnVodm3scufTlBOWRD6N1OBf9TZMhjlNsSfcO5V+7AF4+Vy+9g==
  dependencies:
    "@types/unist" "*"

"@types/html-minifier-terser@^6.0.0":
  version "6.1.0"
  resolved "https://registry.npmmirror.com/@types/html-minifier-terser/-/html-minifier-terser-6.1.0.tgz#4fc33a00c1d0c16987b1a20cf92d20614c55ac35"
  integrity sha512-oh/6byDPnL1zeNXFrDXFLyZjkr1MsBG667IM792caf1L2UPOOMf65NFzjUH/ltyfwjAGfs1rsX1eftK0jC/KIg==

"@types/http-cache-semantics@*":
  version "4.0.1"
  resolved "https://registry.npmmirror.com/@types/http-cache-semantics/-/http-cache-semantics-4.0.1.tgz#0ea7b61496902b95890dc4c3a116b60cb8dae812"
  integrity sha512-SZs7ekbP8CN0txVG2xVRH6EgKmEm31BOxA07vkFaETzZz1xh+cbt8BcI0slpymvwhx5dlFnQG2rTlPVQn+iRPQ==

"@types/http-proxy@^1.17.8":
  version "1.17.9"
  resolved "https://registry.npmmirror.com/@types/http-proxy/-/http-proxy-1.17.9.tgz#7f0e7931343761efde1e2bf48c40f02f3f75705a"
  integrity sha512-QsbSjA/fSk7xB+UXlCT3wHBy5ai9wOcNDWwZAtud+jXhwOM3l+EYZh8Lng4+/6n8uar0J7xILzqftJdJ/Wdfkw==
  dependencies:
    "@types/node" "*"

"@types/json-schema@*", "@types/json-schema@^7.0.4", "@types/json-schema@^7.0.5", "@types/json-schema@^7.0.8", "@types/json-schema@^7.0.9":
  version "7.0.11"
  resolved "https://registry.npmmirror.com/@types/json-schema/-/json-schema-7.0.11.tgz#d421b6c527a3037f7c84433fd2c4229e016863d3"
  integrity sha512-wOuvG1SN4Us4rez+tylwwwCV1psiNVOkJeM3AUWUNWg/jDQY2+HE/444y5gc+jBmRqASOm2Oeh5c1axHobwRKQ==

"@types/katex@^0.11.0":
  version "0.11.1"
  resolved "https://registry.npmmirror.com/@types/katex/-/katex-0.11.1.tgz#34de04477dcf79e2ef6c8d23b41a3d81f9ebeaf5"
  integrity sha512-DUlIj2nk0YnJdlWgsFuVKcX27MLW0KbKmGVoUHmFr+74FYYNUDAaj9ZqTADvsbE8rfxuVmSFc7KczYn5Y09ozg==

"@types/keyv@*":
  version "4.2.0"
  resolved "https://registry.npmmirror.com/@types/keyv/-/keyv-4.2.0.tgz#65b97868ab757906f2dbb653590d7167ad023fa0"
  integrity sha512-xoBtGl5R9jeKUhc8ZqeYaRDx04qqJ10yhhXYGmJ4Jr8qKpvMsDQQrNUvF/wUJ4klOtmJeJM+p2Xo3zp9uaC3tw==
  dependencies:
    keyv "*"

"@types/mdast@^3.0.0":
  version "3.0.10"
  resolved "https://registry.npmmirror.com/@types/mdast/-/mdast-3.0.10.tgz#4724244a82a4598884cbbe9bcfd73dff927ee8af"
  integrity sha512-W864tg/Osz1+9f4lrGTZpCSO5/z4608eUp19tbozkq2HJK6i3z1kT0H9tlADXuYIb1YYOBByU4Jsqkk75q48qA==
  dependencies:
    "@types/unist" "*"

"@types/mime@*":
  version "3.0.1"
  resolved "https://registry.npmmirror.com/@types/mime/-/mime-3.0.1.tgz#5f8f2bca0a5863cb69bc0b0acd88c96cb1d4ae10"
  integrity sha512-Y4XFY5VJAuw0FgAqPNd6NNoV44jbq9Bz2L7Rh/J6jLTiHBSBJa9fxqQIvkIld4GsoDOcCbvzOUAbLPsSKKg+uA==

"@types/node@*":
  version "18.11.9"
  resolved "https://registry.npmmirror.com/@types/node/-/node-18.11.9.tgz#02d013de7058cea16d36168ef2fc653464cfbad4"
  integrity sha512-CRpX21/kGdzjOpFsZSkcrXMGIBWMGNIHXXBVFSH+ggkftxg+XYP20TESbh+zFvFj3EQOl5byk0HTRn1IL6hbqg==

"@types/node@^17.0.5":
  version "17.0.45"
  resolved "https://registry.npmmirror.com/@types/node/-/node-17.0.45.tgz#2c0fafd78705e7a18b7906b5201a522719dc5190"
  integrity sha512-w+tIMs3rq2afQdsPJlODhoUEKzFP1ayaoyl1CcnwtIlsVe7K7bA1NGm4s3PraqTLlXnbIN84zuBlxBWo1u9BLw==

"@types/parse-json@^4.0.0":
  version "4.0.0"
  resolved "https://registry.npmmirror.com/@types/parse-json/-/parse-json-4.0.0.tgz#2f8bb441434d163b35fb8ffdccd7138927ffb8c0"
  integrity sha512-//oorEZjL6sbPcKUaCdIGlIUeH26mgzimjBB77G6XRgnDl/L5wOnpyBGRe/Mmf5CVW3PwEBE1NjiMZ/ssFh4wA==

"@types/parse5@^5.0.0":
  version "5.0.3"
  resolved "https://registry.npmmirror.com/@types/parse5/-/parse5-5.0.3.tgz#e7b5aebbac150f8b5fdd4a46e7f0bd8e65e19109"
  integrity sha512-kUNnecmtkunAoQ3CnjmMkzNU/gtxG8guhi+Fk2U/kOpIKjIMKnXGp4IJCgQJrXSgMsWYimYG4TGjz/UzbGEBTw==

"@types/prop-types@*":
  version "15.7.5"
  resolved "https://registry.npmmirror.com/@types/prop-types/-/prop-types-15.7.5.tgz#5f19d2b85a98e9558036f6a3cacc8819420f05cf"
  integrity sha512-JCB8C6SnDoQf0cNycqd/35A7MjcnK+ZTqE7judS6o7utxUCg6imJg3QK2qzHKszlTjcj2cn+NwMB2i96ubpj7w==

"@types/q@^1.5.1":
  version "1.5.5"
  resolved "https://registry.npmmirror.com/@types/q/-/q-1.5.5.tgz#75a2a8e7d8ab4b230414505d92335d1dcb53a6df"
  integrity sha512-L28j2FcJfSZOnL1WBjDYp2vUHCeIFlyYI/53EwD/rKUBQ7MtUUfbQWiyKJGpcnv4/WgrhWsFKrcPstcAt/J0tQ==

"@types/qs@*":
  version "6.9.7"
  resolved "https://registry.npmmirror.com/@types/qs/-/qs-6.9.7.tgz#63bb7d067db107cc1e457c303bc25d511febf6cb"
  integrity sha512-FGa1F62FT09qcrueBA6qYTrJPVDzah9a+493+o2PCXsesWHIn27G98TsSMs3WPNbZIEj4+VJf6saSFpvD+3Zsw==

"@types/range-parser@*":
  version "1.2.4"
  resolved "https://registry.npmmirror.com/@types/range-parser/-/range-parser-1.2.4.tgz#cd667bcfdd025213aafb7ca5915a932590acdcdc"
  integrity sha512-EEhsLsD6UsDM1yFhAvy0Cjr6VwmpMWqFBCb9w07wVugF7w9nfajxLuVmngTIpgS6svCnm6Vaw+MZhoDCKnOfsw==

"@types/react@*":
  version "18.0.25"
  resolved "https://registry.npmmirror.com/@types/react/-/react-18.0.25.tgz#8b1dcd7e56fe7315535a4af25435e0bb55c8ae44"
  integrity sha512-xD6c0KDT4m7n9uD4ZHi02lzskaiqcBxf4zi+tXZY98a04wvc0hi/TcCPC2FOESZi51Nd7tlUeOJY8RofL799/g==
  dependencies:
    "@types/prop-types" "*"
    "@types/scheduler" "*"
    csstype "^3.0.2"

"@types/responselike@*", "@types/responselike@^1.0.0":
  version "1.0.0"
  resolved "https://registry.npmmirror.com/@types/responselike/-/responselike-1.0.0.tgz#251f4fe7d154d2bad125abe1b429b23afd262e29"
  integrity sha512-85Y2BjiufFzaMIlvJDvTTB8Fxl2xfLo4HgmHzVBz08w4wDePCTjYw66PdrolO0kzli3yam/YCgRufyo1DdQVTA==
  dependencies:
    "@types/node" "*"

"@types/retry@0.12.0":
  version "0.12.0"
  resolved "https://registry.npmmirror.com/@types/retry/-/retry-0.12.0.tgz#2b35eccfcee7d38cd72ad99232fbd58bffb3c84d"
  integrity sha512-wWKOClTTiizcZhXnPY4wikVAwmdYHp8q6DmC+EJUzAMsycb7HB32Kh9RN4+0gExjmPmZSAQjgURXIGATPegAvA==

"@types/sax@^1.2.1":
  version "1.2.4"
  resolved "https://registry.npmmirror.com/@types/sax/-/sax-1.2.4.tgz#8221affa7f4f3cb21abd22f244cfabfa63e6a69e"
  integrity sha512-pSAff4IAxJjfAXUG6tFkO7dsSbTmf8CtUpfhhZ5VhkRpC4628tJhh3+V6H1E+/Gs9piSzYKT5yzHO5M4GG9jkw==
  dependencies:
    "@types/node" "*"

"@types/scheduler@*":
  version "0.16.2"
  resolved "https://registry.npmmirror.com/@types/scheduler/-/scheduler-0.16.2.tgz#1a62f89525723dde24ba1b01b092bf5df8ad4d39"
  integrity sha512-hppQEBDmlwhFAXKJX2KnWLYu5yMfi91yazPb2l+lbJiwW+wdo1gNeRA+3RgNSO39WYX2euey41KEwnqesU2Jew==

"@types/serve-index@^1.9.1":
  version "1.9.1"
  resolved "https://registry.npmmirror.com/@types/serve-index/-/serve-index-1.9.1.tgz#1b5e85370a192c01ec6cec4735cf2917337a6278"
  integrity sha512-d/Hs3nWDxNL2xAczmOVZNj92YZCS6RGxfBPjKzuu/XirCgXdpKEb88dYNbrYGint6IVWLNP+yonwVAuRC0T2Dg==
  dependencies:
    "@types/express" "*"

"@types/serve-static@*", "@types/serve-static@^1.13.10":
  version "1.15.0"
  resolved "https://registry.npmmirror.com/@types/serve-static/-/serve-static-1.15.0.tgz#c7930ff61afb334e121a9da780aac0d9b8f34155"
  integrity sha512-z5xyF6uh8CbjAu9760KDKsH2FcDxZ2tFCsA4HIMWE6IkiYMXfVoa+4f9KX+FN0ZLsaMw1WNG2ETLA6N+/YA+cg==
  dependencies:
    "@types/mime" "*"
    "@types/node" "*"

"@types/sockjs@^0.3.33":
  version "0.3.33"
  resolved "https://registry.npmmirror.com/@types/sockjs/-/sockjs-0.3.33.tgz#570d3a0b99ac995360e3136fd6045113b1bd236f"
  integrity sha512-f0KEEe05NvUnat+boPTZ0dgaLZ4SfSouXUgv5noUiefG2ajgKjmETo9ZJyuqsl7dfl2aHlLJUiki6B4ZYldiiw==
  dependencies:
    "@types/node" "*"

"@types/unist@*", "@types/unist@^2.0.0", "@types/unist@^2.0.2", "@types/unist@^2.0.3":
  version "2.0.6"
  resolved "https://registry.npmmirror.com/@types/unist/-/unist-2.0.6.tgz#250a7b16c3b91f672a24552ec64678eeb1d3a08d"
  integrity sha512-PBjIUxZHOuj0R15/xuwJYjFi+KZdNFrehocChv4g5hu6aFroHue8m0lBP0POdK2nKzbw0cgV1mws8+V/JAcEkQ==

"@types/ws@^8.5.1":
  version "8.5.3"
  resolved "https://registry.npmmirror.com/@types/ws/-/ws-8.5.3.tgz#7d25a1ffbecd3c4f2d35068d0b283c037003274d"
  integrity sha512-6YOoWjruKj1uLf3INHH7D3qTXwFfEsg1kf3c0uDdSBJwfa/llkwIjrAGV7j7mVgGNbzTQ3HiHKKDXl6bJPD97w==
  dependencies:
    "@types/node" "*"

"@webassemblyjs/ast@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/ast/-/ast-1.11.1.tgz#2bfd767eae1a6996f432ff7e8d7fc75679c0b6a7"
  integrity sha512-ukBh14qFLjxTQNTXocdyksN5QdM28S1CxHt2rdskFyL+xFV7VremuBLVbmCePj+URalXBENx/9Lm7lnhihtCSw==
  dependencies:
    "@webassemblyjs/helper-numbers" "1.11.1"
    "@webassemblyjs/helper-wasm-bytecode" "1.11.1"

"@webassemblyjs/floating-point-hex-parser@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/floating-point-hex-parser/-/floating-point-hex-parser-1.11.1.tgz#f6c61a705f0fd7a6aecaa4e8198f23d9dc179e4f"
  integrity sha512-iGRfyc5Bq+NnNuX8b5hwBrRjzf0ocrJPI6GWFodBFzmFnyvrQ83SHKhmilCU/8Jv67i4GJZBMhEzltxzcNagtQ==

"@webassemblyjs/helper-api-error@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/helper-api-error/-/helper-api-error-1.11.1.tgz#1a63192d8788e5c012800ba6a7a46c705288fd16"
  integrity sha512-RlhS8CBCXfRUR/cwo2ho9bkheSXG0+NwooXcc3PAILALf2QLdFyj7KGsKRbVc95hZnhnERon4kW/D3SZpp6Tcg==

"@webassemblyjs/helper-buffer@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/helper-buffer/-/helper-buffer-1.11.1.tgz#832a900eb444884cde9a7cad467f81500f5e5ab5"
  integrity sha512-gwikF65aDNeeXa8JxXa2BAk+REjSyhrNC9ZwdT0f8jc4dQQeDQ7G4m0f2QCLPJiMTTO6wfDmRmj/pW0PsUvIcA==

"@webassemblyjs/helper-numbers@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/helper-numbers/-/helper-numbers-1.11.1.tgz#64d81da219fbbba1e3bd1bfc74f6e8c4e10a62ae"
  integrity sha512-vDkbxiB8zfnPdNK9Rajcey5C0w+QJugEglN0of+kmO8l7lDb77AnlKYQF7aarZuCrv+l0UvqL+68gSDr3k9LPQ==
  dependencies:
    "@webassemblyjs/floating-point-hex-parser" "1.11.1"
    "@webassemblyjs/helper-api-error" "1.11.1"
    "@xtuc/long" "4.2.2"

"@webassemblyjs/helper-wasm-bytecode@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/helper-wasm-bytecode/-/helper-wasm-bytecode-1.11.1.tgz#f328241e41e7b199d0b20c18e88429c4433295e1"
  integrity sha512-PvpoOGiJwXeTrSf/qfudJhwlvDQxFgelbMqtq52WWiXC6Xgg1IREdngmPN3bs4RoO83PnL/nFrxucXj1+BX62Q==

"@webassemblyjs/helper-wasm-section@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/helper-wasm-section/-/helper-wasm-section-1.11.1.tgz#21ee065a7b635f319e738f0dd73bfbda281c097a"
  integrity sha512-10P9No29rYX1j7F3EVPX3JvGPQPae+AomuSTPiF9eBQeChHI6iqjMIwR9JmOJXwpnn/oVGDk7I5IlskuMwU/pg==
  dependencies:
    "@webassemblyjs/ast" "1.11.1"
    "@webassemblyjs/helper-buffer" "1.11.1"
    "@webassemblyjs/helper-wasm-bytecode" "1.11.1"
    "@webassemblyjs/wasm-gen" "1.11.1"

"@webassemblyjs/ieee754@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/ieee754/-/ieee754-1.11.1.tgz#963929e9bbd05709e7e12243a099180812992614"
  integrity sha512-hJ87QIPtAMKbFq6CGTkZYJivEwZDbQUgYd3qKSadTNOhVY7p+gfP6Sr0lLRVTaG1JjFj+r3YchoqRYxNH3M0GQ==
  dependencies:
    "@xtuc/ieee754" "^1.2.0"

"@webassemblyjs/leb128@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/leb128/-/leb128-1.11.1.tgz#ce814b45574e93d76bae1fb2644ab9cdd9527aa5"
  integrity sha512-BJ2P0hNZ0u+Th1YZXJpzW6miwqQUGcIHT1G/sf72gLVD9DZ5AdYTqPNbHZh6K1M5VmKvFXwGSWZADz+qBWxeRw==
  dependencies:
    "@xtuc/long" "4.2.2"

"@webassemblyjs/utf8@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/utf8/-/utf8-1.11.1.tgz#d1f8b764369e7c6e6bae350e854dec9a59f0a3ff"
  integrity sha512-9kqcxAEdMhiwQkHpkNiorZzqpGrodQQ2IGrHHxCy+Ozng0ofyMA0lTqiLkVs1uzTRejX+/O0EOT7KxqVPuXosQ==

"@webassemblyjs/wasm-edit@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/wasm-edit/-/wasm-edit-1.11.1.tgz#ad206ebf4bf95a058ce9880a8c092c5dec8193d6"
  integrity sha512-g+RsupUC1aTHfR8CDgnsVRVZFJqdkFHpsHMfJuWQzWU3tvnLC07UqHICfP+4XyL2tnr1amvl1Sdp06TnYCmVkA==
  dependencies:
    "@webassemblyjs/ast" "1.11.1"
    "@webassemblyjs/helper-buffer" "1.11.1"
    "@webassemblyjs/helper-wasm-bytecode" "1.11.1"
    "@webassemblyjs/helper-wasm-section" "1.11.1"
    "@webassemblyjs/wasm-gen" "1.11.1"
    "@webassemblyjs/wasm-opt" "1.11.1"
    "@webassemblyjs/wasm-parser" "1.11.1"
    "@webassemblyjs/wast-printer" "1.11.1"

"@webassemblyjs/wasm-gen@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/wasm-gen/-/wasm-gen-1.11.1.tgz#86c5ea304849759b7d88c47a32f4f039ae3c8f76"
  integrity sha512-F7QqKXwwNlMmsulj6+O7r4mmtAlCWfO/0HdgOxSklZfQcDu0TpLiD1mRt/zF25Bk59FIjEuGAIyn5ei4yMfLhA==
  dependencies:
    "@webassemblyjs/ast" "1.11.1"
    "@webassemblyjs/helper-wasm-bytecode" "1.11.1"
    "@webassemblyjs/ieee754" "1.11.1"
    "@webassemblyjs/leb128" "1.11.1"
    "@webassemblyjs/utf8" "1.11.1"

"@webassemblyjs/wasm-opt@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/wasm-opt/-/wasm-opt-1.11.1.tgz#657b4c2202f4cf3b345f8a4c6461c8c2418985f2"
  integrity sha512-VqnkNqnZlU5EB64pp1l7hdm3hmQw7Vgqa0KF/KCNO9sIpI6Fk6brDEiX+iCOYrvMuBWDws0NkTOxYEb85XQHHw==
  dependencies:
    "@webassemblyjs/ast" "1.11.1"
    "@webassemblyjs/helper-buffer" "1.11.1"
    "@webassemblyjs/wasm-gen" "1.11.1"
    "@webassemblyjs/wasm-parser" "1.11.1"

"@webassemblyjs/wasm-parser@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/wasm-parser/-/wasm-parser-1.11.1.tgz#86ca734534f417e9bd3c67c7a1c75d8be41fb199"
  integrity sha512-rrBujw+dJu32gYB7/Lup6UhdkPx9S9SnobZzRVL7VcBH9Bt9bCBLEuX/YXOOtBsOZ4NQrRykKhffRWHvigQvOA==
  dependencies:
    "@webassemblyjs/ast" "1.11.1"
    "@webassemblyjs/helper-api-error" "1.11.1"
    "@webassemblyjs/helper-wasm-bytecode" "1.11.1"
    "@webassemblyjs/ieee754" "1.11.1"
    "@webassemblyjs/leb128" "1.11.1"
    "@webassemblyjs/utf8" "1.11.1"

"@webassemblyjs/wast-printer@1.11.1":
  version "1.11.1"
  resolved "https://registry.npmmirror.com/@webassemblyjs/wast-printer/-/wast-printer-1.11.1.tgz#d0c73beda8eec5426f10ae8ef55cee5e7084c2f0"
  integrity sha512-IQboUWM4eKzWW+N/jij2sRatKMh99QEelo3Eb2q0qXkvPRISAj8Qxtmw5itwqK+TTkBuUIE45AxYPToqPtL5gg==
  dependencies:
    "@webassemblyjs/ast" "1.11.1"
    "@xtuc/long" "4.2.2"

"@xtuc/ieee754@^1.2.0":
  version "1.2.0"
  resolved "https://registry.npmmirror.com/@xtuc/ieee754/-/ieee754-1.2.0.tgz#eef014a3145ae477a1cbc00cd1e552336dceb790"
  integrity sha512-DX8nKgqcGwsc0eJSqYt5lwP4DH5FlHnmuWWBRy7X0NcaGR0ZtuyeESgMwTYVEtxmsNGY+qit4QYT/MIYTOTPeA==

"@xtuc/long@4.2.2":
  version "4.2.2"
  resolved "https://registry.npmmirror.com/@xtuc/long/-/long-4.2.2.tgz#d291c6a4e97989b5c61d9acf396ae4fe133a718d"
  integrity sha512-NuHqBY1PB/D8xU6s/thBgOAiAP7HOYDQ32+BFZILJ8ivkUkAHQnWfn6WhL79Owj1qmUnoN/YPhktdIoucipkAQ==

accepts@~1.3.4, accepts@~1.3.5, accepts@~1.3.8:
  version "1.3.8"
  resolved "https://registry.npmmirror.com/accepts/-/accepts-1.3.8.tgz#0bf0be125b67014adcb0b0921e62db7bffe16b2e"
  integrity sha512-PYAthTa2m2VKxuvSD3DPC/Gy+U+sOA1LAuT8mkmRuvw+NACSaeXEQ+NHcVF7rONl6qcaxV3Uuemwawk+7+SJLw==
  dependencies:
    mime-types "~2.1.34"
    negotiator "0.6.3"

acorn-dynamic-import@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/acorn-dynamic-import/-/acorn-dynamic-import-4.0.0.tgz#482210140582a36b83c3e342e1cfebcaa9240948"
  integrity sha512-d3OEjQV4ROpoflsnUA8HozoIR504TFxNivYEUi6uwz0IYhBkTDXGuWlNdMtybRt3nqVx/L6XqMt0FxkXuWKZhw==

acorn-import-assertions@^1.7.6:
  version "1.8.0"
  resolved "https://registry.npmmirror.com/acorn-import-assertions/-/acorn-import-assertions-1.8.0.tgz#ba2b5939ce62c238db6d93d81c9b111b29b855e9"
  integrity sha512-m7VZ3jwz4eK6A4Vtt8Ew1/mNbP24u0FhdyfA7fSvnJR6LMdfOYnmuIrrJAgrYfYJ10F/otaHTtrtrtmHdMNzEw==

acorn-jsx@^5.0.1:
  version "5.3.2"
  resolved "https://registry.npmmirror.com/acorn-jsx/-/acorn-jsx-5.3.2.tgz#7ed5bb55908b3b2f1bc55c6af1653bada7f07937"
  integrity sha512-rq9s+JNhf0IChjtDXxllJ7g41oZk5SlXtp0LHwyA5cejwn7vKmKp4pPri6YEePv2PU65sAsegbXtIinmDFDXgQ==

acorn-walk@^8.0.0:
  version "8.2.0"
  resolved "https://registry.npmmirror.com/acorn-walk/-/acorn-walk-8.2.0.tgz#741210f2e2426454508853a2f44d0ab83b7f69c1"
  integrity sha512-k+iyHEuPgSw6SbuDpGQM+06HQUa04DZ3o+F6CSzXMvvI5KMvnaEqXe+YVe555R9nn6GPt404fos4wcgpw12SDA==

acorn@^6.1.1:
  version "6.4.2"
  resolved "https://registry.npmmirror.com/acorn/-/acorn-6.4.2.tgz#35866fd710528e92de10cf06016498e47e39e1e6"
  integrity sha512-XtGIhXwF8YM8bJhGxG5kXgjkEuNGLTkoYqVE+KMR+aspr4KGYmKYg7yUe3KghyQ9yheNwLnjmzh/7+gfDBmHCQ==

acorn@^8.0.4, acorn@^8.5.0, acorn@^8.7.1:
  version "8.8.1"
  resolved "https://registry.npmmirror.com/acorn/-/acorn-8.8.1.tgz#0a3f9cbecc4ec3bea6f0a80b66ae8dd2da250b73"
  integrity sha512-7zFpHzhnqYKrkYdUjF1HI1bzd0VygEGX8lFk4k5zVMqHEoES+P+7TKI+EvLO9WVMJ8eekdO0aDEK044xTXwPPA==

address@^1.0.1, address@^1.1.2:
  version "1.2.1"
  resolved "https://registry.npmmirror.com/address/-/address-1.2.1.tgz#25bb61095b7522d65b357baa11bc05492d4c8acd"
  integrity sha512-B+6bi5D34+fDYENiH5qOlA0cV2rAGKuWZ9LeyUUehbXy8e0VS9e498yO0Jeeh+iM+6KbfudHTFjXw2MmJD4QRA==

aggregate-error@^3.0.0:
  version "3.1.0"
  resolved "https://registry.npmmirror.com/aggregate-error/-/aggregate-error-3.1.0.tgz#92670ff50f5359bdb7a3e0d40d0ec30c5737687a"
  integrity sha512-4I7Td01quW/RpocfNayFdFVk1qSuoh0E7JrbRJ16nH01HhKFQ88INq9Sd+nd72zqRySlr9BmDA8xlEJ6vJMrYA==
  dependencies:
    clean-stack "^2.0.0"
    indent-string "^4.0.0"

ajv-formats@^2.1.1:
  version "2.1.1"
  resolved "https://registry.npmmirror.com/ajv-formats/-/ajv-formats-2.1.1.tgz#6e669400659eb74973bbf2e33327180a0996b520"
  integrity sha512-Wx0Kx52hxE7C18hkMEggYlEifqWZtYaRgouJor+WMdPnQyEK13vgEWyVNup7SoeeoLMsr4kf5h6dOW11I15MUA==
  dependencies:
    ajv "^8.0.0"

ajv-keywords@^3.4.1, ajv-keywords@^3.5.2:
  version "3.5.2"
  resolved "https://registry.npmmirror.com/ajv-keywords/-/ajv-keywords-3.5.2.tgz#31f29da5ab6e00d1c2d329acf7b5929614d5014d"
  integrity sha512-5p6WTN0DdTGVQk6VjcEju19IgaHudalcfabD7yhDGeA6bcQnmL+CpveLJq/3hvfwd1aof6L386Ougkx6RfyMIQ==

ajv-keywords@^5.0.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/ajv-keywords/-/ajv-keywords-5.1.0.tgz#69d4d385a4733cdbeab44964a1170a88f87f0e16"
  integrity sha512-YCS/JNFAUyr5vAuhk1DWm1CBxRHW9LbJ2ozWeemrIqpbsqKjHVxYPyi5GC0rjZIT5JxJ3virVTS8wk4i/Z+krw==
  dependencies:
    fast-deep-equal "^3.1.3"

ajv@^6.12.2, ajv@^6.12.4, ajv@^6.12.5:
  version "6.12.6"
  resolved "https://registry.npmmirror.com/ajv/-/ajv-6.12.6.tgz#baf5a62e802b07d977034586f8c3baf5adf26df4"
  integrity sha512-j3fVLgvTo527anyYyJOGTYJbG+vnnQYvE0m5mmkc1TK+nxAppkCLMIL0aZ4dblVCNoGShhm+kzE4ZUykBoMg4g==
  dependencies:
    fast-deep-equal "^3.1.1"
    fast-json-stable-stringify "^2.0.0"
    json-schema-traverse "^0.4.1"
    uri-js "^4.2.2"

ajv@^8.0.0, ajv@^8.8.0:
  version "8.11.0"
  resolved "https://registry.npmmirror.com/ajv/-/ajv-8.11.0.tgz#977e91dd96ca669f54a11e23e378e33b884a565f"
  integrity sha512-wGgprdCvMalC0BztXvitD2hC04YffAvtsUn93JbGXYLAtCUO4xd17mCCZQxUOItiBwZvJScWo8NIvQMQ71rdpg==
  dependencies:
    fast-deep-equal "^3.1.1"
    json-schema-traverse "^1.0.0"
    require-from-string "^2.0.2"
    uri-js "^4.2.2"

algoliasearch-helper@^3.5.5:
  version "3.11.1"
  resolved "https://registry.npmmirror.com/algoliasearch-helper/-/algoliasearch-helper-3.11.1.tgz#d83ab7f1a2a374440686ef7a144b3c288b01188a"
  integrity sha512-mvsPN3eK4E0bZG0/WlWJjeqe/bUD2KOEVOl0GyL/TGXn6wcpZU8NOuztGHCUKXkyg5gq6YzUakVTmnmSSO5Yiw==
  dependencies:
    "@algolia/events" "^4.0.1"

algoliasearch@^4.0.0, algoliasearch@^4.10.5:
  version "4.14.2"
  resolved "https://registry.npmmirror.com/algoliasearch/-/algoliasearch-4.14.2.tgz#63f142583bfc3a9bd3cd4a1b098bf6fe58e56f6c"
  integrity sha512-ngbEQonGEmf8dyEh5f+uOIihv4176dgbuOZspiuhmTTBRBuzWu3KCGHre6uHj5YyuC7pNvQGzB6ZNJyZi0z+Sg==
  dependencies:
    "@algolia/cache-browser-local-storage" "4.14.2"
    "@algolia/cache-common" "4.14.2"
    "@algolia/cache-in-memory" "4.14.2"
    "@algolia/client-account" "4.14.2"
    "@algolia/client-analytics" "4.14.2"
    "@algolia/client-common" "4.14.2"
    "@algolia/client-personalization" "4.14.2"
    "@algolia/client-search" "4.14.2"
    "@algolia/logger-common" "4.14.2"
    "@algolia/logger-console" "4.14.2"
    "@algolia/requester-browser-xhr" "4.14.2"
    "@algolia/requester-common" "4.14.2"
    "@algolia/requester-node-http" "4.14.2"
    "@algolia/transporter" "4.14.2"

ansi-align@^3.0.0:
  version "3.0.1"
  resolved "https://registry.npmmirror.com/ansi-align/-/ansi-align-3.0.1.tgz#0cdf12e111ace773a86e9a1fad1225c43cb19a59"
  integrity sha512-IOfwwBF5iczOjp/WeY4YxyjqAFMQoZufdQWDd19SEExbVLNXqvpzSJ/M7Za4/sCPmQ0+GRquoA7bGcINcxew6w==
  dependencies:
    string-width "^4.1.0"

ansi-html-community@^0.0.8:
  version "0.0.8"
  resolved "https://registry.npmmirror.com/ansi-html-community/-/ansi-html-community-0.0.8.tgz#69fbc4d6ccbe383f9736934ae34c3f8290f1bf41"
  integrity sha512-1APHAyr3+PCamwNw3bXCPp4HFLONZt/yIH0sZp0/469KWNTEy+qN5jQ3GVX6DMZ1UXAi34yVwtTeaG/HpBuuzw==

ansi-regex@^5.0.1:
  version "5.0.1"
  resolved "https://registry.npmmirror.com/ansi-regex/-/ansi-regex-5.0.1.tgz#082cb2c89c9fe8659a311a53bd6a4dc5301db304"
  integrity sha512-quJQXlTSUGL2LH9SUXo8VwsY4soanhgo6LNSm84E1LBcE8s3O0wpdiRzyR9z/ZZJMlMWv37qOOb9pdJlMUEKFQ==

ansi-styles@^3.2.1:
  version "3.2.1"
  resolved "https://registry.npmmirror.com/ansi-styles/-/ansi-styles-3.2.1.tgz#41fbb20243e50b12be0f04b8dedbf07520ce841d"
  integrity sha512-VT0ZI6kZRdTh8YyJw3SMbYm/u+NqfsAxEpWO0Pf9sq8/e94WxxOpPKx9FR1FlyCtOVDNOQ+8ntlqFxiRc+r5qA==
  dependencies:
    color-convert "^1.9.0"

ansi-styles@^4.0.0, ansi-styles@^4.1.0:
  version "4.3.0"
  resolved "https://registry.npmmirror.com/ansi-styles/-/ansi-styles-4.3.0.tgz#edd803628ae71c04c85ae7a0906edad34b648937"
  integrity sha512-zbB9rCJAT1rbjiVDb2hqKFHNYLxgtk8NURxZ3IZwD3F6NtxbXZQCnnSi1Lkx+IDohdPlFp222wVALIheZJQSEg==
  dependencies:
    color-convert "^2.0.1"

anymatch@~3.1.2:
  version "3.1.2"
  resolved "https://registry.npmmirror.com/anymatch/-/anymatch-3.1.2.tgz#c0557c096af32f106198f4f4e2a383537e378716"
  integrity sha512-P43ePfOAIupkguHUycrc4qJ9kz8ZiuOUijaETwX7THt0Y/GNK7v0aa8rY816xWjZ7rJdA5XdMcpVFTKMq+RvWg==
  dependencies:
    normalize-path "^3.0.0"
    picomatch "^2.0.4"

arg@^5.0.0:
  version "5.0.2"
  resolved "https://registry.npmmirror.com/arg/-/arg-5.0.2.tgz#c81433cc427c92c4dcf4865142dbca6f15acd59c"
  integrity sha512-PYjyFOLKQ9y57JvQ6QLo8dAgNqswh8M1RMJYdQduT6xbWSgK36P/Z/v+p888pM69jMMfS8Xd8F6I1kQ/I9HUGg==

argparse@^1.0.7:
  version "1.0.10"
  resolved "https://registry.npmmirror.com/argparse/-/argparse-1.0.10.tgz#bcd6791ea5ae09725e17e5ad988134cd40b3d911"
  integrity sha512-o5Roy6tNG4SL/FOkCAN6RzjiakZS25RLYFrcMttJqbdd8BWrnA+fGz57iN5Pb06pvBGvl5gQ0B48dJlslXvoTg==
  dependencies:
    sprintf-js "~1.0.2"

argparse@^2.0.1:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/argparse/-/argparse-2.0.1.tgz#246f50f3ca78a3240f6c997e8a9bd1eac49e4b38"
  integrity sha512-8+9WqebbFzpX9OR+Wa6O29asIogeRMzcGtAINdpMHHyAg10f05aSFVBbcEqGf/PXw1EjAZ+q2/bEBg3DvurK3Q==

array-flatten@1.1.1:
  version "1.1.1"
  resolved "https://registry.npmmirror.com/array-flatten/-/array-flatten-1.1.1.tgz#9a5f699051b1e7073328f2a008968b64ea2955d2"
  integrity sha512-PCVAQswWemu6UdxsDFFX/+gVeYqKAod3D3UVm91jHwynguOwAvYPhx8nNlM++NqRcK6CxxpUafjmhIdKiHibqg==

array-flatten@^2.1.2:
  version "2.1.2"
  resolved "https://registry.npmmirror.com/array-flatten/-/array-flatten-2.1.2.tgz#24ef80a28c1a893617e2149b0c6d0d788293b099"
  integrity sha512-hNfzcOV8W4NdualtqBFPyVO+54DSJuZGY9qT4pRroB6S9e3iiido2ISIC5h9R2sPJ8H3FHCIiEnsv1lPXO3KtQ==

array-union@^2.1.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/array-union/-/array-union-2.1.0.tgz#b798420adbeb1de828d84acd8a2e23d3efe85e8d"
  integrity sha512-HGyxoOTYUyCM6stUe6EJgnd4EoewAI7zMdfqO+kGjnlZmBDz/cR5pf8r/cR4Wq60sL/p0IkcjUEEPwS3GFrIyw==

array.prototype.reduce@^1.0.4:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/array.prototype.reduce/-/array.prototype.reduce-1.0.5.tgz#6b20b0daa9d9734dd6bc7ea66b5bbce395471eac"
  integrity sha512-kDdugMl7id9COE8R7MHF5jWk7Dqt/fs4Pv+JXoICnYwqpjjjbUurz6w5fT5IG6brLdJhv6/VoHB0H7oyIBXd+Q==
  dependencies:
    call-bind "^1.0.2"
    define-properties "^1.1.4"
    es-abstract "^1.20.4"
    es-array-method-boxes-properly "^1.0.0"
    is-string "^1.0.7"

asap@~2.0.3:
  version "2.0.6"
  resolved "https://registry.npmmirror.com/asap/-/asap-2.0.6.tgz#e50347611d7e690943208bbdafebcbc2fb866d46"
  integrity sha512-BSHWgDSAiKs50o2Re8ppvp3seVHXSRM44cdSsT9FfNEUUZLOGWVCsiWaRPWM1Znn+mqZ1OfVZ3z3DWEzSp7hRA==

at-least-node@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/at-least-node/-/at-least-node-1.0.0.tgz#602cd4b46e844ad4effc92a8011a3c46e0238dc2"
  integrity sha512-+q/t7Ekv1EDY2l6Gda6LLiX14rU9TV20Wa3ofeQmwPFZbOMo9DXrLbOjFaaclkXKWidIaopwAObQDqwWtGUjqg==

autoprefixer@^10.3.5, autoprefixer@^10.4.12:
  version "10.4.13"
  resolved "https://registry.npmmirror.com/autoprefixer/-/autoprefixer-10.4.13.tgz#b5136b59930209a321e9fa3dca2e7c4d223e83a8"
  integrity sha512-49vKpMqcZYsJjwotvt4+h/BCjJVnhGwcLpDt5xkcaOG3eLrG/HUYLagrihYsQ+qrIBgIzX1Rw7a6L8I/ZA1Atg==
  dependencies:
    browserslist "^4.21.4"
    caniuse-lite "^1.0.30001426"
    fraction.js "^4.2.0"
    normalize-range "^0.1.2"
    picocolors "^1.0.0"
    postcss-value-parser "^4.2.0"

axios@^0.25.0:
  version "0.25.0"
  resolved "https://registry.npmmirror.com/axios/-/axios-0.25.0.tgz#349cfbb31331a9b4453190791760a8d35b093e0a"
  integrity sha512-cD8FOb0tRH3uuEe6+evtAbgJtfxr7ly3fQjYcMcuPlgkwVS9xboaVIpcDV+cYQe+yGykgwZCs1pzjntcGa6l5g==
  dependencies:
    follow-redirects "^1.14.7"

babel-loader@^8.2.2:
  version "8.3.0"
  resolved "https://registry.npmmirror.com/babel-loader/-/babel-loader-8.3.0.tgz#124936e841ba4fe8176786d6ff28add1f134d6a8"
  integrity sha512-H8SvsMF+m9t15HNLMipppzkC+Y2Yq+v3SonZyU70RBL/h1gxPkH08Ot8pEE9Z4Kd+czyWJClmFS8qzIP9OZ04Q==
  dependencies:
    find-cache-dir "^3.3.1"
    loader-utils "^2.0.0"
    make-dir "^3.1.0"
    schema-utils "^2.6.5"

babel-plugin-apply-mdx-type-prop@1.6.22:
  version "1.6.22"
  resolved "https://registry.npmmirror.com/babel-plugin-apply-mdx-type-prop/-/babel-plugin-apply-mdx-type-prop-1.6.22.tgz#d216e8fd0de91de3f1478ef3231e05446bc8705b"
  integrity sha512-VefL+8o+F/DfK24lPZMtJctrCVOfgbqLAGZSkxwhazQv4VxPg3Za/i40fu22KR2m8eEda+IfSOlPLUSIiLcnCQ==
  dependencies:
    "@babel/helper-plugin-utils" "7.10.4"
    "@mdx-js/util" "1.6.22"

babel-plugin-dynamic-import-node@2.3.0:
  version "2.3.0"
  resolved "https://registry.npmmirror.com/babel-plugin-dynamic-import-node/-/babel-plugin-dynamic-import-node-2.3.0.tgz#f00f507bdaa3c3e3ff6e7e5e98d90a7acab96f7f"
  integrity sha512-o6qFkpeQEBxcqt0XYlWzAVxNCSCZdUgcR8IRlhD/8DylxjjO4foPcvTW0GGKa/cVt3rvxZ7o5ippJ+/0nvLhlQ==
  dependencies:
    object.assign "^4.1.0"

babel-plugin-extract-import-names@1.6.22:
  version "1.6.22"
  resolved "https://registry.npmmirror.com/babel-plugin-extract-import-names/-/babel-plugin-extract-import-names-1.6.22.tgz#de5f9a28eb12f3eb2578bf74472204e66d1a13dc"
  integrity sha512-yJ9BsJaISua7d8zNT7oRG1ZLBJCIdZ4PZqmH8qa9N5AK01ifk3fnkc98AXhtzE7UkfCsEumvoQWgoYLhOnJ7jQ==
  dependencies:
    "@babel/helper-plugin-utils" "7.10.4"

babel-plugin-polyfill-corejs2@^0.3.3:
  version "0.3.3"
  resolved "https://registry.npmmirror.com/babel-plugin-polyfill-corejs2/-/babel-plugin-polyfill-corejs2-0.3.3.tgz#5d1bd3836d0a19e1b84bbf2d9640ccb6f951c122"
  integrity sha512-8hOdmFYFSZhqg2C/JgLUQ+t52o5nirNwaWM2B9LWteozwIvM14VSwdsCAUET10qT+kmySAlseadmfeeSWFCy+Q==
  dependencies:
    "@babel/compat-data" "^7.17.7"
    "@babel/helper-define-polyfill-provider" "^0.3.3"
    semver "^6.1.1"

babel-plugin-polyfill-corejs3@^0.6.0:
  version "0.6.0"
  resolved "https://registry.npmmirror.com/babel-plugin-polyfill-corejs3/-/babel-plugin-polyfill-corejs3-0.6.0.tgz#56ad88237137eade485a71b52f72dbed57c6230a"
  integrity sha512-+eHqR6OPcBhJOGgsIar7xoAB1GcSwVUA3XjAd7HJNzOXT4wv6/H7KIdA/Nc60cvUlDbKApmqNvD1B1bzOt4nyA==
  dependencies:
    "@babel/helper-define-polyfill-provider" "^0.3.3"
    core-js-compat "^3.25.1"

babel-plugin-polyfill-regenerator@^0.4.1:
  version "0.4.1"
  resolved "https://registry.npmmirror.com/babel-plugin-polyfill-regenerator/-/babel-plugin-polyfill-regenerator-0.4.1.tgz#390f91c38d90473592ed43351e801a9d3e0fd747"
  integrity sha512-NtQGmyQDXjQqQ+IzRkBVwEOz9lQ4zxAQZgoAYEtU9dJjnl1Oc98qnN7jcp+bE7O7aYzVpavXE3/VKXNzUbh7aw==
  dependencies:
    "@babel/helper-define-polyfill-provider" "^0.3.3"

bail@^1.0.0:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/bail/-/bail-1.0.5.tgz#b6fa133404a392cbc1f8c4bf63f5953351e7a776"
  integrity sha512-xFbRxM1tahm08yHBP16MMjVUAvDaBMD38zsM9EMAUN61omwLmKlOpB/Zku5QkjZ8TZ4vn53pj+t518cH0S03RQ==

balanced-match@^1.0.0:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/balanced-match/-/balanced-match-1.0.2.tgz#e83e3a7e3f300b34cb9d87f615fa0cbf357690ee"
  integrity sha512-3oSeUO0TMV67hN1AmbXsK4yaqU7tjiHlbxRDZOpH0KW9+CeX4bRAaX0Anxt0tx2MrpRpWwQaPwIlISEJhYU5Pw==

base16@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/base16/-/base16-1.0.0.tgz#e297f60d7ec1014a7a971a39ebc8a98c0b681e70"
  integrity sha512-pNdYkNPiJUnEhnfXV56+sQy8+AaPcG3POZAUnwr4EeqCUZFz4u2PePbo3e5Gj4ziYPCWGUZT9RHisvJKnwFuBQ==

batch@0.6.1:
  version "0.6.1"
  resolved "https://registry.npmmirror.com/batch/-/batch-0.6.1.tgz#dc34314f4e679318093fc760272525f94bf25c16"
  integrity sha512-x+VAiMRL6UPkx+kudNvxTl6hB2XNNCG2r+7wixVfIYwu/2HKRXimwQyaumLjMveWvT2Hkd/cAJw+QBMfJ/EKVw==

big.js@^5.2.2:
  version "5.2.2"
  resolved "https://registry.npmmirror.com/big.js/-/big.js-5.2.2.tgz#65f0af382f578bcdc742bd9c281e9cb2d7768328"
  integrity sha512-vyL2OymJxmarO8gxMr0mhChsO9QGwhynfuu4+MHTAW6czfq9humCB7rKpUjDd9YUiDPU4mzpyupFSvOClAwbmQ==

binary-extensions@^2.0.0:
  version "2.2.0"
  resolved "https://registry.npmmirror.com/binary-extensions/-/binary-extensions-2.2.0.tgz#75f502eeaf9ffde42fc98829645be4ea76bd9e2d"
  integrity sha512-jDctJ/IVQbZoJykoeHbhXpOlNBqGNcwXJKJog42E5HDPUwQTSdjCHdihjj0DlnheQ7blbT6dHOafNAiS8ooQKA==

body-parser@1.20.1:
  version "1.20.1"
  resolved "https://registry.npmmirror.com/body-parser/-/body-parser-1.20.1.tgz#b1812a8912c195cd371a3ee5e66faa2338a5c668"
  integrity sha512-jWi7abTbYwajOytWCQc37VulmWiRae5RyTpaCyDcS5/lMdtwSz5lOpDE67srw/HYe35f1z3fDQw+3txg7gNtWw==
  dependencies:
    bytes "3.1.2"
    content-type "~1.0.4"
    debug "2.6.9"
    depd "2.0.0"
    destroy "1.2.0"
    http-errors "2.0.0"
    iconv-lite "0.4.24"
    on-finished "2.4.1"
    qs "6.11.0"
    raw-body "2.5.1"
    type-is "~1.6.18"
    unpipe "1.0.0"

bonjour-service@^1.0.11:
  version "1.0.14"
  resolved "https://registry.npmmirror.com/bonjour-service/-/bonjour-service-1.0.14.tgz#c346f5bc84e87802d08f8d5a60b93f758e514ee7"
  integrity sha512-HIMbgLnk1Vqvs6B4Wq5ep7mxvj9sGz5d1JJyDNSGNIdA/w2MCz6GTjWTdjqOJV1bEPj+6IkxDvWNFKEBxNt4kQ==
  dependencies:
    array-flatten "^2.1.2"
    dns-equal "^1.0.0"
    fast-deep-equal "^3.1.3"
    multicast-dns "^7.2.5"

boolbase@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/boolbase/-/boolbase-1.0.0.tgz#68dff5fbe60c51eb37725ea9e3ed310dcc1e776e"
  integrity sha512-JZOSA7Mo9sNGB8+UjSgzdLtokWAky1zbztM3WRLCbZ70/3cTANmQmOdR7y2g+J0e2WXywy1yS468tY+IruqEww==

boxen@^5.0.0, boxen@^5.0.1:
  version "5.1.2"
  resolved "https://registry.npmmirror.com/boxen/-/boxen-5.1.2.tgz#788cb686fc83c1f486dfa8a40c68fc2b831d2b50"
  integrity sha512-9gYgQKXx+1nP8mP7CzFyaUARhg7D3n1dF/FnErWmu9l6JvGpNUN278h0aSb+QjoiKSWG+iZ3uHrcqk0qrY9RQQ==
  dependencies:
    ansi-align "^3.0.0"
    camelcase "^6.2.0"
    chalk "^4.1.0"
    cli-boxes "^2.2.1"
    string-width "^4.2.2"
    type-fest "^0.20.2"
    widest-line "^3.1.0"
    wrap-ansi "^7.0.0"

brace-expansion@^1.1.7:
  version "1.1.11"
  resolved "https://registry.npmmirror.com/brace-expansion/-/brace-expansion-1.1.11.tgz#3c7fcbf529d87226f3d2f52b966ff5271eb441dd"
  integrity sha512-iCuPHDFgrHX7H2vEI/5xpz07zSHB00TpugqhmYtVmMO6518mCuRMoOYFldEBl0g187ufozdaHgWKcYFb61qGiA==
  dependencies:
    balanced-match "^1.0.0"
    concat-map "0.0.1"

braces@^3.0.2, braces@~3.0.2:
  version "3.0.2"
  resolved "https://registry.npmmirror.com/braces/-/braces-3.0.2.tgz#3454e1a462ee8d599e236df336cd9ea4f8afe107"
  integrity sha512-b8um+L1RzM3WDSzvhm6gIz1yfTbBt6YTlcEKAvsmqCZZFw46z626lVj9j1yEPW33H5H+lBQpZMP1k8l+78Ha0A==
  dependencies:
    fill-range "^7.0.1"

browserslist@^4.0.0, browserslist@^4.14.5, browserslist@^4.16.5, browserslist@^4.16.6, browserslist@^4.21.3, browserslist@^4.21.4:
  version "4.21.4"
  resolved "https://registry.npmmirror.com/browserslist/-/browserslist-4.21.4.tgz#e7496bbc67b9e39dd0f98565feccdcb0d4ff6987"
  integrity sha512-CBHJJdDmgjl3daYjN5Cp5kbTf1mUhZoS+beLklHIvkOWscs83YAhLlF3Wsh/lciQYAcbBJgTOD44VtG31ZM4Hw==
  dependencies:
    caniuse-lite "^1.0.30001400"
    electron-to-chromium "^1.4.251"
    node-releases "^2.0.6"
    update-browserslist-db "^1.0.9"

buble-jsx-only@^0.19.8:
  version "0.19.8"
  resolved "https://registry.npmmirror.com/buble-jsx-only/-/buble-jsx-only-0.19.8.tgz#6e3524aa0f1c523de32496ac9aceb9cc2b493867"
  integrity sha512-7AW19pf7PrKFnGTEDzs6u9+JZqQwM1VnLS19OlqYDhXomtFFknnoQJAPHeg84RMFWAvOhYrG7harizJNwUKJsA==
  dependencies:
    acorn "^6.1.1"
    acorn-dynamic-import "^4.0.0"
    acorn-jsx "^5.0.1"
    chalk "^2.4.2"
    magic-string "^0.25.3"
    minimist "^1.2.0"
    regexpu-core "^4.5.4"

buffer-from@^1.0.0:
  version "1.1.2"
  resolved "https://registry.npmmirror.com/buffer-from/-/buffer-from-1.1.2.tgz#2b146a6fd72e80b4f55d255f35ed59a3a9a41bd5"
  integrity sha512-E+XQCRwSbaaiChtv6k6Dwgc+bx+Bs6vuKJHHl5kox/BaKbhiXzqQOwK4cO22yElGp2OCmjwVhT3HmxgyPGnJfQ==

bytes@3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/bytes/-/bytes-3.0.0.tgz#d32815404d689699f85a4ea4fa8755dd13a96048"
  integrity sha512-pMhOfFDPiv9t5jjIXkHosWmkSyQbvsgEVNkz0ERHbuLh2T/7j4Mqqpz523Fe8MVY89KC6Sh/QfS2sM+SjgFDcw==

bytes@3.1.2:
  version "3.1.2"
  resolved "https://registry.npmmirror.com/bytes/-/bytes-3.1.2.tgz#8b0beeb98605adf1b128fa4386403c009e0221a5"
  integrity sha512-/Nf7TyzTx6S3yRJObOAV7956r8cr2+Oj8AC5dt8wSP3BQAoeX58NoHyCU8P8zGkNXStjTSi6fzO6F0pBdcYbEg==

cacheable-lookup@^5.0.3:
  version "5.0.4"
  resolved "https://registry.npmmirror.com/cacheable-lookup/-/cacheable-lookup-5.0.4.tgz#5a6b865b2c44357be3d5ebc2a467b032719a7005"
  integrity sha512-2/kNscPhpcxrOigMZzbiWF7dz8ilhb/nIHU3EyZiXWXpeq/au8qJ8VhdftMkty3n7Gj6HIGalQG8oiBNB3AJgA==

cacheable-request@^7.0.2:
  version "7.0.2"
  resolved "https://registry.npmmirror.com/cacheable-request/-/cacheable-request-7.0.2.tgz#ea0d0b889364a25854757301ca12b2da77f91d27"
  integrity sha512-pouW8/FmiPQbuGpkXQ9BAPv/Mo5xDGANgSNXzTzJ8DrKGuXOssM4wIQRjfanNRh3Yu5cfYPvcorqbhg2KIJtew==
  dependencies:
    clone-response "^1.0.2"
    get-stream "^5.1.0"
    http-cache-semantics "^4.0.0"
    keyv "^4.0.0"
    lowercase-keys "^2.0.0"
    normalize-url "^6.0.1"
    responselike "^2.0.0"

call-bind@^1.0.0, call-bind@^1.0.2:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/call-bind/-/call-bind-1.0.2.tgz#b1d4e89e688119c3c9a903ad30abb2f6a919be3c"
  integrity sha512-7O+FbCihrB5WGbFYesctwmTKae6rOiIzmz1icreWJ+0aA7LJfuqhEso2T9ncpcFtzMQtzXf2QGGueWJGTYsqrA==
  dependencies:
    function-bind "^1.1.1"
    get-intrinsic "^1.0.2"

callsites@^3.0.0:
  version "3.1.0"
  resolved "https://registry.npmmirror.com/callsites/-/callsites-3.1.0.tgz#b3630abd8943432f54b3f0519238e33cd7df2f73"
  integrity sha512-P8BjAsXvZS+VIDUI11hHCQEv74YT67YUi5JJFNWIqL235sBmjX4+qx9Muvls5ivyNENctx46xQLQ3aTuE7ssaQ==

camel-case@^4.1.2:
  version "4.1.2"
  resolved "https://registry.npmmirror.com/camel-case/-/camel-case-4.1.2.tgz#9728072a954f805228225a6deea6b38461e1bd5a"
  integrity sha512-gxGWBrTT1JuMx6R+o5PTXMmUnhnVzLQ9SNutD4YqKtI6ap897t3tKECYla6gCWEkplXnlNybEkZg9GEGxKFCgw==
  dependencies:
    pascal-case "^3.1.2"
    tslib "^2.0.3"

camelcase-css@2.0.1:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/camelcase-css/-/camelcase-css-2.0.1.tgz#ee978f6947914cc30c6b44741b6ed1df7f043fd5"
  integrity sha512-QOSvevhslijgYwRx6Rv7zKdMF8lbRmx+uQGx2+vDc+KI/eBnsy9kit5aj23AgGu3pa4t9AgwbnXWqS+iOY+2aA==

camelcase@^6.2.0:
  version "6.3.0"
  resolved "https://registry.npmmirror.com/camelcase/-/camelcase-6.3.0.tgz#5685b95eb209ac9c0c177467778c9c84df58ba9a"
  integrity sha512-Gmy6FhYlCY7uOElZUSbxo2UCDH8owEk996gkbrpsgGtrJLM3J7jGxl9Ic7Qwwj4ivOE5AWZWRMecDdF7hqGjFA==

caniuse-api@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/caniuse-api/-/caniuse-api-3.0.0.tgz#5e4d90e2274961d46291997df599e3ed008ee4c0"
  integrity sha512-bsTwuIg/BZZK/vreVTYYbSWoe2F+71P7K5QGEX+pT250DZbfU1MQ5prOKpPR+LL6uWKK3KMwMCAS74QB3Um1uw==
  dependencies:
    browserslist "^4.0.0"
    caniuse-lite "^1.0.0"
    lodash.memoize "^4.1.2"
    lodash.uniq "^4.5.0"

caniuse-lite@^1.0.0, caniuse-lite@^1.0.30001400, caniuse-lite@^1.0.30001426:
  version "1.0.30001430"
  resolved "https://registry.npmmirror.com/caniuse-lite/-/caniuse-lite-1.0.30001430.tgz#638a8ae00b5a8a97e66ff43733b2701f81b101fa"
  integrity sha512-IB1BXTZKPDVPM7cnV4iaKaHxckvdr/3xtctB3f7Hmenx3qYBhGtTZ//7EllK66aKXW98Lx0+7Yr0kxBtIt3tzg==

ccount@^1.0.0, ccount@^1.0.3:
  version "1.1.0"
  resolved "https://registry.npmmirror.com/ccount/-/ccount-1.1.0.tgz#246687debb6014735131be8abab2d93898f8d043"
  integrity sha512-vlNK021QdI7PNeiUh/lKkC/mNHHfV0m/Ad5JoI0TYtlBnJAslM/JIkm/tGC88bkLIwO6OQ5uV6ztS6kVAtCDlg==

chalk@^2.0.0, chalk@^2.4.1, chalk@^2.4.2:
  version "2.4.2"
  resolved "https://registry.npmmirror.com/chalk/-/chalk-2.4.2.tgz#cd42541677a54333cf541a49108c1432b44c9424"
  integrity sha512-Mti+f9lpJNcwF4tWV8/OrTTtF1gZi+f8FqlyAdouralcFWFQWF2+NgCHShjkCb+IFBLq9buZwE1xckQU4peSuQ==
  dependencies:
    ansi-styles "^3.2.1"
    escape-string-regexp "^1.0.5"
    supports-color "^5.3.0"

chalk@^4.1.0, chalk@^4.1.2:
  version "4.1.2"
  resolved "https://registry.npmmirror.com/chalk/-/chalk-4.1.2.tgz#aac4e2b7734a740867aeb16bf02aad556a1e7a01"
  integrity sha512-oKnbhFyRIXpUuez8iBMmyEa4nbj4IOQyuhc/wy9kY7/WVPcwIO9VA668Pu8RkO7+0G76SLROeyw9CpQ061i4mA==
  dependencies:
    ansi-styles "^4.1.0"
    supports-color "^7.1.0"

character-entities-legacy@^1.0.0:
  version "1.1.4"
  resolved "https://registry.npmmirror.com/character-entities-legacy/-/character-entities-legacy-1.1.4.tgz#94bc1845dce70a5bb9d2ecc748725661293d8fc1"
  integrity sha512-3Xnr+7ZFS1uxeiUDvV02wQ+QDbc55o97tIV5zHScSPJpcLm/r0DFPcoY3tYRp+VZukxuMeKgXYmsXQHO05zQeA==

character-entities@^1.0.0:
  version "1.2.4"
  resolved "https://registry.npmmirror.com/character-entities/-/character-entities-1.2.4.tgz#e12c3939b7eaf4e5b15e7ad4c5e28e1d48c5b16b"
  integrity sha512-iBMyeEHxfVnIakwOuDXpVkc54HijNgCyQB2w0VfGQThle6NXn50zU6V/u+LDhxHcDUPojn6Kpga3PTAD8W1bQw==

character-reference-invalid@^1.0.0:
  version "1.1.4"
  resolved "https://registry.npmmirror.com/character-reference-invalid/-/character-reference-invalid-1.1.4.tgz#083329cda0eae272ab3dbbf37e9a382c13af1560"
  integrity sha512-mKKUkUbhPpQlCOfIuZkvSEgktjPFIsZKRRbC6KWVEMvlzblj3i3asQv5ODsrwt0N3pHAEvjP8KTQPHkp0+6jOg==

cheerio-select@^2.1.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/cheerio-select/-/cheerio-select-2.1.0.tgz#4d8673286b8126ca2a8e42740d5e3c4884ae21b4"
  integrity sha512-9v9kG0LvzrlcungtnJtpGNxY+fzECQKhK4EGJX2vByejiMX84MFNQw4UxPJl3bFbTMw+Dfs37XaIkCwTZfLh4g==
  dependencies:
    boolbase "^1.0.0"
    css-select "^5.1.0"
    css-what "^6.1.0"
    domelementtype "^2.3.0"
    domhandler "^5.0.3"
    domutils "^3.0.1"

cheerio@^1.0.0-rc.3:
  version "1.0.0-rc.12"
  resolved "https://registry.npmmirror.com/cheerio/-/cheerio-1.0.0-rc.12.tgz#788bf7466506b1c6bf5fae51d24a2c4d62e47683"
  integrity sha512-VqR8m68vM46BNnuZ5NtnGBKIE/DfN0cRIzg9n40EIq9NOv90ayxLBXA8fXC5gquFRGJSTRqBq25Jt2ECLR431Q==
  dependencies:
    cheerio-select "^2.1.0"
    dom-serializer "^2.0.0"
    domhandler "^5.0.3"
    domutils "^3.0.1"
    htmlparser2 "^8.0.1"
    parse5 "^7.0.0"
    parse5-htmlparser2-tree-adapter "^7.0.0"

chokidar@^3.4.2, chokidar@^3.5.2, chokidar@^3.5.3:
  version "3.5.3"
  resolved "https://registry.npmmirror.com/chokidar/-/chokidar-3.5.3.tgz#1cf37c8707b932bd1af1ae22c0432e2acd1903bd"
  integrity sha512-Dr3sfKRP6oTcjf2JmUmFJfeVMvXBdegxB0iVQ5eb2V10uFJUCAS8OByZdVAyVb8xXNz3GjjTgj9kLWsZTqE6kw==
  dependencies:
    anymatch "~3.1.2"
    braces "~3.0.2"
    glob-parent "~5.1.2"
    is-binary-path "~2.1.0"
    is-glob "~4.0.1"
    normalize-path "~3.0.0"
    readdirp "~3.6.0"
  optionalDependencies:
    fsevents "~2.3.2"

chrome-trace-event@^1.0.2:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/chrome-trace-event/-/chrome-trace-event-1.0.3.tgz#1015eced4741e15d06664a957dbbf50d041e26ac"
  integrity sha512-p3KULyQg4S7NIHixdwbGX+nFHkoBiA4YQmyWtjb8XngSKV124nJmRysgAeujbUVb15vh+RvFUfCPqU7rXk+hZg==

ci-info@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/ci-info/-/ci-info-2.0.0.tgz#67a9e964be31a51e15e5010d58e6f12834002f46"
  integrity sha512-5tK7EtrZ0N+OLFMthtqOj4fI2Jeb88C4CAZPu25LDVUgXJ0A3Js4PMGqrn0JU1W0Mh1/Z8wZzYPxqUrXeBboCQ==

ci-info@^3.1.1:
  version "3.5.0"
  resolved "https://registry.npmmirror.com/ci-info/-/ci-info-3.5.0.tgz#bfac2a29263de4c829d806b1ab478e35091e171f"
  integrity sha512-yH4RezKOGlOhxkmhbeNuC4eYZKAUsEaGtBuBzDDP1eFUKiccDWzBABxBfOx31IDwDIXMTxWuwAxUGModvkbuVw==

clean-css@^5.1.5, clean-css@^5.2.2:
  version "5.3.1"
  resolved "https://registry.npmmirror.com/clean-css/-/clean-css-5.3.1.tgz#d0610b0b90d125196a2894d35366f734e5d7aa32"
  integrity sha512-lCr8OHhiWCTw4v8POJovCoh4T7I9U11yVsPjMWWnnMmp9ZowCxyad1Pathle/9HjaDp+fdQKjO9fQydE6RHTZg==
  dependencies:
    source-map "~0.6.0"

clean-stack@^2.0.0:
  version "2.2.0"
  resolved "https://registry.npmmirror.com/clean-stack/-/clean-stack-2.2.0.tgz#ee8472dbb129e727b31e8a10a427dee9dfe4008b"
  integrity sha512-4diC9HaTE+KRAMWhDhrGOECgWZxoevMc5TlkObMqNSsVU62PYzXZ/SMTjzyGAFF1YusgxGcSWTEXBhp0CPwQ1A==

cli-boxes@^2.2.1:
  version "2.2.1"
  resolved "https://registry.npmmirror.com/cli-boxes/-/cli-boxes-2.2.1.tgz#ddd5035d25094fce220e9cab40a45840a440318f"
  integrity sha512-y4coMcylgSCdVinjiDBuR8PCC2bLjyGTwEmPb9NHR/QaNU6EUOXcTY/s6VjGMD6ENSEaeQYHCY0GNGS5jfMwPw==

clone-deep@^4.0.1:
  version "4.0.1"
  resolved "https://registry.npmmirror.com/clone-deep/-/clone-deep-4.0.1.tgz#c19fd9bdbbf85942b4fd979c84dcf7d5f07c2387"
  integrity sha512-neHB9xuzh/wk0dIHweyAXv2aPGZIVk3pLMe+/RNzINf17fe0OG96QroktYAUm7SM1PBnzTabaLboqqxDyMU+SQ==
  dependencies:
    is-plain-object "^2.0.4"
    kind-of "^6.0.2"
    shallow-clone "^3.0.0"

clone-response@^1.0.2:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/clone-response/-/clone-response-1.0.3.tgz#af2032aa47816399cf5f0a1d0db902f517abb8c3"
  integrity sha512-ROoL94jJH2dUVML2Y/5PEDNaSHgeOdSDicUyS7izcF63G6sTc/FTjLub4b8Il9S8S0beOfYt0TaA5qvFK+w0wA==
  dependencies:
    mimic-response "^1.0.0"

clsx@^1.1.1:
  version "1.2.1"
  resolved "https://registry.npmmirror.com/clsx/-/clsx-1.2.1.tgz#0ddc4a20a549b59c93a4116bb26f5294ca17dc12"
  integrity sha512-EcR6r5a8bj6pu3ycsa/E/cKVGuTgZJZdsyUYHOksG/UHIiKfjxzRxYJpyVBwYaQeOvghal9fcc4PidlgzugAQg==

coa@^2.0.2:
  version "2.0.2"
  resolved "https://registry.npmmirror.com/coa/-/coa-2.0.2.tgz#43f6c21151b4ef2bf57187db0d73de229e3e7ec3"
  integrity sha512-q5/jG+YQnSy4nRTV4F7lPepBJZ8qBNJJDBuJdoejDyLXgmL7IEo+Le2JDZudFTFt7mrCqIRaSjws4ygRCTCAXA==
  dependencies:
    "@types/q" "^1.5.1"
    chalk "^2.4.1"
    q "^1.1.2"

collapse-white-space@^1.0.2:
  version "1.0.6"
  resolved "https://registry.npmmirror.com/collapse-white-space/-/collapse-white-space-1.0.6.tgz#e63629c0016665792060dbbeb79c42239d2c5287"
  integrity sha512-jEovNnrhMuqyCcjfEJA56v0Xq8SkIoPKDyaHahwo3POf4qcSXqMYuwNcOTzp74vTsR9Tn08z4MxWqAhcekogkQ==

color-convert@^1.9.0:
  version "1.9.3"
  resolved "https://registry.npmmirror.com/color-convert/-/color-convert-1.9.3.tgz#bb71850690e1f136567de629d2d5471deda4c1e8"
  integrity sha512-QfAUtd+vFdAtFQcC8CCyYt1fYWxSqAiK2cSD6zDB8N3cpsEBAvRxp9zOGg6G/SHHJYAT88/az/IuDGALsNVbGg==
  dependencies:
    color-name "1.1.3"

color-convert@^2.0.1:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/color-convert/-/color-convert-2.0.1.tgz#72d3a68d598c9bdb3af2ad1e84f21d896abd4de3"
  integrity sha512-RRECPsj7iu/xb5oKYcsFHSppFNnsj/52OVTRKb4zP5onXwVF3zVmmToNcOfGC+CRDpfK/U584fMg38ZHCaElKQ==
  dependencies:
    color-name "~1.1.4"

color-name@1.1.3:
  version "1.1.3"
  resolved "https://registry.npmmirror.com/color-name/-/color-name-1.1.3.tgz#a7d0558bd89c42f795dd42328f740831ca53bc25"
  integrity sha512-72fSenhMw2HZMTVHeCA9KCmpEIbzWiQsjN+BHcBbS9vr1mtt+vJjPdksIBNUmKAW8TFUDPJK5SUU3QhE9NEXDw==

color-name@~1.1.4:
  version "1.1.4"
  resolved "https://registry.npmmirror.com/color-name/-/color-name-1.1.4.tgz#c2a09a87acbde69543de6f63fa3995c826c536a2"
  integrity sha512-dOy+3AuW3a2wNbZHIuMZpTcgjGuLU/uBL/ubcZF9OXbDo8ff4O8yVp5Bf0efS8uEoYo5q4Fx7dY9OgQGXgAsQA==

colord@^2.9.1:
  version "2.9.3"
  resolved "https://registry.npmmirror.com/colord/-/colord-2.9.3.tgz#4f8ce919de456f1d5c1c368c307fe20f3e59fb43"
  integrity sha512-jeC1axXpnb0/2nn/Y1LPuLdgXBLH7aDcHu4KEKfqw3CUhX7ZpfBSlPKyqXE6btIgEzfWtrX3/tyBCaCvXvMkOw==

colorette@^2.0.10:
  version "2.0.19"
  resolved "https://registry.npmmirror.com/colorette/-/colorette-2.0.19.tgz#cdf044f47ad41a0f4b56b3a0d5b4e6e1a2d5a798"
  integrity sha512-3tlv/dIP7FWvj3BsbHrGLJ6l/oKh1O3TcgBqMn+yyCagOxc23fyzDS6HypQbgxWbkpDnf52p1LuR4eWDQ/K9WQ==

combine-promises@^1.1.0:
  version "1.1.0"
  resolved "https://registry.npmmirror.com/combine-promises/-/combine-promises-1.1.0.tgz#72db90743c0ca7aab7d0d8d2052fd7b0f674de71"
  integrity sha512-ZI9jvcLDxqwaXEixOhArm3r7ReIivsXkpbyEWyeOhzz1QS0iSgBPnWvEqvIQtYyamGCYA88gFhmUrs9hrrQ0pg==

comma-separated-tokens@^1.0.0:
  version "1.0.8"
  resolved "https://registry.npmmirror.com/comma-separated-tokens/-/comma-separated-tokens-1.0.8.tgz#632b80b6117867a158f1080ad498b2fbe7e3f5ea"
  integrity sha512-GHuDRO12Sypu2cV70d1dkA2EUmXHgntrzbpvOB+Qy+49ypNfGgFQIC2fhhXbnyrJRynDCAARsT7Ou0M6hirpfw==

commander@^2.19.0, commander@^2.20.0:
  version "2.20.3"
  resolved "https://registry.npmmirror.com/commander/-/commander-2.20.3.tgz#fd485e84c03eb4881c20722ba48035e8531aeb33"
  integrity sha512-GpVkmM8vF2vQUkj2LvZmD35JxeJOLCwJ9cUkugyk2nuhbv3+mJvpLYYt+0+USMxE+oj+ey/lJEnhZw75x/OMcQ==

commander@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/commander/-/commander-5.1.0.tgz#46abbd1652f8e059bddaef99bbdcb2ad9cf179ae"
  integrity sha512-P0CysNDQ7rtVw4QIQtm+MRxV66vKFSvlsQvGYXZWR3qFU0jlMKHZZZgw8e+8DSah4UDKMqnknRDQz+xuQXQ/Zg==

commander@^7.2.0:
  version "7.2.0"
  resolved "https://registry.npmmirror.com/commander/-/commander-7.2.0.tgz#a36cb57d0b501ce108e4d20559a150a391d97ab7"
  integrity sha512-QrWXB+ZQSVPmIWIhtEO9H+gwHaMGYiF5ChvoJ+K9ZGHG/sVsa6yiesAD1GC/x46sET00Xlwo1u49RVVVzvcSkw==

commander@^8.3.0:
  version "8.3.0"
  resolved "https://registry.npmmirror.com/commander/-/commander-8.3.0.tgz#4837ea1b2da67b9c616a67afbb0fafee567bca66"
  integrity sha512-OkTL9umf+He2DZkUq8f8J9of7yL6RJKI24dVITBmNfZBmri9zYZQrKkuXiKhyfPSu8tUhnVBB1iKXevvnlR4Ww==

commondir@^1.0.1:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/commondir/-/commondir-1.0.1.tgz#ddd800da0c66127393cca5950ea968a3aaf1253b"
  integrity sha512-W9pAhw0ja1Edb5GVdIF1mjZw/ASI0AlShXM83UUGe2DVr5TdAPEA1OA8m/g8zWp9x6On7gqufY+FatDbC3MDQg==

compressible@~2.0.16:
  version "2.0.18"
  resolved "https://registry.npmmirror.com/compressible/-/compressible-2.0.18.tgz#af53cca6b070d4c3c0750fbd77286a6d7cc46fba"
  integrity sha512-AF3r7P5dWxL8MxyITRMlORQNaOA2IkAFaTr4k7BUumjPtRpGDTZpl0Pb1XCO6JeDCBdp126Cgs9sMxqSjgYyRg==
  dependencies:
    mime-db ">= 1.43.0 < 2"

compression@^1.7.4:
  version "1.7.4"
  resolved "https://registry.npmmirror.com/compression/-/compression-1.7.4.tgz#95523eff170ca57c29a0ca41e6fe131f41e5bb8f"
  integrity sha512-jaSIDzP9pZVS4ZfQ+TzvtiWhdpFhE2RDHz8QJkpX9SIpLq88VueF5jJw6t+6CUQcAoA6t+x89MLrWAqpfDE8iQ==
  dependencies:
    accepts "~1.3.5"
    bytes "3.0.0"
    compressible "~2.0.16"
    debug "2.6.9"
    on-headers "~1.0.2"
    safe-buffer "5.1.2"
    vary "~1.1.2"

concat-map@0.0.1:
  version "0.0.1"
  resolved "https://registry.npmmirror.com/concat-map/-/concat-map-0.0.1.tgz#d8a96bd77fd68df7793a73036a3ba0d5405d477b"
  integrity sha512-/Srv4dswyQNBfohGpz9o6Yb3Gz3SrUDqBH5rTuhGR7ahtlbYKnVxw2bCFMRljaA7EXHaXZ8wsHdodFvbkhKmqg==

configstore@^5.0.1:
  version "5.0.1"
  resolved "https://registry.npmmirror.com/configstore/-/configstore-5.0.1.tgz#d365021b5df4b98cdd187d6a3b0e3f6a7cc5ed96"
  integrity sha512-aMKprgk5YhBNyH25hj8wGt2+D52Sw1DRRIzqBwLp2Ya9mFmY8KPvvtvmna8SxVR9JMZ4kzMD68N22vlaRpkeFA==
  dependencies:
    dot-prop "^5.2.0"
    graceful-fs "^4.1.2"
    make-dir "^3.0.0"
    unique-string "^2.0.0"
    write-file-atomic "^3.0.0"
    xdg-basedir "^4.0.0"

connect-history-api-fallback@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/connect-history-api-fallback/-/connect-history-api-fallback-2.0.0.tgz#647264845251a0daf25b97ce87834cace0f5f1c8"
  integrity sha512-U73+6lQFmfiNPrYbXqr6kZ1i1wiRqXnp2nhMsINseWXO8lDau0LGEffJ8kQi4EjLZympVgRdvqjAgiZ1tgzDDA==

consola@^2.15.3:
  version "2.15.3"
  resolved "https://registry.npmmirror.com/consola/-/consola-2.15.3.tgz#2e11f98d6a4be71ff72e0bdf07bd23e12cb61550"
  integrity sha512-9vAdYbHj6x2fLKC4+oPH0kFzY/orMZyG2Aj+kNylHxKGJ/Ed4dpNyAQYwJOdqO4zdM7XpVHmyejQDcQHrnuXbw==

content-disposition@0.5.2:
  version "0.5.2"
  resolved "https://registry.npmmirror.com/content-disposition/-/content-disposition-0.5.2.tgz#0cf68bb9ddf5f2be7961c3a85178cb85dba78cb4"
  integrity sha512-kRGRZw3bLlFISDBgwTSA1TMBFN6J6GWDeubmDE3AF+3+yXL8hTWv8r5rkLbqYXY4RjPk/EzHnClI3zQf1cFmHA==

content-disposition@0.5.4:
  version "0.5.4"
  resolved "https://registry.npmmirror.com/content-disposition/-/content-disposition-0.5.4.tgz#8b82b4efac82512a02bb0b1dcec9d2c5e8eb5bfe"
  integrity sha512-FveZTNuGw04cxlAiWbzi6zTAL/lhehaWbTtgluJh4/E95DqMwTmha3KZN1aAWA8cFIhHzMZUvLevkw5Rqk+tSQ==
  dependencies:
    safe-buffer "5.2.1"

content-type@~1.0.4:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/content-type/-/content-type-1.0.4.tgz#e138cc75e040c727b1966fe5e5f8c9aee256fe3b"
  integrity sha512-hIP3EEPs8tB9AT1L+NUqtwOAps4mk2Zob89MWXMHjHWg9milF/j4osnnQLXBCBFBk/tvIG/tUc9mOUJiPBhPXA==

convert-source-map@^1.7.0:
  version "1.9.0"
  resolved "https://registry.npmmirror.com/convert-source-map/-/convert-source-map-1.9.0.tgz#7faae62353fb4213366d0ca98358d22e8368b05f"
  integrity sha512-ASFBup0Mz1uyiIjANan1jzLQami9z1PoYSZCiiYW2FczPbenXc45FZdBZLzOT+r6+iciuEModtmCti+hjaAk0A==

cookie-signature@1.0.6:
  version "1.0.6"
  resolved "https://registry.npmmirror.com/cookie-signature/-/cookie-signature-1.0.6.tgz#e303a882b342cc3ee8ca513a79999734dab3ae2c"
  integrity sha512-QADzlaHc8icV8I7vbaJXJwod9HWYp8uCqf1xa4OfNu1T7JVxQIrUgOWtHdNDtPiywmFbiS12VjotIXLrKM3orQ==

cookie@0.5.0:
  version "0.5.0"
  resolved "https://registry.npmmirror.com/cookie/-/cookie-0.5.0.tgz#d1f5d71adec6558c58f389987c366aa47e994f8b"
  integrity sha512-YZ3GUyn/o8gfKJlnlX7g7xq4gyO6OSuhGPKaaGssGB2qgDUS0gPgtTvoyZLTt9Ab6dC4hfc9dV5arkvc/OCmrw==

copy-text-to-clipboard@^3.0.1:
  version "3.0.1"
  resolved "https://registry.npmmirror.com/copy-text-to-clipboard/-/copy-text-to-clipboard-3.0.1.tgz#8cbf8f90e0a47f12e4a24743736265d157bce69c"
  integrity sha512-rvVsHrpFcL4F2P8ihsoLdFHmd404+CMg71S756oRSeQgqk51U3kicGdnvfkrxva0xXH92SjGS62B0XIJsbh+9Q==

copy-webpack-plugin@^9.0.1:
  version "9.1.0"
  resolved "https://registry.npmmirror.com/copy-webpack-plugin/-/copy-webpack-plugin-9.1.0.tgz#2d2c460c4c4695ec0a58afb2801a1205256c4e6b"
  integrity sha512-rxnR7PaGigJzhqETHGmAcxKnLZSR5u1Y3/bcIv/1FnqXedcL/E2ewK7ZCNrArJKCiSv8yVXhTqetJh8inDvfsA==
  dependencies:
    fast-glob "^3.2.7"
    glob-parent "^6.0.1"
    globby "^11.0.3"
    normalize-path "^3.0.0"
    schema-utils "^3.1.1"
    serialize-javascript "^6.0.0"

core-js-compat@^3.25.1:
  version "3.26.0"
  resolved "https://registry.npmmirror.com/core-js-compat/-/core-js-compat-3.26.0.tgz#94e2cf8ba3e63800c4956ea298a6473bc9d62b44"
  integrity sha512-piOX9Go+Z4f9ZiBFLnZ5VrOpBl0h7IGCkiFUN11QTe6LjAvOT3ifL/5TdoizMh99hcGy5SoLyWbapIY/PIb/3A==
  dependencies:
    browserslist "^4.21.4"

core-js-pure@^3.25.1:
  version "3.26.0"
  resolved "https://registry.npmmirror.com/core-js-pure/-/core-js-pure-3.26.0.tgz#7ad8a5dd7d910756f3124374b50026e23265ca9a"
  integrity sha512-LiN6fylpVBVwT8twhhluD9TzXmZQQsr2I2eIKtWNbZI1XMfBT7CV18itaN6RA7EtQd/SDdRx/wzvAShX2HvhQA==

core-js@^3.18.0:
  version "3.26.0"
  resolved "https://registry.npmmirror.com/core-js/-/core-js-3.26.0.tgz#a516db0ed0811be10eac5d94f3b8463d03faccfe"
  integrity sha512-+DkDrhoR4Y0PxDz6rurahuB+I45OsEUv8E1maPTB6OuHRohMMcznBq9TMpdpDMm/hUPob/mJJS3PqgbHpMTQgw==

core-util-is@~1.0.0:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/core-util-is/-/core-util-is-1.0.3.tgz#a6042d3634c2b27e9328f837b965fac83808db85"
  integrity sha512-ZQBvi1DcpJ4GDqanjucZ2Hj3wEO5pZDS89BWbkcrvdxksJorwUDDZamX9ldFkp9aw2lmBDLgkObEA4DWNJ9FYQ==

cosmiconfig@^6.0.0:
  version "6.0.0"
  resolved "https://registry.npmmirror.com/cosmiconfig/-/cosmiconfig-6.0.0.tgz#da4fee853c52f6b1e6935f41c1a2fc50bd4a9982"
  integrity sha512-xb3ZL6+L8b9JLLCx3ZdoZy4+2ECphCMo2PwqgP1tlfVq6M6YReyzBJtvWWtbDSpNr9hn96pkCiZqUcFEc+54Qg==
  dependencies:
    "@types/parse-json" "^4.0.0"
    import-fresh "^3.1.0"
    parse-json "^5.0.0"
    path-type "^4.0.0"
    yaml "^1.7.2"

cosmiconfig@^7.0.0, cosmiconfig@^7.0.1:
  version "7.0.1"
  resolved "https://registry.npmmirror.com/cosmiconfig/-/cosmiconfig-7.0.1.tgz#714d756522cace867867ccb4474c5d01bbae5d6d"
  integrity sha512-a1YWNUV2HwGimB7dU2s1wUMurNKjpx60HxBB6xUM8Re+2s1g1IIfJvFR0/iCF+XHdE0GMTKTuLR32UQff4TEyQ==
  dependencies:
    "@types/parse-json" "^4.0.0"
    import-fresh "^3.2.1"
    parse-json "^5.0.0"
    path-type "^4.0.0"
    yaml "^1.10.0"

cross-fetch@^3.1.5:
  version "3.1.5"
  resolved "https://registry.npmmirror.com/cross-fetch/-/cross-fetch-3.1.5.tgz#e1389f44d9e7ba767907f7af8454787952ab534f"
  integrity sha512-lvb1SBsI0Z7GDwmuid+mU3kWVBwTVUbe7S0H52yaaAdQOXq2YktTCZdlAcNKFzE6QtRz0snpw9bNiPeOIkkQvw==
  dependencies:
    node-fetch "2.6.7"

cross-spawn@^7.0.3:
  version "7.0.3"
  resolved "https://registry.npmmirror.com/cross-spawn/-/cross-spawn-7.0.3.tgz#f73a85b9d5d41d045551c177e2882d4ac85728a6"
  integrity sha512-iRDPJKUPVEND7dHPO8rkbOnPpyDygcDFtWjpeWNCgy8WP2rXcxXL8TskReQl6OrB2G7+UJrags1q15Fudc7G6w==
  dependencies:
    path-key "^3.1.0"
    shebang-command "^2.0.0"
    which "^2.0.1"

crypto-random-string@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/crypto-random-string/-/crypto-random-string-2.0.0.tgz#ef2a7a966ec11083388369baa02ebead229b30d5"
  integrity sha512-v1plID3y9r/lPhviJ1wrXpLeyUIGAZ2SHNYTEapm7/8A9nLPoyvVp3RK/EPFqn5kEznyWgYZNsRtYYIWbuG8KA==

css-declaration-sorter@^6.3.1:
  version "6.3.1"
  resolved "https://registry.npmmirror.com/css-declaration-sorter/-/css-declaration-sorter-6.3.1.tgz#be5e1d71b7a992433fb1c542c7a1b835e45682ec"
  integrity sha512-fBffmak0bPAnyqc/HO8C3n2sHrp9wcqQz6ES9koRF2/mLOVAx9zIQ3Y7R29sYCteTPqMCwns4WYQoCX91Xl3+w==

css-loader@^5.1.1:
  version "5.2.7"
  resolved "https://registry.npmmirror.com/css-loader/-/css-loader-5.2.7.tgz#9b9f111edf6fb2be5dc62525644cbc9c232064ae"
  integrity sha512-Q7mOvpBNBG7YrVGMxRxcBJZFL75o+cH2abNASdibkj/fffYD8qWbInZrD0S9ccI6vZclF3DsHE7njGlLtaHbhg==
  dependencies:
    icss-utils "^5.1.0"
    loader-utils "^2.0.0"
    postcss "^8.2.15"
    postcss-modules-extract-imports "^3.0.0"
    postcss-modules-local-by-default "^4.0.0"
    postcss-modules-scope "^3.0.0"
    postcss-modules-values "^4.0.0"
    postcss-value-parser "^4.1.0"
    schema-utils "^3.0.0"
    semver "^7.3.5"

css-minimizer-webpack-plugin@^3.0.2:
  version "3.4.1"
  resolved "https://registry.npmmirror.com/css-minimizer-webpack-plugin/-/css-minimizer-webpack-plugin-3.4.1.tgz#ab78f781ced9181992fe7b6e4f3422e76429878f"
  integrity sha512-1u6D71zeIfgngN2XNRJefc/hY7Ybsxd74Jm4qngIXyUEk7fss3VUzuHxLAq/R8NAba4QU9OUSaMZlbpRc7bM4Q==
  dependencies:
    cssnano "^5.0.6"
    jest-worker "^27.0.2"
    postcss "^8.3.5"
    schema-utils "^4.0.0"
    serialize-javascript "^6.0.0"
    source-map "^0.6.1"

css-select-base-adapter@^0.1.1:
  version "0.1.1"
  resolved "https://registry.npmmirror.com/css-select-base-adapter/-/css-select-base-adapter-0.1.1.tgz#3b2ff4972cc362ab88561507a95408a1432135d7"
  integrity sha512-jQVeeRG70QI08vSTwf1jHxp74JoZsr2XSgETae8/xC8ovSnL2WF87GTLO86Sbwdt2lK4Umg4HnnwMO4YF3Ce7w==

css-select@^2.0.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/css-select/-/css-select-2.1.0.tgz#6a34653356635934a81baca68d0255432105dbef"
  integrity sha512-Dqk7LQKpwLoH3VovzZnkzegqNSuAziQyNZUcrdDM401iY+R5NkGBXGmtO05/yaXQziALuPogeG0b7UAgjnTJTQ==
  dependencies:
    boolbase "^1.0.0"
    css-what "^3.2.1"
    domutils "^1.7.0"
    nth-check "^1.0.2"

css-select@^4.1.3:
  version "4.3.0"
  resolved "https://registry.npmmirror.com/css-select/-/css-select-4.3.0.tgz#db7129b2846662fd8628cfc496abb2b59e41529b"
  integrity sha512-wPpOYtnsVontu2mODhA19JrqWxNsfdatRKd64kmpRbQgh1KtItko5sTnEpPdpSaJszTOhEMlF/RPz28qj4HqhQ==
  dependencies:
    boolbase "^1.0.0"
    css-what "^6.0.1"
    domhandler "^4.3.1"
    domutils "^2.8.0"
    nth-check "^2.0.1"

css-select@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/css-select/-/css-select-5.1.0.tgz#b8ebd6554c3637ccc76688804ad3f6a6fdaea8a6"
  integrity sha512-nwoRF1rvRRnnCqqY7updORDsuqKzqYJ28+oSMaJMMgOauh3fvwHqMS7EZpIPqK8GL+g9mKxF1vP/ZjSeNjEVHg==
  dependencies:
    boolbase "^1.0.0"
    css-what "^6.1.0"
    domhandler "^5.0.2"
    domutils "^3.0.1"
    nth-check "^2.0.1"

css-tree@1.0.0-alpha.37:
  version "1.0.0-alpha.37"
  resolved "https://registry.npmmirror.com/css-tree/-/css-tree-1.0.0-alpha.37.tgz#98bebd62c4c1d9f960ec340cf9f7522e30709a22"
  integrity sha512-DMxWJg0rnz7UgxKT0Q1HU/L9BeJI0M6ksor0OgqOnF+aRCDWg/N2641HmVyU9KVIu0OVVWOb2IpC9A+BJRnejg==
  dependencies:
    mdn-data "2.0.4"
    source-map "^0.6.1"

css-tree@^1.1.2, css-tree@^1.1.3:
  version "1.1.3"
  resolved "https://registry.npmmirror.com/css-tree/-/css-tree-1.1.3.tgz#eb4870fb6fd7707327ec95c2ff2ab09b5e8db91d"
  integrity sha512-tRpdppF7TRazZrjJ6v3stzv93qxRcSsFmW6cX0Zm2NVKpxE1WV1HblnghVv9TreireHkqI/VDEsfolRF1p6y7Q==
  dependencies:
    mdn-data "2.0.14"
    source-map "^0.6.1"

css-what@^3.2.1:
  version "3.4.2"
  resolved "https://registry.npmmirror.com/css-what/-/css-what-3.4.2.tgz#ea7026fcb01777edbde52124e21f327e7ae950e4"
  integrity sha512-ACUm3L0/jiZTqfzRM3Hi9Q8eZqd6IK37mMWPLz9PJxkLWllYeRf+EHUSHYEtFop2Eqytaq1FizFVh7XfBnXCDQ==

css-what@^6.0.1, css-what@^6.1.0:
  version "6.1.0"
  resolved "https://registry.npmmirror.com/css-what/-/css-what-6.1.0.tgz#fb5effcf76f1ddea2c81bdfaa4de44e79bac70f4"
  integrity sha512-HTUrgRJ7r4dsZKU6GjmpfRK1O76h97Z8MfS1G0FozR+oF2kG6Vfe8JE6zwrkbxigziPHinCJ+gCPjA9EaBDtRw==

cssesc@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/cssesc/-/cssesc-3.0.0.tgz#37741919903b868565e1c09ea747445cd18983ee"
  integrity sha512-/Tb/JcjK111nNScGob5MNtsntNM1aCNUDipB/TkwZFhyDrrE47SOx/18wF2bbjgc3ZzCSKW1T5nt5EbFoAz/Vg==

cssnano-preset-advanced@^5.1.4:
  version "5.3.9"
  resolved "https://registry.npmmirror.com/cssnano-preset-advanced/-/cssnano-preset-advanced-5.3.9.tgz#99e1cdf81a467a5e6c366cfc6d874a166c4d9a67"
  integrity sha512-njnh4pp1xCsibJcEHnWZb4EEzni0ePMqPuPNyuWT4Z+YeXmsgqNuTPIljXFEXhxGsWs9183JkXgHxc1TcsahIg==
  dependencies:
    autoprefixer "^10.4.12"
    cssnano-preset-default "^5.2.13"
    postcss-discard-unused "^5.1.0"
    postcss-merge-idents "^5.1.1"
    postcss-reduce-idents "^5.2.0"
    postcss-zindex "^5.1.0"

cssnano-preset-default@^5.2.13:
  version "5.2.13"
  resolved "https://registry.npmmirror.com/cssnano-preset-default/-/cssnano-preset-default-5.2.13.tgz#e7353b0c57975d1bdd97ac96e68e5c1b8c68e990"
  integrity sha512-PX7sQ4Pb+UtOWuz8A1d+Rbi+WimBIxJTRyBdgGp1J75VU0r/HFQeLnMYgHiCAp6AR4rqrc7Y4R+1Rjk3KJz6DQ==
  dependencies:
    css-declaration-sorter "^6.3.1"
    cssnano-utils "^3.1.0"
    postcss-calc "^8.2.3"
    postcss-colormin "^5.3.0"
    postcss-convert-values "^5.1.3"
    postcss-discard-comments "^5.1.2"
    postcss-discard-duplicates "^5.1.0"
    postcss-discard-empty "^5.1.1"
    postcss-discard-overridden "^5.1.0"
    postcss-merge-longhand "^5.1.7"
    postcss-merge-rules "^5.1.3"
    postcss-minify-font-values "^5.1.0"
    postcss-minify-gradients "^5.1.1"
    postcss-minify-params "^5.1.4"
    postcss-minify-selectors "^5.2.1"
    postcss-normalize-charset "^5.1.0"
    postcss-normalize-display-values "^5.1.0"
    postcss-normalize-positions "^5.1.1"
    postcss-normalize-repeat-style "^5.1.1"
    postcss-normalize-string "^5.1.0"
    postcss-normalize-timing-functions "^5.1.0"
    postcss-normalize-unicode "^5.1.1"
    postcss-normalize-url "^5.1.0"
    postcss-normalize-whitespace "^5.1.1"
    postcss-ordered-values "^5.1.3"
    postcss-reduce-initial "^5.1.1"
    postcss-reduce-transforms "^5.1.0"
    postcss-svgo "^5.1.0"
    postcss-unique-selectors "^5.1.1"

cssnano-utils@^3.1.0:
  version "3.1.0"
  resolved "https://registry.npmmirror.com/cssnano-utils/-/cssnano-utils-3.1.0.tgz#95684d08c91511edfc70d2636338ca37ef3a6861"
  integrity sha512-JQNR19/YZhz4psLX/rQ9M83e3z2Wf/HdJbryzte4a3NSuafyp9w/I4U+hx5C2S9g41qlstH7DEWnZaaj83OuEA==

cssnano@^5.0.6, cssnano@^5.0.8:
  version "5.1.14"
  resolved "https://registry.npmmirror.com/cssnano/-/cssnano-5.1.14.tgz#07b0af6da73641276fe5a6d45757702ebae2eb05"
  integrity sha512-Oou7ihiTocbKqi0J1bB+TRJIQX5RMR3JghA8hcWSw9mjBLQ5Y3RWqEDoYG3sRNlAbCIXpqMoZGbq5KDR3vdzgw==
  dependencies:
    cssnano-preset-default "^5.2.13"
    lilconfig "^2.0.3"
    yaml "^1.10.2"

csso@^4.0.2, csso@^4.2.0:
  version "4.2.0"
  resolved "https://registry.npmmirror.com/csso/-/csso-4.2.0.tgz#ea3a561346e8dc9f546d6febedd50187cf389529"
  integrity sha512-wvlcdIbf6pwKEk7vHj8/Bkc0B4ylXZruLvOgs9doS5eOsOpuodOV2zJChSpkp+pRpYQLQMeF04nr3Z68Sta9jA==
  dependencies:
    css-tree "^1.1.2"

csstype@^3.0.2:
  version "3.1.1"
  resolved "https://registry.npmmirror.com/csstype/-/csstype-3.1.1.tgz#841b532c45c758ee546a11d5bd7b7b473c8c30b9"
  integrity sha512-DJR/VvkAvSZW9bTouZue2sSxDwdTN92uHjqeKVm+0dAqdfNykRzQ95tay8aXMBAAPpUiq4Qcug2L7neoRh2Egw==

debug@2.6.9, debug@^2.6.0:
  version "2.6.9"
  resolved "https://registry.npmmirror.com/debug/-/debug-2.6.9.tgz#5d128515df134ff327e90a4c93f4e077a536341f"
  integrity sha512-bC7ElrdJaJnPbAP+1EotYvqZsb3ecl5wi6Bfi6BJTUcNowp6cvspg0jXznRTKDjm/E7AdgFBVeAPVMNcKGsHMA==
  dependencies:
    ms "2.0.0"

debug@4, debug@^4.1.0, debug@^4.1.1, debug@^4.2.0:
  version "4.3.4"
  resolved "https://registry.npmmirror.com/debug/-/debug-4.3.4.tgz#1319f6579357f2338d3337d2cdd4914bb5dcc865"
  integrity sha512-PRWFHuSU3eDtQJPvnNY7Jcket1j0t5OuOsFzPPzsekD52Zl8qUfFIPEiswXqIvHWGVHOgX+7G/vCNNhehwxfkQ==
  dependencies:
    ms "2.1.2"

decompress-response@^6.0.0:
  version "6.0.0"
  resolved "https://registry.npmmirror.com/decompress-response/-/decompress-response-6.0.0.tgz#ca387612ddb7e104bd16d85aab00d5ecf09c66fc"
  integrity sha512-aW35yZM6Bb/4oJlZncMH2LCoZtJXTRxES17vE3hoRiowU2kWHaJKFkSBDnDR+cm9J+9QhXmREyIfv0pji9ejCQ==
  dependencies:
    mimic-response "^3.1.0"

deep-extend@^0.6.0:
  version "0.6.0"
  resolved "https://registry.npmmirror.com/deep-extend/-/deep-extend-0.6.0.tgz#c4fa7c95404a17a9c3e8ca7e1537312b736330ac"
  integrity sha512-LOHxIOaPYdHlJRtCQfDIVZtfw/ufM8+rVj649RIHzcm/vGwQRXFt6OPqIFWsm2XEMrNIEtWR64sY1LEKD2vAOA==

deepmerge@^4.2.2:
  version "4.2.2"
  resolved "https://registry.npmmirror.com/deepmerge/-/deepmerge-4.2.2.tgz#44d2ea3679b8f4d4ffba33f03d865fc1e7bf4955"
  integrity sha512-FJ3UgI4gIl+PHZm53knsuSFpE+nESMr7M4v9QcgB7S63Kj/6WqMiFQJpBBYz1Pt+66bZpP3Q7Lye0Oo9MPKEdg==

default-gateway@^6.0.3:
  version "6.0.3"
  resolved "https://registry.npmmirror.com/default-gateway/-/default-gateway-6.0.3.tgz#819494c888053bdb743edbf343d6cdf7f2943a71"
  integrity sha512-fwSOJsbbNzZ/CUFpqFBqYfYNLj1NbMPm8MMCIzHjC83iSJRBEGmDUxU+WP661BaBQImeC2yHwXtz+P/O9o+XEg==
  dependencies:
    execa "^5.0.0"

defer-to-connect@^2.0.0:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/defer-to-connect/-/defer-to-connect-2.0.1.tgz#8016bdb4143e4632b77a3449c6236277de520587"
  integrity sha512-4tvttepXG1VaYGrRibk5EwJd1t4udunSOVMdLSAL6mId1ix438oPwPZMALY41FCijukO1L0twNcGsdzS7dHgDg==

define-lazy-prop@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/define-lazy-prop/-/define-lazy-prop-2.0.0.tgz#3f7ae421129bcaaac9bc74905c98a0009ec9ee7f"
  integrity sha512-Ds09qNh8yw3khSjiJjiUInaGX9xlqZDY7JVryGxdxV7NPeuqQfplOpQ66yJFZut3jLa5zOwkXw1g9EI2uKh4Og==

define-properties@^1.1.3, define-properties@^1.1.4:
  version "1.1.4"
  resolved "https://registry.npmmirror.com/define-properties/-/define-properties-1.1.4.tgz#0b14d7bd7fbeb2f3572c3a7eda80ea5d57fb05b1"
  integrity sha512-uckOqKcfaVvtBdsVkdPv3XjveQJsNQqmhXgRi8uhvWWuPYZCNlzT8qAyblUgNoXdHdjMTzAqeGjAoli8f+bzPA==
  dependencies:
    has-property-descriptors "^1.0.0"
    object-keys "^1.1.1"

del@^6.0.0:
  version "6.1.1"
  resolved "https://registry.npmmirror.com/del/-/del-6.1.1.tgz#3b70314f1ec0aa325c6b14eb36b95786671edb7a"
  integrity sha512-ua8BhapfP0JUJKC/zV9yHHDW/rDoDxP4Zhn3AkA6/xT6gY7jYXJiaeyBZznYVujhZZET+UgcbZiQ7sN3WqcImg==
  dependencies:
    globby "^11.0.1"
    graceful-fs "^4.2.4"
    is-glob "^4.0.1"
    is-path-cwd "^2.2.0"
    is-path-inside "^3.0.2"
    p-map "^4.0.0"
    rimraf "^3.0.2"
    slash "^3.0.0"

depd@2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/depd/-/depd-2.0.0.tgz#b696163cc757560d09cf22cc8fad1571b79e76df"
  integrity sha512-g7nH6P6dyDioJogAAGprGpCtVImJhpPk/roCzdb3fIh61/s/nPsfR6onyMwkCAR/OlC3yBC0lESvUoQEAssIrw==

depd@~1.1.2:
  version "1.1.2"
  resolved "https://registry.npmmirror.com/depd/-/depd-1.1.2.tgz#9bcd52e14c097763e749b274c4346ed2e560b5a9"
  integrity sha512-7emPTl6Dpo6JRXOXjLRxck+FlLRX5847cLKEn00PLAgc3g2hTZZgr+e4c2v6QpSmLeFP3n5yUo7ft6avBK/5jQ==

destroy@1.2.0:
  version "1.2.0"
  resolved "https://registry.npmmirror.com/destroy/-/destroy-1.2.0.tgz#4803735509ad8be552934c67df614f94e66fa015"
  integrity sha512-2sJGJTaXIIaR1w4iJSNoN0hnMY7Gpc/n8D4qSCJw8QqFWXf7cuAgnEHxBpweaVcPevC2l3KpjYCx3NypQQgaJg==

detab@2.0.4:
  version "2.0.4"
  resolved "https://registry.npmmirror.com/detab/-/detab-2.0.4.tgz#b927892069aff405fbb9a186fe97a44a92a94b43"
  integrity sha512-8zdsQA5bIkoRECvCrNKPla84lyoR7DSAyf7p0YgXzBO9PDJx8KntPUay7NS6yp+KdxdVtiE5SpHKtbp2ZQyA9g==
  dependencies:
    repeat-string "^1.5.4"

detect-node@^2.0.4:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/detect-node/-/detect-node-2.1.0.tgz#c9c70775a49c3d03bc2c06d9a73be550f978f8b1"
  integrity sha512-T0NIuQpnTvFDATNuHN5roPwSBG83rFsuO+MXXH9/3N1eFbn4wcPjttvjMLEPWJ0RGUYgQE7cGgS3tNxbqCGM7g==

detect-port-alt@^1.1.6:
  version "1.1.6"
  resolved "https://registry.npmmirror.com/detect-port-alt/-/detect-port-alt-1.1.6.tgz#24707deabe932d4a3cf621302027c2b266568275"
  integrity sha512-5tQykt+LqfJFBEYaDITx7S7cR7mJ/zQmLXZ2qt5w04ainYZw6tBf9dBunMjVeVOdYVRUzUOE4HkY5J7+uttb5Q==
  dependencies:
    address "^1.0.1"
    debug "^2.6.0"

detect-port@^1.3.0:
  version "1.5.1"
  resolved "https://registry.npmmirror.com/detect-port/-/detect-port-1.5.1.tgz#451ca9b6eaf20451acb0799b8ab40dff7718727b"
  integrity sha512-aBzdj76lueB6uUst5iAs7+0H/oOjqI5D16XUWxlWMIMROhcM0rfsNVk93zTngq1dDNpoXRr++Sus7ETAExppAQ==
  dependencies:
    address "^1.0.1"
    debug "4"

dir-glob@^3.0.1:
  version "3.0.1"
  resolved "https://registry.npmmirror.com/dir-glob/-/dir-glob-3.0.1.tgz#56dbf73d992a4a93ba1584f4534063fd2e41717f"
  integrity sha512-WkrWp9GR4KXfKGYzOLmTuGVi1UWFfws377n9cc55/tb6DuqyF6pcQ5AbiHEshaDpY9v6oaSr2XCDidGmMwdzIA==
  dependencies:
    path-type "^4.0.0"

dns-equal@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/dns-equal/-/dns-equal-1.0.0.tgz#b39e7f1da6eb0a75ba9c17324b34753c47e0654d"
  integrity sha512-z+paD6YUQsk+AbGCEM4PrOXSss5gd66QfcVBFTKR/HpFL9jCqikS94HYwKww6fQyO7IxrIIyUu+g0Ka9tUS2Cg==

dns-packet@^5.2.2:
  version "5.4.0"
  resolved "https://registry.npmmirror.com/dns-packet/-/dns-packet-5.4.0.tgz#1f88477cf9f27e78a213fb6d118ae38e759a879b"
  integrity sha512-EgqGeaBB8hLiHLZtp/IbaDQTL8pZ0+IvwzSHA6d7VyMDM+B9hgddEMa9xjK5oYnw0ci0JQ6g2XCD7/f6cafU6g==
  dependencies:
    "@leichtgewicht/ip-codec" "^2.0.1"

dom-converter@^0.2.0:
  version "0.2.0"
  resolved "https://registry.npmmirror.com/dom-converter/-/dom-converter-0.2.0.tgz#6721a9daee2e293682955b6afe416771627bb768"
  integrity sha512-gd3ypIPfOMr9h5jIKq8E3sHOTCjeirnl0WK5ZdS1AW0Odt0b1PaWaHdJ4Qk4klv+YB9aJBS7mESXjFoDQPu6DA==
  dependencies:
    utila "~0.4"

dom-serializer@0:
  version "0.2.2"
  resolved "https://registry.npmmirror.com/dom-serializer/-/dom-serializer-0.2.2.tgz#1afb81f533717175d478655debc5e332d9f9bb51"
  integrity sha512-2/xPb3ORsQ42nHYiSunXkDjPLBaEj/xTwUO4B7XCZQTRk7EBtTOPaygh10YAAh2OI1Qrp6NWfpAhzswj0ydt9g==
  dependencies:
    domelementtype "^2.0.1"
    entities "^2.0.0"

dom-serializer@^1.0.1:
  version "1.4.1"
  resolved "https://registry.npmmirror.com/dom-serializer/-/dom-serializer-1.4.1.tgz#de5d41b1aea290215dc45a6dae8adcf1d32e2d30"
  integrity sha512-VHwB3KfrcOOkelEG2ZOfxqLZdfkil8PtJi4P8N2MMXucZq2yLp75ClViUlOVwyoHEDjYU433Aq+5zWP61+RGag==
  dependencies:
    domelementtype "^2.0.1"
    domhandler "^4.2.0"
    entities "^2.0.0"

dom-serializer@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/dom-serializer/-/dom-serializer-2.0.0.tgz#e41b802e1eedf9f6cae183ce5e622d789d7d8e53"
  integrity sha512-wIkAryiqt/nV5EQKqQpo3SToSOV9J0DnbJqwK7Wv/Trc92zIAYZ4FlMu+JPFW1DfGFt81ZTCGgDEabffXeLyJg==
  dependencies:
    domelementtype "^2.3.0"
    domhandler "^5.0.2"
    entities "^4.2.0"

domelementtype@1:
  version "1.3.1"
  resolved "https://registry.npmmirror.com/domelementtype/-/domelementtype-1.3.1.tgz#d048c44b37b0d10a7f2a3d5fee3f4333d790481f"
  integrity sha512-BSKB+TSpMpFI/HOxCNr1O8aMOTZ8hT3pM3GQ0w/mWRmkhEDSFJkkyzz4XQsBV44BChwGkrDfMyjVD0eA2aFV3w==

domelementtype@^2.0.1, domelementtype@^2.2.0, domelementtype@^2.3.0:
  version "2.3.0"
  resolved "https://registry.npmmirror.com/domelementtype/-/domelementtype-2.3.0.tgz#5c45e8e869952626331d7aab326d01daf65d589d"
  integrity sha512-OLETBj6w0OsagBwdXnPdN0cnMfF9opN69co+7ZrbfPGrdpPVNBUj02spi6B1N7wChLQiPn4CSH/zJvXw56gmHw==

domhandler@^4.0.0, domhandler@^4.2.0, domhandler@^4.3.1:
  version "4.3.1"
  resolved "https://registry.npmmirror.com/domhandler/-/domhandler-4.3.1.tgz#8d792033416f59d68bc03a5aa7b018c1ca89279c"
  integrity sha512-GrwoxYN+uWlzO8uhUXRl0P+kHE4GtVPfYzVLcUxPL7KNdHKj66vvlhiweIHqYYXWlw+T8iLMp42Lm67ghw4WMQ==
  dependencies:
    domelementtype "^2.2.0"

domhandler@^5.0.1, domhandler@^5.0.2, domhandler@^5.0.3:
  version "5.0.3"
  resolved "https://registry.npmmirror.com/domhandler/-/domhandler-5.0.3.tgz#cc385f7f751f1d1fc650c21374804254538c7d31"
  integrity sha512-cgwlv/1iFQiFnU96XXgROh8xTeetsnJiDsTc7TYCLFd9+/WNkIqPTxiM/8pSd8VIrhXGTf1Ny1q1hquVqDJB5w==
  dependencies:
    domelementtype "^2.3.0"

domutils@^1.7.0:
  version "1.7.0"
  resolved "https://registry.npmmirror.com/domutils/-/domutils-1.7.0.tgz#56ea341e834e06e6748af7a1cb25da67ea9f8c2a"
  integrity sha512-Lgd2XcJ/NjEw+7tFvfKxOzCYKZsdct5lczQ2ZaQY8Djz7pfAD3Gbp8ySJWtreII/vDlMVmxwa6pHmdxIYgttDg==
  dependencies:
    dom-serializer "0"
    domelementtype "1"

domutils@^2.5.2, domutils@^2.8.0:
  version "2.8.0"
  resolved "https://registry.npmmirror.com/domutils/-/domutils-2.8.0.tgz#4437def5db6e2d1f5d6ee859bd95ca7d02048135"
  integrity sha512-w96Cjofp72M5IIhpjgobBimYEfoPjx1Vx0BSX9P30WBdZW2WIKU0T1Bd0kz2eNZ9ikjKgHbEyKx8BB6H1L3h3A==
  dependencies:
    dom-serializer "^1.0.1"
    domelementtype "^2.2.0"
    domhandler "^4.2.0"

domutils@^3.0.1:
  version "3.0.1"
  resolved "https://registry.npmmirror.com/domutils/-/domutils-3.0.1.tgz#696b3875238338cb186b6c0612bd4901c89a4f1c"
  integrity sha512-z08c1l761iKhDFtfXO04C7kTdPBLi41zwOZl00WS8b5eiaebNpY00HKbztwBq+e3vyqWNwWF3mP9YLUeqIrF+Q==
  dependencies:
    dom-serializer "^2.0.0"
    domelementtype "^2.3.0"
    domhandler "^5.0.1"

dot-case@^3.0.4:
  version "3.0.4"
  resolved "https://registry.npmmirror.com/dot-case/-/dot-case-3.0.4.tgz#9b2b670d00a431667a8a75ba29cd1b98809ce751"
  integrity sha512-Kv5nKlh6yRrdrGvxeJ2e5y2eRUpkUosIW4A2AS38zwSz27zu7ufDwQPi5Jhs3XAlGNetl3bmnGhQsMtkKJnj3w==
  dependencies:
    no-case "^3.0.4"
    tslib "^2.0.3"

dot-prop@^5.2.0:
  version "5.3.0"
  resolved "https://registry.npmmirror.com/dot-prop/-/dot-prop-5.3.0.tgz#90ccce708cd9cd82cc4dc8c3ddd9abdd55b20e88"
  integrity sha512-QM8q3zDe58hqUqjraQOmzZ1LIH9SWQJTlEKCH4kJ2oQvLZk7RbQXvtDM2XEq3fwkV9CCvvH4LA0AV+ogFsBM2Q==
  dependencies:
    is-obj "^2.0.0"

duplexer@^0.1.1, duplexer@^0.1.2:
  version "0.1.2"
  resolved "https://registry.npmmirror.com/duplexer/-/duplexer-0.1.2.tgz#3abe43aef3835f8ae077d136ddce0f276b0400e6"
  integrity sha512-jtD6YG370ZCIi/9GTaJKQxWTZD045+4R4hTk/x1UyoqadyJ9x9CgSi1RlVDQF8U2sxLLSnFkCaMihqljHIWgMg==

ee-first@1.1.1:
  version "1.1.1"
  resolved "https://registry.npmmirror.com/ee-first/-/ee-first-1.1.1.tgz#590c61156b0ae2f4f0255732a158b266bc56b21d"
  integrity sha512-WMwm9LhRUo+WUaRN+vRuETqG89IgZphVSNkdFgeb6sS/E4OrDIN7t48CAewSHXc6C8lefD8KKfr5vY61brQlow==

electron-to-chromium@^1.4.251:
  version "1.4.284"
  resolved "https://registry.npmmirror.com/electron-to-chromium/-/electron-to-chromium-1.4.284.tgz#61046d1e4cab3a25238f6bf7413795270f125592"
  integrity sha512-M8WEXFuKXMYMVr45fo8mq0wUrrJHheiKZf6BArTKk9ZBYCKJEOU5H8cdWgDT+qCVZf7Na4lVUaZsA+h6uA9+PA==

emoji-regex@^8.0.0:
  version "8.0.0"
  resolved "https://registry.npmmirror.com/emoji-regex/-/emoji-regex-8.0.0.tgz#e818fd69ce5ccfcb404594f842963bf53164cc37"
  integrity sha512-MSjYzcWNOA0ewAHpz0MxpYFvwg6yjy1NG3xteoqz644VCo/RPgnr1/GGt+ic3iJTzQ8Eu3TdM14SawnVUmGE6A==

emojis-list@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/emojis-list/-/emojis-list-3.0.0.tgz#5570662046ad29e2e916e71aae260abdff4f6a78"
  integrity sha512-/kyM18EfinwXZbno9FyUGeFh87KC8HRQBQGildHZbEuRyWFOmv1U10o9BBp8XVZDVNNuQKyIGIu5ZYAAXJ0V2Q==

emoticon@^3.2.0:
  version "3.2.0"
  resolved "https://registry.npmmirror.com/emoticon/-/emoticon-3.2.0.tgz#c008ca7d7620fac742fe1bf4af8ff8fed154ae7f"
  integrity sha512-SNujglcLTTg+lDAcApPNgEdudaqQFiAbJCqzjNxJkvN9vAwCGi0uu8IUVvx+f16h+V44KCY6Y2yboroc9pilHg==

encodeurl@~1.0.2:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/encodeurl/-/encodeurl-1.0.2.tgz#ad3ff4c86ec2d029322f5a02c3a9a606c95b3f59"
  integrity sha512-TPJXq8JqFaVYm2CWmPvnP2Iyo4ZSM7/QKcSmuMLDObfpH5fi7RUGmd/rTDf+rut/saiDiQEeVTNgAmJEdAOx0w==

end-of-stream@^1.1.0:
  version "1.4.4"
  resolved "https://registry.npmmirror.com/end-of-stream/-/end-of-stream-1.4.4.tgz#5ae64a5f45057baf3626ec14da0ca5e4b2431eb0"
  integrity sha512-+uw1inIHVPQoaVuHzRyXd21icM+cnt4CzD5rW+NC1wjOUSTOs+Te7FOv7AhN7vS9x/oIyhLP5PR1H+phQAHu5Q==
  dependencies:
    once "^1.4.0"

enhanced-resolve@^5.10.0:
  version "5.10.0"
  resolved "https://registry.npmmirror.com/enhanced-resolve/-/enhanced-resolve-5.10.0.tgz#0dc579c3bb2a1032e357ac45b8f3a6f3ad4fb1e6"
  integrity sha512-T0yTFjdpldGY8PmuXXR0PyQ1ufZpEGiHVrp7zHKB7jdR4qlmZHhONVM5AQOAWXuF/w3dnHbEQVrNptJgt7F+cQ==
  dependencies:
    graceful-fs "^4.2.4"
    tapable "^2.2.0"

entities@^2.0.0:
  version "2.2.0"
  resolved "https://registry.npmmirror.com/entities/-/entities-2.2.0.tgz#098dc90ebb83d8dffa089d55256b351d34c4da55"
  integrity sha512-p92if5Nz619I0w+akJrLZH0MX0Pb5DX39XOwQTtXSdQQOaYH03S1uIQp4mhOZtAXrxq4ViO67YTiLBo2638o9A==

entities@^4.2.0, entities@^4.3.0, entities@^4.4.0:
  version "4.4.0"
  resolved "https://registry.npmmirror.com/entities/-/entities-4.4.0.tgz#97bdaba170339446495e653cfd2db78962900174"
  integrity sha512-oYp7156SP8LkeGD0GF85ad1X9Ai79WtRsZ2gxJqtBuzH+98YUV6jkHEKlZkMbcrjJjIVJNIDP/3WL9wQkoPbWA==

error-ex@^1.3.1:
  version "1.3.2"
  resolved "https://registry.npmmirror.com/error-ex/-/error-ex-1.3.2.tgz#b4ac40648107fdcdcfae242f428bea8a14d4f1bf"
  integrity sha512-7dFHNmqeFSEt2ZBsCriorKnn3Z2pj+fd9kmI6QoWw4//DL+icEBfc0U7qJCisqrTsKTjw4fNFy2pW9OqStD84g==
  dependencies:
    is-arrayish "^0.2.1"

es-abstract@^1.17.2, es-abstract@^1.19.0, es-abstract@^1.19.1, es-abstract@^1.19.5, es-abstract@^1.20.1, es-abstract@^1.20.4:
  version "1.20.4"
  resolved "https://registry.npmmirror.com/es-abstract/-/es-abstract-1.20.4.tgz#1d103f9f8d78d4cf0713edcd6d0ed1a46eed5861"
  integrity sha512-0UtvRN79eMe2L+UNEF1BwRe364sj/DXhQ/k5FmivgoSdpM90b8Jc0mDzKMGo7QS0BVbOP/bTwBKNnDc9rNzaPA==
  dependencies:
    call-bind "^1.0.2"
    es-to-primitive "^1.2.1"
    function-bind "^1.1.1"
    function.prototype.name "^1.1.5"
    get-intrinsic "^1.1.3"
    get-symbol-description "^1.0.0"
    has "^1.0.3"
    has-property-descriptors "^1.0.0"
    has-symbols "^1.0.3"
    internal-slot "^1.0.3"
    is-callable "^1.2.7"
    is-negative-zero "^2.0.2"
    is-regex "^1.1.4"
    is-shared-array-buffer "^1.0.2"
    is-string "^1.0.7"
    is-weakref "^1.0.2"
    object-inspect "^1.12.2"
    object-keys "^1.1.1"
    object.assign "^4.1.4"
    regexp.prototype.flags "^1.4.3"
    safe-regex-test "^1.0.0"
    string.prototype.trimend "^1.0.5"
    string.prototype.trimstart "^1.0.5"
    unbox-primitive "^1.0.2"

es-array-method-boxes-properly@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/es-array-method-boxes-properly/-/es-array-method-boxes-properly-1.0.0.tgz#873f3e84418de4ee19c5be752990b2e44718d09e"
  integrity sha512-wd6JXUmyHmt8T5a2xreUwKcGPq6f1f+WwIJkijUqiGcJz1qqnZgP6XIK+QyIWU5lT7imeNxUll48bziG+TSYcA==

es-module-lexer@^0.9.0:
  version "0.9.3"
  resolved "https://registry.npmmirror.com/es-module-lexer/-/es-module-lexer-0.9.3.tgz#6f13db00cc38417137daf74366f535c8eb438f19"
  integrity sha512-1HQ2M2sPtxwnvOvT1ZClHyQDiggdNjURWpY2we6aMKCQiUVxTmVs2UYPLIrD84sS+kMdUwfBSylbJPwNnBrnHQ==

es-to-primitive@^1.2.1:
  version "1.2.1"
  resolved "https://registry.npmmirror.com/es-to-primitive/-/es-to-primitive-1.2.1.tgz#e55cd4c9cdc188bcefb03b366c736323fc5c898a"
  integrity sha512-QCOllgZJtaUo9miYBcLChTUaHNjJF3PYs1VidD7AwiEj1kYxKeQTctLAezAOH5ZKRH0g2IgPn6KwB4IT8iRpvA==
  dependencies:
    is-callable "^1.1.4"
    is-date-object "^1.0.1"
    is-symbol "^1.0.2"

escalade@^3.1.1:
  version "3.1.1"
  resolved "https://registry.npmmirror.com/escalade/-/escalade-3.1.1.tgz#d8cfdc7000965c5a0174b4a82eaa5c0552742e40"
  integrity sha512-k0er2gUkLf8O0zKJiAhmkTnJlTvINGv7ygDNPbeIsX/TJjGJZHuh9B2UxbsaEkmlEo9MfhrSzmhIlhRlI2GXnw==

escape-goat@^2.0.0:
  version "2.1.1"
  resolved "https://registry.npmmirror.com/escape-goat/-/escape-goat-2.1.1.tgz#1b2dc77003676c457ec760b2dc68edb648188675"
  integrity sha512-8/uIhbG12Csjy2JEW7D9pHbreaVaS/OpN3ycnyvElTdwM5n6GY6W6e2IPemfvGZeUMqZ9A/3GqIZMgKnBhAw/Q==

escape-html@^1.0.3, escape-html@~1.0.3:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/escape-html/-/escape-html-1.0.3.tgz#0258eae4d3d0c0974de1c169188ef0051d1d1988"
  integrity sha512-NiSupZ4OeuGwr68lGIeym/ksIZMJodUGOSCZ/FSnTxcrekbvqrgdUxlJOMpijaKZVjAJrWrGs/6Jy8OMuyj9ow==

escape-string-regexp@^1.0.5:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/escape-string-regexp/-/escape-string-regexp-1.0.5.tgz#1b61c0562190a8dff6ae3bb2cf0200ca130b86d4"
  integrity sha512-vbRorB5FUQWvla16U8R/qgaFIya2qGzwDrNmCZuYKrbdSUMG6I1ZCGQRefkRVhuOkIGVne7BQ35DSfo1qvJqFg==

escape-string-regexp@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/escape-string-regexp/-/escape-string-regexp-2.0.0.tgz#a30304e99daa32e23b2fd20f51babd07cffca344"
  integrity sha512-UpzcLCXolUWcNu5HtVMHYdXJjArjsF9C0aNnquZYY4uW/Vu0miy5YoWvbV345HauVvcAUnpRuhMMcqTcGOY2+w==

escape-string-regexp@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/escape-string-regexp/-/escape-string-regexp-4.0.0.tgz#14ba83a5d373e3d311e5afca29cf5bfad965bf34"
  integrity sha512-TtpcNJ3XAzx3Gq8sWRzJaVajRs0uVxA2YAkdb1jm2YkPz4G6egUFAyA3n5vtEIZefPk5Wa4UXbKuS5fKkJWdgA==

eslint-scope@5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/eslint-scope/-/eslint-scope-5.1.1.tgz#e786e59a66cb92b3f6c1fb0d508aab174848f48c"
  integrity sha512-2NxwbF/hZ0KpepYN0cNbo+FN6XoK7GaHlQhgx/hIZl6Va0bF45RQOOwhLIy8lQDbuCiadSLCBnH2CFYquit5bw==
  dependencies:
    esrecurse "^4.3.0"
    estraverse "^4.1.1"

esprima@^4.0.0:
  version "4.0.1"
  resolved "https://registry.npmmirror.com/esprima/-/esprima-4.0.1.tgz#13b04cdb3e6c5d19df91ab6987a8695619b0aa71"
  integrity sha512-eGuFFw7Upda+g4p+QHvnW0RyTX/SVeJBDM/gCtMARO0cLuT2HcEKnTPvhjV6aGeqrCB/sbNop0Kszm0jsaWU4A==

esrecurse@^4.3.0:
  version "4.3.0"
  resolved "https://registry.npmmirror.com/esrecurse/-/esrecurse-4.3.0.tgz#7ad7964d679abb28bee72cec63758b1c5d2c9921"
  integrity sha512-KmfKL3b6G+RXvP8N1vr3Tq1kL/oCFgn2NYXEtqP8/L3pKapUA4G8cFVaoF3SU323CD4XypR/ffioHmkti6/Tag==
  dependencies:
    estraverse "^5.2.0"

estraverse@^4.1.1:
  version "4.3.0"
  resolved "https://registry.npmmirror.com/estraverse/-/estraverse-4.3.0.tgz#398ad3f3c5a24948be7725e83d11a7de28cdbd1d"
  integrity sha512-39nnKffWz8xN1BU/2c79n9nB9HDzo0niYUqx6xyqUnyoAnQyyWpOTdZEeiCch8BBu515t4wp9ZmgVfVhn9EBpw==

estraverse@^5.2.0:
  version "5.3.0"
  resolved "https://registry.npmmirror.com/estraverse/-/estraverse-5.3.0.tgz#2eea5290702f26ab8fe5370370ff86c965d21123"
  integrity sha512-MMdARuVEQziNTeJD8DgMqmhwR11BRQ/cBP+pLtYdSTnf3MIO8fFeiINEbX36ZdNlfU/7A9f3gUw49B3oQsvwBA==

esutils@^2.0.2:
  version "2.0.3"
  resolved "https://registry.npmmirror.com/esutils/-/esutils-2.0.3.tgz#74d2eb4de0b8da1293711910d50775b9b710ef64"
  integrity sha512-kVscqXk4OCp68SZ0dkgEKVi6/8ij300KBWTJq32P/dYeWTSwK41WyTxalN1eRmA5Z9UU/LX9D7FWSmV9SAYx6g==

eta@2.0.0, eta@^1.12.3:
  version "2.0.0"
  resolved "https://registry.yarnpkg.com/eta/-/eta-2.0.0.tgz#376865fadebc899e5b6dfce82fae64cbbe47e594"
  integrity sha512-NqE7S2VmVwgMS8yBxsH4VgNQjNjLq1gfGU0u9I6Cjh468nPRMoDfGdK9n1p/3Dvsw3ebklDkZsFAnKJ9sefjBA==

etag@~1.8.1:
  version "1.8.1"
  resolved "https://registry.npmmirror.com/etag/-/etag-1.8.1.tgz#41ae2eeb65efa62268aebfea83ac7d79299b0887"
  integrity sha512-aIL5Fx7mawVa300al2BnEE4iNvo1qETxLrPI/o05L7z6go7fCw1J6EQmbK4FmJ2AS7kgVF/KEZWufBfdClMcPg==

eval@^0.1.8:
  version "0.1.8"
  resolved "https://registry.npmmirror.com/eval/-/eval-0.1.8.tgz#2b903473b8cc1d1989b83a1e7923f883eb357f85"
  integrity sha512-EzV94NYKoO09GLXGjXj9JIlXijVck4ONSr5wiCWDvhsvj5jxSrzTmRU/9C1DyB6uToszLs8aifA6NQ7lEQdvFw==
  dependencies:
    "@types/node" "*"
    require-like ">= 0.1.1"

eventemitter3@^4.0.0:
  version "4.0.7"
  resolved "https://registry.npmmirror.com/eventemitter3/-/eventemitter3-4.0.7.tgz#2de9b68f6528d5644ef5c59526a1b4a07306169f"
  integrity sha512-8guHBZCwKnFhYdHr2ysuRWErTwhoN2X8XELRlrRwpmfeY2jjuUN4taQMsULKUVo1K4DvZl+0pgfyoysHxvmvEw==

events@^3.2.0:
  version "3.3.0"
  resolved "https://registry.npmmirror.com/events/-/events-3.3.0.tgz#31a95ad0a924e2d2c419a813aeb2c4e878ea7400"
  integrity sha512-mQw+2fkQbALzQ7V0MY0IqdnXNOeTtP4r0lN9z7AAawCXgqea7bDii20AYrIBrFd/Hx0M2Ocz6S111CaFkUcb0Q==

execa@^5.0.0:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/execa/-/execa-5.1.1.tgz#f80ad9cbf4298f7bd1d4c9555c21e93741c411dd"
  integrity sha512-8uSpZZocAZRBAPIEINJj3Lo9HyGitllczc27Eh5YYojjMFMn8yHMDMaUHE2Jqfq05D/wucwI4JGURyXt1vchyg==
  dependencies:
    cross-spawn "^7.0.3"
    get-stream "^6.0.0"
    human-signals "^2.1.0"
    is-stream "^2.0.0"
    merge-stream "^2.0.0"
    npm-run-path "^4.0.1"
    onetime "^5.1.2"
    signal-exit "^3.0.3"
    strip-final-newline "^2.0.0"

express@^4.17.3:
  version "4.18.2"
  resolved "https://registry.npmmirror.com/express/-/express-4.18.2.tgz#3fabe08296e930c796c19e3c516979386ba9fd59"
  integrity sha512-5/PsL6iGPdfQ/lKM1UuielYgv3BUoJfz1aUwU9vHZ+J7gyvwdQXFEBIEIaxeGf0GIcreATNyBExtalisDbuMqQ==
  dependencies:
    accepts "~1.3.8"
    array-flatten "1.1.1"
    body-parser "1.20.1"
    content-disposition "0.5.4"
    content-type "~1.0.4"
    cookie "0.5.0"
    cookie-signature "1.0.6"
    debug "2.6.9"
    depd "2.0.0"
    encodeurl "~1.0.2"
    escape-html "~1.0.3"
    etag "~1.8.1"
    finalhandler "1.2.0"
    fresh "0.5.2"
    http-errors "2.0.0"
    merge-descriptors "1.0.1"
    methods "~1.1.2"
    on-finished "2.4.1"
    parseurl "~1.3.3"
    path-to-regexp "0.1.7"
    proxy-addr "~2.0.7"
    qs "6.11.0"
    range-parser "~1.2.1"
    safe-buffer "5.2.1"
    send "0.18.0"
    serve-static "1.15.0"
    setprototypeof "1.2.0"
    statuses "2.0.1"
    type-is "~1.6.18"
    utils-merge "1.0.1"
    vary "~1.1.2"

extend-shallow@^2.0.1:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/extend-shallow/-/extend-shallow-2.0.1.tgz#51af7d614ad9a9f610ea1bafbb989d6b1c56890f"
  integrity sha512-zCnTtlxNoAiDc3gqY2aYAWFx7XWWiasuF2K8Me5WbN8otHKTUKBwjPtNpRs/rbUZm7KxWAaNj7P1a/p52GbVug==
  dependencies:
    is-extendable "^0.1.0"

extend@^3.0.0:
  version "3.0.2"
  resolved "https://registry.npmmirror.com/extend/-/extend-3.0.2.tgz#f8b1136b4071fbd8eb140aff858b1019ec2915fa"
  integrity sha512-fjquC59cD7CyW6urNXK0FBufkZcoiGG80wTuPujX590cB5Ttln20E2UB4S/WARVqhXffZl2LNgS+gQdPIIim/g==

fast-deep-equal@^3.1.1, fast-deep-equal@^3.1.3:
  version "3.1.3"
  resolved "https://registry.npmmirror.com/fast-deep-equal/-/fast-deep-equal-3.1.3.tgz#3a7d56b559d6cbc3eb512325244e619a65c6c525"
  integrity sha512-f3qQ9oQy9j2AhBe/H9VC91wLmKBCCU/gDOnKNAYG5hswO7BLKj09Hc5HYNz9cGI++xlpDCIgDaitVs03ATR84Q==

fast-glob@^3.2.7, fast-glob@^3.2.9:
  version "3.2.12"
  resolved "https://registry.npmmirror.com/fast-glob/-/fast-glob-3.2.12.tgz#7f39ec99c2e6ab030337142da9e0c18f37afae80"
  integrity sha512-DVj4CQIYYow0BlaelwK1pHl5n5cRSJfM60UA0zK891sVInoPri2Ekj7+e1CT3/3qxXenpI+nBBmQAcJPJgaj4w==
  dependencies:
    "@nodelib/fs.stat" "^2.0.2"
    "@nodelib/fs.walk" "^1.2.3"
    glob-parent "^5.1.2"
    merge2 "^1.3.0"
    micromatch "^4.0.4"

fast-json-stable-stringify@^2.0.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/fast-json-stable-stringify/-/fast-json-stable-stringify-2.1.0.tgz#874bf69c6f404c2b5d99c481341399fd55892633"
  integrity sha512-lhd/wF+Lk98HZoTCtlVraHtfh5XYijIjalXck7saUtuanSDyLMxnHhSXEDJqHxD7msR8D0uCmqlkwjCV8xvwHw==

fast-url-parser@1.1.3:
  version "1.1.3"
  resolved "https://registry.npmmirror.com/fast-url-parser/-/fast-url-parser-1.1.3.tgz#f4af3ea9f34d8a271cf58ad2b3759f431f0b318d"
  integrity sha512-5jOCVXADYNuRkKFzNJ0dCCewsZiYo0dz8QNYljkOpFC6r2U4OBmKtvm/Tsuh4w1YYdDqDb31a8TVhBJ2OJKdqQ==
  dependencies:
    punycode "^1.3.2"

fastq@^1.6.0:
  version "1.13.0"
  resolved "https://registry.npmmirror.com/fastq/-/fastq-1.13.0.tgz#616760f88a7526bdfc596b7cab8c18938c36b98c"
  integrity sha512-YpkpUnK8od0o1hmeSc7UUs/eB/vIPWJYjKck2QKIzAf71Vm1AAQ3EbuZB3g2JIy+pg+ERD0vqI79KyZiB2e2Nw==
  dependencies:
    reusify "^1.0.4"

faye-websocket@^0.11.3:
  version "0.11.4"
  resolved "https://registry.npmmirror.com/faye-websocket/-/faye-websocket-0.11.4.tgz#7f0d9275cfdd86a1c963dc8b65fcc451edcbb1da"
  integrity sha512-CzbClwlXAuiRQAlUyfqPgvPoNKTckTPGfwZV4ZdAhVcP2lh9KUxJg2b5GkE7XbjKQ3YJnQ9z6D9ntLAlB+tP8g==
  dependencies:
    websocket-driver ">=0.5.1"

fbemitter@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/fbemitter/-/fbemitter-3.0.0.tgz#00b2a1af5411254aab416cd75f9e6289bee4bff3"
  integrity sha512-KWKaceCwKQU0+HPoop6gn4eOHk50bBv/VxjJtGMfwmJt3D29JpN4H4eisCtIPA+a8GVBam+ldMMpMjJUvpDyHw==
  dependencies:
    fbjs "^3.0.0"

fbjs-css-vars@^1.0.0:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/fbjs-css-vars/-/fbjs-css-vars-1.0.2.tgz#216551136ae02fe255932c3ec8775f18e2c078b8"
  integrity sha512-b2XGFAFdWZWg0phtAWLHCk836A1Xann+I+Dgd3Gk64MHKZO44FfoD1KxyvbSh0qZsIoXQGGlVztIY+oitJPpRQ==

fbjs@^3.0.0, fbjs@^3.0.1:
  version "3.0.4"
  resolved "https://registry.npmmirror.com/fbjs/-/fbjs-3.0.4.tgz#e1871c6bd3083bac71ff2da868ad5067d37716c6"
  integrity sha512-ucV0tDODnGV3JCnnkmoszb5lf4bNpzjv80K41wd4k798Etq+UYD0y0TIfalLjZoKgjive6/adkRnszwapiDgBQ==
  dependencies:
    cross-fetch "^3.1.5"
    fbjs-css-vars "^1.0.0"
    loose-envify "^1.0.0"
    object-assign "^4.1.0"
    promise "^7.1.1"
    setimmediate "^1.0.5"
    ua-parser-js "^0.7.30"

feed@^4.2.2:
  version "4.2.2"
  resolved "https://registry.npmmirror.com/feed/-/feed-4.2.2.tgz#865783ef6ed12579e2c44bbef3c9113bc4956a7e"
  integrity sha512-u5/sxGfiMfZNtJ3OvQpXcvotFpYkL0n9u9mM2vkui2nGo8b4wvDkJ8gAkYqbA8QpGyFCv3RK0Z+Iv+9veCS9bQ==
  dependencies:
    xml-js "^1.6.11"

file-loader@^6.2.0:
  version "6.2.0"
  resolved "https://registry.npmmirror.com/file-loader/-/file-loader-6.2.0.tgz#baef7cf8e1840df325e4390b4484879480eebe4d"
  integrity sha512-qo3glqyTa61Ytg4u73GultjHGjdRyig3tG6lPtyX/jOEJvHif9uB0/OCI2Kif6ctF3caQTW2G5gym21oAsI4pw==
  dependencies:
    loader-utils "^2.0.0"
    schema-utils "^3.0.0"

filesize@^6.1.0:
  version "6.4.0"
  resolved "https://registry.npmmirror.com/filesize/-/filesize-6.4.0.tgz#914f50471dd66fdca3cefe628bd0cde4ef769bcd"
  integrity sha512-mjFIpOHC4jbfcTfoh4rkWpI31mF7viw9ikj/JyLoKzqlwG/YsefKfvYlYhdYdg/9mtK2z1AzgN/0LvVQ3zdlSQ==

fill-range@^7.0.1:
  version "7.0.1"
  resolved "https://registry.npmmirror.com/fill-range/-/fill-range-7.0.1.tgz#1919a6a7c75fe38b2c7c77e5198535da9acdda40"
  integrity sha512-qOo9F+dMUmC2Lcb4BbVvnKJxTPjCm+RRpe4gDuGrzkL7mEVl/djYSu2OdQ2Pa302N4oqkSg9ir6jaLWJ2USVpQ==
  dependencies:
    to-regex-range "^5.0.1"

finalhandler@1.2.0:
  version "1.2.0"
  resolved "https://registry.npmmirror.com/finalhandler/-/finalhandler-1.2.0.tgz#7d23fe5731b207b4640e4fcd00aec1f9207a7b32"
  integrity sha512-5uXcUVftlQMFnWC9qu/svkWv3GTd2PfUhK/3PLkYNAe7FbqJMt3515HaxE6eRL74GdsriiwujiawdaB1BpEISg==
  dependencies:
    debug "2.6.9"
    encodeurl "~1.0.2"
    escape-html "~1.0.3"
    on-finished "2.4.1"
    parseurl "~1.3.3"
    statuses "2.0.1"
    unpipe "~1.0.0"

find-cache-dir@^3.3.1:
  version "3.3.2"
  resolved "https://registry.npmmirror.com/find-cache-dir/-/find-cache-dir-3.3.2.tgz#b30c5b6eff0730731aea9bbd9dbecbd80256d64b"
  integrity sha512-wXZV5emFEjrridIgED11OoUKLxiYjAcqot/NJdAkOhlJ+vGzwhOAfcG5OX1jP+S0PcjEn8bdMJv+g2jwQ3Onig==
  dependencies:
    commondir "^1.0.1"
    make-dir "^3.0.2"
    pkg-dir "^4.1.0"

find-up@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/find-up/-/find-up-3.0.0.tgz#49169f1d7993430646da61ecc5ae355c21c97b73"
  integrity sha512-1yD6RmLI1XBfxugvORwlck6f75tYL+iR0jqwsOrOxMZyGYqUuDhJ0l4AXdO1iX/FTs9cBAMEk1gWSEx1kSbylg==
  dependencies:
    locate-path "^3.0.0"

find-up@^4.0.0, find-up@^4.1.0:
  version "4.1.0"
  resolved "https://registry.npmmirror.com/find-up/-/find-up-4.1.0.tgz#97afe7d6cdc0bc5928584b7c8d7b16e8a9aa5d19"
  integrity sha512-PpOwAdQ/YlXQ2vj8a3h8IipDuYRi3wceVQQGYWxNINccq40Anw7BlsEXCMbt1Zt+OLA6Fq9suIpIWD0OsnISlw==
  dependencies:
    locate-path "^5.0.0"
    path-exists "^4.0.0"

find-up@^5.0.0:
  version "5.0.0"
  resolved "https://registry.npmmirror.com/find-up/-/find-up-5.0.0.tgz#4c92819ecb7083561e4f4a240a86be5198f536fc"
  integrity sha512-78/PXT1wlLLDgTzDs7sjq9hzz0vXD+zn+7wypEe4fXQxCmdmqfGsEPQxmiCSQI3ajFV91bVSsvNtrJRiW6nGng==
  dependencies:
    locate-path "^6.0.0"
    path-exists "^4.0.0"

flux@^4.0.1:
  version "4.0.3"
  resolved "https://registry.npmmirror.com/flux/-/flux-4.0.3.tgz#573b504a24982c4768fdfb59d8d2ea5637d72ee7"
  integrity sha512-yKAbrp7JhZhj6uiT1FTuVMlIAT1J4jqEyBpFApi1kxpGZCvacMVc/t1pMQyotqHhAgvoE3bNvAykhCo2CLjnYw==
  dependencies:
    fbemitter "^3.0.0"
    fbjs "^3.0.1"

follow-redirects@^1.0.0, follow-redirects@^1.14.7:
  version "1.15.2"
  resolved "https://registry.npmmirror.com/follow-redirects/-/follow-redirects-1.15.2.tgz#b460864144ba63f2681096f274c4e57026da2c13"
  integrity sha512-VQLG33o04KaQ8uYi2tVNbdrWp1QWxNNea+nmIB4EVM28v0hmP17z7aG1+wAkNzVq4KeXTq3221ye5qTJP91JwA==

fork-ts-checker-webpack-plugin@^6.0.5:
  version "6.5.2"
  resolved "https://registry.npmmirror.com/fork-ts-checker-webpack-plugin/-/fork-ts-checker-webpack-plugin-6.5.2.tgz#4f67183f2f9eb8ba7df7177ce3cf3e75cdafb340"
  integrity sha512-m5cUmF30xkZ7h4tWUgTAcEaKmUW7tfyUyTqNNOz7OxWJ0v1VWKTcOvH8FWHUwSjlW/356Ijc9vi3XfcPstpQKA==
  dependencies:
    "@babel/code-frame" "^7.8.3"
    "@types/json-schema" "^7.0.5"
    chalk "^4.1.0"
    chokidar "^3.4.2"
    cosmiconfig "^6.0.0"
    deepmerge "^4.2.2"
    fs-extra "^9.0.0"
    glob "^7.1.6"
    memfs "^3.1.2"
    minimatch "^3.0.4"
    schema-utils "2.7.0"
    semver "^7.3.2"
    tapable "^1.0.0"

forwarded@0.2.0:
  version "0.2.0"
  resolved "https://registry.npmmirror.com/forwarded/-/forwarded-0.2.0.tgz#2269936428aad4c15c7ebe9779a84bf0b2a81811"
  integrity sha512-buRG0fpBtRHSTCOASe6hD258tEubFoRLb4ZNA6NxMVHNw2gOcwHo9wyablzMzOA5z9xA9L1KNjk/Nt6MT9aYow==

fraction.js@^4.2.0:
  version "4.2.0"
  resolved "https://registry.npmmirror.com/fraction.js/-/fraction.js-4.2.0.tgz#448e5109a313a3527f5a3ab2119ec4cf0e0e2950"
  integrity sha512-MhLuK+2gUcnZe8ZHlaaINnQLl0xRIGRfcGk2yl8xoQAfHrSsL3rYu6FCmBdkdbhc9EPlwyGHewaRsvwRMJtAlA==

fresh@0.5.2:
  version "0.5.2"
  resolved "https://registry.npmmirror.com/fresh/-/fresh-0.5.2.tgz#3d8cadd90d976569fa835ab1f8e4b23a105605a7"
  integrity sha512-zJ2mQYM18rEFOudeV4GShTGIQ7RbzA7ozbU9I/XBpm7kqgMywgmylMwXHxZJmkVoYkna9d2pVXVXPdYTP9ej8Q==

fs-extra@^10.0.0, fs-extra@^10.1.0:
  version "10.1.0"
  resolved "https://registry.npmmirror.com/fs-extra/-/fs-extra-10.1.0.tgz#02873cfbc4084dde127eaa5f9905eef2325d1abf"
  integrity sha512-oRXApq54ETRj4eMiFzGnHWGy+zo5raudjuxN0b8H7s/RU2oW0Wvsx9O0ACRN/kRq9E8Vu/ReskGB5o3ji+FzHQ==
  dependencies:
    graceful-fs "^4.2.0"
    jsonfile "^6.0.1"
    universalify "^2.0.0"

fs-extra@^9.0.0, fs-extra@^9.0.1:
  version "9.1.0"
  resolved "https://registry.npmmirror.com/fs-extra/-/fs-extra-9.1.0.tgz#5954460c764a8da2094ba3554bf839e6b9a7c86d"
  integrity sha512-hcg3ZmepS30/7BSFqRvoo3DOMQu7IjqxO5nCDt+zM9XWjb33Wg7ziNT+Qvqbuc3+gWpzO02JubVyk2G4Zvo1OQ==
  dependencies:
    at-least-node "^1.0.0"
    graceful-fs "^4.2.0"
    jsonfile "^6.0.1"
    universalify "^2.0.0"

fs-monkey@^1.0.3:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/fs-monkey/-/fs-monkey-1.0.3.tgz#ae3ac92d53bb328efe0e9a1d9541f6ad8d48e2d3"
  integrity sha512-cybjIfiiE+pTWicSCLFHSrXZ6EilF30oh91FDP9S2B051prEa7QWfrVTQm10/dDpswBDXZugPa1Ogu8Yh+HV0Q==

fs.realpath@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/fs.realpath/-/fs.realpath-1.0.0.tgz#1504ad2523158caa40db4a2787cb01411994ea4f"
  integrity sha512-OO0pH2lK6a0hZnAdau5ItzHPI6pUlvI7jMVnxUQRtw4owF2wk8lOSabtGDCTP4Ggrg2MbGnWO9X8K1t4+fGMDw==

fsevents@~2.3.2:
  version "2.3.2"
  resolved "https://registry.npmmirror.com/fsevents/-/fsevents-2.3.2.tgz#8a526f78b8fdf4623b709e0b975c52c24c02fd1a"
  integrity sha512-xiqMQR4xAeHTuB9uWm+fFRcIOgKBMiOBP+eXiyT7jsgVCq1bkVygt00oASowB7EdtpOHaaPgKt812P9ab+DDKA==

function-bind@^1.1.1:
  version "1.1.1"
  resolved "https://registry.npmmirror.com/function-bind/-/function-bind-1.1.1.tgz#a56899d3ea3c9bab874bb9773b7c5ede92f4895d"
  integrity sha512-yIovAzMX49sF8Yl58fSCWJ5svSLuaibPxXQJFLmBObTuCr0Mf1KiPopGM9NiFjiYBCbfaa2Fh6breQ6ANVTI0A==

function.prototype.name@^1.1.5:
  version "1.1.5"
  resolved "https://registry.npmmirror.com/function.prototype.name/-/function.prototype.name-1.1.5.tgz#cce0505fe1ffb80503e6f9e46cc64e46a12a9621"
  integrity sha512-uN7m/BzVKQnCUF/iW8jYea67v++2u7m5UgENbHRtdDVclOUP+FMPlCNdmk0h/ysGyo2tavMJEDqJAkJdRa1vMA==
  dependencies:
    call-bind "^1.0.2"
    define-properties "^1.1.3"
    es-abstract "^1.19.0"
    functions-have-names "^1.2.2"

functions-have-names@^1.2.2:
  version "1.2.3"
  resolved "https://registry.npmmirror.com/functions-have-names/-/functions-have-names-1.2.3.tgz#0404fe4ee2ba2f607f0e0ec3c80bae994133b834"
  integrity sha512-xckBUXyTIqT97tq2x2AMb+g163b5JFysYk0x4qxNFwbfQkmNZoiRHb6sPzI9/QV33WeuvVYBUIiD4NzNIyqaRQ==

gensync@^1.0.0-beta.1, gensync@^1.0.0-beta.2:
  version "1.0.0-beta.2"
  resolved "https://registry.npmmirror.com/gensync/-/gensync-1.0.0-beta.2.tgz#32a6ee76c3d7f52d46b2b1ae5d93fea8580a25e0"
  integrity sha512-3hN7NaskYvMDLQY55gnW3NQ+mesEAepTqlg+VEbj7zzqEMBVNhzcGYYeqFo/TlYz6eQiFcp1HcsCZO+nGgS8zg==

get-intrinsic@^1.0.2, get-intrinsic@^1.1.0, get-intrinsic@^1.1.1, get-intrinsic@^1.1.3:
  version "1.1.3"
  resolved "https://registry.npmmirror.com/get-intrinsic/-/get-intrinsic-1.1.3.tgz#063c84329ad93e83893c7f4f243ef63ffa351385"
  integrity sha512-QJVz1Tj7MS099PevUG5jvnt9tSkXN8K14dxQlikJuPt4uD9hHAHjLyLBiLR5zELelBdD9QNRAXZzsJx0WaDL9A==
  dependencies:
    function-bind "^1.1.1"
    has "^1.0.3"
    has-symbols "^1.0.3"

get-own-enumerable-property-symbols@^3.0.0:
  version "3.0.2"
  resolved "https://registry.npmmirror.com/get-own-enumerable-property-symbols/-/get-own-enumerable-property-symbols-3.0.2.tgz#b5fde77f22cbe35f390b4e089922c50bce6ef664"
  integrity sha512-I0UBV/XOz1XkIJHEUDMZAbzCThU/H8DxmSfmdGcKPnVhu2VfFqr34jr9777IyaTYvxjedWhqVIilEDsCdP5G6g==

get-stream@^5.1.0:
  version "5.2.0"
  resolved "https://registry.npmmirror.com/get-stream/-/get-stream-5.2.0.tgz#4966a1795ee5ace65e706c4b7beb71257d6e22d3"
  integrity sha512-nBF+F1rAZVCu/p7rjzgA+Yb4lfYXrpl7a6VmJrU8wF9I1CKvP/QwPNZHnOlwbTkY6dvtFIzFMSyQXbLoTQPRpA==
  dependencies:
    pump "^3.0.0"

get-stream@^6.0.0:
  version "6.0.1"
  resolved "https://registry.npmmirror.com/get-stream/-/get-stream-6.0.1.tgz#a262d8eef67aced57c2852ad6167526a43cbf7b7"
  integrity sha512-ts6Wi+2j3jQjqi70w5AlN8DFnkSwC+MqmxEzdEALB2qXZYV3X/b1CTfgPLGJNMeAWxdPfU8FO1ms3NUfaHCPYg==

get-symbol-description@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/get-symbol-description/-/get-symbol-description-1.0.0.tgz#7fdb81c900101fbd564dd5f1a30af5aadc1e58d6"
  integrity sha512-2EmdH1YvIQiZpltCNgkuiUnyukzxM/R6NDJX31Ke3BG1Nq5b0S2PhX59UKi9vZpPDQVdqn+1IcaAwnzTT5vCjw==
  dependencies:
    call-bind "^1.0.2"
    get-intrinsic "^1.1.1"

github-slugger@^1.4.0:
  version "1.5.0"
  resolved "https://registry.npmmirror.com/github-slugger/-/github-slugger-1.5.0.tgz#17891bbc73232051474d68bd867a34625c955f7d"
  integrity sha512-wIh+gKBI9Nshz2o46B0B3f5k/W+WI9ZAv6y5Dn5WJ5SK1t0TnDimB4WE5rmTD05ZAIn8HALCZVmCsvj0w0v0lw==

glob-parent@^5.1.2, glob-parent@~5.1.2:
  version "5.1.2"
  resolved "https://registry.npmmirror.com/glob-parent/-/glob-parent-5.1.2.tgz#869832c58034fe68a4093c17dc15e8340d8401c4"
  integrity sha512-AOIgSQCepiJYwP3ARnGx+5VnTu2HBYdzbGP45eLw1vr3zB3vZLeyed1sC9hnbcOc9/SrMyM5RPQrkGz4aS9Zow==
  dependencies:
    is-glob "^4.0.1"

glob-parent@^6.0.1:
  version "6.0.2"
  resolved "https://registry.npmmirror.com/glob-parent/-/glob-parent-6.0.2.tgz#6d237d99083950c79290f24c7642a3de9a28f9e3"
  integrity sha512-XxwI8EOhVQgWp6iDL+3b0r86f4d6AX6zSU55HfB4ydCEuXLXc5FcYeOu+nnGftS4TEju/11rt4KJPTMgbfmv4A==
  dependencies:
    is-glob "^4.0.3"

glob-to-regexp@^0.4.1:
  version "0.4.1"
  resolved "https://registry.npmmirror.com/glob-to-regexp/-/glob-to-regexp-0.4.1.tgz#c75297087c851b9a578bd217dd59a92f59fe546e"
  integrity sha512-lkX1HJXwyMcprw/5YUZc2s7DrpAiHB21/V+E1rHUrVNokkvB6bqMzT0VfV6/86ZNabt1k14YOIaT7nDvOX3Iiw==

glob@^7.0.0, glob@^7.1.3, glob@^7.1.6:
  version "7.2.3"
  resolved "https://registry.npmmirror.com/glob/-/glob-7.2.3.tgz#b8df0fb802bbfa8e89bd1d938b4e16578ed44f2b"
  integrity sha512-nFR0zLpU2YCaRxwoCJvL6UvCH2JFyFVIvwTLsIf21AuHlMskA1hhTdk+LlYJtOlYt9v6dvszD2BGRqBL+iQK9Q==
  dependencies:
    fs.realpath "^1.0.0"
    inflight "^1.0.4"
    inherits "2"
    minimatch "^3.1.1"
    once "^1.3.0"
    path-is-absolute "^1.0.0"

global-dirs@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/global-dirs/-/global-dirs-3.0.0.tgz#70a76fe84ea315ab37b1f5576cbde7d48ef72686"
  integrity sha512-v8ho2DS5RiCjftj1nD9NmnfaOzTdud7RRnVd9kFNOjqZbISlx5DQ+OrTkywgd0dIt7oFCvKetZSHoHcP3sDdiA==
  dependencies:
    ini "2.0.0"

global-modules@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/global-modules/-/global-modules-2.0.0.tgz#997605ad2345f27f51539bea26574421215c7780"
  integrity sha512-NGbfmJBp9x8IxyJSd1P+otYK8vonoJactOogrVfFRIAEY1ukil8RSKDz2Yo7wh1oihl51l/r6W4epkeKJHqL8A==
  dependencies:
    global-prefix "^3.0.0"

global-prefix@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/global-prefix/-/global-prefix-3.0.0.tgz#fc85f73064df69f50421f47f883fe5b913ba9b97"
  integrity sha512-awConJSVCHVGND6x3tmMaKcQvwXLhjdkmomy2W+Goaui8YPgYgXJZewhg3fWC+DlfqqQuWg8AwqjGTD2nAPVWg==
  dependencies:
    ini "^1.3.5"
    kind-of "^6.0.2"
    which "^1.3.1"

globals@^11.1.0:
  version "11.12.0"
  resolved "https://registry.npmmirror.com/globals/-/globals-11.12.0.tgz#ab8795338868a0babd8525758018c2a7eb95c42e"
  integrity sha512-WOBp/EEGUiIsJSp7wcv/y6MO+lV9UoncWqxuFfm8eBwzWNgyfBd6Gz+IeKQ9jCmyhoH99g15M3T+QaVHFjizVA==

globby@^11.0.1, globby@^11.0.2, globby@^11.0.3, globby@^11.0.4, globby@^11.1.0:
  version "11.1.0"
  resolved "https://registry.npmmirror.com/globby/-/globby-11.1.0.tgz#bd4be98bb042f83d796f7e3811991fbe82a0d34b"
  integrity sha512-jhIXaOzy1sb8IyocaruWSn1TjmnBVs8Ayhcy83rmxNJ8q2uWKCAj3CnJY+KpGSXCueAPc0i05kVvVKtP1t9S3g==
  dependencies:
    array-union "^2.1.0"
    dir-glob "^3.0.1"
    fast-glob "^3.2.9"
    ignore "^5.2.0"
    merge2 "^1.4.1"
    slash "^3.0.0"

got@11.8.5, got@^9.6.0:
  version "11.8.5"
  resolved "https://registry.npmmirror.com/got/-/got-11.8.5.tgz#ce77d045136de56e8f024bebb82ea349bc730046"
  integrity sha512-o0Je4NvQObAuZPHLFoRSkdG2lTgtcynqymzg2Vupdx6PorhaT5MCbIyXG6d4D94kk8ZG57QeosgdiqfJWhEhlQ==
  dependencies:
    "@sindresorhus/is" "^4.0.0"
    "@szmarczak/http-timer" "^4.0.5"
    "@types/cacheable-request" "^6.0.1"
    "@types/responselike" "^1.0.0"
    cacheable-lookup "^5.0.3"
    cacheable-request "^7.0.2"
    decompress-response "^6.0.0"
    http2-wrapper "^1.0.0-beta.5.2"
    lowercase-keys "^2.0.0"
    p-cancelable "^2.0.0"
    responselike "^2.0.0"

graceful-fs@^4.1.11, graceful-fs@^4.1.2, graceful-fs@^4.1.6, graceful-fs@^4.2.0, graceful-fs@^4.2.4, graceful-fs@^4.2.6, graceful-fs@^4.2.9:
  version "4.2.10"
  resolved "https://registry.npmmirror.com/graceful-fs/-/graceful-fs-4.2.10.tgz#147d3a006da4ca3ce14728c7aefc287c367d7a6c"
  integrity sha512-9ByhssR2fPVsNZj478qUUbKfmL0+t5BDVyjShtyZZLiK7ZDAArFFfopyOTj0M05wE2tJPisA4iTnnXl2YoPvOA==

gray-matter@^4.0.3:
  version "4.0.3"
  resolved "https://registry.npmmirror.com/gray-matter/-/gray-matter-4.0.3.tgz#e893c064825de73ea1f5f7d88c7a9f7274288798"
  integrity sha512-5v6yZd4JK3eMI3FqqCouswVqwugaA9r4dNZB1wwcmrD02QkV5H0y7XBQW8QwQqEaZY1pM9aqORSORhJRdNK44Q==
  dependencies:
    js-yaml "^3.13.1"
    kind-of "^6.0.2"
    section-matter "^1.0.0"
    strip-bom-string "^1.0.0"

gzip-size@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/gzip-size/-/gzip-size-5.1.1.tgz#cb9bee692f87c0612b232840a873904e4c135274"
  integrity sha512-FNHi6mmoHvs1mxZAds4PpdCS6QG8B4C1krxJsMutgxl5t3+GlRTzzI3NEkifXx2pVsOvJdOGSmIgDhQ55FwdPA==
  dependencies:
    duplexer "^0.1.1"
    pify "^4.0.1"

gzip-size@^6.0.0:
  version "6.0.0"
  resolved "https://registry.npmmirror.com/gzip-size/-/gzip-size-6.0.0.tgz#065367fd50c239c0671cbcbad5be3e2eeb10e462"
  integrity sha512-ax7ZYomf6jqPTQ4+XCpUGyXKHk5WweS+e05MBO4/y3WJ5RkmPXNKvX+bx1behVILVwr6JSQvZAku021CHPXG3Q==
  dependencies:
    duplexer "^0.1.2"

handle-thing@^2.0.0:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/handle-thing/-/handle-thing-2.0.1.tgz#857f79ce359580c340d43081cc648970d0bb234e"
  integrity sha512-9Qn4yBxelxoh2Ow62nP+Ka/kMnOXRi8BXnRaUwezLNhqelnN49xKz4F/dPP8OYLxLxq6JDtZb2i9XznUQbNPTg==

has-bigints@^1.0.1, has-bigints@^1.0.2:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/has-bigints/-/has-bigints-1.0.2.tgz#0871bd3e3d51626f6ca0966668ba35d5602d6eaa"
  integrity sha512-tSvCKtBr9lkF0Ex0aQiP9N+OpV4zi2r/Nee5VkRDbaqv35RLYMzbwQfFSZZH0kR+Rd6302UJZ2p/bJCEoR3VoQ==

has-flag@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/has-flag/-/has-flag-3.0.0.tgz#b5d454dc2199ae225699f3467e5a07f3b955bafd"
  integrity sha512-sKJf1+ceQBr4SMkvQnBDNDtf4TXpVhVGateu0t918bl30FnbE2m4vNLX+VWe/dpjlb+HugGYzW7uQXH98HPEYw==

has-flag@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/has-flag/-/has-flag-4.0.0.tgz#944771fd9c81c81265c4d6941860da06bb59479b"
  integrity sha512-EykJT/Q1KjTWctppgIAgfSO0tKVuZUjhgMr17kqTumMl6Afv3EISleU7qZUzoXDFTAHTDC4NOoG/ZxU3EvlMPQ==

has-property-descriptors@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/has-property-descriptors/-/has-property-descriptors-1.0.0.tgz#610708600606d36961ed04c196193b6a607fa861"
  integrity sha512-62DVLZGoiEBDHQyqG4w9xCuZ7eJEwNmJRWw2VY84Oedb7WFcA27fiEVe8oUQx9hAUJ4ekurquucTGwsyO1XGdQ==
  dependencies:
    get-intrinsic "^1.1.1"

has-symbols@^1.0.1, has-symbols@^1.0.2, has-symbols@^1.0.3:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/has-symbols/-/has-symbols-1.0.3.tgz#bb7b2c4349251dce87b125f7bdf874aa7c8b39f8"
  integrity sha512-l3LCuF6MgDNwTDKkdYGEihYjt5pRPbEg46rtlmnSPlUbgmB8LOIrKJbYYFBSbnPaJexMKtiPO8hmeRjRz2Td+A==

has-tostringtag@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/has-tostringtag/-/has-tostringtag-1.0.0.tgz#7e133818a7d394734f941e73c3d3f9291e658b25"
  integrity sha512-kFjcSNhnlGV1kyoGk7OXKSawH5JOb/LzUc5w9B02hOTO0dfFRjbHQKvg1d6cf3HbeUmtU9VbbV3qzZ2Teh97WQ==
  dependencies:
    has-symbols "^1.0.2"

has-yarn@^2.1.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/has-yarn/-/has-yarn-2.1.0.tgz#137e11354a7b5bf11aa5cb649cf0c6f3ff2b2e77"
  integrity sha512-UqBRqi4ju7T+TqGNdqAO0PaSVGsDGJUBQvk9eUWNGRY1CFGDzYhLWoM7JQEemnlvVcv/YEmc2wNW8BC24EnUsw==

has@^1.0.3:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/has/-/has-1.0.3.tgz#722d7cbfc1f6aa8241f16dd814e011e1f41e8796"
  integrity sha512-f2dvO0VU6Oej7RkWJGrehjbzMAjFp5/VKPp5tTpWIV4JHHZK1/BxbFRtf/siA2SWTe09caDmVtYYzWEIbBS4zw==
  dependencies:
    function-bind "^1.1.1"

hast-to-hyperscript@^9.0.0:
  version "9.0.1"
  resolved "https://registry.npmmirror.com/hast-to-hyperscript/-/hast-to-hyperscript-9.0.1.tgz#9b67fd188e4c81e8ad66f803855334173920218d"
  integrity sha512-zQgLKqF+O2F72S1aa4y2ivxzSlko3MAvxkwG8ehGmNiqd98BIN3JM1rAJPmplEyLmGLO2QZYJtIneOSZ2YbJuA==
  dependencies:
    "@types/unist" "^2.0.3"
    comma-separated-tokens "^1.0.0"
    property-information "^5.3.0"
    space-separated-tokens "^1.0.0"
    style-to-object "^0.3.0"
    unist-util-is "^4.0.0"
    web-namespaces "^1.0.0"

hast-util-from-parse5@^5.0.0:
  version "5.0.3"
  resolved "https://registry.npmmirror.com/hast-util-from-parse5/-/hast-util-from-parse5-5.0.3.tgz#3089dc0ee2ccf6ec8bc416919b51a54a589e097c"
  integrity sha512-gOc8UB99F6eWVWFtM9jUikjN7QkWxB3nY0df5Z0Zq1/Nkwl5V4hAAsl0tmwlgWl/1shlTF8DnNYLO8X6wRV9pA==
  dependencies:
    ccount "^1.0.3"
    hastscript "^5.0.0"
    property-information "^5.0.0"
    web-namespaces "^1.1.2"
    xtend "^4.0.1"

hast-util-from-parse5@^6.0.0:
  version "6.0.1"
  resolved "https://registry.npmmirror.com/hast-util-from-parse5/-/hast-util-from-parse5-6.0.1.tgz#554e34abdeea25ac76f5bd950a1f0180e0b3bc2a"
  integrity sha512-jeJUWiN5pSxW12Rh01smtVkZgZr33wBokLzKLwinYOUfSzm1Nl/c3GUGebDyOKjdsRgMvoVbV0VpAcpjF4NrJA==
  dependencies:
    "@types/parse5" "^5.0.0"
    hastscript "^6.0.0"
    property-information "^5.0.0"
    vfile "^4.0.0"
    vfile-location "^3.2.0"
    web-namespaces "^1.0.0"

hast-util-is-element@1.1.0, hast-util-is-element@^1.0.0:
  version "1.1.0"
  resolved "https://registry.npmmirror.com/hast-util-is-element/-/hast-util-is-element-1.1.0.tgz#3b3ed5159a2707c6137b48637fbfe068e175a425"
  integrity sha512-oUmNua0bFbdrD/ELDSSEadRVtWZOf3iF6Lbv81naqsIV99RnSCieTbWuWCY8BAeEfKJTKl0gRdokv+dELutHGQ==

hast-util-parse-selector@^2.0.0:
  version "2.2.5"
  resolved "https://registry.npmmirror.com/hast-util-parse-selector/-/hast-util-parse-selector-2.2.5.tgz#d57c23f4da16ae3c63b3b6ca4616683313499c3a"
  integrity sha512-7j6mrk/qqkSehsM92wQjdIgWM2/BW61u/53G6xmC8i1OmEdKLHbk419QKQUjz6LglWsfqoiHmyMRkP1BGjecNQ==

hast-util-raw@6.0.1:
  version "6.0.1"
  resolved "https://registry.npmmirror.com/hast-util-raw/-/hast-util-raw-6.0.1.tgz#973b15930b7529a7b66984c98148b46526885977"
  integrity sha512-ZMuiYA+UF7BXBtsTBNcLBF5HzXzkyE6MLzJnL605LKE8GJylNjGc4jjxazAHUtcwT5/CEt6afRKViYB4X66dig==
  dependencies:
    "@types/hast" "^2.0.0"
    hast-util-from-parse5 "^6.0.0"
    hast-util-to-parse5 "^6.0.0"
    html-void-elements "^1.0.0"
    parse5 "^6.0.0"
    unist-util-position "^3.0.0"
    vfile "^4.0.0"
    web-namespaces "^1.0.0"
    xtend "^4.0.0"
    zwitch "^1.0.0"

hast-util-to-parse5@^6.0.0:
  version "6.0.0"
  resolved "https://registry.npmmirror.com/hast-util-to-parse5/-/hast-util-to-parse5-6.0.0.tgz#1ec44650b631d72952066cea9b1445df699f8479"
  integrity sha512-Lu5m6Lgm/fWuz8eWnrKezHtVY83JeRGaNQ2kn9aJgqaxvVkFCZQBEhgodZUDUvoodgyROHDb3r5IxAEdl6suJQ==
  dependencies:
    hast-to-hyperscript "^9.0.0"
    property-information "^5.0.0"
    web-namespaces "^1.0.0"
    xtend "^4.0.0"
    zwitch "^1.0.0"

hast-util-to-text@^2.0.0:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/hast-util-to-text/-/hast-util-to-text-2.0.1.tgz#04f2e065642a0edb08341976084aa217624a0f8b"
  integrity sha512-8nsgCARfs6VkwH2jJU9b8LNTuR4700na+0h3PqCaEk4MAnMDeu5P0tP8mjk9LLNGxIeQRLbiDbZVw6rku+pYsQ==
  dependencies:
    hast-util-is-element "^1.0.0"
    repeat-string "^1.0.0"
    unist-util-find-after "^3.0.0"

hastscript@^5.0.0:
  version "5.1.2"
  resolved "https://registry.npmmirror.com/hastscript/-/hastscript-5.1.2.tgz#bde2c2e56d04c62dd24e8c5df288d050a355fb8a"
  integrity sha512-WlztFuK+Lrvi3EggsqOkQ52rKbxkXL3RwB6t5lwoa8QLMemoWfBuL43eDrwOamJyR7uKQKdmKYaBH1NZBiIRrQ==
  dependencies:
    comma-separated-tokens "^1.0.0"
    hast-util-parse-selector "^2.0.0"
    property-information "^5.0.0"
    space-separated-tokens "^1.0.0"

hastscript@^6.0.0:
  version "6.0.0"
  resolved "https://registry.npmmirror.com/hastscript/-/hastscript-6.0.0.tgz#e8768d7eac56c3fdeac8a92830d58e811e5bf640"
  integrity sha512-nDM6bvd7lIqDUiYEiu5Sl/+6ReP0BMk/2f4U/Rooccxkj0P5nm+acM5PrGJ/t5I8qPGiqZSE6hVAwZEdZIvP4w==
  dependencies:
    "@types/hast" "^2.0.0"
    comma-separated-tokens "^1.0.0"
    hast-util-parse-selector "^2.0.0"
    property-information "^5.0.0"
    space-separated-tokens "^1.0.0"

he@^1.2.0:
  version "1.2.0"
  resolved "https://registry.npmmirror.com/he/-/he-1.2.0.tgz#84ae65fa7eafb165fddb61566ae14baf05664f0f"
  integrity sha512-F/1DnUGPopORZi0ni+CvrCgHQ5FyEAHRLSApuYWMmrbSwoN2Mn/7k+Gl38gJnR7yyDZk6WLXwiGod1JOWNDKGw==

history@^4.9.0:
  version "4.10.1"
  resolved "https://registry.npmmirror.com/history/-/history-4.10.1.tgz#33371a65e3a83b267434e2b3f3b1b4c58aad4cf3"
  integrity sha512-36nwAD620w12kuzPAsyINPWJqlNbij+hpK1k9XRloDtym8mxzGYl2c17LnV6IAGB2Dmg4tEa7G7DlawS0+qjew==
  dependencies:
    "@babel/runtime" "^7.1.2"
    loose-envify "^1.2.0"
    resolve-pathname "^3.0.0"
    tiny-invariant "^1.0.2"
    tiny-warning "^1.0.0"
    value-equal "^1.0.1"

hoist-non-react-statics@^3.1.0:
  version "3.3.2"
  resolved "https://registry.npmmirror.com/hoist-non-react-statics/-/hoist-non-react-statics-3.3.2.tgz#ece0acaf71d62c2969c2ec59feff42a4b1a85b45"
  integrity sha512-/gGivxi8JPKWNm/W0jSmzcMPpfpPLc3dY/6GxhX2hQ9iGj3aDfklV4ET7NjKpSinLpJ5vafa9iiGIEZg10SfBw==
  dependencies:
    react-is "^16.7.0"

hpack.js@^2.1.6:
  version "2.1.6"
  resolved "https://registry.npmmirror.com/hpack.js/-/hpack.js-2.1.6.tgz#87774c0949e513f42e84575b3c45681fade2a0b2"
  integrity sha512-zJxVehUdMGIKsRaNt7apO2Gqp0BdqW5yaiGHXXmbpvxgBYVZnAql+BJb4RO5ad2MgpbZKn5G6nMnegrH1FcNYQ==
  dependencies:
    inherits "^2.0.1"
    obuf "^1.0.0"
    readable-stream "^2.0.1"
    wbuf "^1.1.0"

html-entities@^2.3.2:
  version "2.3.3"
  resolved "https://registry.npmmirror.com/html-entities/-/html-entities-2.3.3.tgz#117d7626bece327fc8baace8868fa6f5ef856e46"
  integrity sha512-DV5Ln36z34NNTDgnz0EWGBLZENelNAtkiFA4kyNOG2tDI6Mz1uSWiq1wAKdyjnJwyDiDO7Fa2SO1CTxPXL8VxA==

html-minifier-terser@^6.0.2:
  version "6.1.0"
  resolved "https://registry.npmmirror.com/html-minifier-terser/-/html-minifier-terser-6.1.0.tgz#bfc818934cc07918f6b3669f5774ecdfd48f32ab"
  integrity sha512-YXxSlJBZTP7RS3tWnQw74ooKa6L9b9i9QYXY21eUEvhZ3u9XLfv6OnFsQq6RxkhHygsaUMvYsZRV5rU/OVNZxw==
  dependencies:
    camel-case "^4.1.2"
    clean-css "^5.2.2"
    commander "^8.3.0"
    he "^1.2.0"
    param-case "^3.0.4"
    relateurl "^0.2.7"
    terser "^5.10.0"

html-tags@^3.1.0:
  version "3.2.0"
  resolved "https://registry.npmmirror.com/html-tags/-/html-tags-3.2.0.tgz#dbb3518d20b726524e4dd43de397eb0a95726961"
  integrity sha512-vy7ClnArOZwCnqZgvv+ddgHgJiAFXe3Ge9ML5/mBctVJoUoYPCdxVucOywjDARn6CVoh3dRSFdPHy2sX80L0Wg==

html-void-elements@^1.0.0:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/html-void-elements/-/html-void-elements-1.0.5.tgz#ce9159494e86d95e45795b166c2021c2cfca4483"
  integrity sha512-uE/TxKuyNIcx44cIWnjr/rfIATDH7ZaOMmstu0CwhFG1Dunhlp4OC6/NMbhiwoq5BpW0ubi303qnEk/PZj614w==

html-webpack-plugin@^5.4.0:
  version "5.5.0"
  resolved "https://registry.npmmirror.com/html-webpack-plugin/-/html-webpack-plugin-5.5.0.tgz#c3911936f57681c1f9f4d8b68c158cd9dfe52f50"
  integrity sha512-sy88PC2cRTVxvETRgUHFrL4No3UxvcH8G1NepGhqaTT+GXN2kTamqasot0inS5hXeg1cMbFDt27zzo9p35lZVw==
  dependencies:
    "@types/html-minifier-terser" "^6.0.0"
    html-minifier-terser "^6.0.2"
    lodash "^4.17.21"
    pretty-error "^4.0.0"
    tapable "^2.0.0"

htmlparser2@^6.1.0:
  version "6.1.0"
  resolved "https://registry.npmmirror.com/htmlparser2/-/htmlparser2-6.1.0.tgz#c4d762b6c3371a05dbe65e94ae43a9f845fb8fb7"
  integrity sha512-gyyPk6rgonLFEDGoeRgQNaEUvdJ4ktTmmUh/h2t7s+M8oPpIPxgNACWa+6ESR57kXstwqPiCut0V8NRpcwgU7A==
  dependencies:
    domelementtype "^2.0.1"
    domhandler "^4.0.0"
    domutils "^2.5.2"
    entities "^2.0.0"

htmlparser2@^8.0.1:
  version "8.0.1"
  resolved "https://registry.npmmirror.com/htmlparser2/-/htmlparser2-8.0.1.tgz#abaa985474fcefe269bc761a779b544d7196d010"
  integrity sha512-4lVbmc1diZC7GUJQtRQ5yBAeUCL1exyMwmForWkRLnwyzWBFxN633SALPMGYaWZvKe9j1pRZJpauvmxENSp/EA==
  dependencies:
    domelementtype "^2.3.0"
    domhandler "^5.0.2"
    domutils "^3.0.1"
    entities "^4.3.0"

http-cache-semantics@4.1.1, http-cache-semantics@^4.0.0:
  version "4.1.1"
  resolved "https://registry.yarnpkg.com/http-cache-semantics/-/http-cache-semantics-4.1.1.tgz#abe02fcb2985460bf0323be664436ec3476a6d5a"
  integrity sha512-er295DKPVsV82j5kw1Gjt+ADA/XYHsajl82cGNQG2eyoPkvgUhX+nDIyelzhIWbbsXP39EHcI6l5tYs2FYqYXQ==

http-deceiver@^1.2.7:
  version "1.2.7"
  resolved "https://registry.npmmirror.com/http-deceiver/-/http-deceiver-1.2.7.tgz#fa7168944ab9a519d337cb0bec7284dc3e723d87"
  integrity sha512-LmpOGxTfbpgtGVxJrj5k7asXHCgNZp5nLfp+hWc8QQRqtb7fUy6kRY3BO1h9ddF6yIPYUARgxGOwB42DnxIaNw==

http-errors@2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/http-errors/-/http-errors-2.0.0.tgz#b7774a1486ef73cf7667ac9ae0858c012c57b9d3"
  integrity sha512-FtwrG/euBzaEjYeRqOgly7G0qviiXoJWnvEH2Z1plBdXgbyjv34pHTSb9zoeHMyDy33+DWy5Wt9Wo+TURtOYSQ==
  dependencies:
    depd "2.0.0"
    inherits "2.0.4"
    setprototypeof "1.2.0"
    statuses "2.0.1"
    toidentifier "1.0.1"

http-errors@~1.6.2:
  version "1.6.3"
  resolved "https://registry.npmmirror.com/http-errors/-/http-errors-1.6.3.tgz#8b55680bb4be283a0b5bf4ea2e38580be1d9320d"
  integrity sha512-lks+lVC8dgGyh97jxvxeYTWQFvh4uw4yC12gVl63Cg30sjPX4wuGcdkICVXDAESr6OJGjqGA8Iz5mkeN6zlD7A==
  dependencies:
    depd "~1.1.2"
    inherits "2.0.3"
    setprototypeof "1.1.0"
    statuses ">= 1.4.0 < 2"

http-parser-js@>=0.5.1:
  version "0.5.8"
  resolved "https://registry.npmmirror.com/http-parser-js/-/http-parser-js-0.5.8.tgz#af23090d9ac4e24573de6f6aecc9d84a48bf20e3"
  integrity sha512-SGeBX54F94Wgu5RH3X5jsDtf4eHyRogWX1XGT3b4HuW3tQPM4AaBzoUji/4AAJNXCEOWZ5O0DgZmJw1947gD5Q==

http-proxy-middleware@^2.0.3:
  version "2.0.6"
  resolved "https://registry.npmmirror.com/http-proxy-middleware/-/http-proxy-middleware-2.0.6.tgz#e1a4dd6979572c7ab5a4e4b55095d1f32a74963f"
  integrity sha512-ya/UeJ6HVBYxrgYotAZo1KvPWlgB48kUJLDePFeneHsVujFaW5WNj2NgWCAE//B1Dl02BIfYlpNgBy8Kf8Rjmw==
  dependencies:
    "@types/http-proxy" "^1.17.8"
    http-proxy "^1.18.1"
    is-glob "^4.0.1"
    is-plain-obj "^3.0.0"
    micromatch "^4.0.2"

http-proxy@^1.18.1:
  version "1.18.1"
  resolved "https://registry.npmmirror.com/http-proxy/-/http-proxy-1.18.1.tgz#401541f0534884bbf95260334e72f88ee3976549"
  integrity sha512-7mz/721AbnJwIVbnaSv1Cz3Am0ZLT/UBwkC92VlxhXv/k/BBQfM2fXElQNC27BVGr0uwUpplYPQM9LnaBMR5NQ==
  dependencies:
    eventemitter3 "^4.0.0"
    follow-redirects "^1.0.0"
    requires-port "^1.0.0"

http2-wrapper@^1.0.0-beta.5.2:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/http2-wrapper/-/http2-wrapper-1.0.3.tgz#b8f55e0c1f25d4ebd08b3b0c2c079f9590800b3d"
  integrity sha512-V+23sDMr12Wnz7iTcDeJr3O6AIxlnvT/bmaAAAP/Xda35C90p9599p0F1eHR/N1KILWSoWVAiOMFjBBXaXSMxg==
  dependencies:
    quick-lru "^5.1.1"
    resolve-alpn "^1.0.0"

human-signals@^2.1.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/human-signals/-/human-signals-2.1.0.tgz#dc91fcba42e4d06e4abaed33b3e7a3c02f514ea0"
  integrity sha512-B4FFZ6q/T2jhhksgkbEW3HBvWIfDW85snkQgawt07S7J5QXTk6BkNV+0yAeZrM5QpMAdYlocGoljn0sJ/WQkFw==

iconv-lite@0.4.24:
  version "0.4.24"
  resolved "https://registry.npmmirror.com/iconv-lite/-/iconv-lite-0.4.24.tgz#2022b4b25fbddc21d2f524974a474aafe733908b"
  integrity sha512-v3MXnZAcvnywkTUEZomIActle7RXXeedOR31wwl7VlyoXO4Qi9arvSenNQWne1TcRwhCL1HwLI21bEqdpj8/rA==
  dependencies:
    safer-buffer ">= 2.1.2 < 3"

icss-utils@^5.0.0, icss-utils@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/icss-utils/-/icss-utils-5.1.0.tgz#c6be6858abd013d768e98366ae47e25d5887b1ae"
  integrity sha512-soFhflCVWLfRNOPU3iv5Z9VUdT44xFRbzjLsEzSr5AQmgqPMTHdU3PMT1Cf1ssx8fLNJDA1juftYl+PUcv3MqA==

ignore@^5.2.0:
  version "5.2.0"
  resolved "https://registry.npmmirror.com/ignore/-/ignore-5.2.0.tgz#6d3bac8fa7fe0d45d9f9be7bac2fc279577e345a"
  integrity sha512-CmxgYGiEPCLhfLnpPp1MoRmifwEIOgjcHXxOBjv7mY96c+eWScsOP9c112ZyLdWHi0FxHjI+4uVhKYp/gcdRmQ==

immediate@^3.2.3:
  version "3.3.0"
  resolved "https://registry.npmmirror.com/immediate/-/immediate-3.3.0.tgz#1aef225517836bcdf7f2a2de2600c79ff0269266"
  integrity sha512-HR7EVodfFUdQCTIeySw+WDRFJlPcLOJbXfwwZ7Oom6tjsvZ3bOkCDJHehQC3nxJrv7+f9XecwazynjU8e4Vw3Q==

immer@^9.0.6:
  version "9.0.16"
  resolved "https://registry.npmmirror.com/immer/-/immer-9.0.16.tgz#8e7caab80118c2b54b37ad43e05758cdefad0198"
  integrity sha512-qenGE7CstVm1NrHQbMh8YaSzTZTFNP3zPqr3YU0S0UY441j4bJTg4A2Hh5KAhwgaiU6ZZ1Ar6y/2f4TblnMReQ==

import-fresh@^3.1.0, import-fresh@^3.2.1, import-fresh@^3.2.2, import-fresh@^3.3.0:
  version "3.3.0"
  resolved "https://registry.npmmirror.com/import-fresh/-/import-fresh-3.3.0.tgz#37162c25fcb9ebaa2e6e53d5b4d88ce17d9e0c2b"
  integrity sha512-veYYhQa+D1QBKznvhUHxb8faxlrwUnxseDAbAp457E0wLNio2bOSKnjYDhMj+YiAq61xrMGhQk9iXVk5FzgQMw==
  dependencies:
    parent-module "^1.0.0"
    resolve-from "^4.0.0"

import-lazy@^2.1.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/import-lazy/-/import-lazy-2.1.0.tgz#05698e3d45c88e8d7e9d92cb0584e77f096f3e43"
  integrity sha512-m7ZEHgtw69qOGw+jwxXkHlrlIPdTGkyh66zXZ1ajZbxkDBNjSY/LGbmjc7h0s2ELsUDTAhFr55TrPSSqJGPG0A==

imurmurhash@^0.1.4:
  version "0.1.4"
  resolved "https://registry.npmmirror.com/imurmurhash/-/imurmurhash-0.1.4.tgz#9218b9b2b928a238b13dc4fb6b6d576f231453ea"
  integrity sha512-JmXMZ6wuvDmLiHEml9ykzqO6lwFbof0GG4IkcGaENdCRDDmMVnny7s5HsIgHCbaq0w2MyPhDqkhTUgS2LU2PHA==

indent-string@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/indent-string/-/indent-string-4.0.0.tgz#624f8f4497d619b2d9768531d58f4122854d7251"
  integrity sha512-EdDDZu4A2OyIK7Lr/2zG+w5jmbuk1DVBnEwREQvBzspBJkCEbRa8GxU1lghYcaGJCnRWibjDXlq779X1/y5xwg==

infima@0.2.0-alpha.34:
  version "0.2.0-alpha.34"
  resolved "https://registry.npmmirror.com/infima/-/infima-0.2.0-alpha.34.tgz#14a900d79a4de2013e025ac95749a4592f16ef6e"
  integrity sha512-Na6A2Tl56i1p9dzu7VOAT1Kmu3f5buz63Wvd+D9ZZWL6siQ47L7wkEZUICVKFgc5gERFZVZ/PoPB57Kl++h37Q==

inflight@^1.0.4:
  version "1.0.6"
  resolved "https://registry.npmmirror.com/inflight/-/inflight-1.0.6.tgz#49bd6331d7d02d0c09bc910a1075ba8165b56df9"
  integrity sha512-k92I/b08q4wvFscXCLvqfsHCrjrF7yiXsQuIVvVE7N82W3+aqpzuUdBbfhWcy/FZR3/4IgflMgKLOsvPDrGCJA==
  dependencies:
    once "^1.3.0"
    wrappy "1"

inherits@2, inherits@2.0.4, inherits@^2.0.0, inherits@^2.0.1, inherits@^2.0.3, inherits@~2.0.3:
  version "2.0.4"
  resolved "https://registry.npmmirror.com/inherits/-/inherits-2.0.4.tgz#0fa2c64f932917c3433a0ded55363aae37416b7c"
  integrity sha512-k/vGaX4/Yla3WzyMCvTQOXYeIHvqOKtnqBduzTHpzpQZzAskKMhZ2K+EnBiSM9zGSoIFeMpXKxa4dYeZIQqewQ==

inherits@2.0.3:
  version "2.0.3"
  resolved "https://registry.npmmirror.com/inherits/-/inherits-2.0.3.tgz#633c2c83e3da42a502f52466022480f4208261de"
  integrity sha512-x00IRNXNy63jwGkJmzPigoySHbaqpNuzKbBOmzK+g2OdZpQ9w+sxCN+VSB3ja7IAge2OP2qpfxTjeNcyjmW1uw==

ini@2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/ini/-/ini-2.0.0.tgz#e5fd556ecdd5726be978fa1001862eacb0a94bc5"
  integrity sha512-7PnF4oN3CvZF23ADhA5wRaYEQpJ8qygSkbtTXWBeXWXmEVRXK+1ITciHWwHhsjv1TmW0MgacIv6hEi5pX5NQdA==

ini@^1.3.5, ini@~1.3.0:
  version "1.3.8"
  resolved "https://registry.npmmirror.com/ini/-/ini-1.3.8.tgz#a29da425b48806f34767a4efce397269af28432c"
  integrity sha512-JV/yugV2uzW5iMRSiZAyDtQd+nxtUnjeLt0acNdw98kKLrvuRVyB80tsREOE7yvGVgalhZ6RNXCmEHkUKBKxew==

inline-style-parser@0.1.1:
  version "0.1.1"
  resolved "https://registry.npmmirror.com/inline-style-parser/-/inline-style-parser-0.1.1.tgz#ec8a3b429274e9c0a1f1c4ffa9453a7fef72cea1"
  integrity sha512-7NXolsK4CAS5+xvdj5OMMbI962hU/wvwoxk+LWR9Ek9bVtyuuYScDN6eS0rUm6TxApFpw7CX1o4uJzcd4AyD3Q==

internal-slot@^1.0.3:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/internal-slot/-/internal-slot-1.0.3.tgz#7347e307deeea2faac2ac6205d4bc7d34967f59c"
  integrity sha512-O0DB1JC/sPyZl7cIo78n5dR7eUSwwpYPiXRhTzNxZVAMUuB8vlnRFyLxdrVToks6XPLVnFfbzaVd5WLjhgg+vA==
  dependencies:
    get-intrinsic "^1.1.0"
    has "^1.0.3"
    side-channel "^1.0.4"

interpret@^1.0.0:
  version "1.4.0"
  resolved "https://registry.npmmirror.com/interpret/-/interpret-1.4.0.tgz#665ab8bc4da27a774a40584e812e3e0fa45b1a1e"
  integrity sha512-agE4QfB2Lkp9uICn7BAqoscw4SZP9kTE2hxiFI3jBPmXJfdqiahTbUuKGsMoN2GtqL9AxhYioAcVvgsb1HvRbA==

ipaddr.js@1.9.1:
  version "1.9.1"
  resolved "https://registry.npmmirror.com/ipaddr.js/-/ipaddr.js-1.9.1.tgz#bff38543eeb8984825079ff3a2a8e6cbd46781b3"
  integrity sha512-0KI/607xoxSToH7GjN1FfSbLoU0+btTicjsQSWQlh/hZykN8KpmMf7uYwPW3R+akZ6R/w18ZlXSHBYXiYUPO3g==

ipaddr.js@^2.0.1:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/ipaddr.js/-/ipaddr.js-2.0.1.tgz#eca256a7a877e917aeb368b0a7497ddf42ef81c0"
  integrity sha512-1qTgH9NG+IIJ4yfKs2e6Pp1bZg8wbDbKHT21HrLIeYBTRLgMYKnMTPAuI3Lcs61nfx5h1xlXnbJtH1kX5/d/ng==

is-alphabetical@1.0.4, is-alphabetical@^1.0.0:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/is-alphabetical/-/is-alphabetical-1.0.4.tgz#9e7d6b94916be22153745d184c298cbf986a686d"
  integrity sha512-DwzsA04LQ10FHTZuL0/grVDk4rFoVH1pjAToYwBrHSxcrBIGQuXrQMtD5U1b0U2XVgKZCTLLP8u2Qxqhy3l2Vg==

is-alphanumerical@^1.0.0:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/is-alphanumerical/-/is-alphanumerical-1.0.4.tgz#7eb9a2431f855f6b1ef1a78e326df515696c4dbf"
  integrity sha512-UzoZUr+XfVz3t3v4KyGEniVL9BDRoQtY7tOyrRybkVNjDFWyo1yhXNGrrBTQxp3ib9BLAWs7k2YKBQsFRkZG9A==
  dependencies:
    is-alphabetical "^1.0.0"
    is-decimal "^1.0.0"

is-arrayish@^0.2.1:
  version "0.2.1"
  resolved "https://registry.npmmirror.com/is-arrayish/-/is-arrayish-0.2.1.tgz#77c99840527aa8ecb1a8ba697b80645a7a926a9d"
  integrity sha512-zz06S8t0ozoDXMG+ube26zeCTNXcKIPJZJi8hBrF4idCLms4CG9QtK7qBl1boi5ODzFpjswb5JPmHCbMpjaYzg==

is-bigint@^1.0.1:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/is-bigint/-/is-bigint-1.0.4.tgz#08147a1875bc2b32005d41ccd8291dffc6691df3"
  integrity sha512-zB9CruMamjym81i2JZ3UMn54PKGsQzsJeo6xvN3HJJ4CAsQNB6iRutp2To77OfCNuoxspsIhzaPoO1zyCEhFOg==
  dependencies:
    has-bigints "^1.0.1"

is-binary-path@~2.1.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/is-binary-path/-/is-binary-path-2.1.0.tgz#ea1f7f3b80f064236e83470f86c09c254fb45b09"
  integrity sha512-ZMERYes6pDydyuGidse7OsHxtbI7WVeUEozgR/g7rd0xUimYNlvZRE/K2MgZTjWy725IfelLeVcEM97mmtRGXw==
  dependencies:
    binary-extensions "^2.0.0"

is-boolean-object@^1.1.0:
  version "1.1.2"
  resolved "https://registry.npmmirror.com/is-boolean-object/-/is-boolean-object-1.1.2.tgz#5c6dc200246dd9321ae4b885a114bb1f75f63719"
  integrity sha512-gDYaKHJmnj4aWxyj6YHyXVpdQawtVLHU5cb+eztPGczf6cjuTdwve5ZIEfgXqH4e57An1D1AKf8CZ3kYrQRqYA==
  dependencies:
    call-bind "^1.0.2"
    has-tostringtag "^1.0.0"

is-buffer@^2.0.0:
  version "2.0.5"
  resolved "https://registry.npmmirror.com/is-buffer/-/is-buffer-2.0.5.tgz#ebc252e400d22ff8d77fa09888821a24a658c191"
  integrity sha512-i2R6zNFDwgEHJyQUtJEk0XFi1i0dPFn/oqjK3/vPCcDeJvW5NQ83V8QbicfF1SupOaB0h8ntgBC2YiE7dfyctQ==

is-callable@^1.1.4, is-callable@^1.2.7:
  version "1.2.7"
  resolved "https://registry.npmmirror.com/is-callable/-/is-callable-1.2.7.tgz#3bc2a85ea742d9e36205dcacdd72ca1fdc51b055"
  integrity sha512-1BC0BVFhS/p0qtw6enp8e+8OD0UrK0oFLztSjNzhcKA3WDuJxxAPXzPuPtKkjEY9UUoEWlX/8fgKeu2S8i9JTA==

is-ci@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/is-ci/-/is-ci-2.0.0.tgz#6bc6334181810e04b5c22b3d589fdca55026404c"
  integrity sha512-YfJT7rkpQB0updsdHLGWrvhBJfcfzNNawYDNIyQXJz0IViGf75O8EBPKSdvw2rF+LGCsX4FZ8tcr3b19LcZq4w==
  dependencies:
    ci-info "^2.0.0"

is-core-module@^2.9.0:
  version "2.11.0"
  resolved "https://registry.npmmirror.com/is-core-module/-/is-core-module-2.11.0.tgz#ad4cb3e3863e814523c96f3f58d26cc570ff0144"
  integrity sha512-RRjxlvLDkD1YJwDbroBHMb+cukurkDWNyHx7D3oNB5x9rb5ogcksMC5wHCadcXoo67gVr/+3GFySh3134zi6rw==
  dependencies:
    has "^1.0.3"

is-date-object@^1.0.1:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/is-date-object/-/is-date-object-1.0.5.tgz#0841d5536e724c25597bf6ea62e1bd38298df31f"
  integrity sha512-9YQaSxsAiSwcvS33MBk3wTCVnWK+HhF8VZR2jRxehM16QcVOdHqPn4VPHmRK4lSr38n9JriurInLcP90xsYNfQ==
  dependencies:
    has-tostringtag "^1.0.0"

is-decimal@^1.0.0:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/is-decimal/-/is-decimal-1.0.4.tgz#65a3a5958a1c5b63a706e1b333d7cd9f630d3fa5"
  integrity sha512-RGdriMmQQvZ2aqaQq3awNA6dCGtKpiDFcOzrTWrDAT2MiWrKQVPmxLGHl7Y2nNu6led0kEyoX0enY0qXYsv9zw==

is-docker@^2.0.0, is-docker@^2.1.1:
  version "2.2.1"
  resolved "https://registry.npmmirror.com/is-docker/-/is-docker-2.2.1.tgz#33eeabe23cfe86f14bde4408a02c0cfb853acdaa"
  integrity sha512-F+i2BKsFrH66iaUFc0woD8sLy8getkwTwtOBjvs56Cx4CgJDeKQeqfz8wAYiSb8JOprWhHH5p77PbmYCvvUuXQ==

is-extendable@^0.1.0:
  version "0.1.1"
  resolved "https://registry.npmmirror.com/is-extendable/-/is-extendable-0.1.1.tgz#62b110e289a471418e3ec36a617d472e301dfc89"
  integrity sha512-5BMULNob1vgFX6EjQw5izWDxrecWK9AM72rugNr0TFldMOi0fj6Jk+zeKIt0xGj4cEfQIJth4w3OKWOJ4f+AFw==

is-extglob@^2.1.1:
  version "2.1.1"
  resolved "https://registry.npmmirror.com/is-extglob/-/is-extglob-2.1.1.tgz#a88c02535791f02ed37c76a1b9ea9773c833f8c2"
  integrity sha512-SbKbANkN603Vi4jEZv49LeVJMn4yGwsbzZworEoyEiutsN3nJYdbO36zfhGJ6QEDpOZIFkDtnq5JRxmvl3jsoQ==

is-fullwidth-code-point@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/is-fullwidth-code-point/-/is-fullwidth-code-point-3.0.0.tgz#f116f8064fe90b3f7844a38997c0b75051269f1d"
  integrity sha512-zymm5+u+sCsSWyD9qNaejV3DFvhCKclKdizYaJUuHA83RLjb7nSuGnddCHGv0hk+KY7BMAlsWeK4Ueg6EV6XQg==

is-glob@^4.0.1, is-glob@^4.0.3, is-glob@~4.0.1:
  version "4.0.3"
  resolved "https://registry.npmmirror.com/is-glob/-/is-glob-4.0.3.tgz#64f61e42cbbb2eec2071a9dac0b28ba1e65d5084"
  integrity sha512-xelSayHH36ZgE7ZWhli7pW34hNbNl8Ojv5KVmkJD4hBdD3th8Tfk9vYasLM+mXWOZhFkgZfxhLSnrwRr4elSSg==
  dependencies:
    is-extglob "^2.1.1"

is-hexadecimal@^1.0.0:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/is-hexadecimal/-/is-hexadecimal-1.0.4.tgz#cc35c97588da4bd49a8eedd6bc4082d44dcb23a7"
  integrity sha512-gyPJuv83bHMpocVYoqof5VDiZveEoGoFL8m3BXNb2VW8Xs+rz9kqO8LOQ5DH6EsuvilT1ApazU0pyl+ytbPtlw==

is-installed-globally@^0.4.0:
  version "0.4.0"
  resolved "https://registry.npmmirror.com/is-installed-globally/-/is-installed-globally-0.4.0.tgz#9a0fd407949c30f86eb6959ef1b7994ed0b7b520"
  integrity sha512-iwGqO3J21aaSkC7jWnHP/difazwS7SFeIqxv6wEtLU8Y5KlzFTjyqcSIT0d8s4+dDhKytsk9PJZ2BkS5eZwQRQ==
  dependencies:
    global-dirs "^3.0.0"
    is-path-inside "^3.0.2"

is-negative-zero@^2.0.2:
  version "2.0.2"
  resolved "https://registry.npmmirror.com/is-negative-zero/-/is-negative-zero-2.0.2.tgz#7bf6f03a28003b8b3965de3ac26f664d765f3150"
  integrity sha512-dqJvarLawXsFbNDeJW7zAz8ItJ9cd28YufuuFzh0G8pNHjJMnY08Dv7sYX2uF5UpQOwieAeOExEYAWWfu7ZZUA==

is-npm@^5.0.0:
  version "5.0.0"
  resolved "https://registry.npmmirror.com/is-npm/-/is-npm-5.0.0.tgz#43e8d65cc56e1b67f8d47262cf667099193f45a8"
  integrity sha512-WW/rQLOazUq+ST/bCAVBp/2oMERWLsR7OrKyt052dNDk4DHcDE0/7QSXITlmi+VBcV13DfIbysG3tZJm5RfdBA==

is-number-object@^1.0.4:
  version "1.0.7"
  resolved "https://registry.npmmirror.com/is-number-object/-/is-number-object-1.0.7.tgz#59d50ada4c45251784e9904f5246c742f07a42fc"
  integrity sha512-k1U0IRzLMo7ZlYIfzRu23Oh6MiIFasgpb9X76eqfFZAqwH44UI4KTBvBYIZ1dSL9ZzChTB9ShHfLkR4pdW5krQ==
  dependencies:
    has-tostringtag "^1.0.0"

is-number@^7.0.0:
  version "7.0.0"
  resolved "https://registry.npmmirror.com/is-number/-/is-number-7.0.0.tgz#7535345b896734d5f80c4d06c50955527a14f12b"
  integrity sha512-41Cifkg6e8TylSpdtTpeLVMqvSBEVzTttHvERD741+pnZ8ANv0004MRL43QKPDlK9cGvNp6NZWZUBlbGXYxxng==

is-obj@^1.0.1:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/is-obj/-/is-obj-1.0.1.tgz#3e4729ac1f5fde025cd7d83a896dab9f4f67db0f"
  integrity sha512-l4RyHgRqGN4Y3+9JHVrNqO+tN0rV5My76uW5/nuO4K1b6vw5G8d/cmFjP9tRfEsdhZNt0IFdZuK/c2Vr4Nb+Qg==

is-obj@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/is-obj/-/is-obj-2.0.0.tgz#473fb05d973705e3fd9620545018ca8e22ef4982"
  integrity sha512-drqDG3cbczxxEJRoOXcOjtdp1J/lyp1mNn0xaznRs8+muBhgQcrnbspox5X5fOw0HnMnbfDzvnEMEtqDEJEo8w==

is-path-cwd@^2.2.0:
  version "2.2.0"
  resolved "https://registry.npmmirror.com/is-path-cwd/-/is-path-cwd-2.2.0.tgz#67d43b82664a7b5191fd9119127eb300048a9fdb"
  integrity sha512-w942bTcih8fdJPJmQHFzkS76NEP8Kzzvmw92cXsazb8intwLqPibPPdXf4ANdKV3rYMuuQYGIWtvz9JilB3NFQ==

is-path-inside@^3.0.2:
  version "3.0.3"
  resolved "https://registry.npmmirror.com/is-path-inside/-/is-path-inside-3.0.3.tgz#d231362e53a07ff2b0e0ea7fed049161ffd16283"
  integrity sha512-Fd4gABb+ycGAmKou8eMftCupSir5lRxqf4aD/vd0cD2qc4HL07OjCeuHMr8Ro4CoMaeCKDB0/ECBOVWjTwUvPQ==

is-plain-obj@^2.0.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/is-plain-obj/-/is-plain-obj-2.1.0.tgz#45e42e37fccf1f40da8e5f76ee21515840c09287"
  integrity sha512-YWnfyRwxL/+SsrWYfOpUtz5b3YD+nyfkHvjbcanzk8zgyO4ASD67uVMRt8k5bM4lLMDnXfriRhOpemw+NfT1eA==

is-plain-obj@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/is-plain-obj/-/is-plain-obj-3.0.0.tgz#af6f2ea14ac5a646183a5bbdb5baabbc156ad9d7"
  integrity sha512-gwsOE28k+23GP1B6vFl1oVh/WOzmawBrKwo5Ev6wMKzPkaXaCDIQKzLnvsA42DRlbVTWorkgTKIviAKCWkfUwA==

is-plain-object@^2.0.4:
  version "2.0.4"
  resolved "https://registry.npmmirror.com/is-plain-object/-/is-plain-object-2.0.4.tgz#2c163b3fafb1b606d9d17928f05c2a1c38e07677"
  integrity sha512-h5PpgXkWitc38BBMYawTYMWJHFZJVnBquFE57xFpjB8pJFiF6gZ+bU+WyI/yqXiFR5mdLsgYNaPe8uao6Uv9Og==
  dependencies:
    isobject "^3.0.1"

is-regex@^1.1.4:
  version "1.1.4"
  resolved "https://registry.npmmirror.com/is-regex/-/is-regex-1.1.4.tgz#eef5663cd59fa4c0ae339505323df6854bb15958"
  integrity sha512-kvRdxDsxZjhzUX07ZnLydzS1TU/TJlTUHHY4YLL87e37oUA49DfkLqgy+VjFocowy29cKvcSiu+kIv728jTTVg==
  dependencies:
    call-bind "^1.0.2"
    has-tostringtag "^1.0.0"

is-regexp@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/is-regexp/-/is-regexp-1.0.0.tgz#fd2d883545c46bac5a633e7b9a09e87fa2cb5069"
  integrity sha512-7zjFAPO4/gwyQAAgRRmqeEeyIICSdmCqa3tsVHMdBzaXXRiqopZL4Cyghg/XulGWrtABTpbnYYzzIRffLkP4oA==

is-root@^2.1.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/is-root/-/is-root-2.1.0.tgz#809e18129cf1129644302a4f8544035d51984a9c"
  integrity sha512-AGOriNp96vNBd3HtU+RzFEc75FfR5ymiYv8E553I71SCeXBiMsVDUtdio1OEFvrPyLIQ9tVR5RxXIFe5PUFjMg==

is-shared-array-buffer@^1.0.2:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/is-shared-array-buffer/-/is-shared-array-buffer-1.0.2.tgz#8f259c573b60b6a32d4058a1a07430c0a7344c79"
  integrity sha512-sqN2UDu1/0y6uvXyStCOzyhAjCSlHceFoMKJW8W9EU9cvic/QdsZ0kEU93HEy3IUEFZIiH/3w+AH/UQbPHNdhA==
  dependencies:
    call-bind "^1.0.2"

is-stream@^2.0.0:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/is-stream/-/is-stream-2.0.1.tgz#fac1e3d53b97ad5a9d0ae9cef2389f5810a5c077"
  integrity sha512-hFoiJiTl63nn+kstHGBtewWSKnQLpyb155KHheA1l39uvtO9nWIop1p3udqPcUd/xbF1VLMO4n7OI6p7RbngDg==

is-string@^1.0.5, is-string@^1.0.7:
  version "1.0.7"
  resolved "https://registry.npmmirror.com/is-string/-/is-string-1.0.7.tgz#0dd12bf2006f255bb58f695110eff7491eebc0fd"
  integrity sha512-tE2UXzivje6ofPW7l23cjDOMa09gb7xlAqG6jG5ej6uPV32TlWP3NKPigtaGeHNu9fohccRYvIiZMfOOnOYUtg==
  dependencies:
    has-tostringtag "^1.0.0"

is-symbol@^1.0.2, is-symbol@^1.0.3:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/is-symbol/-/is-symbol-1.0.4.tgz#a6dac93b635b063ca6872236de88910a57af139c"
  integrity sha512-C/CPBqKWnvdcxqIARxyOh4v1UUEOCHpgDa0WYgpKDFMszcrPcffg5uhwSgPCLD2WWxmq6isisz87tzT01tuGhg==
  dependencies:
    has-symbols "^1.0.2"

is-typedarray@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/is-typedarray/-/is-typedarray-1.0.0.tgz#e479c80858df0c1b11ddda6940f96011fcda4a9a"
  integrity sha512-cyA56iCMHAh5CdzjJIa4aohJyeO1YbwLi3Jc35MmRU6poroFjIGZzUzupGiRPOjgHg9TLu43xbpwXk523fMxKA==

is-weakref@^1.0.2:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/is-weakref/-/is-weakref-1.0.2.tgz#9529f383a9338205e89765e0392efc2f100f06f2"
  integrity sha512-qctsuLZmIQ0+vSSMfoVvyFe2+GSEvnmZ2ezTup1SBse9+twCCeial6EEi3Nc2KFcf6+qz2FBPnjXsk8xhKSaPQ==
  dependencies:
    call-bind "^1.0.2"

is-whitespace-character@^1.0.0:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/is-whitespace-character/-/is-whitespace-character-1.0.4.tgz#0858edd94a95594c7c9dd0b5c174ec6e45ee4aa7"
  integrity sha512-SDweEzfIZM0SJV0EUga669UTKlmL0Pq8Lno0QDQsPnvECB3IM2aP0gdx5TrU0A01MAPfViaZiI2V1QMZLaKK5w==

is-word-character@^1.0.0:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/is-word-character/-/is-word-character-1.0.4.tgz#ce0e73216f98599060592f62ff31354ddbeb0230"
  integrity sha512-5SMO8RVennx3nZrqtKwCGyyetPE9VDba5ugvKLaD4KopPG5kR4mQ7tNt/r7feL5yt5h3lpuBbIUmCOG2eSzXHA==

is-wsl@^2.1.1, is-wsl@^2.2.0:
  version "2.2.0"
  resolved "https://registry.npmmirror.com/is-wsl/-/is-wsl-2.2.0.tgz#74a4c76e77ca9fd3f932f290c17ea326cd157271"
  integrity sha512-fKzAra0rGJUUBwGBgNkHZuToZcn+TtXHpeCgmkMJMMYx1sQDYaCSyjJBSCa2nH1DGm7s3n1oBnohoVTBaN7Lww==
  dependencies:
    is-docker "^2.0.0"

is-yarn-global@^0.3.0:
  version "0.3.0"
  resolved "https://registry.npmmirror.com/is-yarn-global/-/is-yarn-global-0.3.0.tgz#d502d3382590ea3004893746754c89139973e232"
  integrity sha512-VjSeb/lHmkoyd8ryPVIKvOCn4D1koMqY+vqyjjUfc3xyKtP4dYOxM44sZrnqQSzSds3xyOrUTLTC9LVCVgLngw==

isarray@0.0.1:
  version "0.0.1"
  resolved "https://registry.npmmirror.com/isarray/-/isarray-0.0.1.tgz#8a18acfca9a8f4177e09abfc6038939b05d1eedf"
  integrity sha512-D2S+3GLxWH+uhrNEcoh/fnmYeP8E8/zHl644d/jdA0g2uyXvy3sb0qxotE+ne0LtccHknQzWwZEzhak7oJ0COQ==

isarray@~1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/isarray/-/isarray-1.0.0.tgz#bb935d48582cba168c06834957a54a3e07124f11"
  integrity sha512-VLghIWNM6ELQzo7zwmcg0NmTVyWKYjvIeM83yjp0wRDTmUnrM678fQbcKBo6n2CJEF0szoG//ytg+TKla89ALQ==

isexe@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/isexe/-/isexe-2.0.0.tgz#e8fbf374dc556ff8947a10dcb0572d633f2cfa10"
  integrity sha512-RHxMLp9lnKHGHRng9QFhRCMbYAcVpn69smSGcq3f36xjgVVWThj4qqLbTLlq7Ssj8B+fIQ1EuCEGI2lKsyQeIw==

isobject@^3.0.1:
  version "3.0.1"
  resolved "https://registry.npmmirror.com/isobject/-/isobject-3.0.1.tgz#4e431e92b11a9731636aa1f9c8d1ccbcfdab78df"
  integrity sha512-WhB9zCku7EGTj/HQQRz5aUQEUeoQZH2bWcltRErOpymJ4boYE6wL9Tbr23krRPSZ+C5zqNSrSw+Cc7sZZ4b7vg==

jest-worker@^27.0.2, jest-worker@^27.4.5:
  version "27.5.1"
  resolved "https://registry.npmmirror.com/jest-worker/-/jest-worker-27.5.1.tgz#8d146f0900e8973b106b6f73cc1e9a8cb86f8db0"
  integrity sha512-7vuh85V5cdDofPyxn58nrPjBktZo0u9x1g8WtjQol+jZDaE+fhN+cIvTj11GndBnMnyfrUOG1sZQxCdjKh+DKg==
  dependencies:
    "@types/node" "*"
    merge-stream "^2.0.0"
    supports-color "^8.0.0"

joi@^17.4.2, joi@^17.6.0:
  version "17.7.0"
  resolved "https://registry.npmmirror.com/joi/-/joi-17.7.0.tgz#591a33b1fe1aca2bc27f290bcad9b9c1c570a6b3"
  integrity sha512-1/ugc8djfn93rTE3WRKdCzGGt/EtiYKxITMO4Wiv6q5JL1gl9ePt4kBsl1S499nbosspfctIQTpYIhSmHA3WAg==
  dependencies:
    "@hapi/hoek" "^9.0.0"
    "@hapi/topo" "^5.0.0"
    "@sideway/address" "^4.1.3"
    "@sideway/formula" "^3.0.0"
    "@sideway/pinpoint" "^2.0.0"

"js-tokens@^3.0.0 || ^4.0.0", js-tokens@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/js-tokens/-/js-tokens-4.0.0.tgz#19203fb59991df98e3a287050d4647cdeaf32499"
  integrity sha512-RdJUflcE3cUzKiMqQgsCu06FPu9UdIJO0beYbPhHN4k6apgJtifcoCtT9bcxOpYBtpD2kCM6Sbzg4CausW/PKQ==

js-yaml@^3.13.1:
  version "3.14.1"
  resolved "https://registry.npmmirror.com/js-yaml/-/js-yaml-3.14.1.tgz#dae812fdb3825fa306609a8717383c50c36a0537"
  integrity sha512-okMH7OXXJ7YrN9Ok3/SXrnu4iX9yOk+25nqX4imS2npuvTYDmo/QEZoqwZkYaIDk3jVvBOTOIEgEhaLOynBS9g==
  dependencies:
    argparse "^1.0.7"
    esprima "^4.0.0"

js-yaml@^4.0.0, js-yaml@^4.1.0:
  version "4.1.0"
  resolved "https://registry.npmmirror.com/js-yaml/-/js-yaml-4.1.0.tgz#c1fb65f8f5017901cdd2c951864ba18458a10602"
  integrity sha512-wpxZs9NoxZaJESJGIZTyDEaYpl0FKSA+FB9aJiyemKhMwkxQg63h4T1KJgUGHpTqPDNRcmmYLugrRjJlBtWvRA==
  dependencies:
    argparse "^2.0.1"

jsesc@^2.5.1:
  version "2.5.2"
  resolved "https://registry.npmmirror.com/jsesc/-/jsesc-2.5.2.tgz#80564d2e483dacf6e8ef209650a67df3f0c283a4"
  integrity sha512-OYu7XEzjkCQ3C5Ps3QIZsQfNpqoJyZZA99wd9aWd05NCtC5pWOkShK2mkL6HXQR6/Cy2lbNdPlZBpuQHXE63gA==

jsesc@~0.5.0:
  version "0.5.0"
  resolved "https://registry.npmmirror.com/jsesc/-/jsesc-0.5.0.tgz#e7dee66e35d6fc16f710fe91d5cf69f70f08911d"
  integrity sha512-uZz5UnB7u4T9LvwmFqXii7pZSouaRPorGs5who1Ip7VO0wxanFvBL7GkM6dTHlgX+jhBApRetaWpnDabOeTcnA==

json-buffer@3.0.1:
  version "3.0.1"
  resolved "https://registry.npmmirror.com/json-buffer/-/json-buffer-3.0.1.tgz#9338802a30d3b6605fbe0613e094008ca8c05a13"
  integrity sha512-4bV5BfR2mqfQTJm+V5tPPdf+ZpuhiIvTuAB5g8kcrXOZpTT/QwwVRWBywX1ozr6lEuPdbHxwaJlm9G6mI2sfSQ==

json-parse-even-better-errors@^2.3.0, json-parse-even-better-errors@^2.3.1:
  version "2.3.1"
  resolved "https://registry.npmmirror.com/json-parse-even-better-errors/-/json-parse-even-better-errors-2.3.1.tgz#7c47805a94319928e05777405dc12e1f7a4ee02d"
  integrity sha512-xyFwyhro/JEof6Ghe2iz2NcXoj2sloNsWr/XsERDK/oiPCfaNhl5ONfp+jQdAZRQQ0IJWNzH9zIZF7li91kh2w==

json-schema-traverse@^0.4.1:
  version "0.4.1"
  resolved "https://registry.npmmirror.com/json-schema-traverse/-/json-schema-traverse-0.4.1.tgz#69f6a87d9513ab8bb8fe63bdb0979c448e684660"
  integrity sha512-xbbCH5dCYU5T8LcEhhuh7HJ88HXuW3qsI3Y0zOZFKfZEHcpWiHU/Jxzk629Brsab/mMiHQti9wMP+845RPe3Vg==

json-schema-traverse@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/json-schema-traverse/-/json-schema-traverse-1.0.0.tgz#ae7bcb3656ab77a73ba5c49bf654f38e6b6860e2"
  integrity sha512-NM8/P9n3XjXhIZn1lLhkFaACTOURQXjWhV4BA/RnOv8xvgqtqpAX9IO4mRQxSx1Rlo4tqzeqb0sOlruaOy3dug==

json5@^2.1.2, json5@^2.2.1:
  version "2.2.3"
  resolved "https://registry.yarnpkg.com/json5/-/json5-2.2.3.tgz#78cd6f1a19bdc12b73db5ad0c61efd66c1e29283"
  integrity sha512-XmOWe7eyHYH14cLdVPoyg+GOH3rYX++KpzrylJwSW98t3Nk+U8XOl8FWKOgwtzdb8lXGf6zYwDUzeHMWfxasyg==

jsonfile@^6.0.1:
  version "6.1.0"
  resolved "https://registry.npmmirror.com/jsonfile/-/jsonfile-6.1.0.tgz#bc55b2634793c679ec6403094eb13698a6ec0aae"
  integrity sha512-5dgndWOriYSm5cnYaJNhalLNDKOqFwyDB/rr1E9ZsGciGvKPs8R2xYGCacuf3z6K1YKDz182fd+fY3cn3pMqXQ==
  dependencies:
    universalify "^2.0.0"
  optionalDependencies:
    graceful-fs "^4.1.6"

katex@^0.12.0:
  version "0.12.0"
  resolved "https://registry.npmmirror.com/katex/-/katex-0.12.0.tgz#2fb1c665dbd2b043edcf8a1f5c555f46beaa0cb9"
  integrity sha512-y+8btoc/CK70XqcHqjxiGWBOeIL8upbS0peTPXTvgrh21n1RiWWcIpSWM+4uXq+IAgNh9YYQWdc7LVDPDAEEAg==
  dependencies:
    commander "^2.19.0"

keyv@*, keyv@^4.0.0:
  version "4.5.0"
  resolved "https://registry.npmmirror.com/keyv/-/keyv-4.5.0.tgz#dbce9ade79610b6e641a9a65f2f6499ba06b9bc6"
  integrity sha512-2YvuMsA+jnFGtBareKqgANOEKe1mk3HKiXu2fRmAfyxG0MJAywNhi5ttWA3PMjl4NmpyjZNbFifR2vNjW1znfA==
  dependencies:
    json-buffer "3.0.1"

kind-of@^6.0.0, kind-of@^6.0.2:
  version "6.0.3"
  resolved "https://registry.npmmirror.com/kind-of/-/kind-of-6.0.3.tgz#07c05034a6c349fa06e24fa35aa76db4580ce4dd"
  integrity sha512-dcS1ul+9tmeD95T+x28/ehLgd9mENa3LsvDTtzm3vyBEO7RPptvAD+t44WVXaUjTBRcrpFeFlC8WCruUR456hw==

klaw-sync@^6.0.0:
  version "6.0.0"
  resolved "https://registry.npmmirror.com/klaw-sync/-/klaw-sync-6.0.0.tgz#1fd2cfd56ebb6250181114f0a581167099c2b28c"
  integrity sha512-nIeuVSzdCCs6TDPTqI8w1Yre34sSq7AkZ4B3sfOBbI2CgVSB4Du4aLQijFU2+lhAFCwt9+42Hel6lQNIv6AntQ==
  dependencies:
    graceful-fs "^4.1.11"

kleur@^3.0.3:
  version "3.0.3"
  resolved "https://registry.npmmirror.com/kleur/-/kleur-3.0.3.tgz#a79c9ecc86ee1ce3fa6206d1216c501f147fc07e"
  integrity sha512-eTIzlVOSUR+JxdDFepEYcBMtZ9Qqdef+rnzWdRZuMbOywu5tO2w2N7rqjoANZ5k9vywhL6Br1VRjUIgTQx4E8w==

klona@^2.0.5:
  version "2.0.5"
  resolved "https://registry.npmmirror.com/klona/-/klona-2.0.5.tgz#d166574d90076395d9963aa7a928fabb8d76afbc"
  integrity sha512-pJiBpiXMbt7dkzXe8Ghj/u4FfXOOa98fPW+bihOJ4SjnoijweJrNThJfd3ifXpXhREjpoF2mZVH1GfS9LV3kHQ==

latest-version@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/latest-version/-/latest-version-5.1.0.tgz#119dfe908fe38d15dfa43ecd13fa12ec8832face"
  integrity sha512-weT+r0kTkRQdCdYCNtkMwWXQTMEswKrFBkm4ckQOMVhhqhIMI1UT2hMj+1iigIhgSZm5gTmrRXBNoGUgaTY1xA==
  dependencies:
    package-json "^6.3.0"

leven@^3.1.0:
  version "3.1.0"
  resolved "https://registry.npmmirror.com/leven/-/leven-3.1.0.tgz#77891de834064cccba82ae7842bb6b14a13ed7f2"
  integrity sha512-qsda+H8jTaUaN/x5vzW2rzc+8Rw4TAQ/4KjB46IwK5VH+IlVeeeje/EoZRpiXvIqjFgK84QffqPztGI3VBLG1A==

lilconfig@^2.0.3:
  version "2.0.6"
  resolved "https://registry.npmmirror.com/lilconfig/-/lilconfig-2.0.6.tgz#32a384558bd58af3d4c6e077dd1ad1d397bc69d4"
  integrity sha512-9JROoBW7pobfsx+Sq2JsASvCo6Pfo6WWoUW79HuB1BCoBXD4PLWJPqDF6fNj67pqBYTbAHkE57M1kS/+L1neOg==

lines-and-columns@^1.1.6:
  version "1.2.4"
  resolved "https://registry.npmmirror.com/lines-and-columns/-/lines-and-columns-1.2.4.tgz#eca284f75d2965079309dc0ad9255abb2ebc1632"
  integrity sha512-7ylylesZQ/PV29jhEDl3Ufjo6ZX7gCqJr5F7PKrqc93v7fzSymt1BpwEU8nAUXs8qzzvqhbjhK5QZg6Mt/HkBg==

loader-runner@^4.2.0:
  version "4.3.0"
  resolved "https://registry.npmmirror.com/loader-runner/-/loader-runner-4.3.0.tgz#c1b4a163b99f614830353b16755e7149ac2314e1"
  integrity sha512-3R/1M+yS3j5ou80Me59j7F9IMs4PXs3VqRrm0TU3AbKPxlmpoY1TNscJV/oGJXo8qCatFGTfDbY6W6ipGOYXfg==

loader-utils@2.0.4, loader-utils@^2.0.0:
  version "2.0.4"
  resolved "https://registry.npmmirror.com/loader-utils/-/loader-utils-2.0.4.tgz#8b5cb38b5c34a9a018ee1fc0e6a066d1dfcc528c"
  integrity sha512-xXqpXoINfFhgua9xiqD8fPFHgkoq1mmmpE92WlDbm9rNRd/EbRb+Gqf908T2DMfuHjjJlksiK2RbHVOdD/MqSw==
  dependencies:
    big.js "^5.2.2"
    emojis-list "^3.0.0"
    json5 "^2.1.2"

locate-path@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/locate-path/-/locate-path-3.0.0.tgz#dbec3b3ab759758071b58fe59fc41871af21400e"
  integrity sha512-7AO748wWnIhNqAuaty2ZWHkQHRSNfPVIsPIfwEOWO22AmaoVrWavlOcMR5nzTLNYvp36X220/maaRsrec1G65A==
  dependencies:
    p-locate "^3.0.0"
    path-exists "^3.0.0"

locate-path@^5.0.0:
  version "5.0.0"
  resolved "https://registry.npmmirror.com/locate-path/-/locate-path-5.0.0.tgz#1afba396afd676a6d42504d0a67a3a7eb9f62aa0"
  integrity sha512-t7hw9pI+WvuwNJXwk5zVHpyhIqzg2qTlklJOf0mVxGSbe3Fp2VieZcduNYjaLDoy6p9uGpQEGWG87WpMKlNq8g==
  dependencies:
    p-locate "^4.1.0"

locate-path@^6.0.0:
  version "6.0.0"
  resolved "https://registry.npmmirror.com/locate-path/-/locate-path-6.0.0.tgz#55321eb309febbc59c4801d931a72452a681d286"
  integrity sha512-iPZK6eYjbxRu3uB4/WZ3EsEIMJFMqAoopl3R+zuq0UjcAm/MO6KCweDgPfP3elTztoKP3KtnVHxTn2NHBSDVUw==
  dependencies:
    p-locate "^5.0.0"

lodash.curry@^4.0.1:
  version "4.1.1"
  resolved "https://registry.npmmirror.com/lodash.curry/-/lodash.curry-4.1.1.tgz#248e36072ede906501d75966200a86dab8b23170"
  integrity sha512-/u14pXGviLaweY5JI0IUzgzF2J6Ne8INyzAZjImcryjgkZ+ebruBxy2/JaOOkTqScddcYtakjhSaeemV8lR0tA==

lodash.debounce@^4.0.8:
  version "4.0.8"
  resolved "https://registry.npmmirror.com/lodash.debounce/-/lodash.debounce-4.0.8.tgz#82d79bff30a67c4005ffd5e2515300ad9ca4d7af"
  integrity sha512-FT1yDzDYEoYWhnSGnpE/4Kj1fLZkDFyqRb7fNt6FdYOSxlUWAtp42Eh6Wb0rGIv/m9Bgo7x4GhQbm5Ys4SG5ow==

lodash.flow@^3.3.0:
  version "3.5.0"
  resolved "https://registry.npmmirror.com/lodash.flow/-/lodash.flow-3.5.0.tgz#87bf40292b8cf83e4e8ce1a3ae4209e20071675a"
  integrity sha512-ff3BX/tSioo+XojX4MOsOMhJw0nZoUEF011LX8g8d3gvjVbxd89cCio4BCXronjxcTUIJUoqKEUA+n4CqvvRPw==

lodash.memoize@^4.1.2:
  version "4.1.2"
  resolved "https://registry.npmmirror.com/lodash.memoize/-/lodash.memoize-4.1.2.tgz#bcc6c49a42a2840ed997f323eada5ecd182e0bfe"
  integrity sha512-t7j+NzmgnQzTAYXcsHYLgimltOV1MXHtlOWf6GjL9Kj8GK5FInw5JotxvbOs+IvV1/Dzo04/fCGfLVs7aXb4Ag==

lodash.uniq@4.5.0, lodash.uniq@^4.5.0:
  version "4.5.0"
  resolved "https://registry.npmmirror.com/lodash.uniq/-/lodash.uniq-4.5.0.tgz#d0225373aeb652adc1bc82e4945339a842754773"
  integrity sha512-xfBaXQd9ryd9dlSDvnvI0lvxfLJlYAZzXomUYzLKtUeOQvOP5piqAWuGtrhWeqaXK9hhoM/iyJc5AV+XfsX3HQ==

lodash@^4.17.19, lodash@^4.17.20, lodash@^4.17.21:
  version "4.17.21"
  resolved "https://registry.npmmirror.com/lodash/-/lodash-4.17.21.tgz#679591c564c3bffaae8454cf0b3df370c3d6911c"
  integrity sha512-v2kDEe57lecTulaDIuNTPy3Ry4gLGJ6Z1O3vE1krgXZNrsQ+LFTGHVxVjcXPs17LhbZVGedAJv8XZ1tvj5FvSg==

loose-envify@^1.0.0, loose-envify@^1.1.0, loose-envify@^1.2.0, loose-envify@^1.3.1, loose-envify@^1.4.0:
  version "1.4.0"
  resolved "https://registry.npmmirror.com/loose-envify/-/loose-envify-1.4.0.tgz#71ee51fa7be4caec1a63839f7e682d8132d30caf"
  integrity sha512-lyuxPGr/Wfhrlem2CL/UcnUc1zcqKAImBDzukY7Y5F/yQiNdko6+fRLevlw1HgMySw7f611UIY408EtxRSoK3Q==
  dependencies:
    js-tokens "^3.0.0 || ^4.0.0"

lower-case@^2.0.2:
  version "2.0.2"
  resolved "https://registry.npmmirror.com/lower-case/-/lower-case-2.0.2.tgz#6fa237c63dbdc4a82ca0fd882e4722dc5e634e28"
  integrity sha512-7fm3l3NAF9WfN6W3JOmf5drwpVqX78JtoGJ3A6W0a6ZnldM41w2fV5D490psKFTpMds8TJse/eHLFFsNHHjHgg==
  dependencies:
    tslib "^2.0.3"

lowercase-keys@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/lowercase-keys/-/lowercase-keys-2.0.0.tgz#2603e78b7b4b0006cbca2fbcc8a3202558ac9479"
  integrity sha512-tqNXrS78oMOE73NMxK4EMLQsQowWf8jKooH9g7xPavRT706R6bkQJ6DY2Te7QukaZsulxa30wQ7bk0pm4XiHmA==

lru-cache@^6.0.0:
  version "6.0.0"
  resolved "https://registry.npmmirror.com/lru-cache/-/lru-cache-6.0.0.tgz#6d6fe6570ebd96aaf90fcad1dafa3b2566db3a94"
  integrity sha512-Jo6dJ04CmSjuznwJSS3pUeWmd/H0ffTlkXXgwZi+eq1UCmqQwCh+eLsYOYCwY991i2Fah4h1BEMCx4qThGbsiA==
  dependencies:
    yallist "^4.0.0"

lunr-languages@^1.4.0:
  version "1.10.0"
  resolved "https://registry.npmmirror.com/lunr-languages/-/lunr-languages-1.10.0.tgz#2afe9fff47b435d9bc74bd372fb923dbf8ee1990"
  integrity sha512-BBjKKcwrieJlzwwc9M5H/MRXGJ2qyOSDx/NXYiwkuKjiLOOoouh0WsDzeqcLoUWcX31y7i8sb8IgsZKObdUCkw==

lunr@^2.3.9:
  version "2.3.9"
  resolved "https://registry.npmmirror.com/lunr/-/lunr-2.3.9.tgz#18b123142832337dd6e964df1a5a7707b25d35e1"
  integrity sha512-zTU3DaZaF3Rt9rhN3uBMGQD3dD2/vFQqnvZCDv4dl5iOzq2IZQqTxu90r4E5J+nP70J3ilqVCrbho2eWaeW8Ow==

magic-string@^0.25.3:
  version "0.25.9"
  resolved "https://registry.npmmirror.com/magic-string/-/magic-string-0.25.9.tgz#de7f9faf91ef8a1c91d02c2e5314c8277dbcdd1c"
  integrity sha512-RmF0AsMzgt25qzqqLc1+MbHmhdx0ojF2Fvs4XnOqz2ZOBXzzkEwc/dJQZCYHAn7v1jbVOjAZfK8msRn4BxO4VQ==
  dependencies:
    sourcemap-codec "^1.4.8"

make-dir@^3.0.0, make-dir@^3.0.2, make-dir@^3.1.0:
  version "3.1.0"
  resolved "https://registry.npmmirror.com/make-dir/-/make-dir-3.1.0.tgz#415e967046b3a7f1d185277d84aa58203726a13f"
  integrity sha512-g3FeP20LNwhALb/6Cz6Dd4F2ngze0jz7tbzrD2wAV+o9FeNHe4rL+yK2md0J/fiSf1sa1ADhXqi5+oVwOM/eGw==
  dependencies:
    semver "^6.0.0"

mark.js@^8.11.1:
  version "8.11.1"
  resolved "https://registry.npmmirror.com/mark.js/-/mark.js-8.11.1.tgz#180f1f9ebef8b0e638e4166ad52db879beb2ffc5"
  integrity sha512-1I+1qpDt4idfgLQG+BNWmrqku+7/2bi5nLf4YwF8y8zXvmfiTBY3PV3ZibfrjBueCByROpuBjLLFCajqkgYoLQ==

markdown-escapes@^1.0.0:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/markdown-escapes/-/markdown-escapes-1.0.4.tgz#c95415ef451499d7602b91095f3c8e8975f78535"
  integrity sha512-8z4efJYk43E0upd0NbVXwgSTQs6cT3T06etieCMEg7dRbzCbxUCK/GHlX8mhHRDcp+OLlHkPKsvqQTCvsRl2cg==

mdast-squeeze-paragraphs@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/mdast-squeeze-paragraphs/-/mdast-squeeze-paragraphs-4.0.0.tgz#7c4c114679c3bee27ef10b58e2e015be79f1ef97"
  integrity sha512-zxdPn69hkQ1rm4J+2Cs2j6wDEv7O17TfXTJ33tl/+JPIoEmtV9t2ZzBM5LPHE8QlHsmVD8t3vPKCyY3oH+H8MQ==
  dependencies:
    unist-util-remove "^2.0.0"

mdast-util-definitions@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/mdast-util-definitions/-/mdast-util-definitions-4.0.0.tgz#c5c1a84db799173b4dcf7643cda999e440c24db2"
  integrity sha512-k8AJ6aNnUkB7IE+5azR9h81O5EQ/cTDXtWdMq9Kk5KcEW/8ritU5CeLg/9HhOC++nALHBlaogJ5jz0Ybk3kPMQ==
  dependencies:
    unist-util-visit "^2.0.0"

mdast-util-to-hast@10.0.1:
  version "10.0.1"
  resolved "https://registry.npmmirror.com/mdast-util-to-hast/-/mdast-util-to-hast-10.0.1.tgz#0cfc82089494c52d46eb0e3edb7a4eb2aea021eb"
  integrity sha512-BW3LM9SEMnjf4HXXVApZMt8gLQWVNXc3jryK0nJu/rOXPOnlkUjmdkDlmxMirpbU9ILncGFIwLH/ubnWBbcdgA==
  dependencies:
    "@types/mdast" "^3.0.0"
    "@types/unist" "^2.0.0"
    mdast-util-definitions "^4.0.0"
    mdurl "^1.0.0"
    unist-builder "^2.0.0"
    unist-util-generated "^1.0.0"
    unist-util-position "^3.0.0"
    unist-util-visit "^2.0.0"

mdast-util-to-string@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/mdast-util-to-string/-/mdast-util-to-string-2.0.0.tgz#b8cfe6a713e1091cb5b728fc48885a4767f8b97b"
  integrity sha512-AW4DRS3QbBayY/jJmD8437V1Gombjf8RSOUCMFBuo5iHi58AGEgVCKQ+ezHkZZDpAQS75hcBMpLqjpJTjtUL7w==

mdn-data@2.0.14:
  version "2.0.14"
  resolved "https://registry.npmmirror.com/mdn-data/-/mdn-data-2.0.14.tgz#7113fc4281917d63ce29b43446f701e68c25ba50"
  integrity sha512-dn6wd0uw5GsdswPFfsgMp5NSB0/aDe6fK94YJV/AJDYXL6HVLWBsxeq7js7Ad+mU2K9LAlwpk6kN2D5mwCPVow==

mdn-data@2.0.4:
  version "2.0.4"
  resolved "https://registry.npmmirror.com/mdn-data/-/mdn-data-2.0.4.tgz#699b3c38ac6f1d728091a64650b65d388502fd5b"
  integrity sha512-iV3XNKw06j5Q7mi6h+9vbx23Tv7JkjEVgKHW4pimwyDGWm0OIQntJJ+u1C6mg6mK1EaTv42XQ7w76yuzH7M2cA==

mdurl@^1.0.0:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/mdurl/-/mdurl-1.0.1.tgz#fe85b2ec75a59037f2adfec100fd6c601761152e"
  integrity sha512-/sKlQJCBYVY9Ers9hqzKou4H6V5UWc/M59TH2dvkt+84itfnq7uFOMLpOiOS4ujvHP4etln18fmIxA5R5fll0g==

media-typer@0.3.0:
  version "0.3.0"
  resolved "https://registry.npmmirror.com/media-typer/-/media-typer-0.3.0.tgz#8710d7af0aa626f8fffa1ce00168545263255748"
  integrity sha512-dq+qelQ9akHpcOl/gUVRTxVIOkAJ1wR3QAvb4RsVjS8oVoFjDGTc679wJYmUmknUF5HwMLOgb5O+a3KxfWapPQ==

memfs@^3.1.2, memfs@^3.4.3:
  version "3.4.10"
  resolved "https://registry.npmmirror.com/memfs/-/memfs-3.4.10.tgz#4cdff7cfd21351a85e11b08aa276ebf100210a4d"
  integrity sha512-0bCUP+L79P4am30yP1msPzApwuMQG23TjwlwdHeEV5MxioDR1a0AgB0T9FfggU52eJuDCq8WVwb5ekznFyWiTQ==
  dependencies:
    fs-monkey "^1.0.3"

merge-descriptors@1.0.1:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/merge-descriptors/-/merge-descriptors-1.0.1.tgz#b00aaa556dd8b44568150ec9d1b953f3f90cbb61"
  integrity sha512-cCi6g3/Zr1iqQi6ySbseM1Xvooa98N0w31jzUYrXPX2xqObmFGHJ0tQ5u74H3mVh7wLouTseZyYIq39g8cNp1w==

merge-stream@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/merge-stream/-/merge-stream-2.0.0.tgz#52823629a14dd00c9770fb6ad47dc6310f2c1f60"
  integrity sha512-abv/qOcuPfk3URPfDzmZU1LKmuw8kT+0nIHvKrKgFrwifol/doWcdA4ZqsWQ8ENrFKkd67Mfpo/LovbIUsbt3w==

merge2@^1.3.0, merge2@^1.4.1:
  version "1.4.1"
  resolved "https://registry.npmmirror.com/merge2/-/merge2-1.4.1.tgz#4368892f885e907455a6fd7dc55c0c9d404990ae"
  integrity sha512-8q7VEgMJW4J8tcfVPy8g09NcQwZdbwFEqhe/WZkoIzjn/3TGDwtOCYtXGxA3O8tPzpczCCDgv+P2P5y00ZJOOg==

methods@~1.1.2:
  version "1.1.2"
  resolved "https://registry.npmmirror.com/methods/-/methods-1.1.2.tgz#5529a4d67654134edcc5266656835b0f851afcee"
  integrity sha512-iclAHeNqNm68zFtnZ0e+1L2yUIdvzNoauKU4WBA3VvH/vPFieF7qfRlwUZU+DA9P9bPXIS90ulxoUoCH23sV2w==

micromatch@^4.0.2, micromatch@^4.0.4, micromatch@^4.0.5:
  version "4.0.5"
  resolved "https://registry.npmmirror.com/micromatch/-/micromatch-4.0.5.tgz#bc8999a7cbbf77cdc89f132f6e467051b49090c6"
  integrity sha512-DMy+ERcEW2q8Z2Po+WNXuw3c5YaUSFjAO5GsJqfEl7UjvtIuFKO6ZrKvcItdy98dwFI2N1tg3zNIdKaQT+aNdA==
  dependencies:
    braces "^3.0.2"
    picomatch "^2.3.1"

mime-db@1.52.0, "mime-db@>= 1.43.0 < 2":
  version "1.52.0"
  resolved "https://registry.npmmirror.com/mime-db/-/mime-db-1.52.0.tgz#bbabcdc02859f4987301c856e3387ce5ec43bf70"
  integrity sha512-sPU4uV7dYlvtWJxwwxHD0PuihVNiE7TyAbQ5SWxDCB9mUYvOgroQOwYQQOKPJ8CIbE+1ETVlOoK1UC2nU3gYvg==

mime-db@~1.33.0:
  version "1.33.0"
  resolved "https://registry.npmmirror.com/mime-db/-/mime-db-1.33.0.tgz#a3492050a5cb9b63450541e39d9788d2272783db"
  integrity sha512-BHJ/EKruNIqJf/QahvxwQZXKygOQ256myeN/Ew+THcAa5q+PjyTTMMeNQC4DZw5AwfvelsUrA6B67NKMqXDbzQ==

mime-types@2.1.18:
  version "2.1.18"
  resolved "https://registry.npmmirror.com/mime-types/-/mime-types-2.1.18.tgz#6f323f60a83d11146f831ff11fd66e2fe5503bb8"
  integrity sha512-lc/aahn+t4/SWV/qcmumYjymLsWfN3ELhpmVuUFjgsORruuZPVSwAQryq+HHGvO/SI2KVX26bx+En+zhM8g8hQ==
  dependencies:
    mime-db "~1.33.0"

mime-types@^2.1.27, mime-types@^2.1.31, mime-types@~2.1.17, mime-types@~2.1.24, mime-types@~2.1.34:
  version "2.1.35"
  resolved "https://registry.npmmirror.com/mime-types/-/mime-types-2.1.35.tgz#381a871b62a734450660ae3deee44813f70d959a"
  integrity sha512-ZDY+bPm5zTTF+YpCrAU9nK0UgICYPT0QtT1NZWFv4s++TNkcgVaT0g6+4R2uI4MjQjzysHB1zxuWL50hzaeXiw==
  dependencies:
    mime-db "1.52.0"

mime@1.6.0:
  version "1.6.0"
  resolved "https://registry.npmmirror.com/mime/-/mime-1.6.0.tgz#32cd9e5c64553bd58d19a568af452acff04981b1"
  integrity sha512-x0Vn8spI+wuJ1O6S7gnbaQg8Pxh4NNHb7KSINmEWKiPE4RKOplvijn+NkmYmmRgP68mc70j2EbeTFRsrswaQeg==

mimic-fn@^2.1.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/mimic-fn/-/mimic-fn-2.1.0.tgz#7ed2c2ccccaf84d3ffcb7a69b57711fc2083401b"
  integrity sha512-OqbOk5oEQeAZ8WXWydlu9HJjz9WVdEIvamMCcXmuqUYjTknH/sqsWvhQ3vgwKFRR1HpjvNBKQ37nbJgYzGqGcg==

mimic-response@^1.0.0:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/mimic-response/-/mimic-response-1.0.1.tgz#4923538878eef42063cb8a3e3b0798781487ab1b"
  integrity sha512-j5EctnkH7amfV/q5Hgmoal1g2QHFJRraOtmx0JpIqkxhBhI/lJSl1nMpQ45hVarwNETOoWEimndZ4QK0RHxuxQ==

mimic-response@^3.1.0:
  version "3.1.0"
  resolved "https://registry.npmmirror.com/mimic-response/-/mimic-response-3.1.0.tgz#2d1d59af9c1b129815accc2c46a022a5ce1fa3c9"
  integrity sha512-z0yWI+4FDrrweS8Zmt4Ej5HdJmky15+L2e6Wgn3+iK5fWzb6T3fhNFq2+MeTRb064c6Wr4N/wv0DzQTjNzHNGQ==

mini-css-extract-plugin@^1.6.0:
  version "1.6.2"
  resolved "https://registry.npmmirror.com/mini-css-extract-plugin/-/mini-css-extract-plugin-1.6.2.tgz#83172b4fd812f8fc4a09d6f6d16f924f53990ca8"
  integrity sha512-WhDvO3SjGm40oV5y26GjMJYjd2UMqrLAGKy5YS2/3QKJy2F7jgynuHTir/tgUUOiNQu5saXHdc8reo7YuhhT4Q==
  dependencies:
    loader-utils "^2.0.0"
    schema-utils "^3.0.0"
    webpack-sources "^1.1.0"

minimalistic-assert@^1.0.0:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/minimalistic-assert/-/minimalistic-assert-1.0.1.tgz#2e194de044626d4a10e7f7fbc00ce73e83e4d5c7"
  integrity sha512-UtJcAD4yEaGtjPezWuO9wC4nwUnVH/8/Im3yEHQP4b67cXlD/Qr9hdITCU1xDbSEXg2XKNaP8jsReV7vQd00/A==

minimatch@3.0.5, minimatch@3.1.2, minimatch@^3.0.4, minimatch@^3.0.5, minimatch@^3.1.1:
  version "3.0.5"
  resolved "https://registry.npmmirror.com/minimatch/-/minimatch-3.0.5.tgz#4da8f1290ee0f0f8e83d60ca69f8f134068604a3"
  integrity sha512-tUpxzX0VAzJHjLu0xUfFv1gwVp9ba3IOuRAVH2EGuRW8a5emA2FlACLqiT/lDVtS1W+TGNwqz3sWaNyLgDJWuw==
  dependencies:
    brace-expansion "^1.1.7"

minimist@^1.2.0, minimist@^1.2.5, minimist@^1.2.6:
  version "1.2.7"
  resolved "https://registry.npmmirror.com/minimist/-/minimist-1.2.7.tgz#daa1c4d91f507390437c6a8bc01078e7000c4d18"
  integrity sha512-bzfL1YUZsP41gmu/qjrEk0Q6i2ix/cVeAhbCbqH9u3zYutS1cLg00qhrD0M2MVdCcx4Sc0UpP2eBWo9rotpq6g==

mkdirp@~0.5.1:
  version "0.5.6"
  resolved "https://registry.npmmirror.com/mkdirp/-/mkdirp-0.5.6.tgz#7def03d2432dcae4ba1d611445c48396062255f6"
  integrity sha512-FP+p8RB8OWpF3YZBCrP5gtADmtXApB5AMLn+vdyA+PyxCjrCs00mjyUozssO33cwDeT3wNGdLxJ5M//YqtHAJw==
  dependencies:
    minimist "^1.2.6"

mrmime@^1.0.0:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/mrmime/-/mrmime-1.0.1.tgz#5f90c825fad4bdd41dc914eff5d1a8cfdaf24f27"
  integrity sha512-hzzEagAgDyoU1Q6yg5uI+AorQgdvMCur3FcKf7NhMKWsaYg+RnbTyHRa/9IlLF9rf455MOCtcqqrQQ83pPP7Uw==

ms@2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/ms/-/ms-2.0.0.tgz#5608aeadfc00be6c2901df5f9861788de0d597c8"
  integrity sha512-Tpp60P6IUJDTuOq/5Z8cdskzJujfwqfOTkrwIwj7IRISpnkJnT6SyJ4PCPnGMoFjC9ddhal5KVIYtAt97ix05A==

ms@2.1.2:
  version "2.1.2"
  resolved "https://registry.npmmirror.com/ms/-/ms-2.1.2.tgz#d09d1f357b443f493382a8eb3ccd183872ae6009"
  integrity sha512-sGkPx+VjMtmA6MX27oA4FBFELFCZZ4S4XqeGOXCv68tT+jb3vk/RyaKWP0PTKyWtmLSM0b+adUTEvbs1PEaH2w==

ms@2.1.3:
  version "2.1.3"
  resolved "https://registry.npmmirror.com/ms/-/ms-2.1.3.tgz#574c8138ce1d2b5861f0b44579dbadd60c6615b2"
  integrity sha512-6FlzubTLZG3J2a/NVCAleEhjzq5oxgHyaCU9yYXvcLsvoVaHJq/s5xXI6/XXP6tz7R9xAOtHnSO/tXtF3WRTlA==

multicast-dns@^7.2.5:
  version "7.2.5"
  resolved "https://registry.npmmirror.com/multicast-dns/-/multicast-dns-7.2.5.tgz#77eb46057f4d7adbd16d9290fa7299f6fa64cced"
  integrity sha512-2eznPJP8z2BFLX50tf0LuODrpINqP1RVIm/CObbTcBRITQgmC/TjcREF1NeTBzIcR5XO/ukWo+YHOjBbFwIupg==
  dependencies:
    dns-packet "^5.2.2"
    thunky "^1.0.2"

nanoid@^3.3.6:
  version "3.3.6"
  resolved "https://registry.yarnpkg.com/nanoid/-/nanoid-3.3.6.tgz#443380c856d6e9f9824267d960b4236ad583ea4c"
  integrity sha512-BGcqMMJuToF7i1rt+2PWSNVnWIkGCU78jBG3RxO/bZlnZPK2Cmi2QaffxGO/2RvWi9sL+FAiRiXMgsyxQ1DIDA==

negotiator@0.6.3:
  version "0.6.3"
  resolved "https://registry.npmmirror.com/negotiator/-/negotiator-0.6.3.tgz#58e323a72fedc0d6f9cd4d31fe49f51479590ccd"
  integrity sha512-+EUsqGPLsM+j/zdChZjsnX51g4XrHFOIXwfnCVPGlQk/k5giakcKsuxCObBRu6DSm9opw/O6slWbJdghQM4bBg==

neo-async@^2.6.2:
  version "2.6.2"
  resolved "https://registry.npmmirror.com/neo-async/-/neo-async-2.6.2.tgz#b4aafb93e3aeb2d8174ca53cf163ab7d7308305f"
  integrity sha512-Yd3UES5mWCSqR+qNT93S3UoYUkqAZ9lLg8a7g9rimsWmYGK8cVToA4/sF3RrshdyV3sAGMXVUmpMYOw+dLpOuw==

no-case@^3.0.4:
  version "3.0.4"
  resolved "https://registry.npmmirror.com/no-case/-/no-case-3.0.4.tgz#d361fd5c9800f558551a8369fc0dcd4662b6124d"
  integrity sha512-fgAN3jGAh+RoxUGZHTSOLJIqUc2wmoBwGR4tbpNAKmmovFoWq0OdRkb0VkldReO2a2iBT/OEulG9XSUc10r3zg==
  dependencies:
    lower-case "^2.0.2"
    tslib "^2.0.3"

node-emoji@^1.10.0:
  version "1.11.0"
  resolved "https://registry.npmmirror.com/node-emoji/-/node-emoji-1.11.0.tgz#69a0150e6946e2f115e9d7ea4df7971e2628301c"
  integrity sha512-wo2DpQkQp7Sjm2A0cq+sN7EHKO6Sl0ctXeBdFZrL9T9+UywORbufTcTZxom8YqpLQt/FqNMUkOpkZrJVYSKD3A==
  dependencies:
    lodash "^4.17.21"

node-fetch@2.6.7:
  version "2.6.7"
  resolved "https://registry.npmmirror.com/node-fetch/-/node-fetch-2.6.7.tgz#24de9fba827e3b4ae44dc8b20256a379160052ad"
  integrity sha512-ZjMPFEfVx5j+y2yF35Kzx5sF7kDzxuDj6ziH4FFbOp87zKDZNx8yExJIb05OGF4Nlt9IHFIMBkRl41VdvcNdbQ==
  dependencies:
    whatwg-url "^5.0.0"

node-forge@1.3.0, node-forge@^1:
  version "1.3.0"
  resolved "https://registry.npmmirror.com/node-forge/-/node-forge-1.3.0.tgz#37a874ea723855f37db091e6c186e5b67a01d4b2"
  integrity sha512-08ARB91bUi6zNKzVmaj3QO7cr397uiDT2nJ63cHjyNtCTWIgvS47j3eT0WfzUwS9+6Z5YshRaoasFkXCKrIYbA==

node-releases@^2.0.6:
  version "2.0.6"
  resolved "https://registry.npmmirror.com/node-releases/-/node-releases-2.0.6.tgz#8a7088c63a55e493845683ebf3c828d8c51c5503"
  integrity sha512-PiVXnNuFm5+iYkLBNeq5211hvO38y63T0i2KKh2KnUs3RpzJ+JtODFjkD8yjLwnDkTYF1eKXheUwdssR+NRZdg==

normalize-path@^3.0.0, normalize-path@~3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/normalize-path/-/normalize-path-3.0.0.tgz#0dcd69ff23a1c9b11fd0978316644a0388216a65"
  integrity sha512-6eZs5Ls3WtCisHWp9S2GUy8dqkpGi4BVSz3GaqiE6ezub0512ESztXUwUB6C6IKbQkY2Pnb/mD4WYojCRwcwLA==

normalize-range@^0.1.2:
  version "0.1.2"
  resolved "https://registry.npmmirror.com/normalize-range/-/normalize-range-0.1.2.tgz#2d10c06bdfd312ea9777695a4d28439456b75942"
  integrity sha512-bdok/XvKII3nUpklnV6P2hxtMNrCboOjAcyBuQnWEhO665FwrSNRxU+AqpsyvO6LgGYPspN+lu5CLtw4jPRKNA==

normalize-url@^6.0.1:
  version "6.1.0"
  resolved "https://registry.npmmirror.com/normalize-url/-/normalize-url-6.1.0.tgz#40d0885b535deffe3f3147bec877d05fe4c5668a"
  integrity sha512-DlL+XwOy3NxAQ8xuC0okPgK46iuVNAK01YN7RueYBqqFeGsBjV9XmCAzAdgt+667bCl5kPh9EqKKDwnaPG1I7A==

npm-run-path@^4.0.1:
  version "4.0.1"
  resolved "https://registry.npmmirror.com/npm-run-path/-/npm-run-path-4.0.1.tgz#b7ecd1e5ed53da8e37a55e1c2269e0b97ed748ea"
  integrity sha512-S48WzZW777zhNIrn7gxOlISNAqi9ZC/uQFnRdbeIHhZhCA6UqpkOT8T1G7BvfdgP4Er8gF4sUbaS0i7QvIfCWw==
  dependencies:
    path-key "^3.0.0"

nprogress@^0.2.0:
  version "0.2.0"
  resolved "https://registry.npmmirror.com/nprogress/-/nprogress-0.2.0.tgz#cb8f34c53213d895723fcbab907e9422adbcafb1"
  integrity sha512-I19aIingLgR1fmhftnbWWO3dXc0hSxqHQHQb3H8m+K3TnEn/iSeTZZOyvKXWqQESMwuUVnatlCnZdLBZZt2VSA==

nth-check@2.0.1, nth-check@^1.0.2, nth-check@^2.0.1:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/nth-check/-/nth-check-2.0.1.tgz#2efe162f5c3da06a28959fbd3db75dbeea9f0fc2"
  integrity sha512-it1vE95zF6dTT9lBsYbxvqh0Soy4SPowchj0UBGj/V6cTPnXXtQOPUbhZ6CmGzAD/rW22LQK6E96pcdJXk4A4w==
  dependencies:
    boolbase "^1.0.0"

object-assign@^4.1.0, object-assign@^4.1.1:
  version "4.1.1"
  resolved "https://registry.npmmirror.com/object-assign/-/object-assign-4.1.1.tgz#2109adc7965887cfc05cbbd442cac8bfbb360863"
  integrity sha512-rJgTQnkUnH1sFw8yT6VSU3zD3sWmu6sZhIseY8VX+GRu3P6F7Fu+JNDoXfklElbLJSnc3FUQHVe4cU5hj+BcUg==

object-inspect@^1.12.2, object-inspect@^1.9.0:
  version "1.12.2"
  resolved "https://registry.npmmirror.com/object-inspect/-/object-inspect-1.12.2.tgz#c0641f26394532f28ab8d796ab954e43c009a8ea"
  integrity sha512-z+cPxW0QGUp0mcqcsgQyLVRDoXFQbXOwBaqyF7VIgI4TWNQsDHrBpUQslRmIfAoYWdYzs6UlKJtB2XJpTaNSpQ==

object-keys@^1.1.1:
  version "1.1.1"
  resolved "https://registry.npmmirror.com/object-keys/-/object-keys-1.1.1.tgz#1c47f272df277f3b1daf061677d9c82e2322c60e"
  integrity sha512-NuAESUOUMrlIXOfHKzD6bpPu3tYt3xvjNdRIQ+FeT0lNb4K8WR70CaDxhuNguS2XG+GjkyMwOzsN5ZktImfhLA==

object.assign@^4.1.0, object.assign@^4.1.4:
  version "4.1.4"
  resolved "https://registry.npmmirror.com/object.assign/-/object.assign-4.1.4.tgz#9673c7c7c351ab8c4d0b516f4343ebf4dfb7799f"
  integrity sha512-1mxKf0e58bvyjSCtKYY4sRe9itRk3PJpquJOjeIkz885CczcI4IvJJDLPS72oowuSh+pBxUFROpX+TU++hxhZQ==
  dependencies:
    call-bind "^1.0.2"
    define-properties "^1.1.4"
    has-symbols "^1.0.3"
    object-keys "^1.1.1"

object.getownpropertydescriptors@^2.1.0:
  version "2.1.4"
  resolved "https://registry.npmmirror.com/object.getownpropertydescriptors/-/object.getownpropertydescriptors-2.1.4.tgz#7965e6437a57278b587383831a9b829455a4bc37"
  integrity sha512-sccv3L/pMModT6dJAYF3fzGMVcb38ysQ0tEE6ixv2yXJDtEIPph268OlAdJj5/qZMZDq2g/jqvwppt36uS/uQQ==
  dependencies:
    array.prototype.reduce "^1.0.4"
    call-bind "^1.0.2"
    define-properties "^1.1.4"
    es-abstract "^1.20.1"

object.values@^1.1.0:
  version "1.1.5"
  resolved "https://registry.npmmirror.com/object.values/-/object.values-1.1.5.tgz#959f63e3ce9ef108720333082131e4a459b716ac"
  integrity sha512-QUZRW0ilQ3PnPpbNtgdNV1PDbEqLIiSFB3l+EnGtBQ/8SUTLj1PZwtQHABZtLgwpJZTSZhuGLOGk57Drx2IvYg==
  dependencies:
    call-bind "^1.0.2"
    define-properties "^1.1.3"
    es-abstract "^1.19.1"

obuf@^1.0.0, obuf@^1.1.2:
  version "1.1.2"
  resolved "https://registry.npmmirror.com/obuf/-/obuf-1.1.2.tgz#09bea3343d41859ebd446292d11c9d4db619084e"
  integrity sha512-PX1wu0AmAdPqOL1mWhqmlOd8kOIZQwGZw6rh7uby9fTc5lhaOWFLX3I6R1hrF9k3zUY40e6igsLGkDXK92LJNg==

on-finished@2.4.1:
  version "2.4.1"
  resolved "https://registry.npmmirror.com/on-finished/-/on-finished-2.4.1.tgz#58c8c44116e54845ad57f14ab10b03533184ac3f"
  integrity sha512-oVlzkg3ENAhCk2zdv7IJwd/QUD4z2RxRwpkcGY8psCVcCYZNq4wYnVWALHM+brtuJjePWiYF/ClmuDr8Ch5+kg==
  dependencies:
    ee-first "1.1.1"

on-headers@~1.0.2:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/on-headers/-/on-headers-1.0.2.tgz#772b0ae6aaa525c399e489adfad90c403eb3c28f"
  integrity sha512-pZAE+FJLoyITytdqK0U5s+FIpjN0JP3OzFi/u8Rx+EV5/W+JTWGXG8xFzevE7AjBfDqHv/8vL8qQsIhHnqRkrA==

once@^1.3.0, once@^1.3.1, once@^1.4.0:
  version "1.4.0"
  resolved "https://registry.npmmirror.com/once/-/once-1.4.0.tgz#583b1aa775961d4b113ac17d9c50baef9dd76bd1"
  integrity sha512-lNaJgI+2Q5URQBkccEKHTQOPaXdUxnZZElQTZY0MFUAuaEqe1E+Nyvgdz/aIyNi6Z9MzO5dv1H8n58/GELp3+w==
  dependencies:
    wrappy "1"

onetime@^5.1.2:
  version "5.1.2"
  resolved "https://registry.npmmirror.com/onetime/-/onetime-5.1.2.tgz#d0e96ebb56b07476df1dd9c4806e5237985ca45e"
  integrity sha512-kbpaSSGJTWdAY5KPVeMOKXSrPtr8C8C7wodJbcsd51jRnmD+GZu8Y0VoU6Dm5Z4vWr0Ig/1NKuWRKf7j5aaYSg==
  dependencies:
    mimic-fn "^2.1.0"

open@^7.0.2:
  version "7.4.2"
  resolved "https://registry.npmmirror.com/open/-/open-7.4.2.tgz#b8147e26dcf3e426316c730089fd71edd29c2321"
  integrity sha512-MVHddDVweXZF3awtlAS+6pgKLlm/JgxZ90+/NBurBoQctVOOB/zDdVjcyPzQ+0laDGbsWgrRkflI65sQeOgT9Q==
  dependencies:
    is-docker "^2.0.0"
    is-wsl "^2.1.1"

open@^8.0.9:
  version "8.4.0"
  resolved "https://registry.npmmirror.com/open/-/open-8.4.0.tgz#345321ae18f8138f82565a910fdc6b39e8c244f8"
  integrity sha512-XgFPPM+B28FtCCgSb9I+s9szOC1vZRSwgWsRUA5ylIxRTgKozqjOCrVOqGsYABPYK5qnfqClxZTFBa8PKt2v6Q==
  dependencies:
    define-lazy-prop "^2.0.0"
    is-docker "^2.1.1"
    is-wsl "^2.2.0"

opener@^1.5.2:
  version "1.5.2"
  resolved "https://registry.npmmirror.com/opener/-/opener-1.5.2.tgz#5d37e1f35077b9dcac4301372271afdeb2a13598"
  integrity sha512-ur5UIdyw5Y7yEj9wLzhqXiy6GZ3Mwx0yGI+5sMn2r0N0v3cKJvUmFH5yPP+WXh9e0xfyzyJX95D8l088DNFj7A==

p-cancelable@^2.0.0:
  version "2.1.1"
  resolved "https://registry.npmmirror.com/p-cancelable/-/p-cancelable-2.1.1.tgz#aab7fbd416582fa32a3db49859c122487c5ed2cf"
  integrity sha512-BZOr3nRQHOntUjTrH8+Lh54smKHoHyur8We1V8DSMVrl5A2malOOwuJRnKRDjSnkoeBh4at6BwEnb5I7Jl31wg==

p-limit@^2.0.0, p-limit@^2.2.0:
  version "2.3.0"
  resolved "https://registry.npmmirror.com/p-limit/-/p-limit-2.3.0.tgz#3dd33c647a214fdfffd835933eb086da0dc21db1"
  integrity sha512-//88mFWSJx8lxCzwdAABTJL2MyWB12+eIY7MDL2SqLmAkeKU9qxRvWuSyTjm3FUmpBEMuFfckAIqEaVGUDxb6w==
  dependencies:
    p-try "^2.0.0"

p-limit@^3.0.2:
  version "3.1.0"
  resolved "https://registry.npmmirror.com/p-limit/-/p-limit-3.1.0.tgz#e1daccbe78d0d1388ca18c64fea38e3e57e3706b"
  integrity sha512-TYOanM3wGwNGsZN2cVTYPArw454xnXj5qmWF1bEoAc4+cU/ol7GVh7odevjp1FNHduHc3KZMcFduxU5Xc6uJRQ==
  dependencies:
    yocto-queue "^0.1.0"

p-locate@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/p-locate/-/p-locate-3.0.0.tgz#322d69a05c0264b25997d9f40cd8a891ab0064a4"
  integrity sha512-x+12w/To+4GFfgJhBEpiDcLozRJGegY+Ei7/z0tSLkMmxGZNybVMSfWj9aJn8Z5Fc7dBUNJOOVgPv2H7IwulSQ==
  dependencies:
    p-limit "^2.0.0"

p-locate@^4.1.0:
  version "4.1.0"
  resolved "https://registry.npmmirror.com/p-locate/-/p-locate-4.1.0.tgz#a3428bb7088b3a60292f66919278b7c297ad4f07"
  integrity sha512-R79ZZ/0wAxKGu3oYMlz8jy/kbhsNrS7SKZ7PxEHBgJ5+F2mtFW2fK2cOtBh1cHYkQsbzFV7I+EoRKe6Yt0oK7A==
  dependencies:
    p-limit "^2.2.0"

p-locate@^5.0.0:
  version "5.0.0"
  resolved "https://registry.npmmirror.com/p-locate/-/p-locate-5.0.0.tgz#83c8315c6785005e3bd021839411c9e110e6d834"
  integrity sha512-LaNjtRWUBY++zB5nE/NwcaoMylSPk+S+ZHNB1TzdbMJMny6dynpAGt7X/tl/QYq3TIeE6nxHppbo2LGymrG5Pw==
  dependencies:
    p-limit "^3.0.2"

p-map@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/p-map/-/p-map-4.0.0.tgz#bb2f95a5eda2ec168ec9274e06a747c3e2904d2b"
  integrity sha512-/bjOqmgETBYB5BoEeGVea8dmvHb2m9GLy1E9W43yeyfP6QQCZGFNa+XRceJEuDB6zqr+gKpIAmlLebMpykw/MQ==
  dependencies:
    aggregate-error "^3.0.0"

p-retry@^4.5.0:
  version "4.6.2"
  resolved "https://registry.npmmirror.com/p-retry/-/p-retry-4.6.2.tgz#9baae7184057edd4e17231cee04264106e092a16"
  integrity sha512-312Id396EbJdvRONlngUx0NydfrIQ5lsYu0znKVUzVvArzEIt08V1qhtyESbGVd1FGX7UKtiFp5uwKZdM8wIuQ==
  dependencies:
    "@types/retry" "0.12.0"
    retry "^0.13.1"

p-try@^2.0.0:
  version "2.2.0"
  resolved "https://registry.npmmirror.com/p-try/-/p-try-2.2.0.tgz#cb2868540e313d61de58fafbe35ce9004d5540e6"
  integrity sha512-R4nPAVTAU0B9D35/Gk3uJf/7XYbQcyohSKdvAxIRSNghFl4e71hVoGnBNQz9cWaXxO2I10KTC+3jMdvvoKw6dQ==

package-json@^6.3.0:
  version "6.5.0"
  resolved "https://registry.npmmirror.com/package-json/-/package-json-6.5.0.tgz#6feedaca35e75725876d0b0e64974697fed145b0"
  integrity sha512-k3bdm2n25tkyxcjSKzB5x8kfVxlMdgsbPr0GkZcwHsLpba6cBjqCt1KlcChKEvxHIcTB1FVMuwoijZ26xex5MQ==
  dependencies:
    got "^9.6.0"
    registry-auth-token "^4.0.0"
    registry-url "^5.0.0"
    semver "^6.2.0"

param-case@^3.0.4:
  version "3.0.4"
  resolved "https://registry.npmmirror.com/param-case/-/param-case-3.0.4.tgz#7d17fe4aa12bde34d4a77d91acfb6219caad01c5"
  integrity sha512-RXlj7zCYokReqWpOPH9oYivUzLYZ5vAPIfEmCTNViosC78F8F0H9y7T7gG2M39ymgutxF5gcFEsyZQSph9Bp3A==
  dependencies:
    dot-case "^3.0.4"
    tslib "^2.0.3"

parent-module@^1.0.0:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/parent-module/-/parent-module-1.0.1.tgz#691d2709e78c79fae3a156622452d00762caaaa2"
  integrity sha512-GQ2EWRpQV8/o+Aw8YqtfZZPfNRWZYkbidE9k5rpl/hC3vtHHBfGm2Ifi6qWV+coDGkrUKZAxE3Lot5kcsRlh+g==
  dependencies:
    callsites "^3.0.0"

parse-entities@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/parse-entities/-/parse-entities-2.0.0.tgz#53c6eb5b9314a1f4ec99fa0fdf7ce01ecda0cbe8"
  integrity sha512-kkywGpCcRYhqQIchaWqZ875wzpS/bMKhz5HnN3p7wveJTkTtyAB/AlnS0f8DFSqYW1T82t6yEAkEcB+A1I3MbQ==
  dependencies:
    character-entities "^1.0.0"
    character-entities-legacy "^1.0.0"
    character-reference-invalid "^1.0.0"
    is-alphanumerical "^1.0.0"
    is-decimal "^1.0.0"
    is-hexadecimal "^1.0.0"

parse-json@^5.0.0:
  version "5.2.0"
  resolved "https://registry.npmmirror.com/parse-json/-/parse-json-5.2.0.tgz#c76fc66dee54231c962b22bcc8a72cf2f99753cd"
  integrity sha512-ayCKvm/phCGxOkYRSCM82iDwct8/EonSEgCSxWxD7ve6jHggsFl4fZVQBPRNgQoKiuV/odhFrGzQXZwbifC8Rg==
  dependencies:
    "@babel/code-frame" "^7.0.0"
    error-ex "^1.3.1"
    json-parse-even-better-errors "^2.3.0"
    lines-and-columns "^1.1.6"

parse-numeric-range@^1.3.0:
  version "1.3.0"
  resolved "https://registry.npmmirror.com/parse-numeric-range/-/parse-numeric-range-1.3.0.tgz#7c63b61190d61e4d53a1197f0c83c47bb670ffa3"
  integrity sha512-twN+njEipszzlMJd4ONUYgSfZPDxgHhT9Ahed5uTigpQn90FggW4SA/AIPq/6a149fTbE9qBEcSwE3FAEp6wQQ==

parse5-htmlparser2-tree-adapter@^7.0.0:
  version "7.0.0"
  resolved "https://registry.npmmirror.com/parse5-htmlparser2-tree-adapter/-/parse5-htmlparser2-tree-adapter-7.0.0.tgz#23c2cc233bcf09bb7beba8b8a69d46b08c62c2f1"
  integrity sha512-B77tOZrqqfUfnVcOrUvfdLbz4pu4RopLD/4vmu3HUPswwTA8OH0EMW9BlWR2B0RCoiZRAHEUu7IxeP1Pd1UU+g==
  dependencies:
    domhandler "^5.0.2"
    parse5 "^7.0.0"

parse5@^5.0.0:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/parse5/-/parse5-5.1.1.tgz#f68e4e5ba1852ac2cadc00f4555fff6c2abb6178"
  integrity sha512-ugq4DFI0Ptb+WWjAdOK16+u/nHfiIrcE+sh8kZMaM0WllQKLI9rOUq6c2b7cwPkXdzfQESqvoqK6ug7U/Yyzug==

parse5@^6.0.0:
  version "6.0.1"
  resolved "https://registry.npmmirror.com/parse5/-/parse5-6.0.1.tgz#e1a1c085c569b3dc08321184f19a39cc27f7c30b"
  integrity sha512-Ofn/CTFzRGTTxwpNEs9PP93gXShHcTq255nzRYSKe8AkVpZY7e1fpmTfOyoIvjP5HG7Z2ZM7VS9PPhQGW2pOpw==

parse5@^7.0.0:
  version "7.1.1"
  resolved "https://registry.npmmirror.com/parse5/-/parse5-7.1.1.tgz#4649f940ccfb95d8754f37f73078ea20afe0c746"
  integrity sha512-kwpuwzB+px5WUg9pyK0IcK/shltJN5/OVhQagxhCQNtT9Y9QRZqNY2e1cmbu/paRh5LMnz/oVTVLBpjFmMZhSg==
  dependencies:
    entities "^4.4.0"

parseurl@~1.3.2, parseurl@~1.3.3:
  version "1.3.3"
  resolved "https://registry.npmmirror.com/parseurl/-/parseurl-1.3.3.tgz#9da19e7bee8d12dff0513ed5b76957793bc2e8d4"
  integrity sha512-CiyeOxFT/JZyN5m0z9PfXw4SCBJ6Sygz1Dpl0wqjlhDEGGBP1GnsUVEL0p63hoG1fcj3fHynXi9NYO4nWOL+qQ==

pascal-case@^3.1.2:
  version "3.1.2"
  resolved "https://registry.npmmirror.com/pascal-case/-/pascal-case-3.1.2.tgz#b48e0ef2b98e205e7c1dae747d0b1508237660eb"
  integrity sha512-uWlGT3YSnK9x3BQJaOdcZwrnV6hPpd8jFH1/ucpiLRPh/2zCVJKS19E4GvYHvaCcACn3foXZ0cLB9Wrx1KGe5g==
  dependencies:
    no-case "^3.0.4"
    tslib "^2.0.3"

path-exists@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/path-exists/-/path-exists-3.0.0.tgz#ce0ebeaa5f78cb18925ea7d810d7b59b010fd515"
  integrity sha512-bpC7GYwiDYQ4wYLe+FA8lhRjhQCMcQGuSgGGqDkg/QerRWw9CmGRT0iSOVRSZJ29NMLZgIzqaljJ63oaL4NIJQ==

path-exists@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/path-exists/-/path-exists-4.0.0.tgz#513bdbe2d3b95d7762e8c1137efa195c6c61b5b3"
  integrity sha512-ak9Qy5Q7jYb2Wwcey5Fpvg2KoAc/ZIhLSLOSBmRmygPsGwkVVt0fZa0qrtMz+m6tJTAHfZQ8FnmB4MG4LWy7/w==

path-is-absolute@^1.0.0:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/path-is-absolute/-/path-is-absolute-1.0.1.tgz#174b9268735534ffbc7ace6bf53a5a9e1b5c5f5f"
  integrity sha512-AVbw3UJ2e9bq64vSaS9Am0fje1Pa8pbGqTTsmXfaIiMpnr5DlDhfJOuLj9Sf95ZPVDAUerDfEk88MPmPe7UCQg==

path-is-inside@1.0.2:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/path-is-inside/-/path-is-inside-1.0.2.tgz#365417dede44430d1c11af61027facf074bdfc53"
  integrity sha512-DUWJr3+ULp4zXmol/SZkFf3JGsS9/SIv+Y3Rt93/UjPpDpklB5f1er4O3POIbUuUJ3FXgqte2Q7SrU6zAqwk8w==

path-key@^3.0.0, path-key@^3.1.0:
  version "3.1.1"
  resolved "https://registry.npmmirror.com/path-key/-/path-key-3.1.1.tgz#581f6ade658cbba65a0d3380de7753295054f375"
  integrity sha512-ojmeN0qd+y0jszEtoY48r0Peq5dwMEkIlCOu6Q5f41lfkswXuKtYrhgoTpLnyIcHm24Uhqx+5Tqm2InSwLhE6Q==

path-parse@^1.0.7:
  version "1.0.7"
  resolved "https://registry.npmmirror.com/path-parse/-/path-parse-1.0.7.tgz#fbc114b60ca42b30d9daf5858e4bd68bbedb6735"
  integrity sha512-LDJzPVEEEPR+y48z93A0Ed0yXb8pAByGWo/k5YYdYgpY2/2EsOsksJrq7lOHxryrVOn1ejG6oAp8ahvOIQD8sw==

path-to-regexp@0.1.7:
  version "0.1.7"
  resolved "https://registry.npmmirror.com/path-to-regexp/-/path-to-regexp-0.1.7.tgz#df604178005f522f15eb4490e7247a1bfaa67f8c"
  integrity sha512-5DFkuoqlv1uYQKxy8omFBeJPQcdoE07Kv2sferDCrAq1ohOU+MSDswDIbnx3YAM60qIOnYa53wBhXW0EbMonrQ==

path-to-regexp@2.2.1:
  version "2.2.1"
  resolved "https://registry.npmmirror.com/path-to-regexp/-/path-to-regexp-2.2.1.tgz#90b617025a16381a879bc82a38d4e8bdeb2bcf45"
  integrity sha512-gu9bD6Ta5bwGrrU8muHzVOBFFREpp2iRkVfhBJahwJ6p6Xw20SjT0MxLnwkjOibQmGSYhiUnf2FLe7k+jcFmGQ==

path-to-regexp@^1.7.0:
  version "1.8.0"
  resolved "https://registry.npmmirror.com/path-to-regexp/-/path-to-regexp-1.8.0.tgz#887b3ba9d84393e87a0a0b9f4cb756198b53548a"
  integrity sha512-n43JRhlUKUAlibEJhPeir1ncUID16QnEjNpwzNdO3Lm4ywrBpBZ5oLD0I6br9evr1Y9JTqwRtAh7JLoOzAQdVA==
  dependencies:
    isarray "0.0.1"

path-type@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/path-type/-/path-type-4.0.0.tgz#84ed01c0a7ba380afe09d90a8c180dcd9d03043b"
  integrity sha512-gDKb8aZMDeD/tZWs9P6+q0J9Mwkdl6xMV8TjnGP3qJVJ06bdMgkbBlLU8IdfOsIsFz2BW1rNVT3XuNEl8zPAvw==

picocolors@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/picocolors/-/picocolors-1.0.0.tgz#cb5bdc74ff3f51892236eaf79d68bc44564ab81c"
  integrity sha512-1fygroTLlHu66zi26VoTDv8yRgm0Fccecssto+MhsZ0D/DGW2sm8E8AjW7NU5VVTRt5GxbeZ5qBuJr+HyLYkjQ==

picomatch@^2.0.4, picomatch@^2.2.1, picomatch@^2.3.1:
  version "2.3.1"
  resolved "https://registry.npmmirror.com/picomatch/-/picomatch-2.3.1.tgz#3ba3833733646d9d3e4995946c1365a67fb07a42"
  integrity sha512-JU3teHTNjmE2VCGFzuY8EXzCDVwEqB2a8fsIvwaStHhAWJEeVd1o1QD80CU6+ZdEXXSLbSsuLwJjkCBWqRQUVA==

pify@^4.0.1:
  version "4.0.1"
  resolved "https://registry.npmmirror.com/pify/-/pify-4.0.1.tgz#4b2cd25c50d598735c50292224fd8c6df41e3231"
  integrity sha512-uB80kBFb/tfd68bVleG9T5GGsGPjJrLAUpR5PZIrhBnIaRTQRjqdJSsIKkOP6OAIFbj7GOrcudc5pNjZ+geV2g==

pkg-dir@^4.1.0:
  version "4.2.0"
  resolved "https://registry.npmmirror.com/pkg-dir/-/pkg-dir-4.2.0.tgz#f099133df7ede422e81d1d8448270eeb3e4261f3"
  integrity sha512-HRDzbaKjC+AOWVXxAU/x54COGeIv9eb+6CkDSQoNTt4XyWoIJvuPsXizxu/Fr23EiekbtZwmh1IcIG/l/a10GQ==
  dependencies:
    find-up "^4.0.0"

pkg-up@^3.1.0:
  version "3.1.0"
  resolved "https://registry.npmmirror.com/pkg-up/-/pkg-up-3.1.0.tgz#100ec235cc150e4fd42519412596a28512a0def5"
  integrity sha512-nDywThFk1i4BQK4twPQ6TA4RT8bDY96yeuCVBWL3ePARCiEKDRSrNGbFIgUJpLp+XeIR65v8ra7WuJOFUBtkMA==
  dependencies:
    find-up "^3.0.0"

postcss-calc@^8.2.3:
  version "8.2.4"
  resolved "https://registry.npmmirror.com/postcss-calc/-/postcss-calc-8.2.4.tgz#77b9c29bfcbe8a07ff6693dc87050828889739a5"
  integrity sha512-SmWMSJmB8MRnnULldx0lQIyhSNvuDl9HfrZkaqqE/WHAhToYsAvDq+yAsA/kIyINDszOp3Rh0GFoNuH5Ypsm3Q==
  dependencies:
    postcss-selector-parser "^6.0.9"
    postcss-value-parser "^4.2.0"

postcss-colormin@^5.3.0:
  version "5.3.0"
  resolved "https://registry.npmmirror.com/postcss-colormin/-/postcss-colormin-5.3.0.tgz#3cee9e5ca62b2c27e84fce63affc0cfb5901956a"
  integrity sha512-WdDO4gOFG2Z8n4P8TWBpshnL3JpmNmJwdnfP2gbk2qBA8PWwOYcmjmI/t3CmMeL72a7Hkd+x/Mg9O2/0rD54Pg==
  dependencies:
    browserslist "^4.16.6"
    caniuse-api "^3.0.0"
    colord "^2.9.1"
    postcss-value-parser "^4.2.0"

postcss-convert-values@^5.1.3:
  version "5.1.3"
  resolved "https://registry.npmmirror.com/postcss-convert-values/-/postcss-convert-values-5.1.3.tgz#04998bb9ba6b65aa31035d669a6af342c5f9d393"
  integrity sha512-82pC1xkJZtcJEfiLw6UXnXVXScgtBrjlO5CBmuDQc+dlb88ZYheFsjTn40+zBVi3DkfF7iezO0nJUPLcJK3pvA==
  dependencies:
    browserslist "^4.21.4"
    postcss-value-parser "^4.2.0"

postcss-discard-comments@^5.1.2:
  version "5.1.2"
  resolved "https://registry.npmmirror.com/postcss-discard-comments/-/postcss-discard-comments-5.1.2.tgz#8df5e81d2925af2780075840c1526f0660e53696"
  integrity sha512-+L8208OVbHVF2UQf1iDmRcbdjJkuBF6IS29yBDSiWUIzpYaAhtNl6JYnYm12FnkeCwQqF5LeklOu6rAqgfBZqQ==

postcss-discard-duplicates@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-discard-duplicates/-/postcss-discard-duplicates-5.1.0.tgz#9eb4fe8456706a4eebd6d3b7b777d07bad03e848"
  integrity sha512-zmX3IoSI2aoenxHV6C7plngHWWhUOV3sP1T8y2ifzxzbtnuhk1EdPwm0S1bIUNaJ2eNbWeGLEwzw8huPD67aQw==

postcss-discard-empty@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/postcss-discard-empty/-/postcss-discard-empty-5.1.1.tgz#e57762343ff7f503fe53fca553d18d7f0c369c6c"
  integrity sha512-zPz4WljiSuLWsI0ir4Mcnr4qQQ5e1Ukc3i7UfE2XcrwKK2LIPIqE5jxMRxO6GbI3cv//ztXDsXwEWT3BHOGh3A==

postcss-discard-overridden@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-discard-overridden/-/postcss-discard-overridden-5.1.0.tgz#7e8c5b53325747e9d90131bb88635282fb4a276e"
  integrity sha512-21nOL7RqWR1kasIVdKs8HNqQJhFxLsyRfAnUDm4Fe4t4mCWL9OJiHvlHPjcd8zc5Myu89b/7wZDnOSjFgeWRtw==

postcss-discard-unused@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-discard-unused/-/postcss-discard-unused-5.1.0.tgz#8974e9b143d887677304e558c1166d3762501142"
  integrity sha512-KwLWymI9hbwXmJa0dkrzpRbSJEh0vVUd7r8t0yOGPcfKzyJJxFM8kLyC5Ev9avji6nY95pOp1W6HqIrfT+0VGw==
  dependencies:
    postcss-selector-parser "^6.0.5"

postcss-loader@^6.1.1:
  version "6.2.1"
  resolved "https://registry.npmmirror.com/postcss-loader/-/postcss-loader-6.2.1.tgz#0895f7346b1702103d30fdc66e4d494a93c008ef"
  integrity sha512-WbbYpmAaKcux/P66bZ40bpWsBucjx/TTgVVzRZ9yUO8yQfVBlameJ0ZGVaPfH64hNSBh63a+ICP5nqOpBA0w+Q==
  dependencies:
    cosmiconfig "^7.0.0"
    klona "^2.0.5"
    semver "^7.3.5"

postcss-merge-idents@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/postcss-merge-idents/-/postcss-merge-idents-5.1.1.tgz#7753817c2e0b75d0853b56f78a89771e15ca04a1"
  integrity sha512-pCijL1TREiCoog5nQp7wUe+TUonA2tC2sQ54UGeMmryK3UFGIYKqDyjnqd6RcuI4znFn9hWSLNN8xKE/vWcUQw==
  dependencies:
    cssnano-utils "^3.1.0"
    postcss-value-parser "^4.2.0"

postcss-merge-longhand@^5.1.7:
  version "5.1.7"
  resolved "https://registry.npmmirror.com/postcss-merge-longhand/-/postcss-merge-longhand-5.1.7.tgz#24a1bdf402d9ef0e70f568f39bdc0344d568fb16"
  integrity sha512-YCI9gZB+PLNskrK0BB3/2OzPnGhPkBEwmwhfYk1ilBHYVAZB7/tkTHFBAnCrvBBOmeYyMYw3DMjT55SyxMBzjQ==
  dependencies:
    postcss-value-parser "^4.2.0"
    stylehacks "^5.1.1"

postcss-merge-rules@^5.1.3:
  version "5.1.3"
  resolved "https://registry.npmmirror.com/postcss-merge-rules/-/postcss-merge-rules-5.1.3.tgz#8f97679e67cc8d08677a6519afca41edf2220894"
  integrity sha512-LbLd7uFC00vpOuMvyZop8+vvhnfRGpp2S+IMQKeuOZZapPRY4SMq5ErjQeHbHsjCUgJkRNrlU+LmxsKIqPKQlA==
  dependencies:
    browserslist "^4.21.4"
    caniuse-api "^3.0.0"
    cssnano-utils "^3.1.0"
    postcss-selector-parser "^6.0.5"

postcss-minify-font-values@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-minify-font-values/-/postcss-minify-font-values-5.1.0.tgz#f1df0014a726083d260d3bd85d7385fb89d1f01b"
  integrity sha512-el3mYTgx13ZAPPirSVsHqFzl+BBBDrXvbySvPGFnQcTI4iNslrPaFq4muTkLZmKlGk4gyFAYUBMH30+HurREyA==
  dependencies:
    postcss-value-parser "^4.2.0"

postcss-minify-gradients@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/postcss-minify-gradients/-/postcss-minify-gradients-5.1.1.tgz#f1fe1b4f498134a5068240c2f25d46fcd236ba2c"
  integrity sha512-VGvXMTpCEo4qHTNSa9A0a3D+dxGFZCYwR6Jokk+/3oB6flu2/PnPXAh2x7x52EkY5xlIHLm+Le8tJxe/7TNhzw==
  dependencies:
    colord "^2.9.1"
    cssnano-utils "^3.1.0"
    postcss-value-parser "^4.2.0"

postcss-minify-params@^5.1.4:
  version "5.1.4"
  resolved "https://registry.npmmirror.com/postcss-minify-params/-/postcss-minify-params-5.1.4.tgz#c06a6c787128b3208b38c9364cfc40c8aa5d7352"
  integrity sha512-+mePA3MgdmVmv6g+30rn57USjOGSAyuxUmkfiWpzalZ8aiBkdPYjXWtHuwJGm1v5Ojy0Z0LaSYhHaLJQB0P8Jw==
  dependencies:
    browserslist "^4.21.4"
    cssnano-utils "^3.1.0"
    postcss-value-parser "^4.2.0"

postcss-minify-selectors@^5.2.1:
  version "5.2.1"
  resolved "https://registry.npmmirror.com/postcss-minify-selectors/-/postcss-minify-selectors-5.2.1.tgz#d4e7e6b46147b8117ea9325a915a801d5fe656c6"
  integrity sha512-nPJu7OjZJTsVUmPdm2TcaiohIwxP+v8ha9NehQ2ye9szv4orirRU3SDdtUmKH+10nzn0bAyOXZ0UEr7OpvLehg==
  dependencies:
    postcss-selector-parser "^6.0.5"

postcss-modules-extract-imports@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/postcss-modules-extract-imports/-/postcss-modules-extract-imports-3.0.0.tgz#cda1f047c0ae80c97dbe28c3e76a43b88025741d"
  integrity sha512-bdHleFnP3kZ4NYDhuGlVK+CMrQ/pqUm8bx/oGL93K6gVwiclvX5x0n76fYMKuIGKzlABOy13zsvqjb0f92TEXw==

postcss-modules-local-by-default@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/postcss-modules-local-by-default/-/postcss-modules-local-by-default-4.0.0.tgz#ebbb54fae1598eecfdf691a02b3ff3b390a5a51c"
  integrity sha512-sT7ihtmGSF9yhm6ggikHdV0hlziDTX7oFoXtuVWeDd3hHObNkcHRo9V3yg7vCAY7cONyxJC/XXCmmiHHcvX7bQ==
  dependencies:
    icss-utils "^5.0.0"
    postcss-selector-parser "^6.0.2"
    postcss-value-parser "^4.1.0"

postcss-modules-scope@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/postcss-modules-scope/-/postcss-modules-scope-3.0.0.tgz#9ef3151456d3bbfa120ca44898dfca6f2fa01f06"
  integrity sha512-hncihwFA2yPath8oZ15PZqvWGkWf+XUfQgUGamS4LqoP1anQLOsOJw0vr7J7IwLpoY9fatA2qiGUGmuZL0Iqlg==
  dependencies:
    postcss-selector-parser "^6.0.4"

postcss-modules-values@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/postcss-modules-values/-/postcss-modules-values-4.0.0.tgz#d7c5e7e68c3bb3c9b27cbf48ca0bb3ffb4602c9c"
  integrity sha512-RDxHkAiEGI78gS2ofyvCsu7iycRv7oqw5xMWn9iMoR0N/7mf9D50ecQqUo5BZ9Zh2vH4bCUR/ktCqbB9m8vJjQ==
  dependencies:
    icss-utils "^5.0.0"

postcss-normalize-charset@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-normalize-charset/-/postcss-normalize-charset-5.1.0.tgz#9302de0b29094b52c259e9b2cf8dc0879879f0ed"
  integrity sha512-mSgUJ+pd/ldRGVx26p2wz9dNZ7ji6Pn8VWBajMXFf8jk7vUoSrZ2lt/wZR7DtlZYKesmZI680qjr2CeFF2fbUg==

postcss-normalize-display-values@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-normalize-display-values/-/postcss-normalize-display-values-5.1.0.tgz#72abbae58081960e9edd7200fcf21ab8325c3da8"
  integrity sha512-WP4KIM4o2dazQXWmFaqMmcvsKmhdINFblgSeRgn8BJ6vxaMyaJkwAzpPpuvSIoG/rmX3M+IrRZEz2H0glrQNEA==
  dependencies:
    postcss-value-parser "^4.2.0"

postcss-normalize-positions@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/postcss-normalize-positions/-/postcss-normalize-positions-5.1.1.tgz#ef97279d894087b59325b45c47f1e863daefbb92"
  integrity sha512-6UpCb0G4eofTCQLFVuI3EVNZzBNPiIKcA1AKVka+31fTVySphr3VUgAIULBhxZkKgwLImhzMR2Bw1ORK+37INg==
  dependencies:
    postcss-value-parser "^4.2.0"

postcss-normalize-repeat-style@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/postcss-normalize-repeat-style/-/postcss-normalize-repeat-style-5.1.1.tgz#e9eb96805204f4766df66fd09ed2e13545420fb2"
  integrity sha512-mFpLspGWkQtBcWIRFLmewo8aC3ImN2i/J3v8YCFUwDnPu3Xz4rLohDO26lGjwNsQxB3YF0KKRwspGzE2JEuS0g==
  dependencies:
    postcss-value-parser "^4.2.0"

postcss-normalize-string@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-normalize-string/-/postcss-normalize-string-5.1.0.tgz#411961169e07308c82c1f8c55f3e8a337757e228"
  integrity sha512-oYiIJOf4T9T1N4i+abeIc7Vgm/xPCGih4bZz5Nm0/ARVJ7K6xrDlLwvwqOydvyL3RHNf8qZk6vo3aatiw/go3w==
  dependencies:
    postcss-value-parser "^4.2.0"

postcss-normalize-timing-functions@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-normalize-timing-functions/-/postcss-normalize-timing-functions-5.1.0.tgz#d5614410f8f0b2388e9f240aa6011ba6f52dafbb"
  integrity sha512-DOEkzJ4SAXv5xkHl0Wa9cZLF3WCBhF3o1SKVxKQAa+0pYKlueTpCgvkFAHfk+Y64ezX9+nITGrDZeVGgITJXjg==
  dependencies:
    postcss-value-parser "^4.2.0"

postcss-normalize-unicode@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/postcss-normalize-unicode/-/postcss-normalize-unicode-5.1.1.tgz#f67297fca3fea7f17e0d2caa40769afc487aa030"
  integrity sha512-qnCL5jzkNUmKVhZoENp1mJiGNPcsJCs1aaRmURmeJGES23Z/ajaln+EPTD+rBeNkSryI+2WTdW+lwcVdOikrpA==
  dependencies:
    browserslist "^4.21.4"
    postcss-value-parser "^4.2.0"

postcss-normalize-url@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-normalize-url/-/postcss-normalize-url-5.1.0.tgz#ed9d88ca82e21abef99f743457d3729a042adcdc"
  integrity sha512-5upGeDO+PVthOxSmds43ZeMeZfKH+/DKgGRD7TElkkyS46JXAUhMzIKiCa7BabPeIy3AQcTkXwVVN7DbqsiCew==
  dependencies:
    normalize-url "^6.0.1"
    postcss-value-parser "^4.2.0"

postcss-normalize-whitespace@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/postcss-normalize-whitespace/-/postcss-normalize-whitespace-5.1.1.tgz#08a1a0d1ffa17a7cc6efe1e6c9da969cc4493cfa"
  integrity sha512-83ZJ4t3NUDETIHTa3uEg6asWjSBYL5EdkVB0sDncx9ERzOKBVJIUeDO9RyA9Zwtig8El1d79HBp0JEi8wvGQnA==
  dependencies:
    postcss-value-parser "^4.2.0"

postcss-ordered-values@^5.1.3:
  version "5.1.3"
  resolved "https://registry.npmmirror.com/postcss-ordered-values/-/postcss-ordered-values-5.1.3.tgz#b6fd2bd10f937b23d86bc829c69e7732ce76ea38"
  integrity sha512-9UO79VUhPwEkzbb3RNpqqghc6lcYej1aveQteWY+4POIwlqkYE21HKWaLDF6lWNuqCobEAyTovVhtI32Rbv2RQ==
  dependencies:
    cssnano-utils "^3.1.0"
    postcss-value-parser "^4.2.0"

postcss-reduce-idents@^5.2.0:
  version "5.2.0"
  resolved "https://registry.npmmirror.com/postcss-reduce-idents/-/postcss-reduce-idents-5.2.0.tgz#c89c11336c432ac4b28792f24778859a67dfba95"
  integrity sha512-BTrLjICoSB6gxbc58D5mdBK8OhXRDqud/zodYfdSi52qvDHdMwk+9kB9xsM8yJThH/sZU5A6QVSmMmaN001gIg==
  dependencies:
    postcss-value-parser "^4.2.0"

postcss-reduce-initial@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/postcss-reduce-initial/-/postcss-reduce-initial-5.1.1.tgz#c18b7dfb88aee24b1f8e4936541c29adbd35224e"
  integrity sha512-//jeDqWcHPuXGZLoolFrUXBDyuEGbr9S2rMo19bkTIjBQ4PqkaO+oI8wua5BOUxpfi97i3PCoInsiFIEBfkm9w==
  dependencies:
    browserslist "^4.21.4"
    caniuse-api "^3.0.0"

postcss-reduce-transforms@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-reduce-transforms/-/postcss-reduce-transforms-5.1.0.tgz#333b70e7758b802f3dd0ddfe98bb1ccfef96b6e9"
  integrity sha512-2fbdbmgir5AvpW9RLtdONx1QoYG2/EtqpNQbFASDlixBbAYuTcJ0dECwlqNqH7VbaUnEnh8SrxOe2sRIn24XyQ==
  dependencies:
    postcss-value-parser "^4.2.0"

postcss-selector-parser@^6.0.2, postcss-selector-parser@^6.0.4, postcss-selector-parser@^6.0.5, postcss-selector-parser@^6.0.9:
  version "6.0.10"
  resolved "https://registry.npmmirror.com/postcss-selector-parser/-/postcss-selector-parser-6.0.10.tgz#79b61e2c0d1bfc2602d549e11d0876256f8df88d"
  integrity sha512-IQ7TZdoaqbT+LCpShg46jnZVlhWD2w6iQYAcYXfHARZ7X1t/UGhhceQDs5X0cGqKvYlHNOuv7Oa1xmb0oQuA3w==
  dependencies:
    cssesc "^3.0.0"
    util-deprecate "^1.0.2"

postcss-sort-media-queries@^4.1.0:
  version "4.3.0"
  resolved "https://registry.npmmirror.com/postcss-sort-media-queries/-/postcss-sort-media-queries-4.3.0.tgz#f48a77d6ce379e86676fc3f140cf1b10a06f6051"
  integrity sha512-jAl8gJM2DvuIJiI9sL1CuiHtKM4s5aEIomkU8G3LFvbP+p8i7Sz8VV63uieTgoewGqKbi+hxBTiOKJlB35upCg==
  dependencies:
    sort-css-media-queries "2.1.0"

postcss-svgo@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-svgo/-/postcss-svgo-5.1.0.tgz#0a317400ced789f233a28826e77523f15857d80d"
  integrity sha512-D75KsH1zm5ZrHyxPakAxJWtkyXew5qwS70v56exwvw542d9CRtTo78K0WeFxZB4G7JXKKMbEZtZayTGdIky/eA==
  dependencies:
    postcss-value-parser "^4.2.0"
    svgo "^2.7.0"

postcss-unique-selectors@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/postcss-unique-selectors/-/postcss-unique-selectors-5.1.1.tgz#a9f273d1eacd09e9aa6088f4b0507b18b1b541b6"
  integrity sha512-5JiODlELrz8L2HwxfPnhOWZYWDxVHWL83ufOv84NrcgipI7TaeRsatAhK4Tr2/ZiYldpK/wBvw5BD3qfaK96GA==
  dependencies:
    postcss-selector-parser "^6.0.5"

postcss-value-parser@^4.1.0, postcss-value-parser@^4.2.0:
  version "4.2.0"
  resolved "https://registry.npmmirror.com/postcss-value-parser/-/postcss-value-parser-4.2.0.tgz#723c09920836ba6d3e5af019f92bc0971c02e514"
  integrity sha512-1NNCs6uurfkVbeXG4S8JFT9t19m45ICnif8zWLd5oPSZ50QnwMfK+H3jv408d4jw/7Bttv5axS5IiHoLaVNHeQ==

postcss-zindex@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/postcss-zindex/-/postcss-zindex-5.1.0.tgz#4a5c7e5ff1050bd4c01d95b1847dfdcc58a496ff"
  integrity sha512-fgFMf0OtVSBR1va1JNHYgMxYk73yhn/qb4uQDq1DLGYolz8gHCyr/sesEuGUaYs58E3ZJRcpoGuPVoB7Meiq9A==

postcss@^8.2.15, postcss@^8.3.11, postcss@^8.3.5, postcss@^8.3.7:
  version "8.4.31"
  resolved "https://registry.yarnpkg.com/postcss/-/postcss-8.4.31.tgz#92b451050a9f914da6755af352bdc0192508656d"
  integrity sha512-PS08Iboia9mts/2ygV3eLpY5ghnUcfLV/EXTOW1E2qYxJKGGBUtNjN76FYHnMs36RmARn41bC0AZmn+rR0OVpQ==
  dependencies:
    nanoid "^3.3.6"
    picocolors "^1.0.0"
    source-map-js "^1.0.2"

pretty-error@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/pretty-error/-/pretty-error-4.0.0.tgz#90a703f46dd7234adb46d0f84823e9d1cb8f10d6"
  integrity sha512-AoJ5YMAcXKYxKhuJGdcvse+Voc6v1RgnsR3nWcYU7q4t6z0Q6T86sv5Zq8VIRbOWWFpvdGE83LtdSMNd+6Y0xw==
  dependencies:
    lodash "^4.17.20"
    renderkid "^3.0.0"

pretty-time@^1.1.0:
  version "1.1.0"
  resolved "https://registry.npmmirror.com/pretty-time/-/pretty-time-1.1.0.tgz#ffb7429afabb8535c346a34e41873adf3d74dd0e"
  integrity sha512-28iF6xPQrP8Oa6uxE6a1biz+lWeTOAPKggvjB8HAs6nVMKZwf5bG++632Dx614hIWgUPkgivRfG+a8uAXGTIbA==

prism-react-renderer@^1.2.1:
  version "1.3.5"
  resolved "https://registry.npmmirror.com/prism-react-renderer/-/prism-react-renderer-1.3.5.tgz#786bb69aa6f73c32ba1ee813fbe17a0115435085"
  integrity sha512-IJ+MSwBWKG+SM3b2SUfdrhC+gu01QkV2KmRQgREThBfSQRoufqRfxfHUxpG1WcaFjP+kojcFyO9Qqtpgt3qLCg==

prismjs@^1.23.0:
  version "1.29.0"
  resolved "https://registry.npmmirror.com/prismjs/-/prismjs-1.29.0.tgz#f113555a8fa9b57c35e637bba27509dcf802dd12"
  integrity sha512-Kx/1w86q/epKcmte75LNrEoT+lX8pBpavuAbvJWRXar7Hz8jrtF+e3vY751p0R8H9HdArwaCTNDDzHg/ScJK1Q==

process-nextick-args@~2.0.0:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/process-nextick-args/-/process-nextick-args-2.0.1.tgz#7820d9b16120cc55ca9ae7792680ae7dba6d7fe2"
  integrity sha512-3ouUOpQhtgrbOa17J7+uxOTpITYWaGP7/AhoR3+A+/1e9skrzelGi/dXzEYyvbxubEF6Wn2ypscTKiKJFFn1ag==

promise@^7.1.1:
  version "7.3.1"
  resolved "https://registry.npmmirror.com/promise/-/promise-7.3.1.tgz#064b72602b18f90f29192b8b1bc418ffd1ebd3bf"
  integrity sha512-nolQXZ/4L+bP/UGlkfaIujX9BKxGwmQ9OT4mOt5yvy8iK1h3wqTEJCijzGANTCCl9nWjY41juyAn2K3Q1hLLTg==
  dependencies:
    asap "~2.0.3"

prompts@^2.4.0, prompts@^2.4.1:
  version "2.4.2"
  resolved "https://registry.npmmirror.com/prompts/-/prompts-2.4.2.tgz#7b57e73b3a48029ad10ebd44f74b01722a4cb069"
  integrity sha512-NxNv/kLguCA7p3jE8oL2aEBsrJWgAakBpgmgK6lpPWV+WuOmY6r2/zbAVnP+T8bQlA0nzHXSJSJW0Hq7ylaD2Q==
  dependencies:
    kleur "^3.0.3"
    sisteransi "^1.0.5"

prop-types@^15.6.2, prop-types@^15.7.2:
  version "15.8.1"
  resolved "https://registry.npmmirror.com/prop-types/-/prop-types-15.8.1.tgz#67d87bf1a694f48435cf332c24af10214a3140b5"
  integrity sha512-oj87CgZICdulUohogVAR7AjlC0327U4el4L6eAvOqCeudMDVU0NThNaV+b9Df4dXgSP1gXMTnPdhfe/2qDH5cg==
  dependencies:
    loose-envify "^1.4.0"
    object-assign "^4.1.1"
    react-is "^16.13.1"

property-information@^5.0.0, property-information@^5.3.0:
  version "5.6.0"
  resolved "https://registry.npmmirror.com/property-information/-/property-information-5.6.0.tgz#61675545fb23002f245c6540ec46077d4da3ed69"
  integrity sha512-YUHSPk+A30YPv+0Qf8i9Mbfe/C0hdPXk1s1jPVToV8pk8BQtpw10ct89Eo7OWkutrwqvT0eicAxlOg3dOAu8JA==
  dependencies:
    xtend "^4.0.0"

proxy-addr@~2.0.7:
  version "2.0.7"
  resolved "https://registry.npmmirror.com/proxy-addr/-/proxy-addr-2.0.7.tgz#f19fe69ceab311eeb94b42e70e8c2070f9ba1025"
  integrity sha512-llQsMLSUDUPT44jdrU/O37qlnifitDP+ZwrmmZcoSKyLKvtZxpyV0n2/bD/N4tBAAZ/gJEdZU7KMraoK1+XYAg==
  dependencies:
    forwarded "0.2.0"
    ipaddr.js "1.9.1"

pump@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/pump/-/pump-3.0.0.tgz#b4a2116815bde2f4e1ea602354e8c75565107a64"
  integrity sha512-LwZy+p3SFs1Pytd/jYct4wpv49HiYCqd9Rlc5ZVdk0V+8Yzv6jR5Blk3TRmPL1ft69TxP0IMZGJ+WPFU2BFhww==
  dependencies:
    end-of-stream "^1.1.0"
    once "^1.3.1"

punycode@^1.3.2:
  version "1.4.1"
  resolved "https://registry.npmmirror.com/punycode/-/punycode-1.4.1.tgz#c0d5a63b2718800ad8e1eb0fa5269c84dd41845e"
  integrity sha512-jmYNElW7yvO7TV33CjSmvSiE2yco3bV2czu/OzDKdMNVZQWfxCblURLhf+47syQRBntjfLdd/H0egrzIG+oaFQ==

punycode@^2.1.0:
  version "2.1.1"
  resolved "https://registry.npmmirror.com/punycode/-/punycode-2.1.1.tgz#b58b010ac40c22c5657616c8d2c2c02c7bf479ec"
  integrity sha512-XRsRjdf+j5ml+y/6GKHPZbrF/8p2Yga0JPtdqTIY2Xe5ohJPD9saDJJLPvp9+NSBprVvevdXZybnj2cv8OEd0A==

pupa@^2.1.1:
  version "2.1.1"
  resolved "https://registry.npmmirror.com/pupa/-/pupa-2.1.1.tgz#f5e8fd4afc2c5d97828faa523549ed8744a20d62"
  integrity sha512-l1jNAspIBSFqbT+y+5FosojNpVpF94nlI+wDUpqP9enwOTfHx9f0gh5nB96vl+6yTpsJsypeNrwfzPrKuHB41A==
  dependencies:
    escape-goat "^2.0.0"

pure-color@^1.2.0:
  version "1.3.0"
  resolved "https://registry.npmmirror.com/pure-color/-/pure-color-1.3.0.tgz#1fe064fb0ac851f0de61320a8bf796836422f33e"
  integrity sha512-QFADYnsVoBMw1srW7OVKEYjG+MbIa49s54w1MA1EDY6r2r/sTcKKYqRX1f4GYvnXP7eN/Pe9HFcX+hwzmrXRHA==

q@^1.1.2:
  version "1.5.1"
  resolved "https://registry.npmmirror.com/q/-/q-1.5.1.tgz#7e32f75b41381291d04611f1bf14109ac00651d7"
  integrity sha512-kV/CThkXo6xyFEZUugw/+pIOywXcDbFYgSct5cT3gqlbkBE1SJdwy6UQoZvodiWF/ckQLZyDE/Bu1M6gVu5lVw==

qs@6.11.0:
  version "6.11.0"
  resolved "https://registry.npmmirror.com/qs/-/qs-6.11.0.tgz#fd0d963446f7a65e1367e01abd85429453f0c37a"
  integrity sha512-MvjoMCJwEarSbUYk5O+nmoSzSutSsTwF85zcHPQ9OrlFoZOYIjaqBAJIqIXjptyD5vThxGq52Xu/MaJzRkIk4Q==
  dependencies:
    side-channel "^1.0.4"

querystring@0.2.0:
  version "0.2.0"
  resolved "https://registry.npmmirror.com/querystring/-/querystring-0.2.0.tgz#b209849203bb25df820da756e747005878521620"
  integrity sha512-X/xY82scca2tau62i9mDyU9K+I+djTMUsvwf7xnUX5GLvVzgJybOJf4Y6o9Zx3oJK/LSXg5tTZBjwzqVPaPO2g==

queue-microtask@^1.2.2:
  version "1.2.3"
  resolved "https://registry.npmmirror.com/queue-microtask/-/queue-microtask-1.2.3.tgz#4929228bbc724dfac43e0efb058caf7b6cfb6243"
  integrity sha512-NuaNSa6flKT5JaSYQzJok04JzTL1CA6aGhv5rfLW3PgqA+M2ChpZQnAC8h8i4ZFkBS8X5RqkDBHA7r4hej3K9A==

quick-lru@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/quick-lru/-/quick-lru-5.1.1.tgz#366493e6b3e42a3a6885e2e99d18f80fb7a8c932"
  integrity sha512-WuyALRjWPDGtt/wzJiadO5AXY+8hZ80hVpe6MyivgraREW751X3SbhRvG3eLKOYN+8VEvqLcf3wdnt44Z4S4SA==

randombytes@^2.1.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/randombytes/-/randombytes-2.1.0.tgz#df6f84372f0270dc65cdf6291349ab7a473d4f2a"
  integrity sha512-vYl3iOX+4CKUWuxGi9Ukhie6fsqXqS9FE2Zaic4tNFD2N2QQaXOMFbuKK4QmDHC0JO6B1Zp41J0LpT0oR68amQ==
  dependencies:
    safe-buffer "^5.1.0"

range-parser@1.2.0:
  version "1.2.0"
  resolved "https://registry.npmmirror.com/range-parser/-/range-parser-1.2.0.tgz#f49be6b487894ddc40dcc94a322f611092e00d5e"
  integrity sha512-kA5WQoNVo4t9lNx2kQNFCxKeBl5IbbSNBl1M/tLkw9WCn+hxNBAW5Qh8gdhs63CJnhjJ2zQWFoqPJP2sK1AV5A==

range-parser@^1.2.1, range-parser@~1.2.1:
  version "1.2.1"
  resolved "https://registry.npmmirror.com/range-parser/-/range-parser-1.2.1.tgz#3cf37023d199e1c24d1a55b84800c2f3e6468031"
  integrity sha512-Hrgsx+orqoygnmhFbKaHE6c296J+HTAQXoxEF6gNupROmmGJRoyzfG3ccAveqCBrwr/2yxQ5BVd/GTl5agOwSg==

raw-body@2.5.1:
  version "2.5.1"
  resolved "https://registry.npmmirror.com/raw-body/-/raw-body-2.5.1.tgz#fe1b1628b181b700215e5fd42389f98b71392857"
  integrity sha512-qqJBtEyVgS0ZmPGdCFPWJ3FreoqvG4MVQln/kCgF7Olq95IbOp0/BWyMwbdtn4VTvkM8Y7khCQ2Xgk/tcrCXig==
  dependencies:
    bytes "3.1.2"
    http-errors "2.0.0"
    iconv-lite "0.4.24"
    unpipe "1.0.0"

rc@1.2.8, rc@^1.2.8:
  version "1.2.8"
  resolved "https://registry.npmmirror.com/rc/-/rc-1.2.8.tgz#cd924bf5200a075b83c188cd6b9e211b7fc0d3ed"
  integrity sha512-y3bGgqKj3QBdxLbLkomlohkvsA8gdAiUQlSBJnBhfn+BPxg4bc62d8TcBW15wavDfgexCgccckhcZvywyQYPOw==
  dependencies:
    deep-extend "^0.6.0"
    ini "~1.3.0"
    minimist "^1.2.0"
    strip-json-comments "~2.0.1"

react-base16-styling@^0.6.0:
  version "0.6.0"
  resolved "https://registry.npmmirror.com/react-base16-styling/-/react-base16-styling-0.6.0.tgz#ef2156d66cf4139695c8a167886cb69ea660792c"
  integrity sha512-yvh/7CArceR/jNATXOKDlvTnPKPmGZz7zsenQ3jUwLzHkNUR0CvY3yGYJbWJ/nnxsL8Sgmt5cO3/SILVuPO6TQ==
  dependencies:
    base16 "^1.0.0"
    lodash.curry "^4.0.1"
    lodash.flow "^3.3.0"
    pure-color "^1.2.0"

react-dev-utils@12.0.0-next.47:
  version "12.0.0-next.47"
  resolved "https://registry.npmmirror.com/react-dev-utils/-/react-dev-utils-12.0.0-next.47.tgz#e55c31a05eb30cfd69ca516e8b87d61724e880fb"
  integrity sha512-PsE71vP15TZMmp/RZKOJC4fYD5Pvt0+wCoyG3QHclto0d4FyIJI78xGRICOOThZFROqgXYlZP6ddmeybm+jO4w==
  dependencies:
    "@babel/code-frame" "^7.10.4"
    address "^1.1.2"
    browserslist "^4.16.5"
    chalk "^2.4.2"
    cross-spawn "^7.0.3"
    detect-port-alt "^1.1.6"
    escape-string-regexp "^2.0.0"
    filesize "^6.1.0"
    find-up "^4.1.0"
    fork-ts-checker-webpack-plugin "^6.0.5"
    global-modules "^2.0.0"
    globby "^11.0.1"
    gzip-size "^5.1.1"
    immer "^9.0.6"
    is-root "^2.1.0"
    loader-utils "^2.0.0"
    open "^7.0.2"
    pkg-up "^3.1.0"
    prompts "^2.4.0"
    react-error-overlay "7.0.0-next.54+1465357b"
    recursive-readdir "^2.2.2"
    shell-quote "^1.7.2"
    strip-ansi "^6.0.0"
    text-table "^0.2.0"

react-dom@^17.0.1:
  version "17.0.2"
  resolved "https://registry.npmmirror.com/react-dom/-/react-dom-17.0.2.tgz#ecffb6845e3ad8dbfcdc498f0d0a939736502c23"
  integrity sha512-s4h96KtLDUQlsENhMn1ar8t2bEa+q/YAtj8pPPdIjPDGBDIVNsrD9aXNWqspUe6AzKCIG0C1HZZLqLV7qpOBGA==
  dependencies:
    loose-envify "^1.1.0"
    object-assign "^4.1.1"
    scheduler "^0.20.2"

react-error-overlay@7.0.0-next.54+1465357b:
  version "7.0.0-next.54"
  resolved "https://registry.npmmirror.com/react-error-overlay/-/react-error-overlay-7.0.0-next.54.tgz#c1eb5ab86aee15e9552e6d97897b08f2bd06d140"
  integrity sha512-b96CiTnZahXPDNH9MKplvt5+jD+BkxDw7q5R3jnkUXze/ux1pLv32BBZmlj0OfCUeMqyz4sAmF+0ccJGVMlpXw==

react-error-overlay@^6.0.9:
  version "6.0.11"
  resolved "https://registry.npmmirror.com/react-error-overlay/-/react-error-overlay-6.0.11.tgz#92835de5841c5cf08ba00ddd2d677b6d17ff9adb"
  integrity sha512-/6UZ2qgEyH2aqzYZgQPxEnz33NJ2gNsnHA2o5+o4wW9bLM/JYQitNP9xPhsXwC08hMMovfGe/8retsdDsczPRg==

react-fast-compare@^3.1.1:
  version "3.2.0"
  resolved "https://registry.npmmirror.com/react-fast-compare/-/react-fast-compare-3.2.0.tgz#641a9da81b6a6320f270e89724fb45a0b39e43bb"
  integrity sha512-rtGImPZ0YyLrscKI9xTpV8psd6I8VAtjKCzQDlzyDvqJA8XOW78TXYQwNRNd8g8JZnDu8q9Fu/1v4HPAVwVdHA==

react-helmet@^6.1.0:
  version "6.1.0"
  resolved "https://registry.npmmirror.com/react-helmet/-/react-helmet-6.1.0.tgz#a750d5165cb13cf213e44747502652e794468726"
  integrity sha512-4uMzEY9nlDlgxr61NL3XbKRy1hEkXmKNXhjbAIOVw5vcFrsdYbH2FEwcNyWvWinl103nXgzYNlns9ca+8kFiWw==
  dependencies:
    object-assign "^4.1.1"
    prop-types "^15.7.2"
    react-fast-compare "^3.1.1"
    react-side-effect "^2.1.0"

react-is@^16.13.1, react-is@^16.6.0, react-is@^16.7.0:
  version "16.13.1"
  resolved "https://registry.npmmirror.com/react-is/-/react-is-16.13.1.tgz#789729a4dc36de2999dc156dd6c1d9c18cea56a4"
  integrity sha512-24e6ynE2H+OKt4kqsOvNd8kBpV65zoxbA4BVsEOB3ARVWQki/DHzaUoC5KuON/BiccDaCCTZBuOcfZs70kR8bQ==

react-json-view@^1.21.3:
  version "1.21.3"
  resolved "https://registry.npmmirror.com/react-json-view/-/react-json-view-1.21.3.tgz#f184209ee8f1bf374fb0c41b0813cff54549c475"
  integrity sha512-13p8IREj9/x/Ye4WI/JpjhoIwuzEgUAtgJZNBJckfzJt1qyh24BdTm6UQNGnyTq9dapQdrqvquZTo3dz1X6Cjw==
  dependencies:
    flux "^4.0.1"
    react-base16-styling "^0.6.0"
    react-lifecycles-compat "^3.0.4"
    react-textarea-autosize "^8.3.2"

react-lifecycles-compat@^3.0.4:
  version "3.0.4"
  resolved "https://registry.npmmirror.com/react-lifecycles-compat/-/react-lifecycles-compat-3.0.4.tgz#4f1a273afdfc8f3488a8c516bfda78f872352362"
  integrity sha512-fBASbA6LnOU9dOU2eW7aQ8xmYBSXUIWr+UmF9b1efZBazGNO+rcXT/icdKnYm2pTwcRylVUYwW7H1PHfLekVzA==

react-loadable-ssr-addon-v5-slorber@^1.0.1:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/react-loadable-ssr-addon-v5-slorber/-/react-loadable-ssr-addon-v5-slorber-1.0.1.tgz#2cdc91e8a744ffdf9e3556caabeb6e4278689883"
  integrity sha512-lq3Lyw1lGku8zUEJPDxsNm1AfYHBrO9Y1+olAYwpUJ2IGFBskM0DMKok97A6LWUpHm+o7IvQBOWu9MLenp9Z+A==
  dependencies:
    "@babel/runtime" "^7.10.3"

react-router-config@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/react-router-config/-/react-router-config-5.1.1.tgz#0f4263d1a80c6b2dc7b9c1902c9526478194a988"
  integrity sha512-DuanZjaD8mQp1ppHjgnnUnyOlqYXZVjnov/JzFhjLEwd3Z4dYjMSnqrEzzGThH47vpCOqPPwJM2FtthLeJ8Pbg==
  dependencies:
    "@babel/runtime" "^7.1.2"

react-router-dom@^5.2.0:
  version "5.3.4"
  resolved "https://registry.npmmirror.com/react-router-dom/-/react-router-dom-5.3.4.tgz#2ed62ffd88cae6db134445f4a0c0ae8b91d2e5e6"
  integrity sha512-m4EqFMHv/Ih4kpcBCONHbkT68KoAeHN4p3lAGoNryfHi0dMy0kCzEZakiKRsvg5wHZ/JLrLW8o8KomWiz/qbYQ==
  dependencies:
    "@babel/runtime" "^7.12.13"
    history "^4.9.0"
    loose-envify "^1.3.1"
    prop-types "^15.6.2"
    react-router "5.3.4"
    tiny-invariant "^1.0.2"
    tiny-warning "^1.0.0"

react-router@5.3.4, react-router@^5.2.0:
  version "5.3.4"
  resolved "https://registry.npmmirror.com/react-router/-/react-router-5.3.4.tgz#8ca252d70fcc37841e31473c7a151cf777887bb5"
  integrity sha512-Ys9K+ppnJah3QuaRiLxk+jDWOR1MekYQrlytiXxC1RyfbdsZkS5pvKAzCCr031xHixZwpnsYNT5xysdFHQaYsA==
  dependencies:
    "@babel/runtime" "^7.12.13"
    history "^4.9.0"
    hoist-non-react-statics "^3.1.0"
    loose-envify "^1.3.1"
    path-to-regexp "^1.7.0"
    prop-types "^15.6.2"
    react-is "^16.6.0"
    tiny-invariant "^1.0.2"
    tiny-warning "^1.0.0"

react-side-effect@^2.1.0:
  version "2.1.2"
  resolved "https://registry.npmmirror.com/react-side-effect/-/react-side-effect-2.1.2.tgz#dc6345b9e8f9906dc2eeb68700b615e0b4fe752a"
  integrity sha512-PVjOcvVOyIILrYoyGEpDN3vmYNLdy1CajSFNt4TDsVQC5KpTijDvWVoR+/7Rz2xT978D8/ZtFceXxzsPwZEDvw==

react-textarea-autosize@^8.3.2:
  version "8.3.4"
  resolved "https://registry.npmmirror.com/react-textarea-autosize/-/react-textarea-autosize-8.3.4.tgz#270a343de7ad350534141b02c9cb78903e553524"
  integrity sha512-CdtmP8Dc19xL8/R6sWvtknD/eCXkQr30dtvC4VmGInhRsfF8X/ihXCq6+9l9qbxmKRiq407/7z5fxE7cVWQNgQ==
  dependencies:
    "@babel/runtime" "^7.10.2"
    use-composed-ref "^1.3.0"
    use-latest "^1.2.1"

react@^17.0.1:
  version "17.0.2"
  resolved "https://registry.npmmirror.com/react/-/react-17.0.2.tgz#d0b5cc516d29eb3eee383f75b62864cfb6800037"
  integrity sha512-gnhPt75i/dq/z3/6q/0asP78D0u592D5L1pd7M8P+dck6Fu/jJeL6iVVK23fptSUZj8Vjf++7wXA8UNclGQcbA==
  dependencies:
    loose-envify "^1.1.0"
    object-assign "^4.1.1"

readable-stream@^2.0.1:
  version "2.3.7"
  resolved "https://registry.npmmirror.com/readable-stream/-/readable-stream-2.3.7.tgz#1eca1cf711aef814c04f62252a36a62f6cb23b57"
  integrity sha512-Ebho8K4jIbHAxnuxi7o42OrZgF/ZTNcsZj6nRKyUmkhLFq8CHItp/fy6hQZuZmP/n3yZ9VBUbp4zz/mX8hmYPw==
  dependencies:
    core-util-is "~1.0.0"
    inherits "~2.0.3"
    isarray "~1.0.0"
    process-nextick-args "~2.0.0"
    safe-buffer "~5.1.1"
    string_decoder "~1.1.1"
    util-deprecate "~1.0.1"

readable-stream@^3.0.6:
  version "3.6.0"
  resolved "https://registry.npmmirror.com/readable-stream/-/readable-stream-3.6.0.tgz#337bbda3adc0706bd3e024426a286d4b4b2c9198"
  integrity sha512-BViHy7LKeTz4oNnkcLJ+lVSL6vpiFeX6/d3oSH8zCW7UxP2onchk+vTGB143xuFjHS3deTgkKoXXymXqymiIdA==
  dependencies:
    inherits "^2.0.3"
    string_decoder "^1.1.1"
    util-deprecate "^1.0.1"

readdirp@~3.6.0:
  version "3.6.0"
  resolved "https://registry.npmmirror.com/readdirp/-/readdirp-3.6.0.tgz#74a370bd857116e245b29cc97340cd431a02a6c7"
  integrity sha512-hOS089on8RduqdbhvQ5Z37A0ESjsqz6qnRcffsMU3495FuTdqSm+7bhJ29JvIOsBDEEnan5DPu9t3To9VRlMzA==
  dependencies:
    picomatch "^2.2.1"

reading-time@^1.5.0:
  version "1.5.0"
  resolved "https://registry.npmmirror.com/reading-time/-/reading-time-1.5.0.tgz#d2a7f1b6057cb2e169beaf87113cc3411b5bc5bb"
  integrity sha512-onYyVhBNr4CmAxFsKS7bz+uTLRakypIe4R+5A824vBSkQy/hB3fZepoVEf8OVAxzLvK+H/jm9TzpI3ETSm64Kg==

rechoir@^0.6.2:
  version "0.6.2"
  resolved "https://registry.npmmirror.com/rechoir/-/rechoir-0.6.2.tgz#85204b54dba82d5742e28c96756ef43af50e3384"
  integrity sha512-HFM8rkZ+i3zrV+4LQjwQ0W+ez98pApMGM3HUrN04j3CqzPOzl9nmP15Y8YXNm8QHGv/eacOVEjqhmWpkRV0NAw==
  dependencies:
    resolve "^1.1.6"

recursive-readdir@^2.2.2:
  version "2.2.3"
  resolved "https://registry.npmmirror.com/recursive-readdir/-/recursive-readdir-2.2.3.tgz#e726f328c0d69153bcabd5c322d3195252379372"
  integrity sha512-8HrF5ZsXk5FAH9dgsx3BlUer73nIhuj+9OrQwEbLTPOBzGkL1lsFCR01am+v+0m2Cmbs1nP12hLDl5FA7EszKA==
  dependencies:
    minimatch "^3.0.5"

regenerate-unicode-properties@^10.1.0:
  version "10.1.0"
  resolved "https://registry.npmmirror.com/regenerate-unicode-properties/-/regenerate-unicode-properties-10.1.0.tgz#7c3192cab6dd24e21cb4461e5ddd7dd24fa8374c"
  integrity sha512-d1VudCLoIGitcU/hEg2QqvyGZQmdC0Lf8BqdOMXGFSvJP4bNV1+XqbPQeHHLD51Jh4QJJ225dlIFvY4Ly6MXmQ==
  dependencies:
    regenerate "^1.4.2"

regenerate-unicode-properties@^9.0.0:
  version "9.0.0"
  resolved "https://registry.npmmirror.com/regenerate-unicode-properties/-/regenerate-unicode-properties-9.0.0.tgz#54d09c7115e1f53dc2314a974b32c1c344efe326"
  integrity sha512-3E12UeNSPfjrgwjkR81m5J7Aw/T55Tu7nUyZVQYCKEOs+2dkxEY+DpPtZzO4YruuiPb7NkYLVcyJC4+zCbk5pA==
  dependencies:
    regenerate "^1.4.2"

regenerate@^1.4.2:
  version "1.4.2"
  resolved "https://registry.npmmirror.com/regenerate/-/regenerate-1.4.2.tgz#b9346d8827e8f5a32f7ba29637d398b69014848a"
  integrity sha512-zrceR/XhGYU/d/opr2EKO7aRHUeiBI8qjtfHqADTwZd6Szfy16la6kqD0MIUs5z5hx6AaKa+PixpPrR289+I0A==

regenerator-runtime@^0.13.10:
  version "0.13.10"
  resolved "https://registry.npmmirror.com/regenerator-runtime/-/regenerator-runtime-0.13.10.tgz#ed07b19616bcbec5da6274ebc75ae95634bfc2ee"
  integrity sha512-KepLsg4dU12hryUO7bp/axHAKvwGOCV0sGloQtpagJ12ai+ojVDqkeGSiRX1zlq+kjIMZ1t7gpze+26QqtdGqw==

regenerator-transform@^0.15.0:
  version "0.15.0"
  resolved "https://registry.npmmirror.com/regenerator-transform/-/regenerator-transform-0.15.0.tgz#cbd9ead5d77fae1a48d957cf889ad0586adb6537"
  integrity sha512-LsrGtPmbYg19bcPHwdtmXwbW+TqNvtY4riE3P83foeHRroMbH6/2ddFBfab3t7kbzc7v7p4wbkIecHImqt0QNg==
  dependencies:
    "@babel/runtime" "^7.8.4"

regexp.prototype.flags@^1.4.3:
  version "1.4.3"
  resolved "https://registry.npmmirror.com/regexp.prototype.flags/-/regexp.prototype.flags-1.4.3.tgz#87cab30f80f66660181a3bb7bf5981a872b367ac"
  integrity sha512-fjggEOO3slI6Wvgjwflkc4NFRCTZAu5CnNfBd5qOMYhWdn67nJBBu34/TkD++eeFmd8C9r9jfXJ27+nSiRkSUA==
  dependencies:
    call-bind "^1.0.2"
    define-properties "^1.1.3"
    functions-have-names "^1.2.2"

regexpu-core@^4.5.4:
  version "4.8.0"
  resolved "https://registry.npmmirror.com/regexpu-core/-/regexpu-core-4.8.0.tgz#e5605ba361b67b1718478501327502f4479a98f0"
  integrity sha512-1F6bYsoYiz6is+oz70NWur2Vlh9KWtswuRuzJOfeYUrfPX2o8n74AnUVaOGDbUqVGO9fNHu48/pjJO4sNVwsOg==
  dependencies:
    regenerate "^1.4.2"
    regenerate-unicode-properties "^9.0.0"
    regjsgen "^0.5.2"
    regjsparser "^0.7.0"
    unicode-match-property-ecmascript "^2.0.0"
    unicode-match-property-value-ecmascript "^2.0.0"

regexpu-core@^5.1.0:
  version "5.2.1"
  resolved "https://registry.npmmirror.com/regexpu-core/-/regexpu-core-5.2.1.tgz#a69c26f324c1e962e9ffd0b88b055caba8089139"
  integrity sha512-HrnlNtpvqP1Xkb28tMhBUO2EbyUHdQlsnlAhzWcwHy8WJR53UWr7/MAvqrsQKMbV4qdpv03oTMG8iIhfsPFktQ==
  dependencies:
    regenerate "^1.4.2"
    regenerate-unicode-properties "^10.1.0"
    regjsgen "^0.7.1"
    regjsparser "^0.9.1"
    unicode-match-property-ecmascript "^2.0.0"
    unicode-match-property-value-ecmascript "^2.0.0"

registry-auth-token@^4.0.0:
  version "4.2.2"
  resolved "https://registry.npmmirror.com/registry-auth-token/-/registry-auth-token-4.2.2.tgz#f02d49c3668884612ca031419491a13539e21fac"
  integrity sha512-PC5ZysNb42zpFME6D/XlIgtNGdTl8bBOCw90xQLVMpzuuubJKYDWFAEuUNc+Cn8Z8724tg2SDhDRrkVEsqfDMg==
  dependencies:
    rc "1.2.8"

registry-url@^5.0.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/registry-url/-/registry-url-5.1.0.tgz#e98334b50d5434b81136b44ec638d9c2009c5009"
  integrity sha512-8acYXXTI0AkQv6RAOjE3vOaIXZkT9wo4LOFbBKYQEEnnMNBpKqdUrI6S4NT0KPIo/WVvJ5tE/X5LF/TQUf0ekw==
  dependencies:
    rc "^1.2.8"

regjsgen@^0.5.2:
  version "0.5.2"
  resolved "https://registry.npmmirror.com/regjsgen/-/regjsgen-0.5.2.tgz#92ff295fb1deecbf6ecdab2543d207e91aa33733"
  integrity sha512-OFFT3MfrH90xIW8OOSyUrk6QHD5E9JOTeGodiJeBS3J6IwlgzJMNE/1bZklWz5oTg+9dCMyEetclvCVXOPoN3A==

regjsgen@^0.7.1:
  version "0.7.1"
  resolved "https://registry.npmmirror.com/regjsgen/-/regjsgen-0.7.1.tgz#ee5ef30e18d3f09b7c369b76e7c2373ed25546f6"
  integrity sha512-RAt+8H2ZEzHeYWxZ3H2z6tF18zyyOnlcdaafLrm21Bguj7uZy6ULibiAFdXEtKQY4Sy7wDTwDiOazasMLc4KPA==

regjsparser@^0.7.0:
  version "0.7.0"
  resolved "https://registry.npmmirror.com/regjsparser/-/regjsparser-0.7.0.tgz#a6b667b54c885e18b52554cb4960ef71187e9968"
  integrity sha512-A4pcaORqmNMDVwUjWoTzuhwMGpP+NykpfqAsEgI1FSH/EzC7lrN5TMd+kN8YCovX+jMpu8eaqXgXPCa0g8FQNQ==
  dependencies:
    jsesc "~0.5.0"

regjsparser@^0.9.1:
  version "0.9.1"
  resolved "https://registry.npmmirror.com/regjsparser/-/regjsparser-0.9.1.tgz#272d05aa10c7c1f67095b1ff0addae8442fc5709"
  integrity sha512-dQUtn90WanSNl+7mQKcXAgZxvUe7Z0SqXlgzv0za4LwiUhyzBC58yQO3liFoUgu8GiJVInAhJjkj1N0EtQ5nkQ==
  dependencies:
    jsesc "~0.5.0"

rehype-katex@4:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/rehype-katex/-/rehype-katex-4.0.0.tgz#ce11a5db0bff014350e7a9cfd30147d314b14330"
  integrity sha512-0mgBqYugQyIW0eUl6RDOZ28Cat2YzrnWGaYgKCMQnJw6ClmKgLqXBnkDAPGh2mwxvkkKwQOUMUpSLpA5rt7rzA==
  dependencies:
    "@types/katex" "^0.11.0"
    hast-util-to-text "^2.0.0"
    katex "^0.12.0"
    rehype-parse "^7.0.0"
    unified "^9.0.0"
    unist-util-visit "^2.0.0"

rehype-parse@^6.0.2:
  version "6.0.2"
  resolved "https://registry.npmmirror.com/rehype-parse/-/rehype-parse-6.0.2.tgz#aeb3fdd68085f9f796f1d3137ae2b85a98406964"
  integrity sha512-0S3CpvpTAgGmnz8kiCyFLGuW5yA4OQhyNTm/nwPopZ7+PI11WnGl1TTWTGv/2hPEe/g2jRLlhVVSsoDH8waRug==
  dependencies:
    hast-util-from-parse5 "^5.0.0"
    parse5 "^5.0.0"
    xtend "^4.0.0"

rehype-parse@^7.0.0:
  version "7.0.1"
  resolved "https://registry.npmmirror.com/rehype-parse/-/rehype-parse-7.0.1.tgz#58900f6702b56767814afc2a9efa2d42b1c90c57"
  integrity sha512-fOiR9a9xH+Le19i4fGzIEowAbwG7idy2Jzs4mOrFWBSJ0sNUgy0ev871dwWnbOo371SjgjG4pwzrbgSVrKxecw==
  dependencies:
    hast-util-from-parse5 "^6.0.0"
    parse5 "^6.0.0"

relateurl@^0.2.7:
  version "0.2.7"
  resolved "https://registry.npmmirror.com/relateurl/-/relateurl-0.2.7.tgz#54dbf377e51440aca90a4cd274600d3ff2d888a9"
  integrity sha512-G08Dxvm4iDN3MLM0EsP62EDV9IuhXPR6blNz6Utcp7zyV3tr4HVNINt6MpaRWbxoOHT3Q7YN2P+jaHX8vUbgog==

remark-admonitions@^1.2.1:
  version "1.2.1"
  resolved "https://registry.npmmirror.com/remark-admonitions/-/remark-admonitions-1.2.1.tgz#87caa1a442aa7b4c0cafa04798ed58a342307870"
  integrity sha512-Ji6p68VDvD+H1oS95Fdx9Ar5WA2wcDA4kwrrhVU7fGctC6+d3uiMICu7w7/2Xld+lnU7/gi+432+rRbup5S8ow==
  dependencies:
    rehype-parse "^6.0.2"
    unified "^8.4.2"
    unist-util-visit "^2.0.1"

remark-emoji@^2.1.0:
  version "2.2.0"
  resolved "https://registry.npmmirror.com/remark-emoji/-/remark-emoji-2.2.0.tgz#1c702090a1525da5b80e15a8f963ef2c8236cac7"
  integrity sha512-P3cj9s5ggsUvWw5fS2uzCHJMGuXYRb0NnZqYlNecewXt8QBU9n5vW3DUUKOhepS8F9CwdMx9B8a3i7pqFWAI5w==
  dependencies:
    emoticon "^3.2.0"
    node-emoji "^1.10.0"
    unist-util-visit "^2.0.3"

remark-footnotes@2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/remark-footnotes/-/remark-footnotes-2.0.0.tgz#9001c4c2ffebba55695d2dd80ffb8b82f7e6303f"
  integrity sha512-3Clt8ZMH75Ayjp9q4CorNeyjwIxHFcTkaektplKGl2A1jNGEUey8cKL0ZC5vJwfcD5GFGsNLImLG/NGzWIzoMQ==

remark-math@3:
  version "3.0.1"
  resolved "https://registry.npmmirror.com/remark-math/-/remark-math-3.0.1.tgz#85a02a15b15cad34b89a27244d4887b3a95185bb"
  integrity sha512-epT77R/HK0x7NqrWHdSV75uNLwn8g9qTyMqCRCDujL0vj/6T6+yhdrR7mjELWtkse+Fw02kijAaBuVcHBor1+Q==

remark-mdx-remove-exports@^1.6.22:
  version "1.6.22"
  resolved "https://registry.npmmirror.com/remark-mdx-remove-exports/-/remark-mdx-remove-exports-1.6.22.tgz#9e34f3d02c9c54b02ca0a1fde946449338d06ecb"
  integrity sha512-7g2uiTmTGfz5QyVb+toeX25frbk1Y6yd03RXGPtqx0+DVh86Gb7MkNYbk7H2X27zdZ3CQv1W/JqlFO0Oo8IxVA==
  dependencies:
    unist-util-remove "2.0.0"

remark-mdx-remove-imports@^1.6.22:
  version "1.6.22"
  resolved "https://registry.npmmirror.com/remark-mdx-remove-imports/-/remark-mdx-remove-imports-1.6.22.tgz#79f711c95359cff437a120d1fbdc1326ec455826"
  integrity sha512-lmjAXD8Ltw0TsvBzb45S+Dxx7LTJAtDaMneMAv8LAUIPEyYoKkmGbmVsiF0/pY6mhM1Q16swCmu1TN+ie/vn/A==
  dependencies:
    unist-util-remove "2.0.0"

remark-mdx@1.6.22:
  version "1.6.22"
  resolved "https://registry.npmmirror.com/remark-mdx/-/remark-mdx-1.6.22.tgz#06a8dab07dcfdd57f3373af7f86bd0e992108bbd"
  integrity sha512-phMHBJgeV76uyFkH4rvzCftLfKCr2RZuF+/gmVcaKrpsihyzmhXjA0BEMDaPTXG5y8qZOKPVo83NAOX01LPnOQ==
  dependencies:
    "@babel/core" "7.12.9"
    "@babel/helper-plugin-utils" "7.10.4"
    "@babel/plugin-proposal-object-rest-spread" "7.12.1"
    "@babel/plugin-syntax-jsx" "7.12.1"
    "@mdx-js/util" "1.6.22"
    is-alphabetical "1.0.4"
    remark-parse "8.0.3"
    unified "9.2.0"

remark-parse@8.0.3:
  version "8.0.3"
  resolved "https://registry.npmmirror.com/remark-parse/-/remark-parse-8.0.3.tgz#9c62aa3b35b79a486454c690472906075f40c7e1"
  integrity sha512-E1K9+QLGgggHxCQtLt++uXltxEprmWzNfg+MxpfHsZlrddKzZ/hZyWHDbK3/Ap8HJQqYJRXP+jHczdL6q6i85Q==
  dependencies:
    ccount "^1.0.0"
    collapse-white-space "^1.0.2"
    is-alphabetical "^1.0.0"
    is-decimal "^1.0.0"
    is-whitespace-character "^1.0.0"
    is-word-character "^1.0.0"
    markdown-escapes "^1.0.0"
    parse-entities "^2.0.0"
    repeat-string "^1.5.4"
    state-toggle "^1.0.0"
    trim "0.0.1"
    trim-trailing-lines "^1.0.0"
    unherit "^1.0.4"
    unist-util-remove-position "^2.0.0"
    vfile-location "^3.0.0"
    xtend "^4.0.1"

remark-squeeze-paragraphs@4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/remark-squeeze-paragraphs/-/remark-squeeze-paragraphs-4.0.0.tgz#76eb0e085295131c84748c8e43810159c5653ead"
  integrity sha512-8qRqmL9F4nuLPIgl92XUuxI3pFxize+F1H0e/W3llTk0UsjJaj01+RrirkMw7P21RKe4X6goQhYRSvNWX+70Rw==
  dependencies:
    mdast-squeeze-paragraphs "^4.0.0"

renderkid@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/renderkid/-/renderkid-3.0.0.tgz#5fd823e4d6951d37358ecc9a58b1f06836b6268a"
  integrity sha512-q/7VIQA8lmM1hF+jn+sFSPWGlMkSAeNYcPLmDQx2zzuiDfaLrOmumR8iaUKlenFgh0XRPIUeSPlH3A+AW3Z5pg==
  dependencies:
    css-select "^4.1.3"
    dom-converter "^0.2.0"
    htmlparser2 "^6.1.0"
    lodash "^4.17.21"
    strip-ansi "^6.0.1"

repeat-string@^1.0.0, repeat-string@^1.5.4:
  version "1.6.1"
  resolved "https://registry.npmmirror.com/repeat-string/-/repeat-string-1.6.1.tgz#8dcae470e1c88abc2d600fff4a776286da75e637"
  integrity sha512-PV0dzCYDNfRi1jCDbJzpW7jNNDRuCOG/jI5ctQcGKt/clZD+YcPS3yIlWuTJMmESC8aevCFmWJy5wjAFgNqN6w==

require-from-string@^2.0.2:
  version "2.0.2"
  resolved "https://registry.npmmirror.com/require-from-string/-/require-from-string-2.0.2.tgz#89a7fdd938261267318eafe14f9c32e598c36909"
  integrity sha512-Xf0nWe6RseziFMu+Ap9biiUbmplq6S9/p+7w7YXP/JBHhrUDDUhwa+vANyubuqfZWTveU//DYVGsDG7RKL/vEw==

"require-like@>= 0.1.1":
  version "0.1.2"
  resolved "https://registry.npmmirror.com/require-like/-/require-like-0.1.2.tgz#ad6f30c13becd797010c468afa775c0c0a6b47fa"
  integrity sha512-oyrU88skkMtDdauHDuKVrgR+zuItqr6/c//FXzvmxRGMexSDc6hNvJInGW3LL46n+8b50RykrvwSUIIQH2LQ5A==

requires-port@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/requires-port/-/requires-port-1.0.0.tgz#925d2601d39ac485e091cf0da5c6e694dc3dcaff"
  integrity sha512-KigOCHcocU3XODJxsu8i/j8T9tzT4adHiecwORRQ0ZZFcp7ahwXuRU1m+yuO90C5ZUyGeGfocHDI14M3L3yDAQ==

resolve-alpn@^1.0.0:
  version "1.2.1"
  resolved "https://registry.npmmirror.com/resolve-alpn/-/resolve-alpn-1.2.1.tgz#b7adbdac3546aaaec20b45e7d8265927072726f9"
  integrity sha512-0a1F4l73/ZFZOakJnQ3FvkJ2+gSTQWz/r2KE5OdDY0TxPm5h4GkqkWWfM47T7HsbnOtcJVEF4epCVy6u7Q3K+g==

resolve-from@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/resolve-from/-/resolve-from-4.0.0.tgz#4abcd852ad32dd7baabfe9b40e00a36db5f392e6"
  integrity sha512-pb/MYmXstAkysRFx8piNI1tGFNQIFA3vkE3Gq4EuA1dF6gHp/+vgZqsCGJapvy8N3Q+4o7FwvquPJcnZ7RYy4g==

resolve-pathname@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/resolve-pathname/-/resolve-pathname-3.0.0.tgz#99d02224d3cf263689becbb393bc560313025dcd"
  integrity sha512-C7rARubxI8bXFNB/hqcp/4iUeIXJhJZvFPFPiSPRnhU5UPxzMFIl+2E6yY6c4k9giDJAhtV+enfA+G89N6Csng==

resolve@^1.1.6, resolve@^1.14.2, resolve@^1.3.2:
  version "1.22.1"
  resolved "https://registry.npmmirror.com/resolve/-/resolve-1.22.1.tgz#27cb2ebb53f91abb49470a928bba7558066ac177"
  integrity sha512-nBpuuYuY5jFsli/JIs1oldw6fOQCBioohqWZg/2hiaOybXOft4lonv85uDOKXdf8rhyK159cxU5cDcK/NKk8zw==
  dependencies:
    is-core-module "^2.9.0"
    path-parse "^1.0.7"
    supports-preserve-symlinks-flag "^1.0.0"

responselike@^2.0.0:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/responselike/-/responselike-2.0.1.tgz#9a0bc8fdc252f3fb1cca68b016591059ba1422bc"
  integrity sha512-4gl03wn3hj1HP3yzgdI7d3lCkF95F21Pz4BPGvKHinyQzALR5CapwC8yIi0Rh58DEMQ/SguC03wFj2k0M/mHhw==
  dependencies:
    lowercase-keys "^2.0.0"

retry@^0.13.1:
  version "0.13.1"
  resolved "https://registry.npmmirror.com/retry/-/retry-0.13.1.tgz#185b1587acf67919d63b357349e03537b2484658"
  integrity sha512-XQBQ3I8W1Cge0Seh+6gjj03LbmRFWuoszgK9ooCpwYIrhhoO80pfq4cUkU5DkknwfOfFteRwlZ56PYOGYyFWdg==

reusify@^1.0.4:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/reusify/-/reusify-1.0.4.tgz#90da382b1e126efc02146e90845a88db12925d76"
  integrity sha512-U9nH88a3fc/ekCF1l0/UP1IosiuIjyTh7hBvXVMHYgVcfGvt897Xguj2UOLDeI5BG2m7/uwyaLVT6fbtCwTyzw==

rimraf@^3.0.2:
  version "3.0.2"
  resolved "https://registry.npmmirror.com/rimraf/-/rimraf-3.0.2.tgz#f1a5402ba6220ad52cc1282bac1ae3aa49fd061a"
  integrity sha512-JZkJMZkAGFFPP2YqXZXPbMlMBgsxzE8ILs4lMIX/2o0L9UBw9O/Y3o6wFw/i9YLapcUJWwqbi3kdxIPdC62TIA==
  dependencies:
    glob "^7.1.3"

rtl-detect@^1.0.4:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/rtl-detect/-/rtl-detect-1.0.4.tgz#40ae0ea7302a150b96bc75af7d749607392ecac6"
  integrity sha512-EBR4I2VDSSYr7PkBmFy04uhycIpDKp+21p/jARYXlCSjQksTBQcJ0HFUPOO79EPPH5JS6VAhiIQbycf0O3JAxQ==

rtlcss@^3.3.0:
  version "3.5.0"
  resolved "https://registry.npmmirror.com/rtlcss/-/rtlcss-3.5.0.tgz#c9eb91269827a102bac7ae3115dd5d049de636c3"
  integrity sha512-wzgMaMFHQTnyi9YOwsx9LjOxYXJPzS8sYnFaKm6R5ysvTkwzHiB0vxnbHwchHQT65PTdBjDG21/kQBWI7q9O7A==
  dependencies:
    find-up "^5.0.0"
    picocolors "^1.0.0"
    postcss "^8.3.11"
    strip-json-comments "^3.1.1"

run-parallel@^1.1.9:
  version "1.2.0"
  resolved "https://registry.npmmirror.com/run-parallel/-/run-parallel-1.2.0.tgz#66d1368da7bdf921eb9d95bd1a9229e7f21a43ee"
  integrity sha512-5l4VyZR86LZ/lDxZTR6jqL8AFE2S0IFLMP26AbjsLVADxHdhB/c0GUsH+y39UfCi3dzz8OlQuPmnaJOMoDHQBA==
  dependencies:
    queue-microtask "^1.2.2"

rxjs@^7.5.4:
  version "7.5.7"
  resolved "https://registry.npmmirror.com/rxjs/-/rxjs-7.5.7.tgz#2ec0d57fdc89ece220d2e702730ae8f1e49def39"
  integrity sha512-z9MzKh/UcOqB3i20H6rtrlaE/CgjLOvheWK/9ILrbhROGTweAi1BaFsTT9FbwZi5Trr1qNRs+MXkhmR06awzQA==
  dependencies:
    tslib "^2.1.0"

safe-buffer@5.1.2, safe-buffer@~5.1.0, safe-buffer@~5.1.1:
  version "5.1.2"
  resolved "https://registry.npmmirror.com/safe-buffer/-/safe-buffer-5.1.2.tgz#991ec69d296e0313747d59bdfd2b745c35f8828d"
  integrity sha512-Gd2UZBJDkXlY7GbJxfsE8/nvKkUEU1G38c1siN6QP6a9PT9MmHB8GnpscSmMJSoF8LOIrt8ud/wPtojys4G6+g==

safe-buffer@5.2.1, safe-buffer@>=5.1.0, safe-buffer@^5.1.0, safe-buffer@~5.2.0:
  version "5.2.1"
  resolved "https://registry.npmmirror.com/safe-buffer/-/safe-buffer-5.2.1.tgz#1eaf9fa9bdb1fdd4ec75f58f9cdb4e6b7827eec6"
  integrity sha512-rp3So07KcdmmKbGvgaNxQSJr7bGVSVk5S9Eq1F+ppbRo70+YeaDxkw5Dd8NPN+GD6bjnYm2VuPuCXmpuYvmCXQ==

safe-regex-test@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/safe-regex-test/-/safe-regex-test-1.0.0.tgz#793b874d524eb3640d1873aad03596db2d4f2295"
  integrity sha512-JBUUzyOgEwXQY1NuPtvcj/qcBDbDmEvWufhlnXZIm75DEHp+afM1r1ujJpJsV/gSM4t59tpDyPi1sd6ZaPFfsA==
  dependencies:
    call-bind "^1.0.2"
    get-intrinsic "^1.1.3"
    is-regex "^1.1.4"

"safer-buffer@>= 2.1.2 < 3":
  version "2.1.2"
  resolved "https://registry.npmmirror.com/safer-buffer/-/safer-buffer-2.1.2.tgz#44fa161b0187b9549dd84bb91802f9bd8385cd6a"
  integrity sha512-YZo3K82SD7Riyi0E1EQPojLz7kpepnSQI9IyPbHHg1XXXevb5dJI7tpyN2ADxGcQbHG7vcyRHk0cbwqcQriUtg==

sax@^1.2.4, sax@~1.2.4:
  version "1.2.4"
  resolved "https://registry.npmmirror.com/sax/-/sax-1.2.4.tgz#2816234e2378bddc4e5354fab5caa895df7100d9"
  integrity sha512-NqVDv9TpANUjFm0N8uM5GxL36UgKi9/atZw+x7YFnQ8ckwFGKrl4xX4yWtrey3UJm5nP1kUbnYgLopqWNSRhWw==

scheduler@^0.20.2:
  version "0.20.2"
  resolved "https://registry.npmmirror.com/scheduler/-/scheduler-0.20.2.tgz#4baee39436e34aa93b4874bddcbf0fe8b8b50e91"
  integrity sha512-2eWfGgAqqWFGqtdMmcL5zCMK1U8KlXv8SQFGglL3CEtd0aDVDWgeF/YoCmvln55m5zSk3J/20hTaSBeSObsQDQ==
  dependencies:
    loose-envify "^1.1.0"
    object-assign "^4.1.1"

schema-utils@2.7.0:
  version "2.7.0"
  resolved "https://registry.npmmirror.com/schema-utils/-/schema-utils-2.7.0.tgz#17151f76d8eae67fbbf77960c33c676ad9f4efc7"
  integrity sha512-0ilKFI6QQF5nxDZLFn2dMjvc4hjg/Wkg7rHd3jK6/A4a1Hl9VFdQWvgB1UMGoU94pad1P/8N7fMcEnLnSiju8A==
  dependencies:
    "@types/json-schema" "^7.0.4"
    ajv "^6.12.2"
    ajv-keywords "^3.4.1"

schema-utils@^2.6.5:
  version "2.7.1"
  resolved "https://registry.npmmirror.com/schema-utils/-/schema-utils-2.7.1.tgz#1ca4f32d1b24c590c203b8e7a50bf0ea4cd394d7"
  integrity sha512-SHiNtMOUGWBQJwzISiVYKu82GiV4QYGePp3odlY1tuKO7gPtphAT5R/py0fA6xtbgLL/RvtJZnU9b8s0F1q0Xg==
  dependencies:
    "@types/json-schema" "^7.0.5"
    ajv "^6.12.4"
    ajv-keywords "^3.5.2"

schema-utils@^3.0.0, schema-utils@^3.1.0, schema-utils@^3.1.1:
  version "3.1.1"
  resolved "https://registry.npmmirror.com/schema-utils/-/schema-utils-3.1.1.tgz#bc74c4b6b6995c1d88f76a8b77bea7219e0c8281"
  integrity sha512-Y5PQxS4ITlC+EahLuXaY86TXfR7Dc5lw294alXOq86JAHCihAIZfqv8nNCWvaEJvaC51uN9hbLGeV0cFBdH+Fw==
  dependencies:
    "@types/json-schema" "^7.0.8"
    ajv "^6.12.5"
    ajv-keywords "^3.5.2"

schema-utils@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/schema-utils/-/schema-utils-4.0.0.tgz#60331e9e3ae78ec5d16353c467c34b3a0a1d3df7"
  integrity sha512-1edyXKgh6XnJsJSQ8mKWXnN/BVaIbFMLpouRUrXgVq7WYne5kw3MW7UPhO44uRXQSIpTSXoJbmrR2X0w9kUTyg==
  dependencies:
    "@types/json-schema" "^7.0.9"
    ajv "^8.8.0"
    ajv-formats "^2.1.1"
    ajv-keywords "^5.0.0"

section-matter@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/section-matter/-/section-matter-1.0.0.tgz#e9041953506780ec01d59f292a19c7b850b84167"
  integrity sha512-vfD3pmTzGpufjScBh50YHKzEu2lxBWhVEHsNGoEXmCmn2hKGfeNLYMzCJpe8cD7gqX7TJluOVpBkAequ6dgMmA==
  dependencies:
    extend-shallow "^2.0.1"
    kind-of "^6.0.0"

select-hose@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/select-hose/-/select-hose-2.0.0.tgz#625d8658f865af43ec962bfc376a37359a4994ca"
  integrity sha512-mEugaLK+YfkijB4fx0e6kImuJdCIt2LxCRcbEYPqRGCs4F2ogyfZU5IAZRdjCP8JPq2AtdNoC/Dux63d9Kiryg==

selfsigned@^2.1.1:
  version "2.1.1"
  resolved "https://registry.npmmirror.com/selfsigned/-/selfsigned-2.1.1.tgz#18a7613d714c0cd3385c48af0075abf3f266af61"
  integrity sha512-GSL3aowiF7wa/WtSFwnUrludWFoNhftq8bUkH9pkzjpN2XSPOAYEgg6e0sS9s0rZwgJzJiQRPU18A6clnoW5wQ==
  dependencies:
    node-forge "^1"

semver-diff@^3.1.1:
  version "3.1.1"
  resolved "https://registry.npmmirror.com/semver-diff/-/semver-diff-3.1.1.tgz#05f77ce59f325e00e2706afd67bb506ddb1ca32b"
  integrity sha512-GX0Ix/CJcHyB8c4ykpHGIAvLyOwOobtM/8d+TQkAd81/bEjgPHrfba41Vpesr7jX/t8Uh+R3EX9eAS5be+jQYg==
  dependencies:
    semver "^6.3.0"

semver@^5.4.1:
  version "5.7.2"
  resolved "https://registry.yarnpkg.com/semver/-/semver-5.7.2.tgz#48d55db737c3287cd4835e17fa13feace1c41ef8"
  integrity sha512-cBznnQ9KjJqU67B52RMC65CMarK2600WFnbkcaiwWq3xy/5haFJlshgnpjovMVJ+Hff49d8GEn0b87C5pDQ10g==

semver@^6.0.0, semver@^6.1.1, semver@^6.1.2, semver@^6.2.0, semver@^6.3.0:
  version "6.3.1"
  resolved "https://registry.yarnpkg.com/semver/-/semver-6.3.1.tgz#556d2ef8689146e46dcea4bfdd095f3434dffcb4"
  integrity sha512-BR7VvDCVHO+q2xBEWskxS6DJE1qRnb7DxzUrogb71CWoSficBxYsiAGd+Kl0mmq/MprG9yArRkyrQxTO6XjMzA==

semver@^7.3.2, semver@^7.3.4, semver@^7.3.5:
  version "7.5.4"
  resolved "https://registry.yarnpkg.com/semver/-/semver-7.5.4.tgz#483986ec4ed38e1c6c48c34894a9182dbff68a6e"
  integrity sha512-1bCSESV6Pv+i21Hvpxp3Dx+pSD8lIPt8uVjRrxAUt/nbswYc+tK6Y2btiULjd4+fnq15PX+nqQDC7Oft7WkwcA==
  dependencies:
    lru-cache "^6.0.0"

send@0.18.0:
  version "0.18.0"
  resolved "https://registry.npmmirror.com/send/-/send-0.18.0.tgz#670167cc654b05f5aa4a767f9113bb371bc706be"
  integrity sha512-qqWzuOjSFOuqPjFe4NOsMLafToQQwBSOEpS+FwEt3A2V3vKubTquT3vmLTQpFgMXp8AlFWFuP1qKaJZOtPpVXg==
  dependencies:
    debug "2.6.9"
    depd "2.0.0"
    destroy "1.2.0"
    encodeurl "~1.0.2"
    escape-html "~1.0.3"
    etag "~1.8.1"
    fresh "0.5.2"
    http-errors "2.0.0"
    mime "1.6.0"
    ms "2.1.3"
    on-finished "2.4.1"
    range-parser "~1.2.1"
    statuses "2.0.1"

serialize-javascript@^6.0.0:
  version "6.0.0"
  resolved "https://registry.npmmirror.com/serialize-javascript/-/serialize-javascript-6.0.0.tgz#efae5d88f45d7924141da8b5c3a7a7e663fefeb8"
  integrity sha512-Qr3TosvguFt8ePWqsvRfrKyQXIiW+nGbYpy8XK24NQHE83caxWt+mIymTT19DGFbNWNLfEwsrkSmN64lVWB9ag==
  dependencies:
    randombytes "^2.1.0"

serve-handler@^6.1.3:
  version "6.1.5"
  resolved "https://registry.npmmirror.com/serve-handler/-/serve-handler-6.1.5.tgz#a4a0964f5c55c7e37a02a633232b6f0d6f068375"
  integrity sha512-ijPFle6Hwe8zfmBxJdE+5fta53fdIY0lHISJvuikXB3VYFafRjMRpOffSPvCYsbKyBA7pvy9oYr/BT1O3EArlg==
  dependencies:
    bytes "3.0.0"
    content-disposition "0.5.2"
    fast-url-parser "1.1.3"
    mime-types "2.1.18"
    minimatch "3.1.2"
    path-is-inside "1.0.2"
    path-to-regexp "2.2.1"
    range-parser "1.2.0"

serve-index@^1.9.1:
  version "1.9.1"
  resolved "https://registry.npmmirror.com/serve-index/-/serve-index-1.9.1.tgz#d3768d69b1e7d82e5ce050fff5b453bea12a9239"
  integrity sha512-pXHfKNP4qujrtteMrSBb0rc8HJ9Ms/GrXwcUtUtD5s4ewDJI8bT3Cz2zTVRMKtri49pLx2e0Ya8ziP5Ya2pZZw==
  dependencies:
    accepts "~1.3.4"
    batch "0.6.1"
    debug "2.6.9"
    escape-html "~1.0.3"
    http-errors "~1.6.2"
    mime-types "~2.1.17"
    parseurl "~1.3.2"

serve-static@1.15.0:
  version "1.15.0"
  resolved "https://registry.npmmirror.com/serve-static/-/serve-static-1.15.0.tgz#faaef08cffe0a1a62f60cad0c4e513cff0ac9540"
  integrity sha512-XGuRDNjXUijsUL0vl6nSD7cwURuzEgglbOaFuZM9g3kwDXOWVTck0jLzjPzGD+TazWbboZYu52/9/XPdUgne9g==
  dependencies:
    encodeurl "~1.0.2"
    escape-html "~1.0.3"
    parseurl "~1.3.3"
    send "0.18.0"

setimmediate@^1.0.5:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/setimmediate/-/setimmediate-1.0.5.tgz#290cbb232e306942d7d7ea9b83732ab7856f8285"
  integrity sha512-MATJdZp8sLqDl/68LfQmbP8zKPLQNV6BIZoIgrscFDQ+RsvK/BxeDQOgyxKKoh0y/8h3BqVFnCqQ/gd+reiIXA==

setprototypeof@1.1.0:
  version "1.1.0"
  resolved "https://registry.npmmirror.com/setprototypeof/-/setprototypeof-1.1.0.tgz#d0bd85536887b6fe7c0d818cb962d9d91c54e656"
  integrity sha512-BvE/TwpZX4FXExxOxZyRGQQv651MSwmWKZGqvmPcRIjDqWub67kTKuIMx43cZZrS/cBBzwBcNDWoFxt2XEFIpQ==

setprototypeof@1.2.0:
  version "1.2.0"
  resolved "https://registry.npmmirror.com/setprototypeof/-/setprototypeof-1.2.0.tgz#66c9a24a73f9fc28cbe66b09fed3d33dcaf1b424"
  integrity sha512-E5LDX7Wrp85Kil5bhZv46j8jOeboKq5JMmYM3gVGdGH8xFpPWXUMsNrlODCrkoxMEeNi/XZIwuRvY4XNwYMJpw==

shallow-clone@^3.0.0:
  version "3.0.1"
  resolved "https://registry.npmmirror.com/shallow-clone/-/shallow-clone-3.0.1.tgz#8f2981ad92531f55035b01fb230769a40e02efa3"
  integrity sha512-/6KqX+GVUdqPuPPd2LxDDxzX6CAbjJehAAOKlNpqqUpAqPM6HeL8f+o3a+JsyGjn2lv0WY8UsTgUJjU9Ok55NA==
  dependencies:
    kind-of "^6.0.2"

shebang-command@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/shebang-command/-/shebang-command-2.0.0.tgz#ccd0af4f8835fbdc265b82461aaf0c36663f34ea"
  integrity sha512-kHxr2zZpYtdmrN1qDjrrX/Z1rR1kG8Dx+gkpK1G4eXmvXswmcE1hTWBWYUzlraYw1/yZp6YuDY77YtvbN0dmDA==
  dependencies:
    shebang-regex "^3.0.0"

shebang-regex@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/shebang-regex/-/shebang-regex-3.0.0.tgz#ae16f1644d873ecad843b0307b143362d4c42172"
  integrity sha512-7++dFhtcx3353uBaq8DDR4NuxBetBzC7ZQOhmTQInHEd6bSrXdiEyzCvG07Z44UYdLShWUyXt5M/yhz8ekcb1A==

shell-quote@^1.7.2:
  version "1.7.4"
  resolved "https://registry.npmmirror.com/shell-quote/-/shell-quote-1.7.4.tgz#33fe15dee71ab2a81fcbd3a52106c5cfb9fb75d8"
  integrity sha512-8o/QEhSSRb1a5i7TFR0iM4G16Z0vYB2OQVs4G3aAFXjn3T6yEx8AZxy1PgDF7I00LZHYA3WxaSYIf5e5sAX8Rw==

shelljs@^0.8.4, shelljs@^0.8.5:
  version "0.8.5"
  resolved "https://registry.npmmirror.com/shelljs/-/shelljs-0.8.5.tgz#de055408d8361bed66c669d2f000538ced8ee20c"
  integrity sha512-TiwcRcrkhHvbrZbnRcFYMLl30Dfov3HKqzp5tO5b4pt6G/SezKcYhmDg15zXVBswHmctSAQKznqNW2LO5tTDow==
  dependencies:
    glob "^7.0.0"
    interpret "^1.0.0"
    rechoir "^0.6.2"

side-channel@^1.0.4:
  version "1.0.4"
  resolved "https://registry.npmmirror.com/side-channel/-/side-channel-1.0.4.tgz#efce5c8fdc104ee751b25c58d4290011fa5ea2cf"
  integrity sha512-q5XPytqFEIKHkGdiMIrY10mvLRvnQh42/+GoBlFW3b2LXLE2xxJpZFdm94we0BaoV3RwJyGqg5wS7epxTv0Zvw==
  dependencies:
    call-bind "^1.0.0"
    get-intrinsic "^1.0.2"
    object-inspect "^1.9.0"

signal-exit@^3.0.2, signal-exit@^3.0.3:
  version "3.0.7"
  resolved "https://registry.npmmirror.com/signal-exit/-/signal-exit-3.0.7.tgz#a9a1767f8af84155114eaabd73f99273c8f59ad9"
  integrity sha512-wnD2ZE+l+SPC/uoS0vXeE9L1+0wuaMqKlfz9AMUo38JsyLSBWSFcHR1Rri62LZc12vLr1gb3jl7iwQhgwpAbGQ==

sirv@^1.0.7:
  version "1.0.19"
  resolved "https://registry.npmmirror.com/sirv/-/sirv-1.0.19.tgz#1d73979b38c7fe91fcba49c85280daa9c2363b49"
  integrity sha512-JuLThK3TnZG1TAKDwNIqNq6QA2afLOCcm+iE8D1Kj3GA40pSPsxQjjJl0J8X3tsR7T+CP1GavpzLwYkgVLWrZQ==
  dependencies:
    "@polka/url" "^1.0.0-next.20"
    mrmime "^1.0.0"
    totalist "^1.0.0"

sisteransi@^1.0.5:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/sisteransi/-/sisteransi-1.0.5.tgz#134d681297756437cc05ca01370d3a7a571075ed"
  integrity sha512-bLGGlR1QxBcynn2d5YmDX4MGjlZvy2MRBDRNHLJ8VI6l6+9FUiyTFNJ0IveOSP0bcXgVDPRcfGqA0pjaqUpfVg==

sitemap@^7.0.0:
  version "7.1.1"
  resolved "https://registry.npmmirror.com/sitemap/-/sitemap-7.1.1.tgz#eeed9ad6d95499161a3eadc60f8c6dce4bea2bef"
  integrity sha512-mK3aFtjz4VdJN0igpIJrinf3EO8U8mxOPsTBzSsy06UtjZQJ3YY3o3Xa7zSc5nMqcMrRwlChHZ18Kxg0caiPBg==
  dependencies:
    "@types/node" "^17.0.5"
    "@types/sax" "^1.2.1"
    arg "^5.0.0"
    sax "^1.2.4"

slash@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/slash/-/slash-3.0.0.tgz#6539be870c165adbd5240220dbe361f1bc4d4634"
  integrity sha512-g9Q1haeby36OSStwb4ntCGGGaKsaVSjQ68fBxoQcutl5fS1vuY18H3wSt3jFyFtrkx+Kz0V1G85A4MyAdDMi2Q==

sockjs@^0.3.24:
  version "0.3.24"
  resolved "https://registry.npmmirror.com/sockjs/-/sockjs-0.3.24.tgz#c9bc8995f33a111bea0395ec30aa3206bdb5ccce"
  integrity sha512-GJgLTZ7vYb/JtPSSZ10hsOYIvEYsjbNU+zPdIHcUaWVNUEPivzxku31865sSSud0Da0W4lEeOPlmw93zLQchuQ==
  dependencies:
    faye-websocket "^0.11.3"
    uuid "^8.3.2"
    websocket-driver "^0.7.4"

sort-css-media-queries@2.1.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/sort-css-media-queries/-/sort-css-media-queries-2.1.0.tgz#7c85e06f79826baabb232f5560e9745d7a78c4ce"
  integrity sha512-IeWvo8NkNiY2vVYdPa27MCQiR0MN0M80johAYFVxWWXQ44KU84WNxjslwBHmc/7ZL2ccwkM7/e6S5aiKZXm7jA==

source-list-map@^2.0.0:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/source-list-map/-/source-list-map-2.0.1.tgz#3993bd873bfc48479cca9ea3a547835c7c154b34"
  integrity sha512-qnQ7gVMxGNxsiL4lEuJwe/To8UnK7fAnmbGEEH8RpLouuKbeEm0lhbQVFIrNSuB+G7tVrAlVsZgETT5nljf+Iw==

source-map-js@^1.0.2:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/source-map-js/-/source-map-js-1.0.2.tgz#adbc361d9c62df380125e7f161f71c826f1e490c"
  integrity sha512-R0XvVJ9WusLiqTCEiGCmICCMplcCkIwwR11mOSD9CR5u+IXYdiseeEuXCVAjS54zqwkLcPNnmU4OeJ6tUrWhDw==

source-map-support@~0.5.20:
  version "0.5.21"
  resolved "https://registry.npmmirror.com/source-map-support/-/source-map-support-0.5.21.tgz#04fe7c7f9e1ed2d662233c28cb2b35b9f63f6e4f"
  integrity sha512-uBHU3L3czsIyYXKX88fdrGovxdSCoTGDRZ6SYXtSRxLZUzHg5P/66Ht6uoUlHu9EZod+inXhKo3qQgwXUT/y1w==
  dependencies:
    buffer-from "^1.0.0"
    source-map "^0.6.0"

source-map@^0.5.0:
  version "0.5.7"
  resolved "https://registry.npmmirror.com/source-map/-/source-map-0.5.7.tgz#8a039d2d1021d22d1ea14c80d8ea468ba2ef3fcc"
  integrity sha512-LbrmJOMUSdEVxIKvdcJzQC+nQhe8FUZQTXQy6+I75skNgn3OoQ0DZA8YnFa7gp8tqtL3KPf1kmo0R5DoApeSGQ==

source-map@^0.6.0, source-map@^0.6.1, source-map@~0.6.0, source-map@~0.6.1:
  version "0.6.1"
  resolved "https://registry.npmmirror.com/source-map/-/source-map-0.6.1.tgz#74722af32e9614e9c287a8d0bbde48b5e2f1a263"
  integrity sha512-UjgapumWlbMhkBgzT7Ykc5YXUT46F0iKu8SGXq0bcwP5dz/h0Plj6enJqjz1Zbq2l5WaqYnrVbwWOWMyF3F47g==

sourcemap-codec@^1.4.8:
  version "1.4.8"
  resolved "https://registry.npmmirror.com/sourcemap-codec/-/sourcemap-codec-1.4.8.tgz#ea804bd94857402e6992d05a38ef1ae35a9ab4c4"
  integrity sha512-9NykojV5Uih4lgo5So5dtw+f0JgJX30KCNI8gwhz2J9A15wD0Ml6tjHKwf6fTSa6fAdVBdZeNOs9eJ71qCk8vA==

space-separated-tokens@^1.0.0:
  version "1.1.5"
  resolved "https://registry.npmmirror.com/space-separated-tokens/-/space-separated-tokens-1.1.5.tgz#85f32c3d10d9682007e917414ddc5c26d1aa6899"
  integrity sha512-q/JSVd1Lptzhf5bkYm4ob4iWPjx0KiRe3sRFBNrVqbJkFaBm5vbbowy1mymoPNLRa52+oadOhJ+K49wsSeSjTA==

spdy-transport@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/spdy-transport/-/spdy-transport-3.0.0.tgz#00d4863a6400ad75df93361a1608605e5dcdcf31"
  integrity sha512-hsLVFE5SjA6TCisWeJXFKniGGOpBgMLmerfO2aCyCU5s7nJ/rpAepqmFifv/GCbSbueEeAJJnmSQ2rKC/g8Fcw==
  dependencies:
    debug "^4.1.0"
    detect-node "^2.0.4"
    hpack.js "^2.1.6"
    obuf "^1.1.2"
    readable-stream "^3.0.6"
    wbuf "^1.7.3"

spdy@^4.0.2:
  version "4.0.2"
  resolved "https://registry.npmmirror.com/spdy/-/spdy-4.0.2.tgz#b74f466203a3eda452c02492b91fb9e84a27677b"
  integrity sha512-r46gZQZQV+Kl9oItvl1JZZqJKGr+oEkB08A6BzkiR7593/7IbtuncXHd2YoYeTsG4157ZssMu9KYvUHLcjcDoA==
  dependencies:
    debug "^4.1.0"
    handle-thing "^2.0.0"
    http-deceiver "^1.2.7"
    select-hose "^2.0.0"
    spdy-transport "^3.0.0"

sprintf-js@~1.0.2:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/sprintf-js/-/sprintf-js-1.0.3.tgz#04e6926f662895354f3dd015203633b857297e2c"
  integrity sha512-D9cPgkvLlV3t3IzL0D0YLvGA9Ahk4PcvVwUbN0dSGr1aP0Nrt4AEnTUbuGvquEC0mA64Gqt1fzirlRs5ibXx8g==

stable@^0.1.8:
  version "0.1.8"
  resolved "https://registry.npmmirror.com/stable/-/stable-0.1.8.tgz#836eb3c8382fe2936feaf544631017ce7d47a3cf"
  integrity sha512-ji9qxRnOVfcuLDySj9qzhGSEFVobyt1kIOSkj1qZzYLzq7Tos/oUUWvotUPQLlrsidqsK6tBH89Bc9kL5zHA6w==

state-toggle@^1.0.0:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/state-toggle/-/state-toggle-1.0.3.tgz#e123b16a88e143139b09c6852221bc9815917dfe"
  integrity sha512-d/5Z4/2iiCnHw6Xzghyhb+GcmF89bxwgXG60wjIiZaxnymbyOmI8Hk4VqHXiVVp6u2ysaskFfXg3ekCj4WNftQ==

statuses@2.0.1:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/statuses/-/statuses-2.0.1.tgz#55cb000ccf1d48728bd23c685a063998cf1a1b63"
  integrity sha512-RwNA9Z/7PrK06rYLIzFMlaF+l73iwpzsqRIFgbMLbTcLD6cOao82TaWefPXQvB2fOC4AjuYSEndS7N/mTCbkdQ==

"statuses@>= 1.4.0 < 2":
  version "1.5.0"
  resolved "https://registry.npmmirror.com/statuses/-/statuses-1.5.0.tgz#161c7dac177659fd9811f43771fa99381478628c"
  integrity sha512-OpZ3zP+jT1PI7I8nemJX4AKmAX070ZkYPVWV/AaKTJl+tXCTGyVdC1a4SL8RUQYEwk/f34ZX8UTykN68FwrqAA==

std-env@^2.2.1:
  version "2.3.1"
  resolved "https://registry.npmmirror.com/std-env/-/std-env-2.3.1.tgz#d42271908819c243f8defc77a140fc1fcee336a1"
  integrity sha512-eOsoKTWnr6C8aWrqJJ2KAReXoa7Vn5Ywyw6uCXgA/xDhxPoaIsBa5aNJmISY04dLwXPBnDHW4diGM7Sn5K4R/g==
  dependencies:
    ci-info "^3.1.1"

std-env@^3.0.1:
  version "3.3.0"
  resolved "https://registry.npmmirror.com/std-env/-/std-env-3.3.0.tgz#86b5b5d416c5744b3fdeac6893c2b98196fc1a55"
  integrity sha512-cNNS+VYsXIs5gI6gJipO4qZ8YYT274JHvNnQ1/R/x8Q8mdP0qj0zoMchRXmBNPqp/0eOEhX+3g7g6Fgb7meLIQ==

string-width@^4.0.0, string-width@^4.1.0, string-width@^4.2.2:
  version "4.2.3"
  resolved "https://registry.npmmirror.com/string-width/-/string-width-4.2.3.tgz#269c7117d27b05ad2e536830a8ec895ef9c6d010"
  integrity sha512-wKyQRQpjJ0sIp62ErSZdGsjMJWsap5oRNihHhu6G7JVO/9jIB6UyevL+tXuOqrng8j/cxKTWyWUwvSTriiZz/g==
  dependencies:
    emoji-regex "^8.0.0"
    is-fullwidth-code-point "^3.0.0"
    strip-ansi "^6.0.1"

string.prototype.trimend@^1.0.5:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/string.prototype.trimend/-/string.prototype.trimend-1.0.5.tgz#914a65baaab25fbdd4ee291ca7dde57e869cb8d0"
  integrity sha512-I7RGvmjV4pJ7O3kdf+LXFpVfdNOxtCW/2C8f6jNiW4+PQchwxkCDzlk1/7p+Wl4bqFIZeF47qAHXLuHHWKAxog==
  dependencies:
    call-bind "^1.0.2"
    define-properties "^1.1.4"
    es-abstract "^1.19.5"

string.prototype.trimstart@^1.0.5:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/string.prototype.trimstart/-/string.prototype.trimstart-1.0.5.tgz#5466d93ba58cfa2134839f81d7f42437e8c01fef"
  integrity sha512-THx16TJCGlsN0o6dl2o6ncWUsdgnLRSA23rRE5pyGBw/mLr3Ej/R2LaqCtgP8VNMGZsvMWnf9ooZPyY2bHvUFg==
  dependencies:
    call-bind "^1.0.2"
    define-properties "^1.1.4"
    es-abstract "^1.19.5"

string_decoder@^1.1.1:
  version "1.3.0"
  resolved "https://registry.npmmirror.com/string_decoder/-/string_decoder-1.3.0.tgz#42f114594a46cf1a8e30b0a84f56c78c3edac21e"
  integrity sha512-hkRX8U1WjJFd8LsDJ2yQ/wWWxaopEsABU1XfkM8A+j0+85JAGppt16cr1Whg6KIbb4okU6Mql6BOj+uup/wKeA==
  dependencies:
    safe-buffer "~5.2.0"

string_decoder@~1.1.1:
  version "1.1.1"
  resolved "https://registry.npmmirror.com/string_decoder/-/string_decoder-1.1.1.tgz#9cf1611ba62685d7030ae9e4ba34149c3af03fc8"
  integrity sha512-n/ShnvDi6FHbbVfviro+WojiFzv+s8MPMHBczVePfUpDJLwoLT0ht1l4YwBCbi8pJAveEEdnkHyPyTP/mzRfwg==
  dependencies:
    safe-buffer "~5.1.0"

stringify-object@^3.3.0:
  version "3.3.0"
  resolved "https://registry.npmmirror.com/stringify-object/-/stringify-object-3.3.0.tgz#703065aefca19300d3ce88af4f5b3956d7556629"
  integrity sha512-rHqiFh1elqCQ9WPLIC8I0Q/g/wj5J1eMkyoiD6eoQApWHP0FtlK7rqnhmabL5VUY9JQCcqwwvlOaSuutekgyrw==
  dependencies:
    get-own-enumerable-property-symbols "^3.0.0"
    is-obj "^1.0.1"
    is-regexp "^1.0.0"

strip-ansi@^6.0.0, strip-ansi@^6.0.1:
  version "6.0.1"
  resolved "https://registry.npmmirror.com/strip-ansi/-/strip-ansi-6.0.1.tgz#9e26c63d30f53443e9489495b2105d37b67a85d9"
  integrity sha512-Y38VPSHcqkFrCpFnQ9vuSXmquuv5oXOKpGeT6aGrr3o3Gc9AlVa6JBfUSOCnbxGGZF+/0ooI7KrPuUSztUdU5A==
  dependencies:
    ansi-regex "^5.0.1"

strip-bom-string@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/strip-bom-string/-/strip-bom-string-1.0.0.tgz#e5211e9224369fbb81d633a2f00044dc8cedad92"
  integrity sha512-uCC2VHvQRYu+lMh4My/sFNmF2klFymLX1wHJeXnbEJERpV/ZsVuonzerjfrGpIGF7LBVa1O7i9kjiWvJiFck8g==

strip-final-newline@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/strip-final-newline/-/strip-final-newline-2.0.0.tgz#89b852fb2fcbe936f6f4b3187afb0a12c1ab58ad"
  integrity sha512-BrpvfNAE3dcvq7ll3xVumzjKjZQ5tI1sEUIKr3Uoks0XUl45St3FlatVqef9prk4jRDzhW6WZg+3bk93y6pLjA==

strip-json-comments@^3.1.1:
  version "3.1.1"
  resolved "https://registry.npmmirror.com/strip-json-comments/-/strip-json-comments-3.1.1.tgz#31f1281b3832630434831c310c01cccda8cbe006"
  integrity sha512-6fPc+R4ihwqP6N/aIv2f1gMH8lOVtWQHoqC4yK6oSDVVocumAsfCqjkXnqiYMhmMwS/mEHLp7Vehlt3ql6lEig==

strip-json-comments@~2.0.1:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/strip-json-comments/-/strip-json-comments-2.0.1.tgz#3c531942e908c2697c0ec344858c286c7ca0a60a"
  integrity sha512-4gB8na07fecVVkOI6Rs4e7T6NOTki5EmL7TUduTs6bu3EdnSycntVJ4re8kgZA+wx9IueI2Y11bfbgwtzuE0KQ==

style-to-object@0.3.0, style-to-object@^0.3.0:
  version "0.3.0"
  resolved "https://registry.npmmirror.com/style-to-object/-/style-to-object-0.3.0.tgz#b1b790d205991cc783801967214979ee19a76e46"
  integrity sha512-CzFnRRXhzWIdItT3OmF8SQfWyahHhjq3HwcMNCNLn+N7klOOqPjMeG/4JSu77D7ypZdGvSzvkrbyeTMizz2VrA==
  dependencies:
    inline-style-parser "0.1.1"

stylehacks@^5.1.1:
  version "5.1.1"
  resolved "https://registry.npmmirror.com/stylehacks/-/stylehacks-5.1.1.tgz#7934a34eb59d7152149fa69d6e9e56f2fc34bcc9"
  integrity sha512-sBpcd5Hx7G6seo7b1LkpttvTz7ikD0LlH5RmdcBNb6fFR0Fl7LQwHDFr300q4cwUqi+IYrFGmsIHieMBfnN/Bw==
  dependencies:
    browserslist "^4.21.4"
    postcss-selector-parser "^6.0.4"

supports-color@^5.3.0:
  version "5.5.0"
  resolved "https://registry.npmmirror.com/supports-color/-/supports-color-5.5.0.tgz#e2e69a44ac8772f78a1ec0b35b689df6530efc8f"
  integrity sha512-QjVjwdXIt408MIiAqCX4oUKsgU2EqAGzs2Ppkm4aQYbjm+ZEWEcW4SfFNTr4uMNZma0ey4f5lgLrkB0aX0QMow==
  dependencies:
    has-flag "^3.0.0"

supports-color@^7.1.0:
  version "7.2.0"
  resolved "https://registry.npmmirror.com/supports-color/-/supports-color-7.2.0.tgz#1b7dcdcb32b8138801b3e478ba6a51caa89648da"
  integrity sha512-qpCAvRl9stuOHveKsn7HncJRvv501qIacKzQlO/+Lwxc9+0q2wLyv4Dfvt80/DPn2pqOBsJdDiogXGR9+OvwRw==
  dependencies:
    has-flag "^4.0.0"

supports-color@^8.0.0:
  version "8.1.1"
  resolved "https://registry.npmmirror.com/supports-color/-/supports-color-8.1.1.tgz#cd6fc17e28500cff56c1b86c0a7fd4a54a73005c"
  integrity sha512-MpUEN2OodtUzxvKQl72cUF7RQ5EiHsGvSsVG0ia9c5RbWGL2CI4C7EpPS8UTBIplnlzZiNuV56w+FuNxy3ty2Q==
  dependencies:
    has-flag "^4.0.0"

supports-preserve-symlinks-flag@^1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/supports-preserve-symlinks-flag/-/supports-preserve-symlinks-flag-1.0.0.tgz#6eda4bd344a3c94aea376d4cc31bc77311039e09"
  integrity sha512-ot0WnXS9fgdkgIcePe6RHNk1WA8+muPa6cSjeR3V8K27q9BB1rTE3R1p7Hv0z1ZyAc8s6Vvv8DIyWf681MAt0w==

svg-parser@^2.0.2, svg-parser@^2.0.4:
  version "2.0.4"
  resolved "https://registry.npmmirror.com/svg-parser/-/svg-parser-2.0.4.tgz#fdc2e29e13951736140b76cb122c8ee6630eb6b5"
  integrity sha512-e4hG1hRwoOdRb37cIMSgzNsxyzKfayW6VOflrwvR+/bzrkyxY/31WkbgnQpgtrNp1SdpJvpUAGTa/ZoiPNDuRQ==

svgo@^1.2.2:
  version "1.3.2"
  resolved "https://registry.npmmirror.com/svgo/-/svgo-1.3.2.tgz#b6dc511c063346c9e415b81e43401145b96d4167"
  integrity sha512-yhy/sQYxR5BkC98CY7o31VGsg014AKLEPxdfhora76l36hD9Rdy5NZA/Ocn6yayNPgSamYdtX2rFJdcv07AYVw==
  dependencies:
    chalk "^2.4.1"
    coa "^2.0.2"
    css-select "^2.0.0"
    css-select-base-adapter "^0.1.1"
    css-tree "1.0.0-alpha.37"
    csso "^4.0.2"
    js-yaml "^3.13.1"
    mkdirp "~0.5.1"
    object.values "^1.1.0"
    sax "~1.2.4"
    stable "^0.1.8"
    unquote "~1.1.1"
    util.promisify "~1.0.0"

svgo@^2.7.0, svgo@^2.8.0:
  version "2.8.0"
  resolved "https://registry.npmmirror.com/svgo/-/svgo-2.8.0.tgz#4ff80cce6710dc2795f0c7c74101e6764cfccd24"
  integrity sha512-+N/Q9kV1+F+UeWYoSiULYo4xYSDQlTgb+ayMobAXPwMnLvop7oxKMo9OzIrX5x3eS4L4f2UHhc9axXwY8DpChg==
  dependencies:
    "@trysound/sax" "0.2.0"
    commander "^7.2.0"
    css-select "^4.1.3"
    css-tree "^1.1.3"
    csso "^4.2.0"
    picocolors "^1.0.0"
    stable "^0.1.8"

tapable@^1.0.0:
  version "1.1.3"
  resolved "https://registry.npmmirror.com/tapable/-/tapable-1.1.3.tgz#a1fccc06b58db61fd7a45da2da44f5f3a3e67ba2"
  integrity sha512-4WK/bYZmj8xLr+HUCODHGF1ZFzsYffasLUgEiMBY4fgtltdO6B4WJtlSbPaDTLpYTcGVwM2qLnFTICEcNxs3kA==

tapable@^2.0.0, tapable@^2.1.1, tapable@^2.2.0:
  version "2.2.1"
  resolved "https://registry.npmmirror.com/tapable/-/tapable-2.2.1.tgz#1967a73ef4060a82f12ab96af86d52fdb76eeca0"
  integrity sha512-GNzQvQTOIP6RyTfE2Qxb8ZVlNmw0n88vp1szwWRimP02mnTsx3Wtn5qRdqY9w2XduFNUgvOwhNnQsjwCp+kqaQ==

terser-webpack-plugin@^5.1.3, terser-webpack-plugin@^5.2.4:
  version "5.3.6"
  resolved "https://registry.npmmirror.com/terser-webpack-plugin/-/terser-webpack-plugin-5.3.6.tgz#5590aec31aa3c6f771ce1b1acca60639eab3195c"
  integrity sha512-kfLFk+PoLUQIbLmB1+PZDMRSZS99Mp+/MHqDNmMA6tOItzRt+Npe3E+fsMs5mfcM0wCtrrdU387UnV+vnSffXQ==
  dependencies:
    "@jridgewell/trace-mapping" "^0.3.14"
    jest-worker "^27.4.5"
    schema-utils "^3.1.1"
    serialize-javascript "^6.0.0"
    terser "^5.14.1"

terser@^5.10.0, terser@^5.14.1:
  version "5.15.1"
  resolved "https://registry.npmmirror.com/terser/-/terser-5.15.1.tgz#8561af6e0fd6d839669c73b92bdd5777d870ed6c"
  integrity sha512-K1faMUvpm/FBxjBXud0LWVAGxmvoPbZbfTCYbSgaaYQaIXI3/TdI7a7ZGA73Zrou6Q8Zmz3oeUTsp/dj+ag2Xw==
  dependencies:
    "@jridgewell/source-map" "^0.3.2"
    acorn "^8.5.0"
    commander "^2.20.0"
    source-map-support "~0.5.20"

text-table@^0.2.0:
  version "0.2.0"
  resolved "https://registry.npmmirror.com/text-table/-/text-table-0.2.0.tgz#7f5ee823ae805207c00af2df4a84ec3fcfa570b4"
  integrity sha512-N+8UisAXDGk8PFXP4HAzVR9nbfmVJ3zYLAWiTIoqC5v5isinhr+r5uaO8+7r3BMfuNIufIsA7RdpVgacC2cSpw==

thunky@^1.0.2:
  version "1.1.0"
  resolved "https://registry.npmmirror.com/thunky/-/thunky-1.1.0.tgz#5abaf714a9405db0504732bbccd2cedd9ef9537d"
  integrity sha512-eHY7nBftgThBqOyHGVN+l8gF0BucP09fMo0oO/Lb0w1OF80dJv+lDVpXG60WMQvkcxAkNybKsrEIE3ZtKGmPrA==

tiny-invariant@^1.0.2:
  version "1.3.1"
  resolved "https://registry.npmmirror.com/tiny-invariant/-/tiny-invariant-1.3.1.tgz#8560808c916ef02ecfd55e66090df23a4b7aa642"
  integrity sha512-AD5ih2NlSssTCwsMznbvwMZpJ1cbhkGd2uueNxzv2jDlEeZdU04JQfRnggJQ8DrcVBGjAsCKwFBbDlVNtEMlzw==

tiny-warning@^1.0.0:
  version "1.0.3"
  resolved "https://registry.npmmirror.com/tiny-warning/-/tiny-warning-1.0.3.tgz#94a30db453df4c643d0fd566060d60a875d84754"
  integrity sha512-lBN9zLN/oAf68o3zNXYrdCt1kP8WsiGW8Oo2ka41b2IM5JL/S1CTyX1rW0mb/zSuJun0ZUrDxx4sqvYS2FWzPA==

to-fast-properties@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/to-fast-properties/-/to-fast-properties-2.0.0.tgz#dc5e698cbd079265bc73e0377681a4e4e83f616e"
  integrity sha512-/OaKK0xYrs3DmxRYqL/yDc+FxFUVYhDlXMhRmv3z915w2HF1tnN1omB354j8VUGO/hbRzyD6Y3sA7v7GS/ceog==

to-regex-range@^5.0.1:
  version "5.0.1"
  resolved "https://registry.npmmirror.com/to-regex-range/-/to-regex-range-5.0.1.tgz#1648c44aae7c8d988a326018ed72f5b4dd0392e4"
  integrity sha512-65P7iz6X5yEr1cwcgvQxbbIw7Uk3gOy5dIdtZ4rDveLqhrdJP+Li/Hx6tyK0NEb+2GCyneCMJiGqrADCSNk8sQ==
  dependencies:
    is-number "^7.0.0"

toidentifier@1.0.1:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/toidentifier/-/toidentifier-1.0.1.tgz#3be34321a88a820ed1bd80dfaa33e479fbb8dd35"
  integrity sha512-o5sSPKEkg/DIQNmH43V0/uerLrpzVedkUh8tGNvaeXpfpuwjKenlSox/2O/BTlZUtEe+JG7s5YhEz608PlAHRA==

totalist@^1.0.0:
  version "1.1.0"
  resolved "https://registry.npmmirror.com/totalist/-/totalist-1.1.0.tgz#a4d65a3e546517701e3e5c37a47a70ac97fe56df"
  integrity sha512-gduQwd1rOdDMGxFG1gEvhV88Oirdo2p+KjoYFU7k2g+i7n6AFFbDQ5kMPUsW0pNbfQsB/cwXvT1i4Bue0s9g5g==

tr46@~0.0.3:
  version "0.0.3"
  resolved "https://registry.npmmirror.com/tr46/-/tr46-0.0.3.tgz#8184fd347dac9cdc185992f3a6622e14b9d9ab6a"
  integrity sha512-N3WMsuqV66lT30CrXNbEjx4GEwlow3v6rr4mCcv6prnfwhS01rkgyFdjPNBYd9br7LpXV1+Emh01fHnq2Gdgrw==

trim-trailing-lines@^1.0.0:
  version "1.1.4"
  resolved "https://registry.npmmirror.com/trim-trailing-lines/-/trim-trailing-lines-1.1.4.tgz#bd4abbec7cc880462f10b2c8b5ce1d8d1ec7c2c0"
  integrity sha512-rjUWSqnfTNrjbB9NQWfPMH/xRK1deHeGsHoVfpxJ++XeYXE0d6B1En37AHfw3jtfTU7dzMzZL2jjpe8Qb5gLIQ==

trim@0.0.1, trim@0.0.3, trim@^0.0.3:
  version "0.0.3"
  resolved "https://registry.npmmirror.com/trim/-/trim-0.0.3.tgz#05243a47a3a4113e6b49367880a9cca59697a20b"
  integrity sha512-h82ywcYhHK7veeelXrCScdH7HkWfbIT1D/CgYO+nmDarz3SGNssVBMws6jU16Ga60AJCRAvPV6w6RLuNerQqjg==

trough@^1.0.0:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/trough/-/trough-1.0.5.tgz#b8b639cefad7d0bb2abd37d433ff8293efa5f406"
  integrity sha512-rvuRbTarPXmMb79SmzEp8aqXNKcK+y0XaB298IXueQ8I2PsrATcPBCSPyK/dDNa2iWOhKlfNnOjdAOTBU/nkFA==

tslib@^2.0.3, tslib@^2.1.0, tslib@^2.2.0, tslib@^2.3.1, tslib@^2.4.0:
  version "2.4.1"
  resolved "https://registry.npmmirror.com/tslib/-/tslib-2.4.1.tgz#0d0bfbaac2880b91e22df0768e55be9753a5b17e"
  integrity sha512-tGyy4dAjRIEwI7BzsB0lynWgOpfqjUdq91XXAlIWD2OwKBH7oCl/GZG/HT4BOHrTlPMOASlMQ7veyTqpmRcrNA==

type-fest@^0.20.2:
  version "0.20.2"
  resolved "https://registry.npmmirror.com/type-fest/-/type-fest-0.20.2.tgz#1bf207f4b28f91583666cb5fbd327887301cd5f4"
  integrity sha512-Ne+eE4r0/iWnpAxD852z3A+N0Bt5RN//NjJwRd2VFHEmrywxf5vsZlh4R6lixl6B+wz/8d+maTSAkN1FIkI3LQ==

type-is@~1.6.18:
  version "1.6.18"
  resolved "https://registry.npmmirror.com/type-is/-/type-is-1.6.18.tgz#4e552cd05df09467dcbc4ef739de89f2cf37c131"
  integrity sha512-TkRKr9sUTxEH8MdfuCSP7VizJyzRNMjj2J2do2Jr3Kym598JVdEksuzPQCnlFPW4ky9Q+iA+ma9BGm06XQBy8g==
  dependencies:
    media-typer "0.3.0"
    mime-types "~2.1.24"

typedarray-to-buffer@^3.1.5:
  version "3.1.5"
  resolved "https://registry.npmmirror.com/typedarray-to-buffer/-/typedarray-to-buffer-3.1.5.tgz#a97ee7a9ff42691b9f783ff1bc5112fe3fca9080"
  integrity sha512-zdu8XMNEDepKKR+XYOXAVPtWui0ly0NtohUscw+UmaHiAWT8hrV1rr//H6V+0DvJ3OQ19S979M0laLfX8rm82Q==
  dependencies:
    is-typedarray "^1.0.0"

ua-parser-js@^0.7.30:
  version "0.7.33"
  resolved "https://registry.yarnpkg.com/ua-parser-js/-/ua-parser-js-0.7.33.tgz#1d04acb4ccef9293df6f70f2c3d22f3030d8b532"
  integrity sha512-s8ax/CeZdK9R/56Sui0WM6y9OFREJarMRHqLB2EwkovemBxNQ+Bqu8GAsUnVcXKgphb++ghr/B2BZx4mahujPw==

unbox-primitive@^1.0.2:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/unbox-primitive/-/unbox-primitive-1.0.2.tgz#29032021057d5e6cdbd08c5129c226dff8ed6f9e"
  integrity sha512-61pPlCD9h51VoreyJ0BReideM3MDKMKnh6+V9L08331ipq6Q8OFXZYiqP6n/tbHx4s5I9uRhcye6BrbkizkBDw==
  dependencies:
    call-bind "^1.0.2"
    has-bigints "^1.0.2"
    has-symbols "^1.0.3"
    which-boxed-primitive "^1.0.2"

unherit@^1.0.4:
  version "1.1.3"
  resolved "https://registry.npmmirror.com/unherit/-/unherit-1.1.3.tgz#6c9b503f2b41b262330c80e91c8614abdaa69c22"
  integrity sha512-Ft16BJcnapDKp0+J/rqFC3Rrk6Y/Ng4nzsC028k2jdDII/rdZ7Wd3pPT/6+vIIxRagwRc9K0IUX0Ra4fKvw+WQ==
  dependencies:
    inherits "^2.0.0"
    xtend "^4.0.0"

unicode-canonical-property-names-ecmascript@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/unicode-canonical-property-names-ecmascript/-/unicode-canonical-property-names-ecmascript-2.0.0.tgz#301acdc525631670d39f6146e0e77ff6bbdebddc"
  integrity sha512-yY5PpDlfVIU5+y/BSCxAJRBIS1Zc2dDG3Ujq+sR0U+JjUevW2JhocOF+soROYDSaAezOzOKuyyixhD6mBknSmQ==

unicode-match-property-ecmascript@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/unicode-match-property-ecmascript/-/unicode-match-property-ecmascript-2.0.0.tgz#54fd16e0ecb167cf04cf1f756bdcc92eba7976c3"
  integrity sha512-5kaZCrbp5mmbz5ulBkDkbY0SsPOjKqVS35VpL9ulMPfSl0J0Xsm+9Evphv9CoIZFwre7aJoa94AY6seMKGVN5Q==
  dependencies:
    unicode-canonical-property-names-ecmascript "^2.0.0"
    unicode-property-aliases-ecmascript "^2.0.0"

unicode-match-property-value-ecmascript@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/unicode-match-property-value-ecmascript/-/unicode-match-property-value-ecmascript-2.0.0.tgz#1a01aa57247c14c568b89775a54938788189a714"
  integrity sha512-7Yhkc0Ye+t4PNYzOGKedDhXbYIBe1XEQYQxOPyhcXNMJ0WCABqqj6ckydd6pWRZTHV4GuCPKdBAUiMc60tsKVw==

unicode-property-aliases-ecmascript@^2.0.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/unicode-property-aliases-ecmascript/-/unicode-property-aliases-ecmascript-2.1.0.tgz#43d41e3be698bd493ef911077c9b131f827e8ccd"
  integrity sha512-6t3foTQI9qne+OZoVQB/8x8rk2k1eVy1gRXhV3oFQ5T6R1dqQ1xtin3XqSlx3+ATBkliTaR/hHyJBm+LVPNM8w==

unified@9.2.0:
  version "9.2.0"
  resolved "https://registry.npmmirror.com/unified/-/unified-9.2.0.tgz#67a62c627c40589edebbf60f53edfd4d822027f8"
  integrity sha512-vx2Z0vY+a3YoTj8+pttM3tiJHCwY5UFbYdiWrwBEbHmK8pvsPj2rtAX2BFfgXen8T39CJWblWRDT4L5WGXtDdg==
  dependencies:
    bail "^1.0.0"
    extend "^3.0.0"
    is-buffer "^2.0.0"
    is-plain-obj "^2.0.0"
    trough "^1.0.0"
    vfile "^4.0.0"

unified@^8.4.2:
  version "8.4.2"
  resolved "https://registry.npmmirror.com/unified/-/unified-8.4.2.tgz#13ad58b4a437faa2751a4a4c6a16f680c500fff1"
  integrity sha512-JCrmN13jI4+h9UAyKEoGcDZV+i1E7BLFuG7OsaDvTXI5P0qhHX+vZO/kOhz9jn8HGENDKbwSeB0nVOg4gVStGA==
  dependencies:
    bail "^1.0.0"
    extend "^3.0.0"
    is-plain-obj "^2.0.0"
    trough "^1.0.0"
    vfile "^4.0.0"

unified@^9.0.0:
  version "9.2.2"
  resolved "https://registry.npmmirror.com/unified/-/unified-9.2.2.tgz#67649a1abfc3ab85d2969502902775eb03146975"
  integrity sha512-Sg7j110mtefBD+qunSLO1lqOEKdrwBFBrR6Qd8f4uwkhWNlbkaqwHse6e7QvD3AP/MNoJdEDLaf8OxYyoWgorQ==
  dependencies:
    bail "^1.0.0"
    extend "^3.0.0"
    is-buffer "^2.0.0"
    is-plain-obj "^2.0.0"
    trough "^1.0.0"
    vfile "^4.0.0"

unique-string@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/unique-string/-/unique-string-2.0.0.tgz#39c6451f81afb2749de2b233e3f7c5e8843bd89d"
  integrity sha512-uNaeirEPvpZWSgzwsPGtU2zVSTrn/8L5q/IexZmH0eH6SA73CmAA5U4GwORTxQAZs95TAXLNqeLoPPNO5gZfWg==
  dependencies:
    crypto-random-string "^2.0.0"

unist-builder@2.0.3, unist-builder@^2.0.0:
  version "2.0.3"
  resolved "https://registry.npmmirror.com/unist-builder/-/unist-builder-2.0.3.tgz#77648711b5d86af0942f334397a33c5e91516436"
  integrity sha512-f98yt5pnlMWlzP539tPc4grGMsFaQQlP/vM396b00jngsiINumNmsY8rkXjfoi1c6QaM8nQ3vaGDuoKWbe/1Uw==

unist-util-find-after@^3.0.0:
  version "3.0.0"
  resolved "https://registry.npmmirror.com/unist-util-find-after/-/unist-util-find-after-3.0.0.tgz#5c65fcebf64d4f8f496db46fa8fd0fbf354b43e6"
  integrity sha512-ojlBqfsBftYXExNu3+hHLfJQ/X1jYY/9vdm4yZWjIbf0VuWF6CRufci1ZyoD/wV2TYMKxXUoNuoqwy+CkgzAiQ==
  dependencies:
    unist-util-is "^4.0.0"

unist-util-generated@^1.0.0:
  version "1.1.6"
  resolved "https://registry.npmmirror.com/unist-util-generated/-/unist-util-generated-1.1.6.tgz#5ab51f689e2992a472beb1b35f2ce7ff2f324d4b"
  integrity sha512-cln2Mm1/CZzN5ttGK7vkoGw+RZ8VcUH6BtGbq98DDtRGquAAOXig1mrBQYelOwMXYS8rK+vZDyyojSjp7JX+Lg==

unist-util-is@^4.0.0:
  version "4.1.0"
  resolved "https://registry.npmmirror.com/unist-util-is/-/unist-util-is-4.1.0.tgz#976e5f462a7a5de73d94b706bac1b90671b57797"
  integrity sha512-ZOQSsnce92GrxSqlnEEseX0gi7GH9zTJZ0p9dtu87WRb/37mMPO2Ilx1s/t9vBHrFhbgweUwb+t7cIn5dxPhZg==

unist-util-position@^3.0.0:
  version "3.1.0"
  resolved "https://registry.npmmirror.com/unist-util-position/-/unist-util-position-3.1.0.tgz#1c42ee6301f8d52f47d14f62bbdb796571fa2d47"
  integrity sha512-w+PkwCbYSFw8vpgWD0v7zRCl1FpY3fjDSQ3/N/wNd9Ffa4gPi8+4keqt99N3XW6F99t/mUzp2xAhNmfKWp95QA==

unist-util-remove-position@^2.0.0:
  version "2.0.1"
  resolved "https://registry.npmmirror.com/unist-util-remove-position/-/unist-util-remove-position-2.0.1.tgz#5d19ca79fdba712301999b2b73553ca8f3b352cc"
  integrity sha512-fDZsLYIe2uT+oGFnuZmy73K6ZxOPG/Qcm+w7jbEjaFcJgbQ6cqjs/eSPzXhsmGpAsWPkqZM9pYjww5QTn3LHMA==
  dependencies:
    unist-util-visit "^2.0.0"

unist-util-remove@2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/unist-util-remove/-/unist-util-remove-2.0.0.tgz#32c2ad5578802f2ca62ab808173d505b2c898488"
  integrity sha512-HwwWyNHKkeg/eXRnE11IpzY8JT55JNM1YCwwU9YNCnfzk6s8GhPXrVBBZWiwLeATJbI7euvoGSzcy9M29UeW3g==
  dependencies:
    unist-util-is "^4.0.0"

unist-util-remove@^2.0.0:
  version "2.1.0"
  resolved "https://registry.npmmirror.com/unist-util-remove/-/unist-util-remove-2.1.0.tgz#b0b4738aa7ee445c402fda9328d604a02d010588"
  integrity sha512-J8NYPyBm4baYLdCbjmf1bhPu45Cr1MWTm77qd9istEkzWpnN6O9tMsEbB2JhNnBCqGENRqEWomQ+He6au0B27Q==
  dependencies:
    unist-util-is "^4.0.0"

unist-util-stringify-position@^2.0.0:
  version "2.0.3"
  resolved "https://registry.npmmirror.com/unist-util-stringify-position/-/unist-util-stringify-position-2.0.3.tgz#cce3bfa1cdf85ba7375d1d5b17bdc4cada9bd9da"
  integrity sha512-3faScn5I+hy9VleOq/qNbAd6pAx7iH5jYBMS9I1HgQVijz/4mv5Bvw5iw1sC/90CODiKo81G/ps8AJrISn687g==
  dependencies:
    "@types/unist" "^2.0.2"

unist-util-visit-parents@^3.0.0:
  version "3.1.1"
  resolved "https://registry.npmmirror.com/unist-util-visit-parents/-/unist-util-visit-parents-3.1.1.tgz#65a6ce698f78a6b0f56aa0e88f13801886cdaef6"
  integrity sha512-1KROIZWo6bcMrZEwiH2UrXDyalAa0uqzWCxCJj6lPOvTve2WkfgCytoDTPaMnodXh1WrXOq0haVYHj99ynJlsg==
  dependencies:
    "@types/unist" "^2.0.0"
    unist-util-is "^4.0.0"

unist-util-visit@2.0.3, unist-util-visit@^2.0.0, unist-util-visit@^2.0.1, unist-util-visit@^2.0.2, unist-util-visit@^2.0.3:
  version "2.0.3"
  resolved "https://registry.npmmirror.com/unist-util-visit/-/unist-util-visit-2.0.3.tgz#c3703893146df47203bb8a9795af47d7b971208c"
  integrity sha512-iJ4/RczbJMkD0712mGktuGpm/U4By4FfDonL7N/9tATGIF4imikjOuagyMY53tnZq3NP6BcmlrHhEKAfGWjh7Q==
  dependencies:
    "@types/unist" "^2.0.0"
    unist-util-is "^4.0.0"
    unist-util-visit-parents "^3.0.0"

universalify@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/universalify/-/universalify-2.0.0.tgz#75a4984efedc4b08975c5aeb73f530d02df25717"
  integrity sha512-hAZsKq7Yy11Zu1DE0OzWjw7nnLZmJZYTDZZyEFHZdUhV8FkH5MCfoU1XMaxXovpyW5nq5scPqq0ZDP9Zyl04oQ==

unpipe@1.0.0, unpipe@~1.0.0:
  version "1.0.0"
  resolved "https://registry.npmmirror.com/unpipe/-/unpipe-1.0.0.tgz#b2bf4ee8514aae6165b4817829d21b2ef49904ec"
  integrity sha512-pjy2bYhSsufwWlKwPc+l3cN7+wuJlK6uz0YdJEOlQDbl6jo/YlPi4mb8agUkVC8BF7V8NuzeyPNqRksA3hztKQ==

unquote@~1.1.1:
  version "1.1.1"
  resolved "https://registry.npmmirror.com/unquote/-/unquote-1.1.1.tgz#8fded7324ec6e88a0ff8b905e7c098cdc086d544"
  integrity sha512-vRCqFv6UhXpWxZPyGDh/F3ZpNv8/qo7w6iufLpQg9aKnQ71qM4B5KiI7Mia9COcjEhrO9LueHpMYjYzsWH3OIg==

update-browserslist-db@^1.0.9:
  version "1.0.10"
  resolved "https://registry.npmmirror.com/update-browserslist-db/-/update-browserslist-db-1.0.10.tgz#0f54b876545726f17d00cd9a2561e6dade943ff3"
  integrity sha512-OztqDenkfFkbSG+tRxBeAnCVPckDBcvibKd35yDONx6OU8N7sqgwc7rCbkJ/WcYtVRZ4ba68d6byhC21GFh7sQ==
  dependencies:
    escalade "^3.1.1"
    picocolors "^1.0.0"

update-notifier@^5.1.0:
  version "5.1.0"
  resolved "https://registry.npmmirror.com/update-notifier/-/update-notifier-5.1.0.tgz#4ab0d7c7f36a231dd7316cf7729313f0214d9ad9"
  integrity sha512-ItnICHbeMh9GqUy31hFPrD1kcuZ3rpxDZbf4KUDavXwS0bW5m7SLbDQpGX3UYr072cbrF5hFUs3r5tUsPwjfHw==
  dependencies:
    boxen "^5.0.0"
    chalk "^4.1.0"
    configstore "^5.0.1"
    has-yarn "^2.1.0"
    import-lazy "^2.1.0"
    is-ci "^2.0.0"
    is-installed-globally "^0.4.0"
    is-npm "^5.0.0"
    is-yarn-global "^0.3.0"
    latest-version "^5.1.0"
    pupa "^2.1.1"
    semver "^7.3.4"
    semver-diff "^3.1.1"
    xdg-basedir "^4.0.0"

uri-js@^4.2.2:
  version "4.4.1"
  resolved "https://registry.npmmirror.com/uri-js/-/uri-js-4.4.1.tgz#9b1a52595225859e55f669d928f88c6c57f2a77e"
  integrity sha512-7rKUyy33Q1yc98pQ1DAmLtwX109F7TIfWlW1Ydo8Wl1ii1SeHieeh0HHfPeL2fMXK6z0s8ecKs9frCuLJvndBg==
  dependencies:
    punycode "^2.1.0"

url-loader@^4.1.1:
  version "4.1.1"
  resolved "https://registry.npmmirror.com/url-loader/-/url-loader-4.1.1.tgz#28505e905cae158cf07c92ca622d7f237e70a4e2"
  integrity sha512-3BTV812+AVHHOJQO8O5MkWgZ5aosP7GnROJwvzLS9hWDj00lZ6Z0wNak423Lp9PBZN05N+Jk/N5Si8jRAlGyWA==
  dependencies:
    loader-utils "^2.0.0"
    mime-types "^2.1.27"
    schema-utils "^3.0.0"

use-composed-ref@^1.3.0:
  version "1.3.0"
  resolved "https://registry.npmmirror.com/use-composed-ref/-/use-composed-ref-1.3.0.tgz#3d8104db34b7b264030a9d916c5e94fbe280dbda"
  integrity sha512-GLMG0Jc/jiKov/3Ulid1wbv3r54K9HlMW29IWcDFPEqFkSO2nS0MuefWgMJpeHQ9YJeXDL3ZUF+P3jdXlZX/cQ==

use-isomorphic-layout-effect@^1.1.1:
  version "1.1.2"
  resolved "https://registry.npmmirror.com/use-isomorphic-layout-effect/-/use-isomorphic-layout-effect-1.1.2.tgz#497cefb13d863d687b08477d9e5a164ad8c1a6fb"
  integrity sha512-49L8yCO3iGT/ZF9QttjwLF/ZD9Iwto5LnH5LmEdk/6cFmXddqi2ulF0edxTwjj+7mqvpVVGQWvbXZdn32wRSHA==

use-latest@^1.2.1:
  version "1.2.1"
  resolved "https://registry.npmmirror.com/use-latest/-/use-latest-1.2.1.tgz#d13dfb4b08c28e3e33991546a2cee53e14038cf2"
  integrity sha512-xA+AVm/Wlg3e2P/JiItTziwS7FK92LWrDB0p+hgXloIMuVCeJJ8v6f0eeHyPZaJrM+usM1FkFfbNCrJGs8A/zw==
  dependencies:
    use-isomorphic-layout-effect "^1.1.1"

util-deprecate@^1.0.1, util-deprecate@^1.0.2, util-deprecate@~1.0.1:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/util-deprecate/-/util-deprecate-1.0.2.tgz#450d4dc9fa70de732762fbd2d4a28981419a0ccf"
  integrity sha512-EPD5q1uXyFxJpCrLnCc1nHnq3gOa6DZBocAIiI2TaSCA7VCJ1UJDMagCzIkXNsUYfD1daK//LTEQ8xiIbrHtcw==

util.promisify@~1.0.0:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/util.promisify/-/util.promisify-1.0.1.tgz#6baf7774b80eeb0f7520d8b81d07982a59abbaee"
  integrity sha512-g9JpC/3He3bm38zsLupWryXHoEcS22YHthuPQSJdMy6KNrzIRzWqcsHzD/WUnqe45whVou4VIsPew37DoXWNrA==
  dependencies:
    define-properties "^1.1.3"
    es-abstract "^1.17.2"
    has-symbols "^1.0.1"
    object.getownpropertydescriptors "^2.1.0"

utila@~0.4:
  version "0.4.0"
  resolved "https://registry.npmmirror.com/utila/-/utila-0.4.0.tgz#8a16a05d445657a3aea5eecc5b12a4fa5379772c"
  integrity sha512-Z0DbgELS9/L/75wZbro8xAnT50pBVFQZ+hUEueGDU5FN51YSCYM+jdxsfCiHjwNP/4LCDD0i/graKpeBnOXKRA==

utility-types@^3.10.0:
  version "3.10.0"
  resolved "https://registry.npmmirror.com/utility-types/-/utility-types-3.10.0.tgz#ea4148f9a741015f05ed74fd615e1d20e6bed82b"
  integrity sha512-O11mqxmi7wMKCo6HKFt5AhO4BwY3VV68YU07tgxfz8zJTIxr4BpsezN49Ffwy9j3ZpwwJp4fkRwjRzq3uWE6Rg==

utils-merge@1.0.1:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/utils-merge/-/utils-merge-1.0.1.tgz#9f95710f50a267947b2ccc124741c1028427e713"
  integrity sha512-pMZTvIkT1d+TFGvDOqodOclx0QWkkgi6Tdoa8gC8ffGAAqz9pzPTZWAybbsHHoED/ztMtkv/VoYTYyShUn81hA==

uuid@^8.3.2:
  version "8.3.2"
  resolved "https://registry.npmmirror.com/uuid/-/uuid-8.3.2.tgz#80d5b5ced271bb9af6c445f21a1a04c606cefbe2"
  integrity sha512-+NYs2QeMWy+GWFOEm9xnn6HCDp0l7QBD7ml8zLUmJ+93Q5NF0NocErnwkTkXVFNiX3/fpC6afS8Dhb/gz7R7eg==

value-equal@^1.0.1:
  version "1.0.1"
  resolved "https://registry.npmmirror.com/value-equal/-/value-equal-1.0.1.tgz#1e0b794c734c5c0cade179c437d356d931a34d6c"
  integrity sha512-NOJ6JZCAWr0zlxZt+xqCHNTEKOsrks2HQd4MqhP1qy4z1SkbEP467eNx6TgDKXMvUOb+OENfJCZwM+16n7fRfw==

vary@~1.1.2:
  version "1.1.2"
  resolved "https://registry.npmmirror.com/vary/-/vary-1.1.2.tgz#2299f02c6ded30d4a5961b0b9f74524a18f634fc"
  integrity sha512-BNGbWLfd0eUPabhkXUVm0j8uuvREyTh5ovRa/dyow/BqAbZJyC+5fU+IzQOzmAKzYqYRAISoRhdQr3eIZ/PXqg==

vfile-location@^3.0.0, vfile-location@^3.2.0:
  version "3.2.0"
  resolved "https://registry.npmmirror.com/vfile-location/-/vfile-location-3.2.0.tgz#d8e41fbcbd406063669ebf6c33d56ae8721d0f3c"
  integrity sha512-aLEIZKv/oxuCDZ8lkJGhuhztf/BW4M+iHdCwglA/eWc+vtuRFJj8EtgceYFX4LRjOhCAAiNHsKGssC6onJ+jbA==

vfile-message@^2.0.0:
  version "2.0.4"
  resolved "https://registry.npmmirror.com/vfile-message/-/vfile-message-2.0.4.tgz#5b43b88171d409eae58477d13f23dd41d52c371a"
  integrity sha512-DjssxRGkMvifUOJre00juHoP9DPWuzjxKuMDrhNbk2TdaYYBNMStsNhEOt3idrtI12VQYM/1+iM0KOzXi4pxwQ==
  dependencies:
    "@types/unist" "^2.0.0"
    unist-util-stringify-position "^2.0.0"

vfile@^4.0.0:
  version "4.2.1"
  resolved "https://registry.npmmirror.com/vfile/-/vfile-4.2.1.tgz#03f1dce28fc625c625bc6514350fbdb00fa9e624"
  integrity sha512-O6AE4OskCG5S1emQ/4gl8zK586RqA3srz3nfK/Viy0UPToBc5Trp9BVFb1u0CjsKrAWwnpr4ifM/KBXPWwJbCA==
  dependencies:
    "@types/unist" "^2.0.0"
    is-buffer "^2.0.0"
    unist-util-stringify-position "^2.0.0"
    vfile-message "^2.0.0"

wait-on@^6.0.0:
  version "6.0.1"
  resolved "https://registry.npmmirror.com/wait-on/-/wait-on-6.0.1.tgz#16bbc4d1e4ebdd41c5b4e63a2e16dbd1f4e5601e"
  integrity sha512-zht+KASY3usTY5u2LgaNqn/Cd8MukxLGjdcZxT2ns5QzDmTFc4XoWBgC+C/na+sMRZTuVygQoMYwdcVjHnYIVw==
  dependencies:
    axios "^0.25.0"
    joi "^17.6.0"
    lodash "^4.17.21"
    minimist "^1.2.5"
    rxjs "^7.5.4"

watchpack@^2.4.0:
  version "2.4.0"
  resolved "https://registry.npmmirror.com/watchpack/-/watchpack-2.4.0.tgz#fa33032374962c78113f93c7f2fb4c54c9862a5d"
  integrity sha512-Lcvm7MGST/4fup+ifyKi2hjyIAwcdI4HRgtvTpIUxBRhB+RFtUh8XtDOxUfctVCnhVi+QQj49i91OyvzkJl6cg==
  dependencies:
    glob-to-regexp "^0.4.1"
    graceful-fs "^4.1.2"

wbuf@^1.1.0, wbuf@^1.7.3:
  version "1.7.3"
  resolved "https://registry.npmmirror.com/wbuf/-/wbuf-1.7.3.tgz#c1d8d149316d3ea852848895cb6a0bfe887b87df"
  integrity sha512-O84QOnr0icsbFGLS0O3bI5FswxzRr8/gHwWkDlQFskhSPryQXvrTMxjxGP4+iWYoauLoBvfDpkrOauZ+0iZpDA==
  dependencies:
    minimalistic-assert "^1.0.0"

web-namespaces@^1.0.0, web-namespaces@^1.1.2:
  version "1.1.4"
  resolved "https://registry.npmmirror.com/web-namespaces/-/web-namespaces-1.1.4.tgz#bc98a3de60dadd7faefc403d1076d529f5e030ec"
  integrity sha512-wYxSGajtmoP4WxfejAPIr4l0fVh+jeMXZb08wNc0tMg6xsfZXj3cECqIK0G7ZAqUq0PP8WlMDtaOGVBTAWztNw==

webidl-conversions@^3.0.0:
  version "3.0.1"
  resolved "https://registry.npmmirror.com/webidl-conversions/-/webidl-conversions-3.0.1.tgz#24534275e2a7bc6be7bc86611cc16ae0a5654871"
  integrity sha512-2JAn3z8AR6rjK8Sm8orRC0h/bcl/DqL7tRPdGZ4I1CjdF+EaMLmYxBHyXuKL849eucPFhvBoxMsflfOb8kxaeQ==

webpack-bundle-analyzer@^4.4.2:
  version "4.7.0"
  resolved "https://registry.npmmirror.com/webpack-bundle-analyzer/-/webpack-bundle-analyzer-4.7.0.tgz#33c1c485a7fcae8627c547b5c3328b46de733c66"
  integrity sha512-j9b8ynpJS4K+zfO5GGwsAcQX4ZHpWV+yRiHDiL+bE0XHJ8NiPYLTNVQdlFYWxtpg9lfAQNlwJg16J9AJtFSXRg==
  dependencies:
    acorn "^8.0.4"
    acorn-walk "^8.0.0"
    chalk "^4.1.0"
    commander "^7.2.0"
    gzip-size "^6.0.0"
    lodash "^4.17.20"
    opener "^1.5.2"
    sirv "^1.0.7"
    ws "^7.3.1"

webpack-dev-middleware@^5.3.1:
  version "5.3.3"
  resolved "https://registry.npmmirror.com/webpack-dev-middleware/-/webpack-dev-middleware-5.3.3.tgz#efae67c2793908e7311f1d9b06f2a08dcc97e51f"
  integrity sha512-hj5CYrY0bZLB+eTO+x/j67Pkrquiy7kWepMHmUMoPsmcUaeEnQJqFzHJOyxgWlq746/wUuA64p9ta34Kyb01pA==
  dependencies:
    colorette "^2.0.10"
    memfs "^3.4.3"
    mime-types "^2.1.31"
    range-parser "^1.2.1"
    schema-utils "^4.0.0"

webpack-dev-server@^4.4.0:
  version "4.11.1"
  resolved "https://registry.npmmirror.com/webpack-dev-server/-/webpack-dev-server-4.11.1.tgz#ae07f0d71ca0438cf88446f09029b92ce81380b5"
  integrity sha512-lILVz9tAUy1zGFwieuaQtYiadImb5M3d+H+L1zDYalYoDl0cksAB1UNyuE5MMWJrG6zR1tXkCP2fitl7yoUJiw==
  dependencies:
    "@types/bonjour" "^3.5.9"
    "@types/connect-history-api-fallback" "^1.3.5"
    "@types/express" "^4.17.13"
    "@types/serve-index" "^1.9.1"
    "@types/serve-static" "^1.13.10"
    "@types/sockjs" "^0.3.33"
    "@types/ws" "^8.5.1"
    ansi-html-community "^0.0.8"
    bonjour-service "^1.0.11"
    chokidar "^3.5.3"
    colorette "^2.0.10"
    compression "^1.7.4"
    connect-history-api-fallback "^2.0.0"
    default-gateway "^6.0.3"
    express "^4.17.3"
    graceful-fs "^4.2.6"
    html-entities "^2.3.2"
    http-proxy-middleware "^2.0.3"
    ipaddr.js "^2.0.1"
    open "^8.0.9"
    p-retry "^4.5.0"
    rimraf "^3.0.2"
    schema-utils "^4.0.0"
    selfsigned "^2.1.1"
    serve-index "^1.9.1"
    sockjs "^0.3.24"
    spdy "^4.0.2"
    webpack-dev-middleware "^5.3.1"
    ws "^8.4.2"

webpack-merge@^5.8.0:
  version "5.8.0"
  resolved "https://registry.npmmirror.com/webpack-merge/-/webpack-merge-5.8.0.tgz#2b39dbf22af87776ad744c390223731d30a68f61"
  integrity sha512-/SaI7xY0831XwP6kzuwhKWVKDP9t1QY1h65lAFLbZqMPIuYcD9QAW4u9STIbU9kaJbPBB/geU/gLr1wDjOhQ+Q==
  dependencies:
    clone-deep "^4.0.1"
    wildcard "^2.0.0"

webpack-sources@^1.1.0:
  version "1.4.3"
  resolved "https://registry.npmmirror.com/webpack-sources/-/webpack-sources-1.4.3.tgz#eedd8ec0b928fbf1cbfe994e22d2d890f330a933"
  integrity sha512-lgTS3Xhv1lCOKo7SA5TjKXMjpSM4sBjNV5+q2bqesbSPs5FjGmU6jjtBSkX9b4qW87vDIsCIlUPOEhbZrMdjeQ==
  dependencies:
    source-list-map "^2.0.0"
    source-map "~0.6.1"

webpack-sources@^3.2.2, webpack-sources@^3.2.3:
  version "3.2.3"
  resolved "https://registry.npmmirror.com/webpack-sources/-/webpack-sources-3.2.3.tgz#2d4daab8451fd4b240cc27055ff6a0c2ccea0cde"
  integrity sha512-/DyMEOrDgLKKIG0fmvtz+4dUX/3Ghozwgm6iPp8KRhvn+eQf9+Q7GWxVNMk3+uCPWfdXYC4ExGBckIXdFEfH1w==

webpack@^5.61.0, webpack@^5.73.0:
  version "5.76.1"
  resolved "https://registry.yarnpkg.com/webpack/-/webpack-5.76.1.tgz#7773de017e988bccb0f13c7d75ec245f377d295c"
  integrity sha512-4+YIK4Abzv8172/SGqObnUjaIHjLEuUasz9EwQj/9xmPPkYJy2Mh03Q/lJfSD3YLzbxy5FeTq5Uw0323Oh6SJQ==
  dependencies:
    "@types/eslint-scope" "^3.7.3"
    "@types/estree" "^0.0.51"
    "@webassemblyjs/ast" "1.11.1"
    "@webassemblyjs/wasm-edit" "1.11.1"
    "@webassemblyjs/wasm-parser" "1.11.1"
    acorn "^8.7.1"
    acorn-import-assertions "^1.7.6"
    browserslist "^4.14.5"
    chrome-trace-event "^1.0.2"
    enhanced-resolve "^5.10.0"
    es-module-lexer "^0.9.0"
    eslint-scope "5.1.1"
    events "^3.2.0"
    glob-to-regexp "^0.4.1"
    graceful-fs "^4.2.9"
    json-parse-even-better-errors "^2.3.1"
    loader-runner "^4.2.0"
    mime-types "^2.1.27"
    neo-async "^2.6.2"
    schema-utils "^3.1.0"
    tapable "^2.1.1"
    terser-webpack-plugin "^5.1.3"
    watchpack "^2.4.0"
    webpack-sources "^3.2.3"

webpackbar@^5.0.0-3:
  version "5.0.2"
  resolved "https://registry.npmmirror.com/webpackbar/-/webpackbar-5.0.2.tgz#d3dd466211c73852741dfc842b7556dcbc2b0570"
  integrity sha512-BmFJo7veBDgQzfWXl/wwYXr/VFus0614qZ8i9znqcl9fnEdiVkdbi0TedLQ6xAK92HZHDJ0QmyQ0fmuZPAgCYQ==
  dependencies:
    chalk "^4.1.0"
    consola "^2.15.3"
    pretty-time "^1.1.0"
    std-env "^3.0.1"

websocket-driver@>=0.5.1, websocket-driver@^0.7.4:
  version "0.7.4"
  resolved "https://registry.npmmirror.com/websocket-driver/-/websocket-driver-0.7.4.tgz#89ad5295bbf64b480abcba31e4953aca706f5760"
  integrity sha512-b17KeDIQVjvb0ssuSDF2cYXSg2iztliJ4B9WdsuB6J952qCPKmnVq4DyW5motImXHDC1cBT/1UezrJVsKw5zjg==
  dependencies:
    http-parser-js ">=0.5.1"
    safe-buffer ">=5.1.0"
    websocket-extensions ">=0.1.1"

websocket-extensions@>=0.1.1:
  version "0.1.4"
  resolved "https://registry.npmmirror.com/websocket-extensions/-/websocket-extensions-0.1.4.tgz#7f8473bc839dfd87608adb95d7eb075211578a42"
  integrity sha512-OqedPIGOfsDlo31UNwYbCFMSaO9m9G/0faIHj5/dZFDMFqPTcx6UwqyOy3COEaEOg/9VsGIpdqn62W5KhoKSpg==

whatwg-url@^5.0.0:
  version "5.0.0"
  resolved "https://registry.npmmirror.com/whatwg-url/-/whatwg-url-5.0.0.tgz#966454e8765462e37644d3626f6742ce8b70965d"
  integrity sha512-saE57nupxk6v3HY35+jzBwYa0rKSy0XR8JSxZPwgLr7ys0IBzhGviA1/TUGJLmSVqs8pb9AnvICXEuOHLprYTw==
  dependencies:
    tr46 "~0.0.3"
    webidl-conversions "^3.0.0"

which-boxed-primitive@^1.0.2:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/which-boxed-primitive/-/which-boxed-primitive-1.0.2.tgz#13757bc89b209b049fe5d86430e21cf40a89a8e6"
  integrity sha512-bwZdv0AKLpplFY2KZRX6TvyuN7ojjr7lwkg6ml0roIy9YeuSr7JS372qlNW18UQYzgYK9ziGcerWqZOmEn9VNg==
  dependencies:
    is-bigint "^1.0.1"
    is-boolean-object "^1.1.0"
    is-number-object "^1.0.4"
    is-string "^1.0.5"
    is-symbol "^1.0.3"

which@^1.3.1:
  version "1.3.1"
  resolved "https://registry.npmmirror.com/which/-/which-1.3.1.tgz#a45043d54f5805316da8d62f9f50918d3da70b0a"
  integrity sha512-HxJdYWq1MTIQbJ3nw0cqssHoTNU267KlrDuGZ1WYlxDStUtKUhOaJmh112/TZmHxxUfuJqPXSOm7tDyas0OSIQ==
  dependencies:
    isexe "^2.0.0"

which@^2.0.1:
  version "2.0.2"
  resolved "https://registry.npmmirror.com/which/-/which-2.0.2.tgz#7c6a8dd0a636a0327e10b59c9286eee93f3f51b1"
  integrity sha512-BLI3Tl1TW3Pvl70l3yq3Y64i+awpwXqsGBYWkkqMtnbXgrMD+yj7rhW0kuEDxzJaYXGjEW5ogapKNMEKNMjibA==
  dependencies:
    isexe "^2.0.0"

widest-line@^3.1.0:
  version "3.1.0"
  resolved "https://registry.npmmirror.com/widest-line/-/widest-line-3.1.0.tgz#8292333bbf66cb45ff0de1603b136b7ae1496eca"
  integrity sha512-NsmoXalsWVDMGupxZ5R08ka9flZjjiLvHVAWYOKtiKM8ujtZWr9cRffak+uSE48+Ob8ObalXpwyeUiyDD6QFgg==
  dependencies:
    string-width "^4.0.0"

wildcard@^2.0.0:
  version "2.0.0"
  resolved "https://registry.npmmirror.com/wildcard/-/wildcard-2.0.0.tgz#a77d20e5200c6faaac979e4b3aadc7b3dd7f8fec"
  integrity sha512-JcKqAHLPxcdb9KM49dufGXn2x3ssnfjbcaQdLlfZsL9rH9wgDQjUtDxbo8NE0F6SFvydeu1VhZe7hZuHsB2/pw==

wrap-ansi@^7.0.0:
  version "7.0.0"
  resolved "https://registry.npmmirror.com/wrap-ansi/-/wrap-ansi-7.0.0.tgz#67e145cff510a6a6984bdf1152911d69d2eb9e43"
  integrity sha512-YVGIj2kamLSTxw6NsZjoBxfSwsn0ycdesmc4p+Q21c5zPuZ1pl+NfxVdxPtdHvmNVOQ6XSYG4AUtyt/Fi7D16Q==
  dependencies:
    ansi-styles "^4.0.0"
    string-width "^4.1.0"
    strip-ansi "^6.0.0"

wrappy@1:
  version "1.0.2"
  resolved "https://registry.npmmirror.com/wrappy/-/wrappy-1.0.2.tgz#b5243d8f3ec1aa35f1364605bc0d1036e30ab69f"
  integrity sha512-l4Sp/DRseor9wL6EvV2+TuQn63dMkPjZ/sp9XkghTEbV9KlPS1xUsZ3u7/IQO4wxtcFB4bgpQPRcR3QCvezPcQ==

write-file-atomic@^3.0.0:
  version "3.0.3"
  resolved "https://registry.npmmirror.com/write-file-atomic/-/write-file-atomic-3.0.3.tgz#56bd5c5a5c70481cd19c571bd39ab965a5de56e8"
  integrity sha512-AvHcyZ5JnSfq3ioSyjrBkH9yW4m7Ayk8/9My/DD9onKeu/94fwrMocemO2QAJFAlnnDN+ZDS+ZjAR5ua1/PV/Q==
  dependencies:
    imurmurhash "^0.1.4"
    is-typedarray "^1.0.0"
    signal-exit "^3.0.2"
    typedarray-to-buffer "^3.1.5"

ws@^7.3.1:
  version "7.5.9"
  resolved "https://registry.npmmirror.com/ws/-/ws-7.5.9.tgz#54fa7db29f4c7cec68b1ddd3a89de099942bb591"
  integrity sha512-F+P9Jil7UiSKSkppIiD94dN07AwvFixvLIj1Og1Rl9GGMuNipJnV9JzjD6XuqmAeiswGvUmNLjr5cFuXwNS77Q==

ws@^8.4.2:
  version "8.10.0"
  resolved "https://registry.npmmirror.com/ws/-/ws-8.10.0.tgz#00a28c09dfb76eae4eb45c3b565f771d6951aa51"
  integrity sha512-+s49uSmZpvtAsd2h37vIPy1RBusaLawVe8of+GyEPsaJTCMpj/2v8NpeK1SHXjBlQ95lQTmQofOJnFiLoaN3yw==

xdg-basedir@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/xdg-basedir/-/xdg-basedir-4.0.0.tgz#4bc8d9984403696225ef83a1573cbbcb4e79db13"
  integrity sha512-PSNhEJDejZYV7h50BohL09Er9VaIefr2LMAf3OEmpCkjOi34eYyQYAXUTjEQtZJTKcF0E2UKTh+osDLsgNim9Q==

xml-js@^1.6.11:
  version "1.6.11"
  resolved "https://registry.npmmirror.com/xml-js/-/xml-js-1.6.11.tgz#927d2f6947f7f1c19a316dd8eea3614e8b18f8e9"
  integrity sha512-7rVi2KMfwfWFl+GpPg6m80IVMWXLRjO+PxTq7V2CDhoGak0wzYzFgUY2m4XJ47OGdXd8eLE8EmwfAmdjw7lC1g==
  dependencies:
    sax "^1.2.4"

xtend@^4.0.0, xtend@^4.0.1:
  version "4.0.2"
  resolved "https://registry.npmmirror.com/xtend/-/xtend-4.0.2.tgz#bb72779f5fa465186b1f438f674fa347fdb5db54"
  integrity sha512-LKYU1iAXJXUgAXn9URjiu+MWhyUXHsvfp7mcuYm9dSUKK0/CjtrUwFAxD82/mCWbtLsGjFIad0wIsod4zrTAEQ==

yallist@^4.0.0:
  version "4.0.0"
  resolved "https://registry.npmmirror.com/yallist/-/yallist-4.0.0.tgz#9bb92790d9c0effec63be73519e11a35019a3a72"
  integrity sha512-3wdGidZyq5PB084XLES5TpOSRA3wjXAlIWMhum2kRcv/41Sn2emQ0dycQW4uZXLejwKvg6EsvbdlVL+FYEct7A==

yaml@^1.10.0, yaml@^1.10.2, yaml@^1.7.2:
  version "1.10.2"
  resolved "https://registry.npmmirror.com/yaml/-/yaml-1.10.2.tgz#2301c5ffbf12b467de8da2333a459e29e7920e4b"
  integrity sha512-r3vXyErRCYJ7wg28yvBY5VSoAF8ZvlcW9/BwUzEtUsjvX/DKs24dIkuwjtuprwJJHsbyUbLApepYTR1BN4uHrg==

yocto-queue@^0.1.0:
  version "0.1.0"
  resolved "https://registry.npmmirror.com/yocto-queue/-/yocto-queue-0.1.0.tgz#0294eb3dee05028d31ee1a5fa2c556a6aaf10a1b"
  integrity sha512-rVksvsnNCdJ/ohGc6xgPwyN8eheCxsiLM8mxuE/t/mOVqJewPuO1miLpTHQiRgTKCLexL4MeAFVagts7HmNZ2Q==

zwitch@^1.0.0:
  version "1.0.5"
  resolved "https://registry.npmmirror.com/zwitch/-/zwitch-1.0.5.tgz#d11d7381ffed16b742f6af7b3f223d5cd9fe9920"
  integrity sha512-V50KMwwzqJV0NpZIZFwfOD5/lyny3WlSzRiXgA0G7VUnRlqttta1L6UQIHzd6EuBY/cHGfwTIck7w1yH6Q5zUw==

```````




`../gpt-researcher/docs/README.md`:

```````md
# Website

This website is built using [Docusaurus 2](https://docusaurus.io/), a modern static website generator.

## Prerequisites

To build and test documentation locally, begin by downloading and installing [Node.js](https://nodejs.org/en/download/), and then installing [Yarn](https://classic.yarnpkg.com/en/).
On Windows, you can install via the npm package manager (npm) which comes bundled with Node.js:

```console
npm install --global yarn
```

## Installation

```console
pip install pydoc-markdown
cd website
yarn install
```

## Local Development

Navigate to the website folder and run:

```console
pydoc-markdown
yarn start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

```````




`../gpt-researcher/docs/blog/authors.yml`:

```````yml
assafe:
  name: Assaf Elovic
  title: Creator @ GPT Researcher
  url: https://github.com/assafelovic
  image_url: https://lh3.googleusercontent.com/a/ACg8ocJtrLku69VG_2Y0sJa5mt66gIGNaEBX5r_mgE6CRPEb7A=s96-c

```````




`../gpt-researcher/docs/blog/2023-11-12-openai-assistant/index.md`:

```````md
---
slug: building-openai-assistant
title: How to build an OpenAI Assistant with Internet access
authors: [assafe]
tags: [tavily, search-api, openai, assistant-api]
---

OpenAI has done it again with a [groundbreaking DevDay](https://openai.com/blog/new-models-and-developer-products-announced-at-devday) showcasing some of the latest improvements to the OpenAI suite of tools, products and services. One major release was the new [Assistants API](https://platform.openai.com/docs/assistants/overview) that makes it easier for developers to build their own assistive AI apps that have goals and can call models and tools.

The new Assistants API currently supports three types of tools: Code Interpreter, Retrieval, and Function calling. Although you might expect the Retrieval tool to support online information retrieval (such as search APIs or as ChatGPT plugins), it only supports raw data for now such as text or CSV files.

This blog will demonstrate how to leverage the latest Assistants API with online information using the function calling tool.

To skip the tutorial below, feel free to check out the full [Github Gist here](https://gist.github.com/assafelovic/579822cd42d52d80db1e1c1ff82ffffd).

At a high level, a typical integration of the Assistants API has the following steps:

- Create an [Assistant](https://platform.openai.com/docs/api-reference/assistants/createAssistant) in the API by defining its custom instructions and picking a model. If helpful, enable tools like Code Interpreter, Retrieval, and Function calling.
- Create a [Thread](https://platform.openai.com/docs/api-reference/threads) when a user starts a conversation.
- Add [Messages](https://platform.openai.com/docs/api-reference/messages) to the Thread as the user ask questions.
- [Run](https://platform.openai.com/docs/api-reference/runs) the Assistant on the Thread to trigger responses. This automatically calls the relevant tools.

As you can see below, an Assistant object includes Threads for storing and handling conversation sessions between the assistant and users, and Run for invocation of an Assistant on a Thread.

![OpenAI Assistant Object](./diagram-assistant.jpeg)

Let’s go ahead and implement these steps one by one! For the example, we will build a finance GPT that can provide insights about financial questions. We will use the [OpenAI Python SDK v1.2](https://github.com/openai/openai-python/tree/main#installation) and [Tavily Search API](https://tavily.com).

First things first, let’s define the assistant’s instructions:

```python
assistant_prompt_instruction = """You are a finance expert. 
Your goal is to provide answers based on information from the internet. 
You must use the provided Tavily search API function to find relevant online information. 
You should never use your own knowledge to answer questions.
Please include relevant url sources in the end of your answers.
"""
```
Next, let’s finalize step 1 and create an assistant using the latest [GPT-4 Turbo model](https://github.com/openai/openai-python/tree/main#installation) (128K context), and the call function using the [Tavily web search API](https://tavily.com/):

```python
# Create an assistant
assistant = client.beta.assistants.create(
    instructions=assistant_prompt_instruction,
    model="gpt-4-1106-preview",
    tools=[{
        "type": "function",
        "function": {
            "name": "tavily_search",
            "description": "Get information on recent events from the web.",
            "parameters": {
                "type": "object",
                "properties": {
                    "query": {"type": "string", "description": "The search query to use. For example: 'Latest news on Nvidia stock performance'"},
                },
                "required": ["query"]
            }
        }
    }]
)
```

Step 2+3 are quite straight forward, we’ll initiate a new thread and update it with a user message:

```python
thread = client.beta.threads.create()
user_input = input("You: ")
message = client.beta.threads.messages.create(
    thread_id=thread.id,
    role="user",
    content=user_input,
)
```

Finally, we’ll run the assistant on the thread to trigger the function call and get the response:

```python
run = client.beta.threads.runs.create(
    thread_id=thread.id,
    assistant_id=assistant_id,
)
```

So far so good! But this is where it gets a bit messy. Unlike with the regular GPT APIs, the Assistants API doesn’t return a synchronous response, but returns a status. This allows for asynchronous operations across assistants, but requires more overhead for fetching statuses and dealing with each manually.

![Status Diagram](./diagram-1.png)

To manage this status lifecycle, let’s build a function that can be reused and handles waiting for various statuses (such as ‘requires_action’):

```python
# Function to wait for a run to complete
def wait_for_run_completion(thread_id, run_id):
    while True:
        time.sleep(1)
        run = client.beta.threads.runs.retrieve(thread_id=thread_id, run_id=run_id)
        print(f"Current run status: {run.status}")
        if run.status in ['completed', 'failed', 'requires_action']:
            return run
```

This function will sleep as long as the run has not been finalized such as in cases where it’s completed or requires an action from a function call.

We’re almost there! Lastly, let’s take care of when the assistant wants to call the web search API:

```python
# Function to handle tool output submission
def submit_tool_outputs(thread_id, run_id, tools_to_call):
    tool_output_array = []
    for tool in tools_to_call:
        output = None
        tool_call_id = tool.id
        function_name = tool.function.name
        function_args = tool.function.arguments

        if function_name == "tavily_search":
            output = tavily_search(query=json.loads(function_args)["query"])

        if output:
            tool_output_array.append({"tool_call_id": tool_call_id, "output": output})

    return client.beta.threads.runs.submit_tool_outputs(
        thread_id=thread_id,
        run_id=run_id,
        tool_outputs=tool_output_array
    )
```

As seen above, if the assistant has reasoned that a function call should trigger, we extract the given required function params and pass back to the runnable thread. We catch this status and call our functions as seen below:

```python
if run.status == 'requires_action':
    run = submit_tool_outputs(thread.id, run.id, run.required_action.submit_tool_outputs.tool_calls)
    run = wait_for_run_completion(thread.id, run.id)
```

That’s it! We now have a working OpenAI Assistant that can be used to answer financial questions using real time online information. Below is the full runnable code:

```python
import os
import json
import time
from openai import OpenAI
from tavily import TavilyClient

# Initialize clients with API keys
client = OpenAI(api_key=os.environ["OPENAI_API_KEY"])
tavily_client = TavilyClient(api_key=os.environ["TAVILY_API_KEY"])

assistant_prompt_instruction = """You are a finance expert. 
Your goal is to provide answers based on information from the internet. 
You must use the provided Tavily search API function to find relevant online information. 
You should never use your own knowledge to answer questions.
Please include relevant url sources in the end of your answers.
"""

# Function to perform a Tavily search
def tavily_search(query):
    search_result = tavily_client.get_search_context(query, search_depth="advanced", max_tokens=8000)
    return search_result

# Function to wait for a run to complete
def wait_for_run_completion(thread_id, run_id):
    while True:
        time.sleep(1)
        run = client.beta.threads.runs.retrieve(thread_id=thread_id, run_id=run_id)
        print(f"Current run status: {run.status}")
        if run.status in ['completed', 'failed', 'requires_action']:
            return run

# Function to handle tool output submission
def submit_tool_outputs(thread_id, run_id, tools_to_call):
    tool_output_array = []
    for tool in tools_to_call:
        output = None
        tool_call_id = tool.id
        function_name = tool.function.name
        function_args = tool.function.arguments

        if function_name == "tavily_search":
            output = tavily_search(query=json.loads(function_args)["query"])

        if output:
            tool_output_array.append({"tool_call_id": tool_call_id, "output": output})

    return client.beta.threads.runs.submit_tool_outputs(
        thread_id=thread_id,
        run_id=run_id,
        tool_outputs=tool_output_array
    )

# Function to print messages from a thread
def print_messages_from_thread(thread_id):
    messages = client.beta.threads.messages.list(thread_id=thread_id)
    for msg in messages:
        print(f"{msg.role}: {msg.content[0].text.value}")

# Create an assistant
assistant = client.beta.assistants.create(
    instructions=assistant_prompt_instruction,
    model="gpt-4-1106-preview",
    tools=[{
        "type": "function",
        "function": {
            "name": "tavily_search",
            "description": "Get information on recent events from the web.",
            "parameters": {
                "type": "object",
                "properties": {
                    "query": {"type": "string", "description": "The search query to use. For example: 'Latest news on Nvidia stock performance'"},
                },
                "required": ["query"]
            }
        }
    }]
)
assistant_id = assistant.id
print(f"Assistant ID: {assistant_id}")

# Create a thread
thread = client.beta.threads.create()
print(f"Thread: {thread}")

# Ongoing conversation loop
while True:
    user_input = input("You: ")
    if user_input.lower() == 'exit':
        break

    # Create a message
    message = client.beta.threads.messages.create(
        thread_id=thread.id,
        role="user",
        content=user_input,
    )

    # Create a run
    run = client.beta.threads.runs.create(
        thread_id=thread.id,
        assistant_id=assistant_id,
    )
    print(f"Run ID: {run.id}")

    # Wait for run to complete
    run = wait_for_run_completion(thread.id, run.id)

    if run.status == 'failed':
        print(run.error)
        continue
    elif run.status == 'requires_action':
        run = submit_tool_outputs(thread.id, run.id, run.required_action.submit_tool_outputs.tool_calls)
        run = wait_for_run_completion(thread.id, run.id)

    # Print messages from the thread
    print_messages_from_thread(thread.id)
```

The assistant can be further customized and improved using additional retrieval information, OpenAI’s coding interpreter and more. Also, you can go ahead and add more function tools to make the assistant even smarter.

Feel free to drop a comment below if you have any further questions!

```````




`../gpt-researcher/docs/blog/2023-09-22-gpt-researcher/index.md`:

```````md
---
slug: building-gpt-researcher
title: How we built GPT Researcher
authors: [assafe]
tags: [gpt-researcher, autonomous-agent, opensource, github]
---

After [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) was published, we immediately took it for a spin. The first use case that came to mind was autonomous online research. Forming objective conclusions for manual research tasks can take time, sometimes weeks, to find the right resources and information. Seeing how well AutoGPT created tasks and executed them got me thinking about the great potential of using AI to conduct comprehensive research and what it meant for the future of online research.

But the problem with AutoGPT was that it usually ran into never-ending loops, required human interference for almost every step, constantly lost track of its progress, and almost never actually completed the task.

Nonetheless, the information and context gathered during the research task were lost (such as keeping track of sources), and sometimes hallucinated.

The passion for leveraging AI for online research and the limitations I found put me on a mission to try and solve it while sharing my work with the world. This is when I created [GPT Researcher](https://github.com/assafelovic/gpt-researcher) — an open source autonomous agent for online comprehensive research.

In this article, we will share the steps that guided me toward the proposed solution.

### Moving from infinite loops to deterministic results
The first step in solving these issues was to seek a more deterministic solution that could ultimately guarantee completing any research task within a fixed time frame, without human interference.

This is when we stumbled upon the recent paper [Plan and Solve](https://arxiv.org/abs/2305.04091). The paper aims to provide a better solution for the challenges stated above. The idea is quite simple and consists of two components: first, devising a plan to divide the entire task into smaller subtasks and then carrying out the subtasks according to the plan.

![Planner-Excutor-Model](./planner.jpeg)

As it relates to research, first create an outline of questions to research related to the task, and then deterministically execute an agent for every outline item. This approach eliminates the uncertainty in task completion by breaking the agent steps into a deterministic finite set of tasks. Once all tasks are completed, the agent concludes the research.

Following this strategy has improved the reliability of completing research tasks to 100%. Now the challenge is, how to improve quality and speed?

### Aiming for objective and unbiased results
The biggest challenge with LLMs is the lack of factuality and unbiased responses caused by hallucinations and out-of-date training sets (GPT is currently trained on datasets from 2021). But the irony is that for research tasks, it is crucial to optimize for these exact two criteria: factuality and bias.

To tackle this challenges, we assumed the following:

- Law of large numbers — More content will lead to less biased results. Especially if gathered properly.
- Leveraging LLMs for the summarization of factual information can significantly improve the overall better factuality of results.

After experimenting with LLMs for quite some time, we can say that the areas where foundation models excel are in the summarization and rewriting of given content. So, in theory, if LLMs only review given content and summarize and rewrite it, potentially it would reduce hallucinations significantly.

In addition, assuming the given content is unbiased, or at least holds opinions and information from all sides of a topic, the rewritten result would also be unbiased. So how can content be unbiased? The [law of large numbers](https://en.wikipedia.org/wiki/Law_of_large_numbers). In other words, if enough sites that hold relevant information are scraped, the possibility of biased information reduces greatly. So the idea would be to scrape just enough sites together to form an objective opinion on any topic.

Great! Sounds like, for now, we have an idea for how to create both deterministic, factual, and unbiased results. But what about the speed problem?

### Speeding up the research process
Another issue with AutoGPT is that it works synchronously. The main idea of it is to create a list of tasks and then execute them one by one. So if, let’s say, a research task requires visiting 20 sites, and each site takes around one minute to scrape and summarize, the overall research task would take a minimum of +20 minutes. That’s assuming it ever stops. But what if we could parallelize agent work?

By levering Python libraries such as asyncio, the agent tasks have been optimized to work in parallel, thus significantly reducing the time to research.

```python
# Create a list to hold the coroutine agent tasks
tasks = [async_browse(url, query, self.websocket) for url in await new_search_urls]

# Gather the results as they become available
responses = await asyncio.gather(*tasks, return_exceptions=True)
```

In the example above, we trigger scraping for all URLs in parallel, and only once all is done, continue with the task. Based on many tests, an average research task takes around three minutes (!!). That’s 85% faster than AutoGPT.

### Finalizing the research report
Finally, after aggregating as much information as possible about a given research task, the challenge is to write a comprehensive report about it.

After experimenting with several OpenAI models and even open source, I’ve concluded that the best results are currently achieved with GPT-4. The task is straightforward — provide GPT-4 as context with all the aggregated information, and ask it to write a detailed report about it given the original research task.

The prompt is as follows:
```commandline
"{research_summary}" Using the above information, answer the following question or topic: "{question}" in a detailed report — The report should focus on the answer to the question, should be well structured, informative, in depth, with facts and numbers if available, a minimum of 1,200 words and with markdown syntax and apa format. Write all source urls at the end of the report in apa format. You should write your report only based on the given information and nothing else.
```

The results are quite impressive, with some minor hallucinations in very few samples, but it’s fair to assume that as GPT improves over time, results will only get better.

### The final architecture
Now that we’ve reviewed the necessary steps of GPT Researcher, let’s break down the final architecture, as shown below:

<div align="center">
<img align="center" height="500" src="https://cowriter-images.s3.amazonaws.com/architecture.png"/>
</div>

More specifically:
- Generate an outline of research questions that form an objective opinion on any given task.
- For each research question, trigger a crawler agent that scrapes online resources for information relevant to the given task.
- For each scraped resource, keep track, filter, and summarize only if it includes relevant information.
- Finally, aggregate all summarized sources and generate a final research report.

### Going forward
The future of online research automation is heading toward a major disruption. As AI continues to improve, it is only a matter of time before AI agents can perform comprehensive research tasks for any of our day-to-day needs. AI research can disrupt areas of finance, legal, academia, health, and retail, reducing our time for each research by 95% while optimizing for factual and unbiased reports within an influx and overload of ever-growing online information.

Imagine if an AI can eventually understand and analyze any form of online content — videos, images, graphs, tables, reviews, text, audio. And imagine if it could support and analyze hundreds of thousands of words of aggregated information within a single prompt. Even imagine that AI can eventually improve in reasoning and analysis, making it much more suitable for reaching new and innovative research conclusions. And that it can do all that in minutes, if not seconds.

It’s all a matter of time and what [GPT Researcher](https://github.com/assafelovic/gpt-researcher) is all about.

```````




`../gpt-researcher/docs/pydoc-markdown.yml`:

```````yml
loaders:
   - type: python
     search_path: [../docs]
processors:
  - type: filter
    skip_empty_modules: true
  - type: smart
  - type: crossref
renderer:
  type: docusaurus
  docs_base_path: docs
  relative_output_path: reference
  relative_sidebar_path: sidebar.json
  sidebar_top_level_label: Reference
  markdown:
    escape_html_in_docstring: false

```````




`../gpt-researcher/docs/CNAME`:

```````
docs.tavily.com
```````




`../gpt-researcher/docs/babel.config.js`:

```````js
module.exports = {
  presets: [require.resolve('@docusaurus/core/lib/babel/preset')],
};

```````




`../gpt-researcher/docs/docusaurus.config.js`:

```````js
/** @type {import('@docusaurus/types').DocusaurusConfig} */
const math = require('remark-math');
const katex = require('rehype-katex');

module.exports = {
  title: 'Tavily',
  tagline: 'Tavily is the leading search engine optimized for LLMs',
  url: 'https://docs.tavily.com',
  baseUrl: '/',
  onBrokenLinks: 'ignore',
  //deploymentBranch: 'master',
  onBrokenMarkdownLinks: 'warn',
  favicon: 'img/favicon.ico',
  organizationName: 'assafelovic',
  trailingSlash: false,
  projectName: 'gpt-researcher',
  themeConfig: {
    navbar: {
      //title: 'Tavily',
      logo: {
        alt: 'Tavily',
        src: 'img/tavily.png',
      },
      items: [
        {
          type: 'doc',
          docId: 'welcome',
          position: 'left',
          label: 'Docs',
        },

        {to: 'blog', label: 'Blog', position: 'left'},
        {
          type: 'doc',
          docId: 'faq',
          position: 'left',
          label: 'FAQ',
        },
        {
            href: 'https://app.tavily.com',
            position: 'right',
            label: 'Get API Key',
        },
        {
            href: 'mailto:support@tavily.com',
            position: 'left',
            label: 'Contact',
        },
        {
          href: 'https://github.com/assafelovic/gpt-researcher',
          label: 'GitHub',
          position: 'right',
        },
      ],
    },
    footer: {
      style: 'dark',
      links: [
        {
          title: 'Community',
          items: [
            {
              label: 'Discord',
              href: 'https://discord.gg/8YkBcCED5y',
            },
            {
              label: 'Twitter',
              href: 'https://twitter.com/tavilyai',
            },
            {
              label: 'LinkedIn',
              href: 'https://www.linkedin.com/company/tavily/',
            },
          ],
        },
        {
          title: 'Company',
          items: [
            {
              label: 'Homepage',
              href: 'https://tavily.com',
            },
            {
              label: 'Tavily Platform',
              href: 'https://tavily.com',
            },
            {
              label: 'Contact',
              href: 'mailto:support@tavily.com',
            },
          ],
        },
      ],
      copyright: `Copyright © ${new Date().getFullYear()} Tavily.`,
    },
  },
  presets: [
    [
      '@docusaurus/preset-classic',
      {
        docs: {
          sidebarPath: require.resolve('./sidebars.js'),
          // Please change this to your repo.
          editUrl:
            'https://github.com/assafelovic/gpt-researcher/tree/master/docs',
          remarkPlugins: [math],
          rehypePlugins: [katex],
        },
        theme: {
          customCss: require.resolve('./src/css/custom.css'),
        },
      },
    ],
  ],
  stylesheets: [
    {
        href: "https://cdn.jsdelivr.net/npm/katex@0.13.11/dist/katex.min.css",
        integrity: "sha384-Um5gpz1odJg5Z4HAmzPtgZKdTBHZdw8S29IecapCSB31ligYPhHQZMIlWLYQGVoc",
        crossorigin: "anonymous",
    },
  ],

  plugins: [
    // ... Your other plugins.
    [
      require.resolve("@easyops-cn/docusaurus-search-local"),
      {
        // ... Your options.
        // `hashed` is recommended as long-term-cache of index file is possible.
        hashed: true,
        blogDir:"./blog/"
        // For Docs using Chinese, The `language` is recommended to set to:
        // ```
        // language: ["en", "zh"],
        // ```
        // When applying `zh` in language, please install `nodejieba` in your project.
      },
    ],
  ],
};

```````




`../gpt-researcher/frontend/scripts.js`:

```````js
const GPTResearcher = (() => {
    const init = () => {
      // Not sure, but I think it would be better to add event handlers here instead of in the HTML
      //document.getElementById("startResearch").addEventListener("click", startResearch);
      document.getElementById("copyToClipboard").addEventListener("click", copyToClipboard);

      updateState("initial");
    }

    const startResearch = () => {
      document.getElementById("output").innerHTML = "";
      document.getElementById("reportContainer").innerHTML = "";
      updateState("in_progress")
  
      addAgentResponse({ output: "🤔 Thinking about research questions for the task..." });
  
      listenToSockEvents();
    };
  
    const listenToSockEvents = () => {
      const { protocol, host, pathname } = window.location;
      const ws_uri = `${protocol === 'https:' ? 'wss:' : 'ws:'}//${host}${pathname}ws`;
      const converter = new showdown.Converter();
      const socket = new WebSocket(ws_uri);
  
      socket.onmessage = (event) => {
        const data = JSON.parse(event.data);
        if (data.type === 'logs') {
          addAgentResponse(data);
        } else if (data.type === 'report') {
          writeReport(data, converter);
        } else if (data.type === 'path') {
          updateState("finished")
          updateDownloadLink(data);
        }
      };
  
      socket.onopen = (event) => {
        const task = document.querySelector('input[name="task"]').value;
        const report_type = document.querySelector('select[name="report_type"]').value;
        const agent = document.querySelector('input[name="agent"]:checked').value;
  
        const requestData = {
          task: task,
          report_type: report_type,
          agent: agent,
        };
  
        socket.send(`start ${JSON.stringify(requestData)}`);
      };
    };
  
    const addAgentResponse = (data) => {
      const output = document.getElementById("output");
      output.innerHTML += '<div class="agent_response">' + data.output + '</div>';
      output.scrollTop = output.scrollHeight;
      output.style.display = "block";
      updateScroll();
    };
  
    const writeReport = (data, converter) => {
      const reportContainer = document.getElementById("reportContainer");
      const markdownOutput = converter.makeHtml(data.output);
      reportContainer.innerHTML += markdownOutput;
      updateScroll();
    };
  
    const updateDownloadLink = (data) => {
      const pdf_path = data.output.pdf;
      const docx_path = data.output.docx;
      document.getElementById("downloadLink").setAttribute("href", pdf_path);
      document.getElementById("downloadLinkWord").setAttribute("href", docx_path);
    };
  
    const updateScroll = () => {
      window.scrollTo(0, document.body.scrollHeight);
    };
  
    const copyToClipboard = () => {
      const textarea = document.createElement('textarea');
      textarea.id = 'temp_element';
      textarea.style.height = 0;
      document.body.appendChild(textarea);
      textarea.value = document.getElementById('reportContainer').innerText;
      const selector = document.querySelector('#temp_element');
      selector.select();
      document.execCommand('copy');
      document.body.removeChild(textarea);
    };

    const updateState = (state) => {
      var status = "";
      switch (state) {
        case "in_progress":
          status = "Research in progress..."
          setReportActionsStatus("disabled");
          break;
        case "finished":
          status = "Research finished!"
          setReportActionsStatus("enabled");
          break;
        case "error":
          status = "Research failed!"
          setReportActionsStatus("disabled");
          break;
        case "initial":
          status = ""
          setReportActionsStatus("hidden");
          break;
        default:
          setReportActionsStatus("disabled");
      }
      document.getElementById("status").innerHTML = status;
      if (document.getElementById("status").innerHTML == "") {
        document.getElementById("status").style.display = "none";
      } else {
        document.getElementById("status").style.display = "block";
      }
    }

    /**
     * Shows or hides the download and copy buttons
     * @param {str} status Kind of hacky. Takes "enabled", "disabled", or "hidden". "Hidden is same as disabled but also hides the div"
     */
    const setReportActionsStatus = (status) => {
      const reportActions = document.getElementById("reportActions");
      // Disable everything in reportActions until research is finished

      if (status == "enabled") {
        reportActions.querySelectorAll("a").forEach((link) => {
          link.classList.remove("disabled");
          link.removeAttribute('onclick');
          reportActions.style.display = "block";
        });
      } else {
        reportActions.querySelectorAll("a").forEach((link) => {
          link.classList.add("disabled");
          link.setAttribute('onclick', "return false;");
        });
        if (status == "hidden") {
          reportActions.style.display = "none";
        }
      }
    }

    document.addEventListener("DOMContentLoaded", init);
    return {
      startResearch,
      copyToClipboard,
    };
  })();
```````




`../gpt-researcher/frontend/index.html`:

```````html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>GPT Researcher</title>
    <meta name="description" content="A research assistant powered by GPT-4">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="icon" href="./static/favicon.ico">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="/site/styles.css"/>
    <style>
        .avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
        }

        .agent-name {
            text-align: center;
        }

        .agent-item {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .agent-choices {
            display: none;
        }

        .btn-show {
            display: none;
        }
    </style>
</head>

<body>

<section class="landing">
    <div class="max-w-5xl mx-auto text-center">
        <h1 class="text-4xl font-extrabold mx-auto lg:text-7xl">
            Say Goodbye to <br>
            <span
                    style="background-image:linear-gradient(to right, #9867F0, #ED4E50); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">Hours
                    of Research</span>
        </h1>
        <p class="max-w-5xl mx-auto text-gray-600 mt-8" style="font-size:20px">
            Say Hello to GPT Researcher, your AI mate for rapid insights and comprehensive research. GPT Researcher
            takes care of everything from accurate source gathering to organization of research results - all in one
            platform designed to make your research process a breeze.
        </p>
        <a href="#form" class="btn btn-primary">Get Started</a>
    </div>
</section>

<main class="container" id="form">
    <div class="agent-item"><img src="/static/defaultAgentAvatar.JPG" class="avatar"
                                                alt="Auto Agent"></div>
    <form method="POST" class="mt-3" onsubmit="GPTResearcher.startResearch(); return false;">
        <div class="form-group">
            <label for="task" class="agent-question">What would you like me to research next?</label>
            <input type="text" id="task" name="task" class="form-control" required>
            <input type="radio" name="agent" id="autoAgent" value="Auto Agent" checked hidden>
        </div>
        <div class="form-group">
            <div class="row">


            </div>
            <button type="button" id="btnShowAuto" class="btn btn-secondary mt-3 btn-show">Auto Agent</button>
        </div>
        <div class="form-group">
            <label for="report_type" class="agent-question">What type of report would you like me to generate?</label>
            <select name="report_type" class="form-control" required>
                <option value="research_report">Summary - Short and fast (~2 min)</option>
                <option value="detailed_report">Detailed - In depth and longer (~5 min)</option>
                <option value="resource_report">Resource Report</option>
            </select>
        </div>
        <div class="form-group">
</div>
        <input type="submit" value="Research" class="btn btn-primary button-padding">
    </form>

    <div class="margin-div">
        <h2>Agent Output</h2>
        <p class="mt-2 text-left" style="font-size: 0.8rem;">An agent tailored specifically to your task
                        will be generated to provide the most precise and relevant research results.</p>
        <div id="output"></div>
    </div>
    <div class="margin-div">
        <h2>Research Report</h2>
        <div id="reportContainer"></div>
        <div id="reportActions">
            <div class="alert alert-info" role="alert" id="status"></div>
            <a id="copyToClipboard" onclick="GPTResearcher.copyToClipboard()" class="btn btn-secondary mt-3" style="margin-right: 10px;">Copy to clipboard</a>
            <a id="downloadLink" href="#" class="btn btn-secondary mt-3" style="margin-right: 10px;" target="_blank">Download as PDF</a>
            <a id="downloadLinkWord" href="#" class="btn btn-secondary mt-3" target="_blank">Download as Docx</a>
        </div>
    </div>
</main>

<footer>
    <p>GPT Researcher &copy; 2024 | <a target="_blank" href="https://github.com/assafelovic/gpt-researcher">GitHub
        Page</a></p>
</footer>

<script src="https://cdnjs.cloudflare.com/ajax/libs/showdown/1.9.1/showdown.min.js"></script>
<script src="/site/scripts.js"></script>
<script>
    // const btnChoose = document.getElementById('btnChoose');
    const btnShowAuto = document.getElementById('btnShowAuto');
    const autoAgentDiv = document.getElementById('autoAgentDiv');
    const agentChoices = document.getElementsByClassName('agent-choices');

    /**
    btnChoose.addEventListener('click', function () {
        btnShowAuto.style.display = 'inline-block';
        btnChoose.style.display = 'none';
        autoAgentDiv.style.display = 'none';
        agentChoices[0].style.display = 'flex';
    });
    **/

    btnShowAuto.addEventListener('click', function () {
        btnShowAuto.style.display = 'none';
        btnChoose.style.display = 'inline-block';
        autoAgentDiv.style.display = 'flex';
        agentChoices[0].style.display = 'none';
    });
</script>
</body>

</html>

```````




`../gpt-researcher/frontend/styles.css`:

```````css
@keyframes gradientBG {
    0% {background-position: 0% 50%;}
    50% {background-position: 100% 50%;}
    100% {background-position: 0% 50%;}
}

body {
    font-family: 'Montserrat', sans-serif;
    color: #fff;
    line-height: 1.6;
    background-size: 200% 200%;
    background-image: linear-gradient(45deg, #151A2D, #2D284D, #151A2D);
    animation: gradientBG 10s ease infinite;
}

.landing {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    text-align: center;
}

.landing h1 {
    font-size: 3.5rem;
    font-weight: 700;
    margin-bottom: 2rem;
}

.landing p {
    font-size: 1.5rem;
    font-weight: 400;
    max-width: 500px;
    margin: auto;
    margin-bottom: 2rem;
}

.container {
    max-width: 900px;
    margin: auto;
    padding: 20px;
    background-color: rgba(255, 255, 255, 0.1);
    border-radius: 12px;
    box-shadow: 0px 10px 25px rgba(0, 0, 0, 0.1);
    transition: all .3s ease-in-out;
    margin-bottom: 180px;
}

.container:hover {
    transform: scale(1.01);
    box-shadow: 0px 15px 30px rgba(0, 0, 0, 0.2);
}

input, select, #output, #reportContainer {
    background-color: rgba(255,255,255,0.1);
    border: none;
    color: #fff;
    transition: all .3s ease-in-out;
}

input:hover, input:focus, select:hover, select:focus {
    background-color: #dfe4ea;
    border: 1px solid rgba(255, 255, 255, 0.5);
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease-in-out;
}

.btn-primary {
    background: linear-gradient(to right, #0062cc, #007bff);
    border: none;
    transition: all .3s ease-in-out;
}

.btn-secondary {
    background: linear-gradient(to right, #6c757d, #6c757d);
    border: none;
    transition: all .3s ease-in-out;
}

.btn:hover {
    opacity: 0.8;
    transform: scale(1.1);
    box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.3);
}

.agent_question {
    font-size: 1.2rem;
    font-weight: 500;
    margin-bottom: 0.5rem;
}

footer {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    background: linear-gradient(to right, #151A2D, #111827);
    color: white;
    text-align: center;
    padding: 10px 0;
}

.margin-div {
    margin-top: 20px;
    margin-bottom: 20px;
    padding: 10px;
}

.agent_response {
    background-color: #747d8c;
    margin: 10px;
    padding: 10px;
    border-radius: 12px;
}

#output {
    height: 300px;
    font-family: 'Times New Roman', Times, , "Courier New", serif;
    overflow: auto;
    padding: 10px;
    margin-bottom: 10px;
    margin-top: 10px;
}

#reportContainer {
    background-color: rgba(255,255,255,0.1);
    border: none;
    color: #fff;
    transition: all .3s ease-in-out;
    padding: 10px;
    border-radius: 12px;
}

```````




`../gpt-researcher/frontend/pdf_styles.css`:

```````css
body {
    font-family: 'Libre Baskerville', serif;
    font-size: 12pt; /* standard size for academic papers */
    line-height: 1.6; /* for readability */
    color: #333; /* softer on the eyes than black */
    background-color: #fff; /* white background */
    margin: 0;
    padding: 0;
}

h1, h2, h3, h4, h5, h6 {
    font-family: 'Libre Baskerville', serif;
    color: #000; /* darker than the body text */
    margin-top: 1em; /* space above headers */
}

h1 {
    font-size: 2em; /* make h1 twice the size of the body text */
}

h2 {
    font-size: 1.5em;
}

/* Add some space between paragraphs */
p {
    margin-bottom: 1em;
}

/* Style for blockquotes, often used in academic papers */
blockquote {
    font-style: italic;
    margin: 1em 0;
    padding: 1em;
    background-color: #f9f9f9; /* a light grey background */
}

/* You might want to style tables, figures, etc. too */
table {
    border-collapse: collapse;
    width: 100%;
}

table, th, td {
    border: 1px solid #ddd;
    text-align: left;
    padding: 8px;
}

th {
    background-color: #f2f2f2;
    color: black;
}
```````




`../gpt-researcher/docker-compose.yml`:

```````yml
version: '3'
services:
  gpt-researcher:
    image: assafelovic/gpt-researcher
    build: ./
    environment: 
      OPENAI_API_KEY: ${OPENAI_API_KEY}
      TAVILY_API_KEY: ${TAVILY_API_KEY}
    ports:
      - 8000:8000
```````




`../gpt-researcher/CONTRIBUTING.md`:

```````md
# Contributing to GPT Researcher
First off, we'd like to welcome and thank you for your interest and effort in contributing to our open source project ❤️. Contributions of all forms are welcome, from new features and bug fixes, to documentation and more. 

We are on a mission to build the #1 AI agent for comprehensive, unbiased, and factual research online. And we need your support to achieve this grand vision. 

Please take a moment to review this document in order to make the contribution process easy and effective for everyone involved.

## Reporting Issues

If you come across any issue or have an idea for an improvement, don't hesitate to create an issue on GitHub. Describe your problem in sufficient detail, providing as much relevant information as possible. This way, we can reproduce the issue before attempting to fix it or respond appropriately.

## Contributing Code

1. **Fork the repository and create your branch from `master`.** 
If it's not an urgent bug fix, you should branch from `master` and work on the feature or fix in there.

2. **Conduct your changes.**
Make your changes following best practices for coding in the project's language. 

3. **Test your changes.**
Make sure your changes pass all the tests if there are any. If the project doesn't have automated testing infrastructure, test your changes manually to confirm they behave as expected.

4. **Follow the coding style.**
Ensure your code adheres to the coding conventions used throughout the project, that includes indentation, accurate comments, etc.

5. **Commit your changes.**
Make your git commits informative and concise. This is very helpful for others when they look at the git log.

6. **Push to your fork and submit a pull request.**
When your work is ready and passes tests, push your branch to your fork of the repository and submit a pull request from there.

7. **Pat your back and wait for the review.**
Your work is done, congratulations! Now sit tight. The project maintainers will review your submission as soon as possible. They might suggest changes or ask for improvements. Both constructive conversation and patience are key to the collaboration process.


## Documentation

If you would like to contribute to the project's documentation, please follow the same steps: fork the repository, make your changes, test them, and submit a pull request. 

Documentation is a vital part of any software. It's not just about having good code. Ensuring that the users and contributors understand what's going on, how to use the software or how to contribute, is crucial.

We're grateful for all our contributors, and we look forward to building the world's leading AI research agent hand-in-hand with you. Let's harness the power of Open Source and AI to change the world together!
```````




`../gpt-researcher/setup.py`:

```````py
from setuptools import find_packages, setup

with open(r"README.md", "r", encoding="utf-8") as f:
    long_description = f.read()

with open("requirements.txt", "r") as f:
    reqs = [line.strip() for line in f if ('selenium' not in line and 'webdriver' not in line)]

setup(
    name="gpt-researcher",
    version="0.2.6",
    description="GPT Researcher is an autonomous agent designed for comprehensive online research on a variety of tasks.",
    package_dir={'gpt_researcher': 'gpt_researcher'},
    packages=find_packages(),
    long_description=long_description,
    long_description_content_type="text/markdown",
    url="https://github.com/assafelovic/gpt-researcher",
    author="Assaf Elovic",
    author_email="assaf.elovic@gmail.com",
    license="MIT",
    classifiers=[
        "License :: OSI Approved :: MIT License",
        "Intended Audience :: Developers",
        "Intended Audience :: Education",
        "Intended Audience :: Science/Research",
        "Programming Language :: Python :: 3.11",
        "Programming Language :: Python :: 3.12",
        "Topic :: Scientific/Engineering :: Artificial Intelligence",
    ],
    install_requires=reqs,


)
```````




`../gpt-researcher/README.md`:

```````md
# 🔎 GPT Researcher
[![Official Website](https://img.shields.io/badge/Official%20Website-gptr.dev-blue?style=for-the-badge&logo=world&logoColor=white)](https://gptr.dev)
[![Discord Follow](https://dcbadge.vercel.app/api/server/2pFkc83fRq?style=for-the-badge)](https://discord.com/invite/2pFkc83fRq)

[![GitHub Repo stars](https://img.shields.io/github/stars/assafelovic/gpt-researcher?style=social)](https://github.com/assafelovic/gpt-researcher)
[![Twitter Follow](https://img.shields.io/twitter/follow/assaf_elovic?style=social)](https://twitter.com/assaf_elovic)
[![PyPI version](https://badge.fury.io/py/gpt-researcher.svg)](https://badge.fury.io/py/gpt-researcher)

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/assafelovic/gpt-researcher?style=for-the-badge&color=orange

-  [English](README.md)
-  [中文](README-zh_CN.md)

**GPT Researcher is an autonomous agent designed for comprehensive online research on a variety of tasks.** 

The agent can produce detailed, factual and unbiased research reports, with customization options for focusing on relevant resources, outlines, and lessons. Inspired by the recent [Plan-and-Solve](https://arxiv.org/abs/2305.04091) and [RAG](https://arxiv.org/abs/2005.11401) papers, GPT Researcher addresses issues of speed, determinism and reliability, offering a more stable performance and increased speed through parallelized agent work, as opposed to synchronous operations.

**Our mission is to empower individuals and organizations with accurate, unbiased, and factual information by leveraging the power of AI.**

## Why GPT Researcher?

- To form objective conclusions for manual research tasks can take time, sometimes weeks to find the right resources and information.
- Current LLMs are trained on past and outdated information, with heavy risks of hallucinations, making them almost irrelevant for research tasks.
- Services that enable web search (such as ChatGPT + Web Plugin), only consider limited sources and content that in some cases result in superficial and biased answers.
- Using only a selection of web sources can create bias in determining the right conclusions for research tasks. 

## Architecture
The main idea is to run "planner" and "execution" agents, whereas the planner generates questions to research, and the execution agents seek the most related information based on each generated research question. Finally, the planner filters and aggregates all related information and creates a research report. <br /> <br /> 
The agents leverage both gpt3.5-turbo and gpt-4-turbo (128K context) to complete a research task. We optimize for costs using each only when necessary. **The average research task takes around 3 minutes to complete, and costs ~$0.1.**

<div align="center">
<img align="center" height="500" src="https://cowriter-images.s3.amazonaws.com/architecture.png">
</div>


More specifically:
* Create a domain specific agent based on research query or task.
* Generate a set of research questions that together form an objective opinion on any given task. 
* For each research question, trigger a crawler agent that scrapes online resources for information relevant to the given task.
* For each scraped resources, summarize based on relevant information and keep track of its sources.
* Finally, filter and aggregate all summarized sources and generate a final research report.

## Demo
https://github.com/assafelovic/gpt-researcher/assets/13554167/dd6cf08f-b31e-40c6-9907-1915f52a7110


## Tutorials
 - [How it Works](https://docs.tavily.com/blog/building-gpt-researcher)
 - [How to Install](https://www.loom.com/share/04ebffb6ed2a4520a27c3e3addcdde20?sid=da1848e8-b1f1-42d1-93c3-5b0b9c3b24ea)
 - [Live Demo](https://www.loom.com/share/6a3385db4e8747a1913dd85a7834846f?sid=a740fd5b-2aa3-457e-8fb7-86976f59f9b8)

## Features
- 📝 Generate research, outlines, resources and lessons reports
- 📜 Can generate long and detailed research reports (over 2K words)
- 🌐 Aggregates over 20 web sources per research to form objective and factual conclusions
- 🖥️ Includes an easy-to-use web interface (HTML/CSS/JS)
- 🔍 Scrapes web sources with javascript support
- 📂 Keeps track and context of visited and used web sources
- 📄 Export research reports to PDF, Word and more...

## 📖 Documentation

Please see [here](https://docs.tavily.com/docs/gpt-researcher/getting-started) for full documentation on:

- Getting started (installation, setting up the environment, simple examples)
- Customization and configuration
- How-To examples (demos, integrations, docker support)
- Reference (full API docs)

## ⚙️ Getting Started
> **Step 0** - Install Python 3.11 or later. [See here](https://www.tutorialsteacher.com/python/install-python) for a step-by-step guide.

> **Step 1** - Download the project and navigate to its directory

```bash
git clone https://github.com/assafelovic/gpt-researcher.git
cd gpt-researcher
```

> **Step 3** - Set up API keys using two methods: exporting them directly or storing them in a `.env` file.

For Linux/Windows temporary setup, use the export method:

```bash
export OPENAI_API_KEY={Your OpenAI API Key here}
export TAVILY_API_KEY={Your Tavily API Key here}
```

For a more permanent setup, create a `.env` file in the current `gpt-researcher` directory and input the keys as follows:

```bash
OPENAI_API_KEY={Your OpenAI API Key here}
TAVILY_API_KEY={Your Tavily API Key here}
```

- **For LLM, we recommend [OpenAI GPT](https://platform.openai.com/docs/guides/gpt)**, but you can use any other LLM model (including open sources) supported by [Langchain Adapter](https://python.langchain.com/docs/guides/adapters/openai), simply change the llm model and provider in config/config.py. 
- **For web search API, we recommend [Tavily Search API](https://app.tavily.com)**, but you can also refer to other search APIs of your choice by changing the search provider in config/config.py to `"duckduckgo"`, `"googleAPI"`, `"bing"`, `"googleSerp"`, `"searx"` and more. Then add the corresponding env API key as seen in the config.py file.

### Quickstart

> **Step 1** - Install dependencies

```bash
pip install -r requirements.txt
```

> **Step 2** - Run the agent with FastAPI

```bash
uvicorn main:app --reload
```

> **Step 3** - Go to http://localhost:8000 on any browser and enjoy researching!

<br />

**To learn how to get started with [Docker](https://docs.tavily.com/docs/gpt-researcher/getting-started#try-it-with-docker), [Poetry](https://docs.tavily.com/docs/gpt-researcher/getting-started#poetry) or a [virtual environment](https://docs.tavily.com/docs/gpt-researcher/getting-started#virtual-environment) check out the [documentation](https://docs.tavily.com/docs/gpt-researcher/getting-started) page.**

## 🚀 Contributing
We highly welcome contributions! Please check out [contributing](CONTRIBUTING.md) if you're interested.

Please check out our [roadmap](https://trello.com/b/3O7KBePw/gpt-researcher-roadmap) page and reach out to us via our [Discord community](https://discord.gg/2pFkc83fRq) if you're interested in joining our mission.

## ✉️ Support / Contact us
- [Community Discord](https://discord.gg/spBgZmm3Xe)
- Our email: assafelovic@gmail.com

## 🛡 Disclaimer

This project, GPT Researcher, is an experimental application and is provided "as-is" without any warranty, express or implied. We are sharing codes for academic purposes under the MIT license. Nothing herein is academic advice, and NOT a recommendation to use in academic or research papers.

Our view on unbiased research claims:
1. The main goal of GPT Researcher is to reduce incorrect and biased facts. How? We assume that the more sites we scrape the less chances of incorrect data. By scraping over 20 sites per research, and choosing the most frequent information, the chances that they are all wrong is extremely low.
2. We do not aim to eliminate biases; we aim to reduce it as much as possible. **We are here as a community to figure out the most effective human/llm interactions.**
3. In research, people also tend towards biases as most have already opinions on the topics they research about. This tool scrapes many opinions and will evenly explain diverse views that a biased person would never have read.

**Please note that the use of the GPT-4 language model can be expensive due to its token usage.** By utilizing this project, you acknowledge that you are responsible for monitoring and managing your own token usage and the associated costs. It is highly recommended to check your OpenAI API usage regularly and set up any necessary limits or alerts to prevent unexpected charges.

---

<p align="center">
<a href="https://star-history.com/#assafelovic/gpt-researcher">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=assafelovic/gpt-researcher&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=assafelovic/gpt-researcher&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=assafelovic/gpt-researcher&type=Date" />
  </picture>
</a>
</p>

```````




`../gpt-researcher/CODE_OF_CONDUCT.md`:

```````md
# Contributor Covenant Code of Conduct

## Our Pledge

We as members, contributors, and leaders pledge to make participation in our
community a harassment-free experience for everyone, regardless of age, body
size, visible or invisible disability, ethnicity, sex characteristics, gender
identity and expression, level of experience, education, socio-economic status,
nationality, personal appearance, race, religion, or sexual identity
and orientation.

We pledge to act and interact in ways that contribute to an open, welcoming,
diverse, inclusive, and healthy community.

## Our Standards

Examples of behavior that contributes to a positive environment for our
community include:

* Demonstrating empathy and kindness toward other people
* Being respectful of differing opinions, viewpoints, and experiences
* Giving and gracefully accepting constructive feedback
* Accepting responsibility and apologizing to those affected by our mistakes,
  and learning from the experience
* Focusing on what is best not just for us as individuals, but for the
  overall community

Examples of unacceptable behavior include:

* The use of sexualized language or imagery, and sexual attention or
  advances of any kind
* Trolling, insulting or derogatory comments, and personal or political attacks
* Public or private harassment
* Publishing others' private information, such as a physical or email
  address, without their explicit permission
* Other conduct which could reasonably be considered inappropriate in a
  professional setting

## Enforcement Responsibilities

Community leaders are responsible for clarifying and enforcing our standards of
acceptable behavior and will take appropriate and fair corrective action in
response to any behavior that they deem inappropriate, threatening, offensive,
or harmful.

Community leaders have the right and responsibility to remove, edit, or reject
comments, commits, code, wiki edits, issues, and other contributions that are
not aligned to this Code of Conduct, and will communicate reasons for moderation
decisions when appropriate.

## Scope

This Code of Conduct applies within all community spaces, and also applies when
an individual is officially representing the community in public spaces.
Examples of representing our community include using an official e-mail address,
posting via an official social media account, or acting as an appointed
representative at an online or offline event.

## Enforcement

Instances of abusive, harassing, or otherwise unacceptable behavior may be
reported to the community leaders responsible for enforcement at
Assaf.elovic@gmail.com.
All complaints will be reviewed and investigated promptly and fairly.

All community leaders are obligated to respect the privacy and security of the
reporter of any incident.

## Enforcement Guidelines

Community leaders will follow these Community Impact Guidelines in determining
the consequences for any action they deem in violation of this Code of Conduct:

### 1. Correction

**Community Impact**: Use of inappropriate language or other behavior deemed
unprofessional or unwelcome in the community.

**Consequence**: A private, written warning from community leaders, providing
clarity around the nature of the violation and an explanation of why the
behavior was inappropriate. A public apology may be requested.

### 2. Warning

**Community Impact**: A violation through a single incident or series
of actions.

**Consequence**: A warning with consequences for continued behavior. No
interaction with the people involved, including unsolicited interaction with
those enforcing the Code of Conduct, for a specified period of time. This
includes avoiding interactions in community spaces as well as external channels
like social media. Violating these terms may lead to a temporary or
permanent ban.

### 3. Temporary Ban

**Community Impact**: A serious violation of community standards, including
sustained inappropriate behavior.

**Consequence**: A temporary ban from any sort of interaction or public
communication with the community for a specified period of time. No public or
private interaction with the people involved, including unsolicited interaction
with those enforcing the Code of Conduct, is allowed during this period.
Violating these terms may lead to a permanent ban.

### 4. Permanent Ban

**Community Impact**: Demonstrating a pattern of violation of community
standards, including sustained inappropriate behavior,  harassment of an
individual, or aggression toward or disparagement of classes of individuals.

**Consequence**: A permanent ban from any sort of public interaction within
the community.

## Attribution

This Code of Conduct is adapted from the [Contributor Covenant][homepage],
version 2.0, available at
https://www.contributor-covenant.org/version/2/0/code_of_conduct.html.

Community Impact Guidelines were inspired by [Mozilla's code of conduct
enforcement ladder](https://github.com/mozilla/diversity).

[homepage]: https://www.contributor-covenant.org

For answers to common questions about this code of conduct, see the FAQ at
https://www.contributor-covenant.org/faq. Translations are available at
https://www.contributor-covenant.org/translations.

```````




`../gpt-researcher/pyproject.toml`:

```````toml
[tool.poetry]
name = "gpt-researcher"
version = "0.0.5"
description = "GPT Researcher is an autonomous agent designed for comprehensive online research on a variety of tasks."
authors = ["Tavily <support@tavily.com>"]
license = "MIT"
readme = "README.md"

[tool.poetry.dependencies]
python = ">=3.10,<4.0"
beautifulsoup4 = ">=4.12.2"
colorama = ">=0.4.6"
duckduckgo_search = ">=4.1.1"
md2pdf = ">=1.0.1"
openai = ">=1.3.3"
playwright = ">=1.39.0"
python-dotenv = ">=1.0.0"
pyyaml = ">=6.0.1"
selenium = ">=4.15.2"
webdriver-manager = ">=4.0.1"
uvicorn = ">=0.24.0.post1"
pydantic = ">=2.5.1"
fastapi = ">=0.104.1"
python-multipart = ">=0.0.6"
markdown = ">=3.5.1"
langchain = ">=0.0.350"
tavily-python = ">=0.2.8"
permchain = ">=0.0.6"
arxiv = ">=2.0.0"
PyMuPDF = ">=1.23.6"
requests = ">=2.31.0"
jinja2 = ">=3.1.2"
aiofiles = ">=23.2.1"
newspaper3k = ">=0.2.8"
langchain_community = ">=0.0.28"
SQLAlchemy = ">=2.0.28"
mistune = "^3.0.2"
htmldocx = "^0.0.6"
python-docx = "^1.1.0"
langchain-openai = "^0.1.0"
langchain-google-genai = "^0.0.11"
lxml = { version = ">=4.9.2", extras = ["html_clean"] }

[build-system]
requires = ["poetry-core"]
build-backend = "poetry.core.masonry.api"

```````




`../gpt-researcher/Dockerfile`:

```````
FROM python:3.11.4-slim-bullseye as install-browser

RUN apt-get update \
    && apt-get satisfy -y \
    "chromium, chromium-driver (>= 115.0)" \
    && chromium --version && chromedriver --version

RUN apt-get install -y firefox-esr wget \
    && wget https://github.com/mozilla/geckodriver/releases/download/v0.33.0/geckodriver-v0.33.0-linux64.tar.gz \
    && tar -xvzf geckodriver* \
    && chmod +x geckodriver \
    && mv geckodriver /usr/local/bin/

FROM install-browser as gpt-researcher-install

ENV PIP_ROOT_USER_ACTION=ignore

RUN mkdir /usr/src/app
WORKDIR /usr/src/app

COPY ./requirements.txt ./requirements.txt
RUN pip install -r requirements.txt

FROM gpt-researcher-install AS gpt-researcher

RUN useradd -ms /bin/bash gpt-researcher \
    && chown -R gpt-researcher:gpt-researcher /usr/src/app

USER gpt-researcher

COPY --chown=gpt-researcher:gpt-researcher ./ ./

EXPOSE 8000
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]


```````




`../gpt-researcher/cli.py`:

```````py
"""
Provides a command line interface for the GPTResearcher class.

Usage:

```shell
python cli.py "<query>" --report_type <report_type>
```

"""
import asyncio
import argparse
from argparse import RawTextHelpFormatter
from uuid import uuid4

from dotenv import load_dotenv

from gpt_researcher import GPTResearcher
from gpt_researcher.utils.enum import ReportType

# =============================================================================
# CLI
# =============================================================================

cli = argparse.ArgumentParser(
    description="Generate a research report.",
    # Enables the use of newlines in the help message
    formatter_class=RawTextHelpFormatter)

# =====================================
# Arg: Query
# =====================================

cli.add_argument(
    # Position 0 argument
    "query",
    type=str,
    help="The query to conduct research on.")

# =====================================
# Arg: Report Type
# =====================================

choices = [report_type.value for report_type in ReportType]

report_type_descriptions = {
    ReportType.ResearchReport.value: "Summary - Short and fast (~2 min)",
    ReportType.DetailedReport.value: "Detailed - In depth and longer (~5 min)",
    ReportType.ResourceReport.value: "",
    ReportType.OutlineReport.value: "",
    ReportType.CustomReport.value: "",
    ReportType.SubtopicReport.value: ""
}

cli.add_argument(
    "--report_type",
    type=str,
    help="The type of report to generate. Options:\n" + "\n".join(
        f"  {choice}: {report_type_descriptions[choice]}" for choice in choices
    ),
    # Deserialize ReportType as a List of strings:
    choices=choices,
    required=True)

# =============================================================================
# Main
# =============================================================================


async def main(args):
    """ 
    Conduct research on the given query, generate the report, and write
    it as a markdown file to the output directory.
    """
    researcher = GPTResearcher(
        query=args.query,
        report_type=args.report_type)

    await researcher.conduct_research()

    report = await researcher.write_report()

    # Write the report to a file
    artifact_filepath = f"outputs/{uuid4()}.md"
    with open(artifact_filepath, "w") as f:
        f.write(report)

    print(f"Report written to '{artifact_filepath}'")

if __name__ == "__main__":
    load_dotenv()
    args = cli.parse_args()
    asyncio.run(main(args))

```````




`../gpt-researcher/scraping/processing/text.py`:

```````py
"""Text processing functions"""
import urllib
from typing import Dict, Generator, Optional

from selenium.webdriver.remote.webdriver import WebDriver

from config import Config
from gpt_researcher_old.retriever.llm_utils import create_chat_completion
import os
from md2pdf.core import md2pdf


def split_text(text: str, max_length: int = 8192) -> Generator[str, None, None]:
    """Split text into chunks of a maximum length

    Args:
        text (str): The text to split
        max_length (int, optional): The maximum length of each chunk. Defaults to 8192.

    Yields:
        str: The next chunk of text

    Raises:
        ValueError: If the text is longer than the maximum length
    """
    paragraphs = text.split("\n")
    current_length = 0
    current_chunk = []

    for paragraph in paragraphs:
        if current_length + len(paragraph) + 1 <= max_length:
            current_chunk.append(paragraph)
            current_length += len(paragraph) + 1
        else:
            yield "\n".join(current_chunk)
            current_chunk = [paragraph]
            current_length = len(paragraph) + 1

    if current_chunk:
        yield "\n".join(current_chunk)


def summarize_text(
    fast_llm_model: str, summary_token_limit: int, llm_provider: str, url: str, text: str, question: str, driver: Optional[WebDriver] = None
) -> str:
    """Summarize text using the OpenAI API

    Args:
        fast_llm_model (str): The fast LLM model e.g gpt3.5-turbo-16k
        summary_token_limit (int): The summary token limit
        llm_provider (str): The llm provider
        url (str): The url of the text
        text (str): The text to summarize
        question (str): The question to ask the model
        driver (WebDriver): The webdriver to use to scroll the page

    Returns:
        str: The summary of the text
    """
    if not text:
        return "Error: No text to summarize"

    summaries = []
    chunks = list(split_text(text))
    scroll_ratio = 1 / len(chunks)

    print(f"Summarizing url: {url} with total chunks: {len(chunks)}")
    for i, chunk in enumerate(chunks):
        if driver:
            scroll_to_percentage(driver, scroll_ratio * i)

        #memory_to_add = f"Source: {url}\n" f"Raw content part#{i + 1}: {chunk}"

        #MEMORY.add_documents([Document(page_content=memory_to_add)])

        messages = [create_message(chunk, question)]

        summary = create_chat_completion(
            model=fast_llm_model,
            messages=messages,
            max_tokens=summary_token_limit,
            llm_provider=llm_provider
        )
        summaries.append(summary)
        #memory_to_add = f"Source: {url}\n" f"Content summary part#{i + 1}: {summary}"

        #MEMORY.add_documents([Document(page_content=memory_to_add)])

    combined_summary = "\n".join(summaries)
    messages = [create_message(combined_summary, question)]

    final_summary = create_chat_completion(
        model=fast_llm_model,
        messages=messages,
        max_tokens=summary_token_limit,
        llm_provider=llm_provider,
    )
    print("Final summary length: ", len(combined_summary))
    print(final_summary)

    return final_summary


def scroll_to_percentage(driver: WebDriver, ratio: float) -> None:
    """Scroll to a percentage of the page

    Args:
        driver (WebDriver): The webdriver to use
        ratio (float): The percentage to scroll to

    Raises:
        ValueError: If the ratio is not between 0 and 1
    """
    if ratio < 0 or ratio > 1:
        raise ValueError("Percentage should be between 0 and 1")
    driver.execute_script(f"window.scrollTo(0, document.body.scrollHeight * {ratio});")


def create_message(chunk: str, question: str) -> Dict[str, str]:
    """Create a message for the chat completion

    Args:
        chunk (str): The chunk of text to summarize
        question (str): The question to answer

    Returns:
        Dict[str, str]: The message to send to the chat completion
    """
    return {
        "role": "user",
        "content": f'"""{chunk}"""\n'
        f'Using the above text, summarize it based on the following task or query: "{question}".\n'
        f'If the query cannot be answered using the text, YOU MUST summarize the text in short.\n'
        f'Include all factual information such as numbers, stats, quotes, etc if available.',
    }

def write_to_file(filename: str, text: str) -> None:
    """Write text to a file

    Args:
        text (str): The text to write
        filename (str): The filename to write to
    """
    with open(filename, "w") as file:
        file.write(text)

async def write_md_to_pdf(task: str, path: str, text: str) -> None:
    file_path = f"{path}/{task}"
    write_to_file(f"{file_path}.md", text)
    md_to_pdf(f"{file_path}.md", f"{file_path}.pdf")
    print(f"{task} written to {file_path}.pdf")

    encoded_file_path = urllib.parse.quote(f"{file_path}.pdf")

    return encoded_file_path

def read_txt_files(directory):
    all_text = ''

    for filename in os.listdir(directory):
        if filename.endswith('.txt'):
            with open(os.path.join(directory, filename), 'r') as file:
                all_text += file.read() + '\n'

    return all_text


def md_to_pdf(input_file, output_file):
    md2pdf(output_file,
           md_content=None,
           md_file_path=input_file,
           css_file_path=None,
           base_url=None)

```````




`../gpt-researcher/scraping/processing/html.py`:

```````py
"""HTML processing functions"""
from __future__ import annotations

from bs4 import BeautifulSoup
from requests.compat import urljoin


def extract_hyperlinks(soup: BeautifulSoup, base_url: str) -> list[tuple[str, str]]:
    """Extract hyperlinks from a BeautifulSoup object

    Args:
        soup (BeautifulSoup): The BeautifulSoup object
        base_url (str): The base URL

    Returns:
        List[Tuple[str, str]]: The extracted hyperlinks
    """
    return [
        (link.text, urljoin(base_url, link["href"]))
        for link in soup.find_all("a", href=True)
    ]


def format_hyperlinks(hyperlinks: list[tuple[str, str]]) -> list[str]:
    """Format hyperlinks to be displayed to the user

    Args:
        hyperlinks (List[Tuple[str, str]]): The hyperlinks to format

    Returns:
        List[str]: The formatted hyperlinks
    """
    return [f"{link_text} ({link_url})" for link_text, link_url in hyperlinks]

```````




`../gpt-researcher/scraping/scrape_skills.py`:

```````py
from langchain.document_loaders import PyMuPDFLoader
from langchain.retrievers import ArxivRetriever


def scrape_pdf_with_pymupdf(url) -> str:
    """Scrape a pdf with pymupdf

    Args:
        url (str): The url of the pdf to scrape

    Returns:
        str: The text scraped from the pdf
    """
    loader = PyMuPDFLoader(url)
    doc = loader.load()
    return str(doc)


def scrape_pdf_with_arxiv(query) -> str:
    """Scrape a pdf with arxiv
    default document length of 70000 about ~15 pages or None for no limit

    Args:
        query (str): The query to search for

    Returns:
        str: The text scraped from the pdf
    """
    retriever = ArxivRetriever(load_max_docs=2, doc_content_chars_max=None)
    docs = retriever.get_relevant_documents(query=query)
    return docs[0].page_content
```````




`../gpt-researcher/scraping/web_scrape.py`:

```````py
"""Selenium web scraping module."""
from __future__ import annotations

import logging
import asyncio
from pathlib import Path
from sys import platform

from bs4 import BeautifulSoup
from selenium import webdriver
from selenium.webdriver.chrome.options import Options as ChromeOptions
from selenium.webdriver.common.by import By
from selenium.webdriver.firefox.options import Options as FirefoxOptions
from selenium.webdriver.remote.webdriver import WebDriver
from selenium.webdriver.safari.options import Options as SafariOptions
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.wait import WebDriverWait
from fastapi import WebSocket

from scraping import scrape_skills, processing as summary
from scraping.processing.html import extract_hyperlinks, format_hyperlinks

from concurrent.futures import ThreadPoolExecutor

from scraping.processing.text import summarize_text

executor = ThreadPoolExecutor()

FILE_DIR = Path(__file__).parent.parent


async def async_browse(
        selenium_web_browser: str,
        user_agent: str,
        fast_llm_model: str,
        summary_token_limit: str,
        llm_provider: str,
        url: str, question: str,
        websocket: WebSocket
) -> str:
    """Browse a website and return the answer and links to the user

    Args:
        selenium_web_browser (str): The web browser used for scraping
        user_agent (str): The user agent used when scraping
        url (str): The url of the website to browse
        question (str): The question asked by the user
        websocket (WebSocketManager): The websocket manager

    Returns:
        str: The answer and links to the user
    """
    loop = asyncio.get_event_loop()
    executor = ThreadPoolExecutor(max_workers=8)

    print(f"Scraping url {url} with question {question}")
    if websocket:
        await websocket.send_json(
            {
                "type": "logs",
                "output": f"🔎 Browsing the {url} for relevant about: {question}...",
            }
        )
    else:
        print(f"🔎 Browsing the {url} for relevant about: {question}...")

    try:
        driver, text = await loop.run_in_executor(
            executor, scrape_text_with_selenium, selenium_web_browser, user_agent, url
        )
        await loop.run_in_executor(executor, add_header, driver)
        summary_text = await loop.run_in_executor(
            executor, summarize_text, fast_llm_model, summary_token_limit, llm_provider, url, text, question, driver
        )
        if websocket:
            await websocket.send_json(
                {
                    "type": "logs",
                    "output": f"📝 Information gathered from url {url}: {summary_text}",
                }
            )
        else:
            print(f"📝 Information gathered from url {url}: {summary_text}")

        return f"Information gathered from url {url}: {summary_text}"
    except Exception as e:
        print(f"An error occurred while processing the url {url}: {e}")
        return f"Error processing the url {url}: {e}"


def browse_website(url: str, question: str) -> tuple[str, WebDriver]:
    """Browse a website and return the answer and links to the user

    Args:
        url (str): The url of the website to browse
        question (str): The question asked by the user

    Returns:
        Tuple[str, WebDriver]: The answer and links to the user and the webdriver
    """

    if not url:
        return "A URL was not specified, cancelling request to browse website.", None

    driver, text = scrape_text_with_selenium(url)
    add_header(driver)
    summary_text = summary.summarize_text(url, text, question, driver)

    links = scrape_links_with_selenium(driver, url)

    # Limit links to 5
    if len(links) > 5:
        links = links[:5]

    # write_to_file('research-{0}.txt'.format(url), summary_text + "\nSource Links: {0}\n\n".format(links))

    close_browser(driver)
    return f"Answer gathered from website: {summary_text} \n \n Links: {links}", driver


def scrape_text_with_selenium(selenium_web_browser: str, user_agent: str, url: str) -> tuple[WebDriver, str]:
    """Scrape text from a website using selenium

    Args:
        url (str): The url of the website to scrape
        selenium_web_browser (str): The web browser used to scrape
        user_agent (str): The user agent used when scraping

    Returns:
        Tuple[WebDriver, str]: The webdriver and the text scraped from the website
    """
    logging.getLogger("selenium").setLevel(logging.CRITICAL)

    options_available = {
        "chrome": ChromeOptions,
        "safari": SafariOptions,
        "firefox": FirefoxOptions,
    }

    options = options_available[selenium_web_browser]()
    options.add_argument(f"user-agent={user_agent}")
    options.add_argument("--headless")
    options.add_argument("--enable-javascript")

    if selenium_web_browser == "firefox":
        driver = webdriver.Firefox(options=options)
    elif selenium_web_browser == "safari":
        # Requires a bit more setup on the users end
        # See https://developer.apple.com/documentation/webkit/testing_with_webdriver_in_safari
        driver = webdriver.Safari(options=options)
    else:
        if platform == "linux" or platform == "linux2":
            options.add_argument("--disable-dev-shm-usage")
            options.add_argument("--remote-debugging-port=9222")
        options.add_argument("--no-sandbox")
        options.add_experimental_option("prefs", {"download_restrictions": 3})
        driver = webdriver.Chrome(options=options)

    print(f"scraping url {url}...")
    driver.get(url)

    WebDriverWait(driver, 10).until(
        EC.presence_of_element_located((By.TAG_NAME, "body"))
    )

    # check if url is a pdf or arxiv link
    if url.endswith(".pdf"):
        text = scrape_skills.scrape_pdf_with_pymupdf(url)
    elif "arxiv" in url:
        # parse the document number from the url
        doc_num = url.split("/")[-1]
        text = scrape_skills.scrape_pdf_with_arxiv(doc_num)
    else:
        # Get the HTML content directly from the browser's DOM
        page_source = driver.execute_script("return document.body.outerHTML;")
        soup = BeautifulSoup(page_source, "html.parser")

        for script in soup(["script", "style"]):
            script.extract()

        # text = soup.get_text()
        text = get_text(soup)

    lines = (line.strip() for line in text.splitlines())
    chunks = (phrase.strip() for line in lines for phrase in line.split("  "))
    text = "\n".join(chunk for chunk in chunks if chunk)
    return driver, text


def get_text(soup):
    """Get the text from the soup

    Args:
        soup (BeautifulSoup): The soup to get the text from

    Returns:
        str: The text from the soup
    """
    text = ""
    tags = ["h1", "h2", "h3", "h4", "h5", "p"]
    for element in soup.find_all(tags):  # Find all the <p> elements
        text += element.text + "\n\n"
    return text


def scrape_links_with_selenium(driver: WebDriver, url: str) -> list[str]:
    """Scrape links from a website using selenium

    Args:
        driver (WebDriver): The webdriver to use to scrape the links

    Returns:
        List[str]: The links scraped from the website
    """
    page_source = driver.page_source
    soup = BeautifulSoup(page_source, "html.parser")

    for script in soup(["script", "style"]):
        script.extract()

    hyperlinks = extract_hyperlinks(soup, url)

    return format_hyperlinks(hyperlinks)


def close_browser(driver: WebDriver) -> None:
    """Close the browser

    Args:
        driver (WebDriver): The webdriver to close

    Returns:
        None
    """
    driver.quit()


def add_header(driver: WebDriver) -> None:
    """Add a header to the website

    Args:
        driver (WebDriver): The webdriver to use to add the header

    Returns:
        None
    """
    driver.execute_script(open(f"{FILE_DIR}/js/overlay.js", "r").read())

```````




`../gpt-researcher/scraping/js/overlay.js`:

```````js
const overlay = document.createElement('div');
Object.assign(overlay.style, {
    position: 'fixed',
    zIndex: 999999,
    top: 0,
    left: 0,
    width: '100%',
    height: '100%',
    background: 'rgba(0, 0, 0, 0.7)',
    color: '#fff',
    fontSize: '24px',
    fontWeight: 'bold',
    display: 'flex',
    justifyContent: 'center',
    alignItems: 'center',
});
const textContent = document.createElement('div');
Object.assign(textContent.style, {
    textAlign: 'center',
});
textContent.textContent = 'Tavily AI: Analyzing Page';
overlay.appendChild(textContent);
document.body.append(overlay);
document.body.style.overflow = 'hidden';
let dotCount = 0;
setInterval(() => {
    textContent.textContent = 'Tavily AI: Analyzing Page' + '.'.repeat(dotCount);
    dotCount = (dotCount + 1) % 4;
}, 1000);

```````




`../gpt-researcher/requirements.txt`:

```````txt
# dependencies
beautifulsoup4
colorama
duckduckgo_search
md2pdf
playwright
openai
python-dotenv
pyyaml
selenium
webdriver-manager
uvicorn
pydantic
fastapi
python-multipart
markdown
langchain
tavily-python
arxiv
PyMuPDF
requests
jinja2
aiofiles
newspaper3k
langchain_community
SQLAlchemy
langchain-openai
mistune
python-docx
htmldocx
langchain-google-genai
lxml[html_clean]

```````




`../gpt-researcher/backend/websocket_manager.py`:

```````py
# connect any client to gpt-researcher using websocket
import asyncio
import datetime
from typing import Dict, List

from fastapi import WebSocket

from backend.report_type import BasicReport, DetailedReport

from gpt_researcher.utils.enum import ReportType


class WebSocketManager:
    """Manage websockets"""

    def __init__(self):
        """Initialize the WebSocketManager class."""
        self.active_connections: List[WebSocket] = []
        self.sender_tasks: Dict[WebSocket, asyncio.Task] = {}
        self.message_queues: Dict[WebSocket, asyncio.Queue] = {}

    async def start_sender(self, websocket: WebSocket):
        """Start the sender task."""
        queue = self.message_queues.get(websocket)
        if not queue:
            return

        while True:
            message = await queue.get()
            if websocket in self.active_connections:
                try:
                    await websocket.send_text(message)
                except:
                    break
            else:
                break

    async def connect(self, websocket: WebSocket):
        """Connect a websocket."""
        await websocket.accept()
        self.active_connections.append(websocket)
        self.message_queues[websocket] = asyncio.Queue()
        self.sender_tasks[websocket] = asyncio.create_task(
            self.start_sender(websocket))

    async def disconnect(self, websocket: WebSocket):
        """Disconnect a websocket."""
        if websocket in self.active_connections:
            self.active_connections.remove(websocket)
            self.sender_tasks[websocket].cancel()
            await self.message_queues[websocket].put(None)
            del self.sender_tasks[websocket]
            del self.message_queues[websocket]

    async def start_streaming(self, task, report_type, websocket):
        """Start streaming the output."""
        report = await run_agent(task, report_type, websocket)
        return report


async def run_agent(task, report_type, websocket):
    """Run the agent."""
    # measure time
    start_time = datetime.datetime.now()
    # add customized JSON config file path here
    config_path = ""
    # Instead of running the agent directly run it through the different report type classes
    if report_type == ReportType.DetailedReport.value:
        researcher = DetailedReport(query=task, source_urls=None, config_path=config_path, websocket=websocket)
    else:
        researcher = BasicReport(query=task, report_type=report_type,
                                 source_urls=None, config_path=config_path, websocket=websocket)

    report = await researcher.run()
    # measure time
    end_time = datetime.datetime.now()
    await websocket.send_json({"type": "logs", "output": f"\nTotal run time: {end_time - start_time}\n"})

    return report

```````




`../gpt-researcher/backend/server.py`:

```````py
from fastapi import FastAPI, Request, WebSocket, WebSocketDisconnect
from fastapi.staticfiles import StaticFiles
from fastapi.templating import Jinja2Templates
from pydantic import BaseModel
import json
import os
from backend.websocket_manager import WebSocketManager
from backend.utils import write_md_to_pdf, write_md_to_word


class ResearchRequest(BaseModel):
    task: str
    report_type: str
    agent: str


app = FastAPI()

app.mount("/site", StaticFiles(directory="./frontend"), name="site")
app.mount("/static", StaticFiles(directory="./frontend/static"), name="static")

templates = Jinja2Templates(directory="./frontend")

manager = WebSocketManager()


# Dynamic directory for outputs once first research is run
@app.on_event("startup")
def startup_event():
    if not os.path.isdir("outputs"):
        os.makedirs("outputs")
    app.mount("/outputs", StaticFiles(directory="outputs"), name="outputs")

@app.get("/")
async def read_root(request: Request):
    return templates.TemplateResponse('index.html', {"request": request, "report": None})


@app.websocket("/ws")
async def websocket_endpoint(websocket: WebSocket):
    await manager.connect(websocket)
    try:
        while True:
            data = await websocket.receive_text()
            if data.startswith("start"):
                json_data = json.loads(data[6:])
                task = json_data.get("task")
                report_type = json_data.get("report_type")
                if task and report_type:
                    report = await manager.start_streaming(task, report_type, websocket)
                    # Saving report as pdf
                    pdf_path = await write_md_to_pdf(report)
                    # Saving report as docx
                    docx_path = await write_md_to_word(report)
                    # Returning the path of saved report files
                    await websocket.send_json({"type": "path", "output": {"pdf": pdf_path, "docx": docx_path}})
                else:
                    print("Error: not enough parameters provided.")

    except WebSocketDisconnect:
        await manager.disconnect(websocket)


```````




`../gpt-researcher/backend/report_type/__init__.py`:

```````py
from .basic_report.basic_report import BasicReport
from .detailed_report.detailed_report import DetailedReport

__all__ = [
    "BasicReport",
    "DetailedReport"
]
```````




`../gpt-researcher/backend/report_type/detailed_report/detailed_report.py`:

```````py
import asyncio

from fastapi import WebSocket

from gpt_researcher.master.agent import GPTResearcher
from gpt_researcher.master.functions import (add_source_urls, extract_headers,
                                             table_of_contents)


class DetailedReport():
    def __init__(self, query: str, source_urls, config_path: str, websocket: WebSocket, subtopics=[]):
        self.query = query
        self.source_urls = source_urls
        self.config_path = config_path
        self.websocket = websocket
        self.subtopics = subtopics
        
        # A parent task assistant. Adding research_report as default
        self.main_task_assistant = GPTResearcher(self.query, "research_report", self.source_urls, self.config_path, self.websocket)

        self.existing_headers = []
        # This is a global variable to store the entire context accumulated at any point through searching and scraping
        self.global_context = []
    
        # This is a global variable to store the entire url list accumulated at any point through searching and scraping
        if self.source_urls:
            self.global_urls = set(self.source_urls)

    async def run(self):

        # Conduct initial research using the main assistant
        await self._initial_research()

        # Get list of all subtopics
        subtopics = await self._get_all_subtopics()
        
        # Generate report introduction
        report_introduction = await self.main_task_assistant.write_introduction()

        # Generate the subtopic reports based on the subtopics gathered
        _, report_body = await self._generate_subtopic_reports(subtopics)

        # Construct the final list of visited urls
        self.main_task_assistant.visited_urls.update(self.global_urls)

        # Construct the final detailed report (Optionally add more details to the report)
        report = await self._construct_detailed_report(report_introduction, report_body)

        return report

    async def _initial_research(self):
        # Conduct research using the main task assistant to gather content for generating subtopics
        await self.main_task_assistant.conduct_research()
        # Update context of the global context variable
        self.global_context = self.main_task_assistant.context
        # Update url list of the global list variable
        self.global_urls = self.main_task_assistant.visited_urls

    async def _get_all_subtopics(self) -> list:
        subtopics = await self.main_task_assistant.get_subtopics()
        return subtopics.dict()["subtopics"]

    async def _generate_subtopic_reports(self, subtopics: list) -> tuple:
        subtopic_reports = []
        subtopics_report_body = ""

        async def fetch_report(subtopic):

            subtopic_report = await self._get_subtopic_report(subtopic)

            return {
                "topic": subtopic,
                "report": subtopic_report
            }

        # This is the asyncio version of the same code below
        # Although this will definitely run faster, the problem
        # lies in avoiding duplicate information.
        # To solve this the headers from previous subtopic reports are extracted
        # and passed to the next subtopic report generation.
        # This is only possible to do sequentially

        # tasks = [fetch_report(subtopic) for subtopic in subtopics]
        # results = await asyncio.gather(*tasks)

        # for result in filter(lambda r: r["report"], results):
        #     subtopic_reports.append(result)
        #     subtopics_report_body += "\n\n\n" + result["report"]

        for subtopic in subtopics:
            result = await fetch_report(subtopic)
            if result["report"]:
                subtopic_reports.append(result)
                subtopics_report_body += "\n\n\n" + result["report"]

        return subtopic_reports, subtopics_report_body

    async def _get_subtopic_report(self, subtopic: dict) -> tuple:
        current_subtopic_task = subtopic.get("task")
        subtopic_assistant = GPTResearcher(
            query=current_subtopic_task,
            report_type="subtopic_report",
            websocket=self.websocket,
            parent_query=self.query,
            subtopics=self.subtopics,
            visited_urls=self.global_urls,
            agent=self.main_task_assistant.agent,
            role=self.main_task_assistant.role
        )

        # The subtopics should start research from the context gathered till now
        subtopic_assistant.context = list(set(self.global_context))

        # Conduct research on the subtopic
        await subtopic_assistant.conduct_research()

        # Here the headers gathered from previous subtopic reports are passed to the write report function
        # The LLM is later instructed to avoid generating any information relating to these headers as they have already been generated
        subtopic_report = await subtopic_assistant.write_report(self.existing_headers)

        # Update context of the global context variable
        self.global_context = list(set(subtopic_assistant.context))
        # Update url list of the global list variable
        self.global_urls.update(subtopic_assistant.visited_urls)

        # After a subtopic report has been generated then append the headers of the report to existing headers
        self.existing_headers.append(
            {
                "subtopic task": current_subtopic_task,
                "headers": extract_headers(subtopic_report),
            }
        )

        return subtopic_report

    async def _construct_detailed_report(self, introduction: str, report_body: str):
        # Generating a table of contents from report headers
        toc = table_of_contents(report_body)
        
        # Concatenating all source urls at the end of the report
        report_with_references = add_source_urls(report_body, self.main_task_assistant.visited_urls)
        
        return f"{introduction}\n\n{toc}\n\n{report_with_references}"
```````




`../gpt-researcher/backend/report_type/basic_report/basic_report.py`:

```````py
from gpt_researcher.master.agent import GPTResearcher
from fastapi import WebSocket

class BasicReport():
    def __init__(self, query: str, report_type: str, source_urls, config_path: str, websocket: WebSocket):
        self.query = query
        self.report_type = report_type
        self.source_urls = source_urls
        self.config_path = config_path
        self.websocket = websocket
        
    async def run(self):
        # Initialize researcher
        researcher = GPTResearcher(self.query, self.report_type, self.source_urls, self.config_path, self.websocket)
        
        # Run research
        await researcher.conduct_research()
        
        # and generate report        
        report = await researcher.write_report()
        
        return report
```````




`../gpt-researcher/backend/utils.py`:

```````py
import aiofiles
import urllib
import uuid
from md2pdf.core import md2pdf
import mistune
from docx import Document
from htmldocx import HtmlToDocx

async def write_to_file(filename: str, text: str) -> None:
    """Asynchronously write text to a file in UTF-8 encoding.

    Args:
        filename (str): The filename to write to.
        text (str): The text to write.
    """
    # Convert text to UTF-8, replacing any problematic characters
    text_utf8 = text.encode('utf-8', errors='replace').decode('utf-8')

    async with aiofiles.open(filename, "w", encoding='utf-8') as file:
        await file.write(text_utf8)

async def write_md_to_pdf(text: str) -> str:
    """Converts Markdown text to a PDF file and returns the file path.

    Args:
        text (str): Markdown text to convert.

    Returns:
        str: The encoded file path of the generated PDF.
    """
    task = uuid.uuid4().hex
    file_path = f"outputs/{task}"
    await write_to_file(f"{file_path}.md", text)

    try:
        md2pdf(f"{file_path}.pdf",
               md_content=None,
               md_file_path=f"{file_path}.md",
               css_file_path="./frontend/pdf_styles.css",
               base_url=None)
        print(f"Report written to {file_path}.pdf")
    except Exception as e:
        print(f"Error in converting Markdown to PDF: {e}")
        return ""

    encoded_file_path = urllib.parse.quote(f"{file_path}.pdf")
    return encoded_file_path

async def write_md_to_word(text: str) -> str:
    """Converts Markdown text to a DOCX file and returns the file path.

    Args:
        text (str): Markdown text to convert.

    Returns:
        str: The encoded file path of the generated DOCX.
    """
    task = uuid.uuid4().hex
    file_path = f"outputs/{task}"

    try:
        # Convert report markdown to HTML
        html = mistune.html(text)
        # Create a document object
        doc = Document()
        # Convert the html generated from the report to document format
        HtmlToDocx().add_html_to_document(html, doc)

        # Saving the docx document to file_path
        doc.save(f"{file_path}.docx")
        
        print(f"Report written to {file_path}.docx")

        encoded_file_path = urllib.parse.quote(f"{file_path}.docx")
        return encoded_file_path
    
    except Exception as e:
        print(f"Error in converting Markdown to DOCX: {e}")
        return ""

```````



When analyzing the codebase, please cover the following points:

1. Purpose and Functionality:
   - What is the main purpose of this codebase?
   - What are the key features and functionalities it provides?

2. Architecture and Design:
   - What is the high-level architecture of the codebase?
   - How is the codebase structured in terms of directories and files?
   - What are the main components, modules, or classes, and how do they interact?
   - Are there any design patterns or architectural patterns used?

3. Language and Dependencies:
   - What programming language(s) is the codebase written in?
   - Are there any major frameworks, libraries, or dependencies used?
   - How are the dependencies managed (e.g., package manager)?

4. Data Flow and Control Flow:
   - How does data flow through the application?
   - What are the main entry points and exit points of the application?
   - Are there any significant data structures or algorithms used?

5. Configuration and Environment:
   - Are there any configuration files or environment variables used?
   - What is the purpose of each configuration file or variable?
   - Are there any specific setup or deployment requirements?

6. Testing and Quality Assurance:
   - Is there a testing framework or approach used in the codebase?
   - Where are the test files located?
   - Are there any continuous integration or continuous deployment practices in place?

7. Documentation and Maintainability:
   - Is there any documentation available (e.g., README, API docs, architecture diagrams)?
   - How well-commented and self-explanatory is the code?
   - Are there any areas that could benefit from improved documentation or code comments?

Please provide a clear and concise explanation for each point, highlighting the most important aspects of the codebase. If there are any parts of the codebase that are unclear or confusing, please point them out and suggest ways to clarify them.

Additionally, if you identify any potential areas for improvement or best practices that could be applied, feel free to mention them as well.

Thank you for your help in understanding this codebase better!