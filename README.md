# Ember Lu - Conflation With LLMs

This project is exploring the use of small, scalable LLMs and static embedding models for the purpose of location conflation, or the matching of geographic locations, based on location metadata provided by Overture Maps Foundation. 

# Objectives ✅ 

Current models being invested are Alibaba’s Qwen3-2507, Meta’s Llamas, and Microsoft’s Phi-3 Mini, moving to static embedding models like Meta’s SONAR.

Target metrics are:
* <1K tokens per request
* 50%+ ratio of true positive/negative to false positive/negative place matches (matplotlib)
* Target > 50% Precision and > 50% Recall accuracy calculations
* Time per request (around or <1sec)
* Pricing per request (I/O: <$1.25/1M tokens & <$10/1M tokens)

For contextual performance, the current target metrics measuring the accuracy across different features include:
* categories
* base_emails
* websites
* addresses

Libraries: DSPy, Hugging Face transformers

# Status
11/2/2025
The foundations for all three LLM models created and set up. Currently trying to reduce time for model requests, in addition to implementing SONAR and additional static embedding models. Switched to Google Colab to take advantage of their GPU capabilities for running the models on torch/cuda, as running on CPUs is too slow. The test system prompt is for the models to describe themselves. 

# Findings
11/2/2025
QWEN3-2507-Instruct is taking the longest amount of time to load and respond to even the simplest system prompts. Phi 3 shows promising results, responding quickly to the test system prompt. 
