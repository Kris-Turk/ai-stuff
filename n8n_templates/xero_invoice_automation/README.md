# Xero Invoice Automation Workflow

This n8n workflow automates the process of extracting data from PDF invoices received via email and creating corresponding invoices in Xero. It uses AI to identify invoices, extract relevant information, and handle the entire process from email receipt to invoice creation.

## Workflow Overview

The workflow performs the following steps:

* Monitors an Outlook email folder for new emails with attachments
* Processes PDF attachments by:
* Extracting text from the PDF
* Using AI to determine if the document is an invoice
* Extracting key invoice information (amounts, dates, supplier, etc.)
* Handles supplier management in Xero:
* Searches for existing suppliers by email or name
* Creates new suppliers when needed
* Creates a draft invoice in Xero with all extracted information
* Attaches the original PDF to the Xero invoice
* Moves the processed email to a "processed" folder

## Key Features

* AI-Powered Document Processing: Uses OpenAI models to identify invoices and extract structured data
* Intelligent Supplier Management: Matches or creates suppliers based on email or company name
* Automated Chart of Accounts Selection: Provides AI with the chart of accounts to select appropriate account codes
* Complete Document Handling: Attaches original PDFs to Xero invoices for reference
* Email Organization: Moves processed emails to keep inbox organized

## Required Credentials

To use this workflow, you'll need to set up the following credentials in n8n:

* Microsoft Outlook OAuth2: For accessing emails and attachments
* Xero OAuth2: For creating and managing invoices in Xero

3. OpenAI API: For AI-powered document processing

## Workflow Configuration

Before using this workflow, you'll need to:

1. Update the Outlook folder IDs to match your email setup

* Set your Xero organization ID
* Configure the AI extraction parameters to match your invoice formats
* Review and adjust the account codes based on your Xero chart of accounts

## How It Works

* The workflow is triggered on a schedule to check for new emails
* For each email with attachments, it processes PDF files
* AI models analyze the content to determine if it's an invoice
* If identified as an invoice, detailed information is extracted
* The workflow searches for the supplier in Xero or creates a new one
* A draft invoice is created in Xero with the extracted information
* The original PDF is attached to the invoice
* The email is moved to a processed folder

## Use Cases

* Automating accounts payable processes
* Reducing manual data entry for invoices
* Ensuring consistent invoice processing
* Maintaining complete documentation in Xero
* Streamlining supplier management

This workflow significantly reduces the time and effort required to process invoices while improving accuracy and maintaining a complete audit trail in Xero.
