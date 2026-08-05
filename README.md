# 🚀 Fine-tuning Large Language Models with Direct Preference Optimization (DPO)

A complete educational project demonstrating how to fine-tune Large Language Models (LLMs) using **Direct Preference Optimization (DPO)** with the Hugging Face ecosystem.

This repository covers the complete DPO pipeline, including dataset preparation, model loading, preference-based training, evaluation, and inference.

---

## 📌 Project Overview

Direct Preference Optimization (DPO) is a post-training alignment algorithm that enables language models to learn from human preference data **without training a separate reward model**, making it much simpler than traditional RLHF pipelines. :contentReference[oaicite:0]{index=0}

This project demonstrates how to:

- Load a pretrained language model
- Prepare a preference dataset
- Configure DPO training
- Fine-tune using Hugging Face TRL
- Save the trained model
- Run inference with the aligned model

---

## 🧠 What is DPO?

Unlike RLHF, DPO directly optimizes the model using pairs of:

- ✅ Chosen response
- ❌ Rejected response

Instead of training:

```
Reward Model
        ↓
Reinforcement Learning
        ↓
LLM
```

DPO performs optimization directly on preference pairs:

```
Preference Dataset
        ↓
DPO Trainer
        ↓
Aligned LLM
```

This significantly reduces implementation complexity while achieving competitive alignment performance. :contentReference[oaicite:1]{index=1}

---

# 📂 Project Structure

```text
finetune_with_dpo_part2/
│
├── data/
│   └── preference_dataset/
│
├── notebooks/
│   └── finetune_with_dpo_phi.ipynb
│
├── outputs/
│
└── README.md
```

---

# ⚙️ Technologies

- Python
- PyTorch
- Transformers
- Hugging Face
- TRL
- PEFT
- Datasets
- Accelerate

---

# 📦 Installation

Clone the repository

```bash
git clone https://github.com/c-ehsan/finetune_with_dpo.git

cd finetune_with_dpo
```

Create a virtual environment

```bash
python -m venv transformer_env
```

Activate it

Windows

```bash
transformer_env\Scripts\activate
```

Linux / macOS

```bash
source transformer_env/bin/activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# 📊 Training Pipeline

The project follows the standard DPO workflow:

```
Load Dataset
      │
      ▼
Tokenization
      │
      ▼
Load Base Model
      │
      ▼
Configure DPO Trainer
      │
      ▼
Fine-tuning
      │
      ▼
Save Model
      │
      ▼
Inference
```

---

# 📁 Dataset Format

The dataset should contain preference pairs.

Example:

| prompt | chosen | rejected |
|---------|---------|----------|
| Explain AI | AI is... | AI means... |

Each training sample includes:

- Prompt
- Preferred response
- Rejected response

---

# ▶️ Running Training

Example:

```bash
python train.py
```

or open the notebook:

```
notebooks/dpo_training.ipynb
```

---

# 📈 Output

After training, the fine-tuned model will be saved inside:

```
outputs/
```

You can later load it for inference or additional fine-tuning.

---

# 📚 Learning Objectives

This project is intended for learners who want to understand:

- Preference Learning
- RLHF concepts
- Direct Preference Optimization
- Hugging Face TRL
- LLM Alignment
- Post-training techniques

---

# 📝 References

- Direct Preference Optimization Paper
- Hugging Face TRL Documentation
- Hugging Face Transformers Documentation
- Hugging Face Datasets Documentation :contentReference[oaicite:2]{index=2}

---

# ⭐ Future Improvements

- [ ] LoRA + DPO
- [ ] QLoRA + DPO
- [ ] Evaluation Metrics
- [ ] Multiple Preference Datasets
- [ ] Experiment Tracking
- [ ] Model Comparison
- [ ] WandB Integration

---

# 📄 License

This project is released under the MIT License.

---

## 👨‍💻 Author

**Ehsan Behboodian**

GitHub:
https://github.com/c-ehsan

