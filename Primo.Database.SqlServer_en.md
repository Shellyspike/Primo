# Primo.Database.SqlServer

**Primo.Database.SqlServer** is a library designed to simplify working with MS SQL Server databases in a Windows environment. The package addresses tasks related to executing SQL queries and managing database connections, providing developers with a convenient and intuitive interface.

## Installation and Setup

To install the **Primo.Database.SqlServer** package, use the Visual Studio Dependency Manager or download it from [NuGet.org](https://www.nuget.org/).

### Installation via Dependency Manager:

1. **Open the Dependency Manager:**
   - In the main menu of Primo RPA Studio, select `Manage Dependencies`.
   - Or right-click in the project panel and choose `Dependencies` from the context menu.

2. In the opened window, navigate to the **NuGet.org** section and enter **Primo RPA** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.Database.SqlServer** and click **Install**.

4. Click **Save**.

5. In the modal window click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

More detailed documentation is available on the [Primo RPA website](https://docs.primo-rpa.com).

## Features and Capabilities

Here are the main functions that can be performed using the elements provided by the library:

- **Executing SQL queries** using the **"Execute query"** element.
- **Managing connections**: the ability to use existing connections or configure new ones through element properties with the **"Connect"** and **"Disconnect DB"** elements.
- **Inserting data** into the database using the **"Insert"** element, allowing you to quickly add new records to tables.

## Element Properties

### General Properties
The following properties are common across multiple elements and are defined under the **General** section:

- **Continue on exception**: The script will continue running even if an error occurs during the execution of the element.
- **Disable logging**: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to `File > Settings > General > Elements` and set the desired value in the `Disable logging for new elements` checkbox.
- **Name**: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical components are used.
- **Screenshot on error**: A screenshot will be taken if an error occurs.
- **Screenshot on finish**: Allows taking a screenshot upon the element's completion. All screenshots are saved in the `.Screenshots` folder, which is automatically created inside the process folder.
- **Wait after (ms)**: Pause after the element is executed.
- **Wait before (ms)**: Adds a pause before the element is executed.

### Properties of the "Connect" Element

The "Connect" element establishes a connection to a database (DB). The established connection allows for the transmission of queries and the reception of responses between the application and the database.

1. **Database**:
   - **Connection string**: Required. The connection string that will be used to establish a connection to the database.

2. **Output**:
   - **DB connection**: The database connection instance. This allows you to save the active connection to a variable, which can be used elsewhere in the script for faster connection or disconnection from the database.

### Properties of the "Insert" Element

The "Insert" element inserts data into the specified database (DB) table.

1. **Database**:
   - **Connection string**: The connection string that will be used to establish a connection to the database.
   - **DB connection**: Required field. A variable containing the database connection instance. If this field is filled, leave the "Connection string" field empty.

2. **Output**:
   - **Records**: The number of rows processed.

3. **Query**:
   - **Data**: Required. The data in table format. Specify the variable name.
   - **Table**: Required. The name of the database table where you want to insert the data.
   - **Time-out**: Required. The query timeout in seconds.

### "Execute Query" Element Properties

1. **Database**:
   
   - **Connection string**: The connection string used to establish a connection to the database. 
   - **DB connection**: A variable containing the instance of the database connection. Fill this property if you want to use an already established and active database connection. If you fill in this property, leave the Connection string and DB Type properties empty.

2. ## Output

- **Records**: The number of processed rows.
- **Variable (array)**: A variable to store the query results in an array.
- **Variable (table)**: A variable to store the query results in a `DataTable`.

3. ## Query

- **Arguments (array)**: Query arguments in an array format.
- **Arguments (editor)**: Query arguments in string format. The string can be generated in the wizard window by clicking the ![alt text](image-1.png) button. An example of a result from the wizard:
     ```plaintext
     "{\"Args\":[{\"Position\":0,\"Name\":\"@par1\",\"Script\":\"\\\"test\\\"\"}]}"
     ```
- **Has results**: Indicator of whether query results are expected. Check this if the query is supposed to return data (e.g., `SELECT * FROM table`). If it’s a query like `INSERT INTO` or `DELETE FROM` that does not return data, leave this unchecked..
- **Query**: Required. The SQL query text. An example for PostgreSQL:
     ```sql
     "SELECT * FROM table1 WHERE column1 = @par1"
     ```
- **Time-out**: Query timeout in seconds.

### Properties of the "Disconnect DB" Element

The "Disconnect DB" element terminates the connection to the database.

1. **Database**:
- **DB connection**: Required. A variable containing the database connection instance.
   
## Дополнительные материалы

An example RPA project demonstrating the library's functionality is available in our [public repository](https://github.com/PrimoRPA/Learning).

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
