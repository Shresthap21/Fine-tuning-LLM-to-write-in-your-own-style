# Fine-Tuning Llama 3.2 on My Writing Style Using LoRA, Unsloth, and Ollama

This project demonstrates how I fine-tuned **Llama 3.2 3B** on a custom dataset created from my own writing style using **LoRA** and **Unsloth** on a free **Google Colab T4 GPU**.

The goal was not to teach the model new knowledge, but to adapt its writing style to better match the tone, structure, and explanations found in my existing content.


## Project Overview

Modern fine-tuning tools have lowered the barrier to training language models. Using a small dataset of personal writing samples, I fine-tuned Llama 3.2 with LoRA adapters and exported the resulting model to GGUF format for local inference.

The project covers:

- Dataset creation and curation
- JSONL dataset formatting
- LoRA fine-tuning with Unsloth
- Model evaluation
- Avoiding overfitting
- GGUF export
- Ethical considerations when training on personal data


## Tech Stack

- Llama 3.2 3B Instruct
- Unsloth
- TRL (SFTTrainer)
- Google Colab (T4 GPU)
- Ollama
- GGUF
- Python


## Workflow

```text
Personal Writing Samples
            ↓
Instruction-Response Dataset
            ↓
LoRA Fine-Tuning (Unsloth)
            ↓
Llama 3.2 
            ↓
Custom Writing Model
            ↓
GGUF Export
            ↓
Local Inference (Ollama)
```


## Dataset

The training dataset was created from content I had previously written, including:

- LinkedIn posts
- Instagram captions
- Technical explanations
- Educational content

Each example was converted into an instruction-response pair.

Example:

```json
{"instruction":"Write a LinkedIn post about Kubernetes","response":"Kubernetes is one of those technologies..."}
```

The dataset was then converted into JSONL format and then loaded.


## Fine-Tuning

The model was fine-tuned using:

- LoRA adapters
- Unsloth optimization
- Google Colab free T4 GPU

This approach significantly reduces memory requirements compared to full fine-tuning while preserving strong performance for style adaptation tasks.


## Results

After training, the model was able to generate content that reflected patterns found in the training data, including:

- Technical educational explanations
- Social media style formatting
- Conversational tone
- Developer-focused content

The project successfully demonstrated style adaptation using a relatively small custom dataset.


## Exporting the Model

After training, the LoRA adapters were exported into GGUF format.

This makes the model compatible with:

- Ollama
- llama.cpp
- Other GGUF-supported inference engines


## Ethical Considerations

Training on personal data requires careful consideration.

For this project, the dataset consisted only of content that I had personally created. No private conversations, confidential information, or third-party data were used.

Anyone attempting a similar project should ensure they have permission to use the data included in the training dataset.


## Modified Colab Notebook used for training:
https://colab.research.google.com/drive/1XKiVabzzSTwQ0FjgjPS7ZukeWLCXcve6

Built on top of the official Unsloth Llama 3.2 notebook.

## Article

Read the complete write-up on Dev.to:

**https://dev.to/shresthapandey/i-fine-tuned-llama-32-on-my-own-writing-style-using-lora-unsloth-and-a-free-colab-gpu-13l5**


## Resources

- Unsloth: https://github.com/unslothai/unsloth
- Unsloth notebooks: https://unsloth.ai/docs/get-started/unsloth-notebooks#standard-sft-notebooks
- Ollama: https://ollama.com
