<div align="center">

# Awesome Code as Policy/World/Editor

**把程序当作中间表示的 coding agent。** </br>

<p align="center">
  <img src="awesome-code-as-x.png" alt="Awesome Code as X" width="100%" style="border-radius: 15px; box-shadow: 0 4px 24px rgba(0,0,0,.1); margin: 5px 0;">
</p>

[English](README.md) | [中文](README.zh.md) | [HF Blog](https://huggingface.co/blog/kkakkkka/from-coding-agents-to-physical-agents) | [中文解读](https://mp.weixin.qq.com/s/MuOz0KmmQa5CxzjY7WEEvA)

<table align="center">
  <tr>
    <td align="center" width="35%">
      <img src="sourcemind.jpg" alt="社区二维码" width="35%">
      <br>
      <sub>社区由<strong>sourcemind</strong>支持</sub>
    </td>
    <td align="center" width="35%">
      <img src="wechat.jpg" alt="微信群二维码" width="35%">
      <br>
      <sub>微信群二维码</sub>
    </td>
  </tr>
</table>

</div>

## Overview
- 🎯 [目标](#目标)
- 📚 [Policy Program 定义](#policy-program-定义) | [World Program 定义](#world-program-定义) | [Programmable World Model 定义](#programmable-world-model-定义) | [Edit Graph 定义](#edit-graph-定义) | [Benchmark 定义](#benchmark-定义) | [Project 定义](#project-定义)

**Code as Policy**
- 🦾 [Code as Policy](#code-as-policy)

**Code as World**
- 🗺️ [Code as World](#code-as-world)

**Programmable World Models**
- 🧮 [Programmable World Models](#programmable-world-models)

**Edit Graphs**
- ✂️ [Edit Graph](#edit-graph)

**Benchmarks**
- 📊 [Benchmark](#benchmark)

**Projects**
- 🛠️ [Projects](#projects)
    - [评测报告](#评测报告)
    - [仿真策略程序](#仿真策略程序)
    - [真机策略程序](#真机策略程序)
    - [规划后调用 VLA](#规划后调用-vla)
    - [从视频反演世界程序](#从视频反演世界程序)
    - [编写 RL 训练栈](#编写-rl-训练栈)

## 目标
agent 写出或改好程序、工具图或可检查的世界状态，再交给仿真器、渲染器、机器人或编辑器去跑。应用场景包括：机器人策略、可执行场景、可编程世界模型、图像和视频编辑图，以及评测这些 agent 的 benchmark。没有论文、但是系统、评测或案例合集的，放进 Projects，不塞进论文栏目。

有新论文和项目会继续加。欢迎补充。

## Policy Program 定义
Code-as-Policy 用 LLM / VLM 当高层 agent，写出可执行的机器人程序，或者一层很薄的语义动作接口，用来替代 VLA 动作 token。这个说法来自 Code as Policies。

- [⭐️] **Code as Policies**: Language Model Programs for Embodied Control. [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b.svg)](https://arxiv.org/abs/2209.07753) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-policies.github.io)

## World Program 定义
World program 是可执行的场景或物理程序，比如 Blender、MuJoCo、USD、CadQuery，不是静态 mesh，也不是视频。从语言或布局写出来叫生成；从图像、视频或扫描写回去叫反演。

- [⭐️] **SceneCode**: Executable World Programs for Editable Indoor Scenes with Articulated Objects. [![arXiv](https://img.shields.io/badge/arXiv-2605.19587-b31b1b.svg)](https://arxiv.org/abs/2605.19587) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://scene-code.github.io/)

## Programmable World Model 定义
可编程世界模型把状态和转移写在代码里。生成模型或渲染器只管外观。

- [⭐️] **Code World Model**: Coding Agent as World Brain. [![arXiv](https://img.shields.io/badge/arXiv-2608.25927-b31b1b.svg)](https://arxiv.org/abs/2608.25927) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://buaacyw.github.io/cwm/)

## Edit Graph 定义
编辑图是一次可检查、可回滚的修改：工具调用序列、视觉程序，或时间线补丁。VisProg 是比较早的例子。

- [⭐️] **VisProg**, Visual Programming: Compositional Visual Reasoning Without Training. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://prior.allenai.org/projects/visprog)

## Benchmark 定义
这类 benchmark 测的是 coding agent 能不能写出、跑通、改好机器人学习或可执行世界相关的程序。

- [⭐️] **RLE-Bench**: A Qualifying Exam for Coding Agents as Robot Learning Engineers. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rle-bench.github.io/)

## Project 定义
这里收 X、小红书、只有网页的系统和案例合集，主产物不是论文。agent 可能写机器人程序、世界程序、RL 训练栈，或一层很薄的控制接口。

- [⭐️] **Awesome Astra Embodied AI**: GPT-6 Astra 的具身 / 机器人工作流和 demo。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI)

## Code as Policy

- [⭐️] **Code as Policies**: Language Model Programs for Embodied Control. [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b.svg)](https://arxiv.org/abs/2209.07753) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-policies.github.io)

- [⭐️] **CaP-X**: A Framework for Benchmarking and Improving Coding Agents for Robot Manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2603.22435-b31b1b.svg)](https://arxiv.org/abs/2603.22435) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://capgym.github.io)

- [⭐️] **RATs**, Playful Agentic Robot Learning. [![arXiv](https://img.shields.io/badge/arXiv-2606.19419-b31b1b.svg)](https://arxiv.org/abs/2606.19419) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://Playful-RATs.github.io/)

- [⭐️] **Show-Harness**: Just a VLM Agent Can Play Robots. [![arXiv](https://img.shields.io/badge/arXiv-2609.10522-b31b1b.svg)](https://arxiv.org/abs/2609.10522) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://showlab.github.io/Show-Harness/)

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

## Code as World

### Generation

- [⭐️] **SceneCode**: Executable World Programs for Editable Indoor Scenes with Articulated Objects. [![arXiv](https://img.shields.io/badge/arXiv-2605.19587-b31b1b.svg)](https://arxiv.org/abs/2605.19587) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://scene-code.github.io/)

- [⭐️] **VideoCoCo**: Code-as-CoT for Physically-Consistent Video Generation via an Agentic Dual-Engine System. [![arXiv](https://img.shields.io/badge/arXiv-2607.27380-b31b1b.svg)](https://arxiv.org/abs/2607.27380) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/micky-li-hd/VideoCoCo)

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

- **VIGA**, Vision-as-Inverse-Graphics Agent via Interleaved Multimodal Reasoning. [![arXiv](https://img.shields.io/badge/arXiv-2601.11109-b31b1b.svg)](https://arxiv.org/abs/2601.11109) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://fugtemypt123.github.io/VIGA-website)

- **Thinking in Blender**: Staged Executable Inverse Graphics with Vision-Language Models. [![arXiv](https://img.shields.io/badge/arXiv-2606.02580-b31b1b.svg)](https://arxiv.org/abs/2606.02580)

- **RCWM**, Recursive Code World Models: Building Complex Worlds through Recursive Scene Programs. [![arXiv](https://img.shields.io/badge/arXiv-2609.11499-b31b1b.svg)](https://arxiv.org/abs/2609.11499)

- **VisPhyWorld**: Probing Physical Reasoning via Code-Driven Video Reconstruction. [![arXiv](https://img.shields.io/badge/arXiv-2602.13294-b31b1b.svg)](https://arxiv.org/abs/2602.13294) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/TIGER-AI-Lab/VisPhyWorld)

- [⭐️] **LiteReality-Agent**: An Agentic System for Interactable 3D Indoor Scene Reconstruction. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://litereality.github.io/agent/)

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

- [⭐️] **RLE-Bench**: A Qualifying Exam for Coding Agents as Robot Learning Engineers. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rle-bench.github.io/)

- **WorldCoder-Bench**: Evaluating Executable Three.js Worlds. [![arXiv](https://img.shields.io/badge/arXiv-2606.01869-b31b1b.svg)](https://arxiv.org/abs/2606.01869)

## Projects

X、小红书、以及只有网页的系统。论文仍留在上面的栏目。案例合集见 [Awesome Astra Embodied AI](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI)。

- [⭐️] **Awesome Astra Embodied AI**: GPT-6 Astra 的具身工作流案例合集。 [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI)

- **GPT-6 Astra**（OpenAI）：这里被当成机器人策略、世界程序编写器和 RL 环境工程师来用。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openai.com/index/gpt-6-astra/)

### 评测报告

- **GPT-Policy** / **GPT-Policy-Eval**：VLM agent 从一段视频 in-context 学会真机插插头，不用 VLA、RL 或 DAgger。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://cheng-haha.github.io/GPT-Policy/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/cheng-haha/GPT-Policy-Eval)

- **GPT-as-Policy**，银河通用：公开 benchmark 和报告，把 GPT-6 Astra 当具身策略来打分。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robodojo-benchmark.com/report/gpt-6-astra-eval) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/anonymous-report-421/GPT-as-Policy)

- **RoboCurve GPT-6 Astra evaluation**：YAM 机械臂上的受控对比；报告碗任务 19/20，输出 token 少 80%。 [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openai.robocurve.org/gpt-6-astra/)

### 仿真策略程序

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

- **学打字、自我表达**（[Kaifeng Zhang](https://x.com/kaiwynd)）：开放指令「表达自己」，大约 40 分钟视觉反馈后在真机键盘上打出字。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/kaiwynd/status/2098823484474348008)

- **只从底层控制抓马克笔**（[star大小变](https://www.rednote.com/user/profile/69c2311e000000003203e786)）：没有先验技能，大约 30 分钟摸清关节到末端的控制并抓住马克笔。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa4d7e200000000260145ff?xsec_token=ABur_B60E14GxVQp2ei3USGtEElW40SN75Vj5aB_USVUA=&xsec_source=pc_search&source=web_profile_page)

- **移动操作 in-context learning**（[Axel](https://x.com/ax_pey)）：不给任务文本，只靠视觉上下文在不同房间和布局里推断移动操作。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/ax_pey/status/2098216469012283681)

- **快速适应未见过的本体**（[Lucas Cassiano](https://x.com/lucascassiano)）：在线学会新机器人和 [Vitrus AI](https://x.com/Vitrus_ai) 控制接口，不用人类第一人称数据，也不用 VLA。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/lucascassiano/status/2097830777438486557)

- **ENPIRE harness in-context learning**（[Tonghe Zhang](https://x.com/TongheZhang01)）：通过 ENPIRE harness 做真机 in-context learning，不针对任务重新训练。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/TongheZhang01/status/2097801107602911243)

- **Loop-ROS 切黄瓜**（[盒子桥](https://www.rednote.com/user/profile/65bb8b3d000000000d03e137)）：经 Loop-ROS 直接控制真机手臂完成切黄瓜。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa0c4900000000012034a2f?xsec_token=ABYB6HItIwwYq0Yyi9-hwoM-vMalkFRmYMAkN0iUWpTM4=&xsec_source=pc_search&source=web_profile_page)

- **画金门大桥**（[thijs](https://x.com/cdngdev)）：给机器人、画笔和相机，把语义提示变成真机笔触，并靠视觉反馈一轮轮改。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/cdngdev/status/2097339677128982873)

- **直接输出末端位姿**（[Loule](https://www.rednote.com/user/profile/69ddd8920000000033024ad0)）：用第三人称和腕部相机，输出末端位姿，把最长的面包放进篮子。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6a9fc0710000000029015578?xsec_token=ABMaVBcBS54ctuQIxmhMJMZSAU7Wspgd3bmCnb4tQqHsU=&xsec_source=pc_search&source=web_profile_page)

- **Piper 抓放胡萝卜**（[虽然不但是](https://www.rednote.com/user/profile/5f5ca72900000000010061fb)）：只用 Codex / GPT-6、Piper 和 RealSense，反复视觉抓放胡萝卜。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6a9bd4c80000000028037f67?xsec_token=ABLUcokp8Tzdy13Avv1khxst1pWqWBaR7JLjQhUhWsSs4=&xsec_source=pc_like)

### 规划后调用 VLA

- **经 FluxVLA 做 zero-shot 任务**（[Jikun](https://www.rednote.com/user/profile/5e25bcdc00000000010085a8)）：Astra 负责任务理解和规划，预训练 [FluxVLA](https://github.com/FluxVLA/FluxVLA) 跑底层动作。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa16835000000000b00f46d?xsec_token=ABDcu5eBZZYkAUcveAv8IZNWsbLmXk6CUM5u5BhDPODB0=&xsec_source=pc_search&source=web_profile_page)

### 从视频反演世界程序

- **实验室厨房重建**（[Frank ZY Dou](https://www.rednote.com/user/profile/5e3431cf0000000001002919)）：20 秒单目 RGB 视频重建带可动柜门的实验室厨房。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa4d64c000000000b037809?xsec_token=ABur_B60E14GxVQp2ei3USGkgJntlivJm_02tlDaUFWmg=&xsec_source=pc_search&source=web_profile_page)

- **绳驱灵巧手重建**（[Dmytro Hrybov](https://x.com/dimentary)）：在 MuJoCo 里复现 1X 腱驱手 demo，腱传动做了简化。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/dimentary/status/2097857980150763900)

- **腱驱灵巧手动作重建**（[Jake Fitzgerald](https://x.com/earthtojake)）：设计腱驱手，并在仿真里重建缆线驱动的手指动作。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/earthtojake/status/2097789988670709821)

- **灵巧手-物体 data rollout**（[Lingxiao](https://x.com/Lingxiao234)）：两段视频做 real-to-sim 重建，再物理重定向到 Wuji 手上，没有显式状态或动作。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Lingxiao234/status/2097717020540481630)

- **Video in → Physics out**（[xiao hu](https://x.com/huxiao93612565)）：给 44 自由度手写手部跟踪、IK 重定向和抓取精修代码。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/huxiao93612565/status/2097815230105399402)

- **多视角 real-to-sim**（[Lingxiao](https://x.com/Lingxiao234)）：用多视角 RGB、机器人动作、标定、资产和系统辨识，搭出可回放的 MuJoCo / Blender 仿真。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Lingxiao234/status/2096992059731443923)

### 编写 RL 训练栈

- **Sharpa 手转笔 RL**（[Wentao Zhu](https://x.com/walterzhu8) / Chengyang Li）：大约一天半的自主运行，建笔 mesh、Isaac Lab 任务、PPO 策略和可视化视频。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/walterzhu8/status/2100212420840989112)

- **RL 训练的鸭子机器人**（[拂晓时分_茉莉飘香](https://www.rednote.com/user/profile/5ffbc96d00000000010060ae)）：一张图加一句描述，训出鸭子行走 demo。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa347e2000000000b036667?xsec_token=AB1z4k50CvQ0PFZpqtQXWYlVMONqE2yr3ER8jk-hVWI74=&xsec_source=pc_search&source=web_profile_page)

- **四足 RL 运动系统**（[Akira Sasaki](https://x.com/gclue_akira)）：共同设计机器狗，五天 25 轮迭代，用 RL 训出九个仿真动作。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/gclue_akira/status/2098300921658868185)

- **灵巧手掌内操作 RL**（[十一](https://www.rednote.com/user/profile/610bc8f100000000200284e2)）：训练掌内转核桃；报告的这次 run 没开自碰撞。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa3e146000000002b0123dc?xsec_token=AB5n_GSvnshtGoIJqykTNpkWlIS-zHnIYe2n5pAiGLSgw=&xsec_source=pc_like)

- **办公室扫描 → Newton / G1 Gym**（[Jiarui Xu](https://x.com/Jiarui_X)）：把办公室扫描重建进 Blender，导出 USD，在 Newton 里做成 G1 行走场景。 [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Jiarui_X/status/2098439950991806804)

- **Isaac Sim 环境、PPO 训练和调参**（[十一](https://www.rednote.com/user/profile/610bc8f100000000200284e2)）：一个工作流里搭 Isaac Sim RL 环境、配 PPO、再迭代训练。 [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa29087000000002600bb2e?xsec_token=ABupW63bXfa1dAqIk6vaYviNev-xOXuTmePvxk8Su9NK4=&xsec_source=pc_collect)

