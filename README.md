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
    - [Robot evaluation infrastructure](#robot-evaluation-infrastructure)

**Surveys and Lessons**
- 📚 [Surveys and Lessons](#surveys-and-lessons)

**Projects**
- 🛠️ [Projects](#projects)
    - [Eval reports](#eval-reports)
    - [Policy programs in simulation](#policy-programs-in-simulation)
    - [Policy programs on a real robot](#policy-programs-on-a-real-robot)
    - [Plan, then call a VLA](#plan-then-call-a-vla)
    - [World programs from video](#world-programs-from-video)
    - [RL training stacks](#rl-training-stacks)
    - [Scene programs](#scene-programs)

**Related Resources**
- 🔗 [Related Resources](#related-resources)

## Aim
We collect papers where an agent writes or edits a program, a tool graph, or an explicit world state, then a simulator, renderer, robot, or editor runs it. That includes robot policies, executable scenes, programmable world models, image or video edit graphs, and benchmarks for those agents. Systems, evals, and case catalogs without a paper go under Projects, not under the paper sections.

New papers and projects get added as they appear. PRs are welcome.

## Policy Program Definition
A Code-as-Policy agent is an LLM or VLM that writes executable robot programs, or a thin semantic action interface. That is the alternative to VLA action tokens. The name comes from Code as Policies.

- [⭐️] **Code as Policies**: Language Model Programs for Embodied Control. [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b.svg)](https://arxiv.org/abs/2209.07753) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-policies.github.io)

## World Program Definition
A world program is an executable scene or physics program in Blender, MuJoCo, USD, CadQuery, or a similar stack. It is not a static mesh and not a video. Generation writes the program from language or a layout. Inversion / Reconstruction writes it from images, video, or scans.

- [⭐️] **SceneCode**: Executable World Programs for Editable Indoor Scenes with Articulated Objects. [![arXiv](https://img.shields.io/badge/arXiv-2605.19587-b31b1b.svg)](https://arxiv.org/abs/2605.19587) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://scene-code.github.io/)

Physical Coding, from Self-Evolving Coding Agents: From Digital Programs to Physical-World Intelligence, also uses Code as World for symbolic robot task state: objects, relations, constraints, observations, and progress predicates. That is separate from the executable scene programs grouped below; see [Physical Coding / HexaAnything](#code-as-policy). [![arXiv](https://img.shields.io/badge/arXiv-2609.35432-b31b1b.svg)](https://arxiv.org/abs/2609.35432) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HexaFuture/PhysicalCoding)

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

- **RACaP**, Agentic Reasoning, Acting, and Coding as Policies for Evolvable Robot Learning: evolves typed Policy APIs offline, then a runtime ReAct loop calls the frozen APIs. [![arXiv](https://img.shields.io/badge/arXiv-2609.29394-b31b1b.svg)](https://arxiv.org/abs/2609.29394)

- **RoboDawn**, Transferring the Intelligence of VLMs to Robotic Control: gives the VLM a thin discrete command interface that grounds `move`, `rotate`, `gripper`, and related commands into motion. [![arXiv](https://img.shields.io/badge/arXiv-2609.22966-b31b1b.svg)](https://arxiv.org/abs/2609.22966) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robodawn.top/)

- **GPT-Policy**, In-Context Robot Learning with VLM Agents: compiles context for a VLM agent that issues robot-tool commands through a constrained controller. [![arXiv](https://img.shields.io/badge/arXiv-2609.19138-b31b1b.svg)](https://arxiv.org/abs/2609.19138) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://cheng-haha.github.io/GPT-Policy/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/cheng-haha/GPT-Policy-Eval)

- **RoboDojo GPT-6 Astra evaluation**, An Unexpected Robot Policy: Early Evaluations of GPT-6 Astra on RoboDojo and Beyond: runs a VLM policy through the fixed RoboProbe harness on 42 simulation tasks and 2,100 trials; reports 28.97 average score and 22.48% average success, with real-robot testing halted for safety. [![arXiv](https://img.shields.io/badge/arXiv-2609.24170-b31b1b.svg)](https://arxiv.org/abs/2609.24170) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robodojo-benchmark.com/report/gpt-6-astra-eval)

- **SafeHarness**, Coding Agents with an Obstacle-Aware Harness for Safe Robot Manipulation: adds obstacle-aware routing and contact execution to reduce collisions in generated robot controllers. [![arXiv](https://img.shields.io/badge/arXiv-2609.20822-b31b1b.svg)](https://arxiv.org/abs/2609.20822)

- **WetRobo**, A Reproducible Robot Kit for Coding Agents in Biological Laboratories: lets agents write and execute lab protocols while calling perception, planning, and simulation tools. [![arXiv](https://img.shields.io/badge/arXiv-2609.18435-b31b1b.svg)](https://arxiv.org/abs/2609.18435)

- **AGP**, Agent as Policy for Robotic Manipulation: writes runtime programs, executes them, and revises the policy from physical feedback. [![arXiv](https://img.shields.io/badge/arXiv-2609.12541-b31b1b.svg)](https://arxiv.org/abs/2609.12541) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/agent-as-policy-2026/agent-as-policy)

- **PhysCaP**, Grounding Code-as-Policy Agent with Physics-Informed Exploration: adds information-seeking interactions to estimate hidden physical properties for robot manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2608.21031-b31b1b.svg)](https://arxiv.org/abs/2608.21031) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://physcap.github.io/)

- **Agentic Push-T**, Revisiting the "Push-T" Robot Manipulation Task with Agentic Robotics: has a coding agent write the manipulation algorithm for Push-T without demonstrations. [![arXiv](https://img.shields.io/badge/arXiv-2608.18227-b31b1b.svg)](https://arxiv.org/abs/2608.18227)

- **GaP**, A Graph-as-Policy Multi-Agent Self-Learning Harness for Variational Automation Tasks: represents policy as a directed perception-planning-control graph and refines it in simulation. [![arXiv](https://img.shields.io/badge/arXiv-2607.05369-b31b1b.svg)](https://arxiv.org/abs/2607.05369)

- **ASPIRE**: Agentic /Skills Discovery for Robotics. Writes and repairs control programs from execution traces, then stores validated fixes in a reusable skill library. [![arXiv](https://img.shields.io/badge/arXiv-2607.00272-b31b1b.svg)](https://arxiv.org/abs/2607.00272) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/NVlabs/ASPIRE)

- **ENPIRE**: Agentic Robot Policy Self-Improvement in the Real World. Resets scenes, executes policies, verifies outcomes, and refines policy or training code from real-robot feedback. [![arXiv](https://img.shields.io/badge/arXiv-2606.19980-b31b1b.svg)](https://arxiv.org/abs/2606.19980) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/enpire/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/NVlabs/ENPIRE)

- [⭐️] **CaP-X**: A Framework for Benchmarking and Improving Coding Agents for Robot Manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2603.22435-b31b1b.svg)](https://arxiv.org/abs/2603.22435) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://capgym.github.io)

- [⭐️] **RATs**, Playful Agentic Robot Learning. [![arXiv](https://img.shields.io/badge/arXiv-2606.19419-b31b1b.svg)](https://arxiv.org/abs/2606.19419) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://Playful-RATs.github.io/)

- [⭐️] **Show-Harness**: Just a VLM Agent Can Play Robots. [![arXiv](https://img.shields.io/badge/arXiv-2609.10522-b31b1b.svg)](https://arxiv.org/abs/2609.10522) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://showlab.github.io/Show-Harness/)

- **Physical Coding / HexaAnything**, Self-Evolving Coding Agents: From Digital Programs to Physical-World Intelligence: uses Code as World for symbolic task state and Code as Policy for execution; HexaAnything routes perception, planning, control, and VLA / WAM tools, verifies outcomes, and persists accepted traces as memory or training data. [![arXiv](https://img.shields.io/badge/arXiv-2609.35432-b31b1b.svg)](https://arxiv.org/abs/2609.35432) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HexaFuture/PhysicalCoding)

- **Harness VLA**: memory and visual feedback compose frozen VLA calls with analytic motion primitives. [![arXiv](https://img.shields.io/badge/arXiv-2607.08448-b31b1b.svg)](https://arxiv.org/abs/2607.08448) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://harnessvla.github.io/)

- **Recursive Harness Distillation**: Astra writes a playbook and revises it from Luna’s execution feedback, so the cheaper agent can guide a frozen VLA. [![arXiv](https://img.shields.io/badge/arXiv-2609.33378-b31b1b.svg)](https://arxiv.org/abs/2609.33378) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://seungyeon.me/RHD/)

- **RoboICL**: frozen GPT-6 Astra controls a robot from demonstration context and bounded interaction memory, without robot-specific finetuning or a learned VLA. [![arXiv](https://img.shields.io/badge/arXiv-2609.34261-b31b1b.svg)](https://arxiv.org/abs/2609.34261) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://mosi-ai.github.io/RoboICL-GPT6-Astra.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Mosi-AI/RoboICL)

- **SimEX**: a coding agent grows a toolbox of perception and action primitives in simulation, then writes a fresh code-as-policies script per instruction. Five real-robot trials adapt the toolbox and the simulator together. [![arXiv](https://img.shields.io/badge/arXiv-2609.38982-b31b1b.svg)](https://arxiv.org/abs/2609.38982) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robo-simex.github.io/)

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

- **AstraLOD3**: multi-view evidence to an editable building reconstruction. [![arXiv](https://img.shields.io/badge/arXiv-2609.28061-b31b1b.svg)](https://arxiv.org/abs/2609.28061)

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

- **Video2World**: 222 tasks from 189 embodied videos; coding agents rebuild interactive simulated worlds. Astra ranks 2nd of 9 (V2WScore 43.55, 10.7% success) with the most accurate geometry, still far below the human-assisted reference. [![arXiv](https://img.shields.io/badge/arXiv-2610.04432-b31b1b.svg)](https://arxiv.org/abs/2610.04432) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://aetherlabsai.github.io/Video2World/)

- **4DCodeBench**: agents write executable code that reconstructs dynamic scenes from 200 videos. Astra Max leads 18 agents (overall 0.79) and leads dynamics by 31%. [![arXiv](https://img.shields.io/badge/arXiv-2610.03715-b31b1b.svg)](https://arxiv.org/abs/2610.03715) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://4dcodebench.com/)

- **Moonlake 3D Agent**: sim-ready asset benchmark across 22 metrics and Isaac Sim interaction tests; reported rank score 65.2 versus Astra 47.0. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://moonlakeai.com/blog/evaluating-3d-agent)

### Robot evaluation infrastructure

These evaluate robot policies broadly, including learned policies and program or command interfaces. They are policy-evaluation infrastructure, not code-generation benchmarks.

- **XPolicyLab**: A Unified Standard and Open Ecosystem for Robot Policy Evaluation and Deployment. [![arXiv](https://img.shields.io/badge/arXiv-2608.09892-b31b1b.svg)](https://arxiv.org/abs/2608.09892) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/XPolicyLab/XPolicyLab)

- **RoboDojo**: A Unified Sim-and-Real Benchmark for Comprehensive Evaluation of Generalist Robot Manipulation Policies. [![arXiv](https://img.shields.io/badge/arXiv-2607.04434-b31b1b.svg)](https://arxiv.org/abs/2607.04434) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/robodojo-benchmark/RoboDojo)

- **HumanCLAW**: Can Vision-Language Models Act Through a Body? Tests VLM decisions through a harness that turns them into humanoid motion-generator calls. [![arXiv](https://img.shields.io/badge/arXiv-2607.27180-b31b1b.svg)](https://arxiv.org/abs/2607.27180)

## Surveys and Lessons

- **Weights or Skills?** A Survey of Robot-Learning Techniques: from Action-Predicting Weights to Robots that Write their Own Skills: frames the split between frozen action-predicting weights and executable robot skills. [![arXiv](https://img.shields.io/badge/arXiv-2608.01851-b31b1b.svg)](https://arxiv.org/abs/2608.01851)

- **Code as Agent Harness**: surveys executable, verifiable, stateful harness design for agents that write and run code. [![arXiv](https://img.shields.io/badge/arXiv-2605.18747-b31b1b.svg)](https://arxiv.org/abs/2605.18747)

- **What Stops Recursive Self-Improvement in Robotics?** Lessons from 123 Rounds of Agentic Skill Discovery: reports an agent that wrote, installed, and tested skills, but never solved the target fridge task; relational perception, early-skill bottlenecks, and evaluator behavior were the main failure points. [![arXiv](https://img.shields.io/badge/arXiv-2609.31760-b31b1b.svg)](https://arxiv.org/abs/2609.31760)

## Projects

X posts, Xiaohongshu posts, and webpage-only systems. Papers stay in the sections above. Case catalog: [Awesome Astra Embodied AI](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI).

- [⭐️] **Awesome Astra Embodied AI**: GPT-6 Astra case catalog for embodied workflows. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI)

- **GPT-6 Astra** (OpenAI): coding agent used here as a robot policy, world programmer, and RL environment engineer. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openai.com/index/gpt-6-astra/)

### Eval reports

- **GPT-as-Policy**, Galbot: public benchmark and report that scores GPT-6 Astra as an embodied policy. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/anonymous-report-421/GPT-as-Policy)

- **RoboCurve GPT-6 Astra evaluation**: controlled YAM-arm study; reports 19/20 bowl-task completions and 80% fewer output tokens. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openai.robocurve.org/gpt-6-astra/)

- **RPent** (RLinf): recursive harness that pairs an agentic planner with frozen VLA primitives. The leaderboard reports GPT-6 Astra at 92.63% overall on LIBERO-PRO (741/800) and 59.20% on RoboCasa365 Target50. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/RLinf/RPent)

- **Astra on RoboMME**: three-tier controller on 16 RoboMME tasks; reports 79.13% success (633/800) with 3.63 Astra planning calls per episode. A fine-tuned π0.5 runs the subtask, and a Qwen3-VL-4B monitor decides when Astra should replan. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://bingaochen.github.io/Astra-on-RoboMME/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/bingaochen/Astra-on-RoboMME)

- **RoboICL**: frozen Astra on 30 RoboDojo tasks; reports overall progress 50.64, zero-shot on Open and one demonstration elsewhere, plus three real-robot tasks. See also [RoboICL](#code-as-policy). [![Website](https://img.shields.io/badge/Website-Link-blue)](https://mosi-ai.github.io/RoboICL-GPT6-Astra.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Mosi-AI/RoboICL)

### Policy programs in simulation

- **UR10 conveyor sorting** (NVIDIA Omniverse): Astra builds a conveyor and inspection scene in VS Code, then wires a UR10 and Robotiq gripper to sort rejects. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://nvidia-omniverse.github.io/omniverse-labs/projects/astra-vscode-simulation/)

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

- **SimEX on a dual-arm YAM**: after sim autoresearch, about ten minutes of real-robot time per task covers barcode scanning, plate-to-tote, and towel folding. See also [SimEX](#code-as-policy). [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robo-simex.github.io/)

- **Mocap whip and lasso** ([Krishna Suresh](https://krishnasuresh.org/blog/2026/robot-whips/)): one prompt builds IK, dynamics-constrained trajectory optimization, and an inverse-dynamics controller so an OpenarmX and an xArm7 replay whip cracking and cleat lassoing open-loop. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://krishnasuresh.org/blog/2026/robot-whips/)

### Plan, then call a VLA

- **Harness VLA / RPent**: Astra plans with memory and visual feedback, then calls a frozen VLA plus a fixed library of analytic motion primitives. The real-robot demo sorts plates and retries a failed grasp without fine-tuning the VLA. See also [Harness VLA](#code-as-policy). [![Website](https://img.shields.io/badge/Website-Link-blue)](https://harnessvla.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/RLinf/RPent)

- **Recursive Harness Distillation**: Astra distills robot problem solving into a playbook and revises it from Luna’s feedback, so Luna can steer a frozen VLA. See also [Recursive Harness Distillation](#code-as-policy). [![Website](https://img.shields.io/badge/Website-Link-blue)](https://seungyeon.me/RHD/)

- **Astra on RoboMME**: Astra plans subtasks from instructions and visual history; a fine-tuned π0.5 executes them, and a fine-tuned Qwen3-VL-4B says when the subtask is done. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://bingaochen.github.io/Astra-on-RoboMME/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/bingaochen/Astra-on-RoboMME)

- **Zero-shot Task Execution through FluxVLA** ([Jikun](https://www.rednote.com/user/profile/5e25bcdc00000000010085a8)): Astra does task inference and planning; pretrained [FluxVLA](https://github.com/FluxVLA/FluxVLA) runs the low-level actions. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa16835000000000b00f46d?xsec_token=ABDcu5eBZZYkAUcveAv8IZNWsbLmXk6CUM5u5BhDPODB0=&xsec_source=pc_search&source=web_profile_page)

### World programs from video

- **Astra for 4D Shape Fitting** ([Edgar Sucar](https://x.com/SucarEdgar)): fits a 4D shape from video, using a human tip that leaves are symmetric to constrain the fit. Takes hours and back-and-forth prompting. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/SucarEdgar/status/2101739645759361322)

- **Guan’s Fencing Club**: match video, two animated fencers, and a procedural hall on a UE5 timeline, with a one-second sword-tip trail. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/samguan2020/guans-fencing-club)

- **Lab Kitchen Reconstruction** ([Frank ZY Dou](https://www.rednote.com/user/profile/5e3431cf0000000001002919)): rebuilds a lab kitchen with articulated cabinets from a 20-second monocular RGB video. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa4d64c000000000b037809?xsec_token=ABur_B60E14GxVQp2ei3USGkgJntlivJm_02tlDaUFWmg=&xsec_source=pc_search&source=web_profile_page)

- **Rope-driven Dexterous Hand Reconstruction** ([Dmytro Hrybov](https://x.com/dimentary)): recreates 1X’s tendon-driven hand demo in MuJoCo, with simplified tendon mechanics. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/dimentary/status/2097857980150763900)

- **Tendon-driven Dexterous Hand Motion Reconstruction** ([Jake Fitzgerald](https://x.com/earthtojake)): designs a tendon-driven hand and reconstructs cable-actuated finger motion in simulation. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/earthtojake/status/2097789988670709821)

- **Dexterous Hand-object Data Rollout** ([Lingxiao](https://x.com/Lingxiao234)): two videos drive real-to-sim reconstruction and physical retargeting onto Wuji hands, without explicit states or actions. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Lingxiao234/status/2097717020540481630)

- **Video in → Physics out** ([xiao hu](https://x.com/huxiao93612565)): writes hand tracking, IK retargeting, and grasp-refinement code for a 44-DoF hand. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/huxiao93612565/status/2097815230105399402)

- **Multi-view Real-to-sim Reconstruction** ([Lingxiao](https://x.com/Lingxiao234)): builds a replayable MuJoCo / Blender simulator from multi-view RGB, robot actions, calibration, assets, and system identification. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Lingxiao234/status/2096992059731443923)

### RL training stacks

- **Office Real2Sim2Real Cart Push** ([watchtower](https://www.rednote.com/user/profile/5e38ca4e00000000010034fa)): rebuilds an office, estimates contact supervision, trains an RL cart-push policy with SONIC for whole-body motion, then deploys it on the real humanoid. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6ab34cfd0000000018005cab?xsec_token=CBoKOnuhKTqoyv12enaYThxB4L_a-12BnOafHa5vF3aRw=&xsec_source=app_share)

- **Sharpa Hand Pen-spinning RL** ([Wentao Zhu](https://x.com/walterzhu8) / Chengyang Li): autonomous ~1.5-day run that builds the pen mesh, an Isaac Lab Sharpa-hand task, a PPO policy, and a visualization video. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/walterzhu8/status/2100212420840989112)

- **RL-trained Duck Robot** ([拂晓时分_茉莉飘香](https://www.rednote.com/user/profile/5ffbc96d00000000010060ae)): one image and one description become an RL-trained duck locomotion demo. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa347e2000000000b036667?xsec_token=AB1z4k50CvQ0PFZpqtQXWYlVMONqE2yr3ER8jk-hVWI74=&xsec_source=pc_search&source=web_profile_page)

- **Quadruped Locomotion from RL** ([Akira Sasaki](https://x.com/gclue_akira)): co-designs a robot dog, iterates 25 loops in five days, and trains nine simulated motions with RL. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/gclue_akira/status/2098300921658868185)

- **Dexterous In-hand Manipulation RL** ([十一](https://www.rednote.com/user/profile/610bc8f100000000200284e2)): trains in-hand walnut manipulation; the reported run did not enable self-collision. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa3e146000000002b0123dc?xsec_token=AB5n_GSvnshtGoIJqykTNpkWlIS-zHnIYe2n5pAiGLSgw=&xsec_source=pc_like)

- **Office Scan → Newton / G1 Gym** ([Jiarui Xu](https://x.com/Jiarui_X)): rebuilds an office scan in Blender, exports USD, and makes a G1 walking scene in Newton. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Jiarui_X/status/2098439950991806804)

- **Isaac Sim Environment, PPO Training, and Tuning** ([十一](https://www.rednote.com/user/profile/610bc8f100000000200284e2)): builds an Isaac Sim RL environment, configures PPO, and iterates the run in one workflow. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa29087000000002600bb2e?xsec_token=ABupW63bXfa1dAqIk6vaYviNev-xOXuTmePvxk8Su9NK4=&xsec_source=pc_collect)

### Scene programs

Astra writes a scene, CAD model, or playable world as code, then Blender, OpenSCAD, Three.js, or a game engine runs it. The full set is 285 examples in [Awesome Astra 3D](https://github.com/carpentry-liu/awesome-astra-3d) ([gallery](https://carpentry-liu.github.io/awesome-astra-3d/)). Entries below are source-backed starting points, grouped by the program that gets executed. Video-only renders stay in that atlas.

- [⭐️] **Awesome Astra 3D**: Blender, Houdini, Three.js, CAD, VRM, and interactive-game case catalog. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/carpentry-liu/awesome-astra-3d) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://carpentry-liu.github.io/awesome-astra-3d/)

#### Executable scenes

- **Solace**: architectural iteration through Blender, Cycles, and UE5. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://developers.openai.com/blog/architectural-visualization-with-astra)

- **Pelican on a bicycle**: three Blender iterations with editable meshes and recorded conversations. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/simonw/gpt-6-astra-blender-pelican-bicycle)

- **GPTBlender floor plan**: turns a floor plan into a downloadable furnished home. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://gptblender.com/turn-floor-plan-into-3d-model-gpt6-astra/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/qduoduo-hwh/gptblender_demo)

- **Realsee**: scan to an editable Blender space, with roaming video and prompts. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/realsee-developer/realsee-astra-blender)

- **Orbital Core**: Blender and GLB assets inside an interactive Three.js page. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/wangruofeng/orbital-core-showcase)

- **Piața Unirii**: same brief, voxel square, prompt and source kept. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/danmana/piata-unirii)

- **Real2Sim rooms**: photos to editable rooms, with failed reconstructions kept in the repo. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Roboparty/gpt-6-astra-real2sim-workflow)

- **Jetis**: DWG factory walkthrough exported as a native SketchUp model. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/bambssquad/jetis-digital-twin-astra)

- **WorldGen**: three text scenes built in Blender and Unity. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/andyyuyc/WorldGen_Unity)

- **Junya city generator**: JSON road networks become an editable Blender scene, then Unreal renders. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/junya-tashiro/agent-jp-citygen)

- **Renders**: four Blender architecture projects with revision scripts and an archive of older cuts. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/lucas-chu/Renders)

#### CAD programs

- **J-hook**: OpenSCAD print design compared across models; strength testing still pending. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/WescheNex1q/status/2104590493191479337)

- **Villa, recursive film, turbine CAD**: three editable 3D projects in one repo. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/az9713/gpt-6-3d-projects)

- **Realitizer**: Swift code-first models of a manta ray and a house. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/koher/realitizer)

- **Aetheris difference engine**: hierarchical CAD of digit wheels, carry gears, and a crank, with STEP export. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/yuechen-li-dev/Aetheris/tree/master/demos/Aetheris.DifferenceEngine.Showcase)

- **LDraw Nova**: Python generators emit editable LDraw cathedrals and a tidal observatory. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/anteloc/ldraw-nova)

- **DeepSeek whale**: a logo silhouette becomes an editable single-solid desktop print mesh. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/shyrz/gpt-6-astra-3dp-test)

#### Playable world programs

- **Living Deep**: extends an existing ocean simulation with underwater ecology. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/emollick/abyssal-living-deep)

- **Smash Karts**: multiplayer client, server, and a public agent trajectory. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/amsminn/gpt-6-astra-smash-karts)

- **Little Flock**: one-shot pasture world, with the goal prompt in the repo. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/songkeys/little-flock)

- **Windfield**: 3D adventure plus a terrain editor. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/fuguai1/status/2104531704740512143)

- **Melon Jelly**: WebGPU soft-body comparison. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/esrhengwu/status/2104504957173153951)

- **Pelagic**: procedural ocean and sailboat exploration. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/az9713/gpt-6-astra-3D-ocean)

- **H3 Battle Lab**: 3D units wired to native VCMI combat. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/yzh119/h3-battle-lab)

- **Seabright**: Unity coastal city builder with roads, services, and taxes. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/codersusu/game-city-skylines)

- **Octane Arena**: procedural 3D car soccer with source for the physics. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Goofykings/Octane-Arena)

- **Astra Air Combat**: seeded arenas and a 60 Hz dogfight loop. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/FLYING37520/astra-air-combat)

## Related Resources

- **Awesome Physical AI**: broader curated reading list for robot-policy VLMs, coding agents, policy harnesses, and RoboDojo-style scorecards. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HexaFuture/Awesome-Physical-AI)
