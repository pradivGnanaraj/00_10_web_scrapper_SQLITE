# Web Scraping and Email Notification Script

This Python script performs web scraping to extract tour event information from a website and notifies via email if new events are found. It uses the `requests`, `selectorlib`, and `smtplib` libraries for web scraping, extraction, and email communication respectively. The extracted data is stored in an SQLite database.

## Usage

1. Install the required libraries using the following command:
   ```bash
   pip install requests selectorlib
   ```

2. Before running the script, make sure to update the following parameters:
   - `URL`: The URL of the website to scrape.
   - `username` and `password`: The Gmail credentials for sending email notifications.
   - `receiver`: The email address to receive notifications.

3. Create an SQLite database file named `data.db` using an SQLite tool or command-line interface.

4. The script uses an extraction YAML file named `extract.yaml` which defines how to extract data from the webpage. Ensure that the CSS selector in the YAML file accurately matches the webpage's structure.

5. Run the script using the following command:
   ```bash
   python main.py
   ```

## Script Functionality

1. **Scraping**: The `scrape` function fetches the page source from the provided URL using the `requests` library.

2. **Extraction**: The `extract` function utilizes the `selectorlib` library and the `extract.yaml` file to extract tour event information from the page source.

3. **Email Notification**: The `send_email` function sends an email using Gmail's SMTP server with the provided credentials. It sends a notification if a new event is found.

4. **Storing Data**: The `store` function stores the extracted event information in the SQLite database using SQL queries.

5. **Reading Data**: The `read` function reads data from the database based on the provided event information and returns the matching rows.

6. The script continuously scrapes the webpage, extracts event information, checks if new events exist, and sends email notifications accordingly. It then waits for a specified interval before repeating the process.

## Note

- The script runs in an infinite loop to continuously monitor the website for new events.
- Make sure to secure your Gmail credentials and use an 'App Password' for enhanced security.
- Customize the script according to your needs and add error handling where necessary.
```

Please replace placeholders (like `username` and `password`) with your actual Gmail credentials and adapt other parts of the script as needed for your use case.