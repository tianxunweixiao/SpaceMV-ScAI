# SpaceMV-ScAI

面对日益庞大和复杂的商业航天时代，传统的桌面端仿真软件已难以满足快速迭代的需求。我们是否能拥有一个更智能、更主动的系统，让数据库中的轨道数据自行说话，让决策更加敏捷？
答案是肯定的。

`SpaceMV-ScAI`，由成都天巡微小卫星科技有限责任公司研发，是一个面向 Agent 架构的开源星座智能管理平台。与传统的被动查询工具不同，`SpaceMV-ScAI` 致力于打造一个集成了可视化管理、动态分析与智能交互的 AI 解决方案基座。它的核心愿景，是利用先进的 Agent 技术，将枯燥的轨道根数转化为直观的战略洞察，为未来的智能体自动化编排奠定数据基础。

## **场景勾勒**
当 Agent 遇上航天数据，我们将如何重构星座管理？以下是SpaceMV-ScAI计划构建的六大核心应用场景蓝图：

### **卫星过境智能预报**

告别繁琐的手动反复查询与复杂的参数计算。在 SpaceMV-ScAI，用户只需完成一次“任务订阅”——告诉智能体关注的目标。随后，Agent 便会在后台进行持续的轨道演算与匹配。一旦捕捉到满足用户个性化需求的绝佳窗口，系统将主动推送精准的时间表与方位信息。无论是建立关键通信链路，还是进行科研观测，SpaceMV-ScAI都能即时响应，提前锁定最佳时机。

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/c23149b2-e694-426b-9064-875a51abae98" />
</div>

### **时空覆盖动态仿真**

卫星网络不应只是静态的点阵图。SpaceMV-ScAI在数字世界中重建了一个动态的四维时空，并引入了强大的“区域监测订阅”功能。用户可以划定特定的关注区域（如航线、科考站或重点城市），智能体将7x24小时持续推演巨型星座对该区域的包裹态势。当该区域的覆盖质量出现波动、盲区扩大或满足特定重访要求时，系统即时推送订阅提醒，并能动态回放事发时段的覆盖演变过程，直观掌握全球星座态势变化。

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/094f36fc-ccf8-4de2-baa9-62c353a6ab58" />
</div>

### **自然语言资产交互**

忘掉复杂的 SQL 查询语句。借助 LLM（大语言模型）的理解能力，SpaceMV-ScAI 允许用户像与行业专家对话一样查询数据库。只需在对话框输入：“某国去年发射了多少颗卫星？”或“列出所有重量大于 500kg 的在轨卫星”，数据 Agent 就能精准理解意图并即时返回答案。

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/f9c4bc03-fed3-4d71-96e8-6987cf0a5957" />
</div>

### **图表智能化生成**

不需要具备专业的数据分析技能，也能洞察数据背后的规律。只需提出你的分析需求，SpaceMV-ScAI的分析 Agent 就能从大量基础数据中自动提炼关键指标，智能选择最合适的图表类型（如发射趋势折线图、轨道高度分布直方图等），自动生成专业的可视化大屏，让数据趋势跃然纸上。

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/d85a6de6-ed1c-4e45-b2e0-7beb19388798" />
</div>

### **星座构型智能分析**

这是一种“数据逆向工程”。即使仅凭基础的 TLE 数据，Agent 也能通过精密的数学计算，分析大量卫星的轨道参数分布特征，逆向解析出目标星座的宏观布局和组网策略（例如识别出是 Walker 星座构型还是极轨网）。

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/a2f85774-a70e-4979-bf92-d1c2b5af2622" />
</div>

### **巨型星座衰退**
对于缺乏遥测数据的老旧卫星，我们依然可以洞察其状态。SpaceMV-ScAI通过长期追踪对比 TLE 历史数据的变化趋势，敏锐地捕捉到轨道异常衰减信号。Agent 能智能推断星座内的卫星是否已耗尽燃料、失去姿态控制或即将再入大气层，为用户生成一份潜在的“太空垃圾”或“重点关注对象”预警清单。

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/016c8bb7-2ae4-415c-93d6-cf15ee2f64b5" />
</div>

## **架构设计**

### **业务架构**

<div align="center">
  <img width="80%" alt="image" src="https://github.com/user-attachments/assets/74a34973-c34b-4d5f-8880-43a341d297d4" />
</div>

为了支撑“让数据说话”的愿景，SpaceMV-ScAI 采用了高度模块化的四层业务架构，确保系统既拥有处理海量数据的吞吐能力，又具备Agent 灵活调度的智能特性：

● 数据源与感知层

ScAI 实时同步CelesTrak 等开源权威数据，同时将用户的自然语言指令（NLP）作为核心输入，让“对话”成为系统感知业务意图的第一步。

● 平台服务层

Agent 智能体内核：负责任务拆解与自主决策，是系统的灵魂。

航天数据中台：基于ClickHouse 清洗与存储海量TLE 数据。

双引擎驱动：集成SGP4/SDP4 高精度解算引擎与Cesium 时空可视化引擎，确保算得准、看得清。

● 应用层

智慧监测预警：从过境预报到寿命监测，防患于未然。

时空态势分析：全球覆盖仿真与构型解算，洞察宏观布局。

数据智能洞察：Text-to-SQL 交互与自动化图表，让数据分析零门槛。

● 展现层

除了提供开箱即用的Web 业务工作台，我们特别强调开放性。通过API 数据接口与开源社区协作平台，SpaceMV-ScAI不仅仅是一个工具，更是一个开发者共同参与的开源生态。

### **技术架构**

SpaceMV-ScAI通过“云+端”的分布式架构，结合LLM智能体的强大能力，实现了数据、计算和工具的智能协同。它不仅能够提供精准、实时的卫星业务服务，还能通过智能体的灵活部署和按需分发，为用户按需定制的交互体验和业务效率提升。

<div align="center">
  <img width="80%" alt="image" src="https://github.com/user-attachments/assets/0775910a-ac80-419c-bd65-1ef9d62fbcb2" />
</div>

● 云端中心架构

系统的云端中心是整个架构的基石，主要由“全球卫星数据中心”和“租户业务解算中心”构成。全球卫星数据中心负责汇聚、存储并管理海量的卫星星座数据，包括但不限于TLE（Two-Line Element）数据、卫星状态参数、历史轨道信息等。这些数据是所有智能体业务的基础。租户业务解算中心则是一个高性能的计算集群，承载着复杂的轨道计算、大规模数据分析以及智能体业务逻辑的预处理任务。此外，云端还设置了工具库（Tool Repository），预置了一系列针对卫星业务的专业工具，例如轨道仿真算法、数据分析模型等，这些工具是智能体执行任务的“能力集”。

● 边缘端侧架构

系统的边缘侧主推统一配置的“小型算力盒子”，这些盒子内置了GPU，能够高效运行本地大语言模型（Local LLM Agent）。端侧LLM是智能体的核心，它具备强大的自然语言理解与生成能力，能够将用户的自然语言指令转化为可执行的任务。这些小型算力盒子作为用户侧的智能终端，承担了大量实时性、个性化的计算任务，有效减轻了云端中心的压力，并保障了用户数据的本地化处理。

● 云端协同与智能体赋能

本架构的精髓在于云端之间的紧密协同。云端中心支持数据推送（Data Pushing）机制，根据租户的订阅策略，将定制化的卫星数据定时、精准地同步到边缘端侧的小型算力盒子。同时，云端的业务工具（Business Tools）也能够按需分发至端侧，供本地LLM调用。例如，在“时空覆盖动态仿真”和“自然语言资产交互”等业务中，用户在端侧通过LLM发出指令，LLM则调用本地已分发的工具进行计算和响应，实现业务的闭环。对于“卫星过境智能预报”、“图表智能化生成”和“卫星寿命监测”等业务，端侧LLM结合本地数据和工具，能够快速生成预报结果、可视化图表及监测报告。

● 租户定制化服务

为了满足不同租户的差异化需求，系统支持基于租户订阅的个性化数据分发。这意味着每个租户的边缘算力盒子只会接收到其关注的卫星数据，避免了不必要的数据传输和存储开销。这种设计不仅提升了系统的效率，也增强了数据的安全性和隐私性。

## **功能展示**

### **覆盖性仿真与分析**

平台支持光学遥感卫星对目标区域的覆盖情况进行仿真。系统可生成详细的仿真报告，支持流式输出仿真结果，并利用 STK 引擎保证计算精度。

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/56fb75db-716c-4739-ba9e-ae5feefd0da7" />
</div>

### **三维可视化交互**

前端提供直观的 3D 地球视图，支持：

● 实时渲染卫星轨迹。

● 自动外推卫星轨道状态。

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/600000ed-cb85-4b4b-aab5-295b5b83e585" />
</div>

### **资源与数据管理**

● 星座管理：支持 GPS、Starlink、北斗等预设星座的自动识别与分类，同时支持上传自定义星座配置。

● 数据同步：内置定时器自动从 Celestrak API 同步最新的 TLE（两行轨道根数）数据。

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/4f72d1a6-51a0-4fcc-9836-7a648fe31173" />
</div>

### **智能化扩展**

后端已集成 LLM（Ollama）接口，提供基于 AI 的对话辅助功能，为未来的人机交互与Agent自动编排做准备。

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/a6d64e1c-d41f-46c6-9122-7a45279a020c" />
</div>

## **开源地址**
SpaceMV-ScAI 遵循 Apache 2.0 (后端) 和 AGPL 3.0 (前端) 开源协议，欢迎相关领域的开发者与研究人员关注、使用及贡献代码。

● 后端仓库 (Backend):https://github.com/spacemv-lab/SpaceMV-ScAI-backend

● 前端仓库 (Frontend):https://github.com/spacemv-lab/SpaceMV-ScAI-frontend
