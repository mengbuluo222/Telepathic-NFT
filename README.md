# 灵犀 NFT 项目说明书
## 理念
“灵犀 NFT” 中，“灵犀” 一词取自成语 “心有灵犀”，寓意着在 NFT 领域中，创作者与收藏者、买家与卖家之间能够有一种默契和共鸣。就像心有灵犀一样，收藏者能够精准地发现自己心仪的 NFT 作品，而创作者也能通过作品与收藏者建立起特殊的情感连接。同时，“灵” 也可象征着 NFT 数字作品的灵动性、独特性和创造性，“犀” 给人一种珍贵、坚实的感觉，暗示着 NFT 作为数字资产的价值和可靠性。

## 一、项目概述
“灵犀 NFT” 是基于 Move 语言开发的 NFT 存储与交易平台，旨在为用户打造安全、高效、便捷的 NFT 生态环境，实现 NFT 从创建、存储到交易的全流程服务，促进数字资产的流通与价值发现。

## 二、项目背景
随着区块链技术的发展，NFT 作为独特的数字资产形式，在艺术、游戏、收藏等领域迅速崛起。当前 NFT 市场缺乏既安全又易用，且充分发挥新兴区块链技术优势的交易平台。本项目基于 Move 语言开发，旨在填补这一市场空白，满足用户对 NFT 相关服务的需求。

**用户需求**
- 普通用户：能简单快速地铸造 NFT，安全存储 NFT 资产，在平台便捷地搜索、浏览和交易 NFT。
- 创作者：拥有简单、安全的环境发行数字作品 NFT，可追踪作品交易情况。

## 三、功能模块
- NFT 创建：支持用户自定义 NFT 的名称、描述、图像、音频、视频等元数据，通过简洁直观的操作界面，引导用户轻松完成 NFT 铸造。调用 Move 语言智能合约生成唯一标识 NFT，将元数据加密存储在区块链。
- NFT 存储：运用区块链分布式存储技术，结合 IPFS 星际文件系统，确保 NFT 元数据及文件的安全存储，数据不可篡改且永久保存，在区块链上记录 IPFS 文件哈希值，保障数据完整性与可追溯性。
- 交易功能：提供挂单出售、购买、批量交易、价格协商（议价功能）、取消订单等操作，支持多种交易模式，满足不同用户交易需求；借助智能合约自动执行交易逻辑，保障交易公平、安全、透明。
- 用户管理：负责用户注册、登录、身份验证等操作，采用加密技术保护用户信息安全，支持多链钱包登录，方便用户使用不同数字资产进行交易，同时提供用户个性化设置与偏好管理功能。
- 订单管理：用户可随时查看、管理个人交易订单，包括历史订单查询、订单状态跟踪（如待付款、待发货、已完成、已取消等），订单详情展示交易金额、交易时间、交易双方信息等。
- 市场展示：实时展示热门、最新上架、高价值 NFT，生成热门 NFT 排行榜与分类浏览页面，方便用户发现感兴趣的 NFT，提供搜索框与筛选功能，用户可按关键词、属性、价格范围、创作风格等条件搜索和筛选 NFT。

## 四、技术架构
- 前端：采用 React 框架搭建用户界面，配合 Next.js 实现服务器端渲染，提升页面加载速度与用户体验；运用 HTML5 和 CSS3 进行页面布局与样式设计；使用 Web3.js 库实现前端与区块链的交互，完成 NFT 数据获取、交易签名与发送等操作。
- 智能合约：基于 Move 语言编写，运行于支持 Move 语言的区块链平台，如 Aptos 或 Sui，实现 NFT 创建、所有权转移、交易逻辑等核心功能，确保代码安全、高效执行，保障用户数字资产安全。
- 区块链：选用 Aptos 或 Sui 区块链作为底层平台，提供稳定的区块链基础设施服务，保障数据的分布式存储、不可篡改和共识机制。
- 存储：以区块链存储 NFT 核心数据，如所有权信息、交易记录等；利用 IPFS 存储 NFT 的文件内容，如图片、音频、视频等，提高存储效率与成本效益。
- 数据库：辅助使用 MongoDB 数据库，存储用户信息、交易缓存数据、系统配置信息等，优化系统性能，实现数据快速查询与处理。

## 页面布局
1.首页：展示热门、最新 NFT，设搜索框、导航栏，导航栏链接创建 NFT 页面、用户个人中心、市场分类页面。
2.创建 NFT 页面：含名称、描述、图像上传、属性设置表单，“创建” 按钮生成 NFT，有操作指引和注意事项提示。
3.NFT 详情页：展示 NFT 详细元数据、所有者、历史交易记录、当前价格；出售中的 NFT 有 “购买” 按钮，支持点击议价；非出售状态显示所有者信息及 “关注” 按钮，关注后可接收 NFT 动态。
4.用户个人中心：展示用户拥有的 NFT 资产（支持列表、网格视图切换）、发布的出售订单、收藏的 NFT；提供订单管理功能，可查看订单状态、交易金额、对方信息。
5.市场分类页面：按艺术、游戏、音乐等类别展示 NFT，支持排序和筛选。

## 交互流程
NFT 创建：用户填表单，点击 “创建”，系统检查元数据，调用智能合约铸造 NFT，成功后跳转 NFT 详情页。
NFT 交易：出售方在个人中心选择 NFT，填写价格等信息挂单；购买方浏览 NFT 详情，点击 “购买” 确认订单付款；交易成功更新 NFT 所有权和订单状态。
搜索功能：用户输入关键词或筛选条件，系统返回匹配 NFT 列表。

## 精品网站及源码
[OpenSea](https://github.com/ProjectOpenSea)：是知名的 NFT 交易平台，虽然其未完全开源，但在 GitHub 上有相关项目和代码片段，可参考其智能合约、前端界面设计等方面的代码逻辑。
GitHub 上的 “nft - marketplace” 主题：有 549 个公共仓库且数量不断增加，提供从创建智能合约到构建整个平台的各种代码，可按星级等筛选优质代码参考。
源码分享平台或社区
壹牛 NFT 数字艺术藏品管理系统源码：完全开源，提供了用户找回密码、短信注册和实名制功能，以及后台主图添加等功能，适合研究和二次开发。
2022 年新版 NFT 源码：是中国元宇宙数字藏品艺术品交易平台系统，有详细安装说明，功能强大。
2023 壹牛 NFT 数字艺术藏品数藏系统源码：全开源，修复了一些已知问题，并增加了用户找回密码、短信注册等功能。
