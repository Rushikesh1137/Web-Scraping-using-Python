# Web-Scraping-using-Python

![image](https://github.com/user-attachments/assets/88bb0b43-2c8c-4730-9181-c6708614a824)

<span style="text-decoration: underline;"><strong>Introduction:</strong></span>

<b>Web scraping</b>, <b>web harvesting</b>, or <b>web data extraction</b> is data scraping used for extracting data from websites using its HTML structure.
This project aims to show how to use the Python programming language to web scrape a website. Specifically, we will use the requests and Beautiful Soup libraries to scrape and parse data from Bookings.com and retrieve the “Hotels with any location”.

We will learn how to scale the web scraping process by first retrieving the hotel_name, rating, Location, link, Price , Reviews etc on the website’s first page, and finally, Hotels from multiple pages. Once the scraping process is complete, we will preprocess the dataset and transform it into a more readable format before using matplotlib to visualise the most important information.

<span style="text-decoration: underline;"><strong>What you will learn from this post:</strong></span>
<ul>
	<li>basic understanding of web scraping</li>
	<li>how to extract data from a website using classes and HTML tags</li>
	<li>how to use requests module to get data</li>
	<li>how to use Beautifulsoup</li>
</ul>
<span style="text-decoration: underline;"><strong>Requirements:</strong></span>
<ul>
	<li>python3</li>
	<li>requests</li>
	<li>bs4</li>
</ul>


## Workflow for Web Scraping

The workflow for web scraping can be divided into three main steps:

### 1. **Obtaining the HTML**
   - First, we need to send an HTTP request to the web server of the page we want to scrape.
   - If the request is successful, the server responds with the HTML content of the page.

### 2. **Parsing the HTML**
   - The obtained HTML is often nested and may be difficult to extract using regular string processing techniques.
   - We use a parser, such as `BeautifulSoup`, to process the HTML and create a parse/syntax tree.

### 3. **Extracting the Data**
   - Once we have the syntax tree, we can navigate it to retrieve the specific information we are interested in.

## Libraries Used

### 1. **Requests**
   - `requests` is a simple but powerful library for sending HTTP requests to a web server.
   - It helps us to interact with web pages and fetch the HTML content.

### 2. **BeautifulSoup**
   - `BeautifulSoup` is a library that allows us to parse HTML and XML documents.
   - It works with a user-selected parser to provide idiomatic ways to navigate, search, and modify the parse tree.

## Ethics of Scraping

Web scraping is a powerful tool, but it must be used responsibly. Below are some key points to consider before starting a scraping project:

### 1. **Check the robots.txt**
   - Always check the `robots.txt` file of the website you are about to scrape. It contains guidelines on how bots should behave when accessing the website.

### 2. **Avoid Spamming the Server**
   - Do not send multiple requests in a short amount of time as this can harm the server and may be classified as a Distributed Denial of Service (DDOS) attack.
   - You can limit the rate of requests by introducing delays between requests to avoid overloading the server.

### 3. **Do Not Engage in Piracy or Unauthorized Commercial Use**
   - Avoid using the scraped data for piracy or unauthorized commercial purposes.

### 4. **Use Public APIs When Available**
   - Many websites and companies provide APIs that deliver the data we need in a clean and structured format.
   - If a public API is available, use it instead of scraping the website. This is a more ethical and reliable approach.

### 5. **Read More on Ethics in Web Scraping**
   - For more information on the ethics of web scraping, consider reading James Densmore’s article on the subject.

## Example Code

```python
import requests
from bs4 import BeautifulSoup

# Send an HTTP request to the website
url = 'https://example.com'
response = requests.get(url)

# Check if the request was successful (Status code 200)
if response.status_code == 200:
    # Parse the HTML content of the page
    soup = BeautifulSoup(response.content, 'html.parser')
    
    # Example: Extracting all the headings (h1 tags) from the page
    headings = soup.find_all('h1')
    
    for heading in headings:
        print(heading.text)

