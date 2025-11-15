# EfficientLengthCollator – Dalia Ragab 🚀

This repository demonstrates **In-Batch Dynamic Sorting** for NLP tokenization using Transformers.  
By sorting sentences in a batch by length, padding is minimized, reducing GPU memory usage and speeding up inference/training.

## Key Highlights
- Real benchmark: 2000 examples, BERT-base  
- **45%+ GPU memory saved**  
- **67% faster inference**  
- Includes plots for memory & time comparisons  
- Live Gradio demo: [nlp-speedup-demo](https://huggingface.co/spaces/dalia18-11/nlp-speedup-demo)

## Dependencies
```bash
torch >= 2.0
transformers >= 4.30
datasets >= 2.14
matplotlib >= 3.7
tqdm >= 4.65
gradio >= 5.49
