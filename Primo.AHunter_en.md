# Package Description of Primo.AHunter

The **Primo.AHunter** package is a set of tools for integration with the Ahunter service, designed for the verification, correction, and standardization of mailing addresses, phone numbers, and full names in Russia.

## General Information

**Primo.AHunter** allows for easy integration of address, phone, and full name standardization functions in Primo RPA projects.

## Getting Started Instructions

To install the **Primo.AHunter** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select Manage dependencies.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo.AHunter** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.AHunter** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For more detailed information on configuring and using **Primo.AHunter**, visit the [documentation on our website](https://docs.primo-rpa.com).

## Library Composition

The library includes the following features:

- **Cleanse address**
- **Cleanse phone**
- **Cleanse full name**

To use the element, it must be dragged into the workspace of the Primo RPA Studio project.

## Element Properties

### General Properties

The following properties are common across multiple elements and are defined under the **General** section:

- **Continue on exception**: The script will continue running even if an error occurs during the execution of the element.
- **Disable logging**: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to File > Settings > General > Elements and set the desired value in the Disable logging for new elements checkbox.
- **Name**: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical components are used.
- **Screenshot on error**: A screenshot will be taken if an error occurs.
- **Screenshot on finish**: Allows taking a screenshot upon the element's completion. All screenshots are saved in the .Screenshots folder, which is automatically created inside the process folder.
- **Wait after (ms)**: Pause after the element is executed.
- **Wait before (ms)**: Adds a pause before the element is executed.

### Cleanse address

Performs address standardization. The element includes the following properties:

1. **Output**:
   - Json – the cleansed address in Json format.
   - Result – the cleansed address.
2. **Request**:
   - Address – the address to be cleansed. Mandatory field.
   - Limit – the limit of addresses.
   - Time-out – the server timeout.
   - Token – the API token. Mandatory field.
   - Filter – the address filter.

### Cleanse phone

Performs phone number standardization. The element includes the following properties:

1. **Output**:
   - Json – the cleansed phone number in Json format.
   - Result – the cleansed phone number.
2. **Request**:
   - Phone – the phone number to be cleansed. Mandatory field.
   - Limit – the limit of phone numbers.
   - Time-out – the server timeout.
   - Token – the API token. Mandatory field.

### Cleanse full name

Performs full name standardization. The element includes the following properties:

1. **Output**:
   - Json – the cleansed full name in Json format.
   - Result – the cleansed full name.
2. **Request**:
   - Limit – the limit of full names.
   - Time-out – the server timeout.
   - Token – the API token. Mandatory field.
   - Full name – the full name to be cleansed. Mandatory field.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-ru).
