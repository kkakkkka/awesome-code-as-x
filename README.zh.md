<div align="center">

# Awesome Code as Policy/World/Editor

**把程序当作中间表示的 coding agent。** </br>

<p align="center">
  <img src="assets/awesome-code-as-x.png" alt="Awesome Code as X" width="100%" style="border-radius: 15px; box-shadow: 0 4px 24px rgba(0,0,0,.1); margin: 5px 0;">
</p>

[English](README.md) | [Blog](https://huggingface.co/blog/kkakkkka/from-coding-agents-to-physical-agents) | [SourceMind](assets/sourcemind.jpg) | [中文](README.zh.md) | [公众号文章](https://mp.weixin.qq.com/s/MuOz0KmmQa5CxzjY7WEEvA)

</div>

## Overview
- 🎯 [目标](#目标)
- 📚 [定义](#定义)
- 🦾 [Code as Policy](#code-as-policy)
- 🗺️ [Code as World](#code-as-world)
- 🧮 [Programmable World Models](#programmable-world-models)
- ✂️ [Edit Graph](#edit-graph)
- 📊 [Benchmark](#benchmark)
    - [策略程序](#策略程序)
    - [世界程序](#世界程序)
    - [机器人评测基础设施](#机器人评测基础设施)
- 📚 [综述与经验](#综述与经验)
- 🛠️ [Projects](#projects)
    - [评测报告](#评测报告)
    - [仿真策略程序](#仿真策略程序)
    - [真机策略程序](#真机策略程序)
    - [规划后调用 VLA](#规划后调用-vla)
    - [从视频反演世界程序](#从视频反演世界程序)
    - [编写 RL 训练栈](#编写-rl-训练栈)
    - [场景程序](#场景程序)
- 🔗 [相关资源](#相关资源)

## 目标
agent 写出或改好程序、工具图或可检查的世界状态，再交给仿真器、渲染器、机器人或编辑器去跑。应用场景包括：机器人策略、可执行场景、可编程世界模型、图像和视频编辑图，以及评测这些 agent 的 benchmark。没有论文、但是系统、评测或案例合集的，放进 Projects，不塞进论文栏目。

有新论文和项目会继续加。欢迎补充。

## 定义

- [Policy program](#def-policy-program)
- [World program](#def-world-program)
- [Programmable world model](#def-programmable-world-model)
- [Edit graph](#def-edit-graph)
- [Benchmark](#def-benchmark)
- [Project](#def-project)

<a id="def-policy-program"></a>
**Policy program.** Code-as-Policy 用 LLM / VLM 当高层 agent，写出可执行的机器人程序，或者一层很薄的语义动作接口，用来替代 VLA 动作 token。这个说法来自 Code as Policies。

- [⭐️] **Code as Policies**: Language Model Programs for Embodied Control. [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b.svg)](https://arxiv.org/abs/2209.07753) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-policies.github.io)

<a id="def-world-program"></a>
**World program.** World program 是可执行的场景或物理程序，比如 Blender、MuJoCo、USD、CadQuery，不是静态 mesh，也不是视频。从语言或布局写出来叫生成；从图像、视频或扫描写回去叫反演。

- [⭐️] **SceneCode**: Executable World Programs for Editable Indoor Scenes with Articulated Objects. [![arXiv](https://img.shields.io/badge/arXiv-2605.19587-b31b1b.svg)](https://arxiv.org/abs/2605.19587) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://scene-code.github.io/)

Physical Coding 来自 Self-Evolving Coding Agents: From Digital Programs to Physical-World Intelligence，也用 Code as World 表示机器人任务状态：对象、关系、约束、观测和进度谓词。这个用法和下面按可执行场景程序归类的 World Program 不同；参见 [Physical Coding / HexaAnything](#code-as-policy)。 [![arXiv](https://img.shields.io/badge/arXiv-2609.35432-b31b1b.svg)](https://arxiv.org/abs/2609.35432) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HexaFuture/PhysicalCoding)

<a id="def-programmable-world-model"></a>
**Programmable world model.** 可编程世界模型把状态和转移写在代码里。生成模型或渲染器只管外观。

- [⭐️] **Code World Model**: Coding Agent as World Brain. [![arXiv](https://img.shields.io/badge/arXiv-2608.25927-b31b1b.svg)](https://arxiv.org/abs/2608.25927) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://buaacyw.github.io/cwm/)

<a id="def-edit-graph"></a>
**Edit graph.** 编辑图是一次可检查、可回滚的修改：工具调用序列、视觉程序，或时间线补丁。VisProg 是比较早的例子。

- [⭐️] **VisProg**, Visual Programming: Compositional Visual Reasoning Without Training. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://prior.allenai.org/projects/visprog)

<a id="def-benchmark"></a>
**Benchmark.** 这类 benchmark 测的是 coding agent 能不能写出、跑通、改好一份程序。RLE-Bench 是策略这一侧：机器人学习、训练栈和控制。PhysCodeGym 是世界这一侧：把视频重建成可执行的 Blender 程序，并检查物理是否成立。

- [⭐️] **RLE-Bench**: A Qualifying Exam for Coding Agents as Robot Learning Engineers. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rle-bench.github.io/)

- [⭐️] **PhysCodeGym**: Benchmarking Coding Agents for Physically Verifiable 4D Reconstruction. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/ShaoShuai0605/PhysCodeGym) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://huggingface.co/datasets/ShaoShuai0605/PhysCodeGym)

<a id="def-project"></a>
**Project.** 这里收 X、小红书、只有网页的系统和案例合集，主产物不是论文。agent 可能写机器人程序、世界程序、RL 训练栈，或一层很薄的控制接口。

- [⭐️] **Awesome Astra Embodied AI**: GPT-6 Astra 的具身 / 机器人工作流和 demo。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI)

## Code as Policy

- [⭐️] **Code as Policies**: Language Model Programs for Embodied Control. [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b.svg)](https://arxiv.org/abs/2209.07753) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-policies.github.io)

- [⭐️] **CaP-X**: A Framework for Benchmarking and Improving Coding Agents for Robot Manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2603.22435-b31b1b.svg)](https://arxiv.org/abs/2603.22435) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://capgym.github.io)

- [⭐️] **RATs**, Playful Agentic Robot Learning. [![arXiv](https://img.shields.io/badge/arXiv-2606.19419-b31b1b.svg)](https://arxiv.org/abs/2606.19419) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://Playful-RATs.github.io/)

- [⭐️] **Show-Harness**: Just a VLM Agent Can Play Robots. [![arXiv](https://img.shields.io/badge/arXiv-2609.10522-b31b1b.svg)](https://arxiv.org/abs/2609.10522) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://showlab.github.io/Show-Harness/)

- **RACaP**, Agentic Reasoning, Acting, and Coding as Policies for Evolvable Robot Learning：离线进化 typed Policy API，运行时由 ReAct loop 调用冻结 API。 [![arXiv](https://img.shields.io/badge/arXiv-2609.29394-b31b1b.svg)](https://arxiv.org/abs/2609.29394)

- **RoboDawn**, Transferring the Intelligence of VLMs to Robotic Control：给 VLM 一层很薄的离散命令接口，把 `move`、`rotate`、`gripper` 等命令落到运动规划里。 [![arXiv](https://img.shields.io/badge/arXiv-2609.22966-b31b1b.svg)](https://arxiv.org/abs/2609.22966) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robodawn.top/)

- **GPT-Policy**, In-Context Robot Learning with VLM Agents：把上下文编译给 VLM agent，再经受约束的控制器发出机器人工具命令。 [![arXiv](https://img.shields.io/badge/arXiv-2609.19138-b31b1b.svg)](https://arxiv.org/abs/2609.19138) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://cheng-haha.github.io/GPT-Policy/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/cheng-haha/GPT-Policy-Eval)

- **RoboDojo GPT-6 Astra evaluation**, An Unexpected Robot Policy: Early Evaluations of GPT-6 Astra on RoboDojo and Beyond：把 VLM policy 放进固定 RoboProbe harness，跑 42 个仿真任务、2100 次试验；报告平均分 28.97、平均成功率 22.48%，真机测试因安全原因中止。 [![arXiv](https://img.shields.io/badge/arXiv-2609.24170-b31b1b.svg)](https://arxiv.org/abs/2609.24170) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robodojo-benchmark.com/report/gpt-6-astra-eval)

- **SafeHarness**, Coding Agents with an Obstacle-Aware Harness for Safe Robot Manipulation：在路径规划和接触执行中加入障碍感知，减少生成的机器人控制程序发生碰撞的风险。 [![arXiv](https://img.shields.io/badge/arXiv-2609.20822-b31b1b.svg)](https://arxiv.org/abs/2609.20822)

- **WetRobo**, A Reproducible Robot Kit for Coding Agents in Biological Laboratories：让 agent 编写并执行实验室流程，同时调用感知、规划和仿真工具。 [![arXiv](https://img.shields.io/badge/arXiv-2609.18435-b31b1b.svg)](https://arxiv.org/abs/2609.18435)

- **AGP**, Agent as Policy for Robotic Manipulation：运行时写程序、执行程序，并根据物理反馈修改策略。 [![arXiv](https://img.shields.io/badge/arXiv-2609.12541-b31b1b.svg)](https://arxiv.org/abs/2609.12541) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/agent-as-policy-2026/agent-as-policy)

- **PhysCaP**, Grounding Code-as-Policy Agent with Physics-Informed Exploration：通过主动交互估计隐藏的物理属性，为机器人操作提供依据。 [![arXiv](https://img.shields.io/badge/arXiv-2608.21031-b31b1b.svg)](https://arxiv.org/abs/2608.21031) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://physcap.github.io/)

- **Agentic Push-T**, Revisiting the "Push-T" Robot Manipulation Task with Agentic Robotics：让 coding agent 在没有 demonstrations 的情况下为 Push-T 写操作算法。 [![arXiv](https://img.shields.io/badge/arXiv-2608.18227-b31b1b.svg)](https://arxiv.org/abs/2608.18227)

- **GaP**, A Graph-as-Policy Multi-Agent Self-Learning Harness for Variational Automation Tasks：把 policy 表示成有向的感知-规划-控制图，并在仿真里反复改。 [![arXiv](https://img.shields.io/badge/arXiv-2607.05369-b31b1b.svg)](https://arxiv.org/abs/2607.05369)

- **ASPIRE**: Agentic /Skills Discovery for Robotics。根据执行轨迹编写和修复控制程序，把通过验证的修复积累成可复用的技能库。 [![arXiv](https://img.shields.io/badge/arXiv-2607.00272-b31b1b.svg)](https://arxiv.org/abs/2607.00272) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/NVlabs/ASPIRE)

- **ENPIRE**: Agentic Robot Policy Self-Improvement in the Real World。重置场景、执行策略、检查结果，再根据真机反馈修改策略或训练代码。 [![arXiv](https://img.shields.io/badge/arXiv-2606.19980-b31b1b.svg)](https://arxiv.org/abs/2606.19980) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/enpire/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/NVlabs/ENPIRE)

- **Physical Coding / HexaAnything**, Self-Evolving Coding Agents: From Digital Programs to Physical-World Intelligence：用 Code as World 表示符号任务状态，用 Code as Policy 表示执行过程；HexaAnything 经 Harness 路由感知、规划、控制和 VLA / WAM 工具，检查执行结果，并把通过检查的轨迹存成记忆或训练数据。 [![arXiv](https://img.shields.io/badge/arXiv-2609.35432-b31b1b.svg)](https://arxiv.org/abs/2609.35432) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HexaFuture/PhysicalCoding)

- **Harness VLA**: 用记忆和视觉反馈，把冻结的 VLA 调用和解析运动原语拼在一起。 [![arXiv](https://img.shields.io/badge/arXiv-2607.08448-b31b1b.svg)](https://arxiv.org/abs/2607.08448) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://harnessvla.github.io/)

- **Recursive Harness Distillation**：Astra 把解题经验写成 playbook，再根据 Luna 的执行反馈改它，让更便宜的 agent 去指挥冻结的 VLA。 [![arXiv](https://img.shields.io/badge/arXiv-2609.33378-b31b1b.svg)](https://arxiv.org/abs/2609.33378) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://seungyeon.me/RHD/)

- **RoboICL**：冻结的 GPT-6 Astra 靠示范上下文和有界交互记忆控制机器人，不针对机器人微调，也不用学习好的 VLA。 [![arXiv](https://img.shields.io/badge/arXiv-2609.34261-b31b1b.svg)](https://arxiv.org/abs/2609.34261) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://mosi-ai.github.io/RoboICL-GPT6-Astra.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Mosi-AI/RoboICL)

- **SimEX**：coding agent 在仿真里长出感知和动作原语工具箱，再按每条指令写一份新的 code-as-policies 脚本。五次真机试验同时改工具箱和仿真器。 [![arXiv](https://img.shields.io/badge/arXiv-2609.38982-b31b1b.svg)](https://arxiv.org/abs/2609.38982) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robo-simex.github.io/)

- **OpenRUA**：coding agent 在终端里直接用原生 ROS 2，把传感器读数当文件读写，再按执行反馈改操作程序。 [![arXiv](https://img.shields.io/badge/arXiv-2610.02459-b31b1b.svg)](https://arxiv.org/abs/2610.02459)

- **URAI**, Make Code as Policy Great Again：编程 agent 写并修改可复用的机器人工具，执行 agent 在两次完整局部运动之间挑选工具。 [![arXiv](https://img.shields.io/badge/arXiv-2609.39018-b31b1b.svg)](https://arxiv.org/abs/2609.39018)

- **EmbodiedSWE**：coding agent 解长程灵巧任务，再把成功的程序扩成仿真演示，用来训策略。 [![arXiv](https://img.shields.io/badge/arXiv-2609.27308-b31b1b.svg)](https://arxiv.org/abs/2609.27308)

- **SpatialClaw**：VLM 在持久 Python kernel 里一轮轮写代码，几何工具和中间视觉反馈混在一起。 [![arXiv](https://img.shields.io/badge/arXiv-2606.13673-b31b1b.svg)](https://arxiv.org/abs/2606.13673)

- **EmbodiedRSI**：挑有信息量的试验去检验相互竞争的假设，并改可执行代码、技能和记忆，底层机器人模型保持冻结。 [![arXiv](https://img.shields.io/badge/arXiv-2610.10498-b31b1b.svg)](https://arxiv.org/abs/2610.10498)

- **Recova**：coding agent 在数字孪生里找出恢复技能，部署时再用进度检查去调用任务策略和恢复策略。 [![arXiv](https://img.shields.io/badge/arXiv-2610.01178-b31b1b.svg)](https://arxiv.org/abs/2610.01178)

- **PyRUA-Lean**：在持久 Python cell 里组合机器人原语和冻结的 VLA 调用，带本地检查和重试。 [![arXiv](https://img.shields.io/badge/arXiv-2610.01939-b31b1b.svg)](https://arxiv.org/abs/2610.01939)

- **DynaHarness**：把运行时命令落到控制上，监控执行，回归检查通过之后才改可复用的机器人程序。 [![arXiv](https://img.shields.io/badge/arXiv-2609.40306-b31b1b.svg)](https://arxiv.org/abs/2609.40306)

- **HarnessPAI**：用固定任务程序串起感知和动作原语，回合之间改这段代码，留下通过检查的修复技能。 [![arXiv](https://img.shields.io/badge/arXiv-2609.29166-b31b1b.svg)](https://arxiv.org/abs/2609.29166)

- **Eureka**：LLM 根据环境源码和任务描述写 reward 代码，再按 RL 回报改。 [![arXiv](https://img.shields.io/badge/arXiv-2310.12931-b31b1b.svg)](https://arxiv.org/abs/2310.12931)

- **Code-as-Monitor**：生成视觉监控代码，检查时空约束，违规发生前也能触发。 [![arXiv](https://img.shields.io/badge/arXiv-2412.04455-b31b1b.svg)](https://arxiv.org/abs/2412.04455)

- **ReKep**：把语言和 RGB-D 写成 3D 关键点上的 Python 约束函数，再从这些函数解末端动作。 [![arXiv](https://img.shields.io/badge/arXiv-2409.01652-b31b1b.svg)](https://arxiv.org/abs/2409.01652)

- **COAP**，Embodied Turing Machines：改进写成对有状态机器人代码的 diff。共享库写好、测过、改过之后冻结再回放。在 RoboDojo 的 42 个双臂任务上报告成功率 70.24%。 [![arXiv](https://img.shields.io/badge/arXiv-2610.12369-b31b1b.svg)](https://arxiv.org/abs/2610.12369)

- **AgenticGenTAMP**：coding agent 为每个任务与运动规划环境合成一份程序，冻结后再在留出的实例上跑。 [![arXiv](https://img.shields.io/badge/arXiv-2609.30233-b31b1b.svg)](https://arxiv.org/abs/2609.30233) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/tomsilver/robocode)

- **PhysEvo**：模型权重冻结，用 RoboDojo 和真机 AgileX PiPER 上的物理试验改机器人行为。 [![arXiv](https://img.shields.io/badge/arXiv-2610.08995-b31b1b.svg)](https://arxiv.org/abs/2610.08995)

- **VLCP**, Vision Language Control Policy: Closed-Loop Code Replanning for Robot Manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2608.16978-b31b1b.svg)](https://arxiv.org/abs/2608.16978)

- **RHO**, Your Coding Agent is Secretly a Roboticist. [![arXiv](https://img.shields.io/badge/arXiv-2606.16458-b31b1b.svg)](https://arxiv.org/abs/2606.16458)

- **ALRM**, Agentic LLM for Robotic Manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2601.19510-b31b1b.svg)](https://arxiv.org/abs/2601.19510) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://tiiuae.github.io/ALRM)

- **Act-Observe-Rewrite**, Multimodal Coding Agents as In-Context Policy Learners for Robot Manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2603.04466-b31b1b.svg)](https://arxiv.org/abs/2603.04466)

- **HyCodePolicy**, Hybrid Language Controllers for Multimodal Monitoring and Decision in Embodied Agents. [![arXiv](https://img.shields.io/badge/arXiv-2508.02629-b31b1b.svg)](https://arxiv.org/abs/2508.02629)

- **ModuLoop**, Low-Level Code Generation using Modular Synthesizer and Closed-Loop Debugger for Robotic Control. [![arXiv](https://img.shields.io/badge/arXiv-2606.03047-b31b1b.svg)](https://arxiv.org/abs/2606.03047)

- **NeSyRo**, Towards Reliable Code-as-Policies: A Neuro-Symbolic Framework for Embodied Task Planning. [![arXiv](https://img.shields.io/badge/arXiv-2510.21302-b31b1b.svg)](https://arxiv.org/abs/2510.21302)

- **RoboPro**, Robotic Programmer: Video Instructed Policy Code Generation for Robotic Manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2501.04268-b31b1b.svg)](https://arxiv.org/abs/2501.04268) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://video2code.github.io/RoboPro-website/)

- **ProgPrompt**: Generating Situated Robot Task Plans using Large Language Models. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://progprompt.github.io/)

- **VoxPoser**: Composable 3D Value Maps for Robotic Manipulation with Language Models. [![arXiv](https://img.shields.io/badge/arXiv-2307.05973-b31b1b.svg)](https://arxiv.org/abs/2307.05973) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://voxposer.github.io)

- **Instruct2Act**: Mapping Multi-modality Instructions to Robotic Actions with Large Language Model. [![arXiv](https://img.shields.io/badge/arXiv-2305.11176-b31b1b.svg)](https://arxiv.org/abs/2305.11176)

- **Language to Rewards** for Robotic Skill Synthesis. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://language-to-reward.github.io/)

- **Demo2Code**: From Summarizing Demonstrations to Synthesizing Code via Extended Chain-of-Thought. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/portal-cornell/demo2code)

- **Voyager**: An Open-Ended Embodied Agent with Large Language Models. [![arXiv](https://img.shields.io/badge/arXiv-2305.16291-b31b1b.svg)](https://arxiv.org/abs/2305.16291)

- **AdaHVLA**：分开的 agent 分析证据、修改代码 harness，并判断行为，留下假设和观察结果的图。 [![arXiv](https://img.shields.io/badge/arXiv-2609.29204-b31b1b.svg)](https://arxiv.org/abs/2609.29204)

- **RegenHarness**：对任务模板、路由和恢复规则提出带版本的修改，回归检查通过才留下。 [![arXiv](https://img.shields.io/badge/arXiv-2609.27612-b31b1b.svg)](https://arxiv.org/abs/2609.27612)

- **Zetta**：底层策略冻结，从失败诊断和留出集晋升里长出运行时 critic、恢复手册和工具。 [![arXiv](https://img.shields.io/badge/arXiv-2608.16590-b31b1b.svg)](https://arxiv.org/abs/2608.16590) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://air-embodied-brain.github.io/zetta/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/air-embodied-brain/Zetta-Embodiment)

- **SHAPER**：模型权重冻结，用目标环境的 rollout 演化可复用技能和包在外面的 context-code harness。 [![arXiv](https://img.shields.io/badge/arXiv-2608.11350-b31b1b.svg)](https://arxiv.org/abs/2608.11350)

- **VASO**：对照时序规约和模型检验的反例，修改具身技能契约。 [![arXiv](https://img.shields.io/badge/arXiv-2606.05395-b31b1b.svg)](https://arxiv.org/abs/2606.05395) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://languagegroundedriskdetection.github.io/ProjectPage/vaso-webpage)

- **Code-as-Symbolic-Planner**：从多模态任务上下文写出可执行的符号规划代码，再复用这些规划抽象。 [![arXiv](https://img.shields.io/badge/arXiv-2503.01700-b31b1b.svg)](https://arxiv.org/abs/2503.01700) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://yongchao98.github.io/Code-Symbol-Planner)

- **Agentic Skill Discovery**：语言模型写任务和 reward 代码，RL 训练技能，视觉检查决定能不能进持久技能库。 [![arXiv](https://img.shields.io/badge/arXiv-2405.15019-b31b1b.svg)](https://arxiv.org/abs/2405.15019) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://agentic-skill-discovery.github.io)

- **RAX**：coding agent 在线探索机器人任务，记下成功的前提、动作和效果，再编译出不依赖 agent 也能跑的 Python 控制器。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robot-agent-exploration.com/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/robot-agent-exploration/rax)

- **ASENA**：把 coding agent 接到机器人感知、受监督执行和持久经验上。学出来的导航策略可以作为工具调用。模型权重固定，重复任务会变好。 [![arXiv](https://img.shields.io/badge/arXiv-2609.39207-b31b1b.svg)](https://arxiv.org/abs/2609.39207) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/asena/)

## Code as World

### Generation

- [⭐️] **SceneCode**: Executable World Programs for Editable Indoor Scenes with Articulated Objects. [![arXiv](https://img.shields.io/badge/arXiv-2605.19587-b31b1b.svg)](https://arxiv.org/abs/2605.19587) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://scene-code.github.io/)

- [⭐️] **VideoCoCo**: Code-as-CoT for Physically-Consistent Video Generation via an Agentic Dual-Engine System. [![arXiv](https://img.shields.io/badge/arXiv-2607.27380-b31b1b.svg)](https://arxiv.org/abs/2607.27380) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/micky-li-hd/VideoCoCo)

- **Code Video Model**：把提示写成 Three.js 程序当可执行预演，渲出代理视频和参考图，再只在采样早期把代理视频条件送进预训练视频模型。改代码就能改布局、运动和相机，然后再出成片。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-video-model.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/code-video-model/CodeVideoModel)

- **EmbodiedGen V2**：agent 搭建并编辑资产、多房间场景和任务环境，物理检查之后导出 URDF、USD 或 MJCF。 [![arXiv](https://img.shields.io/badge/arXiv-2607.07459-b31b1b.svg)](https://arxiv.org/abs/2607.07459) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HorizonRobotics/EmbodiedGen)

- **SimFoundry**：模块化的视频到仿真流程，重建物体、编译物理场景，并在 OmniGibson 里提出任务。 [![arXiv](https://img.shields.io/badge/arXiv-2606.28276-b31b1b.svg)](https://arxiv.org/abs/2606.28276) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/NVlabs/SimFoundry)

- **Procedura**：agent 搭的三维装配，零件有名字，连接是可机器检查的类型约束。 [![arXiv](https://img.shields.io/badge/arXiv-2608.26238-b31b1b.svg)](https://arxiv.org/abs/2608.26238)

- **Articraft**：做可动关节三维资产的 agent 流程。 [![arXiv](https://img.shields.io/badge/arXiv-2605.15187-b31b1b.svg)](https://arxiv.org/abs/2605.15187)

- **HARMONY**：分层 agent 推理，把一张图写成场景程序。 [![arXiv](https://img.shields.io/badge/arXiv-2609.26793-b31b1b.svg)](https://arxiv.org/abs/2609.26793) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://cwchenwang.github.io/harmony/)

- **AssemblyWorld**：通用 agent 从渲染图和零件记录做三维装配，不看网格顶点。 [![arXiv](https://img.shields.io/badge/arXiv-2609.40353-b31b1b.svg)](https://arxiv.org/abs/2609.40353) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/AssemblyWorld/assembly-world-bench)

- **USDCraft**：LLM 写并修改程序，把网格和参考图做成仿真可用的关节 USD 资产。 [![arXiv](https://img.shields.io/badge/arXiv-2610.11322-b31b1b.svg)](https://arxiv.org/abs/2610.11322)

- **AffordCraft**：一张照片加任务说明，做成任务可用的仿真资产。 [![arXiv](https://img.shields.io/badge/arXiv-2610.06643-b31b1b.svg)](https://arxiv.org/abs/2610.06643)

- **Agentic RSR**：通过场景重建和执行落地的机器人策略做 real-to-sim-to-real。 [![arXiv](https://img.shields.io/badge/arXiv-2610.10479-b31b1b.svg)](https://arxiv.org/abs/2610.10479)

- **Artisan**：多智能体流程，做物理上站得住的关节三维资产。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://physicalvision.github.io/artisan/)

- **Code-as-Room**: Generating 3D Rooms from Top-Down View Images via Agentic Code Synthesis. [![arXiv](https://img.shields.io/badge/arXiv-2605.18451-b31b1b.svg)](https://arxiv.org/abs/2605.18451) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-room.github.io/)

- **RoomWright**, Beyond Placement and Articulation: Usage-Driven Code Scenes for Embodied Interaction. [![arXiv](https://img.shields.io/badge/arXiv-2608.18840-b31b1b.svg)](https://arxiv.org/abs/2608.18840)

- **SR-Platform**: An Agentic Pipeline for Natural Language-Driven Robot Simulation Environment Synthesis. [![arXiv](https://img.shields.io/badge/arXiv-2605.14700-b31b1b.svg)](https://arxiv.org/abs/2605.14700)

- **GS-Agent**: Creating 4D Physical Worlds With Generative Simulation. [![arXiv](https://img.shields.io/badge/arXiv-2607.21522-b31b1b.svg)](https://arxiv.org/abs/2607.21522) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://umass-embodied-agi.github.io/gs-agent/)

- **SceneCraft**: An LLM Agent for Synthesizing 3D Scenes as Blender Code. [![arXiv](https://img.shields.io/badge/arXiv-2403.01248-b31b1b.svg)](https://arxiv.org/abs/2403.01248)

- **3D-GPT**: Procedural 3D Modeling with Large Language Models. [![arXiv](https://img.shields.io/badge/arXiv-2310.12945-b31b1b.svg)](https://arxiv.org/abs/2310.12945)

- **LL3M**: Large Language 3D Modelers. [![arXiv](https://img.shields.io/badge/arXiv-2508.08228-b31b1b.svg)](https://arxiv.org/abs/2508.08228)

### Inversion / Reconstruction

- [⭐️] **NeoWorld-Pro**: Programming Interactive Scenes from Monocular Images for Embodied Simulation. [![arXiv](https://img.shields.io/badge/arXiv-2608.24212-b31b1b.svg)](https://arxiv.org/abs/2608.24212) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://neoworldproject.github.io/neoworld-pro-website/)

- [⭐️] **Code as Worlds**: Agentic Discovery of Executable World Representations for Physical Reasoning. [![arXiv](https://img.shields.io/badge/arXiv-2608.27549-b31b1b.svg)](https://arxiv.org/abs/2608.27549) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://mirros-lab.github.io/code-as-world/)

- [⭐️] **LiteReality-Agent**: An Agentic System for Interactable 3D Indoor Scene Reconstruction. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://litereality.github.io/agent/)

- **VIGA**, Vision-as-Inverse-Graphics Agent via Interleaved Multimodal Reasoning. [![arXiv](https://img.shields.io/badge/arXiv-2601.11109-b31b1b.svg)](https://arxiv.org/abs/2601.11109) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://fugtemypt123.github.io/VIGA-website)

- **Thinking in Blender**: Staged Executable Inverse Graphics with Vision-Language Models. [![arXiv](https://img.shields.io/badge/arXiv-2606.02580-b31b1b.svg)](https://arxiv.org/abs/2606.02580)

- **RCWM**, Recursive Code World Models: Building Complex Worlds through Recursive Scene Programs. [![arXiv](https://img.shields.io/badge/arXiv-2609.11499-b31b1b.svg)](https://arxiv.org/abs/2609.11499)

- **VisPhyWorld**: Probing Physical Reasoning via Code-Driven Video Reconstruction. [![arXiv](https://img.shields.io/badge/arXiv-2602.13294-b31b1b.svg)](https://arxiv.org/abs/2602.13294) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/TIGER-AI-Lab/VisPhyWorld)

- **AstraLOD3**: 多视图证据重建可编辑建筑。 [![arXiv](https://img.shields.io/badge/arXiv-2609.28061-b31b1b.svg)](https://arxiv.org/abs/2609.28061)

- **RoboSimStudio**：人和 coding agent 对照观察到的机器人行为，修改 Newton 仿真里的场景和物理参数。 [![arXiv](https://img.shields.io/badge/arXiv-2610.18835-b31b1b.svg)](https://arxiv.org/abs/2610.18835) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robosimstudio.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/robosimstudio/robosimstudio)

## Programmable World Models

- [⭐️] **Code World Model**: Coding Agent as World Brain. [![arXiv](https://img.shields.io/badge/arXiv-2608.25927-b31b1b.svg)](https://arxiv.org/abs/2608.25927) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://buaacyw.github.io/cwm/)

- [⭐️] **Programmable World Model**. [![arXiv](https://img.shields.io/badge/arXiv-2609.10540-b31b1b.svg)](https://arxiv.org/abs/2609.10540) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://alaya-lab.github.io/pwm/)

- **PoE-World**: Compositional World Modeling with Products of Programmatic Experts. [![arXiv](https://img.shields.io/badge/arXiv-2505.10819-b31b1b.svg)](https://arxiv.org/abs/2505.10819) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://topwasu.github.io/poe-world)

- **PatchWorld**: Gradient-Free Optimization of Executable World Models for Agent Environments. [![arXiv](https://img.shields.io/badge/arXiv-2605.30880-b31b1b.svg)](https://arxiv.org/abs/2605.30880) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/HKBU-KnowComp/PatchWorld)

- **Mind-Studio**: Executable World Models with Lookahead Evaluation for Partially Observable Games. [![arXiv](https://img.shields.io/badge/arXiv-2606.16070-b31b1b.svg)](https://arxiv.org/abs/2606.16070) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/HKBU-KnowComp/MindStudio)

- **CWM-GGP**, Code World Models for General Game Playing. [![arXiv](https://img.shields.io/badge/arXiv-2510.04542-b31b1b.svg)](https://arxiv.org/abs/2510.04542)

- **Web World Models**. [![arXiv](https://img.shields.io/badge/arXiv-2512.23676-b31b1b.svg)](https://arxiv.org/abs/2512.23676) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://princeton-ai2-lab.github.io/Web-World-Models/)

- **gWorld**, Generative Visual Code Mobile World Models. [![arXiv](https://img.shields.io/badge/arXiv-2602.01576-b31b1b.svg)](https://arxiv.org/abs/2602.01576) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://trillionlabs-gworld.github.io)

- **WorldCoder**: Building World Models by Writing Code and Interacting with the Environment. [![arXiv](https://img.shields.io/badge/arXiv-2402.12275-b31b1b.svg)](https://arxiv.org/abs/2402.12275)

- **GIF-MCTS**, Generating Code World Models with Large Language Models Guided by Monte Carlo Tree Search. [![arXiv](https://img.shields.io/badge/arXiv-2405.15383-b31b1b.svg)](https://arxiv.org/abs/2405.15383)

- **Baba in Wonderland**：在线发现动力学，并写成可执行的世界模型。 [![arXiv](https://img.shields.io/badge/arXiv-2605.16725-b31b1b.svg)](https://arxiv.org/abs/2605.16725)

- **Tycho**：用主动抽象为 ARC-AGI-3 建立程序化世界模型。 [![arXiv](https://img.shields.io/badge/arXiv-2607.28287-b31b1b.svg)](https://arxiv.org/abs/2607.28287) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/NIMI-research/Tycho)

- **WALL-E**：学出对齐世界模型的规则，再拿这些规则做 LLM agent 规划。 [![arXiv](https://img.shields.io/badge/arXiv-2410.07484-b31b1b.svg)](https://arxiv.org/abs/2410.07484)

- **WALL-E 2.0**：学神经符号规则，让世界模型 agent 在环境变化时还能改。 [![arXiv](https://img.shields.io/badge/arXiv-2504.15785-b31b1b.svg)](https://arxiv.org/abs/2504.15785) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/elated-sawyer/WALL-E)

- **VisualPredicator**：把神经符号谓词学成抽象世界模型，用来做机器人规划。 [![arXiv](https://img.shields.io/badge/arXiv-2410.23156-b31b1b.svg)](https://arxiv.org/abs/2410.23156)

## Edit Graph

- [⭐️] **VisProg**, Visual Programming: Compositional Visual Reasoning Without Training. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://prior.allenai.org/projects/visprog)

- [⭐️] **IEAP**, Image Editing As Programs with Diffusion Models. [![arXiv](https://img.shields.io/badge/arXiv-2506.04158-b31b1b.svg)](https://arxiv.org/abs/2506.04158) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/YujiaHu1109/IEAP)

- [⭐️] **EditDuet**: A Multi-Agent System for Video Non-Linear Editing. [![arXiv](https://img.shields.io/badge/arXiv-2509.10761-b31b1b.svg)](https://arxiv.org/abs/2509.10761) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://mudtriangle.com/editduet)

- [⭐️] **VideoAgent**: All-in-One Framework for Video Understanding and Editing. [![arXiv](https://img.shields.io/badge/arXiv-2606.23327-b31b1b.svg)](https://arxiv.org/abs/2606.23327) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/HKUDS/VideoAgent)

- **CoSTA\***: Cost-Sensitive Toolpath Agent for Multi-turn Image Editing. [![arXiv](https://img.shields.io/badge/arXiv-2503.10613-b31b1b.svg)](https://arxiv.org/abs/2503.10613) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/tianyi-lab/CoSTAR)

- **FaSTA\***: Fast-Slow Toolpath Agent with Subroutine Mining for Efficient Multi-turn Image Editing. [![arXiv](https://img.shields.io/badge/arXiv-2506.20911-b31b1b.svg)](https://arxiv.org/abs/2506.20911) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/tianyi-lab/FaSTAR)

- **Lego-Edit**: A General Image Editing Framework with Model-Level Bricks and MLLM Builder. [![arXiv](https://img.shields.io/badge/arXiv-2509.12883-b31b1b.svg)](https://arxiv.org/abs/2509.12883) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/xiaomi-research/lego-edit)

- **CanvasAgent**: Enabling Complex Image Creation and Editing via Visual Tool Orchestration. [![arXiv](https://img.shields.io/badge/arXiv-2607.05465-b31b1b.svg)](https://arxiv.org/abs/2607.05465) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/GML-FMGroup/CanvasAgent)

- **IMAGAgent**: Orchestrating Multi-Turn Image Editing via Constraint-Aware Planning and Reflection. [![arXiv](https://img.shields.io/badge/arXiv-2603.29602-b31b1b.svg)](https://arxiv.org/abs/2603.29602) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/hackermmzz/IMAGAgent)

- **RefineCut**, Plans You Can Check: Verifier-Grounded Learning of an Open-Weight Planner for Executable Video-Editing. [![arXiv](https://img.shields.io/badge/arXiv-2608.25622-b31b1b.svg)](https://arxiv.org/abs/2608.25622) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/Lancelot-wy/RefineCut)

## Benchmark

### 策略程序

agent 写出、跑通或修改机器人控制或学习程序。

- [⭐️] **RLE-Bench**: A Qualifying Exam for Coding Agents as Robot Learning Engineers. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rle-bench.github.io/)

- **CodeActionBench**：25 个仿真双臂任务，agent 对着机器人 API 写代码、跑代码、改代码，用 RGB 和标定几何，不用深度图或特权状态。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/lyhkk/CodeActionBench)

- **LIBERO-Agent**：通用 agent 自己选观测、发原生机器人命令；评测拆成感知、短程执行和长程操作。 [![arXiv](https://img.shields.io/badge/arXiv-2609.39507-b31b1b.svg)](https://arxiv.org/abs/2609.39507) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/dzj441/Libero-Agent)

- **RoboQuest**：10 个仿真厨房移动操作任务，通用 agent 通过工具调用发机器人命令，要先搜索、检查或测试物体找到隐藏信息，再按 SUBMIT 提交。Astra 在 5 个前沿 agent 里排第一（成功率 23.2%）。 [![arXiv](https://img.shields.io/badge/arXiv-2610.10388-b31b1b.svg)](https://arxiv.org/abs/2610.10388) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://declare-lab.github.io/RoboQuest/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/declare-lab/RoboQuest)

- **AA-Robotics v0.1**：真机 Hiwonder NexArm 上 8 个桌面任务。coding agent 在隔离容器里通过 HTTP API 和四路相机控制机械臂，人按终态打分。GPT-6 Astra 69.4，五个模型里第一。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://artificialanalysis.ai/articles/aa-robotics)

### 世界程序

agent 写出可执行的场景、CAD 或物理程序，再交给渲染器或仿真器去跑。

- [⭐️] **PhysCodeGym**：156 个任务，coding agent 把参考视频重建成可执行的 Blender 程序。评分同时看渲染结果和场景里的物理行为，包括反事实干预。配 Codex 时，GPT-6 Astra 总分 0.663 排第一。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/ShaoShuai0605/PhysCodeGym) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://huggingface.co/datasets/ShaoShuai0605/PhysCodeGym)

- **4DCodeBench**：agent 写可执行代码，从 200 段视频重建动态场景。Astra Max 在 18 个 agent 里总分 0.79 排第一，动态项领先 31%。 [![arXiv](https://img.shields.io/badge/arXiv-2610.03715-b31b1b.svg)](https://arxiv.org/abs/2610.03715) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://4dcodebench.com/)

- **Video2World**：189 段具身视频拆成 222 个任务，coding agent 重建可交互仿真世界。Astra 在 9 个 agent 里排第 2（V2WScore 43.55，成功率 10.7%），几何最准，但仍远低于人工辅助参考。 [![arXiv](https://img.shields.io/badge/arXiv-2610.04432-b31b1b.svg)](https://arxiv.org/abs/2610.04432) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://aetherlabsai.github.io/Video2World/)

- **BVB**：agent 把每段视频重建成 Blender 程序，再在这份程序上回答时空问题。论文选出的前沿配置里，Astra high 总分 70.07，51 个里排第一。2026-10-14 的实时榜有 63 个配置，Astra xhigh 为 73.82，排第一。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://frank-zy-dou.github.io/awesome-ai-3d-modeling-robotics/#3d-cad-and-spatial)

- **WorldCoder-Bench**: Evaluating Executable Three.js Worlds. [![arXiv](https://img.shields.io/badge/arXiv-2606.01869-b31b1b.svg)](https://arxiv.org/abs/2606.01869)

- **CodeVideoBench**：22 个可编辑 Three.js 案例，测可控视频，覆盖游戏、场景编辑、物理和 3D/4D 重建。配 MiniMax-H3 时，Code Video Model 在 QwenVL-3.8-27B、GPT-5.6、GPT-6 下总分 85.2 / 82.1 / 85.8，VACE 为 74.3 / 73.1 / 80.6。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://huggingface.co/datasets/code-video-model/CodeVideoBench) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/code-video-model/CodeVideoModel)

- **3JSBench**：100 个短的文本到 Three.js 任务，生成请求和几何都可以检查。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/GeneralContext/3jsbench)

- **BenchCAD**：多视图渲染写成 CadQuery，用体素 IoU 打分。带工具时，报告里 Astra 为 95.9%。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://frank-zy-dou.github.io/awesome-ai-3d-modeling-robotics/#3d-cad-and-spatial)

- **Moonlake 3D Agent**：面向仿真可用资产的评测，22 项指标加 Isaac Sim 交互测试；报告排名分 65.2，Astra 为 47.0。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://moonlakeai.com/blog/evaluating-3d-agent)

- **BuildingBench**：coding agent 把公共建筑的四张照片做成一份带贴图的 glTF。2026-10-14 榜上，Codex CLI ultra 为 0.843 ± 0.014，32 个里第三。Claude Opus 5.5（max）以 0.868 排第一。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://enactra.ai/buildingbench/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/enactra-ai/building-bench)

- **threejseval**：16 个固定的 Three.js 场景提示。人在未标名字的场景之间投票。Astra medium 的 Elo 为 1884 ± 105，36 个里第 4。Claude Opus 5.5 High 以 2071 排第一。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://threejseval.com/ranking)

- **MineBench**：模型对着一个很小的体素 API（`block`、`box`、`line`）写 JavaScript，再由人投票。Astra Pro 为 2259 ± 16.7，74 个里第 2。Gemini 4 Argon 以 2269 排第一，两者区间重叠。作者不把它叫 benchmark。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://minebench.ai/leaderboard) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Ammaar-Alam/minebench)

### 机器人评测基础设施

这些工作评测的是广义机器人策略，包括学习策略、程序接口和命令接口。它们是 policy-evaluation infrastructure，不是代码生成 benchmark。

- **XPolicyLab**: A Unified Standard and Open Ecosystem for Robot Policy Evaluation and Deployment. [![arXiv](https://img.shields.io/badge/arXiv-2608.09892-b31b1b.svg)](https://arxiv.org/abs/2608.09892) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/XPolicyLab/XPolicyLab)

- **RoboDojo**: A Unified Sim-and-Real Benchmark for Comprehensive Evaluation of Generalist Robot Manipulation Policies. [![arXiv](https://img.shields.io/badge/arXiv-2607.04434-b31b1b.svg)](https://arxiv.org/abs/2607.04434) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/robodojo-benchmark/RoboDojo)

- **HumanCLAW**: Can Vision-Language Models Act Through a Body? 用 harness 把 VLM 决策转成全身动作生成器调用，测试 VLM 能否通过身体行动。 [![arXiv](https://img.shields.io/badge/arXiv-2607.27180-b31b1b.svg)](https://arxiv.org/abs/2607.27180)

- **Robo Use Leaderboard**：汇总已发表试验里 agent harness 和 VLA 策略的成功率，带 95% Wilson 区间。每个任务对每个模型和 harness 只计一次。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robouse.ai/hub/leaderboard/)

## 综述与经验

- **World Models for Embodied Intelligence: From Plausible to Controllable to Actionable**：按预测是否合理、干预是否可控、决策是否因此变好，综述具身世界模型。给可执行和可编程世界模型提供背景，但不要求把代码当中间表示。 [![arXiv](https://img.shields.io/badge/arXiv-2609.16697-b31b1b.svg)](https://arxiv.org/abs/2609.16697)

- **Robot-Use Agents**（Phillip Isola）：关于通用 agent 通过传感器和执行器 API 使用机器人的视角文章。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://web.mit.edu/phillipi/www/writing/robot-use-agents.html)

- **Goosebumps**（Ken Goldberg）：coding agent 可以离线编写、测试和修改模块化机器人程序，处在基于模型的工程和机器人学习之间。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Ken_Goldberg/status/2100986412762087909)

- **Survey on Multimodal Embodied Agents**：把电脑使用和机器人使用收成感知、预期、规划、行动、验证。范围比 code-as-IR 方法更宽。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://showlab.github.io/Awesome-Multimodal-Embodied-Agent/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/showlab/Awesome-Multimodal-Embodied-Agent)

- **Weights or Skills?** A Survey of Robot-Learning Techniques: from Action-Predicting Weights to Robots that Write their Own Skills：梳理 action-predicting frozen weights 和可执行 robot skills 这两条路线。 [![arXiv](https://img.shields.io/badge/arXiv-2608.01851-b31b1b.svg)](https://arxiv.org/abs/2608.01851)

- **Code as Agent Harness**：讨论可执行、可验证、带状态的 agent harness 设计，重点是 agent 写代码并运行代码的系统边界。 [![arXiv](https://img.shields.io/badge/arXiv-2605.18747-b31b1b.svg)](https://arxiv.org/abs/2605.18747)

- **What Stops Recursive Self-Improvement in Robotics?** Lessons from 123 Rounds of Agentic Skill Discovery：agent 写、安装并测试 skills，但最终没有完成目标冰箱任务；主要问题是关系感知、早期 skill bottleneck 和 evaluator 行为。 [![arXiv](https://img.shields.io/badge/arXiv-2609.31760-b31b1b.svg)](https://arxiv.org/abs/2609.31760)

- **Harness Engineering for Physical AI**：主张机器人中间件就该当 harness，负责约束、隔离和传递控制、计算与通信。 [![arXiv](https://img.shields.io/badge/arXiv-2606.09416-b31b1b.svg)](https://arxiv.org/abs/2606.09416)

- **Agentic World Modeling**：综述 agentic 世界模型、能力和作者提出的规律。范围比 code-as-IR 方法更宽。 [![arXiv](https://img.shields.io/badge/arXiv-2604.22748-b31b1b.svg)](https://arxiv.org/abs/2604.22748)

- **Towards Agentic Robots: Model, Data, Environment, and Harness**：把 agentic robot 研究分成模型、数据、环境和 harness 四块。范围比 code-as-IR 方法更宽，harness 是其中一块。 [![arXiv](https://img.shields.io/badge/arXiv-2610.20442-b31b1b.svg)](https://arxiv.org/abs/2610.20442) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/chonghanqin/Awesome-Agentic-Robots)

## Projects

X、小红书、以及只有网页的系统。论文仍留在上面的栏目。案例合集见 [Awesome Astra Embodied AI](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI)。

- [⭐️] **Awesome Astra Embodied AI**: GPT-6 Astra 的具身工作流案例合集。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI)

- **GPT-6 Astra**（OpenAI）：这里被当成机器人策略、世界程序编写器和 RL 环境工程师来用。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openai.com/index/gpt-6-astra/)

### 评测报告

- **GPT-as-Policy**，银河通用：公开 benchmark 和报告，把 GPT-6 Astra 当具身策略来打分。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/anonymous-report-421/GPT-as-Policy)

- **RoboCurve GPT-6 Astra evaluation**：YAM 机械臂上的受控对比；报告碗任务 19/20，输出 token 少 80%。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openai.robocurve.org/gpt-6-astra/)

- **RPent**（RLinf）：递归 harness，agent 规划器配冻结的 VLA 原语。榜上 GPT-6 Astra 在 LIBERO-PRO 总成绩 92.63%（741/800），RoboCasa365 Target50 为 59.20%。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/RLinf/RPent)

- **Astra on RoboMME**：三层控制器跑 16 个 RoboMME 任务，报告成功率 79.13%（633/800），平均每回合 3.63 次 Astra 规划。微调过的 π0.5 执行子任务，Qwen3-VL-4B 判断何时重新规划。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://bingaochen.github.io/Astra-on-RoboMME/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/bingaochen/Astra-on-RoboMME)

- **RoboICL**：冻结的 Astra 跑 30 个 RoboDojo 任务，报告总进度分 50.64；Open 任务 zero-shot，其余给一段示范，另外还有三个真机任务。另见 [RoboICL](#code-as-policy)。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://mosi-ai.github.io/RoboICL-GPT6-Astra.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Mosi-AI/RoboICL)

### 仿真策略程序

- **UR10 传送带分拣**（NVIDIA Omniverse）：Astra 在 VS Code 里搭传送带和检测场景，再接上 UR10 和 Robotiq 夹爪分拣不合格件。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://nvidia-omniverse.github.io/omniverse-labs/projects/astra-vscode-simulation/)

- **G1 舞台波比跳**：公开代码里的一段脚本化 Unitree G1 表演：搬支架上台、摆姿势、俯卧撑，再起跳。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Siriuslala/g1-robot-burpee)

- **Dual-ALOHA 空间约束谜题**（[Qineng Wang](https://x.com/qineng_wang)）：规划 Dual-ALOHA 动作，解开互锁零件，并把绳子穿过三个环。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/qineng_wang/status/2099893504658866561) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://qinengwang-aiden.github.io/demos/constraint_demos/)

- **纯视觉人形控制**（[ZQ](https://www.rednote.com/user/profile/5f20ee17000000000101c247)）：只看相机、不用仿真器特权状态，控制仿真人形。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa7e0f6000000002b01297c?xsec_token=ABmjC06EQ2omZK2bVc-pqYOZHTFYlemRyPYY3Kj_9_a1g=&xsec_source=pc_search&source=web_search_result_notes)

- **Isaac Sim 里 G1 捡可乐**（[Flood Sung](https://x.com/RotekSong)）：给 Unitree G1 做高层规划，GEAR-SONIC 跟踪全身 qpos。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/RotekSong/status/2099104628562608371)

- **四足五关键关节轨迹**（[Akira Sasaki](https://x.com/gclue_akira)）：输出稀疏的五个关节轨迹，底层控制器在 MuJoCo 里跑四足。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/gclue_akira/status/2098300921658868185)

- **SONIC 跟踪的 G1 导航**（[Flood Sung](https://x.com/RotekSong)）：给仿真 G1 做导航规划，GEAR-SONIC 转成全身轨迹。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/RotekSong/status/2098212303263183329/video/1)

- **机械手解魔方**（[Ze Yanjie](https://x.com/ZeYanjie)）：仿真里 zero-shot 灵巧解魔方。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/ZeYanjie/status/2098118164626501669)

- **SuperDex 抓苹果柄**（[Kiki Huang](https://www.rednote.com/user/profile/62f72244000000001f0176ea)）：灵巧手在 SuperDex / MuJoCo 里抓住很细的苹果柄。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa27b3a000000002b025d03?xsec_token=ABWznjLAd9oNPOxPF1Mc6ZfMK0VKAVH4AMkoYwkdPqQRw=&xsec_source=pc_search&source=web_profile_page)

- **HumanCLAW-Bench**（[Jiawei Gu](https://x.com/Kuvvius)）：通过 HumanCLAW-Bench harness 完成导航和交互任务。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Kuvvius/status/2098038921301311753)

- **全身轨迹 + 全身控制器**（[橘子不是唯一的水果](https://www.rednote.com/user/profile/695bb2a2000000003702ea8f)）：写出全身轨迹，全身控制器闭环执行。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6a9fe4df00000000110341b8?xsec_token=ABMaVBcBS54ctuQIxmhMJMZVm36xy72xuPS8s6aICdfXM=&xsec_source=pc_search&source=web_profile_page)

- **一句话 Isaac Sim 抓方块**（[神秘小孙](https://www.rednote.com/user/profile/5b3f9fc86b58b75d4c02ccc0)）：一句任务描述，搭出带深度相机的 Isaac Sim 抓方块 demo。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa017a8000000002b002341?xsec_token=ABeuYgBbxlsBRQGFSm3KRd7TFtNG2CtmpEnSxlcSsSC4E=&xsec_source=pc_like)

- **物理写出斐波那契数列**（[Dmytro Hrybov](https://x.com/dimentary)）：仿真里 G1 做长程写斐波那契，最后给出代码和动作。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/dimentary/status/2097455860541009958)

- **桌面操作 LLM harness**（[Jiafei Duan](https://x.com/DJiafei)）：写出并跑通仿真桌面抓放的控制循环。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/DJiafei/status/2096601096705995155)

### 真机策略程序

- **真机 YAM 上的 Agent as Policy**：GPT-6 Astra 在 Codex 里写程序、跑程序，再按相机反馈修改。任务包括看人演示装配、按目标图搭积木、转骰子、投掷和双手叠毛巾。另见 [AGP](#code-as-policy)。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://agent-as-policy-2026.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/agent-as-policy-2026/agent-as-policy)

- **学打字、自我表达**（[Kaifeng Zhang](https://x.com/kaiwynd)）：开放指令「表达自己」，大约 40 分钟视觉反馈后在真机键盘上打出字。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/kaiwynd/status/2098823484474348008)

- **只从底层控制抓马克笔**（[star大小变](https://www.rednote.com/user/profile/69c2311e000000003203e786)）：没有先验技能，大约 30 分钟摸清关节到末端的控制并抓住马克笔。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa4d7e200000000260145ff?xsec_token=ABur_B60E14GxVQp2ei3USGtEElW40SN75Vj5aB_USVUA=&xsec_source=pc_search&source=web_profile_page)

- **移动操作 in-context learning**（[Axel](https://x.com/ax_pey)）：不给任务文本，只靠视觉上下文在不同房间和布局里推断移动操作。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/ax_pey/status/2098216469012283681)

- **快速适应未见过的本体**（[Lucas Cassiano](https://x.com/lucascassiano)）：在线学会新机器人和 [Vitrus AI](https://x.com/Vitrus_ai) 控制接口，不用人类第一人称数据，也不用 VLA。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/lucascassiano/status/2097830777438486557)

- **ENPIRE harness in-context learning**（[Tonghe Zhang](https://x.com/TongheZhang01)）：通过 ENPIRE harness 做真机 in-context learning，不针对任务重新训练。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/TongheZhang01/status/2097801107602911243)

- **Loop-ROS 切黄瓜**（[盒子桥](https://www.rednote.com/user/profile/65bb8b3d000000000d03e137)）：经 Loop-ROS 直接控制真机手臂完成切黄瓜。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa0c4900000000012034a2f?xsec_token=ABYB6HItIwwYq0Yyi9-hwoM-vMalkFRmYMAkN0iUWpTM4=&xsec_source=pc_search&source=web_profile_page)

- **画金门大桥**（[thijs](https://x.com/cdngdev)）：给机器人、画笔和相机，把语义提示变成真机笔触，并靠视觉反馈一轮轮改。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/cdngdev/status/2097339677128982873)

- **直接输出末端位姿**（[Loule](https://www.rednote.com/user/profile/69ddd8920000000033024ad0)）：用第三人称和腕部相机，输出末端位姿，把最长的面包放进篮子。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6a9fc0710000000029015578?xsec_token=ABMaVBcBS54ctuQIxmhMJMZSAU7Wspgd3bmCnb4tQqHsU=&xsec_source=pc_search&source=web_profile_page)

- **Piper 抓放胡萝卜**（[虽然不但是](https://www.rednote.com/user/profile/5f5ca72900000000010061fb)）：只用 Codex / GPT-6、Piper 和 RealSense，反复视觉抓放胡萝卜。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6a9bd4c80000000028037f67?xsec_token=ABLUcokp8Tzdy13Avv1khxst1pWqWBaR7JLjQhUhWsSs4=&xsec_source=pc_like)

- **双臂 YAM 上的 SimEX**：仿真里自动研究之后，扫条码、盘子放进周转箱、叠衣服每个任务大约用十分钟真机时间。另见 [SimEX](#code-as-policy)。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robo-simex.github.io/)

- **动捕甩鞭和套索**（[Krishna Suresh](https://krishnasuresh.org/blog/2026/robot-whips/)）：一句提示写出逆运动学、带动力学约束的轨迹优化和逆动力学控制器，OpenarmX 和 xArm7 开环复现甩鞭和套缆桩。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://krishnasuresh.org/blog/2026/robot-whips/)

### 规划后调用 VLA

- **Harness VLA / RPent**：Astra 用记忆和视觉反馈做规划，再调用冻结的 VLA 和一组固定的解析运动原语。真机 demo 分拣盘子，抓取失败后重试，不微调 VLA。另见 [Harness VLA](#code-as-policy)。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://harnessvla.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/RLinf/RPent)

- **Recursive Harness Distillation**：Astra 把机器人解题写成 playbook，再按 Luna 的反馈改写，让 Luna 去指挥冻结的 VLA。另见 [Recursive Harness Distillation](#code-as-policy)。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://seungyeon.me/RHD/)

- **Astra on RoboMME**：Astra 根据指令和视觉历史规划子任务，微调过的 π0.5 执行，微调过的 Qwen3-VL-4B 判断子任务是否完成。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://bingaochen.github.io/Astra-on-RoboMME/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/bingaochen/Astra-on-RoboMME)

- **经 FluxVLA 做 zero-shot 任务**（[Jikun](https://www.rednote.com/user/profile/5e25bcdc00000000010085a8)）：Astra 负责任务理解和规划，预训练 [FluxVLA](https://github.com/FluxVLA/FluxVLA) 跑底层动作。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa16835000000000b00f46d?xsec_token=ABDcu5eBZZYkAUcveAv8IZNWsbLmXk6CUM5u5BhDPODB0=&xsec_source=pc_search&source=web_profile_page)

### 从视频反演世界程序

- **Astra 做 4D 形状拟合**（[Edgar Sucar](https://x.com/SucarEdgar)）：从视频拟合 4D 形状，人工提示叶子对称来约束拟合。要几个小时，并且来回 prompt。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/SucarEdgar/status/2101739645759361322)

- **Guan’s Fencing Club**：比赛录像、两名动画击剑手和程序化剑馆放在 UE5 时间轴上，剑尖留一秒轨迹。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/samguan2020/guans-fencing-club)

- **AHa-3D**：Astra 加重建工具，把室内视频做成可编辑的 Blender 房间，带接触修正地恢复人体动作，再导出浏览器场景。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://kevinxu02.github.io/real2sim-indoor-site/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/KevinXu02/aha-3d)

- **Real2Gym**：agent 从视频重建 Blender / MuJoCo gym，再用生成的 Python 阶段和视觉反馈跑操作，然后迁移技能。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/real2gym/Real2Gym)

- **实验室厨房重建**（[Frank ZY Dou](https://www.rednote.com/user/profile/5e3431cf0000000001002919)）：20 秒单目 RGB 视频重建带可动柜门的实验室厨房。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa4d64c000000000b037809?xsec_token=ABur_B60E14GxVQp2ei3USGkgJntlivJm_02tlDaUFWmg=&xsec_source=pc_search&source=web_profile_page)

- **绳驱灵巧手重建**（[Dmytro Hrybov](https://x.com/dimentary)）：在 MuJoCo 里复现 1X 腱驱手 demo，腱传动做了简化。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/dimentary/status/2097857980150763900)

- **腱驱灵巧手动作重建**（[Jake Fitzgerald](https://x.com/earthtojake)）：设计腱驱手，并在仿真里重建缆线驱动的手指动作。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/earthtojake/status/2097789988670709821)

- **灵巧手-物体 data rollout**（[Lingxiao](https://x.com/Lingxiao234)）：两段视频做 real-to-sim 重建，再物理重定向到 Wuji 手上，没有显式状态或动作。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Lingxiao234/status/2097717020540481630)

- **Video in → Physics out**（[xiao hu](https://x.com/huxiao93612565)）：给 44 自由度手写手部跟踪、IK 重定向和抓取精修代码。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/huxiao93612565/status/2097815230105399402)

- **多视角 real-to-sim**（[Lingxiao](https://x.com/Lingxiao234)）：用多视角 RGB、机器人动作、标定、资产和系统辨识，搭出可回放的 MuJoCo / Blender 仿真。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Lingxiao234/status/2096992059731443923)

- **Robotica Real2Sim**：一张桌面照片变成带 Franka Panda 的 MuJoCo 场景。Codex 录下 50 段逆运动学轨迹，再把规划放到不同物理参数下回放。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/inematds/robotica-real2sim)

### 编写 RL 训练栈

- **Dexterous Astra**（[Jianglong Ye](https://github.com/jianglongye)）：放出的是 Astra 实验的最终产物，不是事先给 agent 的 harness。Sharpa Wave 在 Isaac Lab 里转笔（zero-shot 关键帧规划，再 PPO 转三圈并握住），Wuji 手在 MuJoCo 里解魔方（zero-shot 双手脚本，再学单手策略解出 `U F L`）。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/jianglongye/dexterous-astra)

- **办公室 Real2Sim2Real 推车**（[watchtower](https://www.rednote.com/user/profile/5e38ca4e00000000010034fa)）：重建办公室，估计接触监督，用 SONIC 做全身运动并训练推车 RL，再部署回真机人形。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6ab34cfd0000000018005cab?xsec_token=CBoKOnuhKTqoyv12enaYThxB4L_a-12BnOafHa5vF3aRw=&xsec_source=app_share)

- **Sharpa 手转笔 RL**（[Wentao Zhu](https://x.com/walterzhu8) / Chengyang Li）：大约一天半的自主运行，建笔 mesh、Isaac Lab 任务、PPO 策略和可视化视频。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/walterzhu8/status/2100212420840989112)

- **RL 训练的鸭子机器人**（[拂晓时分_茉莉飘香](https://www.rednote.com/user/profile/5ffbc96d00000000010060ae)）：一张图加一句描述，训出鸭子行走 demo。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa347e2000000000b036667?xsec_token=AB1z4k50CvQ0PFZpqtQXWYlVMONqE2yr3ER8jk-hVWI74=&xsec_source=pc_search&source=web_profile_page)

- **四足 RL 运动系统**（[Akira Sasaki](https://x.com/gclue_akira)）：共同设计机器狗，五天 25 轮迭代，用 RL 训出九个仿真动作。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/gclue_akira/status/2098300921658868185)

- **灵巧手掌内操作 RL**（[十一](https://www.rednote.com/user/profile/610bc8f100000000200284e2)）：训练掌内转核桃；报告的这次 run 没开自碰撞。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa3e146000000002b0123dc?xsec_token=AB5n_GSvnshtGoIJqykTNpkWlIS-zHnIYe2n5pAiGLSgw=&xsec_source=pc_like)

- **办公室扫描 → Newton / G1 Gym**（[Jiarui Xu](https://x.com/Jiarui_X)）：把办公室扫描重建进 Blender，导出 USD，在 Newton 里做成 G1 行走场景。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Jiarui_X/status/2098439950991806804)

- **Isaac Sim 环境、PPO 训练和调参**（[十一](https://www.rednote.com/user/profile/610bc8f100000000200284e2)）：一个工作流里搭 Isaac Sim RL 环境、配 PPO、再迭代训练。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa29087000000002600bb2e?xsec_token=ABupW63bXfa1dAqIk6vaYviNev-xOXuTmePvxk8Su9NK4=&xsec_source=pc_collect)

### 场景程序

Astra 把场景、CAD 或可玩世界写成程序，再交给 Blender、OpenSCAD、Three.js 或游戏引擎去跑。完整集合是 [Awesome Astra 3D](https://github.com/carpentry-liu/awesome-astra-3d) 里的 338 个例子（[画廊](https://carpentry-liu.github.io/awesome-astra-3d/)）。下面只收有源码或可检查程序的入口，按跑起来的程序分组。只有视频的渲染留在那个图集里。

- [⭐️] **Awesome Astra 3D**：Blender、Houdini、Three.js、CAD、VRM 和交互游戏的案例合集。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/carpentry-liu/awesome-astra-3d) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://carpentry-liu.github.io/awesome-astra-3d/)

#### 可执行场景

- **Solace**：用 Blender、Cycles 和 UE5 迭代建筑方案。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://developers.openai.com/blog/architectural-visualization-with-astra)

- **骑自行车的鹈鹕**：三次 Blender 迭代，网格可编辑，对话有记录。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/simonw/gpt-6-astra-blender-pelican-bicycle)

- **GPTBlender 平面图**：平面图生成可下载的带家具房屋。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://gptblender.com/turn-floor-plan-into-3d-model-gpt6-astra/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/qduoduo-hwh/gptblender_demo)

- **Realsee**：实景扫描到可编辑的 Blender 空间，带漫游视频和提示词。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/realsee-developer/realsee-astra-blender)

- **Orbital Core**：Blender 和 GLB 放进可交互的 Three.js 页面。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/wangruofeng/orbital-core-showcase)

- **Piața Unirii**：同一简报做出的体素广场，提示词和源码都在。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/danmana/piata-unirii)

- **Real2Sim 房间**：照片重建成可编辑房间，失败结果也留在仓库里。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Roboparty/gpt-6-astra-real2sim-workflow)

- **Jetis**：从 DWG 做成可漫游工厂，并导出原生 SketchUp 模型。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/bambssquad/jetis-digital-twin-astra)

- **WorldGen**：三句文字场景，分别在 Blender 和 Unity 里搭出来。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/andyyuyc/WorldGen_Unity)

- **Junya 日本城市生成器**：JSON 路网写成可编辑的 Blender 场景，再进 Unreal 渲染。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/junya-tashiro/agent-jp-citygen)

- **Renders**：四座建筑的 Blender 工程，带修订脚本和旧版存档。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/lucas-chu/Renders)

- **Stanford in Blender**：五组可编辑校园场景，带程序化脚本和可单独打开的 `.blend`。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/minsik-ai/stanford-in-blender)

- **鼓楼校园**：用 TypeScript、Three.js 和 Rapier 做成可走的南京大学鼓楼校区，可以骑行、滑翔、切换天气。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/wang-jiahao/gulou)

- **Gargantua**：着色器画的吸积盘和弯曲光线，相机可以环绕。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/pedroaugustonyo/gargantua)

- **BHBench**：Astra 写的原生黑洞渲染，带生成的 C++ / GLSL、光线积分和曲率网格。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/SSHdotCodes/bhbench/tree/main/submissions/gpt-6-astra-xhigh)

- **One Equation, Three Worlds**：同一条洛伦兹曲线做成可编辑铜雕、程序墨迹和移动光线。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/davisbuilds/oneshots/tree/main/runs/three-worlds-chatgpt)

#### CAD 程序

- **J 型挂钩**：OpenSCAD 打印设计的模型对照，强度测试还没做。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/WescheNex1q/status/2104590493191479337)

- **别墅、递归电影、涡轮 CAD**：一个仓库里三个可编辑三维项目。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/az9713/gpt-6-3d-projects)

- **Realitizer**：用 Swift 做代码优先的蝠鲼和房屋模型。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/koher/realitizer)

- **Aetheris 差分机**：数位轮、进位齿轮和曲柄的层级 CAD，可导出 STEP。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/yuechen-li-dev/Aetheris/tree/master/demos/Aetheris.DifferenceEngine.Showcase)

- **LDraw Nova**：Python 生成器输出可编辑的 LDraw 大教堂和潮汐观测站。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/anteloc/ldraw-nova)

- **DeepSeek 鲸鱼摆件**：标志剪影做成可改尺寸的单实体打印网格。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/shyrz/gpt-6-astra-3dp-test)

#### 可玩的世界程序

- **Living Deep**：在已有海洋仿真上加海底生态。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/emollick/abyssal-living-deep)

- **Smash Karts**：多人客户端、服务端，以及公开的 agent 轨迹。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/amsminn/gpt-6-astra-smash-karts)

- **Little Flock**：一次写出的牧场世界，目标提示词在仓库里。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/songkeys/little-flock)

- **Windfield**：三维冒险加上地形编辑器。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/fuguai1/status/2104531704740512143)

- **Melon Jelly**：WebGPU 软体果冻的模型对照。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/esrhengwu/status/2104504957173153951)

- **Pelagic**：程序化海洋和帆船探索。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/az9713/gpt-6-astra-3D-ocean)

- **H3 Battle Lab**：三维兵种接到原生 VCMI 战斗接口。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/yzh119/h3-battle-lab)

- **Seabright**：Unity 海岸建城，含道路、公共服务和税收。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/codersusu/game-city-skylines)

- **Octane Arena**：程序化三维车球，物理源码公开。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Goofykings/Octane-Arena)

- **Astra Air Combat**：按种子生成战区，60 Hz 空战循环。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/FLYING37520/astra-air-combat)

- **Palm Bay**：保留下来的一次生成的低多边形驾驶沙盒，原始提示和恢复出的 JavaScript 都在仓库里。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/nitzangames/PalmBayOneShot)

- **Corner Mart**：可编辑便利店，带购物清单和三分钟营业，仓库里有 `.blend`、GLB 和生成脚本。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/ericyanpek/game-sample-corner-mart)

- **Hallowmere**：火炬村庄 RPG，程序化角色、战斗和合作模式。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/miguelsolorio/hallowmere)

- **Morrow**：一个 HTML 里的月光毛绒幽灵，可以抓、戳、梳毛和改颜色。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Kayou-31/moonlit-plush-gallery/blob/main/morrow.html)

- **Moss & Moon**：Three.js 里的程序赤狐和林地生态，带骨架、足部 IK 和按需求寻路。Astra 的提交单独放在一个目录里。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/hdnng/ai-3d-animal-astra-vs-argon-vs-opus/tree/main/astra)

## 相关资源

- **Awesome Physical AI**：更宽的 robot-policy VLM、coding agent、policy harness 和 RoboDojo 类 scorecard 阅读列表。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HexaFuture/Awesome-Physical-AI)

- **Awesome Robot Use Agent**：robot-use agent、harness、ROS 工具栈和社交 demo 的总表。这里只收把程序当中间表示的条目。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/kairunwen/Awesome-Robot-Use-Agent) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://kairunwen.github.io/Awesome-Robot-Use-Agent/)

- **Awesome AI for 3D Modeling & Robotics**：AI 三维建模、CAD 和机器人控制的带来源案例，以及从原文读来的评测数字。社交视频留在那个目录里。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Frank-ZY-Dou/awesome-ai-3d-modeling-robotics) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://frank-zy-dou.github.io/awesome-ai-3d-modeling-robotics/)

- **Awesome Multimodal Embodied Agent**：从电脑使用到机器人使用的多模态 agent，含综述和评测。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/showlab/Awesome-Multimodal-Embodied-Agent)

- **Awesome Embodied RSI**：具身递归自我改进，按改的是模型、记忆、技能还是 harness 来分。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/cocacola-lab/awesome-embodied-rsi)

- **Awesome Humanoid Robot Learning**：人形行走、操作、遥操作和 sim-to-real。多数是学习策略，不是程序。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/YanjieZe/awesome-humanoid-robot-learning)

- **Awesome Embodied Robotics and Agent**：具身机器人方法和评测。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/zchoi/Awesome-Embodied-Robotics-and-Agent)

- **Awesome Agentic Robotics**：机器人控制里的 agent、harness 和 VLA 栈。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/w-xb/awesome-agentic-robotics)

- **Awesome Agentic World Modeling**：世界模型按预测器、仿真器和演化器来分。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/matrix-agent/awesome-agentic-world-modeling)
