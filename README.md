# 🏨 Vietname Hotel Review Analysis & Translation Pipeline

This repository contains a Python-based data engineering pipeline designed to scrape, clean, and translate multilingual Google reviews for **Mekong Home**, a boutique homestay in the Mekong Delta, Vietnam[cite: 1]. The project solves critical data science challenges, including repairing broken character encoding and unifying diverse languages into English for sentiment analysis[cite: 1].

---

## 🛠️ Features

*   **Automated Scraping:** Extracts review text, ratings, and dates from Google Maps into Excel[cite: 1].
*   **Encoding Repair:** Fixes the common "glitch" where Vietnamese characters break (Mojibake) during export by forcing UTF-8-BOM encoding[cite: 1].
*   **Multilingual Translation:** Automatically detects and converts French, Italian, German, and Vietnamese reviews into English using the Google Translate API[cite: 1].
*   **Robust Data Cleaning:** Filters out reviews exceeding API character limits and handles translation errors without crashing the script[cite: 1].

---

## 🚀 Technical Stack

*   **Language:** Python 3.10+
*   **Libraries:** 
    *   `pandas`: For data manipulation and Excel export[cite: 1].
    *   `googletrans`: For automated translation services[cite: 1].
    *   `selenium`: For web scraping dynamic content[cite: 1].
    *   `openpyxl`: For handling `.xlsx` file formats[cite: 1].

---

## 📂 Project Structure

```bash
├── data/
│   ├── raw_reviews.xlsx          # Initial scraped data with encoding issues
│   └── translated_output.xlsx    # Final cleaned English dataset
├── scripts/
│   ├── scraper.py                # Selenium script for Google Maps
│   └── translator.py             # Translation and cleaning pipeline
└── README.md
```

---

## ⚙️ Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/mekong-home-analysis.git
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

*   **Rate Limiting:** Implemented a `time.sleep()` delay to prevent IP bans from Google's translation servers[cite: 1].
*   **Data Integrity:** Used "Entire Dataset" detection to ensure inconsistent row data (like mixed symbols) didn't break column data types during import[cite: 1].
*   **Error Handling:** Utilized `try-except` blocks to manage `Translator` attribute errors and connection timeouts[cite: 1].

---

## 📈 Future Work
The final output of this project is optimized for training Sentiment Analysis models using **VADER**, **TextBlob**, or **BERT** to visualize guest satisfaction across different nationalities[cite: 1].
```
