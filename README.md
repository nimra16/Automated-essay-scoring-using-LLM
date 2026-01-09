# Automated Essay Scoring Using Large Language Models

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Paper](https://img.shields.io/badge/Paper-Submitted-orange.svg)](https://github.com/nimra16/Automated-essay-scoring-using-LLM)

This repository contains the implementation code for the research paper:

**"Exploring Potential of Large Language Models for Automated Essay Scoring in Education"**

*Submitted for review*

## 📋 Overview

This study explores the potential of Large Language Models (LLMs), specifically **GPT-3.5-turbo** and **Google Gemini-Pro**, for Automated Essay Scoring (AES) and comprehensive feedback provision. Unlike traditional AES systems that rely on fine-tuning, this work investigates the **zero-shot learning capabilities** of LLMs, making the approach highly scalable and efficient.

## 📊 Datasets

### Benchmark Datasets

1. **ASAP-AES (Hewlett Foundation)**
   - Publicly available benchmark dataset for automated essay scoring
   - Source: [Kaggle ASAP-AES Competition](https://www.kaggle.com/competitions/asap-aes/data)
   - Contains essays from students across various academic levels and disciplines
   - Six different essay sets with varying prompts and scoring rubrics

2. **LA-AES (Learning Agency Lab - Automated Essay Scoring 2.0)**
   - Source: [Kaggle LA-AES Competition](https://www.kaggle.com/competitions/learning-agency-lab-automated-essay-scoring-2)
   - Focuses on holistic essay quality assessment
   - 30% stratified random sample used for evaluation (maintaining score distribution)
   - Score range: 1-4

### Real-World Dataset

**O-Levels English Class (Subject Code: 1123)**
- 21 student essays from Sukkur IBA Community College, Pakistan
- Multiple writing domains: informal writing, report writing, narrative, and descriptive writing
- Evaluated by two independent domain experts
- Used to investigate human assessor subjectivity and fatigue


## 🚀 Getting Started

### Prerequisites

```bash
Python 3.9+
OpenAI API key
Google Gemini API key
```

### Installation

```bash
# Clone the repository
git clone https://github.com/nimra16/Automated-essay-scoring-using-LLM.git
cd Automated-essay-scoring-using-LLM

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Environment Setup

Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your_openai_api_key_here
GEMINI_API_KEY=your_gemini_api_key_here
```

### Usage

```bash
# Run the automated essay scoring
python app.py

# For specific datasets
python score_essays.py --dataset asap --model gpt
python score_essays.py --dataset la-aes --model gemini
```

## 🌐 Live Demo

Try our web-based GUI for real-time essay scoring and feedback:

**[Live Demo](https://nimra16.pythonanywhere.com/assesment_checker)**

Features:
- Input custom rubrics and essays
- Get instant scores and detailed feedback
- Compare GPT and Gemini performance
- View rubric-aligned suggestions


## 🙏 Acknowledgments

We sincerely thank **Mrs. Sanam Zaryab,** English Lecturer (O-Levels) at Sukkur IBA Community College, and **Mr. Usama Abdul Rehman**, English Lecturer at Sukkur IBA University, for generously providing classroom data and sharing their academic expertise. Their contributions were instrumental to this study on automated essay scoring and human assessment alignment.


### Institutions

- Sukkur IBA University
- Sukkur IBA Community College
- Norwegian University of Science and Technology (NTNU)
- Linnaeus University
- University of Balochistan

## 👥 Authors

- **Nimra Mughal** - Sukkur IBA University
- **Ali Shariq Imran** - Norwegian University of Science and Technology
- **Sher Muhammad Daudpota** - Sukkur IBA University
- **Zenun Kastrati** - Linnaeus University
- **Waheed Noor** - University of Balochistan

## 📄 Citation

If you use this code or findings in your research, please cite:

```bibtex
@article{mughal2024exploring,
  title={Exploring Potential of Large Language Models for Automated Essay Scoring in Education},
  author={Mughal, Nimra and Imran, Ali Shariq and Daudpota, Sher Muhammad and Kastrati, Zenun and Noor, Waheed},
  journal={Under Review},
  year={2024}
}
```

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 Links

- **Live Demo**: [https://nimra16.pythonanywhere.com/assesment_checker](https://nimra16.pythonanywhere.com/assesment_checker)
- **ASAP-AES Dataset**: [Kaggle Competition](https://www.kaggle.com/competitions/asap-aes/data)
- **LA-AES Dataset**: [Kaggle Competition](https://www.kaggle.com/competitions/learning-agency-lab-automated-essay-scoring-2)

## Contact

For questions or collaborations, please contact:
- Nimra Mughal: [nimra@iba-suk.edu.pk](mailto:nimra@iba-suk.edu.pk)

## Data Privacy

This research adheres to strict ethical guidelines:
- All benchmark datasets are publicly available and pre-anonymized
- Real-world student data was anonymized using unique identifiers (e001-e021)
- No personally identifiable information (PII) was transmitted to API providers
- All data handling complies with educational research ethics standards

---

**If you find this research useful, please consider starring this repository!**

*Last Updated: January 2025*
