# Web-Scraping-using-Python

![image](https://github.com/user-attachments/assets/88bb0b43-2c8c-4730-9181-c6708614a824)

<span style="text-decoration: underline;"><strong>Introduction:</strong></span>

<b>Web scraping</b>, <b>web harvesting</b>, or <b>web data extraction</b> is data scraping used for extracting data from websites using its HTML structure, In this post, I will explain basic fundaments of web scraping using python and also explore it by a live demonstration with two python libraries Beautifulsoup and requests respectively.

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

Web Scraping Workflow
The workflow for web scraping with Python can be divided into the following three steps:

Obtaining the HTML: Firstly, we need to send an HTTP request to the web page server that we want to scrape. If the request is successful, the server will respond with the HTML content of the page.

Parsing the HTML: Most of the obtained HTML data is nested, making it difficult to extract information using stand string processing techniques. Instead, we need a parser, i.e. an algorithm designed to parse the HTML and create a parse/syntax tree of the HTML data.

Extracting the Data: Once the syntax tree is created, we need to navigate it and retrieve the information that we are interested in

To complete those steps, we need two third-party Python libraries:

Requests: a simple but powerful library for sending all kinds of HTTP requests to a web server,

Beautiful Soup: a library for parsing HTML and XML documents. It works with a user-selected parser to provide idiomatic ways of navigating, searching, and modifying the parse tree.


Ethics of Scraping
Web scraping is a powerful tool that should be used responsibly. Below is a list of things to consider before we start scraping data:

Always check the robots.txt file of the site you are about to scrape, as it contains guidelines on how bots should behave on the website.

Do not spam the website with multiple requests in a short amount of time, as that may hurt their server(s) and/or may be classified as a DDOS attack. If you need to scrape multiple pages, you can artificially limit the rate of requests, as we will show in the code.

Do not engage in piracy or other unauthorised commercial use regarding the data you extract.

Additionally, some companies and websites may provide the data we are interested in in a clean and concise way through an API. If a public API that provides the information we are looking for is available, web scarping should be avoided altogether.

If you would like to know more, I suggest reading James Densmore’s article on the Ethics in Web Scraping.

