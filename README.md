# Hate Speech Detection Pipeline

## 📌 Overview
This repository contains Jupyter notebook files for the paper.  
For anonymity, all links to models and datasets have been removed.  
Only links to the Unsloth model are included.  
As a result, all fine-tuned models could not be included, as their sizes are larger than 50MB.

### Evaluation
The performance of the fine-tuned models (LGB, Vote, Mean, Human, and Human-LGB) is evaluated for Hate/Neutral:
- The files include the probability outputs for each label for all fine-tuned models.
BERT models need to be fine-tuned on specific data before they can generate results. The base models are available on Hugging Face.

### Labeling
- **LLM_Labeling**: Prompt file for generating probabilities for labels from four language models: Mistral-7B, Llama3.1-8B, Gemma2-9B, and Qwen2.5-14B.
- **Ensemble_Labeling**: Creates ensemble labeling for three methods: LGB, Vote, and Mean, from the four language model probabilities.
- Includes a portion of 50K samples of the synthetic dataset for each task.
- LGB-trained models :
  - `lgb_model_label_1.pkl` and `lgb_model_label_2.pkl` for the 2-label task.

### Training
- **LightGBM_Labeled**: Training LightGBM models using the human-labeled dataset.
- **LoRA**: Training LoRA fine-tuned models for two base models: Llama3.2-1B and Qwen2.5-14B.
- **Pretrained-Bert**:
