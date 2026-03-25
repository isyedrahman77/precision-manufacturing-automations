# Precision Manufacturing — Automation Portfolio

**Client:** Precision Manufacturing Co.
**Built by:** Syed
**Status:** Active

## Overview

A suite of automation tools built to eliminate manual invoice processing at Precision Manufacturing. The Finance team was spending 2+ hours daily manually entering invoice data — these automations reduce that to near zero.

## Automations

### 1. Invoice Processor (Local Script)
Extracts invoice data from PDF files and saves records to Airtable automatically.

- **Input:** PDF invoices in a local folder
- **Output:** Structured records in Airtable
- **Tech:** Python, pdfplumber, Airtable API
- **Location:** `automations/invoice-processor/`

### 2. Google Drive Automation
Watches a Google Drive folder for new invoices and processes them automatically — no manual trigger needed.

- **Input:** PDF invoices uploaded to Google Drive
- **Output:** Structured records in Airtable
- **Tech:** Python, Google Drive API, pdfplumber, Airtable API
- **Location:** `automations/drive-automation/`

### 3. Invoice Upload Web App
A self-service web portal where anyone on the Finance team can upload an invoice, review the extracted data, and save it to Airtable — from any device.

- **Live URL:** https://invoice-webapp-inky.vercel.app/
- **Tech:** FastAPI, pdfplumber, Airtable API, Vercel
- **Location:** `automations/invoice-webapp/`

## Setup

### Prerequisites
- Python 3.9+
- Airtable account with an Invoices table
- Google Cloud credentials (for Drive automation)

### Environment Variables

Each automation uses a `.env` file. See `.env.example` in each folder for required variables:

```
AIRTABLE_TOKEN=your_airtable_token
AIRTABLE_BASE_ID=your_base_id
AIRTABLE_TABLE_NAME=Invoices
```

### Install Dependencies

```bash
cd automations/invoice-processor
pip install -r requirements.txt
```

### Run the Invoice Processor

```bash
python invoice_processor.py
```

### Run the Drive Watcher

```bash
python drive_watcher.py
```

### Run the Web App Locally

```bash
cd automations/invoice-webapp
pip install -r requirements.txt
uvicorn main:app --reload
```

Then open: http://localhost:8000

## Sample Data

Test invoices are in the `sample-data/` folder.

## Results

- Finance team saves 2+ hours daily on manual data entry
- Invoice data is captured accurately and consistently
- Any team member can process invoices from any device via the web app
