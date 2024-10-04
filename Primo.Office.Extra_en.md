# Package description Primo.Office.Extra

The **Primo.Office.Extra** package provides tools for working with Excel and Word files, including automatic column adjustment, file information extraction, and table handling.

## General Information

**Primo.Office.Extra** extends the capabilities of working with Excel and Word documents, allowing the automation of data reading, formatting, and table content analysis.

## Getting Started Instructions

To install the **Primo.Office.Extra** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Manage dependencies`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo.Office.Extra** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.Office.Extra** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

6. After installing the library, the **Office Extras** group will appear in the elements panel.

## Documentation

For more detailed information on configuring and using **Primo.Office.Extra**, visit the [documentation on our website](https://docs.primo-rpa.com).

## Library Contents

The library includes the following features:

- Excel autofit range
- Excel file info
- Read range visible
- Word table counts

To use the element, drag it into the working field of a Primo RPA Studio project.

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

### Element "Excel autofit range"

Automatically adjusts the optimal widths of columns for the specified range of cells in an Excel document. It is added inside the ["Excel workbook"](https://docs.primo-rpa.com/g_elements/el_basic/els_excel/el_excel_app) container.

Includes the following properties:

1. **Data**:
   - Range — the range of cells whose widths will be automatically adjusted.
   - Sheet-source index — the sheet index. It takes precedence over the sheet name.
   - Sheet name — the name of the sheet. It is ignored if the sheet index is specified.

### Element "Excel file info"

Extracts metadata from an Excel document, such as the file name, creation date, and other properties. It is added inside the ["Excel workbook"](https://docs.primo-rpa.com/g_elements/el_basic/els_excel/el_excel_app) container.

Includes the following properties:

1. **Output**:
   - Result — the name of the variable where the file information will be saved.

### Element "Read range visible"

Added inside the ["Excel workbook"](https://docs.primo-rpa.com/g_elements/el_basic/els_excel/el_excel_app) container. It reads data from the visible range of Excel cells.

Includes the following properties:

1. **Output**:
   - Variable (info) — a variable to store the results of reading the cell information.
   - Variable (table) — a variable to store the results of reading text values.
   - Variable (text) — a variable to store the results of reading text values.
   - Headers row — indicates that the first row contains headers (for the table).
   - Use Excel cell field types — indicates that Excel cell field types will be taken into account.
2. **Data**:
   - Range — the range of cells to read (e.g., A1:D12). If not specified, the selected range will be read. If the `*` symbol is specified, the entire sheet will be read.
   - Sheet index — the sheet index. It takes precedence over the sheet name.
   - Sheet name — the name of the sheet. It is ignored if the sheet index is specified.
   - Date format.

### Element "Word table counts"

Counts the number of tables in a Word document. It is added inside the ["Word document"](https://docs.primo-rpa.com/g_elements/el_basic/els_word/el_word_app) container.

Includes the following properties:

1. **Output**:
   - Result — the name of the variable where the result of the table count will be saved.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.com](mailto:support@primo-rpa.com).
