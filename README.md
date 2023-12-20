Overview
The provided Python script is designed to scrape customer complaints from the "sikayetvar.com" website for a specified company or service. It does so by performing the following steps:

Setting up a session for making HTTP requests using the requests library with a retry mechanism.
Extracting the total number of pages containing complaints for the given company.
Collecting all complaint links from each page.
Scraping and extracting details (such as username, date, title, comment, and views) from each complaint link.
Storing the extracted data in a Pandas DataFrame.
Saving the DataFrame as an Excel file.
Additionally, the script uses the Gradio library to create a user interface for running the scraping process. Users can input the name of the company or service they want to scrape complaints for, and the script will perform the scraping and provide an Excel file as output.

Code Explanation
Here is an explanation of the key functions and sections in the code:

setup_session(): Configures and returns a session for making HTTP requests with retry mechanisms to handle network issues.

get_page_count(session, url): Retrieves the total number of pages containing complaints for the specified URL.

get_complaint_links(session, url, page_count): Gathers all complaint links from each page for the given URL.

scrape_complaint(session, url): Scrapes details (username, date, title, comment, views) from a single complaint page.

scrape_and_save(kargo, progress=gr.Progress()): The main function that orchestrates the scraping process. It takes a company or service name as input and returns an Excel file containing the scraped data.

Gradio Interface (iface): Sets up a Gradio interface that allows users to input the company or service name and triggers the scraping process.

Usage
To use this script, follow these steps:

Ensure you have the required libraries (pandas, bs4, requests, gradio, tqdm) installed.

Run the script, and it will create a Gradio interface for you to interact with.

Input the name of the company or service you want to scrape complaints for, following the format provided in the description (e.g., for "https://www.sikayetvar.com/aras-kargo" please write "aras-kargo" to the grabber).

Click the "Submit" button in the Gradio interface to start the scraping process.

The script will display the scraping progress in the console, and once completed, it will provide a link to download the scraped data as an Excel file.

Note
Be mindful of web scraping etiquette and ensure you are scraping data only from websites that allow it. Always check and respect the website's terms of service and robots.txt file.

The script uses random delays between requests to avoid overloading the website's server and to simulate more natural browsing behavior.

The script may encounter errors when scraping certain pages due to variations in website structure. Any errors encountered will be printed in the console.

Ensure you have the necessary permissions and legal rights to scrape data from the website you intend to use this script on.

Please use this script responsibly and only for legal and ethical purposes.
