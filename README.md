# SEQURE

**An Intent-Aware, Explainable SIEM Using Behavioral Sequence Modeling**

---

## Overview

SEQURE is a research-driven Security Information and Event Management (SIEM) system designed to detect stealthy cyber attacks by modeling **behavioral evolution over time**, rather than relying on isolated log events or opaque machine learning predictions.

Unlike traditional SIEM platforms that depend heavily on static rules or black-box anomaly detection, SEQURE focuses on **intent inference** — identifying how malicious behavior gradually emerges through repetition, adaptation, and temporal patterns.

The system emphasizes **explainability, analyst trust, and narrative-driven alerts**, making detections both actionable and understandable.

---

## Motivation

Modern SIEM systems face persistent challenges:

* Rule-based detections fail against low-and-slow attacks
* ML-based detections often act as black boxes
* Analysts are overwhelmed with alerts lacking context
* Behavioral drift and evolving environments degrade model reliability

SEQURE is motivated by a simple idea:

> Attacks do not announce themselves in single events — they reveal intent through behavioral sequences.

By modeling activity as structured sessions composed of ordered events, SEQURE aims to surface malicious intent early while reducing false positives and analyst fatigue.

---

## Core Concepts

* **Session-Centric Analysis**:
  Activity is grouped into behavioral sessions rather than treated as isolated log entries.

* **Sequence-Based Intent Modeling**:
  Temporal models analyze how behavior evolves across time to infer malicious intent.

* **Hybrid Detection Pipeline**:
  Combines statistical baselines, interpretable anomaly detection, and deep learning.

* **Explainability by Design**:
  Every alert is supported by feature-level explanations and raw evidence.

* **Narrative-Driven Alerts**:
  Alerts are presented as coherent attack stories, not disconnected signals.

---

## Initial Scope

The current scope focuses on **web application attacks observed through HTTP traffic**, including:

* SQL Injection
* Cross-Site Scripting (XSS)
* Directory Traversal
* Credential Stuffing / Brute Force

This domain provides rich structure for behavioral modeling while remaining realistic and extensible to broader SIEM use cases.

---

## High-Level Architecture

```
PCAP / Logs
     │
     ▼
Ingestion & Normalization
     │
     ▼
Session & Event Modeling
     │
     ▼
Baseline & Anomaly Detection
     │
     ▼
Sequence-Based Intent Modeling
     │
     ▼
Correlation & Narrative Engine
     │
     ▼
Analyst-Facing Alerts & Explanations
```

---

## Technology Stack

* **Language:** Python
* **ML:** scikit-learn, PyTorch
* **Sequence Models:** ConvGRU / Temporal Models
* **Storage:** PostgreSQL
* **Backend API:** FastAPI
* **Frontend (Prototype):** Streamlit
* **Packet Analysis:** Scapy / PyShark

---

## Project Structure (Planned)

```
sequre/
├── ingestion/        # PCAP and log parsing
├── modeling/         # Baselines, anomaly detection, intent models
├── correlation/      # Alert correlation and narrative generation
├── storage/          # Database schemas and access layer
├── api/              # Backend API
├── frontend/         # Analyst dashboard
├── experiments/      # Notebooks and evaluation
└── docs/             # Design and evaluation documentation
```

---

## Goals

* Detect stealthy and adaptive attacks earlier than rule-based SIEMs
* Reduce false positives through intent-aware correlation
* Provide transparent, human-readable explanations for alerts
* Demonstrate a practical architecture for explainable ML in SIEM systems

---

## Status

🚧 **Work in progress**
Currently in the design and data modeling phase.

---

## Future Work

* Expand beyond HTTP traffic to system and cloud logs
* Evaluate robustness against adversarial behavior
* Compare against commercial SIEM detection strategies
* Explore graph-based reasoning for multi-entity correlation

---

## ✍️ Author

Made with ♥ by [Payal Samant](https://github.com/pys07)
