# Data Analyst AI

This repository contains a Jupyter notebook.The notebook performs OCR, document parsing, data visualization, and utilizes a powerful language model from Together.ai to assist in data analysis tasks.

## 🧠 Features

- 📄 Extracts text from PDFs, Word documents, and images
- 🧠 Integrates LLM (LLaMA) via Together.ai for answering questions and generating insights
- 📊 Data visualization using Matplotlib and Seaborn
- 🧪 OCR using Tesseract and pdfplumber
- 🖼️ Interactive front-end using Gradio


## 🚀 Getting Started

### 1. Clone the repo

```
git clone https://github.com/GitHub-Aditya14Raj/data-analyst-ai.git
cd data-analyst-ai
```
### 2. Install requirements
```pip install -r requirements.txt```
### 3. 🧠 Using Together.ai
Create a free account: https://www.together.ai/

Generate your API key from the dashboard.

Inside the `DataAnalystAgent` class:
```python
from together import Together

class DataAnalystAgent:
    def __init__(self):
        self.api_key = "your_api_key_here"
        self.model_name = "meta-llama/Llama-4-Maverick-17B-128E-Instruct-FP8"
        self.client = Together(api_key=self.api_key)

    def _call_llama(self, prompt):
        response = self.client.chat.completions.create(
            model=self.model_name,
            messages=[{"role": "user", "content": prompt}],
            max_tokens=2048,
            temperature=0.7,
            stream=False
        )
        return response.choices[0].message.content.strip()
```

### 4. Launch notebook
```jupyter notebook Data_analyst_ai.ipynb```

📁 Project Files
.
├── Data_analyst_ai.ipynb     # Main notebook
├── requirements.txt            # Dependencies
├── .gitignore                  # Git exclusions
├── LICENSE                     # MIT license
└── README.md                   # Instructions (this file)


📜 License
This project is licensed under the MIT License.

