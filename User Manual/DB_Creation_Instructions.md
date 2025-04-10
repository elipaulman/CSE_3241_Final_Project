# CSE_3241_Final_Project

## Setting Up the SQLite Database

Follow these steps to set up the SQLite database on your local machine:

### Prerequisites
1. **Download SQLite**:
   - Go to the [SQLite Downloads page](https://sqlite.org/download.html).
   - Download the **Precompiled Binaries for Windows** (e.g., `sqlite-tools-win32-x86-*.zip`).
   - Extract the `.zip` file to a folder, such as `C:\sqlite`.

2. **Add SQLite to PATH (Optional)**:
   - Add the folder containing `sqlite3.exe` to your system's PATH environment variable for easier access.

### Steps to Recreate the Database
1. **Navigate to the Project Directory**:
   - Open a terminal or Command Prompt and navigate to the folder containing your database and SQL files:
     ```sh
     cd "<path-to-your-project-folder>"
     ```

2. **Create the SQLite Database**:
   - Open the SQLite shell:
     ```sh
     sqlite3 <your-database-name>.sqlite
     ```
   - Inside the SQLite shell, run the following command to create the tables:
     ```sql
     .read <your-create-sql-file>.txt
     ```
   - If you have a file for inserting data, run:
     ```sql
     .read <your-insert-sql-file>.txt
     ```

3. **Verify the Database**:
   - Use `.tables` to list all tables and ensure they were created successfully.
   - Use SQL queries like `SELECT * FROM table_name;` to view the data.

### Optional: Use a GUI Tool
- You can use [DB Browser for SQLite](https://sqlitebrowser.org/) to open and inspect the database.