# PSAIDS-Manager
Powershell AI Dataset Manager (PSAIDS) - By - jm@cloudware.host

PSAIDS Manager is a PowerShell-based automation tool for curating, validating, and managing AI training datasets. It is designed specifically for PowerShell scripting and Microsoft Graph API automation, ensuring that models learn only verified, Microsoft-supported syntax.

---

Features
- Automated Directory Scaffolding – Organizes datasets, instructions, dependencies, and knowledge base files.
- Knowledge Base (RAG) – Builds and updates a verified repository of PowerShell and Microsoft Graph API syntax.
- Data Validation and Conversion – Cleans raw PowerShell scripts, filters incorrect syntax, and converts them to structured JSONL format.
- AI Environment Setup – Installs Python, dependencies, and AI libraries required for fine-tuning models.
- GPU and Compatibility Checks – Detects available GPU support, including CUDA, ROCm, and DirectML.
- Dataset Preparation for AI Models – Ensures that only validated, high-quality data is used for training.

---

Installation
1. Clone this repository:
   git clone https://github.com/vilonauzd/AI-Dataset-Manager.git
   cd AI-Dataset-Manager

2. Run the AI Dataset Manager script:
   powershell -ExecutionPolicy Bypass -File AI_Dataset_Manager.ps1

---

Usage
After launching the AI Dataset Manager, follow the on-screen menu options:

1. Create Directory Scaffolding  
   - Organizes the necessary folders for raw data, processed data, instructions, dependencies, and knowledge base.  

2. Install AI Training Environment  
   - Checks for Python installation and installs it if missing.  
   - Ensures pip is installed and updated.  
   - Installs AI-related dependencies, including PyTorch, Transformers, and other required libraries.

3. Check GPU and Environment Setup  
   - Detects available GPU support for CUDA, ROCm, and DirectML.  
   - Runs a test script to validate AI framework compatibility.

4. Build and Update Knowledge Base  
   - Extracts all valid PowerShell cmdlets and their parameters.  
   - Retrieves Microsoft Graph API commands and stores verified syntax in a structured knowledge base.  
   - Ensures that only supported PowerShell and Graph API commands are used in training.

5. Convert and Validate Dataset  
   - Scans raw PowerShell scripts for verification.  
   - Cross-references scripts with the verified Knowledge Base (RAG).  
   - Filters out invalid, deprecated, or incorrect syntax.  
   - Saves the validated dataset in JSONL format for AI model training.

6. Exit  
   - Closes the AI Dataset Manager application.

---

![image](https://github.com/user-attachments/assets/98bf207a-8c6a-4014-9177-c4e1d22e43ca)

---

Instructions

1. Preparing Your Dataset
   - Place raw PowerShell scripts in raw_data/powershell_scripts/
   - Add text-based documentation in raw_data/txt_docs/
   - Include Microsoft Graph API documentation in raw_data/ms_graph_docs/
   - Run the AI Dataset Manager script and select "Convert and Validate Dataset" to process the data.

2. Fine-Tuning AI Model
   - Install dependencies:
     pip install torch torchvision torchaudio transformers datasets accelerate deepspeed

   - Load dataset in Python:
     from datasets import load_dataset
     dataset = load_dataset("json", data_files={"train": "processed_data/powershell_dataset.jsonl"})

   - Train the model:
     trainer.train()

3. Running the Fine-Tuned Model
   - Load the trained model:
     from transformers import pipeline
     pipe = pipeline("text-generation", model="qwen_powershell", tokenizer=tokenizer, torch_dtype="bf16", device=0)

   - Run inference on PowerShell tasks:
     output = pipe("Write a PowerShell script to list all users from Azure AD.", max_length=512)
     print(output[0]["generated_text"])

---

Contact
Author: jm@cloudware.host

Contribution
Contributions are welcome. To contribute:
1. Fork this repository.
2. Create a new branch:
   git checkout -b feature-branch
3. Commit your changes:
   git commit -m "Description of changes"
4. Push to your branch:
   git push origin feature-branch
5. Open a pull request.

---

License
This project is licensed under the MIT License. See the LICENSE file for details.

---

Acknowledgments
This project is designed to enhance AI model training by ensuring high-quality, validated PowerShell and Microsoft Graph API datasets.
