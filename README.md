# Unsloth Fine-Tuning Repository

This repository contains notebooks for fine-tuning language models using [Unsloth](https://github.com/unslothai/unsloth), a library that enables 2-5x faster and 80% less memory usage for LLM fine-tuning.

## 📚 Notebooks

### 1. Number Combination Prediction Fine-tuning
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tkim/unsloth-fine-tuning/blob/main/fine_tuning_mb.ipynb)

**File:** `fine_tuning_mb.ipynb`

This notebook demonstrates fine-tuning a language model for predicting number combinations using CSV data.

**Features:**
- Loads training data from CSV format (`/data/training-data-1.csv`)
- Uses Phi-3-mini-4k model with 4-bit quantization
- Implements LoRA (Low-Rank Adaptation) for efficient fine-tuning
- Optimized for Google Colab with GPU support
- Exports model in GGUF format for deployment

**Use Case:** Ideal for tasks involving pattern recognition in numerical sequences, lottery number prediction, or any sequential number generation tasks.

### 2. Qwen3 4B Number Prediction Fine-tuning
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tkim/unsloth-fine-tuning/blob/main/Qwen3_4B.ipynb)

**File:** `Qwen3_4B.ipynb`

This notebook demonstrates fine-tuning the Qwen3 4B model for number combination prediction using CSV data.

**Features:**
- Uses the Qwen3 4B parameter model with 4-bit quantization
- Supervised fine-tuning for number sequence prediction
- Takes all 6 numbers (5 lottery numbers + mega ball) as input
- Predicts all 6 numbers as output
- Memory-efficient training with LoRA
- Optimized training parameters for Colab environment

## 🚀 Getting Started

### Prerequisites
- Google Colab account (free tier works with T4 GPU)
- Basic understanding of Python and machine learning concepts
- Training data in appropriate format

### Quick Start
1. Click on the "Open in Colab" button for the notebook you want to use
2. In Colab, go to `Runtime` > `Change runtime type` and select `GPU` (T4 recommended)
3. Run all cells in sequence

### Local Setup
If you want to run locally:

```bash
# Clone the repository
git clone https://github.com/tkim/unsloth-fine-tuning.git
cd unsloth-fine-tuning

# Install dependencies
pip install unsloth trl peft accelerate bitsandbytes pandas numpy torch
```

## 📊 Data Format

### For Number Prediction (fine_tuning_mb.ipynb)
The CSV file should have the following structure:
```csv
input,output
"12, 34, 56, 78, 90","15, 37, 59, 81, 93"
"5, 10, 15, 20, 25","30, 35, 40, 45, 50"
```

- `input`: Historical number combinations (comma-separated)
- `output`: Target/predicted number combinations

## 🛠️ Key Technologies

- **Unsloth**: Fast and memory-efficient LLM fine-tuning
- **LoRA**: Parameter-efficient fine-tuning technique
- **4-bit Quantization**: Reduces model size while maintaining performance
- **GGUF Format**: Efficient model format for deployment
- **TRL (Transformer Reinforcement Learning)**: Training utilities
- **PEFT (Parameter-Efficient Fine-Tuning)**: Efficient adaptation methods

## 📈 Performance Tips

1. **GPU Selection**: T4 (free tier) works well, but A100 provides better performance
2. **Batch Size**: Adjust based on your GPU memory (2-4 for T4, higher for better GPUs)
3. **Learning Rate**: Default is 2e-4, but experiment based on your dataset
4. **Epochs**: Start with 3 epochs and adjust based on validation performance

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- [Unsloth AI](https://unsloth.ai/) for the amazing optimization library
- Google Colab for providing free GPU resources
- The open-source community for continuous improvements

## 📞 Contact

For questions or suggestions, please open an issue in this repository.

---
⭐ If you find this repository helpful, please consider giving it a star!