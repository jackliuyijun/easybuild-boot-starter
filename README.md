<h1 align="center"> 🚀 易构 EasyBuild </h1>
<p align="center">
<strong>企业级 Java 微服务架构与快速开发平台的「瑞士军刀」</strong>
</p>

<p align="center">
<img src="https://img.shields.io/badge/Java-21-blue.svg" alt="Java 21">
<img src="https://img.shields.io/badge/Spring%20Boot-3.2.x-brightgreen.svg" alt="Spring Boot 3">
<img src="https://img.shields.io/badge/Next.js-15-black.svg" alt="Next.js 15">
<img src="https://img.shields.io/badge/Architecture-Single%20%7C%20Microservice%20%7C%20Smart-orange.svg" alt="Architecture">
<a href="https://easybuild.pro"><img src="https://img.shields.io/badge/Official%20Website-easybuild.pro-blueviolet" alt="官网"></a>
</p>

<p align="center">
一套平台，武装全栈。从依赖治理到代码生成，从单体到微服务，让每一位开发者拥有大厂基建能力，分钟级交付企业级应用。
</p>

🔗 官方传送门

🌍 官方网站：https://easybuild.pro

📖 开发文档：https://easybuild.pro/docs

💻 快速上手：https://easybuild.pro/docs/reader/dev-env

💡 为什么选择 EasyBuild？

你是否也面临这些开发困境？

每次新开项目都要耗费一周搭基建（统一响应、异常处理、权限、日志、Redis 封装）？

手写重复的 CRUD，实体类、DTO、Mapper、Service 写到吐？

选定单体架构后，业务爆发想拆微服务，发现代码高度耦合几乎要重写？

需要电商、支付、权限系统，网上找的开源代码质量堪忧，自己从头写全是坑？

EasyBuild 就是为了终结这些痛点而生！ 它不是一个简单的示例工程，而是一个平台级的底层 SDK + 全栈脚手架。

🔥 核心黑科技

⚡️ 架构形态一键无缝切换
只需在配置中修改一行 project-type: single / microservice / smart，你的项目结构、API 路由、RPC 调用方式瞬间完成单体与微服务的切换。业务初期用单体，爆发期拆微服务，代码零重构。

🪄 智能全栈代码生成器
直连数据库（支持 22 种中外/信创 DB），一次配置，秒级生成 15+ 个文件（从底层 Entity/Mapper 到 DTO/RPC，再到 Controller），完整覆盖业务链路。

🧩 40+ 生产级组件「即插即用」
需要缓存？引入 cache-caffeine。需要分布式锁？引入 lock-redisson。所有组件高度抽象，换 ORM（MyBatis-Plus 换 Flex）、换 MQ（RabbitMQ 换 Kafka）只需更换一行依赖，业务代码一行不改。

🛍 18+ 高频业务模块「开箱即用」
内置企业级 Auth 权限、SaaS 多租户、商品(SPU/SKU)、交易编排、全场景订单、支付集成等模块。自带高并发库存安全、支付幂等处理。

🎨 后端驱动的 Next.js 15 现代化前台
基于 React 19 + Tailwind CSS，前端菜单与权限完全由后端动态下发！极简复用，90% 的页面只需通过 JSON 配置即可生成强大的 Table 和 Form。

🛠 极客级的技术选型

坚持 “选最新的、用最稳的”，享受极致性能：

核心基建 (EasyFK)

底层环境：Java 21 + Spring Boot 3.2.x + Jakarta EE

双栈 RPC：Apache Dubbo 3.3.x + Spring Cloud OpenFeign（支持并存）

极致性能优化：

序列化：Apache Fory 0.14.1（性能达 JDK 原生 100 倍）

进程内队列：LMAX Disruptor 无锁队列（单线程百万级 TPS）

Web 容器：Undertow（更低内存，更高并发）

堆外缓存：Chronicle Map 亚微秒级零 GC 缓存

业务与中后台

中后台前端：Next.js 15 + React 19 + Shadcn/ui + Zustand

表单与表格：React Hook Form + Zod + TanStack Table

数据存储：MyBatis-Plus / MyBatis-Flex、ShardingSphere、Redis、ClickHouse、MongoDB

中间件：Kafka / RocketMQ / RabbitMQ、Seata、Sentinel、Nacos

🚀 5 分钟极速上手

无需繁琐的配置，引入平台依赖即可获得无敌的基础设施。

1. 引入统一版本治理 BOM

在 build.gradle 或 pom.xml 中引入 EasyBuild 依赖底座：

code
Gradle
download
content_copy
expand_less
dependencies {
    // 1. 引入统一版本平台
    implementation platform('com.mcst:easyfk-dependencies:3.2.12')
    
    // 2. 按需引入技术组件 (无需指定版本号)
    implementation 'com.mcst:orm-mybatis'         // 数据库访问
    implementation 'com.mcst:db-redis'            // Redis
    implementation 'com.mcst:web-prd'             // 生产级 Web 引擎
}
2. 配置代码生成器

配置你的数据库信息与生成策略：

code
Yaml
download
content_copy
expand_less
easyfk:
  config:
    generator:
      project:
        project-type: smart           # 架构类型: single / microservice / smart
        prd-type: separation          # 表现层: none / single / separation
        orm-type: MYBATIS             # ORM: MYBATIS / MYBATIS_FLEX
      code:
        db-short-url: localhost:3306/easybuild_db
        model-list:
          - model-name: Product
            model-desc: 商品信息
3. 一键生成全栈代码

执行生成任务，瞬间得到包含 API 接口、业务逻辑、分布式 RPC 和前端对接层在内的完整代码。立刻启动，专注于你的核心业务逻辑开发！

👉 查看完整《快速上手指南》

🏗 产品模块全景图

EasyBuild 提供从技术底层到业务前端的全场景解决方案：

code
Text
download
content_copy
expand_less
易构 easybuild 
├── ① EasyFK (技术架构底座) —— 包含依赖治理、核心框架、40+组件与代码生成器
├── ② 通用业务模块 —— 18+ 开箱即用的微服务 (权限/用户/VIP/商品/交易/订单/支付)
├── ③ easybuild-Admin —— 基于 Next.js 15 的现代化中后台前端工程
├── ④ 小程序开发脚手架 —— 快速搭建标准化微信生态应用
├── ⑤ 跨平台 APP 脚手架 —— 基于 Flutter 的移动端双端方案
└── ⑥ AI 智能辅助 —— 深度整合大模型的开发搭档
🤝 获取商业授权与支持

EasyBuild 致力于为企业提供稳定、高效的研发平台。如需获取完整源码、商业授权或企业级技术支持，欢迎访问官网或与我们联系：

🌐 官网：https://easybuild.pro

💬 合作联系：请访问官网获取微信/邮箱联系方式。

"让每一行代码都站在坚实的基础设施之上，专注业务创新，加速交付价值。"
—— EasyBuild 易构团队

(由于文档较长，此仓库仅作开源技术交流与示例展示，完整体验与文档请前往 易构官方网站 查看。)
