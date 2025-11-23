# Ember Lu - Conflation With LLMs

This project is exploring the use of small, scalable LLMs and static embedding models for the purpose of location conflation, or the matching of geographic locations, based on location metadata provided by Overture Maps Foundation.

## Objectives ✅

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

Libraries: Hugging Face transformers

## Status  
11/22/2025  
Accuracy for each model being investigated has significantly increased. Phi-3 Mini is producing a preliminary overall accuracy of **60.1%**->**93%**. Llama 3.2 is producing an overall accuracy of **53.6%**->**60.1%**. Instead of using a CausalLM such as Qwen3-2507, it has been replaced with a smaller, sequence classifier model, Google's Electra model that is producing an overal acuracy of **70.1%**.

## Metrics

### Phi-3 Mini
* Accuracy: 93.2%
* True Positives : False Positives Ratio - 18.103
* True Negatives : False Negatives Ratio - 9.8125
* Precision: 0.948
* Recall: 0.943
* F1 Score: 0.945

### Llama 3.2
* Accuracy: 60.1%
* True Positives : False Positives Ratio - 3.735
* True Negatives : False Negatives Ratio - 1.047
* Precision: 0.7888
* Recall: 0.721
* F1 Score: 0.753

### Electra
* Accuracy: 83.5%
* True Positives : False Positives Ratio - 4.894
* True Negatives : False Negatives Ratio - 5.407
* Precision: 0.830
* Recall: 0.895
* F1 Score: 0.861
