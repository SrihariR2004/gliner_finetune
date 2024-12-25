# Fine-Tuned Gliner Model: Patient and Provider Name Classification
# Overview
This repository contains a fine-tuned version of the Gliner model designed specifically to classify Patient Names and Provider Names from input text. The model has been fine-tuned on domain-specific data to achieve high accuracy in identifying and categorizing these entities, making it useful for applications in healthcare, medical record management, and other related fields.

Features
Entity Classification: Detects and classifies entities into two categories:
Patient Name
Provider Name
Fine-Tuned for Precision: Optimized on a custom dataset to ensure accurate classification for medical text.
Ready for Integration: Can be seamlessly integrated into pipelines for Natural Language Processing (NLP) tasks.

Getting Started
Prerequisites

Python 3.8 or later

Install required libraries:

pip install transformers in 4.48.0.dev0

pip install gliner 

Usage Input Format

Provide the model with raw text input. 

Example:

input text

"Dr. Smith provided the report for John Doe."

Output Format:

The model will classify and output entities with their respective categories:

{

  "Patient Name": "John Doe",
  
  "Provider Name": "Dr. Smith"
  
}

Example Script

Use the following script to run the model:

# Load the fine-tuned model

from gliner import GLiNERConfig, GLiNER

model = GLiNER.from_pretrained("srihari420/gliner_patientandprovider_name_classifier")

# Input text
text = "Dr. Smith provided the report for John Doe."

# Tokenize and classify
inputs = tokenizer(text, return_tensors="pt", truncation=True, padding=True)
outputs = model.predict_entities(text,labels=['patient','Provider'])

# Process the output (implement logic based on your model's specifics)
print("Classification Output:", outputs)
Model Details
Fine-Tuning Dataset: A proprietary dataset with annotated patient and provider names.

# Applications
Electronic Health Records (EHR) Processing: Automate the identification of patient and provider names in medical documents.
Data Annotation Tools: Enhance the labeling process for healthcare-related text data.
NLP Pipelines: Integrate into larger text processing workflows for downstream tasks.

# Contributing
Contributions are welcome! Feel free to submit a pull request or open an issue if you encounter bugs or have feature requests.

