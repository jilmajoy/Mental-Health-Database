# Mental-Health-Database
Project Overview

This project is a relational database system designed for The Mindful Health Clinic, a telehealth service specializing in outpatient therapy for anxiety and mood disorders. The clinic faced challenges such as inefficient patient record management, therapist scheduling issues, and billing complexities.

The goal of this project is to centralize clinic operations by integrating patient records, therapy sessions, medication management, billing, and insurance claims into a single PostgreSQL database. Additionally, data analysis and visualization were performed using Python (Jupyter Notebook) to generate meaningful business insights.

Features

Patient Management: Stores and manages patient demographics, medical history, and therapy sessions.
Therapist Scheduling: Tracks therapist availability and appointments.
Treatment Tracking: Records therapy sessions, follow-ups, and prescribed medications.
Billing & Claims Processing: Manages invoices, insurance claims, and payments.
Data Analysis & Visualization: Provides insights into clinic performance, therapy trends, insurance claim approvals, and patient demographics.
Tech Stack

Database: PostgreSQL
Programming Language: Python
Libraries Used: psycopg2, SQLAlchemy, Pandas, Matplotlib, Seaborn, Plotly (for interactive maps)
Development Tools: Jupyter Notebook

Database Schema

The database consists of 10 interconnected tables:

Patient: Stores patient demographics and medical history.
Therapist: Holds therapist details such as specialization and qualification.
TherapistSchedule: Tracks therapist availability.
Therapy: Logs therapy sessions and follow-up requirements.
Medication: Records prescribed medications.
MentalHealthScreening: Stores screening assessments like PHQ-9 and GAD-7 scores.
Insurance: Contains patient insurance details.
Claim: Manages insurance claims and approvals.
Bill: Stores invoices for therapy sessions.
BillPayment: Tracks payments made by patients or insurance.
How to Run the Project

1. Setting Up the Database
Install PostgreSQL and create a new database:
CREATE DATABASE mental_health_db;
Execute the SQL script to create tables and insert sample data:
psql -U your_username -d mental_health_db -f create_tables.sql
psql -U your_username -d mental_health_db -f insert_data.sql
2. Connecting to the Database with Python
Install dependencies:
pip install psycopg2 SQLAlchemy pandas matplotlib seaborn plotly
Run the Python script for data analysis:
python analysis.py
3. Querying the Database
Example SQL query to retrieve active patients:
SELECT first_name, last_name FROM Patient WHERE patient_id IN 
(SELECT DISTINCT patient_id FROM Insurance WHERE is_active = TRUE);

Data Analysis Insights

Most common therapy session duration: 60-90 minutes
Average patient age: 35 years
Top insurance providers with highest approval rates: Aetna, Anthem Blue Cross, Cigna
Most common mental health condition treated: Depression
Claim approval rate by state: Varies significantly, with some states having 100% approval and others near 0%

Future Improvements

User Interface Development: A Flask or Streamlit-based web application for easy interaction.
Security Enhancements: Implement HIPAA-compliant security measures for patient data protection.
Predictive Analytics: Using machine learning to analyze patient outcomes based on therapy sessions and medications.

Author
Jilma Joy
DTSC 691: Applied Data Science
Date: 10/13/2024

