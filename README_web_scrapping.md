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
