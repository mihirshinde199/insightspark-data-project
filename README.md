# 📊 InsightSpark Data Engineering & Analysis Project

This project was developed as part of InsightSpark’s collaboration with CBA, focusing on structured and unstructured data handling, data privacy, and database design. It includes four key tasks that simulate real-world data engineering responsibilities.

---

## ✅ Tasks Overview

### 🔹 Task 1: Supermarket Transaction Analysis

* **Goal:** Analyze supermarket transaction data to answer business-related questions.
* **Tools Used:** Excel / LibreOffice Calc
* **Key Steps:**

  * Filtered transactions to count apple purchases made in cash.
  * Calculated total cash spent on apples.
  * Summed sales at Bakershire store by non-member customers.

### 🔹 Task 2: Mobile Customer Data Anonymisation

* **Goal:** Protect personal data while retaining analytical value.
* **Techniques Used:**

  * Masking (usernames, emails, credit card numbers)
  * Removal (customer IDs, location data)
  * Categorisation (age and salary bins)
  * Tokenisation (employer, job titles)
  * Noise addition (date fields)

### 🔹 Task 3: Twitter Data Insight Proposal

* **Goal:** Explore how @CommBank’s public Twitter data could be leveraged for insights.
* **Tools:** Twitter API, Python (requests, pandas)
* **Highlights:**

  * Identified key data points from the API (tweets, replies, metrics).
  * Proposed use cases such as sentiment analysis, brand engagement, topic tracking.

### 🔹 Task 4: Twitter Data Database Design

* **Goal:** Design a normalized schema to store tweet data and its interactions.
* **Deliverables:**

  * Defined tables for Tweets, Users, Replies, Quote Retweets, Mentions.
  * Outlined primary keys and table relationships.
  * Ensured low redundancy and high data integrity.

---

## 📁 Project Structure

```
insightspark-data-project/
├── Task 1 - Supermarket Analysis/
│   ├── supermarket_transactions.xlsx
│   ├── Task 1 - Example Answer - Spreadsheet.ods
│   └── README.md
├── Task 2 - Data Anonymisation/
│   ├── mobile_customers.xlsx
│   ├── model_answer_csv.csv
│   └── README.md
├── Task 3 - Twitter Data Insights/
│   ├── Commen_wealth_bank.ipynb
│   ├── screenshots/
│   └── README.md
├── Task 4 - Database Design/
│   └── twitter_database_design.md
├── LICENSE
└── README.md
```

---

## 💻 Technologies Used

* Python (pandas, requests)
* Excel / LibreOffice Calc
* Twitter API v2
* Data anonymisation best practices
* Relational database schema design

---

## 🧠 Key Learnings

* Applied practical data engineering tasks using real-world datasets.
* Understood the process of anonymising sensitive customer information.
* Learned how to extract insights from unstructured social media data.
* Designed clean, scalable database structures for dynamic data.

---

## 📄 License

This project is for **educational purposes only**. It is not affiliated with Commonwealth Bank of Australia or InsightSpark.
