# Resume Fianchetta

Resume Fianchetta is an AI powered resume parsing system that converts raw resumes into structured and searchable candidate profiles. The platform uses Python, Django, and a lightweight machine learning pipeline to extract key information such as personal details, skills, education, and work experience. It is designed to help companies collect large volumes of resumes, process them automatically, and review clean reports through a recruiter dashboard.

---

## Features

### 1. Resume Upload

- Supports PDF, DOCX, and TXT.
- Validates and sanitizes uploads.
- Converts files to plain text for processing.

### 2. AI Powered Parsing

- Uses NLP to extract:

  - Personal information
  - Skills
  - Experience
  - Education
  - Certifications
  - Projects or summary sections

- Handles different resume structures with custom logic.

### 3. Candidate Profiles

- Parsed data is stored in a structured format.
- Each resume generates a candidate profile with clean fields.
- Profiles can be viewed, edited, or exported as JSON.

### 4. Recruiter Dashboard

- Recruiters can log in and view all candidates.
- Includes filtering, searching, and summary reports.
- Shows upload history and parsing accuracy.

### 5. REST API

- Resume upload endpoint
- Candidate profile endpoints
- Resume summary endpoint
- Auth endpoints for login and registration

---

## System Architecture

### Backend

- Django
- Django REST Framework
- PostgreSQL

### Machine Learning

- spaCy or a small transformer model
- Regex based extraction for personal info
- Custom parsing logic for experience and education

### File Processing

- pdfminer.six for PDF
- python-docx for DOCX
- Plain text extraction pipeline

### Frontend (optional)

- React or Django templates for viewing parsed profiles

---

## Project Structure

```
resume_fianchetta/
    backend/
        parsers/
        candidates/
        recruiters/
        api/
        core/
    frontend/ (optional)
    docs/
```

---

## Core API Endpoints

### Authentication

- POST /api/auth/register
- POST /api/auth/login
- POST /api/auth/logout

### Candidate Resume Workflow

- POST /api/resumes/upload
- GET /api/resumes/<id>
- GET /api/resumes/<id>/summary
- GET /api/candidates/<id>
- PUT /api/candidates/<id>/update

### Recruiter Dashboard

- GET /api/recruiter/candidates
- GET /api/recruiter/reports
- GET /api/recruiter/uploads

---

## How It Works

1. The candidate uploads a resume.
2. Django extracts text from the file.
3. The NLP model identifies sections and entities.
4. Parsed data is cleaned and normalized.
5. The system stores the structured profile.
6. Recruiters view profiles and reports through the dashboard.

---

## Installation

### 1. Clone the repository

```
git clone https://github.com/your-username/resume-fianchetta.git
```

### 2. Create a virtual environment

```
python -m venv env
source env/bin/activate
```

### 3. Install dependencies

```
pip install -r requirements.txt
```

### 4. Run migrations

```
python manage.py migrate
```

### 5. Start the server

```
python manage.py runserver
```

---

## Future Improvements

- Automatic job matching
- Multi language resume support
- Export parsed resume into a formatted template
- AI confidence scoring
- Admin review tools for correction
