# Web-Scrapping-in-Laravel
The provided code performs web scraping on multiple web pages and saves the extracted data to a CSV file
 Here's a description of each function:

url_script(url): This function takes a URL as input, fetches the HTML content of the webpage, and extracts the text from all <p> tags using the BeautifulSoup library. The extracted paragraphs are returned as a list.

clean_data(data): This function receives a list of text data and applies regular expressions to clean the data. It removes special characters using the re.sub method and excludes empty strings. The cleaned data is returned as a new list.

save_to_csv(data, filename): This function saves the provided data to a CSV file. It creates a Pandas DataFrame from the data list, and then uses the to_csv method to save the DataFrame to the specified filename. The index parameter is set to False to exclude row indices from the CSV file. The CSV file is saved with UTF-8 encoding.

scrape_webpages(urls): This function scrapes multiple web pages by iterating over a list of URLs. For each URL, it calls the url_script function to extract the paragraphs, cleans the extracted data using clean_data, and appends the cleaned data to the all_data list. After iterating over all URLs, the all_data list is saved to a single CSV file using save_to_csv.

To use the code, you need to provide the desired URLs in the urls list. You can uncomment the line # save_to_csv(articles, f'articles_{i+1}.csv') if you want to save the data to separate CSV files for each web page.
