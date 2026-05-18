# CROSS-Pose
## Framework
![framework](Fig1.png)

## 🔧 Installation

Create the conda environment:

```bash
conda env create -f CROSSPose_env.yaml
```

## Download Checkpoints  
We provide checkpoints for the trained models on REAL275 and CAMERA. You can download them from [huggingface](https://huggingface.co/moshu413/CROSS-Pose/tree/main) .


## 📦 Dataset Preparation

### Required datasets:

* **NOCS dataset**
  Follow the instructions in the [[LaPose](https://github.com/lolrudy/LaPose)] repository.

* **IVFC map (training only)**
  Download from: [[IVFC](https://drive.google.com/file/d/1kF8ck7EM9mnz6jyySncVUxzXgRxHH9e-/view)]

* **Wild6D dataset**
  Download from: [[Wild6D](https://github.com/OasisYang/Wild6D)]

### Directory structure:

```bash
data/
├── NOCS/
├── IVFC/
├── Wild6D/
```
---

## 🚀 Training

### Train on CAMERA + Real dataset

```bash
python engine/train.py \
--model_save "./output/model_save"
```

### Train on CAMERA dataset only

```bash
python engine/train.py \
--model_save "./output/model_save_C" \
--dataset CAMERA
```

---

## 📊 Evaluation

### Evaluate on Real dataset

```bash
python evaluation/evaluate.py \
--resume_model "./path/to/pose_net/xxx.pth" \
--dataset Real \
--use_scale_net \
--sn_path "./path/to/scale_net/xxx.pth"
```

---

### Evaluate on Wild6D dataset

```bash
python evaluation/evaluate.py \
--resume_model "./path/to/pose_net/xxx.pth" \
--dataset wild6d \
--use_scale_net \
--sn_path "./path/to/scale_net/xxx.pth"
```

---

### Evaluate on CAMERA dataset

```bash
python evaluation/evaluate.py \
--resume_model "./path/to/pose_net_C/xxx.pth" \
--dataset CAMERA \
--use_scale_net \
--sn_path "./path/to/scale_net_C/xxx.pth"
```

---


