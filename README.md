# 🏨 Vietname Hotel Review Analysis & Translation Pipeline

This repository contains a Python-based data engineering pipeline designed to scrape, clean, and translate multilingual TripAdvisor reviews for **Vietnam Hotels**

---

## 🛠️ Features

*   **Automated Scraping:** Extracts review text, ratings, and dates from Google Maps into Excel.
*   **Encoding Repair:** Fixes the common "glitch" where Vietnamese characters break during export by forcing UTF-8-BOM encoding.
*   **Multilingual Translation:** Automatically detects and converts French, Italian, German, and Vietnamese reviews into English using the Google Translate API.
*   **Robust Data Cleaning:** Filters out reviews exceeding API character limits and handles translation errors without crashing the script.

---

## 🚀 Technical Stack

*   **Language:** Python 3.10+
*   **Libraries:** 
    *   `pandas`: For data manipulation and Excel export.
    *   `googletrans`: For automated translation services.
    *   `selenium`: For web scraping dynamic content.
    *   `openpyxl`: For handling `.xlsx` file formats.

---

## 📂 Project Structure

```bash
├── data/
│   └── translated_output.xlsx    # Final cleaned English dataset
├── scripts/
│   ├── scraper.py                # Selenium script for Google Maps
│   └── translator.py             # Translation and cleaning pipeline
└── README.md
```

---
📊 Dataset
Access the raw, unprocessed data here:

🔗 [https://zenodo.org/records/7967494]

## ⚙️ Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/hnfakmal/Sentiment-Analysis-on-Vietnam-Hotels-60k-Reviews-
.git
   ```

2. **Install dependencies:**
   
```bash
   pip install pandas googletrans==3.1.0a0 selenium openpyxl
   ```

3. **Run the pipeline:**
   Place your raw Excel file in the directory and run:
   
```bash
   python scripts/translator.py
   ```

---

## ⚠️ Challenges Overcome

*   **Rate Limiting:** Implemented a `time.sleep()` delay to prevent IP bans from Google's translation servers.
*   **Data Integrity:** Used "Entire Dataset" detection to ensure inconsistent row data (like mixed symbols) didn't break column data types during import.
*   **Error Handling:** Utilized `try-except` blocks to manage `Translator` attribute errors and connection timeouts.

---

## 📈 Future Work
The final output of this project is optimized for training Sentiment Analysis models using **VADER**, **TextBlob**, or **BERT** to visualize guest satisfaction across different nationalities.
```
