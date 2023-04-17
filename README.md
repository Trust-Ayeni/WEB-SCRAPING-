# WEB-SCRAPING 🕸️
I utilized Beautifulsoup to collect data to make data entry into the company's wordpress site easier.

## Data Isn't Always Easy to Access 🔍
We want to get Rotten Tomatoes' audience scores and the number of audience reviews to add to our dataset. However, this is not easily accessible from the website and to get this data we will need to do web scraping, which allows us to extract data from websites using code.

## How Does Web Scraping Work? 🤔
Website data is written in HTML (HyperText Markup Language) which uses tags to structure the page. Because HTML and its tags are just text, the text can be accessed using parsers 🕵️. We'll be using a Python parser called Beautiful Soup.

Let's get started by exploring the structure of HTML files.

#### Accessing the HTML 📥
>- Manual Access
The quick way to get HTML data is by saving the HTML file to your computer manually. You can do this by clicking Save in your browser.

>- Programmatic Access
Programmatic access is preferred for scalability and reproducibility. Two options include:

1. Downloading HTML file programmatically. We'll explore this code in more detail later
```
import requests
url = 'https://www.rottentomatoes.com/m/et_the_extraterrestrial'
response = requests.get(url)

# Save HTML to file

with open("et_the_extraterrestrial.html", mode='wb') as file:
    file.write(response.content)
```
2. Working with the response content live in your computer's memory using the BeautifulSoup HTML parser
```
# Work with HTML in memory
from bs4 import BeautifulSoup
soup = BeautifulSoup(response.content, 'lxml')
```
## Accessing HTML 🌐
Also, a web page's HTML is known to change over time. Scraping code can break easily when web redesigns occur, which makes scraping brittle and not recommended for projects with longevity. So just use these codes and pretend like you saved them yourself with one of the methods described above.

More Information ℹ️
There are some ethical issues involved in web scraping. Read this thoughtful article to learn more: [Towards Data Science: Ethics in Web Scraping](https://towardsdatascience.com/ethics-in-web-scraping-b96b18136f01?gi=f9471436f5a1)
