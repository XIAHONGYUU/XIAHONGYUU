# Hi, I'm XIAHONGYUU 👋

**模拟电路 × AI × 工程工具**

我关注如何把模拟设计与版图经验转化为可执行的约束、可复核的数据和可持续迭代的工具。这里记录我的项目实践与研究思考，涵盖 AI 辅助模拟设计、芯片图像重建、传感器读出，以及 Agent 与内容工作流。

📧 **邮箱**：[zuokaiyuann@foxmail.com](mailto:zuokaiyuann@foxmail.com)　｜　💬 **微信**：`ZUOKAIYUANN`

## 最近在做

### 📐 [Analog2Layout](https://github.com/XIAHONGYUU/Analog2Layout)

**把模拟设计意图转化为可执行的版图白线、面积数据与 Layout Card。**

从真实网表出发，先解决“每个管子是干什么的”的语义层，再把 W/L/m、匹配组、ring/DNW、R/C 和面积约束编译成可复核的白线意图。

![Area-first class-A white-line](https://raw.githubusercontent.com/XIAHONGYUU/Analog2Layout/main/examples/classa_opamp/area-min.png)

- **当前白线案例**：16-MOS class-A，面积优先版 **225.9 × 69.8 µm / 15,766 µm² / 74.6% utilization**；R/C 在主 DNW 内并带 AA ring，M14 在外侧独立 DNW。
- **白线不只一张图**：同时保留 balanced baseline、阵列细节和长宽比候选；面积口径明确区分有效面积与 DNW bbox。
- **正在做**：把 schematic → annotation → white-line 封装为 **hybrid prompt + deterministic scripts** 的 skill；JSON schema、class-A golden case 和 5T annotated schematic 已完成。
- **边界**：白线是 layout intent，不是 DRC/LVS/PEX signoff。

[Area-first white-line](https://github.com/XIAHONGYUU/Analog2Layout/blob/main/examples/classa_opamp/area-min.png) · [Balanced baseline](https://github.com/XIAHONGYUU/Analog2Layout/blob/main/examples/classa_opamp/white-line.png) · [Aspect candidates](https://github.com/XIAHONGYUU/Analog2Layout/blob/main/examples/classa_opamp/aspect-candidates.png) · [Class-A README](https://github.com/XIAHONGYUU/Analog2Layout/blob/main/examples/classa_opamp/README.md) · [Layout Guideline](https://github.com/XIAHONGYUU/Analog2Layout/tree/main/layout-guideline)

### 🔁 [AnalogLoop](https://github.com/XIAHONGYUU/AnalogLoop)

**面向 AI 辅助模拟电路设计的参考架构。**

围绕参数优化中的仿真成本、设计意图与验证可信度，讨论 LLM 策略层、确定性执行工具链、快速代理模型和真实 SPICE 验证之间的分工。

- 用语义网表表达器件角色、匹配关系和可调范围。
- 把面积预算、验证晋级条件与实验记录纳入设计流程。
- **当前交付**：架构文档、工具契约与示例规范；v1.0.0 为架构笔记冻结版，可运行的优化闭环仍在路线图中。

[看架构与评审入口](https://github.com/XIAHONGYUU/AnalogLoop/blob/main/docs/for-reviewers.md)

### 🔬 [SiliconEye](https://github.com/XIAHONGYUU/SiliconEye)

**从多层芯片照片出发，用版图约束与人工复核逐步重建材料、器件和连接。**

将模拟版图经验用于图像重建：结合图像算法、AI 观察、规则几何与增量修订，让来源照片、器件编号和跨层关系可以相互追溯。

- **交互案例**：AA/POLY/CT 材料规则重建、器件编号与连接、五层导体联合复核。
- **工程重点**：记录错误与修订依据，让局部改善能够接续已有结果，并检查是否引入退化。
- **当前阶段**：同一颗芯片上的人机协作研究原型；全芯片自动恢复、工艺 DRC/LVS 和仿真就绪网表仍待完成。

[打开交互 Demo →](https://xiahongyuu.github.io/SiliconEye/) · [看质量纠错案例](https://github.com/XIAHONGYUU/SiliconEye/blob/main/docs/portfolio/quality-case.md)

## 传感与集成电路研究

| 项目 | 关注的问题 | 阅读入口 |
| --- | --- | --- |
| [FIBER-SENSOR-IC](https://github.com/XIAHONGYUU/FIBER-SENSOR-IC) | 光纤传感如何与集成光子、CMOS 读出及封装测试协同设计。 | [在线报告](https://xiahongyuu.github.io/FIBER-SENSOR-IC/) |
| [GAS-SENSOR-IC](https://github.com/XIAHONGYUU/GAS-SENSOR-IC) | 如何将气敏传感器的电学变化接入可校准、可测试的数模混合读出系统。 | [在线报告](https://xiahongyuu.github.io/GAS-SENSOR-IC/) |

这两项目前以公开研究构想、文献整理与技术交流为主，具体进度和待验证问题见各自仓库。

## Agent、工作流与其他探索

| 项目 | 内容 |
| --- | --- |
| [Hermes Ops](https://github.com/XIAHONGYUU/hermes-ops) | 单容器 Hermes Agent 运维工具：定时任务监控、容器规格记录、重建与凭据诊断。 |
| [Hermes Skills](https://github.com/XIAHONGYUU/hermes-skills) | 可复用的 Agent Skills：工作区审计、证据检查、结构化提取与运维流程。 |
| [Novel Workspace Pipeline](https://github.com/XIAHONGYUU/novel-workspace-pipeline) | 长篇小说的分层分析工作区，覆盖章节骨架、开篇、人物、大纲与高光场景，支持续跑、校验和交接。 |
| [Novel Outline Workspace](https://github.com/XIAHONGYUU/Novel-Outline-Workspace) | 面向原创小说策划，组织设定、大纲、时间线与想法，支持一致性检查和合并流程。 |
| [Home Automation Notes](https://github.com/XIAHONGYUU/home-automation-notes) | 全屋智能与 AI Agent 架构笔记，讨论协议、设备、控制边界和选型依据。 |

## 欢迎交流

欢迎交流模拟电路与版图、AI 辅助设计、芯片图像重建、传感器读出，以及 Agent 与知识工作流。

项目问题和改进建议可以提交到对应仓库的 Issues，也可以通过上方邮箱或微信联系我。
