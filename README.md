1. Parse sys args
Reads command-line arguments using sys.argv.
Assigns values to variables representing script name, database details, audit key, authentication credentials, load type, and table name.
2. Connect to Datawarehouse
Uses pyodbc and sqlalchemy to connect to a SQL Server data warehouse.
3. Create Functions
3.1 Error Log Function (errorLog)
Logs errors to a predefined SQL engine.
Takes parameters like audit key, exception (e), and optional details.
3.2 Object to String Function (convert_objects_to_strings)
Converts 'object' columns in a DataFrame to 'string' for SQLAlchemy compatibility.
4. Import Required Libraries
Imports necessary libraries for the script, including Azure-related libraries, datetime handling, pandas, requests, and SQLAlchemy.
5. Authenticate with PBI Admin API
Uses Azure's ClientSecretCredential to authenticate and obtain an access token for the Power BI Admin API.
6. Retrieve Workspaces and Store in DataFrame
Makes various API calls to Power BI Admin API based on the specified 'table' value.
Retrieves information about workspaces, reports, datasets, apps, modified workspaces, workspace users, refreshables, app users, and activity events.
Processes and organizes the retrieved data into pandas DataFrames.
7. Insert Data into Data Lake
Inserts the retrieved data into the SQL Server database tables based on the specified 'table' value.
Utilizes SQLAlchemy's to_sql method for DataFrame-to-SQL insertion.
Note:
The code contains placeholder values like 'Enter Tenant Id', 'Enter Schema name', etc., which need to be replaced with actual values.
Some error handling is implemented, logging errors to the 'log.Error' table in the SQL database.
This script seems to be part of a larger ETL process that extracts information from the Power BI Admin API and loads it into a SQL Server data warehouse. It's essential to customize placeholder values and ensure compatibility with your specific environment and requirements.
