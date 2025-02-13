# Fine-Tuning DeepSeek-R1-Distill-Llama-8B with Unsloth

This repository provides a step-by-step guide for fine-tuning the `DeepSeek-R1-Distill-Llama-8B` model using `Unsloth`. It leverages LoRA (Low-Rank Adaptation) and optimized training techniques for efficient model training on Kaggle.

## Features
- Fine-tuning of DeepSeek-R1-Distill-Llama-8B
- Uses LoRA to optimize training
- Training on the `FreedomIntelligence/medical-o1-reasoning-SFT` dataset
- Implements optimized inference for better efficiency
- Tracks training using Weights & Biases (WnB)

## Installation
To set up the environment, install the required dependencies using:

```bash
pip install -r requirements.txt
```

## Usage

### 1. Setup API Keys
Before running the script, ensure you have Kaggle secrets set up for Hugging Face (`HF_Token`) and Weights & Biases (`wnb`).

### 2. Run the Fine-Tuning Script
Execute the script in a Kaggle notebook or a local environment:

```python
!pip install unsloth
!pip install --force-reinstall --no-cache-dir --no-deps git+https://github.com/unslothai/unsloth.git
```

### 3. Model Training
The script loads the dataset, formats it to match the prompt structure, and fine-tunes the model using the `SFTTrainer`.

### 4. Tracking with WnB
The training process is logged to Weights & Biases. Ensure that WnB is initialized properly with:

```python
wandb.login(key = "your_wandb_key")
wandb.init(project = 'Fine-tune-Deepseek-R1-Distill-Llama-8B', job_type = 'training', anonymous = 'allow')
```

### 5. Saving the Fine-Tuned Model
After training, the fine-tuned model is saved in the `outputs/` directory.

## Contributing
Feel free to submit pull requests or raise issues to improve the codebase!

## License
This project is licensed under the MIT License.

