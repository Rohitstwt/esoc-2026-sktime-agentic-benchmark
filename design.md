# Design Overview

The agentic benchmarking framework is structured into three main components:

---

## 1. Task Definition

Tasks are defined using YAML files.

Each task specifies:

* Dataset
* Task type (forecasting, classification, etc.)
* Evaluation metric

This allows contributors to add new tasks without modifying core code.

---

## 2. Runner

The runner executes agent-generated pipelines across all defined tasks.

Responsibilities:

* Load tasks
* Execute pipelines
* Collect results

---

## 3. Scorer

The scorer evaluates results across three dimensions:

* **Pipeline Validity** — checks correctness of pipeline structure
* **Task Alignment** — verifies if the selected estimator matches the task
* **Performance** — evaluates predictive accuracy (e.g., MAPE)

---

## Design Principles

* Modular and extensible
* Easy task addition (YAML-based)
* Clear separation of execution and evaluation
* Compatible with future CI integration
