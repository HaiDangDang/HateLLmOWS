# Hate Speech Detection Pipeline

## 📌 Overview
This repository contains Jupyter notebook files for the paper.  
For anonymity, all links to models and datasets have been removed.  
Only links to the Unsloth model are included.  
As a result, all fine-tuned models could not be included, as their sizes are larger than 50MB.

### Evaluation
The performance of the fine-tuned models (LGB, Vote, Mean, Human, and Human-LGB) is evaluated for two tasks:
- Two files are included for evaluating the two tasks: 2-labels and 3-labels.
- Data includes `df_eval_set_1` and `df_eval_set_2` for the 2-label task, and `df_eval_set` for the 3-label task.
- The files include the probability outputs for each label for all fine-tuned models, which could not be included in the repository.
- These files cannot be run without the models.

### Labeling
- **LLM_Labeling**: Prompt file for generating probabilities for labels from four language models: Mistral-7B, Llama3.1-8B, Gemma2-9B, and Qwen2.5-14B.
- **Ensemble_Labeling**: Creates ensemble labeling for three methods: LGB, Vote, and Mean, from the four language model probabilities.
- Includes a portion of 50K samples of the synthetic dataset for each task.
- LGB-trained models for two tasks:
  - `2_lgb_label_1.pkl` and `2_lgb_label_2.pkl` for the 2-label task.
  - `3_lgb_label.pkl` for the 3-label task.

### Training
- **LightGBM_Labeled**: Training LightGBM models using the human-labeled dataset.
- **LoRA**: Training LoRA fine-tuned models for two base models: Llama3.2-1B and Qwen2.5-14B.
- **7_Human_Dataset**: 84k human-labeled dataset from seven test sets, group 1 of the 2-label task in the paper.
- **LGB_Data_2_Label**: Human-labeled dataset with probabilities from four language models for the 2-label task.
- **LGB_Data_3_Label**: Human-labeled dataset with probabilities from four language models for the 3-label task.
