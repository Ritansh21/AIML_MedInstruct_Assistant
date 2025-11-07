This project is developed as part of the AI/ML Internship Assessment by Solar Industries India Ltd. It is created by Himanshu Vaidya, a student of Data Science at G. H. Raisoni College of Engineering and Management.

The AIML MedInstruct Assistant is an AI-based application designed to generate safe, educational, and informative responses to health-related queries. It uses LoRA fine-tuning on the Falcon-RW-1B model to build a lightweight and efficient AI assistant capable of running even on Google Colab Free GPU.

Project Architecture Base Model: tiiuae/falcon-rw-1b Fine-Tuning Technique: LoRA (Low-Rank Adaptation) Frameworks Used: Hugging Face Transformers, PEFT, BitsAndBytes, Accelerate Development Platform: Google Colab Trainable Parameters: ~1.5 Million only

Working Process

Dataset Preparation: Instruction–Response pairs related to basic health guidance. Example:
Instruction: Explain how to treat a mild fever at home safely.

Response: Rest well, stay hydrated, and avoid self-medication. Consult a doctor if fever persists for more than two days.

Model Loading: Falcon-RW-1B loaded in 4-bit precision for memory efficiency.

LoRA Adapter Application: Added trainable adapters on attention layers for low-resource fine-tuning.

Training: One epoch of fine-tuning using AdamW optimizer.

Adapter Saving & Inference: LoRA adapter saved as lora_adapter.zip and tested on sample queries.

Example Output

User Input: What should I do for a mild headache?

Model Output:

Stay in a quiet, dark place and drink enough water.

Avoid screen time and rest your eyes.

If the pain continues, consult a healthcare professional.

This response is for educational purposes only and not medical advice.

Repository Structure AIML_MedInstruct_Assistant/

├── README.md

├── colab_notebook.ipynb

├── requirements.txt

└── sample_inference_output.txt

Requirements

transformers==4.41.2

peft==0.10.0

bitsandbytes==0.43.1

accelerate==0.30.1

datasets==2.20.0

torch>=2.2.0

tqdm

How to Run

Clone the repository git clone https://github.com//AIML_MedInstruct_Assistant.git cd AIML_MedInstruct_Assistant

Install dependencies: pip install -r requirements.txt

Open and run the notebook in Google Colab or Jupyter.

Author

Name: Ritansh Khapre

Branch: Data Science

College: G. H. Raisoni College of Engineering and Management

Internship: AI/ML Internship – Solar Industries India Ltd
