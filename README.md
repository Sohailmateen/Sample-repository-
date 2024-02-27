# Sample-repository-
import requests
from bs4 import BeautifulSoup

def scrape_news_headlines(url):
    response = requests.get(url)
    if response.status_code == 200:
        soup = BeautifulSoup(response.text, 'html.parser')
        headlines = soup.find_all('h2')
        for headline in headlines:
            print(headline.text.strip())
    else:
        print("Failed to retrieve data from the website.")

if __name__ == "__main__":
    news_url = "https://example.com/news"  # Replace this with the URL of the news website you want to scrape
    scrape_news_headlines(news_url)
    
