<div align="center">

# Awesome Code as Policy/World/Editor

**Coding-agent papers that treat a program as the intermediate representation.** </br>

<p align="center">
  <img src="assets/awesome-code-as-x.png" alt="Awesome Code as X" width="100%" style="border-radius: 15px; box-shadow: 0 4px 24px rgba(0,0,0,.1); margin: 5px 0;">
</p>

[English](README.md) | [中文](README.zh.md) | [HF Blog](https://huggingface.co/blog/kkakkkka/from-coding-agents-to-physical-agents) | [中文解读](https://mp.weixin.qq.com/s/MuOz0KmmQa5CxzjY7WEEvA) | [SourceMind](assets/sourcemind.jpg)

</div>

## Overview
- 🎯 [Aim](#aim)
- 📚 [Definitions](#definitions)
- 🦾 [Code as Policy](#code-as-policy)
- 🗺️ [Code as World](#code-as-world)
- 🧮 [Programmable World Models](#programmable-world-models)
- ✂️ [Edit Graph](#edit-graph)
- 📊 [Benchmark](#benchmark)
    - [Policy programs](#policy-programs)
    - [World programs](#world-programs)
    - [Robot evaluation infrastructure](#robot-evaluation-infrastructure)
- 📚 [Surveys and Lessons](#surveys-and-lessons)
- 🛠️ [Projects](#projects)
    - [Eval reports](#eval-reports)
    - [Policy programs in simulation](#policy-programs-in-simulation)
    - [Policy programs on a real robot](#policy-programs-on-a-real-robot)
    - [Plan, then call a VLA](#plan-then-call-a-vla)
    - [World programs from video](#world-programs-from-video)
    - [RL training stacks](#rl-training-stacks)
    - [Scene programs](#scene-programs)
- 🔗 [Related Resources](#related-resources)

## Aim
We collect papers where an agent writes or edits a program, a tool graph, or an explicit world state, then a simulator, renderer, robot, or editor runs it. That includes robot policies, executable scenes, programmable world models, image or video edit graphs, and benchmarks for those agents. Systems, evals, and case catalogs without a paper go under Projects, not under the paper sections.

New papers and projects get added as they appear. PRs are welcome.

## Definitions

- [Policy program](#def-policy-program)
- [World program](#def-world-program)
- [Programmable world model](#def-programmable-world-model)
- [Edit graph](#def-edit-graph)
- [Benchmark](#def-benchmark)
- [Project](#def-project)

<a id="def-policy-program"></a>
**Policy program.** A Code-as-Policy agent is an LLM or VLM that writes executable robot programs, or a thin semantic action interface. That is the alternative to VLA action tokens. The name comes from Code as Policies.

- [⭐️] **Code as Policies**: Language Model Programs for Embodied Control. [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b.svg)](https://arxiv.org/abs/2209.07753) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-policies.github.io)

<a id="def-world-program"></a>
**World program.** A world program is an executable scene or physics program in Blender, MuJoCo, USD, CadQuery, or a similar stack. It is not a static mesh and not a video. Generation writes the program from language or a layout. Inversion / Reconstruction writes it from images, video, or scans.

- [⭐️] **SceneCode**: Executable World Programs for Editable Indoor Scenes with Articulated Objects. [![arXiv](https://img.shields.io/badge/arXiv-2605.19587-b31b1b.svg)](https://arxiv.org/abs/2605.19587) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://scene-code.github.io/)

Physical Coding, from Self-Evolving Coding Agents: From Digital Programs to Physical-World Intelligence, also uses Code as World for symbolic robot task state: objects, relations, constraints, observations, and progress predicates. That is separate from the executable scene programs grouped below; see [Physical Coding / HexaAnything](#code-as-policy). [![arXiv](https://img.shields.io/badge/arXiv-2609.35432-b31b1b.svg)](https://arxiv.org/abs/2609.35432) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HexaFuture/PhysicalCoding)

<a id="def-programmable-world-model"></a>
**Programmable world model.** Programmable world models keep state and transitions in code. The generator or renderer only handles how things look.

- [⭐️] **Code World Model**: Coding Agent as World Brain. [![arXiv](https://img.shields.io/badge/arXiv-2608.25927-b31b1b.svg)](https://arxiv.org/abs/2608.25927) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://buaacyw.github.io/cwm/)

<a id="def-edit-graph"></a>
**Edit graph.** An edit graph is a sequence of tool calls, a visual program, or a timeline patch. You can inspect it and roll it back. VisProg is an early example.

- [⭐️] **VisProg**, Visual Programming: Compositional Visual Reasoning Without Training. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://prior.allenai.org/projects/visprog)

<a id="def-benchmark"></a>
**Benchmark.** These benchmarks test whether a coding agent can write, run, and revise a program. RLE-Bench is the policy side: robot learning, training stacks, and control. PhysCodeGym is the world side: reconstruct a video as an executable Blender program and check that the physics holds.

- [⭐️] **RLE-Bench**: A Qualifying Exam for Coding Agents as Robot Learning Engineers. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rle-bench.github.io/)

- [⭐️] **PhysCodeGym**: Benchmarking Coding Agents for Physically Verifiable 4D Reconstruction. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/ShaoShuai0605/PhysCodeGym) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://huggingface.co/datasets/ShaoShuai0605/PhysCodeGym)

<a id="def-project"></a>
**Project.** A project here is an X post, Xiaohongshu post, webpage-only system, or eval whose primary artifact is not a paper. The coding agent still writes a program as the IR, or closed-loop controls a robot or simulator from code.

- [⭐️] **Awesome Astra Embodied AI**: GPT-6 Astra with embodied AI / robotics workflows and demos. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/zjwzcx/Awesome-Astra-Embodied-AI)

## Code as Policy

- [⭐️] **Code as Policies**: Language Model Programs for Embodied Control. [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b.svg)](https://arxiv.org/abs/2209.07753) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-policies.github.io)

- [⭐️] **CaP-X**: A Framework for Benchmarking and Improving Coding Agents for Robot Manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2603.22435-b31b1b.svg)](https://arxiv.org/abs/2603.22435) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://capgym.github.io)

- [⭐️] **RATs**, Playful Agentic Robot Learning. [![arXiv](https://img.shields.io/badge/arXiv-2606.19419-b31b1b.svg)](https://arxiv.org/abs/2606.19419) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://Playful-RATs.github.io/)

- [⭐️] **Show-Harness**: Just a VLM Agent Can Play Robots. [![arXiv](https://img.shields.io/badge/arXiv-2609.10522-b31b1b.svg)](https://arxiv.org/abs/2609.10522) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://showlab.github.io/Show-Harness/)

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

- **Physical Coding / HexaAnything**, Self-Evolving Coding Agents: From Digital Programs to Physical-World Intelligence: uses Code as World for symbolic task state and Code as Policy for execution; HexaAnything routes perception, planning, control, and VLA / WAM tools, verifies outcomes, and persists accepted traces as memory or training data. [![arXiv](https://img.shields.io/badge/arXiv-2609.35432-b31b1b.svg)](https://arxiv.org/abs/2609.35432) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HexaFuture/PhysicalCoding)

- **Harness VLA**: memory and visual feedback compose frozen VLA calls with analytic motion primitives. [![arXiv](https://img.shields.io/badge/arXiv-2607.08448-b31b1b.svg)](https://arxiv.org/abs/2607.08448) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://harnessvla.github.io/)

- **Recursive Harness Distillation**: Astra writes a playbook and revises it from Luna’s execution feedback, so the cheaper agent can guide a frozen VLA. [![arXiv](https://img.shields.io/badge/arXiv-2609.33378-b31b1b.svg)](https://arxiv.org/abs/2609.33378) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://seungyeon.me/RHD/)

- **RoboICL**: frozen GPT-6 Astra controls a robot from demonstration context and bounded interaction memory, without robot-specific finetuning or a learned VLA. [![arXiv](https://img.shields.io/badge/arXiv-2609.34261-b31b1b.svg)](https://arxiv.org/abs/2609.34261) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://mosi-ai.github.io/RoboICL-GPT6-Astra.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Mosi-AI/RoboICL)

- **SimEX**: a coding agent grows a toolbox of perception and action primitives in simulation, then writes a fresh code-as-policies script per instruction. Five real-robot trials adapt the toolbox and the simulator together. [![arXiv](https://img.shields.io/badge/arXiv-2609.38982-b31b1b.svg)](https://arxiv.org/abs/2609.38982) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robo-simex.github.io/)

- **OpenRUA**: coding agents use native ROS 2 from the terminal, treat sensor readings as file I/O, and revise manipulation programs from execution feedback. [![arXiv](https://img.shields.io/badge/arXiv-2610.02459-b31b1b.svg)](https://arxiv.org/abs/2610.02459)

- **URAI**, Make Code as Policy Great Again: a programming agent writes and revises reusable robot tools; an execution agent picks tools between complete local motions. [![arXiv](https://img.shields.io/badge/arXiv-2609.39018-b31b1b.svg)](https://arxiv.org/abs/2609.39018)

- **EmbodiedSWE**: coding agents solve long-horizon dexterous tasks, then turn successful programs into simulation demonstrations for policy training. [![arXiv](https://img.shields.io/badge/arXiv-2609.27308-b31b1b.svg)](https://arxiv.org/abs/2609.27308)

- **SpatialClaw**: a VLM writes iterative Python cells in a persistent kernel, mixing geometry tools with intermediate visual feedback. [![arXiv](https://img.shields.io/badge/arXiv-2606.13673-b31b1b.svg)](https://arxiv.org/abs/2606.13673)

- **EmbodiedRSI**: picks informative trials, tests competing hypotheses, and revises executable code, skills, and memory around a frozen robot model. [![arXiv](https://img.shields.io/badge/arXiv-2610.10498-b31b1b.svg)](https://arxiv.org/abs/2610.10498)

- **Recova**: a coding agent discovers recovery skills in a digital twin, then calls task and recovery policies with progress checks on the robot. [![arXiv](https://img.shields.io/badge/arXiv-2610.01178-b31b1b.svg)](https://arxiv.org/abs/2610.01178)

- **PyRUA-Lean**: composes robot primitives and frozen VLA calls inside persistent Python cells, with local checks and retries. [![arXiv](https://img.shields.io/badge/arXiv-2610.01939-b31b1b.svg)](https://arxiv.org/abs/2610.01939)

- **DynaHarness**: grounds runtime commands, monitors execution, and revises reusable robot programs only after regression checks. [![arXiv](https://img.shields.io/badge/arXiv-2609.40306-b31b1b.svg)](https://arxiv.org/abs/2609.40306)

- **HarnessPAI**: runs a fixed task program over perception and action primitives, then edits that code between rollouts and keeps repair skills that pass. [![arXiv](https://img.shields.io/badge/arXiv-2609.29166-b31b1b.svg)](https://arxiv.org/abs/2609.29166)

- **Eureka**: an LLM writes reward code from the environment source and task text, then revises it from RL returns. [![arXiv](https://img.shields.io/badge/arXiv-2310.12931-b31b1b.svg)](https://arxiv.org/abs/2310.12931)

- **Code-as-Monitor**: generates visual monitoring code for spatio-temporal constraints, including checks that fire before a violation. [![arXiv](https://img.shields.io/badge/arXiv-2412.04455-b31b1b.svg)](https://arxiv.org/abs/2412.04455)

- **ReKep**: turns language and RGB-D into Python constraint functions over 3D keypoints, then solves end-effector actions from those functions. [![arXiv](https://img.shields.io/badge/arXiv-2409.01652-b31b1b.svg)](https://arxiv.org/abs/2409.01652)

- **COAP**, Embodied Turing Machines: improvement is a diff to stateful robot code. A shared library is written, tested, and debugged across rounds, then frozen and replayed. Reports 70.24% success on RoboDojo’s 42 bimanual tasks. [![arXiv](https://img.shields.io/badge/arXiv-2610.12369-b31b1b.svg)](https://arxiv.org/abs/2610.12369)

- **AgenticGenTAMP**: coding agents synthesize one program per task-and-motion-planning environment; the frozen program then runs on held-out instances. [![arXiv](https://img.shields.io/badge/arXiv-2609.30233-b31b1b.svg)](https://arxiv.org/abs/2609.30233) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/tomsilver/robocode)

- **PhysEvo**: keeps one model frozen and improves robot behavior from physical trials on RoboDojo and a real AgileX PiPER. [![arXiv](https://img.shields.io/badge/arXiv-2610.08995-b31b1b.svg)](https://arxiv.org/abs/2610.08995)

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

- **AdaHVLA**: separate agents analyze evidence, revise a code harness, and judge behavior, keeping a graph of hypotheses and observed effects. [![arXiv](https://img.shields.io/badge/arXiv-2609.29204-b31b1b.svg)](https://arxiv.org/abs/2609.29204)

- **RegenHarness**: proposes versioned edits to task templates, routing, and recovery rules, and only keeps a harness change after regression checks. [![arXiv](https://img.shields.io/badge/arXiv-2609.27612-b31b1b.svg)](https://arxiv.org/abs/2609.27612)

- **Zetta**: freezes the base policy and grows runtime critics, recovery playbooks, and tools from failure diagnosis and held-out promotion. [![arXiv](https://img.shields.io/badge/arXiv-2608.16590-b31b1b.svg)](https://arxiv.org/abs/2608.16590) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://air-embodied-brain.github.io/zetta/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/air-embodied-brain/Zetta-Embodiment)

- **SHAPER**: with model weights frozen, target-environment rollouts evolve reusable skills and the context-code harness around them. [![arXiv](https://img.shields.io/badge/arXiv-2608.11350-b31b1b.svg)](https://arxiv.org/abs/2608.11350)

- **VASO**: revises embodied skill contracts against temporal specifications and model-checking counterexamples. [![arXiv](https://img.shields.io/badge/arXiv-2606.05395-b31b1b.svg)](https://arxiv.org/abs/2606.05395) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://languagegroundedriskdetection.github.io/ProjectPage/vaso-webpage)

- **Code-as-Symbolic-Planner**: writes executable symbolic planning code from multimodal task context, then reuses those planning abstractions. [![arXiv](https://img.shields.io/badge/arXiv-2503.01700-b31b1b.svg)](https://arxiv.org/abs/2503.01700) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://yongchao98.github.io/Code-Symbol-Planner)

- **Agentic Skill Discovery**: a language model writes tasks and reward code, RL trains the skill, and a visual check decides whether the skill enters a persistent library. [![arXiv](https://img.shields.io/badge/arXiv-2405.15019-b31b1b.svg)](https://arxiv.org/abs/2405.15019) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://agentic-skill-discovery.github.io)

- **RAX**: a coding agent explores a robot task, records successful preconditions, actions, and effects, then compiles a standalone Python controller that runs without the agent. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robot-agent-exploration.com/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/robot-agent-exploration/rax)

- **ASENA**: connects a coding agent to robot sensing, supervised execution, and persistent experience. An optional learned navigation policy can be called as a tool. Model weights stay fixed while repeated tasks improve. [![arXiv](https://img.shields.io/badge/arXiv-2609.39207-b31b1b.svg)](https://arxiv.org/abs/2609.39207) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/asena/)

## Code as World

### Generation

- [⭐️] **SceneCode**: Executable World Programs for Editable Indoor Scenes with Articulated Objects. [![arXiv](https://img.shields.io/badge/arXiv-2605.19587-b31b1b.svg)](https://arxiv.org/abs/2605.19587) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://scene-code.github.io/)

- [⭐️] **VideoCoCo**: Code-as-CoT for Physically-Consistent Video Generation via an Agentic Dual-Engine System. [![arXiv](https://img.shields.io/badge/arXiv-2607.27380-b31b1b.svg)](https://arxiv.org/abs/2607.27380) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://github.com/micky-li-hd/VideoCoCo)

- **Code Video Model**: writes a Three.js program as an executable previs, renders a proxy video and a reference image, then conditions a pretrained video model on the proxy only in early sampling steps. Code edits change layout, motion, and camera before the final clip. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-video-model.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/code-video-model/CodeVideoModel)

- **EmbodiedGen V2**: an agent builds and edits assets, multi-room scenes, and task environments, then exports URDF, USD, or MJCF after physics checks. [![arXiv](https://img.shields.io/badge/arXiv-2607.07459-b31b1b.svg)](https://arxiv.org/abs/2607.07459) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HorizonRobotics/EmbodiedGen)

- **SimFoundry**: a modular video-to-simulation pipeline that reconstructs objects, compiles a physical scene, and proposes tasks in OmniGibson. [![arXiv](https://img.shields.io/badge/arXiv-2606.28276-b31b1b.svg)](https://arxiv.org/abs/2606.28276) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/NVlabs/SimFoundry)

- **Procedura**: agentic 3D assemblies whose named parts are joined by typed, machine-checkable constraints. [![arXiv](https://img.shields.io/badge/arXiv-2608.26238-b31b1b.svg)](https://arxiv.org/abs/2608.26238)

- **Articraft**: an agentic pipeline for scalable articulated 3D assets. [![arXiv](https://img.shields.io/badge/arXiv-2605.15187-b31b1b.svg)](https://arxiv.org/abs/2605.15187)

- **HARMONY**: hierarchical agentic reasoning that turns one image into a scene program. [![arXiv](https://img.shields.io/badge/arXiv-2609.26793-b31b1b.svg)](https://arxiv.org/abs/2609.26793) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://cwchenwang.github.io/harmony/)

- **AssemblyWorld**: general-purpose agents solve 3D assembly from rendered views and part records, not mesh vertices. [![arXiv](https://img.shields.io/badge/arXiv-2609.40353-b31b1b.svg)](https://arxiv.org/abs/2609.40353) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/AssemblyWorld/assembly-world-bench)

- **USDCraft**: an LLM writes and revises a program that turns a mesh and a reference image into a simulation-ready articulated USD asset. [![arXiv](https://img.shields.io/badge/arXiv-2610.11322-b31b1b.svg)](https://arxiv.org/abs/2610.11322)

- **AffordCraft**: from one photo and a task, builds task-ready simulation assets. [![arXiv](https://img.shields.io/badge/arXiv-2610.06643-b31b1b.svg)](https://arxiv.org/abs/2610.06643)

- **Agentic RSR**: real-to-sim-to-real through scene reconstruction and execution-grounded robot policies. [![arXiv](https://img.shields.io/badge/arXiv-2610.10479-b31b1b.svg)](https://arxiv.org/abs/2610.10479)

- **Artisan**: a multi-agent pipeline for physically grounded articulated 3D assets. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://physicalvision.github.io/artisan/)

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

- **AstraLOD3**: multi-view evidence to an editable building reconstruction. [![arXiv](https://img.shields.io/badge/arXiv-2609.28061-b31b1b.svg)](https://arxiv.org/abs/2609.28061)

- **RoboSimStudio**: humans and coding agents refine a Newton simulation's scene and physical parameters against observed robot behavior. [![arXiv](https://img.shields.io/badge/arXiv-2610.18835-b31b1b.svg)](https://arxiv.org/abs/2610.18835) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robosimstudio.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/robosimstudio/robosimstudio)

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

- **Baba in Wonderland**: discovers dynamics online and writes them down as an executable world model. [![arXiv](https://img.shields.io/badge/arXiv-2605.16725-b31b1b.svg)](https://arxiv.org/abs/2605.16725)

- **Tycho**: builds programmatic world models by active abstraction for ARC-AGI-3. [![arXiv](https://img.shields.io/badge/arXiv-2607.28287-b31b1b.svg)](https://arxiv.org/abs/2607.28287) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/NIMI-research/Tycho)

- **WALL-E**: learns rules that align a world model, then uses those rules for LLM-agent planning. [![arXiv](https://img.shields.io/badge/arXiv-2410.07484-b31b1b.svg)](https://arxiv.org/abs/2410.07484)

- **WALL-E 2.0**: learns neurosymbolic rules so a world-model agent can adapt when the environment changes. [![arXiv](https://img.shields.io/badge/arXiv-2504.15785-b31b1b.svg)](https://arxiv.org/abs/2504.15785) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/elated-sawyer/WALL-E)

- **VisualPredicator**: learns neuro-symbolic predicates as an abstract world model for robot planning. [![arXiv](https://img.shields.io/badge/arXiv-2410.23156-b31b1b.svg)](https://arxiv.org/abs/2410.23156)

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

### Policy programs

The agent writes, runs, or revises a robot control or learning program.

- [⭐️] **RLE-Bench**: A Qualifying Exam for Coding Agents as Robot Learning Engineers. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rle-bench.github.io/)

- **CodeActionBench**: 25 simulated dual-arm tasks where the agent writes, runs, and revises code against a robot API with RGB and calibrated geometry, without depth or privileged state. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/lyhkk/CodeActionBench)

- **LIBERO-Agent**: general-purpose agents choose observations and issue native robot commands; the split is perception, short-horizon execution, and long-horizon manipulation. [![arXiv](https://img.shields.io/badge/arXiv-2609.39507-b31b1b.svg)](https://arxiv.org/abs/2609.39507) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/dzj441/Libero-Agent)

- **RoboQuest**: general-purpose agents issue robot commands through tool calls on ten simulated kitchen mobile-manipulation tasks, searching, inspecting, or testing to find hidden information before pressing SUBMIT. Astra leads five frontier agents (23.2% success). [![arXiv](https://img.shields.io/badge/arXiv-2610.10388-b31b1b.svg)](https://arxiv.org/abs/2610.10388) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://declare-lab.github.io/RoboQuest/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/declare-lab/RoboQuest)

- **AA-Robotics v0.1**: eight tabletop tasks on a real Hiwonder NexArm. A coding agent in an isolated container drives the arm through an HTTP API and four cameras, and a person scores the end state. GPT-6 Astra scores 69.4, first of five. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://artificialanalysis.ai/articles/aa-robotics)

### World programs

The agent writes an executable scene, CAD model, or physics program. A renderer or simulator then runs it.

- [⭐️] **PhysCodeGym**: 156 tasks where a coding agent reconstructs a reference video as an executable Blender program. Scoring covers the rendered video and the scene's physical behavior, including counterfactual interventions. With Codex, GPT-6 Astra leads overall at 0.663. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/ShaoShuai0605/PhysCodeGym) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://huggingface.co/datasets/ShaoShuai0605/PhysCodeGym)

- **4DCodeBench**: agents write executable code that reconstructs dynamic scenes from 200 videos. Astra Max leads 18 agents (overall 0.79) and leads dynamics by 31%. [![arXiv](https://img.shields.io/badge/arXiv-2610.03715-b31b1b.svg)](https://arxiv.org/abs/2610.03715) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://4dcodebench.com/)

- **Video2World**: 222 tasks from 189 embodied videos; coding agents rebuild interactive simulated worlds. Astra ranks 2nd of 9 (V2WScore 43.55, 10.7% success) with the most accurate geometry, still far below the human-assisted reference. [![arXiv](https://img.shields.io/badge/arXiv-2610.04432-b31b1b.svg)](https://arxiv.org/abs/2610.04432) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://aetherlabsai.github.io/Video2World/)

- **BVB**: the agent rebuilds each video as a Blender program, then answers spatiotemporal questions on that program. Astra high scores overall 70.07, rank 1 of 51 on the paper's frontier set. On the live leaderboard of 63 configurations (2026-10-14), Astra xhigh is 73.82, rank 1. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://frank-zy-dou.github.io/awesome-ai-3d-modeling-robotics/#3d-cad-and-spatial)

- **WorldCoder-Bench**: Evaluating Executable Three.js Worlds. [![arXiv](https://img.shields.io/badge/arXiv-2606.01869-b31b1b.svg)](https://arxiv.org/abs/2606.01869)

- **CodeVideoBench**: 22 editable Three.js cases for controllable video, covering gaming, scene editing, physics, and 3D/4D reconstruction. With MiniMax-H3, Code Video Model reports overall scores of 85.2 / 82.1 / 85.8 under QwenVL-3.8-27B, GPT-5.6, and GPT-6, versus 74.3 / 73.1 / 80.6 for VACE. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://huggingface.co/datasets/code-video-model/CodeVideoBench) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/code-video-model/CodeVideoModel)

- **3JSBench**: 100 short text-to-Three.js tasks, with the generation requests and inspectable geometry. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/GeneralContext/3jsbench)

- **BenchCAD**: multi-view renders to CadQuery, scored by mean voxel IoU. With tools, Astra is reported at 95.9%. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://frank-zy-dou.github.io/awesome-ai-3d-modeling-robotics/#3d-cad-and-spatial)

- **Moonlake 3D Agent**: sim-ready asset benchmark across 22 metrics and Isaac Sim interaction tests; reported rank score 65.2 versus Astra 47.0. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://moonlakeai.com/blog/evaluating-3d-agent)

- **BuildingBench**: a coding agent turns four photographs of a public building into one textured glTF. On the 2026-10-14 leaderboard, Codex CLI at ultra effort scores 0.843 ± 0.014, third of 32. Claude Opus 5.5 (max) leads at 0.868. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://enactra.ai/buildingbench/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/enactra-ai/building-bench)

- **threejseval**: 16 fixed Three.js scene prompts. People vote between unlabeled scenes. Astra at medium effort is Elo 1884 ± 105, rank 4 of 36. Claude Opus 5.5 High leads at 2071. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://threejseval.com/ranking)

- **MineBench**: the model writes JavaScript against a small voxel API (`block`, `box`, `line`), then people vote. Astra Pro is 2259 ± 16.7, rank 2 of 74. Gemini 4 Argon leads at 2269, and the two intervals overlap. The author does not call it a benchmark. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://minebench.ai/leaderboard) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Ammaar-Alam/minebench)

### Robot evaluation infrastructure

These evaluate robot policies broadly, including learned policies and program or command interfaces. They are policy-evaluation infrastructure, not code-generation benchmarks.

- **XPolicyLab**: A Unified Standard and Open Ecosystem for Robot Policy Evaluation and Deployment. [![arXiv](https://img.shields.io/badge/arXiv-2608.09892-b31b1b.svg)](https://arxiv.org/abs/2608.09892) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/XPolicyLab/XPolicyLab)

- **RoboDojo**: A Unified Sim-and-Real Benchmark for Comprehensive Evaluation of Generalist Robot Manipulation Policies. [![arXiv](https://img.shields.io/badge/arXiv-2607.04434-b31b1b.svg)](https://arxiv.org/abs/2607.04434) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/robodojo-benchmark/RoboDojo)

- **HumanCLAW**: Can Vision-Language Models Act Through a Body? Tests VLM decisions through a harness that turns them into humanoid motion-generator calls. [![arXiv](https://img.shields.io/badge/arXiv-2607.27180-b31b1b.svg)](https://arxiv.org/abs/2607.27180)

- **Robo Use Leaderboard**: aggregates published solve rates for agent harnesses and VLA policies, with 95% Wilson intervals. Each task counts once per model and harness. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robouse.ai/hub/leaderboard/)

## Surveys and Lessons

- **World Models for Embodied Intelligence: From Plausible to Controllable to Actionable**: surveys embodied world models by predictive plausibility, intervention controllability, and downstream decision utility. Useful context for executable and programmable world models. It does not require code as the intermediate representation. [![arXiv](https://img.shields.io/badge/arXiv-2609.16697-b31b1b.svg)](https://arxiv.org/abs/2609.16697)

- **Robot-Use Agents** (Phillip Isola): perspective on general-purpose agents that use robots through sensor and actuator APIs. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://web.mit.edu/phillipi/www/writing/robot-use-agents.html)

- **Goosebumps** (Ken Goldberg): argues that coding agents can write, test, and revise modular robot programs offline, between model-based engineering and robot learning. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Ken_Goldberg/status/2100986412762087909)

- **Survey on Multimodal Embodied Agents**: unifies computer-use and robot-use as perceive, anticipate, plan, act, and verify. Broader than code-as-IR methods. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://showlab.github.io/Awesome-Multimodal-Embodied-Agent/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/showlab/Awesome-Multimodal-Embodied-Agent)

- **Weights or Skills?** A Survey of Robot-Learning Techniques: from Action-Predicting Weights to Robots that Write their Own Skills: frames the split between frozen action-predicting weights and executable robot skills. [![arXiv](https://img.shields.io/badge/arXiv-2608.01851-b31b1b.svg)](https://arxiv.org/abs/2608.01851)

- **Code as Agent Harness**: surveys executable, verifiable, stateful harness design for agents that write and run code. [![arXiv](https://img.shields.io/badge/arXiv-2605.18747-b31b1b.svg)](https://arxiv.org/abs/2605.18747)

- **What Stops Recursive Self-Improvement in Robotics?** Lessons from 123 Rounds of Agentic Skill Discovery: reports an agent that wrote, installed, and tested skills, but never solved the target fridge task; relational perception, early-skill bottlenecks, and evaluator behavior were the main failure points. [![arXiv](https://img.shields.io/badge/arXiv-2609.31760-b31b1b.svg)](https://arxiv.org/abs/2609.31760)

- **Harness Engineering for Physical AI**: argues that robot middleware should be the harness: it projects, isolates, and transfers control, compute, and communication around a model. [![arXiv](https://img.shields.io/badge/arXiv-2606.09416-b31b1b.svg)](https://arxiv.org/abs/2606.09416)

- **Agentic World Modeling**: a survey of agentic world models, their capabilities, and the laws proposed for them. It is broader than code-as-IR methods. [![arXiv](https://img.shields.io/badge/arXiv-2604.22748-b31b1b.svg)](https://arxiv.org/abs/2604.22748)

- **Towards Agentic Robots: Model, Data, Environment, and Harness**: organizes agentic-robot research into those four domains. Broader than code-as-IR methods; harness is one of the four. [![arXiv](https://img.shields.io/badge/arXiv-2610.20442-b31b1b.svg)](https://arxiv.org/abs/2610.20442) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/chonghanqin/Awesome-Agentic-Robots)

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

- **G1 stage burpee**: a scripted Unitree G1 routine in public code: carry a stand on stage, hold a pose, do push-ups, then jump. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Siriuslala/g1-robot-burpee)

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

- **Agent as Policy on a real YAM**: GPT-6 Astra in Codex writes and runs programs on a real arm, then revises them from camera feedback. Tasks include assembly from a human video, block building from a goal image, dice reorientation, throwing, and bimanual towel folding. See also [AGP](#code-as-policy). [![Website](https://img.shields.io/badge/Website-Link-blue)](https://agent-as-policy-2026.github.io/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/agent-as-policy-2026/agent-as-policy)

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

- **AHa-3D**: Astra plus reconstruction tools turn indoor video into editable Blender rooms, recover human motion with contact refinement, and export a browser scene. [![Website](https://img.shields.io/badge/Website-Link-blue)](https://kevinxu02.github.io/real2sim-indoor-site/) [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/KevinXu02/aha-3d)

- **Real2Gym**: an agent rebuilds a Blender / MuJoCo gym from video, then runs generated Python stages with visual feedback before skill transfer. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/real2gym/Real2Gym)

- **Lab Kitchen Reconstruction** ([Frank ZY Dou](https://www.rednote.com/user/profile/5e3431cf0000000001002919)): rebuilds a lab kitchen with articulated cabinets from a 20-second monocular RGB video. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa4d64c000000000b037809?xsec_token=ABur_B60E14GxVQp2ei3USGkgJntlivJm_02tlDaUFWmg=&xsec_source=pc_search&source=web_profile_page)

- **Rope-driven Dexterous Hand Reconstruction** ([Dmytro Hrybov](https://x.com/dimentary)): recreates 1X’s tendon-driven hand demo in MuJoCo, with simplified tendon mechanics. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/dimentary/status/2097857980150763900)

- **Tendon-driven Dexterous Hand Motion Reconstruction** ([Jake Fitzgerald](https://x.com/earthtojake)): designs a tendon-driven hand and reconstructs cable-actuated finger motion in simulation. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/earthtojake/status/2097789988670709821)

- **Dexterous Hand-object Data Rollout** ([Lingxiao](https://x.com/Lingxiao234)): two videos drive real-to-sim reconstruction and physical retargeting onto Wuji hands, without explicit states or actions. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Lingxiao234/status/2097717020540481630)

- **Video in → Physics out** ([xiao hu](https://x.com/huxiao93612565)): writes hand tracking, IK retargeting, and grasp-refinement code for a 44-DoF hand. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/huxiao93612565/status/2097815230105399402)

- **Multi-view Real-to-sim Reconstruction** ([Lingxiao](https://x.com/Lingxiao234)): builds a replayable MuJoCo / Blender simulator from multi-view RGB, robot actions, calibration, assets, and system identification. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Lingxiao234/status/2096992059731443923)

- **Robotica Real2Sim**: a table photo becomes a MuJoCo scene with a Franka Panda. Codex records 50 inverse-kinematics episodes, then a plan is replayed under physics variations. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/inematds/robotica-real2sim)

### RL training stacks

- **Dexterous Astra** ([Jianglong Ye](https://github.com/jianglongye)): released artifacts from Astra experiments, not a harness given to the agent. Sharpa Wave pen spinning in Isaac Lab (a zero-shot keyframe planner, then PPO for three turns and a hold) and Wuji-hand Rubik's cube in MuJoCo (a zero-shot two-hand script, then a learned one-hand policy that solves `U F L`). [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/jianglongye/dexterous-astra)

- **Office Real2Sim2Real Cart Push** ([watchtower](https://www.rednote.com/user/profile/5e38ca4e00000000010034fa)): rebuilds an office, estimates contact supervision, trains an RL cart-push policy with SONIC for whole-body motion, then deploys it on the real humanoid. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6ab34cfd0000000018005cab?xsec_token=CBoKOnuhKTqoyv12enaYThxB4L_a-12BnOafHa5vF3aRw=&xsec_source=app_share)

- **Sharpa Hand Pen-spinning RL** ([Wentao Zhu](https://x.com/walterzhu8) / Chengyang Li): autonomous ~1.5-day run that builds the pen mesh, an Isaac Lab Sharpa-hand task, a PPO policy, and a visualization video. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/walterzhu8/status/2100212420840989112)

- **RL-trained Duck Robot** ([拂晓时分_茉莉飘香](https://www.rednote.com/user/profile/5ffbc96d00000000010060ae)): one image and one description become an RL-trained duck locomotion demo. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa347e2000000000b036667?xsec_token=AB1z4k50CvQ0PFZpqtQXWYlVMONqE2yr3ER8jk-hVWI74=&xsec_source=pc_search&source=web_profile_page)

- **Quadruped Locomotion from RL** ([Akira Sasaki](https://x.com/gclue_akira)): co-designs a robot dog, iterates 25 loops in five days, and trains nine simulated motions with RL. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/gclue_akira/status/2098300921658868185)

- **Dexterous In-hand Manipulation RL** ([十一](https://www.rednote.com/user/profile/610bc8f100000000200284e2)): trains in-hand walnut manipulation; the reported run did not enable self-collision. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa3e146000000002b0123dc?xsec_token=AB5n_GSvnshtGoIJqykTNpkWlIS-zHnIYe2n5pAiGLSgw=&xsec_source=pc_like)

- **Office Scan → Newton / G1 Gym** ([Jiarui Xu](https://x.com/Jiarui_X)): rebuilds an office scan in Blender, exports USD, and makes a G1 walking scene in Newton. [![X](https://img.shields.io/badge/X-Post-black)](https://x.com/Jiarui_X/status/2098439950991806804)

- **Isaac Sim Environment, PPO Training, and Tuning** ([十一](https://www.rednote.com/user/profile/610bc8f100000000200284e2)): builds an Isaac Sim RL environment, configures PPO, and iterates the run in one workflow. [![Rednote](https://img.shields.io/badge/Rednote-Post-ff2442)](https://www.rednote.com/discovery/item/6aa29087000000002600bb2e?xsec_token=ABupW63bXfa1dAqIk6vaYviNev-xOXuTmePvxk8Su9NK4=&xsec_source=pc_collect)

### Scene programs

Astra writes a scene, CAD model, or playable world as code, then Blender, OpenSCAD, Three.js, or a game engine runs it. The full set is 338 examples in [Awesome Astra 3D](https://github.com/carpentry-liu/awesome-astra-3d) ([gallery](https://carpentry-liu.github.io/awesome-astra-3d/)). Entries below are source-backed starting points, grouped by the program that gets executed. Video-only renders stay in that atlas.

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

- **Stanford in Blender**: five editable campus scenes, with procedural scripts and standalone `.blend` files. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/minsik-ai/stanford-in-blender)

- **Gulou campus**: a walkable Nanjing University campus in TypeScript, Three.js, and Rapier, with cycling, gliding, and weather. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/wang-jiahao/gulou)

- **Gargantua**: a shader accretion disk and bent light, with an orbit camera. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/pedroaugustonyo/gargantua)

- **BHBench**: Astra’s native black-hole renderer, with the generated C++ / GLSL, ray integration, and a curvature grid. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/SSHdotCodes/bhbench/tree/main/submissions/gpt-6-astra-xhigh)

- **One Equation, Three Worlds**: one Lorenz curve kept as an editable copper sculpture, procedural ink, and moving light. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/davisbuilds/oneshots/tree/main/runs/three-worlds-chatgpt)

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

- **Palm Bay**: a preserved one-shot low-poly driving sandbox, with the original prompt and recovered JavaScript. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/nitzangames/PalmBayOneShot)

- **Corner Mart**: an editable convenience store with shopping lists and a three-minute shift, plus the `.blend`, GLB, and generation scripts. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/ericyanpek/game-sample-corner-mart)

- **Hallowmere**: a torchlit village RPG with procedural characters, combat, and co-op. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/miguelsolorio/hallowmere)

- **Morrow**: an interactive moonlit plush ghost in one HTML file, with grab, poke, brush, and color controls. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Kayou-31/moonlit-plush-gallery/blob/main/morrow.html)

- **Moss & Moon**: a procedural fox and woodland ecosystem in Three.js, with a skeleton, foot IK, and need-driven pathfinding. The Astra submission is kept in its own folder. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/hdnng/ai-3d-animal-astra-vs-argon-vs-opus/tree/main/astra)

## Related Resources

- **Awesome Physical AI**: broader curated reading list for robot-policy VLMs, coding agents, policy harnesses, and RoboDojo-style scorecards. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/HexaFuture/Awesome-Physical-AI)

- **Awesome Robot Use Agent**: catalog of robot-use agents, harnesses, ROS tool stacks, and social demos. Entries here keep only the ones that use a program as the intermediate representation. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/kairunwen/Awesome-Robot-Use-Agent) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://kairunwen.github.io/Awesome-Robot-Use-Agent/)

- **Awesome AI for 3D Modeling & Robotics**: source-linked cases for AI 3D modeling, CAD, and robot control, plus benchmark numbers read from the original reports. Social clips stay in that catalog. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/Frank-ZY-Dou/awesome-ai-3d-modeling-robotics) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://frank-zy-dou.github.io/awesome-ai-3d-modeling-robotics/)

- **Awesome Multimodal Embodied Agent**: computer-use and robot-use agents, from surveys through benchmarks. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/showlab/Awesome-Multimodal-Embodied-Agent)

- **Awesome Embodied RSI**: embodied recursive self-improvement, grouped by what gets updated: model, memory, skills, or harness. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/cocacola-lab/awesome-embodied-rsi)

- **Awesome Humanoid Robot Learning**: humanoid locomotion, manipulation, teleoperation, and sim-to-real. Most entries are learned policies, not programs. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/YanjieZe/awesome-humanoid-robot-learning)

- **Awesome Embodied Robotics and Agent**: embodied robotics methods and benchmarks. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/zchoi/Awesome-Embodied-Robotics-and-Agent)

- **Awesome Agentic Robotics**: agent, harness, and VLA stacks for robot control. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/w-xb/awesome-agentic-robotics)

- **Awesome Agentic World Modeling**: world models sorted into predictor, simulator, and evolver. [![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/matrix-agent/awesome-agentic-world-modeling)
