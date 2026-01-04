# UK Care Homes Scraper (WMCA)

A Python web scraper that extracts care home information from the West Midlands Combined Authority (WMCA) care homes directory.

## Overview

This project scrapes comprehensive details about care homes in the West Midlands region, including Birmingham, Coventry, Dudley, Sandwell, Solihull, Walsall, and Wolverhampton. The scraper collects information such as care home names, addresses, contact details, specialisms, and more.

## Features

- Scrapes multiple cities in the West Midlands region
- Extracts detailed care home information including:
  - Care Home Name
  - Street Address
  - Suburb
  - City
  - Post Code
  - Specialisms (e.g., Nursing, Learning Disabilities, Mental Health, Dementia)
  - Local Authority Area
  - Phone Number
  - Email Address
  - Website URL
- Exports data to CSV format for easy analysis
- Handles missing data with "Not Specified" placeholders

## Requirements

### Python Version
- Python 3.7 or higher

### Dependencies

```python
requests==2.31.0
beautifulsoup4==4.12.2
lxml==4.9.3
pandas==2.1.0
numpy==1.24.3
```

## Installation

1. Clone this repository or download the notebook file
2. Install required packages:

```bash
pip install requests beautifulsoup4 lxml pandas numpy
```

Or install using requirements.txt:

```bash
pip install -r requirements.txt
```

### Create requirements.txt file:

```
requests==2.31.0
beautifulsoup4==4.12.2
lxml==4.9.3
pandas==2.1.0
numpy==1.24.3
jupyter==1.0.0
notebook==7.0.0
```

## Usage

1. Open the Jupyter Notebook `UK_Care_Homes_Scraper(wmca_care).ipynb`
2. Run all cells in sequence
3. The script will:
   - Connect to the WMCA care homes directory
   - Scrape all available care homes across multiple cities
   - Process and clean the data
   - Export results to `wmca.csv`

## Code Structure

### Cell 1: Web Scraping
- Sets up HTTP headers to mimic a browser request
- Connects to the WMCA care homes directory
- Navigates through city pages
- Extracts care home details from individual care home pages
- Handles special URL formatting for Coventry

### Cell 2: Data Processing
- Converts scraped data into a Pandas DataFrame
- Organizes data into structured columns

### Cell 3: Data Preview
- Displays the first 10 rows of the scraped data

### Cell 4-5: Data Cleaning
- Replaces empty strings with "Not Specified"
- Handles missing values in the suburb column

### Cell 6: Data Export
- Exports the cleaned DataFrame to `wmca.csv`

## Output Format

The scraper generates a CSV file with the following columns:

| Column | Description |
|--------|-------------|
| Care Home Name | Name of the care facility |
| street | Street address |
| suburb | Suburb or area name |
| city | City name |
| PostCode | UK postal code |
| Specialisms | Type of care provided (e.g., Nursing, Learning Disabilities) |
| Local authority area | Governing local authority |
| phone Number | Contact phone number |
| email | Contact email address |
| Website URL | Link to care home details page |

## Sample Data

```
Care Home Name: Abbey Rose Nursing Home
Street: 2 Ivyfield Road
Suburb: Erdington
City: Birmingham
PostCode: B23 7HH
Specialisms: Nursing
Local authority area: Birmingham
Phone Number: 0121 3776707
Email: AR.admin@macccare.com
```

## Data Statistics

- Total care homes scraped: 319
- Cities covered: Birmingham, Coventry, Dudley, Sandwell, Solihull, Walsall, Wolverhampton
- Data fields: 10 columns per care home

## Notes

- The scraper includes special handling for Coventry URLs
- Empty fields are automatically filled with "Not Specified"
- The script uses a user agent to ensure proper access to the website
- Some entries may have placeholder data (e.g., "CH Town", "CH Email") indicating incomplete information on the source website

## Legal Disclaimer

This scraper is intended for educational and research purposes only. Please ensure you comply with:
- The website's Terms of Service
- robots.txt directives
- UK data protection laws (GDPR)
- Appropriate rate limiting to avoid overwhelming the server

Always verify that web scraping is permitted before running this code on any website.

## Future Enhancements

- Add error handling for network timeouts
- Implement rate limiting between requests
- Add logging functionality
- Include data validation checks
- Support for exporting to multiple formats (JSON, Excel)
- Add command-line interface

## Contributing

Feel free to fork this project and submit pull requests for any improvements.

## Author

**Rehan Afroz**

Created for scraping UK care homes data from the WMCA directory.

---

## Contact & Support

For questions, issues, or contributions, please reach out through GitHub.

## Acknowledgments

- Data source: [WMCA Care Homes Directory](https://www.wmca.care/hmfc/directory/carehomes)
- Built with Python, BeautifulSoup, and Pandas

## License

This project is provided as-is for educational purposes.
