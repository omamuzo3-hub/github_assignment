# Jatto Favour - File Handling Assignment

## 📝 About
This program demonstrates **file handling** in Python with a practical example:  
managing visitor entries in a file called `visitors.txt`.

---

## 📂 Features
- Uses **with statement** for safe file handling.  
- Asks the user to enter a visitor’s name.  
- Checks the **last line** in `visitors.txt`:
  - If the same visitor name appears again → raises a **custom exception** `DuplicateVisitorError`.  
- Ensures **no visitor can be added within 5 minutes** of the last entry.  
- If the file doesn’t exist, it is automatically created.  
- Logs each visitor’s name with a **timestamp**.  
- Handles errors gracefully so the program does not crash.

---

## ▶️ How to Run
Run the script directly in the terminal:
```bash
python visitors.py
