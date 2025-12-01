# Clone My Professor

This project helps researchers clone the writing style of their Principal Investigators (PIs) or professors, allowing for reduced revisions when adapting to their preferred language style.

## Table of Contents
- [Overview](#overview)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Data Preparation](#data-preparation)
- [Model Training](#model-training)
- [Inferencing](#inferencing)
- [Saving & Loading Models](#saving-loading-models)

## Overview
Professors often have distinct writing styles that can be observed in their publications. By automating the process of learning these styles, the project simplifies the task of rewriting drafts in a manner closer to that of the professor's style.

## Tech Stack
- `ollama`
- `PyPDF2`
- `unsloth`

## Installation
To install the necessary dependencies, run the following command:

```bash
pip install PyPDF2 unsloth
```

## Usage
1. **Load Publications**: Place the professor's published papers into a folder named `papers`.
2. **Extract Text**: The code will extract text from the PDFs in the `papers` directory.
3. **Clean and Chunk Text**: The extracted text will be cleaned and divided into manageable chunks.
4. **Simplify Text**: Use the OpenAI API to simplify the text into a form suitable for rewriting.
5. **Fine-tune the Model**: Use the `unsloth` library to fine-tune a language model.
6. **Inferencing**: Utilize the model to rewrite text based on the learned professor style.

## Data Preparation
Data is prepared by extracting, cleaning, and chunking the text from the PDF files. Here's how you can prepare the data:
- Load PDF files from the `papers` folder
- Extract and clean text using regex for better analysis
- Segment the cleaned text into 2000 character chunks for processing

## Model Training
The model is trained using the `unsloth` library. Fine-tuning capitalizes on the unique characteristics of the professor's writing style. Follow the training steps provided in the code to obtain the adapted model.

## Inferencing
For continuous inference, a `TextStreamer` can be used, allowing the user to see the generative text token by token.

## Saving & Loading Models
To save the trained model, use Huggingface's `push_to_hub` for online saving or `save_pretrained` for local. Remember, this saves only the LoRA adapters and not the full model.

---
Enjoy your journey in perfecting your academic writing by adapting to your professor's style!