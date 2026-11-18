# 📦 Inventory and Reorder Tracker
### Console-Based Inventory Management Application

A menu-driven inventory management application developed using **Python 3.10+**. It enables users to manage products, monitor stock levels, record stock movements, generate reorder alerts, analyse inventory data, and produce reports through a simple console interface.

The application uses CSV files for persistent storage and integrates NumPy, Pandas, and Matplotlib for statistical analysis, reporting, and data visualisation.

---

## 🚀 Key Features

- **Product Management:** Add, view, search, and update inventory products.
- **Stock Management:** Record stock-in and stock-out transactions with automatic quantity updates.
- **Reorder Alerts:** Identify products requiring restocking through NORMAL and URGENT alerts.
- **Inventory Valuation:** Calculate individual product values and total inventory value.
- **NumPy Statistical Analysis:** Generate inventory summaries, including mean, median, minimum, and maximum stock quantities.
- **Pandas Reporting:** Generate category-wise and monthly inventory reports.
- **Data Visualisation:** Create stock and estimated sales-value charts using Matplotlib.
- **JSON Export:** Export inventory information into JSON format.
- **Data Persistence:** Store inventory records and transaction history in CSV files.
- **Input Validation:** Prevent invalid product details, quantities, prices, and stock operations.
- **Automated Testing:** Includes 51 unit tests using Python's unittest framework.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python 3.10+ | Core application development |
| NumPy | Statistical calculations |
| Pandas | Inventory analysis and reporting |
| Matplotlib | Charts and data visualisation |
| CSV | Inventory and transaction storage |
| JSON | Data export |
| Dataclasses | Structured product and transaction records |
| Unittest | Automated testing |

---

## 📁 Project Structure

```text
Inventory-and-Reorder-Tracker/
│
├── inventory_tracker.py
│
├── requirements.txt
├── README.md
├── .gitignore
│
├── tests/
│   └── test_inventory_tracker.py
│
├── docs/
│   ├── sample_output.txt
│   └── PROJECT_REPORT_OUTLINE.md
│
└── data/
    ├── products.csv
    ├── transactions.csv
    ├── charts/
    └── exports/
```

**Note:** The `data/` directory and its files are created automatically when the application runs.

---

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/Inventory-and-Reorder-Tracker.git
```

### 2. Navigate to the Project Directory

```bash
cd Inventory-and-Reorder-Tracker
```

### 3. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate the virtual environment:

**Windows:**
```bash
.venv\Scripts\activate
```

**macOS / Linux:**
```bash
source .venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Application

```bash
python inventory_tracker.py
```

The application starts in the console, and inventory data is stored in the local `data/` directory.

### Optional: Custom Data Directory

```bash
python inventory_tracker.py --data-dir D:\my_data
```

---

## 🧩 Application Architecture

The application follows a modular, object-oriented design.

| Component | Description |
|---|---|
| `Product` | Dataclass representing inventory products and validating product attributes. |
| `Transaction` | Represents stock-in and stock-out records. |
| `Inventory` | Handles product management, stock operations, searches, alerts, and inventory valuation. |
| `Storage` | Manages CSV loading, saving, backup creation, and JSON exports. |
| `Student` | Not applicable; the application uses inventory-specific data structures. |
| `NumPy Summary` | Calculates statistical summaries of inventory data. |
| `Pandas Reports` | Generates category-wise and monthly inventory reports. |
| `Matplotlib Charts` | Produces stock and estimated sales-value visualisations. |
| `App` | Handles the console menu, user inputs, and application workflow. |
| `Validators` | Validate text, IDs, quantities, prices, and transaction values. |

---

## 📊 Inventory Management Operations

### 1. Product Management
Users can add new products, view existing inventory, search for products, and update product information.

### 2. Stock-In Operations
Stock-in operations increase the available quantity and automatically record the corresponding transaction.

### 3. Stock-Out Operations
Stock-out operations decrease the available quantity. The application rejects requests that exceed the available stock.

### 4. Reorder Alert System

The application identifies products that require restocking.

| Alert Level | Condition |
|---|---|
| NORMAL | Quantity is at or below the reorder level. |
| URGENT | Quantity is zero or at or below 50% of the reorder level. |

**Example:** If the reorder level is 10 units:

- 11 units: No alert
- 10 units: NORMAL
- 6 units: NORMAL
- 5 units: URGENT
- 0 units: URGENT

### 5. Inventory Valuation

Calculates the total value of inventory using:

**Product Value = Unit Price × Available Quantity**

**Total Inventory Value = Sum of All Product Values**

### 6. Data Analysis and Reporting

NumPy and Pandas are used to generate statistical summaries, category-wise reports, monthly transaction reports, and daily stock-out value analysis.

### 7. Data Visualisation

Matplotlib generates charts illustrating inventory stock levels and estimated sales values.

### 8. JSON Export

The application supports exporting inventory information into JSON format for structured data storage and external use.

---

## 💾 Data Storage and Persistence

The application uses CSV files to maintain inventory records and transaction history.

**products.csv**

Stores:
- Product ID
- Product Name
- Category
- Unit Price
- Available Quantity
- Reorder Level

**transactions.csv**

Stores:
- Transaction ID
- Timestamp
- Product ID
- Transaction Type
- Quantity
- Unit Price
- Transaction Value

Data is saved after inventory changes and when the application exits. The storage module also implements backup and recovery-related handling for corrupted CSV records.

---

## 🧪 Testing and Validation

The project includes an automated testing suite implemented using Python's `unittest` framework.

### Run Automated Tests

```bash
python -m unittest discover -s tests -v
```

### Testing Coverage

- Input validation and error handling.
- Duplicate product detection.
- Stock-in and stock-out operations.
- Reorder alert boundary conditions.
- Inventory valuation.
- CSV saving and reloading.
- Corrupted data handling.
- JSON export.
- Empty inventory reports.
- Console menu operations.

### Testing Results

**51 unit tests** were reported as passing at packaging time.

Testing environment:
- Python 3.12
- NumPy 2.4
- Pandas 3.0
- Matplotlib 3.10

Some aspects, including interactive chart windows, terminal formatting, and operating-system-specific behaviour, require manual verification.

---

## 📋 Sample Application Output

A sample console session is available in:

```text
docs/sample_output.txt
```

It demonstrates the application's menu operations and expected console responses.

---

## 🎯 Project Objectives

1. Develop a functional console-based inventory management system.
2. Apply object-oriented programming principles in Python.
3. Implement reliable stock-in and stock-out operations.
4. Automate inventory monitoring and reorder notifications.
5. Perform statistical analysis using NumPy.
6. Generate structured inventory reports using Pandas.
7. Visualise inventory information using Matplotlib.
8. Implement persistent storage and data export functionality.
9. Improve reliability through input validation and automated testing.

---

## 🔮 Future Scope

- Develop a graphical user interface (GUI).
- Integrate a relational database such as SQLite or MySQL.
- Implement barcode-based product identification.
- Add supplier and purchase-order management.
- Introduce automated email notifications for low-stock products.
- Develop a web-based inventory management dashboard.

---

## 👥 Project Team

**Project Title:** Inventory and Reorder Tracker – Console-Based Application

**Department:** Electronics and Communication Engineering

**Institution:** Institute of Engineering & Management (IEM), Salt Lake, Kolkata

**Academic Year:** 2026

**Team Members:**

Add the names and roll numbers of all group members here.

---

## 📄 Project Documentation

The complete project report is available in the repository in PDF format.

---

## 📜 License

This project is developed for academic and educational purposes as part of an engineering project submission.
