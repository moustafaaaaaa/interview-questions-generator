Interview Question Generator

A Python-based AI project that generates relevant interview questions for a given job title. The model is trained using the GPT-Neo architecture with LoRA (Low-Rank Adaptation) for efficient fine-tuning.

This project demonstrates end-to-end NLP model training, fine-tuning, and deployment using modern libraries such as PyTorch, Transformers, PEFT, and Gradio.

Features

Generates multiple interview questions based on a job title.

Supports diverse question generation using top-p (nucleus) sampling and adjustable temperature.

Fine-tuned with LoRA to optimize training on limited data.

Evaluation with ROUGE metrics to measure similarity with reference questions.

Simple deployment with Gradio for interactive use.

Technologies & Libraries Used

Python 3.11

PyTorch – for deep learning and model training

Transformers (Hugging Face) – for GPT-Neo model and tokenization

PEFT / LoRA – for parameter-efficient fine-tuning

Datasets – for handling tabular and text data

Evaluate – for ROUGE-based evaluation

Pandas – for data manipulation

Gradio – for web-based deployment

Dataset

The model is trained on a dataset of interview questions stored in a CSV file. The dataset should have a text column (e.g., Text or question_text) containing reference questions.

Training

The model is fine-tuned on GPT-Neo 1.3B with the following configuration:

LoRA parameters: r=8, lora_alpha=16, lora_dropout=0.1

Batch size: 4

Learning rate: 2e-4

Epochs: 3

Example Usage
job_title = "Software Engineer"
generated_questions = generate_questions(job_title, num_questions=5)
print(generated_questions)


Sample Output:

1. What is your experience with Python and software development?
2. How do you handle version control in your projects?
3. Explain a challenging bug you resolved in the past.
4. Describe your experience with Agile methodologies.
5. How do you ensure code quality and testing in your work?

Evaluation

The model was evaluated using ROUGE to measure similarity between generated questions and reference questions:

ROUGE-1: 0.431

ROUGE-2: 0.305

ROUGE-L: 0.431

These results indicate a moderate overlap with reference questions, which is expected given the diversity of valid interview questions.

Deployment

The model can be deployed using Gradio for an interactive web interface:

FP16 training enabled if GPU is available

The model uses causal language modeling for question generation.
