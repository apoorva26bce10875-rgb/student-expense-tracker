# student-expense-tracker
## Project Description  The **Student Expense Tracker** is a Python-based program designed to help students manage and monitor their daily expenses. The program allows users to add expense details such as category, description, and amount. Users can also view their expense history, calculate total spending, search expenses by category.
# Student Expense Tracker

## Files in the Project

```text
StudentExpenseTracker/
│
├── student_expense_tracker.py
└── README.md
```

### `student_expense_tracker.py`

Contains the complete Python program for the Student Expense Tracker, including adding, viewing, searching, calculating, and deleting expenses.

### `README.md`

Contains information about the project files and instructions for running the program.

## How to Run

### 1. Install Python

Make sure Python is installed on your computer.

Check the installation using:

```bash
python --version
```

### 2. Download or Clone the Project

Download the project files or clone the GitHub repository.

### 3. Open the Project

Open the project folder in **PyCharm**, **VS Code**, or any Python-supported IDE.

### 4. Run the Program

Open the terminal in the project folder and run:

```bash
python student_expense_tracker.py
```

Alternatively, open `student_expense_tracker.py` in your IDE and click **Run**.

### 5. Use the Program

The program will display the main menu:

```text
1. Add Expense
2. View Expenses
3. Calculate Total Expense
4. Search Expense by Category
5. Delete Expense
6. Exit
```

Enter the number corresponding to the operation you want to perform.

# Student Expense Tracker

expenses = []

while True:
    print("\n===== STUDENT EXPENSE TRACKER =====")
    print("1. Add Expense")
    print("2. View Expenses")
    print("3. Calculate Total Expense")
    print("4. Search Expense by Category")
    print("5. Delete Expense")
    print("6. Exit")


    PROGRAM

    choice = int(input("Enter your choice: "))

    # Add Expense
    if choice == 1:
        category = input("Enter category (Food/Travel/Shopping/Education/Other): ")
        description = input("Enter description: ")
        amount = float(input("Enter amount: ₹"))

        expense = {
            "category": category,
            "description": description,
            "amount": amount
        }

        expenses.append(expense)

        print("Expense added successfully!")

    # View Expenses
    elif choice == 2:
        if len(expenses) == 0:
            print("No expenses recorded.")

        else:
            print("\n----- EXPENSE HISTORY -----")

            for i, expense in enumerate(expenses, start=1):
                print("\nExpense", i)
                print("Category:", expense["category"])
                print("Description:", expense["description"])
                print("Amount: ₹", expense["amount"])

    # Calculate Total
    elif choice == 3:
        total = 0

        for expense in expenses:
            total += expense["amount"]

        print("Total Expense: ₹", total)

    # Search by Category
    elif choice == 4:
        category = input("Enter category to search: ")

        found = False

        for expense in expenses:
            if expense["category"].lower() == category.lower():
                print("\nDescription:", expense["description"])
                print("Amount: ₹", expense["amount"])
                found = True

        if not found:
            print("No expenses found in this category.")

    # Delete Expense
    elif choice == 5:
        if len(expenses) == 0:
            print("No expenses to delete.")

        else:
            for i, expense in enumerate(expenses, start=1):
                print(i, expense["category"], expense["description"],
                      "₹", expense["amount"])

            number = int(input("Enter expense number to delete: "))

            if 1 <= number <= len(expenses):
                expenses.pop(number - 1)
                print("Expense deleted successfully!")
            else:
                print("Invalid expense number.")

    # Exit
    elif choice == 6:
        print("Thank you for using Student Expense Tracker!")
        break

    else:
        print("Invalid choice. Please try again.")
