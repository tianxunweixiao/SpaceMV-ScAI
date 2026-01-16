# SpaceMV-ScAI

In the face of the increasingly massive and complex era of commercial spaceflight, traditional desktop simulation software can hardly meet the needs of rapid iteration. Can we possess a smarter, more proactive system that lets the orbital data in the database speak for itself, making decision-making more agile?
The answer is yes.

`SpaceMV-ScAI`, developed by Chengdu Tianxun Micro-Satellite Technology Co., Ltd., is an open-source constellation intelligent management platform oriented towards an Agent architecture. Unlike traditional passive query tools, `SpaceMV-ScAI` is dedicated to building an AI solution foundation that integrates visual management, dynamic analysis, and intelligent interaction. Its core vision is to utilize advanced Agent technology to transform boring orbital elements into intuitive strategic insights, laying the data foundation for future automated orchestration of intelligent agents.

## **Scenarios Outline**
When Agents meet aerospace data, how will we reconstruct constellation management? The following are the six core application scenario blueprints that SpaceMV-ScAI plans to build:

### **Intelligent Satellite Pass Prediction**

Bid farewell to tedious manual repeated queries and complex parameter calculations. In SpaceMV-ScAI, users only need to complete a one-time "task subscription"—telling the Agent the target to focus on. Subsequently, the Agent will conduct continuous orbital calculations and matching in the background. Once an excellent window meeting the user's personalized needs is captured, the system will actively push precise schedules and azimuth information. Whether establishing critical communication links or conducting scientific observations, SpaceMV-ScAI can respond instantly and lock in the best timing in advance.

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/c23149b2-e694-426b-9064-875a51abae98" />
</div>

### **Dynamic Spatiotemporal Coverage Simulation**

Satellite networks should not be just static dot plots. SpaceMV-ScAI rebuilds a dynamic four-dimensional space-time in the digital world and introduces a powerful "Regional Monitoring Subscription" function. Users can delineate specific areas of interest (such as flight routes, scientific research stations, or key cities), and the Agent will continuously deduce the mega-constellation's wrapping posture over the area 24/7. When the coverage quality of the area fluctuates, blind spots expand, or specific revisit requirements are met, the system instantly pushes subscription alerts and can dynamically playback the coverage evolution process during the event period, allowing for an intuitive grasp of global constellation situational changes.

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/094f36fc-ccf8-4de2-baa9-62c353a6ab58" />
</div>

### **Natural Language Asset Interaction**

Forget complex SQL query statements. Leveraging the understanding capabilities of LLMs (Large Language Models), SpaceMV-ScAI allows users to query the database just like talking to an industry expert. Simply enter in the dialog box: "How many satellites did a certain country launch last year?" or "List all on-orbit satellites weighing more than 500kg," and the Data Agent can precisely understand the intent and return the answer instantly.

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/f9c4bc03-fed3-4d71-96e8-6987cf0a5957" />
</div>

### **Intelligent Chart Generation**

You don't need professional data analysis skills to gain insight into the laws behind the data. Simply state your analysis requirements, and SpaceMV-ScAI's Analysis Agent can automatically extract key indicators from massive basic data, intelligently select the most suitable chart type (such as launch trend line charts, orbital altitude distribution histograms, etc.), and automatically generate professional visualization dashboards, making data trends leap onto the screen.

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/d85a6de6-ed1c-4e45-b2e0-7beb19388798" />
</div>

### **Constellation Configuration Intelligent Analysis**

This is a form of "data reverse engineering." Even with only basic TLE data, the Agent can analyze the orbital parameter distribution characteristics of a large number of satellites through precise mathematical calculations, and reverse-engineer the macro layout and networking strategy of the target constellation (for example, identifying whether it is a Walker constellation configuration or a polar orbit network).

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/a2f85774-a70e-4979-bf92-d1c2b5af2622" />
</div>

### **Mega-Constellation Decay**
For old satellites lacking telemetry data, we can still gain insight into their status. SpaceMV-ScAI keenly captures orbital anomaly decay signals by tracking and comparing the trends of TLE historical data over a long period. The Agent can intelligently infer whether satellites within the constellation have exhausted their fuel, lost attitude control, or are about to re-enter the atmosphere, generating a potential "space debris" or "priority watch object" warning list for the user.

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/016c8bb7-2ae4-415c-93d6-cf15ee2f64b5" />
</div>

## **Architecture Design**

### **Business Architecture**

<div align="center">
  <img width="80%" alt="image" src="https://github.com/user-attachments/assets/74a34973-c34b-4d5f-8880-43a341d297d4" />
</div>

To support the vision of "Letting Data Speak," SpaceMV-ScAI adopts a highly modular four-layer business architecture, ensuring the system possesses both the throughput capacity to handle massive data and the intelligent characteristics of flexible Agent scheduling:

* **Data Source & Perception Layer**
    ScAI synchronizes authoritative open-source data such as CelesTrak in real-time, while taking user Natural Language Processing (NLP) commands as core inputs, making "dialogue" the first step for the system to perceive business intent.

* **Platform Service Layer**
    * **Agent Kernel:** Responsible for task decomposition and autonomous decision-making; it is the soul of the system.
    * **Aerospace Data Middle Platform:** Cleans and stores massive TLE data based on ClickHouse.
    * **Dual-Engine Drive:** Integrates SGP4/SDP4 high-precision calculation engines with the Cesium spatiotemporal visualization engine, ensuring accurate calculations and clear visualization.

* **Application Layer**
    * **Smart Monitoring & Warning:** From pass prediction to life monitoring, preventing problems before they happen.
    * **Spatiotemporal Situational Analysis:** Global coverage simulation and configuration calculation, providing insight into macro layouts.
    * **Data Intelligence Insight:** Text-to-SQL interaction and automated charts, making data analysis accessible with zero threshold.

* **Presentation Layer**
    In addition to providing an out-of-the-box Web business workbench, we emphasize openness. Through API data interfaces and open-source community collaboration platforms, SpaceMV-ScAI is not just a tool, but an open-source ecosystem participated in by developers together.

### **Technical Architecture**

SpaceMV-ScAI achieves intelligent synergy of data, computing, and tools through a "Cloud + Edge" distributed architecture combined with the powerful capabilities of LLM Agents. It can not only provide precise, real-time satellite business services but also offer users customized interactive experiences and business efficiency improvements through flexible deployment and on-demand distribution of Agents.

<div align="center">
  <img width="80%" alt="image" src="https://github.com/user-attachments/assets/0775910a-ac80-419c-bd65-1ef9d62fbcb2" />
</div>

* **Cloud Center Architecture**
    The system's cloud center is the cornerstone of the entire architecture, mainly composed of the "Global Satellite Data Center" and the "Tenant Business Calculation Center." The Global Satellite Data Center is responsible for aggregating, storing, and managing massive satellite constellation data, including but not limited to TLE (Two-Line Element) data, satellite status parameters, historical orbital information, etc. These data are the foundation of all Agent businesses. The Tenant Business Calculation Center is a high-performance computing cluster carrying complex orbital calculations, large-scale data analysis, and preprocessing tasks for Agent business logic. In addition, a Tool Repository is set up in the cloud, pre-installing a series of professional tools for satellite business, such as orbit simulation algorithms and data analysis models, which are the "capability sets" for Agents to execute tasks.

* **Edge/Terminal Side Architecture**
    The edge side of the system promotes unified "Small Computing Boxes," which have built-in GPUs capable of efficiently running Local LLM Agents. The terminal-side LLM is the core of the Agent, possessing powerful natural language understanding and generation capabilities, able to transform user natural language commands into executable tasks. As user-side intelligent terminals, these small computing boxes undertake a large number of real-time, personalized computing tasks, effectively reducing the pressure on the cloud center and ensuring localized processing of user data.

* **Cloud-Edge Synergy & Agent Empowerment**
    The essence of this architecture lies in the close synergy between the cloud and the edge. The cloud center supports a Data Pushing mechanism, which synchronizes customized satellite data precisely and periodically to the small computing boxes on the edge side according to the tenant's subscription strategy. At the same time, cloud Business Tools can also be distributed to the edge side on demand for the local LLM to call. For example, in businesses such as "Dynamic Spatiotemporal Coverage Simulation" and "Natural Language Asset Interaction," the user issues commands via LLM at the edge, and the LLM calls the locally distributed tools to calculate and respond, achieving a closed business loop. For businesses like "Intelligent Satellite Pass Prediction," "Intelligent Chart Generation," and "Satellite Life Monitoring," the edge LLM combines local data and tools to quickly generate forecast results, visualization charts, and monitoring reports.

* **Tenant Customized Service**
    To meet the differentiated needs of different tenants, the system supports personalized data distribution based on tenant subscription. This means that each tenant's edge computing box will only receive the satellite data it focuses on, avoiding unnecessary data transmission and storage overhead. This design not only improves system efficiency but also enhances data security and privacy.

## **Feature Showcase**

### **Coverage Simulation & Analysis**

The platform supports the simulation of coverage by optical remote sensing satellites over target areas. The system can generate detailed simulation reports, supports streaming output of simulation results, and utilizes the STK engine to ensure calculation precision.

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/56fb75db-716c-4739-ba9e-ae5feefd0da7" />
</div>

### **3D Visualization Interaction**

The frontend provides an intuitive 3D Earth view, supporting:

* Real-time rendering of satellite trajectories.
* Automatic extrapolation of satellite orbital states.

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/600000ed-cb85-4b4b-aab5-295b5b83e585" />
</div>

### **Resource & Data Management**

* **Constellation Management:** Supports automatic identification and classification of preset constellations such as GPS, Starlink, and Beidou, while also supporting the upload of custom constellation configurations.
* **Data Synchronization:** Built-in timer automatically synchronizes the latest TLE (Two-Line Element) data from the CelesTrak API.

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/4f72d1a6-51a0-4fcc-9836-7a648fe31173" />
</div>

### **Intelligent Extension**

The backend has integrated the LLM (Ollama) interface, providing AI-based dialogue assistance functions to prepare for future human-computer interaction and automated Agent orchestration.

<div align="center">
  <img width="60%" alt="image" src="https://github.com/user-attachments/assets/a6d64e1c-d41f-46c6-9122-7a45279a020c" />
</div>

## **Open Source Repositories**
SpaceMV-ScAI follows the Apache 2.0 (Backend) and AGPL 3.0 (Frontend) open source protocols. We welcome developers and researchers in related fields to follow, use, and contribute code.

* Backend Repository: https://github.com/tianxunweixiao/SpaceMV-ScAI-backend
* Frontend Repository: https://github.com/tianxunweixiao/SpaceMV-ScAI-frontend
