# CausalTraj
**Official Implementation of "Coherent Multi-Agent Trajectory Forecasting in Team Sports with CausalTraj" (accepted to the AI4TS workshop @ AAAI 2026)**

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

Trained models on the NBA SportVU dataset can be downloaded from https://huggingface.co/wezteoh/causaltraj.

Notes:
1. For Basketball-U and Football-U datasets, please rearrange the entity order in each frame to move the position of the ball to the last index instead of the first.

Bibtex:
```
@misc{teoh2025coherentmultiagenttrajectoryforecasting,
      title={Coherent Multi-Agent Trajectory Forecasting in Team Sports with CausalTraj}, 
      author={Wei Zhen Teoh},
      year={2025},
      eprint={2511.18248},
      archivePrefix={arXiv},
      primaryClass={cs.LG},
      url={https://arxiv.org/abs/2511.18248}, 
}
```