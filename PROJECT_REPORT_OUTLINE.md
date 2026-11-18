# PROJECT REPORT OUTLINE
## INVENTORY AND REORDER TRACKER – CONSOLE-BASED APPLICATION

**Institution:** Institute of Engineering & Management (IEM), Kolkata  
**Programme:** B.Tech  
**Subject:** Python Programming Laboratory  
**Department:** Electronics and Communication Engineering  
**Section:** A 
**Academic Session:** 2026–2027  
**Project Title:** Inventory and Reorder Tracker

---

## REPORT FORMATTING REQUIREMENTS

- Follow the format and presentation style of the sample project report provided by the department.
- Use formal academic language and professional technical documentation.
- Include properly numbered chapters, subheadings, tables, figures, diagrams and captions.
- Use Times New Roman font with consistent heading styles.
- Include the footer on every page:

"Department of Electronics and Communication Engineering | Page N"

- The cover page must contain the institution name, programme, subject, project title, team members' names, roll/enrollment numbers, Section B, department, academic session, submitted to and submission date.

## 1. ABSTRACT

Write an abstract of approximately 150–200 words covering:

- The importance of inventory management.
- The problem of manual stock tracking and delayed restocking.
- The proposed Inventory and Reorder Tracker application.
- Technologies used: Python, CSV, NumPy, Pandas, Matplotlib and JSON.
- Automated testing using 51 unit tests.
- Demonstration results: 12 products and 303 total units, with the total inventory value taken directly from the application output.
- The limitation of the current system being designed for a single user.

## 2. KEYWORDS

Inventory management; Reorder alerts; Python; CSV; NumPy; Pandas; Matplotlib; JSON; Unit testing; Stock management.

## 3. INTRODUCTION

Explain:

- The concept of inventory management.
- The importance of stock monitoring for small businesses.
- Problems associated with manual inventory tracking.
- The need for automated stock-in and stock-out records.
- The role of reorder alerts in preventing stock shortages.
- Introduction to the developed console-based application.
- Overview of the technologies and tools used.

## 4. PROBLEM STATEMENT AND OBJECTIVES

### 4.1 Problem Statement

Describe the difficulties of maintaining product records, monitoring stock quantities, calculating inventory value, tracking transactions and identifying products that require restocking.

### 4.2 Project Objectives

List all 20 required project features as individual bullet-point objectives. Explain each feature briefly and accurately according to the actual implementation.

## 5. SOFTWARE AND SYSTEM REQUIREMENTS

### 5.1 Hardware Requirements

Mention the basic computer system requirements.

### 5.2 Software Requirements

Include the following table:

| Component | Specification |
|---|---|
| Programming Language | Python 3.10 or above |
| Numerical Library | NumPy |
| Data Analysis Library | Pandas |
| Visualisation Library | Matplotlib |
| Testing Framework | unittest |
| Data Storage | CSV files |
| Data Export | JSON |
| Operating System | Windows / Linux / macOS |
| Free Storage | Approximately 100 MB |

## 6. SYSTEM DESIGN AND METHODOLOGY

### 6.1 Overall System Architecture

Explain the layered architecture:

1. Application Layer – App
2. Reporting Layer – NumPy, Pandas and Matplotlib
3. Storage Layer – Storage
4. Inventory Management Layer – Inventory
5. Data Record Layer – Product and Transaction

### 6.2 Data Flow Diagram

Include a clearly labelled data flow diagram showing the interaction between the user, application, inventory operations, storage system and reporting modules.

### 6.3 CSV Data Structure

Explain the two CSV files.

**products.csv**

Fields:
- product_id
- name
- category
- unit_price
- quantity
- reorder_level

**transactions.csv**

Fields:
- transaction_id
- timestamp
- product_id
- type
- quantity
- unit_price
- value

### 6.4 Stock-Out Flowchart

Include a flowchart showing:
1. Start.
2. Enter product ID.
3. Validate product ID.
4. Enter stock-out quantity.
5. Validate quantity.
6. Check available stock.
7. Reject if requested quantity exceeds available stock.
8. Update inventory quantity.
9. Record transaction.
10. Save inventory data.
11. Display updated stock.
12. End.

### 6.5 Reorder Alert Mechanism

Include the following table:

| Alert Level | Condition |
|---|---|
| NORMAL | Quantity is at or below the reorder level |
| URGENT | Quantity is zero or at or below 50% of the reorder level |

Example: If the reorder level is 10 units:

- 11 units – No alert
- 10 units – NORMAL
- 6 units – NORMAL
- 5 units – URGENT
- 0 units – URGENT

### 6.6 Input Validation and Error Handling

Explain validation of product IDs, product names, categories, quantities, prices and stock transactions. Discuss duplicate detection, invalid input handling, corrupted CSV records and error prevention.

## 7. IMPLEMENTATION OF MAJOR MODULES

Explain the implementation of each major module.

Include a table with two columns:

| Module / Function | Functionality |
|---|---|
| Product | Represents product records using a dataclass |
| Transaction | Stores inventory transaction details |
| Inventory | Manages product and stock operations |
| add_product() | Adds new products |
| update_product() | Updates product information |
| stock_in() | Increases available stock |
| stock_out() | Decreases available stock |
| alert_level() | Determines reorder alert status |
| total_value() | Calculates inventory valuation |
| numpy_summary() | Calculates statistical summaries |
| category_report() | Generates category-wise reports |
| monthly_report() | Generates monthly transaction reports |
| daily_stock_out_value() | Calculates daily stock-out values |
| stock_chart() | Generates inventory stock charts |
| sales_chart() | Generates estimated sales-value charts |
| Storage.save() | Saves inventory and transaction records |
| export_json() | Exports inventory data into JSON format |
| App | Provides the console menu and user interaction |

Include and explain relevant source-code snippets from the actual project for:

- stock_out()
- alert_level()
- Storage.save()

Explain the purpose and working of each snippet.

## 8. RESULTS AND DISCUSSION

Present the actual application outputs with screenshots and explanations.

Include screenshots of:

1. Main application menu.
2. Product inventory table.
3. Reorder alert display.
4. Category-wise inventory report.
5. Monthly transaction report.
6. Stock chart.
7. Estimated sales-value chart.
8. JSON export output.

### 8.1 Demonstration Results

Include the following confirmed demonstration figures:

- Total products: 12
- Total inventory units: 303
- Total inventory value: Obtain from actual application output.

Discuss the observed functionality, inventory calculations, reorder notifications and generated reports.

Do not fabricate screenshots, numerical values or execution results.

## 9. TESTING AND VALIDATION

### 9.1 Automated Testing

Explain the use of Python's unittest framework.

Include the command:

python -m unittest discover -s tests -v

Report the test results:

51 automated tests passed out of 51, as reported by the project test suite at packaging time.

### 9.2 Test Case Table

Include the following columns:

| Test Case | Expected Result | Observed Result | Status |
|---|---|---|---|

Cover product validation, duplicate detection, stock-in, stock-out, reorder thresholds, inventory valuation, CSV storage, corrupted data handling, JSON export and empty reports.

### 9.3 Manual Testing

Include a separate table documenting the manual testing of every console menu option.

Clearly distinguish automated test coverage from features that were verified only through manual testing.

Mention that terminal colours, box characters, interactive chart windows, real file-permission situations and cross-platform behaviour require manual verification.

## 10. LIMITATIONS AND FUTURE SCOPE

### 10.1 Limitations

- Designed for single-user operation.
- No login or authentication system.
- CSV files are used instead of a relational database.
- Sales value is estimated from stock-out transactions.
- Supplier management is not implemented.
- Barcode-based product identification is not available.

### 10.2 Future Scope

- Integration with SQLite or MySQL.
- Development of a graphical user interface.
- Development of a web-based inventory dashboard.
- Supplier and purchase-order management.
- Barcode scanning and product identification.
- Automated reorder quantity calculation.
- Automated low-stock notifications.

## 11. CONCLUSION

Summarise the successful development of the Inventory and Reorder Tracker. Explain how Python programming, object-oriented design, CSV storage, NumPy, Pandas and Matplotlib have been applied to develop a functional inventory management application.

Discuss the significance of automated stock monitoring, inventory valuation, transaction tracking, reorder alerts and testing.

## 12. REFERENCES

Include official documentation references:

1. Python Documentation – https://docs.python.org/3/
2. NumPy Documentation – https://numpy.org/doc/
3. Pandas Documentation – https://pandas.pydata.org/docs/
4. Matplotlib Documentation – https://matplotlib.org/stable/contents.html

Follow the reference formatting used in the department's sample report.

## 13. APPENDIX

### Appendix A: CSV File Formats

Include the structure and sample records of products.csv and transactions.csv.

### Appendix B: Installation and Execution

Include the installation and execution commands:

pip install -r requirements.txt

python inventory_tracker.py

### Appendix C: Automated Testing

Include:

python -m unittest discover -s tests -v

### Appendix D: Sample Application Session

Include the actual sample session from:

docs/sample_output.txt

### Appendix E: Source Code

Provide the complete source-code listing or refer to the source file inventory_tracker.py included in the project repository.

---

## FINAL REPORT EXPORT REQUIREMENTS

**Final PDF Filename:**

Inventory_Reorder_Tracker_Report.pdf

**Required submission location:**

report/Inventory_Reorder_Tracker_Report.pdf

Export the completed report from Microsoft Word or Google Docs in PDF format.

## GITHUB SUBMISSION INSTRUCTIONS

**Deadline: 20 November 2026**

### 1. Create a GitHub Account

Visit https://github.com/ and create a free account if you do not already have one.

### 2. Create a New Repository

Repository name:

Inventory-and-Reorder-Tracker

Visibility: Public

Do not initialise another README because the project already contains one.

### 3. Upload the Project

Open the terminal inside the project folder and execute:

git init

git add .

git commit -m "Inventory and Reorder Tracker - final submission"

git branch -M main

git remote add origin https://github.com/YOUR_USERNAME/Inventory-and-Reorder-Tracker.git

git push -u origin main

Replace YOUR_USERNAME with your actual GitHub username.

### 4. Upload the Final Project Report

Place the PDF inside the report folder:

report/Inventory_Reorder_Tracker_Report.pdf

Then execute:

git add .

git commit -m "Add project report"

git push

Alternatively, use GitHub's Add file → Upload files option to upload the additional files through the website.

### 5. Verify Repository Access

Open the repository link in a private/incognito browser window.

Confirm that:
- The repository is publicly accessible.
- All source files are uploaded.
- The project report PDF is available.
- Supporting files and documentation are accessible.

### 6. Google Sheet Submission

Only ONE team member should submit the public GitHub repository link in the Google Sheet provided by the department.

Avoid duplicate submissions from multiple members of the same group.

---

**FINAL DELIVERABLE:** A complete, professionally formatted academic project report in PDF format, accompanied by the full Python source code, test files, supporting data and documentation in a public GitHub repository.
