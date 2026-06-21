# Enterprise Invoice Reconciliation: A Hybrid Neuro-Symbolic Architecture

## 📌 Project Overview
This repository contains a proof-of-concept evaluation demonstrating the application of a **Hybrid Neuro-Symbolic Architecture** for automated B2B invoice reconciliation. Developed as part of an Executive MBA research initiative utilizing the Design Science Research (DSR) methodology, this project addresses the critical issue of "silent data poisoning" (mathematical hallucinations) when using pure Large Language Models (LLMs) for enterprise financial data extraction.

## 🏗️ Architecture
The project evaluates two paradigms:
1. **Pure Neural Baseline:** An LLM processes unstructured OCR text to extract financial entities (Net, VAT, Gross).
2. **Hybrid Neuro-Symbolic (Proposed):** An LLM performs the initial extraction, while a deterministic symbolic rules engine (built with Python's `pydantic`) enforces strict syntactic typing and mathematical business logic (e.g., `Net + VAT == Gross`).

## 📊 Dataset
The evaluation uses a Kaggle dataset of **100 OCR-Ready Synthetic Invoice PDFs** (Indian Consumer Electronics market), utilizing the raw embedded text (`ocred_text`) and the ground-truth structured JSON (`json_data`).

## 🚀 Key Findings & Business Impact
Through simulated pipeline execution, the neuro-symbolic framework proved superior for enterprise ERP integration:
* **Eliminated Data Poisoning:** The pure LLM silently allowed a ~10% rate of mathematical hallucinations. The symbolic layer actively blocked 100% of these logical errors.
* **Handled Syntactic Crashes:** Gracefully caught 5% of pipeline crashes caused by incomplete JSON generation.
* **100% Reconciliation Accuracy:** Guaranteed that every record passed to the downstream datastore was structurally and mathematically sound.

## 🛠️ Usage
Run the `Automated Invoice Reconcillation.ipynb` script to execute the simulation and generate the comparative performance metrics.
