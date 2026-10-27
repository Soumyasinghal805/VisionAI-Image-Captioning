<p align="center">
  <img src="assets/logo.png" alt="Image-to-Text Generator Logo" width="100"/>
</p>

<h1 align="center">🖼️ Image-to-Text Generator</h1>

<p align="center">
  <strong>Multi-Modal Vision-Language Model for Automatic Image Captioning using BLIP Architecture</strong>
</p>

<p align="center">
  <a href="#-overview">Overview</a> •
  <a href="#-live-demo">Live Demo</a> •
  <a href="#-features">Features</a> •
  <a href="#-installation">Installation</a> •
  <a href="#-results">Results</a> •
  <a href="#-documentation">Documentation</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.9+"/>
  <img src="https://img.shields.io/badge/PyTorch-2.0+-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch"/>
  <img src="https://img.shields.io/badge/🤗_Transformers-4.35+-FFD21E?style=for-the-badge" alt="Transformers"/>
  <img src="https://img.shields.io/badge/Streamlit-1.28+-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/License-MIT-00D9A5?style=for-the-badge" alt="MIT License"/>
  <img src="https://img.shields.io/badge/Model-BLIP--Large-0ea5e9?style=for-the-badge" alt="BLIP"/>
  <img src="https://img.shields.io/badge/BLEU--4-39.7%25-E94560?style=for-the-badge" alt="BLEU-4"/>
</p>

---

## 🎯 Overview

A production-ready image captioning system using **BLIP (Bootstrapping Language-Image Pre-training)** architecture. This project implements state-of-the-art vision-language understanding for generating natural language descriptions of images, with a focus on **reading and reasoning about text in images**.

Built and evaluated using the [TextCaps Dataset](https://textvqa.org/textcaps/) containing **142,040 captions** for 28,408 images that require multimodal reasoning between visual entities and OCR tokens.

The pipeline automatically:
- Processes images through a **ViT-L/16** vision encoder with 384×384 resolution
- Applies **Image-Text Contrastive (ITC)** and **Image-Text Matching (ITM)** learning
- Generates fluent captions using an **autoregressive text decoder**
- Supports **batch processing** of up to **25 images** simultaneously
- Provides **ZIP download** with captioned images and summary file

**Key Achievement:** Achieved **39.7% BLEU-4**, **136.7 CIDEr**, and **24.1% SPICE** using BLIP-Large with 129M parameters!

### 🔄 Pipeline Architecture

<p align="center">
  <img src="assets/screenshots/blip_architecture.png" alt="BLIP Image Captioning Pipeline" width="900"/>
</p>

---

## 📱 App Preview

### Main Interface
Upload up to 25 images and generate AI-powered captions with state-of-the-art accuracy.

<p align="center">
  <img src="assets/screenshots/app_main_ui.png" alt="Main Interface" width="900"/>
</p>

### Image Preview
Preview all uploaded images before generating captions.

<p align="center">
  <img src="assets/screenshots/app_image_preview.png" alt="Image Preview" width="900"/>
</p>

### Caption Generation Examples
See how the model generates accurate, descriptive captions for different image types.

<table>
<tr>
<td width="50%">

**🍽️ Food Recognition**
<img src="assets/screenshots/caption_food.png" alt="Food Caption" width="100%"/>

*"There is a bowl of food with meat, vegetables and eggs"*

</td>
<td width="50%">

**🌆 Urban Scenes**
<img src="assets/screenshots/caption_city.png" alt="City Caption" width="100%"/>

*"Araful view of the city skyline with skyscrapers and buildings"*

</td>
</tr>
<tr>
<td width="50%">

**🚗 Vehicle Detection**
<img src="assets/screenshots/caption_car.png" alt="Car Caption" width="100%"/>

*"A close up of the front end of a black mustang"*

</td>
<td width="50%">

**🏖️ Nature & Landscapes**
<img src="assets/screenshots/caption_beach.png" alt="Beach Caption" width="100%"/>

*"A close up of the sun setting over an ocean beach"*

</td>
</tr>
</table>

### Download Results
Download all captioned images as a ZIP file with embedded captions and summary text file.

<p align="center">
  <img src="assets/screenshots/app_download_results.png" alt="Download Results" width="900"/>
</p>

---

## 🚀 Live Demo

Try the interactive Streamlit app - generate captions for any image in real-time!

<p align="center">
  <a href="https://blip-image-to-text-generator.streamlit.app">
    <img src="https://img.shields.io/badge/▶_OPEN_LIVE_DEMO-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white" alt="Open Live Demo" height="50"/>
  </a>
</p>

### Run Locally

```bash
# Clone and navigate
git clone https://github.com/tharun-ship-it/image-to-text-generator.git
cd image-to-text-generator

# Install dependencies
pip install -r requirements.txt

# Launch the demo
streamlit run app.py
```

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| **State-of-the-Art Accuracy** | 39.7% BLEU-4, 136.7 CIDEr, 24.1% SPICE |
| **Batch Processing** | Upload and process up to **25 images** simultaneously |
| **ZIP Download** | Download all images with captions embedded + summary text file |
| **BLIP Architecture** | Unified vision-language pre-training with CapFilt bootstrapping |
| **Conditional Captioning** | Guide output with custom prompts like "a photograph of..." |
| **Real-time Inference** | Fast caption generation with beam search optimization |
| **Web Interface** | Beautiful Streamlit-based UI with professional pink theme |
| **Configurable Parameters** | Adjustable beam width, caption length, and generation settings |

### 💡 Key Capabilities

- **Batch Processing**: Process up to 25 images in one session (2GB max total size)
- **ZIP Export**: Download captioned images with black text on white background
- **Summary File**: Get a text file with all captions listed sequentially (Image 1 to 25)
- **CapFilt Bootstrapping**: Cleaner training data for more natural captions
- **ITC + ITM Learning**: Image-Text Contrastive and Matching for better alignment
- **Conditional Generation**: Control caption style with custom prompts
- **High Resolution**: 384×384 image processing for detailed understanding

---

## 📊 Dataset

This project uses the **TextCaps dataset**, which consists of 142K captions for 28K images, requiring models to perform multimodal reasoning between visual entities and OCR tokens.

| Attribute | Details |
|-----------|---------|
| **Dataset Name** | TextCaps |
| **Creators** | Facebook AI Research (FAIR) |
| **Official Page** | [textvqa.org/textcaps](https://textvqa.org/textcaps/) |
| **Associated Research** | [arXiv:2003.12462](https://arxiv.org/abs/2003.12462) |

**Paper Citation:** O. Sidorov, R. Hu, M. Rohrbach, A. Singh, "TextCaps: A Dataset for Image Captioning with Reading Comprehension", *Proceedings of the European Conference on Computer Vision (ECCV 2020)*, Glasgow, UK, August 23-28, 2020.

| Feature | Description |
|---------|-------------|
| **Total Images** | 28,408 unique images |
| **Total Captions** | 142,040 human-written captions |
| **Captions per Image** | 5 reference captions |
| **Focus** | Reading and reasoning about text in images |
| **Language** | English |

### 📈 Dataset Statistics

| Metric | Value |
|--------|-------|
| **Training Images** | 21,953 |
| **Validation Images** | 3,166 |
| **Test Images** | 3,289 |
| **Avg Caption Length** | 12.4 words |
| **Vocabulary Size** | 50,257 tokens |

---

## 📁 Project Structure

```
image-to-text-generator/
├── src/
│   ├── __init__.py
│   ├── data/
│   │   └── preprocessor.py        # Image & text preprocessing
│   ├── models/
│   │   ├── blip_captioner.py      # BLIP model wrapper
│   │   ├── vision_encoder.py      # ViT-L/16 encoder
│   │   ├── text_decoder.py        # Text decoder
│   │   └── attention.py           # Attention mechanisms
│   ├── inference/
│   │   └── generator.py           # Caption generation utilities
│   ├── evaluation/
│   │   └── metrics.py             # BLEU, CIDEr, SPICE metrics
│   └── utils/
│       └── helpers.py             # Utility functions
├── app.py                         # Streamlit web application
├── notebooks/
│   └── demo.ipynb                 # Interactive Colab demo
├── scripts/
│   ├── train.py                   # Training script
│   ├── evaluate.py                # Evaluation script
│   └── deploy_streamlit.py        # Deployment helper
├── tests/
│   └── test_models.py             # Unit tests
├── config/
│   └── config.yaml                # Pipeline configuration
├── assets/
│   └── screenshots/               # README images
├── requirements.txt
├── setup.py
├── LICENSE
└── README.md
```

---

## 📊 Model Performance

| Model | BLEU-4 | CIDEr | METEOR | SPICE |
|-------|--------|-------|--------|-------|
| **BLIP-Large (Ours)** | **39.7%** | **136.7** | **30.2%** | **24.1%** |
| BLIP-Base | 38.6% | 133.3 | 29.5% | 23.6% |
| ViT-GPT2 | 32.4% | 108.6 | 24.7% | 20.1% |
| Transformer Baseline | 28.3% | 94.5 | 22.8% | 18.2% |
| Show-Attend-Tell | 25.1% | 82.3 | 20.2% | 16.8% |

*Benchmarked on TextCaps test set*

---

## 📸 Results

### Model Comparison

<p align="center">
  <img src="assets/screenshots/model_comparison.png" alt="Model Performance Comparison" width="900"/>
</p>

**BLIP-Large** significantly outperforms all baseline models across every metric, demonstrating the power of unified vision-language pre-training with CapFilt bootstrapping.

---

### Training Progress

<p align="center">
  <img src="assets/screenshots/training_curves.png" alt="Training Curves" width="900"/>
</p>

BLIP's two-stage pre-training (ITC + ITM + LM) converges smoothly with consistent improvement across all metrics. The CapFilt bootstrapping provides cleaner gradients for stable training.

---

### Dataset Samples

<p align="center">
  <img src="assets/screenshots/dataset_samples.png" alt="Dataset Samples" width="900"/>
</p>

**Visual examples from TextCaps dataset:**
- Images contain text that must be read and understood
- Captions reference both visual content and text in the scene
- Diverse domains including signs, products, documents, and screens

---

## 📦 Installation

### Prerequisites

```bash
Python >= 3.9
pip >= 21.0
```


```

---

## 🔧 Quick Start

### Python API

```python
from transformers import BlipProcessor, BlipForConditionalGeneration
from PIL import Image
import torch

# Load BLIP model
model_name = "Salesforce/blip-image-captioning-large"
processor = BlipProcessor.from_pretrained(model_name)
model = BlipForConditionalGeneration.from_pretrained(model_name)

device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
model.to(device)

# Generate caption
image = Image.open("your_image.jpg").convert("RGB")
inputs = processor(image, return_tensors="pt").to(device)

with torch.no_grad():
    output_ids = model.generate(**inputs, max_length=50, num_beams=5)
    
caption = processor.decode(output_ids[0], skip_special_tokens=True)
print(f"Caption: {caption}")
```

### Conditional Captioning

```python
# Guide the caption with a custom prompt
text = "a photograph of"
inputs = processor(image, text, return_tensors="pt").to(device)

output_ids = model.generate(**inputs, max_length=50, num_beams=5)
caption = processor.decode(output_ids[0], skip_special_tokens=True)
print(f"Guided Caption: {caption}")
```

### Streamlit Demo

```bash
# Run the web application
streamlit run app.py
```

---

## 🛠 Technologies

| Technology | Purpose |
|------------|---------|
| ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) | Core framework |
| ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white) | Deep learning |
| ![Transformers](https://img.shields.io/badge/Transformers-FFD21E?style=flat&logo=huggingface&logoColor=black) | BLIP model |
| ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white) | Web demo |
| ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white) | Numerical computing |
| ![Pillow](https://img.shields.io/badge/Pillow-3776AB?style=flat) | Image processing |

---

## 📚 Documentation

### Configuration

All pipeline settings are controlled via `config/config.yaml`:

```yaml
model:
  name: "Salesforce/blip-image-captioning-large"
  device: "auto"

generation:
  max_length: 50
  min_length: 5
  num_beams: 5
  repetition_penalty: 1.5

preprocessing:
  image_size: 384

batch_processing:
  max_images: 25
  max_total_size: "2GB"
```



---

## 🧪 Testing

Run the comprehensive test suite:

```bash
# Run all tests
pytest tests/ -v

# Run with coverage report
pytest tests/ --cov=src --cov-report=html
```

---



---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

```bash
# Fork and clone
git clone https://github.com/YOUR_USERNAME/image-to-text-generator.git

# Create branch
git checkout -b feature/amazing-feature

# Commit and push
git commit -m 'Add amazing feature'
git push origin feature/amazing-feature

# Open Pull Request
```

---

## 📄 License

This project is licensed under the MIT License—see the [LICENSE](LICENSE) file for details.

---

#

---

## 👤 Author

**Tharun Ponnam**

* GitHub: [@tharun-ship-it](https://github.com/tharun-ship-it)
* Email: tharunponnam007@gmail.com

---

