# **Project Requirement Document: Real-Time Sentiment Analysis System**

## **1\. Executive Summary**

**Project Name: Real-Time Sentiment Analysis Dashboard Objective: Build a live system that ingests social media feeds (e.g., Twitter/X, Reddit) or product reviews to classify sentiment (Positive, Negative, Neutral) in real-time. Goal: Provide hands-on experience with NLP, data engineering, and stream processing while creating a tool useful for brand monitoring.**

## **2\. User Roles**

* **Marketing Manager: Monitors the "Pulse" of the brand to gauge public reaction.**  
* **Product Manager: Tracks sentiment specific to feature releases or product launches.**  
* **Customer Support: Receives alerts for high-priority negative feedback to intervene quickly.**

## **3\. Functional Requirements (MVP)**

* **FR1 \- Ingestion: Fetch live data via APIs (Twitter API v2, Reddit PRAW) or simulate a stream.**  
* **FR2 \- Preprocessing: Clean text (remove URLs, handles, emojis) and normalize (handle contractions).**  
* **FR3 \- Classification: categorize text as Positive, Neutral, or Negative with a confidence score.**  
* **FR4 \- Visualization: Display a live scrolling feed and real-time charts (e.g., sentiment trends over time).**  
* **FR5 \- Alerts: Flag "Highly Negative" posts exceeding a confidence threshold.**

## **4\. Non-Functional Requirements**

* **Latency: End-to-end processing within \< 2 seconds.**  
* **Scalability: Handle spikes of 100+ posts per minute.**  
* **Accuracy: Target F1-score \> 0.80 on standard validation sets.**

## **5\. Technology Stack**

* **Language: Python 3.11+**  
* **Data Ingestion: Tweepy (Twitter) or PRAW (Reddit)**  
* **Message Broker: Apache Kafka or Redis Pub/Sub (for buffering streams)**  
* **NLP Model: Hugging Face Transformers (`cardiffnlp/twitter-roberta-base-sentiment`)**  
* **Backend: FastAPI (for high-performance async handling)**  
* **Frontend: Streamlit (for rapid dashboard development)**  
* **Containerization: Docker**

## **6\. Architecture Overview**

1. **Producer: Connects to external API and pushes raw text to the Message Broker.**  
2. **Consumer (Worker): Pulls messages, runs the NLP model, and saves results.**  
3. **Database: Stores processed sentiment data (e.g., PostgreSQL or MongoDB).**  
4. **UI: Queries the database/backend to display live metrics.**

## **7\. Low level Design and Component desing**

<img width="1824" height="2336" alt="LLD Diagram" src="https://github.com/user-attachments/assets/d04a96b9-749e-4e98-807c-1e951e163f73" />


