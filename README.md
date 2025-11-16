# EfficientLengthCollator – Dalia Ragab

EfficientLengthCollator implements In-Batch Dynamic Length Sorting, a technique that reduces unnecessary padding inside NLP batches.  
By sorting each batch by sequence length, padding is minimized, leading to lower memory usage and faster inference/training with Transformers models.

---

## Key Features
- Realistic benchmark on 2000 examples (IMDB + SST-2)
- Works with any HuggingFace tokenizer/model
- Supports CPU and GPU peak-memory measurement
- Achieves:
  - 72.3% memory reduction
  - 57.7% speed improvement
- Includes reproducible scripts and benchmark plots
- Live Gradio demo available

---

## Benchmark Results (BERT-base)

| Metric | Default | Efficient | Improvement |
|--------|---------|-----------|-------------|
| Memory | 959 MB | 265 MB | 72.3% saved |
| Time | 186.99s | 79.19s | 57.7% faster |

![Benchmark Plot](benchmark_plot.png)

---

## Installation

Install dependencies:

```bash
pip install torch transformers datasets matplotlib tqdm psutil gradio
```

Requirements:

```
torch >= 2.0
transformers >= 4.30
datasets >= 2.14
matplotlib >= 3.7
tqdm >= 4.65
gradio >= 3.49
psutil >= 5.9
```

---

## How to Run

Run the notebook:

```bash
jupyter notebook main.ipynb
```

Or run the benchmark script:

```bash
python run_benchmark.py
```

---

## Example Usage

```python
from efficient_collator import EfficientLengthCollator
from transformers import AutoTokenizer
from torch.utils.data import DataLoader

tokenizer = AutoTokenizer.from_pretrained("bert-base-uncased")
collator = EfficientLengthCollator(tokenizer)

dataset = [
    tokenizer("This is a short sentence.", truncation=True),
    tokenizer("This is a longer sentence that requires more padding.", truncation=True),
]

loader = DataLoader(dataset, batch_size=2, collate_fn=collator)

for batch in loader:
    print(batch["input_ids"].shape)
```

---

## Live Demo

https://huggingface.co/spaces/dalia18-11/efficient-collator-demo

---

## Contact

Developed by Dalia Ragab.  
For questions or contributions, please open an issue or pull request.

---

## Support

If you find this project useful, consider starring the repository.
