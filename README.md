# Automated Result Scraper with CAPTCHA Solver

This Python script automates the login and result extraction process from a student result portal that uses image-based CAPTCHA verification. It reads student credentials from an Excel file, logs in using Selenium, solves the CAPTCHA using Tesseract OCR, and extracts result data into a CSV file.

---

## Features

- Reads student registration numbers and passwords from an Excel file (`Data.xlsx`)
- Bypasses image CAPTCHA using OCR (Tesseract)
- Retries automatically on CAPTCHA failure
- Optional support for proxy authentication
- Saves extracted results to `results.csv`

---

## Requirements

- Python 3.7 or higher
- Google Chrome browser
- ChromeDriver (automatically managed via `webdriver-manager`)
- Tesseract OCR (installed separately)

---

## Python Dependencies

Install the required packages using pip:

```bash
pip install selenium webdriver-manager pillow pytesseract pandas openpyxl
```

---

## Tesseract Installation

Download and install Tesseract OCR:

- Windows: https://github.com/tesseract-ocr/tesseract
- Make sure to update the path to `tesseract.exe` in the script:
  ```python
  pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"
  ```

---

## Input Format

Place an Excel file named `Data.xlsx` in the script directory with the following columns:

- `Exam Registration Number`
- `Password`

Each row represents one student.

---

## Output

After execution, a `results.csv` file will be generated with the following columns:

- Exam Registration Number
- Candidate Name
- Rank
- Score

If a student’s result could not be retrieved, "Failed", "N/A", and "N/A" are used as placeholders.

---

## Notes

- Make sure to update all placeholder XPaths and the target URL in the script to match the actual result portal.
- The script includes a retry loop for CAPTCHA failures.
- Proxy configuration is optional and can be enabled or disabled using the `use_proxy` flag.

---


