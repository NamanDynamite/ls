# LinkedIn Profile Scraper via SerpAPI

This project scrapes LinkedIn profiles using Google Search results via SerpAPI. It is designed to collect information about professionals in specific roles, locations, and industries, and save the results to a CSV file for further analysis.

## Features
- Searches Google for LinkedIn profiles matching specified roles, locations, and industries
- Extracts name, company, position, LinkedIn URL, and location from search results
- Cleans and parses profile data to avoid geographic or irrelevant information
- Saves the results to a CSV file (`linkedin_serpapi_contacts_debug.csv`)
- Includes debug print statements for transparency and troubleshooting

## How It Works
1. **Configuration**: Set up roles, locations, industries, and SerpAPI key in the script or via environment variables.
2. **Search**: For each combination of role and location, the script queries Google (via SerpAPI) for LinkedIn profiles.
3. **Extraction**: Parses the search result titles and snippets to extract relevant profile information.
4. **Location Detection**: Uses regex and keyword matching to accurately assign locations.
5. **Output**: Results are deduplicated and saved to a CSV file for easy access.

## Requirements
- Python 3.7+
- [SerpAPI](https://serpapi.com/) account and API key
- Required Python packages:
  - `requests`
  - `pandas`
  - `python-dotenv`

Install dependencies with:
```bash
pip install requests pandas python-dotenv
```

## Environment Variables
Create a `.env` file in the project directory with your SerpAPI key:
```
SERPAPI_KEY=your_serpapi_key_here
```

## Usage
Run the script:
```bash
python scrapping.py
```

The output CSV file will be saved as `linkedin_serpapi_contacts_debug.csv` in the project directory.

## Customization
- Edit the `ROLES`, `LOCATIONS`, and `INDUSTRIES` lists in `scrapping.py` to target different profiles.
- Adjust `MAX_RESULTS` to control how many profiles are collected.

## Notes
- The script includes delays to avoid hitting SerpAPI rate limits.
- Debug print statements help trace the extraction and cleaning process.
- Only public information from Google search results is used; no direct LinkedIn scraping is performed.

## Disclaimer
This project is for educational and research purposes only. Always comply with LinkedIn's and SerpAPI's terms of service.
