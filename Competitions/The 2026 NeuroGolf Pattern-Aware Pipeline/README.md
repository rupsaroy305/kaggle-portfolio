# Pattern-Aware ONNX Solver for ARC

An experimental framework for constructing lightweight ONNX networks to solve ARC (Abstraction and Reasoning Corpus) tasks in **the 2026 NeuroGolf Championship**.

Instead of training a single deep learning model, this project explores a modular approach where compact, task-aware neural networks are automatically generated for individual ARC reasoning problems.

## Notebook

**Kaggle Notebook:** [*Click Here*](https://www.kaggle.com/code/rupsarroy/pattern-aware-onnx-solver-for-arc)

## Competition

**The 2026 NeuroGolf Championship:** [*Click Here*](https://www.kaggle.com/competitions/neurogolf-2026)

## Overview

The objective of this project is to investigate whether small, highly specialized ONNX computation graphs can reproduce common ARC transformations while remaining computationally efficient. 
The notebook demonstrates the complete workflow, from representing ARC grids as one-hot tensors to exporting validated ONNX models for competition submission.


## What the Notebook Covers

* Environment setup and dependency configuration
* ARC grid preprocessing and one-hot tensor encoding
* ONNX graph construction utilities
* Identity transformation detection
* Gravity-based transformation solver
* Task-aware ONNX model generation
* Model verification using ONNX Runtime
* Memory and parameter analysis
* Solver performance summary
* Automatic generation of `submission.zip`

## Results

The complete pipeline was executed across **400 ARC tasks**, successfully generating valid ONNX models for **232 tasks**, achieving a **58.0% task coverage**.

The notebook also provides a summary of solved tasks, estimated model complexity, memory consumption, and overall framework performance.


##  Competition Results

| Metric | Score |
|--------|------:|
| **Private Score** | 3108.82 |
| **Leaderboard Rank** | 2118 / 3061 |


## Technologies

* Python
* NumPy
* ONNX
* ONNX Runtime
* NeuroGolf Utilities

## Output

The notebook generates:

* Task-specific ONNX networks
* Validation statistics
* Solver performance summary
* Competition-ready `submission.zip`

## Future Work

Potential extensions include implementing additional ARC transformation solvers such as object movement, rotation, reflection, cropping, color mapping, and symmetry detection to increase task coverage and improve overall solver performance.

## License

This project is intended for educational and research purposes.
