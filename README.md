<div align="center">

# Awesome Code as Policy/World/Editor

**Coding-agent papers that treat a program as the intermediate representation.** </br>

<p align="center">
  <img src="awesome-code-as-x.png" alt="Awesome Code as X" width="100%" style="border-radius: 15px; box-shadow: 0 4px 24px rgba(0,0,0,.1); margin: 5px 0;">
</p>

[English](README.md) | [中文](README.zh.md) | [HF Blog](https://huggingface.co/blog/kkakkkka/from-coding-agents-to-physical-agents) | [中文解读](https://mp.weixin.qq.com/s/MuOz0KmmQa5CxzjY7WEEvA)

<table align="center">
  <tr>
    <td align="center" width="35%">
      <img src="sourcemind.jpg" alt="Community QR Code" width="35%">
      <br>
      <sub>Community supported by <strong>sourcemind</strong></sub>
    </td>
    <td align="center" width="35%">
      <img src="wechat.jpg" alt="WeChat Group QR Code" width="35%">
      <br>
      <sub>WeChat Group</sub>
    </td>
  </tr>
</table>
</div>

## Overview
- 🎯 [Aim](#aim)
- 📚 [Policy Program Definition](#policy-program-definition) | [World Program Definition](#world-program-definition) | [Programmable World Model Definition](#programmable-world-model-definition) | [Edit Graph Definition](#edit-graph-definition) | [Benchmark Definition](#benchmark-definition) | [Project Definition](#project-definition)

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
    - [Eval reports](#eval-reports)
    - [Policy programs in simulation](#policy-programs-in-simulation)
    - [Policy programs on a real robot](#policy-programs-on-a-real-robot)
    - [Plan, then call a VLA](#plan-then-call-a-vla)
    - [World programs from video](#world-programs-from-video)
    - [RL training stacks](#rl-training-stacks)

## Aim
We collect papers where an agent writes or edits a program, a tool graph, or an explicit world state, then a simulator, renderer, robot, or editor runs it. That includes robot policies, executable scenes, programmable world models, image or video edit graphs, and benchmarks for those agents. Systems, evals, and case catalogs without a paper go under Projects, not under the paper sections.

New papers and projects get added as they appear. PRs are welcome.

## Policy Program Definition
A Code-as-Policy agent is an LLM or VLM that writes executable robot programs, or a thin semantic action interface. That is the alternative to VLA action tokens. The name comes from Code as Policies.

- [⭐️] **Code as Policies**: Language Model Programs for Embodied Control. [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b.svg)](https://arxiv.org/abs/2209.07753) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-policies.github.io)

## World Program Definition
A world program is an executable scene or physics program in Blender, MuJoCo, USD, CadQuery, or a similar stack. It is not a static mesh and not a video. Generation writes the program from language or a layout. Inversion / Reconstruction writes it from images, video, or scans.

- [⭐️] **SceneCode**: Executable World Programs for Editable Indoor Scenes with Articulated Objects. [![arXiv](https://img.shields.io/badge/arXiv-2605.19587-b31b1b.svg)](https://arxiv.org/abs/2605.19587) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://scene-code.github.io/)

## Programmable World Model Definition
Programmable world models keep state and transitions in code. The generator or renderer only handles how things look.

- [⭐️] **Code World Model**: Coding Agent as World Brain. [![arXiv](https://img.shields.io/badge/arXiv-2608.25927-b31b1b.svg)](https://arxiv.org/abs/2608.25927) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://buaacyw.github.io/cwm/)

## Edit Graph Definition
An edit graph is a sequence of tool calls, a visual program, or a timeline patch. You can inspect it and roll it back. VisProg is an early example.

- [⭐️] **VisProg**, Visual Programming: Compositional Visual Reasoning Without Training. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://prior.allenai.org/projects/visprog)

## Benchmark Definition
These benchmarks test whether a coding agent can write, run, and revise programs for robot learning or executable worlds.

- [⭐️] **RLE-Bench**: A Qualifying Exam for Coding Agents as Robot Learning Engineers. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rle-bench.github.io/)

## Project Definition
A project here is an X post, Xiaohongshu post, webpage-only system, or eval whose primary artifact is not a paper. The coding agent still writes a program as the IR, or closed-loop controls a robot or simulator from code.

- [⭐️] **Awesome Astra Embodied AI**: GPT-6 Astra with embodied AI / robotics workflows and demos. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI)

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

X posts, Xiaohongshu posts, and webpage-only systems. Papers stay in the sections above. Case catalog: [Awesome Astra Embodied AI](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI).

- [⭐️] **Awesome Astra Embodied AI**: GPT-6 Astra case catalog for embodied workflows. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI)

- **GPT-6 Astra** (OpenAI): coding agent used here as a robot policy, world programmer, and RL environment engineer. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openai.com/index/gpt-6-astra/)

### Eval reports

- **GPT-Policy** / **GPT-Policy-Eval**: VLM agent learns a real-robot plug-insertion policy in-context from one video, without VLA, RL, or DAgger. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://cheng-haha.github.io/GPT-Policy/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/cheng-haha/GPT-Policy-Eval)

- **GPT-as-Policy**, Galaxea AI: public benchmark and report that scores GPT-6 Astra as an embodied policy. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robodojo-benchmark.com/report/gpt-6-astra-eval) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/anonymous-report-421/GPT-as-Policy)

- **RoboCurve GPT-6 Astra evaluation**: controlled YAM-arm study; reports 19/20 bowl-task completions and 80% fewer output tokens. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openai.robocurve.org/gpt-6-astra/)

### Policy programs in simulation

- **Dual-ALOHA Spatial-constraint Puzzles** ([Qineng Wang](https://x.com/qineng_wang)): plans Dual-ALOHA motions that unhook interlocked parts and thread a rope through three rings. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/qineng_wang/status/2099893504658866561) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://qinengwang-aiden.github.io/demos/constraint_demos/)

- **Vision-only Humanoid Body Control** ([ZQ](https://www.rednote.com/user/profile/5f20ee17000000000101c247)): controls a simulated humanoid from camera observations only, with no privileged simulator state. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa7e0f6000000002b01297c?xsec_token=ABmjC06EQ2omZK2bVc-pqYOZHTFYlemRyPYY3Kj_9_a1g=&xsec_source=pc_search&source=web_search_result_notes)

- **G1 Cola Bottle Pick-up in Isaac Sim** ([Flood Sung](https://x.com/RotekSong)): high-level plan for a Unitree G1 cola pick-up; GEAR-SONIC tracks the whole-body qpos. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/RotekSong/status/2099104628562608371)

- **Quadruped Five-key-joint Trajectory** ([Akira Sasaki](https://x.com/gclue_akira)): outputs a sparse five-joint trajectory; a low-level controller runs the quadruped in MuJoCo. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/gclue_akira/status/2098300921658868185)

- **G1 Navigation Tracked by SONIC** ([Flood Sung](https://x.com/RotekSong)): navigation plan for a simulated G1; GEAR-SONIC converts it into a whole-body trajectory. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/RotekSong/status/2098212303263183329/video/1)

- **Robot Hands Solve a Rubik’s Cube** ([Ze Yanjie](https://x.com/ZeYanjie)): zero-shot dexterous cube solving in simulation. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/ZeYanjie/status/2098118164626501669)

- **Dexterous Apple-stem Grasp in SuperDex** ([Kiki Huang](https://www.rednote.com/user/profile/62f72244000000001f0176ea)): dexterous hand grasps the narrow stem of an apple in SuperDex / MuJoCo. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa27b3a000000002b025d03?xsec_token=ABWznjLAd9oNPOxPF1Mc6ZfMK0VKAVH4AMkoYwkdPqQRw=&xsec_source=pc_search&source=web_profile_page)

- **HumanCLAW-Bench** ([Jiawei Gu](https://x.com/Kuvvius)): completes benchmark navigation and interaction tasks through the HumanCLAW-Bench harness. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Kuvvius/status/2098038921301311753)

- **Whole-body Trajectory + Controller** ([橘子不是唯一的水果](https://www.rednote.com/user/profile/695bb2a2000000003702ea8f)): writes a whole-body trajectory; a whole-body controller closes the loop. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6a9fe4df00000000110341b8?xsec_token=ABMaVBcBS54ctuQIxmhMJMZVm36xy72xuPS8s6aICdfXM=&xsec_source=pc_search&source=web_profile_page)

- **Isaac Sim Cube Grasp from One Prompt** ([神秘小孙](https://www.rednote.com/user/profile/5b3f9fc86b58b75d4c02ccc0)): one task sentence builds a depth-camera cube-grasp demo in Isaac Sim. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa017a8000000002b002341?xsec_token=ABeuYgBbxlsBRQGFSm3KRd7TFtNG2CtmpEnSxlcSsSC4E=&xsec_source=pc_like)

- **Physically Writing a Fibonacci Sequence** ([Dmytro Hrybov](https://x.com/dimentary)): long-horizon G1 Fibonacci-writing task in simulation, ending in generated code and motion. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/dimentary/status/2097455860541009958)

- **LLM Harness for Tabletop Robot Control** ([Jiafei Duan](https://x.com/DJiafei)): writes and runs the control loop for a simulated tabletop grasp-and-place task. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/DJiafei/status/2096601096705995155)

### Policy programs on a real robot

- **Learning to Type on a Keyboard** ([Kaifeng Zhang](https://x.com/kaiwynd)): turns an open-ended “express yourself” prompt into real key presses with about 40 minutes of visual feedback. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/kaiwynd/status/2098823484474348008)

- **Marker Grasp from Low-level Control Only** ([star大小变](https://www.rednote.com/user/profile/69c2311e000000003203e786)): discovers joint-to-end-effector control and grasps a marker in about 30 minutes, with no prior skills. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa4d7e200000000260145ff?xsec_token=ABur_B60E14GxVQp2ei3USGtEElW40SN75Vj5aB_USVUA=&xsec_source=pc_search&source=web_profile_page)

- **Mobile Manipulation with In-context Learning** ([Axel](https://x.com/ax_pey)): infers mobile-manipulation behavior from visual context across rooms and layouts, without a task-specific text prompt. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/ax_pey/status/2098216469012283681)

- **Rapid Adaptation to an Unseen Embodiment** ([Lucas Cassiano](https://x.com/lucascassiano)): learns a new robot and [Vitrus AI](https://x.com/Vitrus_ai) control interface online, without human egocentric data or a VLA. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/lucascassiano/status/2097830777438486557)

- **ENPIRE Robotics Harness In-context Learning** ([Tonghe Zhang](https://x.com/TongheZhang01)): in-context robot learning through the ENPIRE harness, without task-specific retraining. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/TongheZhang01/status/2097801107602911243)

- **Cucumber Slicing with Loop-ROS** ([盒子桥](https://www.rednote.com/user/profile/65bb8b3d000000000d03e137)): directly controls a real arm through Loop-ROS for a cucumber-slicing sequence. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa0c4900000000012034a2f?xsec_token=ABYB6HItIwwYq0Yyi9-hwoM-vMalkFRmYMAkN0iUWpTM4=&xsec_source=pc_search&source=web_profile_page)

- **Painting the Golden Gate Bridge** ([thijs](https://x.com/cdngdev)): given a robot, a paintbrush, and a camera, turns a semantic prompt into real brush strokes and improves across attempts. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/cdngdev/status/2097339677128982873)

- **Direct End-effector Pose Control** ([Loule](https://www.rednote.com/user/profile/69ddd8920000000033024ad0)): outputs end-effector poses to put the longest piece of bread into a basket, using third-person and wrist cameras. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6a9fc0710000000029015578?xsec_token=ABMaVBcBS54ctuQIxmhMJMZSAU7Wspgd3bmCnb4tQqHsU=&xsec_source=pc_search&source=web_profile_page)

- **Piper Carrot Pick-and-place** ([虽然不但是](https://www.rednote.com/user/profile/5f5ca72900000000010061fb)): Codex / GPT-6 plus Piper and RealSense; repeated visual pick-and-place of a carrot. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6a9bd4c80000000028037f67?xsec_token=ABLUcokp8Tzdy13Avv1khxst1pWqWBaR7JLjQhUhWsSs4=&xsec_source=pc_like)

### Plan, then call a VLA

- **Zero-shot Task Execution through FluxVLA** ([Jikun](https://www.rednote.com/user/profile/5e25bcdc00000000010085a8)): Astra does task inference and planning; pretrained [FluxVLA](https://github.com/FluxVLA/FluxVLA) runs the low-level actions. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa16835000000000b00f46d?xsec_token=ABDcu5eBZZYkAUcveAv8IZNWsbLmXk6CUM5u5BhDPODB0=&xsec_source=pc_search&source=web_profile_page)

### World programs from video

- **Astra for 4D Shape Fitting** ([Edgar Sucar](https://x.com/SucarEdgar)): fits a 4D shape from video, using a human tip that leaves are symmetric to constrain the fit. Takes hours and back-and-forth prompting. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/SucarEdgar/status/2101739645759361322)

- **Lab Kitchen Reconstruction** ([Frank ZY Dou](https://www.rednote.com/user/profile/5e3431cf0000000001002919)): rebuilds a lab kitchen with articulated cabinets from a 20-second monocular RGB video. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa4d64c000000000b037809?xsec_token=ABur_B60E14GxVQp2ei3USGkgJntlivJm_02tlDaUFWmg=&xsec_source=pc_search&source=web_profile_page)

- **Rope-driven Dexterous Hand Reconstruction** ([Dmytro Hrybov](https://x.com/dimentary)): recreates 1X’s tendon-driven hand demo in MuJoCo, with simplified tendon mechanics. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/dimentary/status/2097857980150763900)

- **Tendon-driven Dexterous Hand Motion Reconstruction** ([Jake Fitzgerald](https://x.com/earthtojake)): designs a tendon-driven hand and reconstructs cable-actuated finger motion in simulation. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/earthtojake/status/2097789988670709821)

- **Dexterous Hand-object Data Rollout** ([Lingxiao](https://x.com/Lingxiao234)): two videos drive real-to-sim reconstruction and physical retargeting onto Wuji hands, without explicit states or actions. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Lingxiao234/status/2097717020540481630)

- **Video in → Physics out** ([xiao hu](https://x.com/huxiao93612565)): writes hand tracking, IK retargeting, and grasp-refinement code for a 44-DoF hand. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/huxiao93612565/status/2097815230105399402)

- **Multi-view Real-to-sim Reconstruction** ([Lingxiao](https://x.com/Lingxiao234)): builds a replayable MuJoCo / Blender simulator from multi-view RGB, robot actions, calibration, assets, and system identification. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Lingxiao234/status/2096992059731443923)

### RL training stacks

- **Sharpa Hand Pen-spinning RL** ([Wentao Zhu](https://x.com/walterzhu8) / Chengyang Li): autonomous ~1.5-day run that builds the pen mesh, an Isaac Lab Sharpa-hand task, a PPO policy, and a visualization video. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/walterzhu8/status/2100212420840989112)

- **RL-trained Duck Robot** ([拂晓时分_茉莉飘香](https://www.rednote.com/user/profile/5ffbc96d00000000010060ae)): one image and one description become an RL-trained duck locomotion demo. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa347e2000000000b036667?xsec_token=AB1z4k50CvQ0PFZpqtQXWYlVMONqE2yr3ER8jk-hVWI74=&xsec_source=pc_search&source=web_profile_page)

- **Quadruped Locomotion from RL** ([Akira Sasaki](https://x.com/gclue_akira)): co-designs a robot dog, iterates 25 loops in five days, and trains nine simulated motions with RL. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/gclue_akira/status/2098300921658868185)

- **Dexterous In-hand Manipulation RL** ([十一](https://www.rednote.com/user/profile/610bc8f100000000200284e2)): trains in-hand walnut manipulation; the reported run did not enable self-collision. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa3e146000000002b0123dc?xsec_token=AB5n_GSvnshtGoIJqykTNpkWlIS-zHnIYe2n5pAiGLSgw=&xsec_source=pc_like)

- **Office Scan → Newton / G1 Gym** ([Jiarui Xu](https://x.com/Jiarui_X)): rebuilds an office scan in Blender, exports USD, and makes a G1 walking scene in Newton. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Jiarui_X/status/2098439950991806804)

- **Isaac Sim Environment, PPO Training, and Tuning** ([十一](https://www.rednote.com/user/profile/610bc8f100000000200284e2)): builds an Isaac Sim RL environment, configures PPO, and iterates the run in one workflow. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa29087000000002600bb2e?xsec_token=ABupW63bXfa1dAqIk6vaYviNev-xOXuTmePvxk8Su9NK4=&xsec_source=pc_collect)

