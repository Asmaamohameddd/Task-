# Electric Device Assistant

This project builds a pipeline to convert electric appliance PDFs (TVs, fridges, ACs, etc.) into Q&A datasets, fine-tune LLaMA3, and serve responses via a Streamlit chatbot.


## Pipeline Overview

1. **Scraping/Collection**: Gather PDFs of device catalogs from web or local storage.
2. **Data Extraction**: Extract structured text using PDF parsers .
3. **QA Conversion**: Convert device specs to question/answer pairs using prompts and llm model(llama 3.1 8b).
4. **Model Fine-Tuning**: Fine-tune `LLaMA3-8B` on QA pairs with LoRA.
5. **Evaluation**: Evaluate the model with ROUGE, BLEU, latency, throughput.
6. **Deployment**: Streamlit-based chatbot hosted locally and via HuggingFace Spaces.
