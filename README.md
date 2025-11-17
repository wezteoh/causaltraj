# CausalTraj
**Official Implementation of "Coherent Multi-Agent Trajectory Forecasting in Team Sports with CausalTraj" (AI4TS workshop @ AAAI 2026)**

CausalTraj is a temporally causal, likelihood-based model for multi-agent trajectory generation.

<img src="https://github.com/causaltraj/causal-traj/blob/main/assets/sample_0.gif" width="400"><img src="https://github.com/causaltraj/causal-traj/blob/main/assets/sample_1.gif" width="400">


Environment: Python 3.12, CUDA 12.8 \
Hardware used: Single A100 GPU

The datasets used in this work are kindly open sourced by https://github.com/MediaBrain-SJTU/LED and https://github.com/colorfulfuture/UniTraj-pytorch.

Command to train model on NBA dataset:
```
HYDRA_FULL_ERROR=1 python train.py --config-path configs/nba --config-name cpointnet_default.yaml
```

Command to evaluate model on NBA dataset:
```
python eval.py --base-config-path configs/nba/cpointnet_default.yaml --test-config-path configs/nba/test.yaml --ckpt [CHECKPOINT_PATH] --test-size 12500
```

Notes:
1. For basketball-u and football-u datasets, please rearrange the entity order in each frame to move the position of ball to the last index instead of first, before training and testing.