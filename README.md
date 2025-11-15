# EfficientLengthCollator – Dalia Ragab 🚀

This repository demonstrates **In-Batch Dynamic Sorting** for NLP tokenization using Transformers.  
By sorting sentences in a batch by length, padding is minimized, reducing GPU memory usage and speeding up inference/training.

## Key Highlights
- Real benchmark: 2000 examples, BERT-base  
- **45%+ GPU memory saved**  
- **67.9% faster inference**  
- Includes plots for memory & time comparisons  
- Live Gradio demo: [efficient-collator-demo](https://huggingface.co/spaces/dalia18-11/efficient-collator-demo)

![Benchmark Plot](benchmark_plot.png)

## Dependencies
