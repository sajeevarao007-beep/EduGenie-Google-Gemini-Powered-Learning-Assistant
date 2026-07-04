# 🧠 EduGenie Learning Assistant – AI Modules Description

---

## 📘 Explanation Module

EduGenie utilizes the **LaMini-Flan-T5** model, a lightweight yet powerful generative AI, to deliver educational content in a simplified and highly readable manner.

This model is specifically fine-tuned to:
- Provide concise and context-aware responses  
- Break down complex topics into simple language  
- Improve readability for beginners  

### 🎯 Key Benefits:
- Helps learners with minimal background knowledge  
- Ideal for school students and self-learners  
- Reduces cognitive overload by simplifying explanations  
- Acts as a reliable study companion for foundational learning  

👉 The integration of LaMini-Flan-T5 enables EduGenie to deliver clear, structured, and beginner-friendly explanations across multiple subjects.

---

## ❓ QnA Module

EduGenie is powered by **Google Gemini 1.5 Pro**, enabling high-quality question-answering capabilities.

### 🎯 Key Features:
- Handles general knowledge and academic questions  
- Provides accurate and context-aware answers  
- Supports multi-domain learning topics  
- Uses advanced reasoning and understanding  

👉 This module ensures learners receive precise, AI-driven assistance across various educational domains.

---

## 🧪 Quiz Module

The Quiz Module generates **multiple-choice questions (MCQs)** from a given passage.

### ⚙️ Working Process:
- Generates **3 MCQs per input passage**
- Each question contains **4 options**
- Uses Gemini model for contextual understanding
- Ensures realistic and meaningful distractors
- Outputs results in **structured JSON format**

### 🧾 Implementation Details:
- Sends a structured prompt to the model  
- Expects valid JSON output  
- Cleans response using `clean_json_block()` function  
- Parses cleaned JSON into Python list  
- Handles errors with detailed debug messages  

---

## 📝 Summary Module

This feature uses **Gemini’s generative capabilities** to convert long text into short, meaningful summaries.

### 🎯 Key Features:
- Converts long paragraphs into concise summaries  
- Retains core meaning and important points  
- Removes unnecessary repetition  
- Ideal for quick revision and exam preparation  

### ⚙️ Working:
- Sends structured prompt to Gemini  
- Receives summarized response  
- Ensures clarity and context preservation  

👉 Helps learners quickly understand and revise large content efficiently.

---

## 🧭 Learning Path Module

The Learning Path Module generates personalized learning recommendations using **Google Gemini**.

### 🎯 Key Features:
- Creates structured learning paths for any topic  
- Organizes content from beginner → advanced levels  
- Suggests helpful resources (videos, articles, books)  
- Adapts to learner’s knowledge level  

### ⚙️ Working:
- Uses `get_learning_recommendations()` function  
- Sends structured prompt to Gemini  
- Generates step-by-step learning roadmap  
- Handles API errors safely and returns fallback messages if needed  

👉 This module helps learners follow a guided and structured study plan.

---

## ✅ Summary

EduGenie integrates multiple AI modules to create a complete learning ecosystem:

- 📘 LaMini-Flan-T5 → Simple explanations  
- ❓ Gemini 1.5 Pro → Advanced QnA  
- 🧪 Quiz Generator → MCQ-based assessment  
- 📝 Summarization → Fast revision tool  
- 🧭 Learning Path → Personalized study roadmap  

Together, these modules make EduGenie a **powerful AI-based educational assistant**.
