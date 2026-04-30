# ESoC 2026 Proposal: Agentic Benchmarking Framework for sktime-mcp

## Overview

This project proposes a unified benchmarking framework for evaluating agent-generated workflows in the sktime-mcp ecosystem.

The goal is to create a standardized evaluation layer where agentic pipelines can be compared based on correctness, task alignment, and predictive performance.

## Existing Work

This proposal builds directly on my ongoing contribution:
- https://github.com/sktime/sktime-mcp/pull/396

## Current Progress

An initial version of the benchmark framework has already been implemented and tested locally (8/8 tests passing), forming the foundation for this proposal.

---

## Motivation

With LLM-based agents increasingly generating ML pipelines, there is a need for a consistent way to evaluate:

* Pipeline validity
* Task correctness
* Real-world performance

Currently, sktime-mcp lacks a structured benchmarking system.

---

## Core Idea

A benchmark system with 3 evaluation dimensions:

* **Pipeline Validity (30%)**
* **Task Alignment (20%)**
* **Performance (50%)**

---

## Key Features

* YAML-based task definitions
* Modular runner for executing workflows
* Scoring engine for evaluation
* Extensible design for future tasks

---

## Expected Outcomes

* Benchmark suite integrated into sktime-mcp
* Multi-task coverage (forecasting, classification, detection)
* CI integration
* Agent performance comparison

---

## Why Me

I have already contributed to sktime and sktime-mcp through:

* Fixing forecasting and dependency issues
* Improving estimator utilities and test coverage
* Designing and implementing the initial benchmark framework

---

## Example Usage

```python
from sktime_mcp.benchmark.runner import BenchmarkRunner
from sktime_mcp.benchmark.scorer import BenchmarkScorer
from sktime_mcp.benchmark.tasks import load_all_tasks

runner = BenchmarkRunner()
scorer = BenchmarkScorer()

all_results = runner.run_all()

for task in load_all_tasks():
    scores = scorer.score_results(all_results[task.name], task)
    print(scorer.summary(scores))
```

This demonstrates how agent-generated pipelines can be executed and evaluated across multiple tasks using the proposed benchmarking framework.


## GitHub

https://github.com/Rohitstwt

