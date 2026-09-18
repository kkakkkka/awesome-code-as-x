<div align="center">

# Awesome Code as Policy/World/Editor

**把程序当作中间表示的 coding agent。** </br>

<p align="center">
  <img src="awesome-code-as-x.png" alt="Awesome Code as X" width="100%" style="border-radius: 15px; box-shadow: 0 4px 24px rgba(0,0,0,.1); margin: 5px 0;">
</p>

[English](README.md) | [中文](README.zh.md) | [中文解读](https://mp.weixin.qq.com/s/MuOz0KmmQa5CxzjY7WEEvA)

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
- 📚 [Policy Program 定义](#policy-program-定义) | [World Program 定义](#world-program-定义) | [Programmable World Model 定义](#programmable-world-model-定义) | [Edit Graph 定义](#edit-graph-定义) | [Benchmark 定义](#benchmark-定义)

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

## 目标
agent 写出或改好程序、工具图或可检查的世界状态，再交给仿真器、渲染器、机器人或编辑器去跑。应用场景包括：机器人策略、可执行场景、可编程世界模型、图像和视频编辑图，以及评测这些 agent 的 benchmark。

有新论文会继续加。欢迎补充。

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

## Code as Policy

- [⭐️] **Code as Policies**: Language Model Programs for Embodied Control. [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b.svg)](https://arxiv.org/abs/2209.07753) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-policies.github.io)

- [⭐️] **CaP-X**: A Framework for Benchmarking and Improving Coding Agents for Robot Manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2603.22435-b31b1b.svg)](https://arxiv.org/abs/2603.22435) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://capgym.github.io)

- [⭐️] **RATs**, Playful Agentic Robot Learning. [![arXiv](https://img.shields.io/badge/arXiv-2606.19419-b31b1b.svg)](https://arxiv.org/abs/2606.19419) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://Playful-RATs.github.io/)

- [⭐️] **Show-Harness**: Just a VLM Agent Can Play Robots. [![arXiv](https://img.shields.io/badge/arXiv-2609.10522-b31b1b.svg)](https://arxiv.org/abs/2609.10522) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://showlab.github.io/Show-Harness/)

- **GPT-Policy**: In-Context Robot Learning with VLM Agents. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://cheng-haha.github.io/GPT-Policy/)

- **GPT-as-Policy**: GPT 6 Astra as an Embodied Policy. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robodojo-benchmark.com/report/gpt-6-astra-eval)

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

