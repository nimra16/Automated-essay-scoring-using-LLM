# Automated Essay Scoring Using Large Language Models

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Paper](https://img.shields.io/badge/Paper-Submitted-orange.svg)](https://github.com/nimra16/Automated-essay-scoring-using-LLM)

This repository contains the implementation code for the research paper:

**"Exploring Potential of Large Language Models for Automated Essay Scoring in Education"**

*Submitted for review*

## 📋 Overview

This study explores the potential of Large Language Models (LLMs), specifically **GPT-3.5-turbo** and **Google Gemini-Pro**, for Automated Essay Scoring (AES) and comprehensive feedback provision. Unlike traditional AES systems that rely on fine-tuning, this work investigates the **zero-shot learning capabilities** of LLMs, making the approach highly scalable and efficient.

### Key Contributions

1. **Zero-Shot Learning Focus**: Investigates zero-shot capabilities of LLMs for AES without requiring fine-tuning
2. **Comparative Analysis**: Rigorous statistical comparison between GPT-3.5-turbo and Gemini-Pro
3. **Rubric Quality Impact**: Analysis of how rubric complexity affects LLM performance
4. **Human Bias Investigation**: Examines assessor fatigue and cognitive biases in human grading

## 🎯 Research Questions

1. **RQ1**: To what extent do LLM models correlate with human assessors for essay scoring?
2. **RQ2**: What is the LLM's performance as an assessor at varying levels of essay complexity?
3. **RQ3**: To what extent does rubric quality affect the performance of the AES model?

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

## 🔬 Methodology

### Models Used

- **GPT-3.5-turbo** (OpenAI)
- **Gemini-Pro** (Google AI)

### Configuration

- **Temperature**: 0.1 (for deterministic and consistent results)
- **Approach**: Zero-shot learning (no fine-tuning required)
- **Prompt Design**: Persona-based prompts with explicit rubric guidelines

### Evaluation Metrics

- **Primary Metric**: Quadratic Weighted Kappa (QWK)
  - Accounts for ordinal nature of scoring
  - Penalizes larger disagreements more heavily
- **Secondary Analysis**: Confusion matrices, agreement analysis

## 🎯 Key Findings

### Model Performance

- **Gemini-Pro** consistently outperformed GPT-3.5-turbo:
  - Average QWK of **0.45** on ASAP-AES
  - Average QWK of **0.43** on LA-AES
- Superior performance attributed to:
  - More recent instruction-tuning
  - Better handling of longer contexts
  - Fewer token-limit failures

### Human Bias Analysis

Real-world evaluation revealed:
- Significant variation between two human assessors (HA₁ vs HA₂)
- Evidence of assessor fatigue: agreement declined for later-assessed essays
- LLM scoring remained consistent and objective throughout
- Human assessors prone to cognitive biases (halo effect, leniency bias, fatigue)

### Rubric Quality Impact

- Clear, quantifiable rubric criteria → better LLM performance
- Subjective terms (e.g., "detailed") → increased model-human disagreement
- Recommendation: Use specific metrics (e.g., "200-300 words") instead of vague descriptors

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

## 📁 Repository Structure

```
Automated-essay-scoring-using-LLM/
├── data/                      # Dataset files
│   ├── asap/                  # ASAP-AES dataset
│   ├── la-aes/                # LA-AES dataset
│   └── o-levels/              # Real-world O-Levels data
├── src/                       # Source code
│   ├── models/                # LLM integration
│   ├── prompts/               # Prompt templates
│   ├── evaluation/            # Metrics and evaluation
│   └── utils/                 # Utility functions
├── notebooks/                 # Jupyter notebooks for analysis
├── results/                   # Experimental results
├── app.py                     # Flask web application
├── requirements.txt           # Python dependencies
├── .env.example              # Environment variables template
└── README.md                 # This file
```

## 📈 Results Summary

### ASAP-AES Performance

| Essay Set | GPT-3.5 QWK | Gemini-Pro QWK | Human Agreement |
|-----------|-------------|----------------|-----------------|
| Set 1     | 0.07        | 0.23           | 0.72            |
| Set 2 (D1)| 0.48        | 0.52           | 0.81            |
| Set 3     | 0.31        | 0.46           | 0.77            |
| Set 4     | 0.45        | 0.51           | 0.85            |
| Set 5     | 0.46        | 0.52           | 0.82            |
| Set 6     | 0.54        | 0.63           | 0.80            |

### LA-AES Performance

| Metric          | GPT-3.5 | Gemini-Pro | Human Inter-rater |
|-----------------|---------|------------|-------------------|
| QWK Score       | 0.29    | 0.43       | 0.72-0.85         |

## 🔮 Future Work

1. **Newer Models**: Evaluate GPT-4, Gemini 1.5, Claude 3, and Llama-3
2. **Additional Metrics**: Incorporate Pearson correlation and mean absolute error
3. **Fairness Analysis**: Examine demographic biases (gender, ethnicity, socioeconomic background)
4. **Multilingual Support**: Extend to non-English essays
5. **Multimodal Tasks**: Include essays with images, charts, or diagrams
6. **Subject Expansion**: Apply to programming assessment, scientific experiments, mathematical equations

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
