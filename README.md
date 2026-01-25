# 📉 Amazon Web Scraper & Price Tracker

A Python-based automation tool designed to track product prices on Amazon over time. This project scrapes real-time data, stores it for historical analysis, and sends automated email alerts when a price drop occurs.

## 📌 Project Overview
The goal of this project was to apply **Data Analysis** and **Web Scraping** concepts to solve a real-world problem: monitoring price fluctuations to identify the best buying time. 

Instead of manually checking Amazon daily, this script automates the process, building a dataset of price history and notifying the user immediately when a target price is reached.

## 🛠️ Technologies & Tools Used
* **Python 3.x**: The core programming language.
* **BeautifulSoup4**: For parsing HTML and extracting data (Web Scraping).
* **Requests**: To fetch the HTML content from Amazon.
* **Pandas**: For data manipulation and reading the CSV dataset.
* **smtplib**: For sending automated email notifications (SMTP).
* **datetime & time**: For timestamping data and handling automation intervals.
* **CSV**: For persistent data storage.

## ⚙️ Key Features
1.  **Web Scraping**: Connects to Amazon using custom headers (to mimic a real browser) and extracts the product title and current price.
2.  **Data Cleaning**: 
    * Removes currency symbols (`$`) and extra whitespace.
    * Converts string data into numerical formats (`float`) for logic comparison.
3.  **Data Persistence**: Appends the scraped data (Product, Price, Date) into a CSV file without overwriting previous records, creating a historical dataset.
4.  **Automation**: Runs continuously (using a loop) to check prices every 24 hours.
5.  **Email Alert System**: checks if the price falls below a specific threshold (e.g., $20) and sends a "Buy Now" email notification with the product link.

## 🚀 How It Works
1.  The script sends a `GET` request to the Amazon product URL.
2.  It parses the page content to find the Title and Price elements.
3.  It cleans the data and gets the current date.
4.  It saves the new entry into `Amazon Web Scraping.csv`.
5.  **Logic Check**: 
    * If `Price < Target_Price`: It logs into Gmail (using an App Password) and sends an alert.
    * If `Price > Target_Price`: It continues monitoring.

## 📝 Usage Note
To run this script, you need to generate a **Google App Password** for the email sending function to work securely, as standard Gmail passwords are not supported for third-party apps.

---
**Author:** Mahmoud Khaled  
*Aspiring Data Analyst | Biophysics Graduate*
