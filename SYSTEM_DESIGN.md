
**System Overview:**

The system is designed to monitor a website for upcoming tour events, extract event information, store it in a database, and send email notifications for new events.

**Components:**

1. **Web Scraping Component:**
   - Utilizes the `requests` library to send HTTP requests to the target website.
   - Fetches the page source containing tour event information.
   
2. **Data Extraction Component:**
   - Utilizes the `selectorlib` library to define CSS selectors in the "extract.yaml" configuration file.
   - Extracts event details (band name, city, date) from the fetched page source using defined selectors.
   
3. **Database Component:**
   - Utilizes the `sqlite3` library to interact with the SQLite database.
   - Stores the extracted event details in the "data.db" database.
   - Provides functions for inserting new event data and querying existing data.
   
4. **Email Component:**
   - Utilizes the `smtplib` and `ssl` libraries for sending email notifications.
   - Sends email notifications using Gmail's SMTP server.
   
5. **Main Script Component (main.py):**
   - Combines all the components and orchestrates their interactions.
   - Runs in an infinite loop, periodically checking for new events.
   - Calls the web scraping component to fetch page source.
   - Calls the data extraction component to extract event details.
   - Calls the database component to check and store event data.
   - If a new event is detected, calls the email component to send notifications.
   - Sleeps for a specified interval before checking again.
   
**Data Flow:**

1. The "main.py" script initiates the process by calling the web scraping component.
2. The web scraping component fetches the page source from the specified URL.
3. The data extraction component uses CSS selectors defined in "extract.yaml" to extract event details.
4. Extracted data is passed to the database component, which checks if the event is new and stores it if necessary.
5. If a new event is detected, the email component sends an email notification.
6. The script then goes to sleep for a defined interval and repeats the process.

**Benefits:**

- Automation: The system automates the process of monitoring and notifying about new events.
- Scalability: The modular design allows easy addition of new functionalities or components.
- Flexibility: Can be customized for different websites by adjusting URL and selectors.
- User Notification: Users receive timely email notifications about new events.
- Data Storage: Event data is stored in an SQLite database for historical analysis.

This system design showcases a structured and organized approach to monitoring and notifying events from websites. It highlights the seamless integration of various components to achieve the desired functionality.