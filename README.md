# Hierarchical Deep Learning Framework for Explainable Diabetic Retinopathy Detection

About This Repository
This repository releases the trained model weights and inference code for a two-stage hierarchical deep learning framework for automated Diabetic Retinopathy (DR) detection and severity grading from color retinal fundus images, developed as part of a Master's thesis in Digital Health at the Deggendorf Institute of Technology, Germany, and submitted for publication at an international conference.

The problem: Conventional flat multiclass classifiers struggle to distinguish adjacent DR severity grades, particularly the mild-to-moderate NPDR boundary, achieving multiclass AUC values as low as 0.75–0.85 and per-class sensitivities for Mild NPDR below 40%.

The solution: A clinically motivated two-stage pipeline that mirrors expert ophthalmological diagnosis:

Stage 1 — ResNet50 performs binary screening (No DR vs. DR), acting as a high-sensitivity triage filter

Stage 2 — InceptionResNetV2 performs fine-grained severity grading across four classes (Mild NPDR, Moderate NPDR, Severe NPDR, PDR)

Grad-CAM is applied at both stages to generate lesion-focused visual attribution heatmaps, localizing microaneurysms, hemorrhages, and neovascularization, enabling clinicians to verify model reasoning

Key results on APTOS 2019:

97% accuracy and macro-F1 of 0.97 (proposed vs. 90% flat baseline)

Cohen's κ of 0.9645 — exceeding the 0.94 QWK of Triple-DRNet (EyePACS)

Near-perfect AUC across all four DR severity grades

A Flask-based web application enables real-time point-of-care screening with embedded Grad-CAM overlays

Why it matters: The framework directly addresses EU AI Act and FDA SaMD transparency requirements by providing stage-specific visual explanations alongside every prediction, supporting clinical trust, auditability, and regulatory compliance
