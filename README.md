# AI-Powered Image Captioning

An image-captioning project built around a ViT-GPT2 model, with scripts for preparing COCO and Stable Diffusion datasets, training models, evaluating captions with BLEU, and running a Gradio demo.

## Project contents

- `notebooks/` — numbered scripts for dataset preparation, model training, checkpoint loading, and BLEU evaluation.
- `frontend/` — a Gradio image-captioning demo.
- `images/Dataset_Structure.jpg` — dataset layout reference.

## Workflow

The scripts are intended to be run in sequence:

1. Connect Google Drive in Colab and download COCO annotations.
2. Split the data and prepare the COCO and AI-generated image datasets.
3. Train the ViT-GPT2 models using the training scripts.
4. Load checkpoints and run the BLEU evaluation scripts.
5. Configure the checkpoint location in the Gradio script and launch the demo.

The dataset and model paths in the scripts currently refer to Google Drive locations. Update them to match your environment before running the scripts.

## Running the demo

Install the demo dependencies:

```bash
pip install gradio transformers torch pillow
```

Update `output_model_dir` in the Gradio script to point to a directory containing the trained model, tokenizer, and image processor, then run the script:

```bash
python "frontend/17.GRADIO frontend for A.I image captioner model formed.py"
```

## Data and model files

This repository contains the project scripts and documentation only. The COCO data, generated datasets, and trained model checkpoints are not included; obtain or create those separately before running training, evaluation, or inference.

## Evaluation results

The original project notes report the following BLEU scores:

| Model | BLEU (COCO) | BLEU (AI) |
|---|---:|---:|
| ViT-GPT2 (COCO) | 0.135 | 0.105 |
| ViT-GPT2 (AI) | 0.088 | 0.094 |
