# megasam-batch

*Unofficial batch processing tool for MegaSaM*

For more details about MegaSaM, visit the [MegaSaM Official GitHub Repository](https://github.com/mega-sam/mega-sam).

- Inputs: A csv file listing video paths, total frame counts, and fps values.
- Outputs: Camera parameters and depth maps saved in a structured output directory.

## 🛠️ Installation Guide

1. Clone this repository:

   ```bash
   git clone https://github.com/FelixYuan-YF/megasam-batch.git  
   cd megasam-batch  
   ```
2. Install dependencies:

   ```bash
   conda create -n megasam-batch python=3.10 -y
   conda activate megasam-batch
   pip install -r requirements.txt  
   ```
3. Download checkpoint files:

   ```bash
   bash download_checkpoints.sh
   ```

## 🚀 Quick Start

Process a batch of videos using the provided script:

```bash
bash run.sh
```

## 📷 Visualization

Install the required visualization dependencies:

```bash
pip install plotly
pip install -e viser
```

You can visualize the `poses.npy` in the `reconstruction` folder of each annotated clip using the [`visualize_pose.py`](viser/visualize_pose.py) script.

You can visualize the final annotation result(`sgd_cvd_hr.npz`) using the [`visualize_megasam.py`](viser/visualize_megasam.py) script.

Note that if you uncomment the `--only_depth` in `run.sh`, you need to use the script [`pack_clip_assets.py`](utils/pack_clip_assets.py) to unify the depth, RGB frames, intrinsics, extrinsics, etc. of that clip into a single npz file first. And then you can use the visualization script to visualize it.
