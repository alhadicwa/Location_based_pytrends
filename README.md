# Google Trends Interest Analysis: Sheraton (US-NY)

This project utilizes the `pytrends` library to fetch and analyze Google Trends data for the keyword **"Sheraton"** specifically within the **New York (US-NY)** region. It compares search interest between February 2024 and February 2025.

## 📊 Overview
The script performs the following:
1. Connects to Google Trends via the `TrendReq` API.
2. Pulls a 13-month dataset to ensure a consistent normalization scale.
3. Extracts specific weekly data points for February 2024 and February 2025.
4. Calculates the arithmetic mean for both periods to provide a comparative "Interest Score."

## 🧬 Data Logic & Normalization
Google Trends does not provide raw search volume. Instead, it provides a **Relative Interest Score**:
* **The 100 Peak:** The engine finds the maximum search interest point within the requested timeframe (Feb 2024 – Feb 2025) and assigns it a value of 100.
* **Relative Scaling:** All other data points are scaled as a percentage of that peak. (e.g., a score of 50 means interest was half as high as the peak).
* **Time Aggregation:** Since the timeframe exceeds 90 days, Google automatically aggregates data into **weekly buckets** to maintain data integrity.

## 🚀 How to Use
1. **Install Dependencies:**
   ```bash
   pip install pytrends pandas
2.Run the Script:
The script includes a time.sleep(10) delay to respect Google's rate limits and prevent 429 Too Many Requests errors.
## Sample Output:
--- Final Summary for 'Sheraton' in US-NY ---
February 2024 Average Score: 43.50
February 2025 Average Score: 42.75
