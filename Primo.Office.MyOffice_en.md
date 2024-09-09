# Description of the Primo.Office.MyOffice Package

The **Primo.Office.MyOffice** package provides tools for automating tasks with MyOffice suite documents. It allows operations with text and spreadsheet documents, including data entry, formatting, and document structure management.

## General Information

**Primo.Office.MyOffice** is a library designed for interaction with documents in MyOffice applications. The package supports the automation of tasks with text and spreadsheet files, offering a convenient interface for performing various operations, such as data entry, document structure modification, macro execution, and more.

## Installation and Setup

To install the **Primo.Office.MyOffice**, package, use the Visual Studio Dependency Manager or download it from [NuGet.org](https://www.nuget.org/).

### Installation via Dependency Manager:

1. **Open the Dependency Manager:**
   - In the main menu of Primo RPA Studio, select `Manage Dependencies`.
   - Or right-click in the project panel and choose `Dependencies` from the context menu.

2. In the opened window, navigate to the **NuGet.org** section and enter **Primo RPA** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.Office.MyOffice** and click **Install**.

4. Click **Save**.

5. In the modal window click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

More detailed documentation is available on the [Primo RPA website](https://docs.primo-rpa.com).

## Library Composition

The library includes the following features:

- **Table**:
   - Sheets
      - Add sheet
      - Rename sheet
      - Get sheets
      - Delete sheet
   - Append range
   - Cell input
   - Delete columns
   - Delete rows
   - Insert columns
   - Insert rows
   - MyOffice Table
   - Read range
   - Run macro
   - Save workbook

- **Text**:
  - Add table row
  - Export document
  - Get text
  - Insert image
  - Insert table
  - MyOffice text
  - Read table
  - Replace text
  - Save document
  - Text input
  - Write table cell

To use an element, drag it into the working area of the Primo RPA Studio project.

## Usage Examples of Primo.Office.MyOffice

### Example of Working with Tables

```csharp
LTools.Office.MyOfficeTableApp app = LTools.Office.MyOfficeTableApp.Init(wf, fileName);
app.SheetAdd("Page1", 20, 3);
app.WriteCell("A4", "Value", "Page1");
app.Save();
```

### Example of Working with Text Documents

```csharp
LTools.Office.MyOfficeTextApp app = LTools.Office.MyOfficeTextApp.Init(wf, fileName);
app.AppendText("Text example");
app.Save();
```

### Example of Modifying an Existing Table

```csharp
var app = LTools.Office.MyOfficeTableApp.Init(wf, existingFile);
app.SheetSelect("Page1");
app.WriteCell("B2", "New value", "Page1");
app.Save();
```

### Example of Adding a Page to a Text Document

```csharp
LTools.Office.MyOfficeTextApp app = LTools.Office.MyOfficeTextApp.Init(wf, fileName);
app.AddPage();
app.AppendText("Text on a new page");
app.Save();
```

### Example of Creating a New Table with Headers

```csharp
var app = LTools.Office.MyOfficeTableApp.Init(wf, newFile);
app.SheetAdd("Page1", 10, 5);
app.WriteCell("A1", "Header 1", "Page1");
app.WriteCell("B1", "Header 2", "Page1");
app.Save();
```

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

### "Table" Section

All the components listed below are added to the working area inside the **MyOffice Table** element. This is a component for connecting to the "MyOffice Tables" application. If the specified file does not exist, a new one will be created. The **MyOffice Table** element includes the following properties:

- **Byte array**: Byte array of the document.
- **Codepage**.
- **File path**: By clicking the button ![alt text](image-3.png), you can specify the file path in the Explorer window.

---

#### "Sheets" Subsection

   ##### Add sheet
   
   A component for adding a new sheet to the Table. Includes the following properties:
   
   1. **Table**:
      - Columns — Number of columns.
      - Index — Sheet index.
      - Name — Name of the new sheet.
      - Rows — Number of rows.
   
   ##### Delete sheet
   
   A component for deleting a sheet from the Table. Includes the following properties:
   
   1. **Table**:
      - Index — Sheet index.

   ##### Get sheets
   
   A component for retrieving the list of sheets from the Table. Includes the following properties:
   
   1. **Output**:
      - Variable — Variable for storing the list of sheets.

   ##### Rename sheet
   
   A component for renaming a sheet in the Table. Includes the following properties:
   
   1. **Table**:
      - Name — Name of the sheet.
      - Index — Sheet index.

---

#### "Append range" Component

A component that writes data from a range of cells into the Table. Includes the following properties:

1. **Table**:
   - Add headers — Add table column headers.
   - As text — Insert value as text.
   - Direction — Direction of cell shift:
     - Down
     - Right
   - Expand range — Automatically expand the range to fit the data.
   - Number format — Format of the input number (#,#).
   - Overwrite — Indicator to overwrite data.
   - Range — Cell range to write (A1:D12).
   - Sheet index.
   - Sheet name.
   - Variable (information) — Variable for storing cell information data.
   - Variable (table) — Variable for storing table value data.
   - Variable (text) — Variable for storing text value data.

#### "Cell input" Component

This component writes data into a cell of the Table. Includes the following properties:

1. **Table**:
   - As text — Insert value as text.
   - Cell — Cell index.
   - Number format — Format of the input number (#,#).
   - Sheet index.
   - Sheet name.
   - Text.

#### "Insert columns" Component

A component that inserts columns into a sheet of the Table. Includes the following properties:

1. **Table**:
   - Index — Index of the column, to the right of which the insertion will occur. If not specified, the insertion is done at the end of the sheet.
   - Quantity — Number of columns to insert.
   - Sheet index.
   - Sheet name.

#### "Insert rows" Component

A component that inserts rows into a sheet of the Table. Includes the following properties:

1. **Table**:
   - Index — Index of the row, after which the insertion will occur. If not specified, the insertion is done at the end of the sheet.
   - Quantity — Number of rows to insert.
   - Sheet index.
   - Sheet name.

#### "Delete columns" Component

This element deletes columns from the Table sheet. Includes the following properties:

1. **Table**:
   - Index — Index of the column to delete.
   - Quantity — Number of columns to delete.
   - Sheet index.
   - Sheet name.

#### "Delete rows" Component

This element deletes rows from the Table sheet. Includes the following properties:

1. **Table**:
   - Index — Index of the row to delete.
   - Quantity — Number of rows to delete.
   - Sheet index.
   - Sheet name.

#### "Read range" Component

This element reads data from a range of cells in the Table. Includes the following properties:

1. **Output**:
   - Headers row — Indicates whether the first row contains headers (for the table). If checked, headers will be taken into account.
   - Variable (info) — Variable for storing cell information data.
   - Variable (table) — Variable for storing table value data.
   - Variable (text) — Variable for storing text value data.

2. **Table**:
   - Range — Range of cells to read ("A1:D12"). If not specified, the selected range will be read. If the "*" symbol is used, the entire sheet will be read.
   - Sheet index.
   - Sheet name.

#### "Run macro" Component

A component for executing a macro in the Table. Includes the following properties:

1. **Misc**:
   - Result.
2. **Table**:
   - Macro.

#### "Save workbook" Component

This element saves the current state of the Table file. If the file path is not specified, the file opened within the current Table container will be saved. Includes the following properties:

1. **Table**:
   - File path — By clicking the button ![alt text](image-3.png), you can specify the file path in the Explorer window.

### "Text" Section

All the components listed below are added to the working area inside the **MyOffice Text** element. This container connects to the MyOffice Text application. If the specified file does not exist, a new one will be created. The **MyOffice Text** element includes the following properties:

1. **Table**:
   - Codepage
2. **Text**:
   - Byte array — Byte array of the document.
   - File path — By clicking the button ![alt text](image-3.png), you can specify the file path in the Explorer window.

#### "Add table row" Component

This element adds a row to a table. Includes the following properties:

1. **Text**:
   - Data
   - DataRow — Data of the row.
   - Index — Table number.

#### "Export document" Component

This element exports a text document to another format. Includes the following properties:

1. **Word**:
   - File path — Path to the exported file (e.g., c:\folder\files.pdf).
   - Format — Format type. Currently, only the PDF format is supported.

#### "Get text" Component

This element reads data from a text document. Includes the following properties:

1. **Output**:
   - Variable — Variable for storing the reading results.

#### "Insert image" Component

This element inserts images into a text document. Includes the following properties:

1. **Text**:
   - Bookmark — Name of the bookmark that determines the start of the insertion. If not specified, the insertion is done at the end of the text.
   - Height — Mandatory. Height of the image. Default is 100.
   - Image — Mandatory. The image to insert into the document.
   - Width — Mandatory. Width of the image. Default is 100.

#### "Read table" Component

This element reads a table from a text document. Includes the following properties:

1. **Output**:
   - Data — Name of the variable to store a two-dimensional list of text data.
   - DataTable — Name of the variable to store table data.
2. **Text**:
   - Index — Mandatory. Table number.

#### "Replace text" Component

This element replaces all occurrences of the original text with a new one. Includes the following properties (mandatory):

1. **Text**:
   - Old text — The text to be replaced.
   - New text — The new text for the replacement.

#### "Save document" Component

This element saves the current state of the text file. Includes the following properties:

1. **Text**:
   - File path — By clicking the button ![alt text](image-3.png), you can specify the file path in the Explorer window.

#### "Text input" Component

This element writes data into a text document. Includes the following properties:

1. **Word**:
   - Bookmark — Name of the bookmark that determines the start of the writing. If not specified, the insertion position is determined by the Position property.
2. **Text**:
   - Position — Text input at the beginning/end. The default is End.
   - Text — Mandatory.

#### "Insert table" Component

This element inserts a table into a document. Includes the following properties:

1. **Text**:
   - Bookmark — Name of the bookmark that determines the start of the insertion. If not specified, the insertion is done at the end of the text.
   - Data — Table data.
   - DataTable — Name of the variable with table data.

#### "Write table cell" Component

This element writes text into a table cell. Includes the following properties:

1. **Text**:
   - Column — Column number.
   - Data — Cell data.
   - Index — Mandatory. Table number.
   - Row — Row number.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
