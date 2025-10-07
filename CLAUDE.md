# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a learning repository for reinforcement learning following HuggingFace's Deep RL Course. The project contains tutorial implementations and experiments using Gymnasium environments and Stable-Baselines3.

## Repository Structure

- `tutorials/` - Tutorial implementations as Jupyter notebooks following HuggingFace Deep RL Course units
- `experiments/` - Custom experiments and modifications
- `notebooks/` - Jupyter notebooks for exploration
- `utils/` - Helper functions and utilities

## Environment Setup

This project uses a dedicated conda environment named `huggingface_rl`.

### Activate the environment

```bash
conda activate huggingface_rl
```

### Installing Dependencies

Notebooks install dependencies inline. The primary tutorial (Unit 1) installs from:
```bash
conda activate huggingface_rl
pip install -r https://raw.githubusercontent.com/huggingface/deep-rl-class/main/notebooks/unit1/requirements-unit1.txt
```

Common packages used: `gymnasium`, `stable-baselines3`, `pyvirtualdisplay`, `swig`

### System Dependencies for RL Environments

For Box2D environments (like LunarLander), system packages are required:
```bash
sudo apt install swig cmake python3-opengl ffmpeg xvfb
```

## Development Commands

### Running Jupyter Notebooks

```bash
conda activate huggingface_rl
jupyter notebook tutorials/
```

### Running Python Scripts

```bash
conda activate huggingface_rl
python <script_name>.py
```

## Key Implementation Details

### Tutorial Notebooks

- Notebooks follow a structure: Setup → Import → Create Environment → Define Model → Train → Evaluate → Visualize
- Use virtual displays (`pyvirtualdisplay`) for rendering in headless environments
- Models are saved locally (e.g., `ppo_lunarlander`)
- TensorBoard logs are typically stored in `./[algorithm]_[environment]_tensorboard/`
- Videos are recorded to `videos/` directory

### RL Framework

- **Environment**: Gymnasium (formerly OpenAI Gym)
- **Training**: Stable-Baselines3 (PPO, DQN, A2C, etc.)
- **Evaluation**: `stable_baselines3.common.evaluation.evaluate_policy`
- **Visualization**: VecVideoRecorder for generating MP4 videos of trained agents

## Course Structure

The repository follows HuggingFace Deep RL Course units:
1. Introduction to Deep RL
2. Q-Learning
3. Deep Q-Learning (DQN)
4. Policy Gradient Methods
5. Actor-Critic Methods
6. Advantage Actor-Critic (A2C/A3C)
7. Proximal Policy Optimization (PPO)
8. Multi-Agent RL

## Resources

- [HuggingFace Deep RL Course](https://huggingface.co/deep-rl-course/unit0/introduction)
- [HuggingFace RL Library](https://github.com/huggingface/deep-rl-class)
