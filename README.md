# 🌍 Ember Lu - Conflation With LLMs

This project is exploring the use of small, scalable LLMs and static embedding models for the purpose of location conflation, or the matching of geographic locations, based on location metadata provided by Overture Maps Foundation.

## 🎯 Objectives ✅

Current models being investigated are Google's Electra, Meta’s Llamas, and Microsoft’s Phi-3 Mini, moving to static embedding models like Meta’s SONAR.

Target metrics are:
* ✅ 50%+ ratio of true positive/negative to false positive/negative place matches (matplotlib)
* ✅ Target > 50% Precision and > 50% Recall accuracy calculations
* ✅ F1 Score > 80%
* ✅ Pricing per request (I/O: <$1.25/1M tokens & <$10/1M tokens)
* Time per request (around or <1sec)

For contextual performance, the current target metrics measuring the accuracy across different features include:
* ✅ categories
* ✅ base_emails
* ✅ websites
* ✅ addresses
* ✅ no exclusions

Libraries: Hugging Face transformers, Torch

## 📊 Status  
11/22/2025  
Accuracy for each model being investigated has significantly increased. Phi-3 Mini is producing a preliminary overall accuracy of **60.1%**->**90.4%**. Llama 3.2 is producing an overall accuracy of **53.6%**->**89%**. Instead of using a CausalLM such as Qwen3-2507, it has been replaced with a smaller, sequence classifier model, Google's Electra model that is producing an overall acuracy of **70.1%**->**85.7%**.

## 📈 Metrics
### 🧠 Microsoft's Phi-3 Mini
**Accuracy:** 90.4%  
- **TP : FP Ratio:** 13.0  
- **TN : FN Ratio:** 6.532
- **Precision:** 0.929
- **Recall:** 0.915
- **F1 Score:** 0.921

---

### 🦙 Meta's Llama 3.2
**Accuracy:** 89%  
- **TP : FP Ratio:** 9.125  
- **TN : FN Ratio:** 6.744 
- **Precision:** 0.901
- **Recall:** 0.922
- **F1 Score:** 0.912

---

### ⚡ Google's Electra
**Accuracy:** 85.7%  
- **TP : FP Ratio:** 8.607
- **TN : FN Ratio:** 4.028  
- **Precision:** 0.896  
- **Recall:** 0.870 
- **F1 Score:** 0.883