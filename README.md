# Exploring Web Analytics via Python – API, Scraping, and Forecasting Practice

This project is a hands-on exercise designed to showcase various data analytics techniques using Python. It focuses on real-world data sourcing methods such as web scraping and API integration, along with data cleaning, exploratory data analysis (EDA), and forecasting models. The datasets used are based on real data sources; however, the forecasts and insights generated in this project are purely educational and should not be used for making real-world decisions. The primary aim is to demonstrate proficiency in Python for data-driven problem solving.

---

## 📌 Objectives

- Practice and demonstrate skills in:
  - Web scraping with BeautifulSoup
  - API calls and JSON parsing
  - Data manipulation with Pandas
  - Forecasting using time series techniques
  - Visualization using Matplotlib/Seaborn
- Apply real-world data to mock business/analytical scenarios
- Build a structured data analytics project for portfolio purposes

---

## 🛠️ Technologies Used

- Python 3.x
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib / Seaborn
- Requests
- BeautifulSoup
- Statsmodels / scikit-learn (if applicable)

---

## 📂 Project Structure

# Web Scraping – USD to LKR Exchange Rate (2019)

This script scrapes historical exchange rate data (USD to LKR) from [x-rates.com](https://www.x-rates.com/) for the period from **January 1, 2019 to April 30, 2019**.

It is part of a broader analytics project designed to demonstrate Python-based data acquisition techniques using web scraping.

---

## 🧠 What the Script Does

- Iterates through each date in the specified range.
- Sends a GET request to `x-rates.com` for the historical exchange rate page.
- Parses the returned HTML using **BeautifulSoup**.
- Locates the table containing exchange rates.
- Extracts the exchange rate for **US Dollar (USD)** against **Sri Lankan Rupee (LKR)**.
- Appends the data to a list and converts it into a **Pandas DataFrame**.

---

## 🔧 Technologies Used

- `requests` – To send HTTP requests.
- `BeautifulSoup` – For HTML parsing and extraction.
- `pandas` – To store and handle tabular data.
- `datetime` – For handling date ranges.

---

## 📁 Output

- A preview of the data is printed to the console using `df.head()`.
- You can easily export it to CSV with:

```python
df_usd.to_csv("usd_lkr_exchange_rates.csv", index=False)
```
# API Request – Shanghai Stock Data via Alpha Vantage

This script demonstrates how to fetch **daily stock market data** for the Shanghai stock symbol `600104.SHH` using the **Alpha Vantage API**. The purpose is to showcase API integration in Python and basic data conversion for time-series analysis.

---

## 🧠 What the Script Does

- Connects to the **Alpha Vantage** API using a free API key.
- Sends a request to the `TIME_SERIES_DAILY` endpoint for the full historical daily time series.
- Converts the JSON response into a structured `pandas` DataFrame.
- Lays the groundwork for time-series analysis, forecasting, or visualization.

---

## 🔧 Technologies Used

- `requests` – For making HTTP GET requests.
- `pandas` – For converting and handling JSON data.

---

## 🌐 API Source

- **Provider**: [Alpha Vantage](https://www.alphavantage.co)
- **Endpoint**: `https://www.alphavantage.co/query?function=TIME_SERIES_DAILY`
- **Symbol Used**: `600104.SHH` (Shanghai-listed stock)
- **Authentication**: Requires a free API key from Alpha Vantage.

---

## 📁 Output

- A raw DataFrame `df_shang` containing the nested JSON time series data.
- (Optional) You can transform and save this data as CSV:

```python
df_shang.to_csv("shanghai_stock_data.csv")


