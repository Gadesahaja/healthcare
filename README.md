Healthcare Patient Management 

Key Python Modules:
    concurrent.futures: For concurrency.
    smtplib: For sending email alerts.
    paramiko: For SSH communication (file transfers).
    requests: For web scraping.
    logging: For error handling and logging.

Concurrency: Tasks like network communication, file transfer, and scraping are executed concurrently using ThreadPoolExecutor.
Error Handling: Logs errors to system.log.
Scalability: The use of multithreading allows the system to scale across multiple devices or tasks.
Database: The CSV serves as a dummy database


  Loading Patient Data:
                        The system will read the patients_data.csv file to retrieve patient data such as patient_id, patient_name, and device_ip.
                        For each patient, it will attempt to connect to the network device at the IP address specified in device_ip using SSH.

  Network Communication:
                    If a connection is established successfully, the system can execute remote commands on the device using execute_command. If there's an error (e.g., the device is unreachable), the error will be                               logged.

  File Transfer:
              The transfer_file function can be called to upload files to a device using SFTP (via SSH). Any failure in the file transfer will be logged.

  Email Alerts:
          The send_email function sends an email alert if a particular task requires it. For example, after a device check or after encountering an error, an email can be triggered to notify the administrator.

  Web Scraping:
          The scrape_data function scrapes a specified URL, fetches its HTML content, and logs the data. If the URL is invalid or the server is unreachable, an error will be logged

  Logging:
      All errors (e.g., failed SSH connections, failed file transfers, scraping issues) will be recorded in the system.log file located in the root directory of the project.
