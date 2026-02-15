# Swachh Saathi – System Design Document

## 1. System Architecture

Swachh Saathi follows a Client-Server Architecture:

Frontend (Web/Mobile)
        ↓
REST API (Backend - Flask/FastAPI)
        ↓
Database
        ↓
AI Processing Layer

---

## 2. Technology Stack

Backend:
- Python
- Flask / FastAPI
- REST APIs

Frontend:
- HTML
- CSS
- JavaScript

Database:
- SQLite (development)
- PostgreSQL (production)

AI Layer:
- TensorFlow / PyTorch
- Pre-trained image classification model
- NLP model for complaint categorization

Deployment:
- Render / Railway / AWS / GCP (free tier)

---

## 3. Component Design

### 3.1 Frontend

- Complaint submission form
- User dashboard
- Complaint tracking page
- Admin dashboard

### 3.2 Backend APIs

POST /register  
POST /login  
POST /submit-complaint  
GET /complaints  
PUT /update-status  

### 3.3 Database Design

Users Table:
- id
- name
- email
- password_hash
- role
- created_at

Complaints Table:
- id
- user_id
- image_path
- description
- location_lat
- location_long
- severity
- priority_score
- status
- created_at

---

## 4. AI Workflow

1. User uploads image
2. Backend sends image to AI model
3. AI predicts issue type and severity
4. NLP processes complaint text
5. Priority score calculated
6. Data stored in database
7. Notification sent to admin

---

## 5. Security Design

- JWT-based authentication
- Role-based access control
- Input validation
- Encrypted password storage (bcrypt)
- HTTPS deployment

---

## 6. Scalability Considerations

- Modular AI service
- Microservice-ready backend
- Database indexing on location and priority
- API rate limiting

---

## 7. Future Enhancements

- Real-time map heatmap visualization
- Worker tracking integration
- Predictive sanitation analytics
- Multilingual chatbot support
