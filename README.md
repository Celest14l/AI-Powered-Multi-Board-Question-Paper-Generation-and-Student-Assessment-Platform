# 🎓 BoardAI — AI-Powered Multi-Board Assessment & Question Paper Generator

> **Generate. Assess. Analyze. Improve.**

BoardAI is an AI-powered educational assessment platform designed to help schools, coaching institutes, and teachers create **customized, board-aligned question papers** for CBSE, ICSE, and State Boards.

The platform combines **Large Language Models (LLMs), Retrieval-Augmented Generation (RAG), board-specific assessment rules, syllabus mapping, question banks, automated validation, marking-scheme generation, and student performance analytics**.

Instead of simply asking an AI to "generate questions," BoardAI uses a structured assessment pipeline to create papers based on the teacher's exact requirements.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Solution](#-solution)
- [Key Features](#-key-features)
- [Example](#-example)
- [How It Works](#-how-it-works)
- [AI Architecture](#-ai-architecture)
- [System Architecture](#-system-architecture)
- [Board Support](#-board-support)
- [Question Generation](#-question-generation)
- [Question Validation](#-question-validation)
- [Assessment Analytics](#-assessment-analytics)
- [Technology Stack](#-technology-stack)
- [Project Structure](#-project-structure)
- [Database Design](#-database-design)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [Development Workflow](#-development-workflow)
- [Roadmap](#-roadmap)
- [Future Scope](#-future-scope)
- [Security](#-security)
- [Responsible AI](#-responsible-ai)
- [Contributing](#-contributing)
- [License](#-license)

---

# 🚀 Overview

Teachers and educational institutes frequently need to create large numbers of question papers for:

- Chapter tests
- Unit tests
- Weekly tests
- Monthly tests
- Mid-term examinations
- Pre-board examinations
- Revision tests
- Mock board examinations

Creating these papers manually requires significant time and effort.

BoardAI automates this process while allowing teachers to retain complete control over the final assessment.

A teacher can specify:

```text
Board: CBSE
Class: 10
Subject: Science

Chapters:
2, 3 and 4

Marks:
30

Duration:
60 minutes

Difficulty:
Board Level

Question Preferences:
Application Based
MCQs
Short Answer
Case Study
```

BoardAI generates a complete assessment while maintaining the requested constraints.

---

# 🎯 Problem Statement

Generic AI question generators have several limitations.

They may generate questions that:

- Fall outside the syllabus
- Do not match the selected board
- Have incorrect marks distribution
- Have inappropriate difficulty
- Repeat similar questions
- Contain factual or numerical errors
- Do not follow expected examination structures
- Lack proper marking schemes
- Cannot reliably handle chapter-wise weightage
- Do not account for examination duration

BoardAI addresses these limitations using a combination of:

```text
LLM
+
RAG
+
Board Rule Engine
+
Syllabus Database
+
Question Bank
+
Validation Engine
+
Assessment Analytics
```

---

# 💡 Solution

BoardAI converts a teacher's requirements into a structured **Assessment Blueprint**.

### Pipeline

```text
Teacher Requirements
        ↓
Requirement Parser
        ↓
Assessment Blueprint
        ↓
Board Rule Validation
        ↓
Syllabus Retrieval
        ↓
Question Generation
        ↓
Question Validation
        ↓
Duplicate Detection
        ↓
Paper Assembly
        ↓
Answer Key
        ↓
Marking Scheme
        ↓
Teacher Review
        ↓
Final Assessment
```

The teacher remains the final decision-maker.

---

# ✨ Key Features

## 1. Custom Question Paper Generation

Create papers using:

- Board
- Class
- Subject
- Chapters
- Topics
- Marks
- Duration
- Difficulty
- Question types
- Chapter weightage
- Competency requirements

---

## 2. Natural Language Paper Creation

Teachers can describe what they want in plain language.

Example:

> Create a 30-mark CBSE Class 10 Science paper from Chapters 2, 3 and 4. Keep it board-level, include six MCQs and one case-study question, and give slightly more weightage to Chapter 3.

The system converts this into a structured configuration automatically.

---

## 3. Multi-Board Support

Designed to support:

- CBSE
- ICSE
- Maharashtra SSC
- Karnataka SSLC
- Gujarat Board
- UP Board
- MP Board
- Rajasthan Board
- Other State Boards

The architecture is designed so new boards can be added without changing the core AI generation engine.

---

## 4. Chapter-Level Customization

Teachers can select any combination of chapters.

Example:

```text
☑ Chapter 2
☑ Chapter 3
☑ Chapter 4
☐ Chapter 5
```

The system generates questions only from the selected content.

---

## 5. Custom Marks

Supported examples:

```text
10 Marks
20 Marks
30 Marks
40 Marks
50 Marks
80 Marks
100 Marks
Custom
```

The system validates:

```text
Sum of all question marks = Total requested marks
```

---

## 6. Difficulty Control

Teachers can choose:

- Easy
- Moderate
- Board Level
- Difficult
- Custom Distribution

Example:

```text
Easy        20%
Moderate    50%
Difficult   30%
```

---

## 7. Question-Type Control

Depending on the selected board and subject:

- MCQ
- Very Short Answer
- Short Answer
- Long Answer
- Numerical
- Assertion-Reason
- Case Study
- Competency Based
- Application Based
- Source Based
- Diagram Based
- Match the Following
- Fill in the Blanks
- True/False

The platform only offers question types compatible with the selected assessment configuration.

---

## 8. Chapter-Wise Weightage

Example:

```text
Chapter 2 → 8 Marks
Chapter 3 → 12 Marks
Chapter 4 → 10 Marks

Total → 30 Marks
```

Teachers can either specify the distribution manually or allow the system to generate a balanced distribution.

---

## 9. Competency-Based Questions

Questions can be classified according to skills such as:

- Knowledge
- Understanding
- Application
- Analysis
- Reasoning
- Problem Solving
- Critical Thinking
- Interpretation

---

## 10. Bloom's Taxonomy

Questions can be categorized as:

```text
Remember
Understand
Apply
Analyze
Evaluate
Create
```

Teachers can optionally specify a desired distribution.

---

## 11. AI Question Validation

Every generated question is independently evaluated for:

- Syllabus alignment
- Board alignment
- Difficulty
- Language
- Conceptual correctness
- Answerability
- Marks suitability
- Competency
- Duplication

---

## 12. Duplicate Detection

The system detects:

- Exact duplicates
- Near duplicates
- Semantically similar questions
- Repeated numerical patterns
- Excessive concept repetition

Possible techniques include:

- Embeddings
- Semantic similarity
- Metadata comparison
- LLM-based comparison

---

## 13. Automatic Answer Key

The platform generates:

- Objective answers
- Expected subjective answers
- Important points
- Numerical solutions

---

## 14. Automatic Marking Scheme

Example:

```text
Question: 3 Marks

Correct concept       → 1 Mark
Correct explanation   → 1 Mark
Correct conclusion    → 1 Mark
```

For numerical questions:

```text
Formula               → 1 Mark
Substitution          → 1 Mark
Calculation            → 1 Mark
Final Answer           → 1 Mark
```

The marking scheme is generated according to the question and applicable assessment guidance.

---

## 15. Paper Quality Analysis

Before finalizing a paper, the platform performs quality checks.

Example:

```text
---------------------------------------
PAPER QUALITY ANALYSIS
---------------------------------------

Total Marks          ✓ 30 / 30
Syllabus Alignment   ✓ 100%
Chapter Distribution ✓ Valid
Difficulty Balance   ✓ Good
Board Alignment      ✓ High
Question Diversity   ✓ Good
Time Estimate        ✓ 56 Minutes
Duplicate Check      ✓ Passed
Answer Key           ✓ Generated
Marking Scheme       ✓ Generated

---------------------------------------
STATUS: READY FOR REVIEW
---------------------------------------
```

Quality scores are intended as internal decision-support metrics and do not represent official board certification.

---

# 🧠 AI Architecture

BoardAI does not rely solely on an LLM.

It combines several AI and software components.

```text
                 ┌────────────────────┐
                 │ Teacher / Admin     │
                 └─────────┬──────────┘
                           ↓
                 ┌────────────────────┐
                 │ Requirement Parser  │
                 └─────────┬──────────┘
                           ↓
                 ┌────────────────────┐
                 │ Assessment Blueprint│
                 └─────────┬──────────┘
                           ↓
          ┌────────────────┴────────────────┐
          ↓                                 ↓
 ┌──────────────────┐              ┌──────────────────┐
 │ Board Rule Engine│              │ Syllabus Engine  │
 └────────┬─────────┘              └────────┬─────────┘
          │                                 │
          └────────────────┬────────────────┘
                           ↓
                 ┌────────────────────┐
                 │ RAG Retrieval      │
                 └─────────┬──────────┘
                           ↓
                 ┌────────────────────┐
                 │ Question Generator │
                 │       LLM          │
                 └─────────┬──────────┘
                           ↓
                 ┌────────────────────┐
                 │ Question Validator │
                 └─────────┬──────────┘
                           ↓
                 ┌────────────────────┐
                 │ Paper Assembly     │
                 └─────────┬──────────┘
                           ↓
              ┌────────────┴────────────┐
              ↓                         ↓
       Question Paper             Answer Key
                                        │
                                        ↓
                                Marking Scheme
```

---

# 📚 Retrieval-Augmented Generation

RAG is used to ground the AI in relevant educational information.

### Data Sources

The knowledge base can contain appropriately sourced:

- Official board curriculum
- Official syllabus
- Official assessment guidelines
- Sample question papers
- Marking schemes
- Examination frameworks
- Learning outcomes
- Institute-approved educational material

### RAG Pipeline

```text
Documents
    ↓
Text Extraction
    ↓
Cleaning
    ↓
Chunking
    ↓
Metadata
    ↓
Embeddings
    ↓
Vector Database
    ↓
Relevant Retrieval
    ↓
LLM
    ↓
Structured Output
```

Metadata should include:

```text
board
class
subject
chapter
topic
document_type
academic_year
source
```

---

# ⚙️ Board Rule Engine

Each board has a configurable profile.

Example:

```text
Board Profile
│
├── Board Name
├── Academic Year
├── Classes
├── Subjects
├── Syllabus
├── Examination Structure
├── Marks Rules
├── Question Types
├── Assessment Requirements
└── Official Documents
```

The board rule engine ensures that the AI does not blindly apply one board's structure to another board.

---

# 📝 Question Metadata

Every question should be stored with structured metadata.

Example:

```json
{
  "question_id": "Q10293",
  "board": "CBSE",
  "class": 10,
  "subject": "Science",
  "chapter": "Chapter 3",
  "topic": "Chemical Reactions",
  "marks": 3,
  "question_type": "short_answer",
  "difficulty": "medium",
  "bloom_level": "apply",
  "competency": "application",
  "estimated_time_minutes": 5,
  "answer": "...",
  "marking_scheme": []
}
```

This metadata enables:

- Search
- Filtering
- Analytics
- Question reuse
- Difficulty calibration
- Personalized practice
- Paper generation

---

# 🧪 Question Generation Strategy

The system should not generate an entire paper using one LLM call.

Instead:

### Step 1 — Requirement Parsing

Understand the teacher's request.

### Step 2 — Blueprint Generation

Determine:

- Number of questions
- Marks distribution
- Chapter distribution
- Difficulty distribution
- Question-type distribution
- Competency distribution

### Step 3 — Knowledge Retrieval

Retrieve relevant syllabus and assessment information.

### Step 4 — Question Generation

Generate questions individually or in controlled batches.

### Step 5 — Question Validation

Check each question.

### Step 6 — Paper Assembly

Build the complete assessment.

### Step 7 — Final Validation

Check the entire paper again.

---

# 🔍 Validation Engine

The validation engine combines deterministic rules and AI-based evaluation.

## Deterministic Validation

Used for:

- Total marks
- Question count
- Section marks
- Chapter distribution
- Allowed question types
- Duration
- Required fields

Example:

```python
total_marks = sum(q.marks for q in questions)

if total_marks != requested_marks:
    raise ValidationError("Marks mismatch")
```

## AI Validation

Used for:

- Academic correctness
- Difficulty
- Language
- Board style
- Syllabus relevance
- Answerability

This hybrid approach is preferred over relying entirely on AI.

---

# ⏱️ Time Feasibility

The system should estimate how long a student may need to complete the paper.

Example:

```text
Question 1 → 1 min
Question 2 → 2 min
Question 3 → 5 min
...

Estimated solving time → 54 min
Exam duration → 60 min

Status → Feasible
```

If the estimated time is too high:

> ⚠️ The current paper may be too lengthy for the selected duration.

---

# 👨‍🏫 Teacher Dashboard

The teacher dashboard should include:

```text
Dashboard
│
├── Create Paper
├── My Papers
├── Question Bank
├── Students
├── Tests
├── Results
├── Analytics
└── Settings
```

---

# 🖥️ Paper Generator UI

Example:

```text
========================================

        CREATE ASSESSMENT

Board
[ CBSE ▼ ]

Class
[ 10 ▼ ]

Subject
[ Science ▼ ]

Chapters
☑ Chapter 2
☑ Chapter 3
☑ Chapter 4

Total Marks
[ 30 ]

Duration
[ 60 Minutes ]

Difficulty
[ Board Level ▼ ]

Question Types
☑ MCQ
☑ Short Answer
☑ Case Study

Additional Instructions

[ Board-level difficulty.
  Focus on application-based questions. ]

             [ GENERATE PAPER ]

========================================
```

---

# ✏️ Paper Editor

After generation, teachers can:

- Edit questions
- Delete questions
- Replace questions
- Change difficulty
- Change question type
- Lock questions
- Modify marks
- Regenerate answers
- Regenerate marking schemes

### Replace Question

For example:

```text
Replace Q7

[ Same Difficulty ]
[ Easier ]
[ Harder ]
[ Application Based ]
[ Numerical ]
[ Case Study ]
[ Different Topic ]
```

The replacement should preserve the overall paper constraints.

---

# 📊 Student Assessment Module

Students can:

- Take online tests
- Submit answers
- Upload answer sheets
- View marks
- Review mistakes
- Practice weak areas
- Take personalized tests

---

# 🤖 AI Answer Evaluation

Future versions can support handwritten answer evaluation.

```text
Handwritten Answer Sheet
        ↓
OCR / Vision Model
        ↓
Question Detection
        ↓
Answer Extraction
        ↓
Marking Scheme
        ↓
AI Evaluation
        ↓
Marks
        ↓
Feedback
```

Example:

```text
Q8

Score: 2 / 3

✓ Correct concept
✓ Correct formula
✗ Final calculation incorrect

Recommendation:
Recheck your calculation after substitution.
```

---

# 📈 Student Performance Analytics

The system should track:

- Accuracy
- Marks
- Time
- Chapter performance
- Topic performance
- Question-type performance
- Difficulty performance
- Frequent mistakes
- Improvement over time

Example:

```text
MATHEMATICS

Algebra          82%
Geometry         71%
Trigonometry     54%
Statistics       88%

Priority Area:
Trigonometry
```

---

# 🎯 Personalized Practice

Based on performance:

```text
Weak Topic:
Trigonometric Ratios

Generate:

5 Easy Questions
5 Moderate Questions
5 Application Questions
1 Mini Test
```

The system then uses the new results to update the student's profile.

---

# 🔄 Adaptive Assessment

A future adaptive engine can modify difficulty based on student performance.

```text
Correct Answers
      ↓
Increase Difficulty

Repeated Mistakes
      ↓
Reduce Difficulty
      ↓
Reinforce Concept
      ↓
Increase Difficulty
```

---

# 📄 Multiple Paper Versions

Institutes can generate:

```text
Paper A
Paper B
Paper C
Paper D
```

All versions should maintain:

- Same total marks
- Same syllabus
- Similar difficulty
- Similar chapter weightage
- Different questions

This is useful for different batches and anti-copying purposes.

---

# 🗂️ Question Bank

Questions can be searched using:

```text
Board
Class
Subject
Chapter
Topic
Marks
Difficulty
Question Type
Competency
Bloom Level
Usage
Student Performance
```

The question bank should support both:

- AI-generated questions
- Teacher-created questions

---

# 🏗️ System Architecture

```text
                         USER
                           │
                           ▼
                    WEB APPLICATION
                           │
                           ▼
                       API LAYER
                           │
       ┌───────────────────┼───────────────────┐
       │                   │                   │
       ▼                   ▼                   ▼
 USER MANAGEMENT     ASSESSMENT SERVICE   STUDENT SERVICE
       │                   │                   │
       └───────────────────┼───────────────────┘
                           │
                           ▼
                    AI ORCHESTRATOR
                           │
       ┌───────────────────┼───────────────────┐
       │                   │                   │
       ▼                   ▼                   ▼
      RAG             QUESTION AI        VALIDATION AI
       │                   │                   │
       ▼                   ▼                   ▼
 VECTOR DATABASE        LLM             QUALITY ENGINE
       │
       ▼
 BOARD KNOWLEDGE BASE

                           │
                           ▼
                       POSTGRESQL
                           │
                           ▼
                    ANALYTICS ENGINE
```

---

# 🛠️ Technology Stack

## Frontend

- React
- Next.js
- TypeScript
- Tailwind CSS

## Backend

- Python
- FastAPI

## Database

- PostgreSQL

## Vector Search

Initial:

- FAISS
- Chroma

Production options:

- pgvector
- Pinecone
- Weaviate

## AI

- Large Language Model API
- Embedding Model
- Optional Vision Model for answer-sheet evaluation

## RAG

- LangChain
- LlamaIndex
- Or custom retrieval pipeline

## Document Processing

- PDF extraction
- OCR where required
- Structured document processing

## Export

- PDF
- DOCX

---

# 📁 Suggested Project Structure

```text
boardai/
│
├── frontend/
│   ├── app/
│   ├── components/
│   ├── pages/
│   ├── services/
│   ├── hooks/
│   └── types/
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   ├── repositories/
│   │   ├── ai/
│   │   ├── rag/
│   │   ├── validators/
│   │   └── utils/
│   │
│   ├── tests/
│   └── main.py
│
├── knowledge_base/
│   ├── cbse/
│   ├── icse/
│   └── state_boards/
│
├── data/
│   ├── syllabus/
│   ├── questions/
│   └── datasets/
│
├── scripts/
│   ├── ingest_documents.py
│   ├── create_embeddings.py
│   └── seed_database.py
│
├── docs/
│   ├── architecture.md
│   ├── api.md
│   └── ai-pipeline.md
│
├── .env.example
├── docker-compose.yml
├── requirements.txt
├── package.json
└── README.md
```

---

# 🗄️ Core Database Entities

```text
Users
Boards
AcademicYears
Classes
Subjects
Chapters
Topics
BoardRules
Documents
Questions
QuestionVersions
QuestionPapers
PaperQuestions
Students
Tests
Attempts
Answers
Performance
AIReviews
```

---

# 🔐 Authentication & Authorization

The platform should use role-based access control.

### Roles

```text
SUPER_ADMIN
ADMIN
TEACHER
STUDENT
```

Permissions should be separated accordingly.

For example:

```text
Teacher
✓ Create paper
✓ Edit paper
✓ Assign test
✓ View student results

Student
✓ Attempt test
✓ View own results
✓ Practice questions

Admin
✓ Manage users
✓ Manage boards
✓ Manage syllabus
```

---

# 🔒 Security

The platform should implement:

- Secure authentication
- Password hashing
- JWT/session-based authorization
- Role-based permissions
- Input validation
- API authentication
- Secure database access
- Audit logs
- Rate limiting
- Secure file uploads
- Protection of student data

---

# 🧠 AI Reliability

AI-generated educational content must be validated.

The system should use:

```text
RAG Grounding
+
Structured Outputs
+
Deterministic Validation
+
AI Validation
+
Teacher Review
```

AI should not be treated as infallible.

Particularly important areas:

- Mathematical calculations
- Scientific facts
- Marking schemes
- Board-specific rules
- Syllabus boundaries

---

# 📚 Academic-Year Versioning

Board requirements can change.

Therefore, all board data should be versioned.

Example:

```text
CBSE
│
├── 2025-26
├── 2026-27
└── 2027-28
```

Questions should also store the academic-year context when appropriate.

This prevents outdated rules from being accidentally applied to newer assessments.

---

# ⚖️ Responsible Use

BoardAI is intended to assist teachers and educational institutions.

It should not claim that an AI-generated paper is an official examination paper or guarantee that it will exactly match a future board examination.

The platform should clearly distinguish between:

- Official board content
- Teacher-created content
- Licensed content
- AI-generated content
- Board-aligned practice content

Teachers should retain final approval over assessments.

---

# 🚫 Avoiding Copyright Problems

Previous papers should primarily be used to understand:

- Assessment structure
- Question types
- Difficulty patterns
- Topic distribution
- Competency requirements

The system should prioritize generating **original questions** rather than reproducing copyrighted questions.

---

# 🧪 Testing Strategy

## Unit Testing

Test:

- Marks calculations
- Rule engine
- Chapter distribution
- Question metadata
- Database operations
- Authentication

## Integration Testing

Test:

```text
Frontend
→ API
→ AI
→ Database
→ PDF
```

## AI Testing

Evaluate:

- Syllabus alignment
- Academic correctness
- Board alignment
- Difficulty
- Question diversity
- Answer correctness

## User Acceptance Testing

Teachers should review generated papers and rate:

- Quality
- Relevance
- Difficulty
- Accuracy
- Usability

---

# 📊 Evaluation Metrics

The system can be evaluated using:

### Constraint Accuracy

Percentage of papers satisfying requested configuration.

### Syllabus Alignment

Percentage of generated questions correctly mapped to selected syllabus content.

### Marks Accuracy

```text
Generated Marks = Requested Marks
```

### Teacher Acceptance Rate

Percentage of generated questions accepted without modification.

### Duplicate Rate

Percentage of questions rejected due to excessive similarity.

### Difficulty Accuracy

Comparison between predicted difficulty and observed student performance.

### Time Estimation Accuracy

Comparison between estimated and actual solving time.

---

# 🚀 Development Roadmap

## Phase 1 — MVP

### Target

CBSE Class 9 and 10.

### Subjects

- Mathematics
- Science
- English

### Features

- Board selection
- Class selection
- Subject selection
- Chapter selection
- Custom marks
- Difficulty
- Question types
- AI generation
- RAG
- Blueprint generation
- Question validation
- Answer key
- Marking scheme
- Teacher editing
- PDF export

---

## Phase 2 — Assessment Platform

Add:

- Question bank
- Multiple paper versions
- Duplicate detection
- Paper quality scoring
- Time estimation
- Student accounts
- Online tests
- Results
- Performance analytics

---

## Phase 3 — Multi-Board

Add:

- ICSE
- Maharashtra SSC
- Karnataka
- Gujarat
- UP
- MP
- Rajasthan
- Additional State Boards

---

## Phase 4 — Personalized Learning

Add:

- Personalized practice
- Weak-topic detection
- Adaptive testing
- Student mastery tracking
- AI revision recommendations

---

## Phase 5 — AI Examiner

Add:

- Handwritten answer recognition
- OCR/Vision
- AI answer evaluation
- Automated marking
- Feedback generation
- Difficulty calibration

---

# 🔮 Future Scope

Potential future features include:

## AI Tutor

Students can ask questions and receive explanations.

## AI Doubt Solver

Students can upload a question or image.

## AI Revision Planner

Generate personalized revision plans based on:

- Exam date
- Weak topics
- Available study time
- Past performance

## Learning Gap Detection

Identify conceptual gaps rather than only incorrect answers.

## Predictive Analytics

Estimate readiness based on historical performance.

## LMS Integration

Integrate with:

- Learning Management Systems
- Institute portals
- Online classroom systems

---

# 🌟 Long-Term Vision

BoardAI should evolve beyond a question-paper generator into a complete **AI Assessment & Learning Intelligence Platform**.

```text
                  BOARD KNOWLEDGE
                        │
                        ▼
               ASSESSMENT BLUEPRINT
                        │
                        ▼
               AI QUESTION GENERATION
                        │
                        ▼
                QUALITY VALIDATION
                        │
                        ▼
                     EXAM
                        │
                        ▼
                STUDENT ATTEMPT
                        │
                        ▼
                 AI EVALUATION
                        │
                        ▼
               PERFORMANCE ANALYSIS
                        │
                        ▼
               LEARNING GAP DETECTION
                        │
                        ▼
              PERSONALIZED PRACTICE
                        │
                        ▼
                   NEW TEST
                        │
                        └───────────────↺
```

The ultimate objective is a feedback loop where assessment data continuously improves the quality and personalization of future assessments.

---

# 🎯 Project Objectives

### Primary Objective

Develop an AI-powered platform capable of generating customized, board-aligned assessments for multiple educational boards.

### Secondary Objectives

1. Automate question-paper creation.
2. Support chapter-level customization.
3. Support custom marks and duration.
4. Generate board-appropriate question types.
5. Generate answer keys.
6. Generate marking schemes.
7. Validate AI-generated questions.
8. Detect duplicate questions.
9. Estimate paper difficulty.
10. Estimate paper completion time.
11. Analyze student performance.
12. Generate personalized practice.
13. Support multiple educational boards.
14. Create a scalable assessment architecture.

---

# 💻 Getting Started

## Prerequisites

Install:

- Node.js
- Python 3.11+
- PostgreSQL
- Git

Optional:

- Docker
- Docker Compose

---

## Clone Repository

```bash
git clone <repository-url>
cd boardai
```

---

## Backend Setup

```bash
cd backend

python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### macOS/Linux

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run backend:

```bash
uvicorn app.main:app --reload
```

---

## Frontend Setup

```bash
cd frontend

npm install

npm run dev
```

---

# 🔑 Environment Variables

Create a `.env` file.

Example:

```env
DATABASE_URL=

LLM_API_KEY=

EMBEDDING_API_KEY=

VECTOR_DATABASE_URL=

SECRET_KEY=

ENVIRONMENT=development
```

Never commit secrets to Git.

Use:

```text
.env
```

in `.gitignore`.

---

# 🧩 Development Workflow

Recommended development order:

```text
1. Authentication
        ↓
2. Board Management
        ↓
3. Syllabus Management
        ↓
4. Question Database
        ↓
5. Assessment Blueprint
        ↓
6. RAG
        ↓
7. AI Question Generator
        ↓
8. Validation Engine
        ↓
9. Paper Assembly
        ↓
10. Answer Key
        ↓
11. Marking Scheme
        ↓
12. Teacher Dashboard
        ↓
13. PDF Export
        ↓
14. Student Tests
        ↓
15. Analytics
```

---

# 🧠 Core Design Principles

## 1. AI should generate, not control everything

Use deterministic code wherever exact validation is possible.

## 2. Board rules must be configurable

Never hardcode one board's rules into the entire application.

## 3. Teacher remains in control

AI output must be editable and reviewable.

## 4. Use RAG for grounding

The AI should retrieve relevant educational information instead of relying entirely on model memory.

## 5. Use structured outputs

Questions should be returned as structured data.

## 6. Keep the system modular

New boards and subjects should be addable without rewriting the core engine.

## 7. Learn from student performance

Actual student data should eventually improve difficulty calibration.

---

# 🏆 What Makes BoardAI Different?

Generic AI:

```text
Prompt
 ↓
LLM
 ↓
Questions
```

BoardAI:

```text
Teacher Requirements
        ↓
Board Rules
        ↓
Syllabus
        ↓
Assessment Blueprint
        ↓
RAG
        ↓
Question Generation
        ↓
AI Validation
        ↓
Rule Validation
        ↓
Paper Assembly
        ↓
Answer Key
        ↓
Marking Scheme
        ↓
Teacher Review
        ↓
Student Performance
        ↓
Personalized Assessment
```

The goal is not simply to generate more questions.

The goal is to generate **appropriate questions under explicit educational constraints**.

---

# 📌 Example Use Case

### Teacher Request

```text
Create a 30-mark CBSE Class 10 Science paper.

Chapters:
2, 3 and 4.

Difficulty:
Board Level.

Duration:
60 minutes.

Include:
6 MCQs,
short-answer questions,
application-based questions,
and one case study.

Give slightly higher weightage to Chapter 3.
```

### BoardAI

```text
1. Parses request
2. Validates board
3. Loads syllabus
4. Loads assessment rules
5. Creates blueprint
6. Calculates marks
7. Retrieves relevant knowledge
8. Generates questions
9. Validates questions
10. Removes duplicates
11. Checks difficulty
12. Checks time feasibility
13. Creates paper
14. Generates answer key
15. Generates marking scheme
16. Presents paper to teacher
```

---

# 📜 License

License to be decided based on project requirements.

Possible options:

- MIT
- Apache 2.0
- Proprietary
- Academic/Research License

---

# 👥 Contributors

Add project contributors here.

```text
Project Team
------------
Priyanshu Singh
```

---

# 📬 Contact

For questions, suggestions, or collaboration:

```text
Email: <priyaanshu128912@gmailcom>
GitHub: <[github-profile](https://github.com/Celest14l/)>
```

---

# ⭐ Final Vision

**BoardAI aims to make assessment creation faster, more structured, more personalized, and more data-driven.**

The platform begins with a simple requirement:

> **"Create a 30-mark paper from Chapters 2, 3 and 4."**

But underneath that simple request is an intelligent assessment engine capable of understanding:

- Which board?
- Which class?
- Which subject?
- Which syllabus?
- Which academic year?
- Which chapters?
- How many marks?
- Which question types?
- What difficulty?
- Which competencies?
- What chapter weightage?
- How much time does the student have?
- Is the paper balanced?
- Are the questions valid?
- Is the marking scheme appropriate?
- What does the student's performance indicate?
- What should the student practice next?

The ultimate goal is to create a system where:

> **Teachers define the assessment. AI builds it. Rules validate it. Students attempt it. AI evaluates it. Analytics understand it. And the system uses those insights to create better learning experiences.**

---

## 🚧 Project Status

**Status:** Planning / Development

The initial MVP will focus on:

**CBSE → Classes 9 & 10 → Mathematics, Science & English → Custom AI Question Papers**

Additional boards, subjects, student analytics, adaptive testing, and AI answer-sheet evaluation will be introduced incrementally.
