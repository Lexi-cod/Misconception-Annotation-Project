# Misconception-Annotation-Project
Kaggle Competition: Predicting math misconceptions from student explanations with NLP.

# Misconception Annotation Project (MAP)

This repository contains my work on the Kaggle MAP competition, where the goal is to identify mathematical misconceptions from students’ written explanations using NLP and machine learning.

## Highlights
- Iterative model development from baseline (~40%) to final model (~93%)
- Experiments with DeBERTa, Qwen, ensembling, and optimization techniques
- Detailed research timeline and paper notes
- Learnings from the 1st place solution

## Project Structure
- `experiments/` – model notebooks across iterations
- `timeline.md` – chronological learning and experimentation journey
- `solution_summary.md` – explanation of the winning approach
- `notes/` – research notes on models and optimization techniques

## Problem Statement

Students’ written explanations in mathematics often reveal underlying misconceptions—systematic errors in reasoning that arise when prior knowledge is incorrectly applied or new concepts are misunderstood. Identifying these misconceptions is crucial for providing targeted feedback and improving learning outcomes, but manually annotating student responses is time-consuming, subjective, and difficult to scale.

The Misconception Annotation Project (MAP) addresses this challenge by framing misconception detection as an NLP classification task. Given a math question, multiple-choice context, and a student’s explanation, the goal is to predict whether the response is correct, neither correct nor misconception-based, or reflects a specific misconception. Each response is associated with exactly one correct Category:Misconception label, and models may output up to three ranked predictions, evaluated using Mean Average Precision at 3 (MAP@3).

This task is particularly challenging due to the subtlety of misconceptions, the domain-specific mathematical reasoning required, and label noise across categories. Effective solutions must generalize across different problems while accurately capturing nuanced patterns in student reasoning.

## Key Results
| Model Version | Approach | Accuracy |
|--------------|--------|----------|
| MAP_v1 | Initial baseline & Ensemble | ~40–60% |
| MAP_v3 | Improved modeling | ~90% |
| MAP_fv | Optimized DeBERTa | ~93% |

## Acknowledgments
Thanks to Vanderbilt University, The Learning Agency, Eedi, and Kaggle for hosting this competition.
