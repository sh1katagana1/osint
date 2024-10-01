# Crytography OSINT
**Description** \
This will be for items related to crytography

# CRT.SH Certificate Details Script

The goal with this one is to create a text file with a list of domains that I want SSL Certificate details for. The site I like to use for this is crt.sh, so I want the script to query that site for the details. I also want the script to include rate limiting to prevent overwhelming the crt.sh server with rapid requests.

## Instructions
1. Create a text file with a list of domains you want SSL certificate details for, called domains.txt
2. Run the script.

## What is the script doing?

1. It imports necessary libraries for making HTTP requests, handling JSON data, working with Excel files, and managing time delays.
2. The script defines a function get_cert_details that queries the crt.sh website for certificate information about a given domain. It sends a GET request to the crt.sh API and returns the JSON response if successful.
3. An Excel workbook is created with a sheet titled "Certificate Details". The sheet's headers are set up with bold formatting.
4. The script reads a list of domains from a file named 'domains.txt'.
5. It then iterates through each domain in the list:
6. Queries crt.sh for certificate details
7. If certificate details are found, it writes the information (Domain, Common Name, Issuer, Not Before, Not After) to the Excel sheet
8. If no certificates are found or an error occurs, it notes this in the sheet
9. To avoid overloading the crt.sh server, the script implements a 2-second delay between each request.
10. Finally, the script saves the Excel workbook as "certificate_details.xlsx" and prints a completion message.

## Key Features
1. API Interaction: The script interacts with the crt.sh API to retrieve SSL/TLS certificate information for specified domains. 
2. Data Processing: It processes the JSON responses from the API, extracting relevant certificate details. 
3. Excel Output: The script organizes and writes the collected data into an Excel spreadsheet for easy viewing and analysis. Error Handling: It handles cases where no certificates are found or errors occur during the API request. 
4. Rate Limiting: To be respectful of the crt.sh service, the script implements a simple rate limiting mechanism. 

This script is useful for gathering SSL/TLS certificate information for multiple domains efficiently, which can be valuable for security audits, domain management, or certificate monitoring purposes.

## Script


```
import requests
import json
import openpyxl
from openpyxl.styles import Font
import time

def get_cert_details(domain, session):
    url = f"https://crt.sh/?q={domain}&output=json"
    response = session.get(url)
    if response.status_code == 200:
        return json.loads(response.text)
    else:
        return None

# Create a new workbook and select the active sheet
workbook = openpyxl.Workbook()
sheet = workbook.active
sheet.title = "Certificate Details"

# Set up headers
headers = ["Domain", "Common Name", "Issuer", "Not Before", "Not After"]
for col, header in enumerate(headers, start=1):
    cell = sheet.cell(row=1, column=col)
    cell.value = header
    cell.font = Font(bold=True)

# Read domains from a text file
with open('domains.txt', 'r') as file:
    domains = file.read().splitlines()

# Create a session for requests
session = requests.Session()

# Query crt.sh for each domain and write to Excel
row = 2
for domain in domains:
    cert_details = get_cert_details(domain, session)
    if cert_details:
        for cert in cert_details:
            sheet.cell(row=row, column=1, value=domain)
            sheet.cell(row=row, column=2, value=cert['common_name'])
            sheet.cell(row=row, column=3, value=cert['issuer_name'])
            sheet.cell(row=row, column=4, value=cert['not_before'])
            sheet.cell(row=row, column=5, value=cert['not_after'])
            row += 1
    else:
        sheet.cell(row=row, column=1, value=domain)
        sheet.cell(row=row, column=2, value="No certificates found or error occurred")
        row += 1
    
    # Rate limiting: Sleep for 2 seconds between requests
    time.sleep(2)

# Save the workbook
workbook.save("certificate_details.xlsx")
print("Certificate details have been saved to certificate_details.xlsx")
```


[CyberChef](https://gchq.github.io/CyberChef/) The ultimate cryptography tool \
[CRT](https://crt.sh/) Check certifcates \
[Osint.sh Certificate Check](https://osint.sh/crt/) Good site to check certifcate details of a site \
[Osint.sh SSL Checker](https://osint.sh/ssl/) Verify that the SSL Certificate on your web server is properly installed and trusted \
[SSL Checker](https://hackertarget.com/ssl-check/) Hackertargets SSL Scanner
