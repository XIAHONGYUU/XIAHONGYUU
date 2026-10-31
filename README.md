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

**以仿真预算为中心、可复现的模拟电路设计 Agent 架构。**

不是把 LLM 当仿真器，而是把策略、确定性工具链、两层验证和可复盘账本分开。

![AnalogLoop architecture](https://raw.githubusercontent.com/XIAHONGYUU/AnalogLoop/main/diagrams/png/architecture.png)

- **两层验证**：代理模型做探索/排序，真实 SPICE 做签核；晋级门显式决定何时升级。
- **语义网表 + validator**：role/match/ratio/tunable 写入 `roles.yaml`；名字只是提示，manifest 是事实，validator 是仲裁。
- **面积进入闭环**：角色感知面积、三值面积门、Pareto 选择，而不是事后统计。
- **执行与复原**：ASST 固化 CLI/config/measure/archive；给定 run 可在另一台机器复原。
- **当前交付**：v1.0.0 architecture note freeze；架构、契约、规范，不是可运行闭环或流片验证。

[架构图](https://github.com/XIAHONGYUU/AnalogLoop/blob/main/diagrams/png/architecture.png) · [10 分钟评审入口](https://github.com/XIAHONGYUU/AnalogLoop/blob/main/docs/for-reviewers.md) · [语义网表图](https://github.com/XIAHONGYUU/AnalogLoop/blob/main/diagrams/png/netlist-semantics.png) · [面积与 layout handoff](https://github.com/XIAHONGYUU/AnalogLoop/blob/main/docs/area-and-layout.md)

### 🔬 [SiliconEye](https://github.com/XIAHONGYUU/SiliconEye)

**从同一颗芯片的 8 张逐层照片出发，把模拟版图经验变成可执行、可复核的逆向重建约束。**

![SiliconEye overview](https://raw.githubusercontent.com/XIAHONGYUU/SiliconEye/main/site/assets/overview.webp)

- **真实案例**：AA/POLY/CT 材料规则重建、MOS 栅指编号、M1/V1/M2/V2/M3 五层联合复核。
- **质量门**：从六孔 V1 组接窄 M2-A 的错误出发，增加孔数、完整阵列和上下承载检查；局部改善可继承，但不允许退化。
- **结果边界**：AA/POLY/CT 工作层对象数；8 个历史任务（2 个机器评分、6 个人工 rubric）；2 条失败记录公开；不把“测试通过”当识别准确率。
- **当前阶段**：一颗芯片上的人机协作研究原型；全芯片自动恢复、真实工艺 DRC/LVS、仿真就绪网表仍待完成。

[打开交互 Demo →](https://xiahongyuu.github.io/SiliconEye/) · [质量纠错案例](https://github.com/XIAHONGYUU/SiliconEye/blob/main/docs/portfolio/quality-case.md) · [评测基准](https://github.com/XIAHONGYUU/SiliconEye/blob/main/benchmarks/portfolio-quality-v1/README.md) · [三个交互案例](https://github.com/XIAHONGYUU/SiliconEye/blob/main/docs/portfolio/cases.md)

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
