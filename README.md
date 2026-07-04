# EduGenie Learning Assistant – ER Diagram Explanation

## Entities Involved

The diagram consists of six primary entities:

### USER
Represents students or learners using the EduGenie Learning Assistant platform.

### USER_QUERY
Represents educational requests submitted by users, such as question answering, explanations, quiz generation, summarization, and learning recommendations.

### AI_RESPONSE
Represents AI-generated educational responses produced by Gemini 1.5 Pro or LaMini-Flan-T5 models.

### QUIZ
Represents quiz records generated from educational topics or passages.

### SUMMARY
Represents summarized educational content generated from lengthy text inputs.

### LEARNING_PATH
Represents personalized learning recommendations and structured study paths generated for users.

---

## Primary Keys

- **USER**: `user_id` (PK) uniquely identifies each user  
- **USER_QUERY**: `query_id` (PK) uniquely identifies each educational request  
- **AI_RESPONSE**: `response_id` (PK) uniquely identifies each AI response  
- **QUIZ**: `quiz_id` (PK) uniquely identifies each quiz  
- **SUMMARY**: `summary_id` (PK) uniquely identifies each summary  
- **LEARNING_PATH**: `path_id` (PK) uniquely identifies each learning path  

---

## Relationships

- **USER → USER_QUERY**: One-to-Many  
  One user can submit multiple queries.

- **USER_QUERY → AI_RESPONSE**: One-to-One  
  Each query generates one AI response.

- **USER_QUERY → QUIZ**: One-to-Many  
  One query can generate multiple quiz questions.

- **USER_QUERY → SUMMARY**: One-to-Many  
  One query can produce multiple summaries.

- **USER_QUERY → LEARNING_PATH**: One-to-Many  
  One query can generate multiple learning recommendations.

---

## Foreign Keys

- **USER_QUERY**: `user_id` (FK) → USER.user_id  
- **AI_RESPONSE**: `query_id` (FK) → USER_QUERY.query_id  
- **QUIZ**: `query_id` (FK) → USER_QUERY.query_id  
- **SUMMARY**: `query_id` (FK) → USER_QUERY.query_id  
- **LEARNING_PATH**: `query_id` (FK) → USER_QUERY.query_id  

---

## User Attributes

- `user_id`: Unique identifier  
- `name`: User name  
- `email`: Email address  
- `password`: Encrypted password  
- `created_at`: Account creation timestamp  

---

## User Query Attributes

- `query_id`: Primary key  
- `user_id` (FK): Linked user  
- `query_type`: QnA, Explanation, Quiz, Summary, Recommendation  
- `query_text`: Input topic or question  
- `created_at`: Timestamp  

---

## AI Response Attributes

- `response_id`: Primary key  
- `query_id` (FK): Related query  
- `response_text`: AI-generated answer  
- `model_used`: Gemini / LaMini-Flan-T5  
- `created_at`: Timestamp  

---

## Quiz Attributes

- `quiz_id`: Primary key  
- `query_id` (FK): Related query  
- `question_text`: MCQ question  
- `option_a`, `option_b`, `option_c`, `option_d`  
- `correct_answer`: Correct option  
- `created_at`: Timestamp  

---

## Learning Path Attributes

- `path_id`: Primary key  
- `query_id` (FK): Related query  
- `topic`: Learning topic  
- `difficulty_level`: Beginner / Intermediate / Advanced  
- `recommended_resources`: Suggested materials  
- `created_at`: Timestamp  

---

## Cardinality

- One USER → Many USER_QUERY  
- One USER_QUERY → One AI_RESPONSE  
- One USER_QUERY → Many QUIZ  
- One USER_QUERY → Many SUMMARY  
- One USER_QUERY → Many LEARNING_PATH  

---

## Normalization and Structure

The ER diagram follows normalization principles by separating users, queries, AI outputs, quizzes, summaries, and learning paths into distinct entities. This reduces redundancy and improves scalability and data integrity.

---

## Use Case Coverage

- User registration and authentication  
- QnA and explanations  
- Quiz generation  
- Summarization  
- Learning recommendations  
- AI response tracking  
- Educational workflow management  
- Real-time learning assistance  

---

## Scalability and Cloud Relevance

This modular structure is suitable for cloud databases like MySQL, PostgreSQL, MongoDB, or Firebase.

Future enhancements supported:
- Student progress tracking  
- Voice-based learning  
- Multilingual support  
- LMS integration  
- Mobile applications  
- Real-time collaboration  
- AI analytics dashboards  
- Adaptive learning systems  
