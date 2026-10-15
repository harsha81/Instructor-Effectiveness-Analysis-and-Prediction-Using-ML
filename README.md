# 📚 PDF Library & Reading Tracker

A sleek and simple Python desktop application to manage your local PDF book collection. Keep track of what you need to read, open books directly from the app, and log your completed reads into an Excel database automatically.

## ✨ Features

- **Automated Scanning**: Automatically detects all `.pdf` files in your designated library folder.
- **Progress Tracking**: Sorts your books into "Pending" and "Completed" lists.
- **Persistent Storage**: Uses a Pandas-powered Excel backend (`books_list.xlsx`) to remember your reading history across sessions.
- **One-Click Read**: Select any pending book and click "Open" to instantly launch it in your default PDF viewer.
- **Easy Updates**: Mark books as completed with a single click, automatically migrating them to the finished list and updating the Excel database.

## 🎨 UI Design & Layout

The application features a clean, dual-pane, 1900x800 graphical interface. 

| 📖 Pending Books (Listbox) | 🎓 Completed Books (Listbox) |
| :--- | :--- |
| `Book_1_Python_Basics.pdf` | `Book_3_Data_Science.pdf` |
| `Book_2_Advanced_Tkinter.pdf` | `Book_4_Machine_Learning.pdf` |
| ... | ... |
| **[ Open ]** *(Opens selected PDF)* | **[ Mark as Completed ]** *(Moves book to completed)*|

## 🛠️ Prerequisites

Before running this application, ensure you have Python installed along with the following libraries:

- `pandas`
- `openpyxl` (Required by pandas to read/write `.xlsx` files)

You can install the required packages using pip:
```bash
pip install pandas openpyxl
```

## 🚀 Setup & Installation

1. **Clone or Download** the script to your local machine.
2. **Configure your directories**: 
   Open the Python script and locate the following lines near the bottom of the code:
   ```python
   folder_path = r"D:/Books"  # Update to your actual PDF folder
   excel_file = r"D:/VSS/Library/books_list.xlsx" # Update to where you want the Excel file saved
   ```
   *Note: Make sure the folders you specify actually exist on your machine, otherwise the script will throw an error.*
3. **Run the application**:
   ```bash
   python your_script_name.py
   ```

## 📖 Usage Guide

1. **Launch the App**: When the app opens, it will scan your folder and populate the "Pending Books" list. If the Excel file doesn't exist, it will create one automatically.
2. **Read a Book**: Click on any book in the **Pending Books** column and click the **Open** button.
3. **Mark as Read**: Once you finish a book, select it in the **Pending Books** column and click **Mark as Completed**. It will instantly move to the Completed list and your Excel file will be updated.

## 💻 Technologies Used

- **Python 3**: Core programming language.
- **Tkinter**: For the Graphical User Interface (GUI).
- **Pandas**: For reading, creating, and updating the Excel database.
- **OS Module**: For directory scanning and file execution.

---
*Built to make reading tracking simple and effective.*
