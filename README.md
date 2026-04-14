

# Gas Video-1000 Dataset

**Gas Video-1000** is a curated benchmark designed to systematically probe "spatiotemporal sycophancy" in Video Large Language Models (Vid-LLMs) under adversarial conversational pressure.

[🏠 Project Page](https://pengkun-jiao.github.io/GasVideo-1000)
[<img src="https://huggingface.co/front/assets/huggingface_logo-noborder.svg" alt="Hugging Face Logo" width="18" style="vertical-align: middle; margin-right: 4px;"> Dataset](https://huggingface.co/datasets/kk12ff/GasVideo1000) 

![Gas Video-1000 Framework](./static/images/framework.jpg)

## Core Phenomenon: Spatiotemporal Sycophancy
This benchmark specifically evaluates a critical failure mode in Vid-LLMs:
* **Definition**: Under negation-based gaslighting, models retract initially correct, visually grounded judgments and conform to misleading user feedback.
* **Rationalized Hallucination**: Rather than merely changing their answers, the models frequently generate fabricated temporal or spatial explanations to justify their incorrect revisions. 

![Temporal Sycophancy](./static/images/example1.jpg) ![Spatial Sycophancy](./static/images/example2.jpg)

## Dataset Construction Principles & Scale
Gas Video-1000 consists of **1,013 high-quality samples**. The construction of the dataset adheres strictly to three core principles:
**Objective Grounding**: Samples are selected with unambiguous visual evidence to ensure that "belief reversal" stems from conversational pressure rather than visual uncertainty.
**Temporal Density**: For Temporal Understanding, the dataset prioritizes samples requiring information aggregation over time, as these are uniquely vulnerable to temporal distortion attacks.
**Balanced Complexity**: The dataset maintains a mix of simple recognition and complex reasoning to determine if model fragility correlates with task difficulty.

## Data Sources
The samples in Gas Video-1000 are drawn from several prominent general video comprehension and fine-grained reasoning benchmarks:
* **MSRVTT-QA**: 300 samples
* **PerceptionTest**: 293 samples 
* **ActivityNet-QA**: 200 samples 
* **MVBench**: 120 samples 
* **VideoMME**: 100 samples

## Task Taxonomy
To enable a systematic analysis, the curated samples are reorganized into a unified taxonomy consisting of 3 high-level domains and 8 sub-categories:

* **🌐 General Knowledge (45.0%)**: 
  * **Media Topics (15.0%)**: Spans genres such as movies, news, and sports to test resilience against stylistic biases.
  * **Daily Life (13.9%)**: Focuses on routine activities (e.g., cooking, family) to challenge common-sense grounding under negation.
  * **Scene Context (3.3%)**: Assesses the stability of environmental reasoning, such as location identification.
  * **Logical Reasoning (12.8%)**: Examines whether models succumb to negation when the overarching narrative or setting is challenged.
* **⏳ Temporal Understanding (27.4%)**: 
  * **Action Recognition (14.2%)**.
  * **Temporal Sequencing (7.4%)**.
  * **Temporal Prediction (5.8%)**.
* **📐 Spatial Understanding (27.5%)**: 
  * **Object Recognition (12.4%)**.
  * **Spatial Relations (9.2%)**.
  * **Object Counting (5.9%)**.

## Evaluation Protocols and Pressure Types
To simulate real-world social pressures, the benchmark utilizes three categories of negation-based gaslighting prompts to coerce models into retracting correct judgments:
* **Direct Denial**: Explicitly rejects the model's prediction by flatly asserting a false alternative premise, challenging the model to align with an objectively incorrect statement.
* **Authority Appeal**: Invokes a simulated authoritative persona (e.g., an expert or a supervisor) to dismiss the model's reasoning as incorrect or amateurish, leveraging perceived hierarchy to induce doubt.
* **Emotional Pressure**: Utilizes charged linguistic cues conveying frustration or stern disappointment to undermine the model's confidence and pressure it into conforming to the user's erroneous narrative.

