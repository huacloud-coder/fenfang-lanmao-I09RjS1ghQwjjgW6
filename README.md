
![](https://img2024.cnblogs.com/blog/759200/202501/759200-20250106214920454-1120483720.png)


上周，DeepSeek\-V3 将训练大模型的成本给打下来了，但训练大模型对普通开发者来说仍然门槛很高。所以，本期的热门开源项目聚焦于降低 LLM 应用开发的入门门槛。


极易上手的向量数据库 chroma 用起来十分方便，只需一行命令 `pip install chromadb` 就能轻松拥有一个向量数据库，用于存储和检索向量数据。接下来是专为构建实时 AI 应用的 Python ETL 框架 pathway，它提供了简单易用的 Python API 和可视化监控界面，全面提升 LLM 应用处理数据的效率。同样开箱即用的 Rust 全栈 Web 框架 Loco，则将 Rails 的开发体验与 Rust 的高性能相结合，是快速开发 Web 应用不错的选择。


最后是两个相见恨晚的开源项目，Python 项目打包神器 pex，它为 Python 项目提供了一键部署的丝滑体验。以及可以轻松部署家庭多媒体中心的 docker\-xiaoya。


* 本文目录
	+ 1\. 热门开源项目
		- 1\.1 极易上手的向量数据库：chroma
		- 1\.2 Rust 的全栈 Web 框架：Loco
		- 1\.3 开箱即用的端口扫描工具：RustScan
		- 1\.4 实时更新的轻量级推荐系统：monolith
		- 1\.5 构建实时 AI 系统的 Python 框架：pathway
	+ 2\. HelloGitHub 热评
		- 2\.1 相见恨晚的 Python 项目打包工具：pex
		- 2\.2 一键部署完整的家庭多媒体中心：docker\-xiaoya
	+ 3\. 结尾


## 1\. 热门开源项目


### 1\.1 极易上手的向量数据库：chroma


![](https://img2024.cnblogs.com/blog/759200/202501/759200-20250106214925595-1837559953.png)


**主语言：Rust**，**Star：16\.3k**，**周增长：400**


这是一款专为 AI 应用设计的开源向量数据库（Embedding Database），支持 Python、JavaScript、Rust 等多种编程语言。它提供了简单易用的 API 和多种启动模式（内存、文件存储、服务器），支持基于 embedding 模型的自动向量化处理，以及查询、过滤、密度估计等操作，适用于快速构建基于语义的搜索和推荐等应用。



```
import chromadb
client = chromadb.Client()

collection = client.create_collection("all-my-documents")
collection.add(
    documents=["This is document1", "This is document2"], # we handle tokenization, embedding, and indexing automatically. You can skip that and add your own embeddings as well
    metadatas=[{"source": "notion"}, {"source": "google-docs"}], # filter on these!
    ids=["doc1", "doc2"], # unique for each doc
)

results = collection.query(
    query_texts=["This is a query document"],
    n_results=2,
    # where={"metadata_field": "is_equal_to_this"}, # optional filter
    # where_document={"$contains":"search_string"}  # optional filter
)

```


> GitHub 地址→[github.com/chroma\-core/chroma](https://github.com)


### 1\.2 Rust 的全栈 Web 框架：Loco


![](https://img2024.cnblogs.com/blog/759200/202501/759200-20250106214930445-1666126974.png)


**主语言：Rust**，**Star：6\.4k**，**周增长：600**


该项目是受 Ruby on Rails 启发的 Rust Web 框架，专为帮助开发者快速构建 Web 应用而设计。它结合了类似 Rails 的开发体验和 Rust 的高性能优势，支持 ORM 集成、后台任务、中间件（认证、日志、错误处理）、生成部署配置等功能，适用于开发个人项目和初创企业的 Web 应用。



> GitHub 地址→[github.com/loco\-rs/loco](https://github.com)


### 1\.3 开箱即用的端口扫描工具：RustScan


![](https://img2024.cnblogs.com/blog/759200/202501/759200-20250106214935358-1162016588.gif)


**主语言：Rust**，**Star：15k**


这是一个用 Rust 开发的端口扫描工具，能够在 3 秒内扫描指定 IP 的所有端口。它提供了灵活的脚本引擎，支持 Python、Lua 和 Shell 脚本，开发者可以根据需求自定义脚本，实现个性化的扫描和处理逻辑。



> GitHub 地址→[github.com/RustScan/RustScan](https://github.com)


### 1\.4 实时更新的轻量级推荐系统：monolith


![](https://img2024.cnblogs.com/blog/759200/202501/759200-20250106214939150-1774989627.png)


**主语言：Python**，**Star：6\.6k**，**周增长：2\.4k**


该项目是字节跳动开源的一款轻量级推荐系统，旨在提升推荐系统的准确性和实时性。它基于 TensorFlow 构建，支持无冲突嵌入表（collisionless embedding tables）、批量和实时训练等功能，能够快速响应用户的行为变化，并及时更新模型，提升推荐效果。



> GitHub 地址→[github.com/bytedance/monolith](https://github.com)


### 1\.5 构建实时 AI 系统的 Python 框架：pathway


![](https://img2024.cnblogs.com/blog/759200/202501/759200-20250106214943654-229231920.png)


**主语言：Python**，**Star：12k**，**周增长：1\.4k**


这是一个专为流处理、实时分析、LLM 管道和 RAG 应用设计的 Python ETL 框架。它底层采用 Rust 引擎，具备高吞吐和低延迟的实时处理能力，同时提供简单易用的 Python API 和可视化监控面板，支持多种数据源、数据转换和持久化等功能。



> GitHub 地址→[github.com/pathwaycom/pathway](https://github.com)


## 2\. HelloGitHub 热评


在此章节中，我们将为大家介绍本周 HelloGitHub 网站上的热门开源项目，我们不仅希望您能从中收获开源神器和编程知识，更渴望“听”到您的声音。欢迎您与我们分享使用这些**开源项目的亲身体验和评价**，用最真实反馈为开源项目的作者注入动力。


![](https://img2024.cnblogs.com/blog/759200/202501/759200-20250106214951636-1750072292.png)


### 2\.1 相见恨晚的 Python 项目打包工具：pex


![](https://img2024.cnblogs.com/blog/759200/202501/759200-20250106214948271-383094183.png)


**主语言：Python**


这是一个开源的 Python 项目打包工具，专为跨环境部署和无法访问公网的部署场景设计。它能够将 Python 项目及其所有依赖，甚至是 Python 解释器（可选），打包成单个可执行文件（.pex），让开发者无需安装运行环境，即可直接运行 Python 程序，支持 Linux 和 macOS 系统。



> 项目详情→[hellogithub.com/repository/5c47cbf587f448fd8c4106436b3de8e3](https://github.com):[西部世界westwingy加速器](https://www.yicheer.com)


### 2\.2 一键部署完整的家庭多媒体中心：docker\-xiaoya


![](https://img2024.cnblogs.com/blog/759200/202501/759200-20250106214956485-930137291.png)


**主语言：Shell**


该项目提供了一键部署 Alist、Emby 和 Jellyfin 服务的解决方案，帮你轻松构建完整的家庭多媒体中心，支持 Linux、macOS、Windows 等平台。



> 项目详情→[hellogithub.com/repository/c0360e74337e448b852ab96ea4382a62](https://github.com)


## 3\. 结尾


以上就是本期「GitHub 热点速览」的全部内容，希望这些开源项目能激发你的兴趣，成为你下一个值得尝试的工具！如果你有其他好玩、有趣的 GitHub 开源项目想要分享，欢迎来 [HelloGitHub](https://github.com) 与我们交流和讨论。


**往期回顾**


* [神仙打架的一期](https://github.com)
* [双语对照的 PDF 翻译工具](https://github.com)


