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


# Executive Summary

This project investigates the relationships between the All Share Price Index (ASPI) and various macroeconomic indicators, explores the predictive power of these variables, and assesses the influence of international stock markets on the Sri Lankan stock market. The analysis is based on a comprehensive dataset compiled from multiple sources, including the Colombo Stock Exchange, the Central Bank of Sri Lanka, X-Rates website(web scrape) and Alpha Vantage API.

#### Data Acquisition Techniques

The analysis relies on a comprehensive dataset compiled from multiple reputable sources. Data acquisition techniques included both static and dynamic methods to ensure a robust and diverse data collection.

1. **Static Data Acquisition** 
   - **Historical Values from Colombo Stock Exchange**: Daily closing values for ASPI and S&P SL20 were sourced from the official Colombo Stock Exchange website. This ensured reliable and accurate historical market data.
   - **Macroeconomic Indicators from the Central Bank of Sri Lanka**: Interest rates and inflation rates were obtained from the Central Bank of Sri Lanka's official website. This provided authoritative and up-to-date economic data.
   - **Access to CSE Data**: As an investor in the CSE, I have privileged access to detailed market data, enhancing the reliability and depth of the analysis.

2. **Dynamic Data Acquisition** 
   - **API Data Retrieval**: Data for the London and Shanghai stock markets were dynamically acquired using the Alpha Vantage API. This approach enabled the collection of real-time and historical stock market data from these international markets, facilitating comparative analysis.
   
   - **Web Scraping Exchange Rates**: Exchange rates from 01/01/2019 to 30/04/2024 were dynamically acquired by web scraping from the X-Rates website. This method involved extracting the daily USD/LKR exchange rate data to ensure accurate and comprehensive currency information.

**Sources and Access Dates**
- **Interest Rates**: Central Bank of Sri Lanka - Website (https://www.cbsl.lk/eResearch/Modules/RD/SearchPages/CMB_LendingAndDeposit.aspx), accessed on 07/05/2024.
- **Inflation Rates**: Central Bank of Sri Lanka - Website (https://www.cbsl.gov.lk/measures-of-consumer-price-inflation), accessed on 07/05/2024.
- **Exchange Rates**: Exchange rates were web scraped from the **X-Rates website** (https://www.x-rates.com/historical/?from=LKR&amount=1&date=), accessed on 20/05/2024.
- **Sri Lankan Stock Market Data**: ASPI and S&P SL20 values from the Colombo Stock Exchange official website (https://cse.lk/), accessed on 08/05/2024.
- **International Stock Market Data**: Acquired using the Alpha Vantage API (https://www.alphavantage.co/), accessed on 07/05/2024. 


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
```

# Example plots in the main project

### Observations from Summary Statistics, Box Plots and Histograms
<img width="1489" height="490" alt="image" src="https://github.com/user-attachments/assets/f8c7c4d8-e787-442f-95e1-141a20981943" />

### **Time series data Visualization**
<img width="871" height="396" alt="image" src="https://github.com/user-attachments/assets/ab060d70-3dcd-4d4d-9726-a27ac916f3fc" />

### Sri Lankan Stock Market Indices Over Time
<img width="1179" height="626" alt="image" src="https://github.com/user-attachments/assets/31b3b917-540c-4f1b-acf8-03f438c7dceb" />

### Correlation Matrix
<img width="1181" height="947" alt="image" src="https://github.com/user-attachments/assets/332229ec-f26b-42d3-bf63-abe35fd181f1" />

### Actual vs Predicted
<img width="715" height="472" alt="image" src="https://github.com/user-attachments/assets/def2375b-ed68-444d-8d68-e5773b4d9a80" />

### Prediction with Random Forest model
<img width="945" height="392" alt="image" src="https://github.com/user-attachments/assets/fe6aa337-511e-4fa0-9eee-c6fb36fb3eaa" />

### Residual analysis
<img width="1491" height="545" alt="image" src="https://github.com/user-attachments/assets/2838fd3a-0447-41b2-974e-f3084d8bc023" />

### VAR Model forcast
<img width="871" height="396" alt="image" src="https://github.com/user-attachments/assets/de553eeb-f0b2-47e6-ad1a-743890d7c934" />
<img width="982" height="973" alt="image" src="https://github.com/user-attachments/assets/143f2d24-1098-4002-9cd8-206d82553122" />
<img width="1193" height="606" alt="image" src="https://github.com/user-attachments/assets/014fe7e0-965a-495c-bdba-4672b7cd455b" />







