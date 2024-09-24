# Primo.Office.Pdf Package Description

The **Primo.Office.Pdf** package provides a set of elements for working with PDFs, including retrieving data from XFA forms and extracting tables contained in a PDF document.

## General Information

**Primo.Office.Pdf** is a powerful tool for working with PDF documents within the Primo RPA Studio automation environment. The library offers convenient elements for extracting data from complex PDF formats, such as XFA forms, as well as for quickly and accurately extracting tabular data.

## Getting Started Instructions

To install the **Primo.Office.Pdf** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Manage dependecies`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo.Office.Pdf** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.Office.Pdf** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For more detailed information on configuring and using **Primo.Office.Pdf**, visit the [documentation on our website](https://docs.primo-rpa.com).

## Library Composition

The library includes the following features:

- **Get XFA form** — extracts data from XFA forms in a PDF document. XFA forms are interactive web forms that can be saved in PDF format.
- **Get table** — extracts tabular data from PDF documents. Using this element significantly speeds up and simplifies data processing, minimizing the need for manual input. It ensures high accuracy when extracting data, helping to avoid errors associated with manual copying of information.

To use the element, drag it into the working field of a Primo RPA Studio project.

## Usage Examples

### Getting XFA Form

Example of using the element in a "Pure code" process:

- C#: `Primo.Office.Pdf.GetXfaForm.GetTable(wf, "File path", "Password");`
- Python: `Primo.Office.Pdf.GetXfaForm.GetTable(wf, "File path", "Password");`
- JavaScript: `_lib.Primo.Office.Pdf.GetXfaForm.GetTable(wf, "File path", "Password");`

### Reading Table

Example of using the element in a "Pure code" process:

- C#: `Primo.Office.Pdf.PdfApp.GetTable(wf, "File path", "Index", "Page", "Headers", "Password");`
- Python: `Primo.Office.Pdf.PdfApp.GetTable(wf, "File path", "Index", "Page", "Headers", "Password");`
- JavaScript: `_lib.Primo.Office.Pdf.PdfApp.GetTable(wf, "File path", "Index", "Page", "Headers", "Password");`

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

### Get XFA form

XFA forms are interactive web forms that can be saved in PDF format. Distinctive characteristics of XFA forms:

- XFA is XML-based and uses a separate XML structure to define form elements and their behavior.
- XFA separates data from the template, allowing data to be packaged separately from the form.
- XFA can create dynamically growing forms.

The element includes the following properties:

1. **PDF**:
   - Core — a component for processing the PDF file. Available options:
      - Spire — the default component, does not require Adobe Acrobat installation. Supports processing PDF documents without page limits and allows extracting forms, images, text, pages, and attachments with high speed and accuracy.
      - Aspose — a component for processing and analyzing PDF documents without installing Adobe Acrobat. Supports working with pages, forms, text, images, and other objects. Limitation: the document must not exceed 3 pages.
   - File path — the path to the PDF file. Example: `"C:\\Users\\user\\Documents\\test.pdf"`. By clicking the button ![alt text](image-4.png), you can specify the file path in the Explorer.
   - Password — the password to access the protected PDF document.
   - Secure password — a secure way to provide a password for accessing the PDF document.
2. **Output**:
   - Form — a variable to store data from the XFA form.

Example of using the element in a Pure Code process:

- C# : `Primo.Office.Pdf.GetXfaForm.GetTable(wf, "File path", "Password");`
- Python: `Primo.Office.Pdf.GetXfaForm.GetTable(wf, "File path", "Password")`
- JavaScript: `_lib.Primo.Office.Pdf.GetXfaForm.GetTable(wf, "File path", "Password");`

### Get table

The element is designed to automatically extract tabular data from PDF documents. It provides a fast and accurate way to read tables from PDF pages, which is especially useful when processing large volumes of documents or when integrating data from PDFs into other systems and applications.

The element includes the following properties:

1. **PDF**:
   - Core — a component for processing the PDF file. Available options:
      - Spire — the default component, does not require Adobe Acrobat installation. Supports processing PDF documents without page limits and allows extracting forms, images, text, pages, and attachments with high speed and accuracy.
      - Aspose — a component for processing and analyzing PDF documents without installing Adobe Acrobat. Supports working with pages, forms, text, images, and other objects. Limitation: the document must not exceed 3 pages.
   - File path — the path to the PDF file. Example: `"C:\\Users\\user\\Documents\\test.pdf"`. By clicking the button ![alt text](image-4.png), you can specify the file path in the Explorer.
   - Headers — indicates the presence of headers in the table.
   - Index — the index of the table on the page if the page contains multiple tables. Indexing starts at zero.
   - Page — the page number of the PDF document where the table is located. Indexing starts at zero.
   - Password — the password to access the protected PDF document.
   - Secure password — a secure way to provide a password for accessing the PDF document.
2. **Output**:
   - Variable — a variable to store data extracted from the table in the PDF document.

### Possible Errors

When working with the **Get table** element, the following errors may occur:

- **File read error**: If the file path is incorrect or the file is not accessible, a file read error may occur. Ensure that the file path is correct and the file is accessible for reading.
- **Password issues**: If the PDF file is password-protected, an incorrect password may cause an access error. Ensure that the password is correct and is being passed to the component correctly.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.com](mailto:support@primo-rpa.com).
