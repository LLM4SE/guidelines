# Threats of Using LLMs in Software Engineering

This repository contains some community guidelines for LLM Providers & SE researchers.

# Guidelines for LLM Providers

## Closed-Source Models

### Enhance Model Transparency

LLM providers should prioritize transparency by providing comprehensive information about their models. This should include details on the model's creation process, methodology for data selection during training, and statistics related to the training dataset. Establishing an API service is encouraged to allow users to verify if specific data sources were included in the model's training or validation datasets, enhancing transparency, privacy, and copyright verification.

### Use Versioning Information

Providers should supply their model version and adopt a versioning nomenclature distinguishing major revisions from minor updates. This enables users to understand the significance of model version changes.

## Data Leakage

In addressing concerns about closed-source models, LLM providers should offer services allowing researchers to verify which projects and sources were considered during pre-training.

## Reproducibility

### Use a Fixed Random Seed

LLM providers should ensure the inclusion of a settable random seed during LLM inference. This deterministic approach guarantees consistent results for a given prompt when coupled with a specific fixed random seed. For closed-source LLMs, providing a dedicated API to set the seed without requiring access to the entire model is recommended.

### Use an Archiving System

In addition to versioning information, we advocate for the use of a general archiving system. This ensures accessibility to various LLM versions, facilitating evaluation and assessment of performance characteristics over time. Existing platforms like HuggingFace and Zenodo serve as examples, but a dedicated platform for LLMs is still needed.

# Guidelines for SE Researchers

## Closed-Source Models

### Perform Comparative Analysis

Researchers are encouraged to conduct experiments using both open-source and closed-source LLMs. This comparative approach provides insights into the strengths and limitations of each. Frameworks such as ONNX can be leveraged to streamline the evaluation process across multiple models.

## Data Leakage

To address concerns about potential data leakage:

### Assess LLMs on Metamorphic Data

Use metamorphic testing to generate new data samples and assess LLM robustness. Researchers should complement performance analysis with data samples generated through metamorphic testing, aligning transformations with the specific task.

### Use Different Sources

Gather software projects and data from multiple sources to mitigate the impact of potential data leakage.

### Code Clone Detection

Utilize code clone detection techniques to check if generated code is similar to code found in online repositories.

### Check for Common Dependencies

Cross-compare external dependencies between projects belonging to different sets and use code cloning techniques to assess similarities.

## Reproducibility

### Assess Output Variability

Conduct multiple replication runs and use variability metrics during the evaluation to address output variability.

### Provide Execution Metadata

Include relevant additional data such as model information, prompts, date of LLM query, output variability metrics, and the scope of reproducibility in the evaluation.

### Use an Archiving System

In addition to versioning information, advocate for the use of a general archiving system to ensure external parties can reproduce observations made by LLMs. Existing platforms like HuggingFace and Zenodo can be referenced, but a dedicated platform for LLMs is still needed, incorporating functionality for specifying and associating execution metadata.
