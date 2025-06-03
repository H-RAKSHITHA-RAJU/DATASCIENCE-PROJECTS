# 🧠 Analyzing Students' Mental Health (SQL + CSV + Notebook Project)

This project investigates how accommodation type affects the **mental health** of interstate students using structured data and SQL-based analysis. The dataset includes key psychological and academic stress indicators for students.

---

## 🗂️ Project Directory Structure

Analyzing_students_mental_health/
├── mentalhealth.jpg # Cover image or infographic about student mental health
├── notebook.ipynb # Jupyter notebook for data exploration or visualization
├── students.csv # Dataset containing student survey responses
├── README.md # Project documentation (this file)
---

## 🎯 Objective

To examine how **interstate students'** accommodation status (`stay`: hostel vs. day scholar) impacts their:

- **Depression level** (PHQ - `todep`)
- **Self-compassion** (SCS - `tosc`)
- **Academic stress** (AS - `toas`)

---

## 📊 Metrics Analyzed

For each `stay` group:

- 📌 `count_int`: Total number of interstate students
- 📌 `average_phq`: Average PHQ (Patient Health Questionnaire) score
- 📌 `average_scs`: Average Self-Compassion Score
- 📌 `average_as`: Average Academic Stress score

All averages are rounded to two decimal places for clarity.

---

## 🧾 Dataset Overview (`students.csv`)

**Columns Used:**

| Column Name | Description |
|-------------|-------------|
| `inter_dom` | Student category (Interstate or Domestic) |
| `stay`      | Accommodation status (Yes = Hostel, No = Day Scholar) |
| `todep`     | PHQ (Depression) score |
| `tosc`      | Self-Compassion Score |
| `toas`      | Academic Stress score |

---

## 🧠 Core SQL Query

```sql
SELECT stay, 
       COUNT(*) AS count_int,
       ROUND(AVG(todep), 2) AS average_phq, 
       ROUND(AVG(tosc), 2) AS average_scs, 
       ROUND(AVG(toas), 2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;

📓 Jupyter Notebook (notebook.ipynb)

The notebook complements the SQL analysis by:

Loading and exploring the CSV data
Visualizing group-wise PHQ, SCS, and AS scores using graphs
Interpreting trends between hostel vs. day scholar students
🌐 Requirements

Python 3.x
Jupyter Notebook
pandas, matplotlib, seaborn
SQL environment (MySQL/PostgreSQL/SQLite or Python SQLite engine)
📌 Insights

This project helps:

Educational institutions identify mental health trends based on living situations
Guide support systems for interstate students
Lay the foundation for larger mental wellness research using structured survey data
🛠️ Author

H Rakshitha Raju
CMR Institute of Technology
Class of 2025

📈 Future Enhancements

Add support for Dom (domestic) students in comparative charts
Build a Streamlit dashboard for dynamic data filtering
Integrate sentiment analysis from student feedback (if available)
