# 🧠 Plagiarism Detection System

A web-based platform for detecting plagiarism in academic submissions using intelligent NLP techniques. This system helps educators upload assignments, analyze similarities, and generate insightful plagiarism reports using TF-IDF, K-gram, and sentence-level comparison algorithms.

![2 checking plagiarism](https://github.com/user-attachments/assets/70f13c73-3b7e-45a8-83a9-52cb04dd5214)

---

## 🚀 Features

- 📁 Upload files (PDF, DOCX, TXT)
- 🔍 Multi-algorithm plagiarism detection
- 🧾 Detailed similarity reports
- 👨‍🏫 Role-based user access (Teacher & Student)
- 🔐 JWT Authentication with Djoser
- 📚 Course and assignment management
- 💻 Modern, responsive frontend using Next.js & Tailwind CSS

---

## 🏗 Tech Stack

| Layer        | Technology                                |
|--------------|--------------------------------------------|
| Frontend     | Next.js 14, React 18, Tailwind CSS, TypeScript |
| Backend      | Django 4.2.7, Django REST Framework, Python 3.8+ |
| Authentication | JWT, Djoser |
| NLP & ML     | scikit-learn, NLTK |
| Database     | SQLite (dev), PostgreSQL (prod) |
| File Parsing | PyPDF2, python-docx |
| UI Components| shadcn/ui, Lucide React Icons |

---

## ⚙ Setup Instructions

### ✅ Prerequisites
- Python 3.8+
- Node.js 16+
- npm or yarn

---

### 🔧 Backend Setup

bash
git clone https://github.com/yourusername/plagiarism-detector.git
cd plagiarism-detector

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Download NLTK data
python setup.py

# Setup database
python manage.py makemigrations accounts detector
python manage.py migrate

🌐 Frontend Setup
cd frontend

# Install dependencies
npm install  # or yarn install

# Create env file
echo "NEXT_PUBLIC_API_URL=http://localhost:8000" > .env.local

# Run dev server
npm run dev  # or yarn dev

# Open in browser
http://localhost:3000

![1 server_running](https://github.com/user-attachments/assets/6f2540f7-fd64-4f1e-999e-789cc10e3688)

# Create superuser
python manage.py createsuperuser

# Run server

### 🔁 *Project Workflow*

- 🔐 *User Authentication*  
  - User registers/logs in via the frontend
  - Backend issues JWT tokens  
  - Tokens are stored in localStorage and used in API headers  

- 📤 *Assignment Upload*  
  - User uploads a document (PDF, DOCX, TXT) with assignment details
  ![4 document_selection](https://github.com/user-attachments/assets/410c870c-5fe9-4034-80e0-c120364b18bc)

extracts text content and stores it in the database  

- 🧪 *Plagiarism Detection*  
  - User selects an assignment to check

![3 interface](https://github.com/user-attachments/assets/155d9829-90e4-467e-9aa1-011c7686cd23)

  - Text is preprocessed (lowercase, cleaned)  
  - Detection algorithms are applied:
    - TF-IDF + Cosine Similarity
    - K-gram Fingerprinting
    - Sentence-Level Matching  
  - Results (score + matches) are saved and returned  

![5 result_comparison](https://github.com/user-attachments/assets/cd165d61-1979-476d-b2b9-4e3072402bd5)

- 📊 *Results Visualization*  
  - Frontend fetches results via API  
  - Plagiarism reports show:
    - Matched text snippets  
    - Source types (Assignment, Internet, DB)  
    - Similarity scores  

![6 final_result](https://github.com/user-attachments/assets/6fb2d49e-4ca9-4eb6-8a7c-1cfe0809cc2e)

- 🛠 *Tech & Communication*  
  - Frontend ↔ Backend via RESTful API  
  - Django handles logic; Next.js renders UI  

---
python manage.py runserver
