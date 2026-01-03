# 🏥 WMCA Care Homes Data Scraper

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-BS4-yellow?style=for-the-badge)
![Requests](https://img.shields.io/badge/Requests-2.x-green?style=for-the-badge)
![Pandas](https://img.shields.io/badge/Pandas-Data-150458?style=for-the-badge&logo=pandas)

## 📖 Project Overview
This project is a specialized web scraper built to extract care home data from the **West Midlands Care Association (WMCA)** directory. 

Unlike simple scrapers, this script navigates through city directories, drills down into individual care home profiles (`/dp/{id}`), and extracts granular details. It also includes a robust data cleaning pipeline using **Pandas** to handle missing values and formatting.

## ✨ Key Features
*   **🔗 Deep Crawling:** Navigates from the main directory -> City pages -> Individual Care Home profiles.
*   **📄 Structured Extraction:** Scrapes 10 key data points including Contact Info, Specialisms, and Local Authority details.
*   **🧹 Data Cleaning:** 
    *   Handles empty strings and missing data automatically.
    *   Replaces `NaN` and blank values with "Not Specified".
    *   Standardizes "Unknown" fields during extraction.
*   **📂 CSV Export:** Outputs a ready-to-use dataset named `wmca.csv`.

## 🛠️ Technologies Used
*   **Python**: Core programming language.
*   **Requests**: For making HTTP requests to fetch HTML content.
*   **Beautiful Soup (bs4)**: For parsing HTML and locating specific tags.
*   **Pandas**: For organizing data into a DataFrame and performing cleanup/export.
*   **LXML**: Fast HTML parser used by Beautiful Soup.

## 📊 Data Extracted
The scraper collects the following fields for each care home:
1.  **Care Home Name**
2.  **Street Address**
3.  **Suburb**
4.  **City**
5.  **PostCode**
6.  **Specialisms** (e.g., Nursing, Dementia, Learning Disabilities)
7.  **Local Authority Area**
8.  **Phone Number**
9.  **Email Address**
10. **Website URL** (Profile Link)

## 🚀 How to Run

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/YOUR-USERNAME/WMCA-Care-Homes-Scraper.git
    ```

2.  **Install dependencies:**
    ```bash
    pip install requests beautifulsoup4 pandas lxml numpy
    ```

3.  **Run the script:**
    ```bash
    python scraper.py
    ```

4.  **Check the output:**
    The script will generate a file named `wmca.csv` in the same directory.

## 📝 Output Preview
The final CSV contains cleaned data where missing values are handled gracefully:

| Care Home Name | Street | City | Specialisms | Phone | Email |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Abbey Rose Nursing Home | 2 Ivyfield Road | Birmingham | Nursing | 0121 3776707 | AR.admin@... |
| Arden Lodge | 946 Warwick Road | Birmingham | Not Specified | 0121 7067958 | manager@... |
| New Care Home | Not Specified | Solihull | Dementia | Not Specified | info@... |

---
**Disclaimer:** This tool is for educational purposes only. Please respect the website's `robots.txt` and terms of service.