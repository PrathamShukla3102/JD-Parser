# JD-Parser
Job Descriptions Parser
 
**Unstructured Job Descriptions → Structured, Queryable Data**

---

## Overview
JD-Parser is an automated data pipeline that converts unstructured job descriptions into structured datasets using LLMs.

The system ingests raw job descriptions from a CSV file, extracts key attributes such as role, skills, seniority, location, and salary, and outputs clean, queryable data in CSV format.

---

## Problem Statement
Hiring data is often stored in unstructured text formats, making it:
- Difficult to search  
- Hard to analyze  
- Inconsistent across sources  

This project solves that by transforming raw job descriptions into structured, standardized fields automatically.

---

## What I Built

### Core Pipeline
- Input: CSV file with 25 job descriptions  
- Processing: LLM-based extraction using OpenAI API  
- Output:
  - Structured dataset (CSV)  
  - JSON-like structured records  

---

## Extracted Fields
- Role  
- Seniority  
- Experience  
- Skills (list)  
- Location  
- Salary  

---

## Tech Stack
- Python  
- Pandas  
- OpenAI API  

---

## System Workflow

1. Load CSV file containing job descriptions  
2. Iterate through each job description  
3. Send text to LLM for extraction  
4. Parse structured JSON response  
5. Store results in a DataFrame  
6. Export final structured data as CSV  

---

## Input Format

CSV file with column:
job_descriptions
Example:
We are hiring a Data Scientist with Python and ML experience...
Looking for ML Engineer with AWS and TensorFlow skills...
## Output Format

{
  "role": "Data Scientist",
  "seniority": "Mid",
  "experience": "3+ years",
  "skills": ["Python", "ML"],
  "location": "Pune",
  "salary": "Not specified"
}
## How to Run
### 1. Install dependencies
   pip install openai pandas
### 2. Set API Key
   os.environ["OPENAI_API_KEY"] = "Enter_API_KEY"
### 3. Run script / notebook
  - Upload CSV file
  - Execute pipeline
  - Output CSV will be generated
    
## Challenges Faced
- JSON parsing errors from LLM responses
- Missing or ambiguous fields in some job descriptions
- Inconsistent formatting in raw input
## Fixes:
- Cleaned LLM responses before parsing
- Added default values ("Not specified")
- Implemented error handling for failed rows

