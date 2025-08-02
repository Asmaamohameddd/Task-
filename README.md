# Electric Device Assistant

This project builds a pipeline to convert electric appliance PDFs (TVs, fridges, ACs, etc.) into Q&A datasets, fine-tune LLaMA3, and serve responses via a Streamlit chatbot.


## Pipeline Overview

1. **Scraping/Collection**: Gather PDFs of device catalogs from web or local storage.
2. **Data Extraction**: Extract structured text using PDF parsers .
3. **QA Conversion**: Convert device specs to question/answer pairs using prompts and llm model(llama 3.1 8b).
4. **Model Fine-Tuning**: Fine-tune `LLaMA3-8B` on QA pairs with LoRA.
5. **Evaluation**: Evaluate the model with ROUGE, BLEU, latency, throughput.
6. **Deployment**: Streamlit-based chatbot hosted locally and via HuggingFace Spaces
   
             |
## Evaluation Results

| **Metric**       | **Baseline Model** | **Fine-tuned Model (`llama3-electric`)** |
|------------------|--------------------|------------------------------------------|
| **ROUGE-1**      | 0.114              | **0.148**                                |
| **ROUGE-2**      | 0.031              | **0.050**                                |
| **BLEU**         | 1.05               | **1.22**                                 |
| **Latency (s)**  | 0.027              | **0.024**                                |
| **Throughput**   | 37.26 qps          | **41.71 qps**                            |

>  The fine-tuned model `Asmaamaghraby/llama3-electric` shows noticeable improvement across all evaluation metrics compared to the base model.
