# Ember Lu - Conflation With LLMs

This project is exploring the use of small, scalable LLMs and static embedding models for the purpose of location conflation, or the matching of geographic locations, based on location metadata provided by Overture Maps Foundation. 

# Objectives ✅ 

Current models being investigated are Google's Electra, Meta’s Llamas, and Microsoft’s Phi-3 Mini, moving to static embedding models like Meta’s SONAR.

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
11/19/2025
Accuracy for each model being investigated has significantly increased. Phi-3 Mini is producing a preliminary overall accuracy of **60.1%**. Llama 3.2 is producing an overall accuracy of **53.6%**. Instead of using a CausalLM such as Qwen3-2507, it has been replaced with a smaller, sequence classifier model, Google's Electra model that is producing an overal acuracy of **70.1%**.
