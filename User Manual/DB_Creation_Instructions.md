# Bookstore Database Setup Instructions

## Setting Up the SQLite Database

Follow these steps to set up the Bits & Books Bookstore database on your local machine:

### Prerequisites
1. **Download SQLite**:
   - Go to the [SQLite Downloads page](https://sqlite.org/download.html).
   - Download the **Precompiled Binaries for Windows** (e.g., `sqlite-tools-win32-x86-*.zip`).
   - Extract the `.zip` file to a folder of your choice, such as `C:\sqlite`.

2. **Add SQLite to PATH (Optional)**:
   - Add the folder containing `sqlite3.exe` to your system's PATH environment variable for easier access.

3. **Alternative: Use Database Browser for SQLite**:
   - For a graphical interface, you can download [DB Browser for SQLite](https://sqlitebrowser.org/).
   - This tool provides a user-friendly GUI for database operations.

### Creating the Database from Scratch

1. **Navigate to the Project Directory**:
   - Open a terminal or Command Prompt and navigate to the project's DB folder:
     ```sh
     cd "path\to\CSE_3241_Final_Project\DB"
     ```

2. **Create and Set Up the Database**:
   - Create a new SQLite database:
     ```sh
     sqlite3 Bookstore.db
     ```
   - Enable foreign key constraints (important for maintaining data integrity):
     ```sql
     PRAGMA foreign_keys = ON;
     ```
   - Run the schema creation script:
     ```sql
     .read SQL_Create.txt
     ```
   - Populate the database with sample data:
     ```sql
     .read SQL_Insert.txt
     ```

3. **Verify the Database Setup**:
   - List all tables to ensure they were created correctly:
     ```sql
     .tables
     ```
   - You should see the following tables: 
     `author, book, book_author, bookDemand, category, customer, customer_contact, customer_order, inventory, orderItem, profitMargin, publisher`
   - Check database schema:
     ```sql
     .schema
     ```
   - Run a simple query to verify data was inserted:
     ```sql
     SELECT COUNT(*) FROM book;
     ```
   - Exit the SQLite shell:
     ```sql
     .exit
     ```

### Using the Provided Database File

If you already have the Bookstore.db file:

1. **Open the Existing Database**:
   - With SQLite command line:
     ```sh
     sqlite3 "path\to\CSE_3241_Final_Project\DB\Bookstore.db"
     ```
   - Or use DB Browser for SQLite to open the file directly.

2. **Run Sample Queries**:
   - You can run the sample queries from SQL_Queries.txt and SQL_InsertDelete_Samples.txt.
   - Example query to find low-stock books:
     ```sql
     SELECT b.Title, b.ISBN
     FROM book b
     JOIN inventory i ON b.ISBN = i.ISBN
     WHERE i.StockQuantity < 5;
     ```

### Using DB Browser for SQLite (Recommended for Beginners)

1. **Open the Database**:
   - Launch DB Browser for SQLite.
   - Click "Open Database" and navigate to the Bookstore.db file.
   - You can now browse tables, run SQL queries, and visualize the database structure.

2. **Execute SQL Files**:
   - Go to "File" → "Import" → "SQL file..."
   - Select SQL_Create.txt to create the schema (if starting with a new database).
   - Select SQL_Insert.txt to populate the database with data.

3. **Execute SQL Queries**:
   - Go to the "Execute SQL" tab.
   - Copy and paste queries from SQL_Queries.txt or write your own.
   - Click the "Execute" button (play icon) to run the query.

### Project-Specific Database Structure

The Bookstore database consists of the following main entities:
- Books (with ISBNs as unique identifiers)
- Authors (many-to-many relationship with books)
- Publishers (one-to-many relationship with books)
- Categories (one-to-many relationship with books)
- Customers (who place orders)
- Orders (containing multiple order items)

Auxiliary tables track inventory levels, book popularity, and profit margins.

### Troubleshooting

- **Foreign Key Constraints**: If you encounter foreign key constraint errors, ensure you have enabled foreign keys with `PRAGMA foreign_keys = ON;`
- **Table Already Exists**: If tables already exist when trying to create them, you may need to drop them first or use a new database file.
- **Missing Tables/Data**: Ensure that you're running the SQL scripts from the correct directory and that the file paths are correct.