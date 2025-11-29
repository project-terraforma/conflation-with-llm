# 🌎 Ember Lu - Conflation With LLMs

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

- ⭐ **Best Price-to-Performance — Meta Llama 3.2**
  - Accuracy: 89%
  - Precision: 0.901
  - Recall: 0.922
  - F1 Score: 0.912
  - Pricing: $0.06 per 1M tokens
  - Avg. Tokens / Request: 165
  - Avg. Time / Request: 6.34 ms


## 🎯 Objectives ✅
Models being benchmarked are Meta’s Llama 3.2, Microsoft’s Phi-3 Mini, and Google's Electra.

OKRs are 100% met. Target metrics calculated/measured are:
* ✅ 50%+ ratio of true positive/negative to false positive/negative place matches (matplotlib)
* ✅ Target > 50% Precision and > 50% Recall accuracy calculations
* ✅ F1 Score > 80%
* ✅ Pricing per request (<$1.25/1M tokens)
* ✅ Time per request (around or <1sec)

For contextual performance, the current target metrics measuring the accuracy across different features include: categories, base_emails, websites, addresses, and no exclusions.

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

# Running the Notebook (Models.ipynb)
1. Run: Cell 1 uses pip to install all necessary libraries: transformers, accelerate, torch, hugging_face
2. Run: Cell 2 imports the necessary methods from Hugging Face for the models selected
3. Choose a model to use, and scroll to the cell underneath the model's name labeled. Run the cell.
* NOTE: For the Llama 3.2, login into HuggingFace is required first, with permissions needed for access to the model by the HF Llama moderators.
4. Scroll down to Training Models, and run the cell directly underneath its label. This trains
the model with our training data, part of the 3K data points in the parquet.
* NOTE: For the Llama 3.2, the first two lines of code in the Training Models cell need to be uncommented (sets a necessary parameter for the tokenizer). For other models, comment out those lines.
5. Scroll down to Evaluation Data, and run the three cells directly underneath its label. This lists
accuracy metrics, tokens, precision, recall, F1 score, etc. 


## 📊 Status  (Updated: 11/28/2025)
OKRs are 100% met! ✅ Phi-3 Mini has the best performance, but Llama 3.2 has nearly identical performance with 2x faster speed and half the price as the Phi-3 Mini. Current recommendation is the Llama 3.2.

Phi-3 Mini as an LLM-> Sequence Classifier is producing a overall accuracy of **90.4%**. 
Llama 3.2 as an LLM -> Sequence Classifier is producing an overall accuracy of **89%**. 
Google's Electra as a static embedding model is producing an overall acuracy of **85.7%**. 
(see more metrics below and in results/context_results.md)

## 📈 Metrics
| Model                  | Accuracy | Precision | Recall | F1 Score | Pricing (USD)     | Avg. Tokens / Request | Avg. Time / Request |
|------------------------|:--------:|:---------:|:------:|:--------:|--------------------|------------------------|----------------------|
| **Microsoft Phi-3 Mini** | 90.4% | 0.929 | 0.915 | 0.921 | $0.13 / 1M tokens   | 215 tokens             | 15.5 ms           |
| **Meta Llama 3.2**       | 89%   | 0.901 | 0.922 | 0.912 | $0.06 / 1M tokens   | 165 tokens             | 6.34 ms           |
| **Google Electra**       | 85.7% | 0.896 | 0.870 | 0.883 | Free (Open Source)  | 233 tokens             | 4.57 ms           |


