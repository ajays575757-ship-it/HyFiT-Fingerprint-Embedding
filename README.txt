HyFiT: A Lightweight Hybrid CNN–Transformer Framework for Protocol-Sensitive Fingerprint Embedding Analysis
Overview
This repository contains the official implementation of the proposed HyFiT (Hybrid Fingerprint Transformer) framework for protocol-sensitive fingerprint embedding analysis. The framework combines lightweight convolutional feature extraction with transformer-based global contextual modeling to generate compact and discriminative fingerprint embeddings for biometric recognition and verification analysis.
The study investigates the relationship between classification accuracy, embedding geometry, verification robustness, and dataset protocol sensitivity under varying fingerprint acquisition conditions.
Main Contributions
* Lightweight hybrid CNN–Transformer fingerprint representation framework
* 128-dimensional L2-normalized embedding generation
* Protocol-sensitive fingerprint embedding analysis
* Verification-oriented biometric evaluation
* Reduced-impression fingerprint evaluation
* Embedding-centric analysis using ROC, AUC, EER, and t-SNE
* Comparative evaluation using:
o Softmax classification
o SVM classification
o KNN classification
o Triplet-loss-based metric learning

Experimental Protocols
The framework was evaluated using:
1. FVC2000 (Grayscale)
2. FVC2000 (Colorized)
3. FVC2000(R) Reduced-Impression Grayscale
4. FVC2000(R) Reduced-Impression Colorized
5. SOCOFing (100-Class Sparse-Impression Protocol)
6. 
Experimental Stages
Stage 1 — Baseline CNN
Conventional CNN-based fingerprint classification.
Stage 2 — HyFiT + Cross Entropy + Softmax
Hybrid CNN–Transformer learning using cross-entropy supervision.
Stage 3 — HyFiT + Cross Entropy + SVM/KNN
Embedding extraction followed by external SVM and KNN evaluation.
Stage 4 — HyFiT + Triplet Loss + SVM/KNN
Metric-learning-based embedding optimization using Triplet Loss.
Repository Structure
HyFiT-Fingerprint-Embedding/
?
??? README.md
??? requirements.txt
??? LICENSE
?
??? Stage_1_Baseline_CNN/
??? Stage_2_HyFiT_Softmax/
??? Stage_3_HyFiT_SVM_KNN/
??? Stage_4_HyFiT_Triplet/
?
??? Figures/
??? Results/
??? Datasets_Info/
??? utils/
Architecture Summary
ComponentConfigurationInput Resolution224 × 224CNN StemConv + BN + GELU + MaxPoolPatch Size7 × 7Transformer Depth6 BlocksAttention Heads8 HeadsTransformer Embedding Dimension256Projection Dimension128NormalizationL2 NormalizationTotal Parameters~6.78 Million


Evaluation Metrics
The proposed framework is evaluated using:
* Classification Accuracy
* Mean ± Standard Deviation
* ROC Curve Analysis
* Area Under Curve (AUC)
* Equal Error Rate (EER)
* Intra-Class Distance
* Inter-Class Distance
* Embedding Separation Margin
* t-SNE Visualization

Key Findings
* Classification accuracy alone is insufficient for evaluating fingerprint embedding quality.
* Cross-entropy-based embedding learning frequently produced more stable verification behaviour than metric-learning-based optimization under sparse-impression conditions.
* Reduced-impression protocols strongly affect embedding separability and geometric stability.
* SOCOFing exhibited severe embedding overlap and verification degradation despite moderate classification accuracy.
* Protocol-aware biometric evaluation is essential for reliable fingerprint representation analysis.

Installation
pip install -r requirements.txt

Dataset Preparation
Please refer to:
Datasets_Info/dataset_description.md
Datasets_Info/preprocessing.md
for dataset organization and preprocessing details.




Running Experiments
Stage 1 — Baseline CNN
python train_baseline.py
Stage 2 — HyFiT + Softmax
python train_softmax.py
Stage 3 — Embedding Extraction + SVM/KNN
python extract_embeddings.py
python train_svm.py
python train_knn.py
Stage 4 — Triplet Loss + SVM/KNN
python train_triplet.py

Citation
If you use this repository in your research, please cite the associated manuscript after publication.
License
The associated manuscript is currently under review in Machine Learning with Applications. Citation information will be updated after publication
Contact
For questions or collaboration inquiries, please contact the corresponding author.

