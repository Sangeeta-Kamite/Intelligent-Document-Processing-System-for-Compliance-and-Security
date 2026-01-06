# Intelligent Document Processing-System-for-Compliance-and-Security
This project develops an AI-powered document processing system that extracts, classifies, and redacts sensitive information from documents using Natural Language Processing (NLP).
The system ensures privacy compliance (e.g., GDPR, HIPAA, CCPA) by automatically detecting and redacting Personally Identifiable Information (PII) while categorizing document types and their sections.

**Key Objectives**
1. Automate document processing to reduce manual effort.
2. Ensure compliance by detecting and redacting sensitive data.
3. Categorize documents (Legal, Finance, Medical, etc.).
4. Enhance security through automated data protection.

**Features | Technology | Implementation**
1. **Document Parsing** | OCR/ Text Extraction  | pdfplumber, Textract
2. **Named Entity Recognition(NER)** | Detect PII(Names, Dates) | spacy, Flair, Stanza
3. **PII Redaction** | Masks detected PII(e.g., [REDACTED]) | Regex + NER
4. **Text Classification** | classifies document type | TF-IDF + Naive Bayes [Machine Learning]
5. **Section-wise classification** | Categorise document parts(e.g., Financial Data, Personal Info) | BERT, Hugging Face, Transformers
6. **JSON/PDF Output** | Saves processed documents | json, pyMuPDF
7. **Deployment** | FastAPI, Flask

**Workflow of the System**

**1. Extract Text from Documents**
   - Parses text from PDFs (structured & scanned) using OCR (pdfplumber, Tesseract).
   - Handles legal, financial, and medical documents.
   
**2. Detect PII (Named Entity Recognition)**
   - Identifies names, phone numbers, addresses, SSNs, and bank details using NER models (spaCy).
   - Extracted PII is stored for compliance tracking.
   
**3. Redact PII**
   - Automatically masks sensitive information in documents.
   
**4. Classify Document Type**
   - Uses TF-IDF & Naive Bayes to classify documents as Legal, Finance, or Medical.
   - Example:
       "This contract is legally binding." → Legal Document
       "Your account balance is $5,000." → Finance Document
       
**5. Section-Level Classification**
   - Uses Hugging Face Transformers (BERT) to classify document sections:
   - Personal Information
   - Financial Data
   - Legal Information
   - Medical Records
   
**6. Output Processed Document**
   - Saves as structured JSON with classifications.
   - Optionally generates redacted PDF with removed PII.

**Real-World Applications**
1. Legal Compliance: Redacts PII for GDPR, HIPAA regulations.
2. Finance & Insurance: Automates contract & invoice processing. 
3. HR & Recruitment: Extracts structured data from resumes.
4. Medical Records Processing: De-identifies patient data for research.
5. Government & Security: Handles classified document processing.
