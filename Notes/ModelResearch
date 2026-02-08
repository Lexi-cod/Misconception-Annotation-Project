# Paper Notes — What I Learned During the Project

Below are short notes on each paper I read during the project and what I took away from them in practical terms.

---

## Attention Is All You Need (2017)  
https://arxiv.org/abs/1706.03762

This paper introduced the Transformer architecture and showed that attention alone is enough to model relationships in text. What stood out to me was how self-attention lets the model look at all parts of the input at once instead of step by step like RNNs. This helped me understand why modern NLP models are so good at understanding long and structured inputs like questions and explanations, which is exactly what this competition needed.

---

## BERT: Bidirectional Encoder Representations from Transformers  
https://arxiv.org/abs/1810.04805

BERT showed how powerful bidirectional context is for understanding text. Instead of reading left-to-right, the model sees the full sentence at once, which makes it very strong for classification tasks. Reading this helped me understand why encoder-based models are a natural fit for problems where the goal is understanding meaning rather than generating text.

---

## DeBERTa: Decoding-enhanced BERT with Disentangled Attention  
https://arxiv.org/abs/2006.03654

DeBERTa builds on BERT by separating *what* a word is from *where* it appears using disentangled attention. This made it clearer to me why DeBERTa often outperforms BERT on classification benchmarks. It reinforced the idea that small architectural changes can lead to meaningful improvements in understanding complex inputs.

---

## DeBERTa-V3: Improving DeBERTa using ELECTRA-style pretraining  
https://arxiv.org/abs/2111.09543

DeBERTa-V3 showed that better pretraining strategies can matter just as much as architecture. Using replaced token detection instead of masked language modeling helped produce stronger representations. This made me realize that how a model is pretrained strongly affects how well it fine-tunes later, even when the downstream task stays the same.

---

## LoRA: Low-Rank Adaptation of Large Language Models  
https://arxiv.org/abs/2106.09685

LoRA introduced the idea of fine-tuning models by updating only small low-rank matrices instead of all parameters. This paper completely changed how I thought about fine-tuning. It showed that you don’t need to update everything to get good results, and that efficiency and performance don’t always have to be trade-offs.

---

## QLoRA: Efficient Finetuning of Quantized LLMs  
https://arxiv.org/abs/2305.14314

QLoRA combined quantization with LoRA to make fine-tuning much more memory-efficient. The key takeaway for me was that careful engineering choices can make large models usable without changing the core learning behavior. This paper directly influenced my experiments and made it possible to run more iterations and test ideas faster.

---

## Parameter-Efficient Fine-Tuning for Large Models (2025)  
https://arxiv.org/abs/2512.17983

This paper reinforced the idea that parameter-efficient methods are not just tricks but a serious research direction. It helped me see LoRA-style methods as part of a bigger trend rather than isolated techniques, and gave confidence that using these methods is a sound design choice.

---

## Language Models are Few-Shot Learners (GPT-3)  
https://arxiv.org/abs/2005.14165

This paper showed how scaling models leads to emergent abilities like few-shot learning. While I didn’t directly use GPT-3, reading this helped me understand why large models behave so differently from smaller ones. It also helped explain why the first-place solution benefited so much from larger models and different problem framing.

---

## RoBERTa: A Robustly Optimized BERT Pretraining Approach  
https://arxiv.org/abs/1907.11692

RoBERTa showed that many gains come from better training setups rather than new architectures. Longer training, better data usage, and removing unnecessary constraints led to large improvements. This reinforced the idea that implementation details and training choices matter a lot.

---

## Quantization of Large Language Models  
https://arxiv.org/abs/2303.11287

This paper helped me understand the trade-offs involved in quantizing models. It explained how reducing numerical precision can speed up training and inference while still preserving performance if done carefully. This directly connected to my use of 4-bit quantization and helped me reason about when and why it works.

---

## Overall Reflection

Reading these papers made it clear that strong performance usually comes from **combining ideas**:
- good architectures
- smart pretraining
- efficient fine-tuning
- and, most importantly, clear problem formulation

More than anything, this reading phase shaped how I think about NLP systems as a whole, not just individual models.

