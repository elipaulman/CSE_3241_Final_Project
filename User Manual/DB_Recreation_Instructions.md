# Database Recreation Instructions

This document provides instructions on how to recreate the Bookstore database from scratch using the provided SQL scripts.

## Prerequisites

- SQLite3 command line tool or Firefox SQLite Admin tool
- Access to the SQL script files in the DB folder

## Files Overview

The database can be recreated using the following files:

1. **SQL_Create.txt**: Contains all schema creation scripts including tables, indexes, and views.
2. **SQL_Insert.txt**: Contains data insertion scripts to populate all tables.
3. **SQL_Queries.txt**: Contains sample queries referenced in the final report.
4. **SQL_InsertDelete_Samples.txt**: Contains sample INSERT and DELETE statements from the user manual.
5. **Bookstore.db**: Binary SQLite database file (provided as a convenience).

## Recreation Steps

### Option 1: Using the SQLite3 Command Line Tool

1. Open a command prompt/terminal.
2. Navigate to the folder containing the SQL scripts.
3. Create a new database by running:
   ```
   sqlite3 Bookstore_New.db
   ```
4. Import the schema creation script:
   ```
   .read SQL_Create.txt
   ```
5. Import the data insertion script:
   ```
   .read SQL_Insert.txt
   ```
6. Verify the database was created successfully by running a simple query:
   ```
   SELECT COUNT(*) FROM book;
   ```
7. Exit SQLite:
   ```
   .exit
   ```

### Option 2: Using Firefox SQLite Admin Tool

1. Open Firefox and the SQLite Admin extension.
2. Create a new database named "Bookstore_New.db".
3. Open the SQL_Create.txt file in a text editor.
4. Copy all contents.
5. Paste into the SQLite Admin query window and execute.
6. Open the SQL_Insert.txt file in a text editor.
7. Copy all contents.
8. Paste into the SQLite Admin query window and execute.

## Running Sample Queries

To test your newly created database with the sample queries:

1. Open your database in your preferred SQLite tool.
2. Open SQL_Queries.txt in a text editor.
3. Copy individual queries or sections.
4. Paste into your SQLite tool and execute.

## Testing INSERT/DELETE Operations

To test the sample INSERT and DELETE operations:

1. Open your database in your preferred SQLite tool.
2. Open SQL_InsertDelete_Samples.txt in a text editor.
3. Copy individual statements or sections.
4. Paste into your SQLite tool and execute.
5. Note: The INSERT statements should be executed in the order they appear in the file.
6. Note: The DELETE statements should be executed in the order they appear in the file to avoid constraint violations.

## Troubleshooting

If you encounter foreign key constraint errors:

1. Ensure you're running the scripts in the correct order (Create, then Insert).
2. Check that foreign key enforcement is enabled in SQLite:
   ```
   PRAGMA foreign_keys = ON;
   ```
3. Verify that you're not trying to delete data in an order that would violate constraints.

If you encounter unique constraint errors:

1. Ensure you haven't already executed the INSERT statements.
2. If recreating a database from scratch, make sure you're starting with a fresh database file.