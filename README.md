# News Article Scraper

This script uses the GoogleNews library to retrieve the top 100 news articles related to a user-specified topic from the past seven days. It gathers each article's title and URL, scrapes descriptions from the articles, and stores the descriptions in individual text files in a `NEWS_data` folder.

## Prerequisites

Make sure you have the following libraries installed:

- `GoogleNews`
- `pandas`
- `requests`
- `beautifulsoup4`
- `tqdm`

To install them, run:

```bash
pip install GoogleNews pandas requests beautifulsoup4 tqdm
```

## Usage

1. **Specify a Topic**: When prompted, enter a topic you want to search news articles for.
2. **Article Retrieval**: The script will search Google News for articles from the past 7 days and fetch up to 100 unique articles.
3. **Article Descriptions**: For each article, it attempts to scrape the full description by extracting paragraph text.
4. **Save Descriptions**: The final descriptions are saved as individual text files in a folder named `NEWS_data`.

## Script Breakdown

1. **Search News Articles**: 
   - The script prompts for a search term, searches Google News, and retrieves up to 100 unique articles.
   
2. **Format Article Links**: 
   - It processes each article link to ensure it's in a clean format for scraping.
   
3. **Scrape Article Descriptions**: 
   - For each article, the script sends an HTTP request to retrieve the page, parses it using BeautifulSoup, and extracts paragraph text for a detailed description.
   - Introduces a random delay between requests to avoid rate limiting.
   
4. **Save Descriptions**:
   - The descriptions are saved as `.txt` files in the `NEWS_data` folder.

## Example Output

After running the script, you will see a `NEWS_data` folder containing up to 100 text files named `description_1.txt`, `description_2.txt`, etc., with each file containing the article’s description.

## Notes

- **Timeout Handling**: The script uses error handling for requests with a timeout to prevent it from hanging on unresponsive pages.
- **Duplicate Filtering**: Duplicate article titles are removed to ensure a variety of content.
- **Rate Limiting**: Random sleep intervals prevent overloading the server.

