# 📉 Automated Amazon Web Scraper & Price Tracker

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-4B8BBE?style=for-the-badge&logo=python&logoColor=white)

## 📋 Project Overview
A Python-based automation tool designed to track product prices on Amazon over time. This project bridges the gap between Web Scraping and Data Analysis to solve a real-world problem: monitoring price fluctuations to identify the optimal buying time without manual intervention.

## 🎯 Objective
Instead of manually checking Amazon daily, this script automates the entire process. It continuously builds a historical dataset of price changes and immediately notifies the user via email when a specific target price is reached.

---

## ⚙️ Key Features & Technical Workflow

### 1. Web Scraping & Data Extraction
* Utilizes **Requests** with custom headers (mimicking a real browser) to bypass basic blocks and fetch HTML content.
* Parses the page structure using **BeautifulSoup4** to extract the product title and current price.

### 2. Data Cleaning & Transformation
* Removes currency symbols (e.g., `$`) and unnecessary whitespace.
* Converts string data into numerical formats (`float`) to enable logic comparisons for price drops.

### 3. Data Persistence & Tracking
* Automatically appends the structured data (Product Title, Price, Timestamp) into a **CSV file** using **Pandas**.
* Creates a continuous historical dataset without overwriting previous records.

### 4. Automation & Email Alert System
* Uses a `while` loop combined with the `time` library to run the script at set intervals (e.g., every 24 hours).
* Integrates **smtplib** to send an automated "Buy Now!" email alert containing the product link the moment the price drops below the user-defined threshold.

---

## 🚀 How It Works (Execution Flow)
1. **Fetch:** Sends a GET request to the target Amazon product URL.
2. **Parse & Clean:** Extracts the title and price, then formats the data.
3. **Log:** Saves the new entry along with the current date into `Amazon Web Scraping.csv`.
4. **Evaluate:** * *If Price < Target_Price:* Logs into Gmail (via SMTP) and sends the alert email.
   * *If Price > Target_Price:* Goes to sleep and continues monitoring in the next cycle.

---

## ⚠️ Usage Note
To run this script locally and enable the email notification system, you must generate a **Google App Password**. Standard Gmail passwords are not supported for third-party scripts via SMTP due to security policies.
