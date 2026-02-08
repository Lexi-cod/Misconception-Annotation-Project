# Project Timeline - MAP Misconception Annotation

A short timeline of how I progressed through the project.

- **Understanding the problem**
  - Read the competition description and MAP@3 evaluation metric.
  - Explored the dataset to understand questions, choices, student explanations, and labels.

- **Model research and learning**
  - Read about transformer models, starting from BERT and moving to DeBERTa.
  - Learned parameter-efficient fine-tuning methods such as LoRA and QLoRA.

- **Experiment 1: Efficiency and parameter reduction**
  - Tried parameter reduction with QLoRA using DeBERTa.
  - Result: **~40% accuracy**, indicating this approach was not effective on its own.

- **Experiment 2: Ensemble attempt**
  - Tried an ensemble of Qwen and DeBERTa using the same formulation.
  - Result: small improvement to **~60%**, but with a large increase in runtime.

- **Key insight: problem formulation**
  - Realized the main limitation was likely not the model, but how inputs and labels were framed.

- **Experiment 3: Reformulation with QLoRA**
  - Reworked input formatting and label construction to better represent correct vs. incorrect reasoning.
  - Used 4-bit quantization and QLoRA with Qwen.
  - Result: large performance jump to **~91%**.

- **Final experiment: DeBERTa-v3-xsmall**
  - Switched the backbone to DeBERTa-v3-xsmall while keeping the improved formulation and QLoRA setup.
  - Result: best overall performance at **~93%**.

- **Additional exploration and next steps**
  - Looked into other models such as LLaMA and GPT variants.
  - Ultimately stuck with Qwen and DeBERTa, as they performed best for my setup.
  - The same method could be further explored using larger backbones (e.g., DeBERTa-large, ModernBERT, or larger Qwen models) to potentially gain additional accuracy.

