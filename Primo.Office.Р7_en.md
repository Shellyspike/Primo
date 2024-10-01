# Primo.Office.MyOffice Package Description

The **Primo.Office.MyOffice** package provides tools for automating work with documents from the R7 office suite. It allows actions with text and spreadsheet documents, including data entry, formatting, and document structure management.

## General Information

**Primo.Office.MyOffice** is a library designed for interacting with documents in R7 applications. The package supports automation of work with text and spreadsheet files, offering a convenient interface for performing various operations such as data entry, document structure modification, macro execution, and much more.

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

6. After installing the library, the **P7-Tables** and **P7-Documents** groups will appear in the elements panel.


## Documentation

More detailed documentation is available on the [Primo RPA website](https://docs.primo-rpa.com).

## Library Composition

The library includes the following features:

- **P7-Tables**:
   - Sheets
      - Add sheet
      - Rename sheet
      - Get sheets
      - Delete sheet
   - Append range
   - Run macro
   - Run script
   - Change background
   - Change cells
   - Save workbook
   - P7 workbook 
   - Delete range
   - Read range

- **Р7-Documents**:
  - Text input
  - P7 document
  - Replace text
  - Run macro
  - Run script
  - Save workbook
  - Delete text
  - Get text

To use an element, drag it into the working area of the Primo RPA Studio project.

## Element Properties

### General Properties

The following properties are common across multiple elements and are defined under the **General** section:

- **Continue on exception**: The script will continue running even if an error occurs during the execution of the element.
- **Disable logging**: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to `File > Settings > General > Elements` and set the desired value in the `Disable logging for new elements` checkbox.
- **Name**: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical elements are used.
- **Screenshot on error**: A screenshot will be taken if an error occurs.
- **Screenshot on finish**: Allows taking a screenshot upon the element's completion. All screenshots are saved in the `.Screenshots` folder, which is automatically created inside the process folder.
- **Wait after (ms)**: Pause after the element is executed.
- **Wait before (ms)**: Adds a pause before the element is executed.

### P7-Tables Section

All elements listed below are added to the workspace within the **P7 workbook** element. This element is used to connect to the R7 application. If the specified file is missing, a new one will be created. The **P7 workbook** element includes the following properties:

1. **Table**
   - File name – the file name of the R7 document.
   - Time-out – the request time-out in seconds.

---

#### Pages Subsection

##### Add sheet

An element for adding a new sheet to the Table. It includes the following properties:

1. **Table**:
   - Name — the name of the new sheet. Required.
   - Index — the index of the sheet.

##### Rename sheet

An element for renaming a sheet in the Table. It includes the following properties:

1. **Table** (required):
   - Name — the name of the sheet.
   - Index — the index of the sheet.

##### Get sheets

An element for retrieving the list of sheets in the Table. It includes the following properties:

1. **Output**:
   - Variable — the variable for storing the list of sheets.

##### Delete sheet

An element for deleting a sheet from the Table. It includes the following properties:

1. **Table** (required):
   - Index — the index of the sheet.

---

#### Append range Element

An element that writes a cell range of data to the table. It includes the following properties:

1. **Table**:
   - Range — the range of cells to write (A1:D12).
   - Add headers — add column headers to the table.
   - Sheet index
   - Direction — the direction to shift cells:
     - Down
     - Right
   - Overwrite — flag for overwriting data.
   - Variable (table) — variable for storing text data values.
   - Variable (text) — variable for storing text data values for writing.
   - Expand range — automatically expand the range to fit the data size.
   - Sheet name — the name of the sheet.

#### Run macro Element

An element for executing a table macro. It includes the following properties:

1. **Output**:
   - Result — the result of execution.
2. **Table**:
   - Arguments — the macro arguments.
   - Macro — the name of the macro. Required.

#### Run script Element

An element for executing a table script. It includes the following properties:

1. **Output**:
   - Result — the result of execution.
2. **Table**:
   - Arguments — the script arguments.
   - Script — the script text. Required.

#### Change background Element

Changes the background color of a table range. It includes the following properties:

1. **Table**:
   - Range — the range of cells (A1:D12). Required.
   - Sheet index
   - Sheet name
   - Background color — the background color of the range, e.g., `System.Drawing.Color.Black`.

#### Change cells Element

Changes the format of table cells. It includes the following properties:

1. **Table**:
   - Range — the range of cells (A1:D12). Required.
   - Sheet index
   - Sheet name
   - Border type — the border type of the cells.
   - Border thickness — the border thickness of the cells.
   - Border color — the border color of the cell range.
   - Cells color — the cell color of the range.

#### Read range Element

An element that reads data from a cell range in the table. It includes the following properties:

1. **Output**:
   - Variable (table) — variable for storing text data reading results.
   - Variable (text) — variable for storing text data reading results.
   - Headers row — flag indicating that the first row contains headers (for the table). If checked, the headers will be considered.
2. **Table**:
   - Range — the range of cells to read ("A1:D12"). If not specified, the selected range will be read. If "*" is specified, the entire sheet will be read.
   - Sheet index
   - Sheet name

#### Delete range Element

An element that deletes a range of cells in the table. It includes the following properties:

1. **Table**:
   - Range — the range of cells to read ("A1:D12"). If not specified, the selected range will be read. If "*" is specified, the entire sheet will be read. Required.
   - Sheet index
   - Shift — the direction of the cell shift.
   - Sheet name

#### Save workbook Element

An element that saves the table file.

### P7-Documents Section

All elements listed below are added to the workspace within the **P7 document** element. This container connects to the R7 application. If the specified file is missing, a new one will be created. The **P7 document** element includes the following properties:

1. **Table**:
   - Time-out — the request time-out in seconds. Required.
2. **Text**:
   - File name — the file name of the document. Required.

#### Text input Element

An element that writes data to a text document. It includes the following properties:

1. **Text**:
   - Bookmark — the name of the bookmark defining the start of the writing. If not specified, the writing will occur at the end of the text.
   - Start — the index of the insertion point.
   - Text — the data to be entered in the document. Required.

#### Replace text Element

An element that replaces all occurrences of the original text with new text. It includes the following properties:

1. **Text**:
   - Old text — the text to be replaced.
   - New text — the new text for replacement. Required.

#### Run macro Element

An element for executing a document macro. It includes the following properties:

1. **Output**:
   - Result — the result of execution.
2. **Table**:
   - Arguments — the macro arguments.
   - Name — the name of the macro. Required.

#### Run script Element

An element for executing a document script. It includes the following properties:

1. **Output**:
   - Result — the result of execution.
2. **Table**:
   - Arguments — the script arguments.
   - Text — the script text. Required.

#### Get text Element

An element that reads data from the document. It includes the following properties:

1. **Text**:
   - Length — the length of the selection.
   - Start — the start of the selection.
   - Variable — the variable for storing the reading results. Required.

#### Delete text Element

Removes text of the specified length. If neither Start nor Length is specified, all text will be removed. It includes the following properties:

1. **Text**:
   - Length — the length of the selection.
   - Start — the start of the selection.

#### Save workbook Element

An element that saves the file.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
