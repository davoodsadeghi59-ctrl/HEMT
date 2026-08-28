# HEMT-AI Framework

**Physics-Guided Artificial Intelligence Framework for AlGaN/GaN MOS-HEMT Biosensors**

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)](https://www.tensorflow.org/)
[![Status](https://img.shields.io/badge/Status-Thesis%20Project-green)]()

---

## Overview

This repository contains a complete **physics-guided machine learning framework** developed for predicting the drain current (I<sub>DS</sub>) of **AlGaN/GaN MOS-HEMT biosensors** using data generated from Silvaco TCAD simulations.

The framework integrates:
- Automated extraction of I–V characteristics from TCAD log files
- Design of Experiments (Latin Hypercube Sampling)
- Data preprocessing and scaling
- Artificial Neural Network (ANN) regression model
- Model evaluation and residual analysis
- Explainable AI (SHAP + Permutation Importance)

**Author:** AmirReza Sadeghi  
**Version:** 1.1.0  
**Status:** Thesis Project (Final Delivery)

---

## Scientific Motivation

AlGaN/GaN MOS-HEMTs are promising candidates for high-sensitivity biosensors due to their high electron mobility and surface sensitivity. Traditional TCAD simulations are accurate but computationally expensive for large design-space exploration.

This work develops a **surrogate model** that learns the mapping from key device parameters to I<sub>DS</sub>, enabling rapid prediction while remaining grounded in physics-based simulation data.

**Input features:**
- `EPS` — Relative permittivity of the gate dielectric
- `QF` — Fixed interface charge density (cm⁻²)
- `VGS` — Gate-source voltage (V)

**Target:**
- `IDS` — Drain current (A)

All simulations were performed at a fixed drain-source bias of **V<sub>DS</sub> = 5 V**.

---

## Key Results

| Metric | Value |
|--------|-------|
| **R² Score** | 0.890 |
| **MAE** | 0.0127 |
| **RMSE** | 0.0174 |
| **MAPE** | 24.96% |
| Training samples | ~4,500 |
| Test samples | 965 |
| TCAD log files | 30 |
| Total I–V points | 6,432 |

**Feature Importance (SHAP):**
1. **VGS** (dominant) — Mean |SHAP| ≈ 0.679
2. **QF** — Mean |SHAP| ≈ 0.231
3. **EPS** — Mean |SHAP| ≈ 0.201

These results confirm that the gate voltage is the primary driver of I<sub>DS</sub>, while interface charge and dielectric permittivity act as important secondary modulators — consistent with the physics of MOS-HEMT devices.

---

## Repository Structure
