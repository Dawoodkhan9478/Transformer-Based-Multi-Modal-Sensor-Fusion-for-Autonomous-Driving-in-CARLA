# TransFuser-CARLA

Transformer-Based Multi-Modal Sensor Fusion for Autonomous Driving
Introduction

This repository contains an implementation of a transformer-based sensor fusion framework for end-to-end autonomous driving using the CARLA simulator.
The model is trained using imitation learning, where expert driving behavior is learned from multi-modal sensor data.

The system fuses information from RGB cameras and LiDAR using a transformer-based architecture to generate vehicle control commands.
This codebase is designed for research and experimentation in autonomous driving, sensor fusion, and learning-based control within realistic simulated environments.


---

## Workflow Overview

### 1. Data Generation
- A **rule-based autopilot agent** drives autonomously in CARLA.
- Sensor data (**RGB cameras, LiDAR**) and vehicle states are recorded.
- The collected data serves as expert demonstrations for imitation learning.

### 2. Training
- The **TransFuser model** is trained using imitation learning.
- A transformer-based architecture fuses multi-modal sensor features.
- The model learns to predict vehicle control commands directly from sensor inputs.

### 3. Evaluation
- The trained model is deployed as an autonomous agent in CARLA.
- Performance is evaluated on predefined routes and driving scenarios.
- Metrics such as route completion, infractions, and driving stability are analyzed.

---

## Key Features

- Transformer-based **multi-modal sensor fusion**
- End-to-end **imitation learning framework**
- Fully integrated with the **CARLA simulator**
- Supports **single-GPU and multi-GPU training**
- Modular and extensible codebase for autonomous driving research


## Code Structure

```text
transfuser/
├── team_code_transfuser/
│   ├── train.py
│   │   Main training script for imitation learning.
│   │   Handles data loading, model training, logging, and checkpointing.
│   │
│   ├── submission_agent.py
│   │   Inference agent used for evaluation in CARLA.
│   │   Loads trained models and outputs vehicle control commands.
│   │
│   ├── model.py
│   │   Defines the TransFuser neural network architecture.
│   │   Includes transformer-based fusion of camera and LiDAR features.
│   │
│   ├── config.py
│   │   Configuration file for model parameters,
│   │   training settings, and sensor specifications.
│
├── team_code_autopilot/
│   └── autopilot.py
│       Rule-based expert agent used to generate
│       training data for imitation learning.
│
├── tools/
│   ├── dataset/
│   │   Scripts and utilities for dataset generation
│   │   and preprocessing.
│   │
│   └── result_parser.py
│       Utility for parsing and summarizing
│       evaluation results.
│
├── leaderboard/
│   Scripts and configuration files for running
│   evaluations using CARLA benchmark routes.
│
├── figures/
│   Visualization and demo images.
│
├── setup_carla.sh
│   Script for setting up the CARLA environment.
│
└── environment.yml
    Conda environment specification.


---
