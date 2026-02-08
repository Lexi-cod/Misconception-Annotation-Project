# First Place Solution vs My Best Model (DeBERTa-v3-xsmall + QLoRA)

This document explains how the first place solution in the MAP competition worked and how it compares to my best-performing approach. The goal here is not to hype either method, but to clearly explain *what was done, why it worked, and what I learned from it*.

---

## First Place Solution — How It Actually Worked

The first place solution did **not** solve this problem as a standard classification task.

Instead of training a model to directly predict a class ID, the problem was reframed as a **suffix (label) selection task**.

In simple terms:
- The **question and student explanation** are kept fixed (the prefix)
- Each possible `Category:Misconception` is treated as **text**
- The model scores which label text best fits the context

So the model is effectively answering:
> “Which of these label texts best completes this context?”

This framing works extremely well with **large language models**, because LLMs are trained to compare and complete text rather than predict numeric class IDs.

Key things the first place solution did well:
- Used **very large models** (Qwen, GLM, DeepSeek, up to 32B)
- Ran **multiple training seeds** per model
- Relied on **ensembling** instead of trusting a single run
- Paid close attention to **loss**, not just MAP@3
- Used heavy **engineering optimizations** (offloading, quantization, layer-wise inference)

Overall, the solution combined strong problem framing with large models and careful validation.

---

## My Best Solution — DeBERTa-v3-xsmall + QLoRA

My best solution followed a **different but more efficient path**.

I treated the task as a **multi-class sequence classification problem**:
- Input = question + selected answer + student explanation
- Output = one `Category:Misconception` label
- Model = **DeBERTa-v3-xsmall**
- Training = **4-bit quantization + LoRA (QLoRA)**
- Evaluation = **MAP@3**
- Output = Kaggle-compatible submission file

Instead of asking the model to compare label texts, the model directly predicts the class.

This approach worked well because:
- DeBERTa is **very strong at classification tasks**
- The model is small and **easy to fine-tune**
- QLoRA allows **fast training with low memory usage**
- Iteration speed is high, making experimentation practical

This setup resulted in a **~2% accuracy improvement** over my previous approach and became my **best-performing solution**.

---

## Why I Did Not Use Very Large Models

I did not avoid large models because they are ineffective.

I avoided them because:
- Training time is much longer
- Iteration becomes slow
- Debugging is harder
- Compute cost increases significantly

Instead, I optimized for:
- Fast feedback
- Stable training
- Clean implementation
- Strong performance per unit of compute

Given these constraints, DeBERTa-v3-xsmall + QLoRA was the most practical and effective choice.

---

## What I Learned

From the first place solution:
- Problem framing can matter more than model choice
- Single validation scores can be misleading
- Multi-seed ensembling improves reliability
- Engineering is a major part of top-level performance

From my own solution:
- Small models can still perform very well
- Classification-focused models are extremely effective
- QLoRA is powerful for fast experimentation

---

## Final Takeaway

The biggest lesson from this project was that how you frame the problem and prepare the data matters more than anything else.

Small changes in input structure, labeling strategy, or preprocessing can completely change how well a model learns, even when everything else stays the same. This project made it clear to me that strong performance often comes from thinking carefully about the task itself, not just from changing models.

