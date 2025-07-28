# 🔹 Task 2: Mobile Customer Data Anonymisation

## 🔢 Objective
Anonymise sensitive mobile customer data while preserving its analytical utility for data science use.

## 📁 Files
- `mobile_customers.xlsx` — Original dataset
- `model_answer_csv.csv` — Final anonymised version

## ⚖️ Techniques Applied
- **Removal:** `customer_id`, `current_location`, `address`
- **Masking:** `username`, `email`, `credit_card_number`, `credit_card_security_code`
- **Noise Addition:** `birthdate`, `date_registered`
- **Tokenisation:** `credit_card_provider`, `credit_card_expire`, `employer`, `job`
- **Categorisation:** `age` and `salary` into logical bins

## 📈 Benefits of Anonymisation
- Protects personal identity
- Preserves statistical distribution
- Enables safe downstream data processing

## 📅 Tools Used
- Excel / LibreOffice Calc

---

> This task demonstrates practical understanding of data privacy and anonymisation techniques essential for modern data engineers and analysts.
