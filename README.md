# Smart Expense Tracker

A command-line expense tracking application built in Python that enables users to manage personal finances efficiently. The tracker persists data in Excel spreadsheets, providing real-time insights into spending patterns through category-based aggregation and visual analytics.

## Why I Built This

I wanted to create an app that could track my expenses so that I could become more responsible with my spending habits. This project actually helps me see patterns. Plus, it was an interesting project to build that taught me several new skills, most notably file handling and digital representation (matplotlib).

## Features

- **Add Expenses** – Record transactions with date, description, category, and amount
- **View History** – Display all recorded expenses in a formatted table
- **Total Spending** – Calculate aggregate spending across all transactions
- **Category Analysis** – Summarize expenses by category with subtotals
- **Data Visualization** – Generate pie charts showing expense distribution by category
- **Persistent Storage** – Automatically create and maintain Excel spreadsheet database
- **Input Validation** – Error handling for invalid monetary amounts
- **Interactive CLI** – User-friendly menu-driven interface

## Technologies Used

- **Python 3** – Core application logic
- **OpenPyXL** – Excel file creation and manipulation
- **Matplotlib** – Data visualization and chart generation
- **DateTime** – Automatic timestamp recording for transactions

## Project Structure

```
expense-tracker.py       # Main application file (172 lines)
requirements.txt         # Python package dependencies
expenses.xlsx            # Auto-generated Excel database (created on first run)
README.md                # Documentation
```

**Key Components:**

- `ExpenseTracker` class – Encapsulates all tracker functionality
- `setup_file()` – Initializes Excel workbook with headers if not present
- `add_expense()` – Handles user input and appends to spreadsheet
- `view_expenses()` – Displays all transactions with enumeration
- `total_spending()` – Calculates sum of all amounts
- `category_summary()` – Aggregates spending by category using dictionaries
- `generate_chart()` – Creates pie chart from categorical data
- `menu()` – REPL-style command dispatcher

## Installation

### Prerequisites

- Python 3.7 or higher
- pip (Python package manager)

### Setup

1. **Clone or download the repository:**

   ```bash
   git clone <repository-url>
   cd smart-expenses-tracker
   ```

2. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application:**
   ```bash
   python expense-tracker.py
   ```

## Usage

Launch the application using:

```bash
python expense-tracker.py
```

You will see an interactive menu:

```
======Expense Tracker =====
1. Add Expense
2. View Expenses
3. Total Spending
4. Category Summary
5. Generate Pie Chart
6. Exit
```

Select an option by entering the corresponding number and follow the prompts.

## Example Workflow

Here's a typical session:

```
======Expense Tracker =====
1. Add Expense
2. View Expenses
3. Total Spending
4. Category Summary
5. Generate Pie Chart
6. Exit

Enter choice: 1
Description: Morning Coffee
Category: Food & Beverage
Amount: ₹120
Expense added successfully.

Enter choice: 1
Description: Gym Membership
Category: Health
Amount: ₹2500
Expense added successfully.

Enter choice: 2
--- Expenses ---
1. 2026-06-03 | Morning Coffee | Food & Beverage | ₹120.0
2. 2026-06-03 | Gym Membership | Health | ₹2500.0

Enter choice: 3
Total Spending: ₹2620.00

Enter choice: 4
--- Category Summary ---
Food & Beverage: ₹120.00
Health: ₹2500.00

Enter choice: 5
[Pie chart displayed in Matplotlib window]
```

## Python Concepts Demonstrated

### Object-Oriented Programming

- Encapsulation: All tracker logic is contained within the `ExpenseTracker` class
- Initialization: `__init__()` and `setup_file()` handle object instantiation and file setup
- State management: Class maintains implicit state through file operations

### File Handling & Persistence

- File existence checking using `os.path.exists()`
- Excel workbook creation with `openpyxl.Workbook()`
- Dynamic Excel file loading and modification with `load_workbook()`
- Header row definition and structured data appending

### Error Handling

- Try-except block for numeric input validation
- Graceful degradation when no expenses exist
- User feedback for invalid menu selections

### Data Aggregation & Analysis

- Dictionary-based categorical summation using `get()` method with defaults
- Iteration over spreadsheet rows using generator (`iter_rows()`)
- Tuple unpacking for row data extraction

### Data Visualization

- Matplotlib pie chart generation with automatic percentage labeling
- Conditional rendering based on data availability
- Clear labeling and titling for visual clarity

### External Libraries

- **OpenPyXL** – Programmatic Excel interaction without requiring Excel installation
- **Matplotlib** – Publication-ready data visualization

## Future Improvements

- **Budget Tracking** – Set spending limits per category with alerts
- **Data Export** – CSV export functionality for external analysis
- **Recurring Expenses** – Automate entry of monthly subscriptions
- **Search & Filter** – Query expenses by date range or category
- **Spending Analytics** – Monthly/yearly trends and comparison reports
- **GUI Interface** – Replace CLI with Tkinter/PyQt for broader accessibility
- **Multi-user Support** – Database backend (SQLite/PostgreSQL) for shared tracking
- **Machine Learning Integration** – Predictive spending analysis and anomaly detection

## Learning Outcomes

Building this project reinforced several key software development practices:

- **Clean Architecture** – Separating concerns into methods with single responsibilities
- **Data Persistence** – Understanding file-based vs. database storage trade-offs
- **User Experience** – Designing intuitive CLI interfaces and clear prompts
- **Error Resilience** – Anticipating edge cases (empty datasets, invalid inputs)
- **Library Integration** – Leveraging external packages to solve domain-specific problems
- **Code Organization** – Structuring a project for maintainability and extensibility

This project serves as a practical foundation for exploring distributed systems (cloud sync), relational databases, and web frameworks in future iterations.
