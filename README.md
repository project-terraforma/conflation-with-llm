# Ember Lu - Conflation With LLMs

This project is exploring the use of small, scalable LLMs and static embedding models for the purpose of location conflation, or the matching of geographic locations, based on location metadata provided by Overture Maps Foundation.

## 🗻 Result Highlights
- **Best Overall Accuracy — Microsoft Phi-3 Mini**
  - Accuracy: 90.4%
  - Precision: 0.929
  - Recall: 0.915
  - F1 Score: 0.921
  - Pricing: $0.13 per 1M tokens
  - Avg. Tokens / Request: 215
  - Avg. Time / Request: 15.5 ms

- **Best Price-to-Performance Model — Meta Llama 3.2**
  - Accuracy: 89%
  - Precision: 0.901
  - Recall: 0.922
  - F1 Score: 0.912
  - Pricing: $0.06 per 1M tokens
  - Avg. Tokens / Request: 165
  - Avg. Time / Request: 6.34 ms


## 🎯 Objectives ✅

Models being benchmarked are Meta’s Llama 3.2, Microsoft’s Phi-3 Mini, and Google's Electra.

Target metrics are:
* ✅ 50%+ ratio of true positive/negative to false positive/negative place matches (matplotlib)
* ✅ Target > 50% Precision and > 50% Recall accuracy calculations
* ✅ F1 Score > 80%
* ✅ Pricing per request (I/O: <$1.25/1M tokens & <$10/1M tokens)
* ✅ Time per request (around or <1sec)

For contextual performance, the current target metrics measuring the accuracy across different features include:
* ✅ categories
* ✅ base_emails
* ✅ websites
* ✅ addresses
* ✅ no exclusions

Libraries: Hugging Face transformers, Torch

## 🛠️ Method Overview
- **Transformers (Hugging Face):** Loaded and configured the models and tokenizer for sequence classification.  
- **Pandas:** Read the dataset from Parquet format and removed unneeded fields.  
- **scikit-learn:** Created training and testing splits.
- **PyTorch:** Converted all inputs into tensors for model training and evaluation. Imported models from Hugging Face, which by default are PyTorch models.
- **matplotlib:** Visualized all models' accuracy/performance metrics with contextual performance

## 🏢 Repo Organization
> ```
> CONFLATION-WITH-LLM/
> ├── code/
> │   ├── MetricVisualization.ipynb        # Metric Graph Generation
> │   └── Models.ipynb                     # Model Training & Evaluation
> │
> ├── data/
> │   └── samples_3k_project_c_updated.parquet   # Dataset (3,000 samples)
> │
> └── results/
>     ├── metric_graphs/                   # Metric Visualizations over Contextual Performance 
>     │   ├── accuracy.png
>     │   ├── f1.png
>     │   ├── precision.png
>     │   ├── recall.png
>     │   ├── tn_to_fn_ratio.png
>     │   └── tp_to_fp_ratio.png
>     │
>     └── context_results.md               # Metric Summary and Context Analysis
> ```


## 📊 Status  
11/28/2025  
Phi-3 Mini as an LLM-> Sequence Classifier is producing a  overall accuracy of **90.4%**. Llama 3.2 as an LLM -> Sequence Classifier is producing an overall accuracy of **89%**. Google's Electra as a static embedding model is producing an overall acuracy of **85.7%**. OKRs are 100% met! ✅

## 📈 Metrics
| Model                  | Accuracy | Precision | Recall | F1 Score | Pricing (USD)     | Avg. Tokens / Request | Avg. Time / Request |
|------------------------|:--------:|:---------:|:------:|:--------:|--------------------|------------------------|----------------------|
| **Microsoft Phi-3 Mini** | 90.4% | 0.929 | 0.915 | 0.921 | $0.13 / 1M tokens   | 215 tokens             | 15.5 ms           |
| **Meta Llama 3.2**       | 89%   | 0.901 | 0.922 | 0.912 | $0.06 / 1M tokens   | 165 tokens             | 6.34 ms           |
| **Google Electra**       | 85.7% | 0.896 | 0.870 | 0.883 | Free (Open Source)  | 233 tokens             | 4.57 ms           |


