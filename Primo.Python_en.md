# Primo.Python Package Description

The **Primo.Python** package provides tools for interacting with Python scripts, including their execution and data retrieval. It supports Python version 3.9.

## General Information

**Primo.Python** is a library for integrating Python scripts into Primo RPA-based projects. Python 3.9 and Pywin32 must be installed on the robot's machine for the package to function properly.

## Getting Started Instructions

To install the **Primo.Python** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Manage dependecies`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo.Python** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.Python** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For detailed information on setting up and using **Primo.Python**, please visit [our documentation](https://docs.primo-rpa.com).

## Library Elements

The library provides the following features:

- Python
- Execute script
- Add function
- Get object

To use an element, drag it into the workspace of Primo RPA Studio.

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

### Python Element

The **Python** element is used to establish a connection with Python and includes the following properties:

1. **Connection**:
   - Console – Check the box to display the console window.
   - Python path – Required. Specify the path to the `python.exe` file.
   - Buffer size – Buffer size for data exchange. Default value: 65535.
   - Time-out – Time-out for the connection with Python in milliseconds.

### Execute Script Element

This element runs the specified Python Script. Properties:

1. **Script**:
   - Args
   - Script – Required. The text of the script.

### Add Function Element

Adds a Python function to the project. Properties:

1. **Script** (Required):
   - Text – Required. The text of the script.
   - File – Path to the script file.

### Get Object Element

This element allows retrieving a Python object. Properties:

1. **Output**:
   - Variable – The variable for saving the result.
2. **Object**:
   - Name
   - Type – The data type of the object.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.com](mailto:support@primo-rpa.com).
