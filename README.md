# 🕵️‍♂️ Fraud Detection Analysis

## 📘 Overview
This project explores **fraud detection patterns** using **SQL** and **Python (Pandas + SQLite)**.  
It focuses on analyzing transactional data to identify which transaction types, channels, and merchant categories are most associated with fraudulent behavior.  

The analysis is divided into **five high-impact business questions**, each supported by SQL queries and data validation using Pandas.

---

## 🧰 Tools & Technologies
- **Python:** Pandas, SQLite3  
- **SQL:** Data querying and aggregation  
- **Jupyter Notebook:** For interactive analysis and visualization  

---

## 🔥 High-Impact Business Questions
1. **Immediate Fraud Flags:**  
   → Which transaction types and payment channels have the highest fraud rates? 💳  

2. **Behavioral Analysis:**  
   → Do fraudulent transactions have higher velocity scores or shorter time gaps between transactions? ⚡  

3. **Geographic & Device Risk:**  
   → Is there a correlation between `geo_anomaly_score` and confirmed fraud? 🌍  

4. **Fraud Category:**  
   → What is the most common type of fraud (`fraud_type`) in the dataset? 🕵️‍♂️  

5. **Merchant Risk:**  
   → Which `merchant_category` shows the highest frequency of fraud? 🏪  

---

## 🧹 Data Cleaning
- Checked for missing values using `df.isnull().sum()`  
- Filled missing values in:
  - `fraud_type` → replaced with `'not_fraud'`  
  - `time_since_last_transaction` → replaced with `0`  
- Verified no remaining nulls before running SQL queries  

---

## 📊 Key Findings

### 🚨 1. Immediate Fraud Flags
- Highest fraud rate: **payment via wire_transfer (~3.65%)**
- Transfers and withdrawals are close behind (~3.6%)
- **Wire transfer** and **UPI** channels show slightly higher risk  

### 🧠 2. Behavioral Analysis
| Metric | Fraud | Non-Fraud | Observation |
|:--|:--:|:--:|:--|
| avg_velocity | 10.51 | 10.50 | No clear difference |
| avg_time_gap | 1.77 | 1.51 | Slightly longer gap before fraud |

✅ *Fraudulent transactions are not more sudden or rapid than normal ones.*

---

### 🌍 3. Geographic & Device Risk
- Correlation between `geo_anomaly_score` and `is_fraud` ≈ **0.00**  
- Fraud rate in `high_geo` and `normal_geo` are identical (~3.59%)  
✅ *No geographic pattern of fraud detected.*

---

### 🏷️ 4. Fraud Category
- Only one fraud type: **`card_not_present`**  
⚙️ *Dataset simulates card-not-present (CNP) fraud — common in online transactions.*

---

### 🏪 5. Merchant Risk
| Merchant Category | Fraud Rate |
|:--|:--:|
| 🎭 Entertainment | 3.61% |
| 💼 Other | 3.61% |
| ✈️ Travel | 3.60% |
| 🛒 Grocery | 3.60% |
| 🏬 Retail | 3.58% |

📉 *Fraud rates are nearly identical across merchants → merchant type doesn’t strongly influence risk.*

---

## 🧠 Overall Summary
- Overall fraud rate: **~3.6%**  
- No strong numerical correlation with fraud (e.g., velocity_score, geo_anomaly_score ≈ 0)  
- Fraud type = **card_not_present**  
- SQL + Python provided clear, data-backed insights into fraud patterns  

---

## 🧾 Key Skills Demonstrated
- Data cleaning and validation with Pandas  
- SQL query design and execution via SQLite  
- Analytical storytelling using Python and SQL integration  
- Business insight extraction from transaction data  

---

## 📂 Project Structure
