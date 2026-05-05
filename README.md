# IT23270206 Test Automation

This project contains a Python Playwright automation script for running frontend test cases against the Pixels Suite Chat Translator page.

## Files

- `IT23270206_test_automation.py` - Main automation script.
- `IT23270206_Test cases.xlsx` - Excel test case file.
- `IT23270206_requirements.txt` - Python dependencies.
- `IT23270206_README.md` - Project documentation.

## Requirements

- Python 3.8 or newer
- Google Chrome or Chromium support through Playwright

## Installation

Install the required Python packages:

```bash
pip install -r IT23270206_requirements.txt
```

Install Playwright browser binaries:

```bash
playwright install
```

## Usage

Run the automation script with the Excel test case file:

```bash
python IT23270206_test_automation.py --excel "IT23270206_Test cases.xlsx"
```

By default, the script tests:

```text
https://www.pixelssuite.com/chat-translator
```

To test a different frontend URL:

```bash
python IT23270206_test_automation.py --excel "IT23270206_Test cases.xlsx" --url "https://example.com"
```

To run in headless mode:

```bash
python IT23270206_test_automation.py --excel "IT23270206_Test cases.xlsx" --headless
```

Full run command:

```bash
python .\IT23270206_test_automation.py --excel "C:\Users\IMAKA TEC\Desktop\IT23270206\IT23270206_Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

## Excel Format

The Excel sheet should include the following columns:

- `Input`
- `Expected output`
- `Actual output`
- `Status`

If `Actual output` or `Status` columns are missing, the script will create them automatically.

## Output

The script enters each input value into the frontend, collects the generated output, compares it with the expected output, and writes the result back to the Excel file.

Possible status values:

- `PASS` - Actual output matches expected output.
- `FAIL` - Actual output does not match expected output.
- `COLLECTED` - No expected output was provided.
- `UI Error` - The script encountered an issue while interacting with the page.
