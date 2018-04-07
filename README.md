# Web 平台区块链开发

---
###### 作者：熊伟伦（Azard）[GitHub](https://github.com/Azard) [知乎](https://www.zhihu.com/people/xiong-wei-lun) [微博](https://weibo.com/azard5) 

### 本书面向的读者

* 具有一定的计算机和编程基础。
* 希望从零了解区块链或者希望了解开发运行在Web平台区块链系统的人。
* 希望了解大型JavaScript / Node.js项目的人。
* 希望了解如何复用代码开发Web、桌面双平台程序的人。

### 简介

自2009年中本聪（Satoshi Nakamoto）发布比特币（Bitcoin[^1]）以来，从中提炼出的“区块链”（BlockChain）技术的热度日益升高，比特币将“分布式系统”与“密码学”这两大计算机技术领域结合起来形成了“区块链”模型，又加以经济学激励，形成了一个稳定的基于区块链技术的点对点电子现金生态系统。

伴随着比特币热度的上升，使用区块链技术开发的项目也在日益增加，其中比较著名的有以太坊（Ethereum[^2]）和超级账本（HyperLeadger[^3]）。以太坊是由 Vitalik Buterin 创立、以太坊基金会维护的公有区块链平台，相比于比特币其最大的差异就是以太坊增加了图灵完备的“智能合约”（Smart Contract），给区块链系统增添了更多的想象力。超级账本是由 IBM 发起、上百家公司参与的开源区块链平台，主要目标是打造通用的企业级区块链系统，让企业能够依赖该项目进行开发而不需要重新“造轮子”。

本书讲解如何开发一个原生运行在 Web 平台的区块链系统，系统原型是 Nimiq[^4] 项目。区块链系统能够运行在 Web 平台上意味着浏览器就能运行，这有多个好处：（1）易用性：运行比特币、以太坊的节点和本地钱包需要足够的计算机基础并进行复杂的配置，而浏览器运行则只需要打开网页，非专业人士更容易使用；（2）轻便：只需打开网页并同步小部分数据即可加入区块链网络，无需下载繁重的客户端同步所有数据；（3）兼容性：能安装现代浏览器的设备都可运行区块链系统，包括手机、车载、电视盒子等设备，Web 平台提供了应用与系统之间一个绝佳的兼容层。

本书讲解的系统大部分使用 JavaScript ES6+ 开发，计算密集型的一小部分使用 C 语言开发，使用这两种语言开发使得该区块链系统通过一套代码就能同时运行在 Web 平台和桌面平台：对于 Web 平台，现代浏览器的“官方语言”就是 JavaScript，而 WebAssembly[^5] 规范让 Web 平台能够运行 C 语言源代码编译的程序；对于桌面平台（Windows、Linux、MacOS 等），则使用 Node.js[^6] 运行该区块链系统，C 语言源代码通过 Node.js Addons 运行。

### 目录

* [本书简介](README.md)
* [1. 区块链概览](Chapter_1/1.区块链概览.md)
    * [1.1. 分布式系统与密码学](Chapter_1/1.1.分布式系统与密码学.md)
    * [1.2. P2P 与 BT 技术](Chapter_1/1.2.P2P与BT技术.md)
    * [1.3. 比特币：一切开始的地方](Chapter_1/1.3.比特币：一切开始的地方.md)
    * [1.4. 以太坊：网络上的乌托邦](Chapter_1/1.4.以太坊：网络上的乌托邦.md)
    * [1.5. 后继者们](Chapter_1/1.5.后继者们.md)
* [2. 区块链系统剖析](Chapter_2/2.区块链系统剖析.md)
    * [2.1. 区块与链](Chapter_2/2.1.区块与链.md)
    * [2.2. 共识算法：挖矿的本质](Chapter_2/2.2.共识算法：挖矿的本质.md)
    * [2.3. 智能合约](Chapter_2/2.3.智能合约.md)
    * [2.4. 百花齐放的时代](Chapter_2/2.4.百花齐放的时代.md)
* [3. 现代 Web 技术](Chapter_3/3.现代Web技术.md)
    * [3.1. JavaScript：Web 王者](Chapter_3/3.1.JavaScript：Web王者.md)
    * [3.2. Web Worker：三头六臂](Chapter_3/3.2.WebWorker：三头六臂.md)
    * [3.3. WebAssembly：浏览器的翅膀](Chapter_3/3.3.WebAssembly：浏览器的翅膀.md)
    * [3.4. Node.js：广阔天地大有可为](Chapter_3/3.4.Node.js：广阔天地大有可为.md)
* [4. Web 平台区块链开发](Chapter_4/4.Web平台区块链开发.md)
    * [4.1. 系统概览](Chapter_4/4.1.系统概览.md)
    * [4.2. 数据结构](Chapter_4/4.2.数据结构.md)
    * [4.3. 出块与共识](Chapter_4/4.3.出块与共识.md)
    * [4.4. P2P 通信](Chapter_4/4.4.P2P通信.md)
    * [4.5. 发起交易](Chapter_4/4.5.发起交易.md)
    * [4.6. 编译与测试](Chapter_4/4.6.编译与测试.md)
* [5. Nimiq 源码分析](Chapter_5/5.Nimiq源码分析.md)
    * [5.1. Nimiq 概览](Chapter_5/5.1.Nimiq概览.md)
    * [5.2. SDK](Chapter_5/5.2.SDK.md)
    * [5.3. 工作量证明](Chapter_5/5.3.工作量证明.md)
    * [5.4. WebRTC 与 WebSocket 多态通信](Chapter_5/5.4.WebRTC与WebSocket多态通信.md)
    * [5.5. 扩展方向](Chapter_5/5.5.扩展方向.md)
* [6. Web 台区块链的应用](Chapter_6/6.Web平台区块链的应用.md)

---

[^1]: 比特币源代码地址: https://github.com/bitcoin/bitcoin

[^2]: 以太坊官网: https://www.ethereum.org/

[^3]: 超级账本官网: https://www.hyperledger.org/

[^4]: 基于浏览器的区块链系统 Nimiq: https://nimiq.com/

[^5]: WebAssembly: http://webassembly.org/

[^6]: Node.js: https://nodejs.org/
