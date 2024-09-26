# Primo.SharePoint Package Description

The **Primo.SharePoint** package provides a set of elements for integration with Microsoft SharePoint.

## General Information

**Primo.SharePoint** is a library designed to work with SharePoint objects, such as files and directories, through Primo RPA Studio elements. The package allows managing access rights, uploading and downloading files, as well as retrieving lists of directories and files.

## Getting Started Instructions

To install the **Primo.SharePoint** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Manage dependecies`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo.SharePoint** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.SharePoint** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For detailed information on setting up and using **Primo.SharePoint**, please visit [our documentation](https://docs.primo-rpa.com/).

## Library Components

The library provides the following features:

- **Create directory**
- **Grant access to directory** 
- **Upload file**
- **Grant access to file**
- **Download file**
- **Delete file**
- **Get directories**
- **Get files**

To use an element, drag it into the workspace of Primo RPA Studio.

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

### Create Directory Element

Creates a directory on the SharePoint server. It includes the following properties:

1. **SharePoint**:
   - URL: The SharePoint server URL. This is required.
   - Domain: The domain name.
   - Login: The user login.
   - Disable inheritance: Disables role inheritance.
   - Password: The user password.
   - Users: The array of users.
   - Role: The access role.
2. **Action**:
   - Relative URL: The relative URL of the directory. This is required.

### Grant Access to Directory Element

Grants access to a directory on the SharePoint server. It includes the following properties:

1. **SharePoint**:
   - URL: The SharePoint server URL. This is required.
   - Domain: The domain name.
   - Login: The user login.
   - Password: The user password.
   - Users: The array of users.
   - Role: The access role.
2. **Action**:
   - Relative URL: The relative URL of the directory. This is required.

### Upload File Element

Uploads a file to the SharePoint server. It includes the following properties:

1. **SharePoint**:
   - URL: The SharePoint server URL. This is required.
   - Domain: The domain name.
   - Login: The user login.
   - Disable inheritance: Disables role inheritance.
   - Password: The user password.
   - Users: The array of users.
   - Role: The access role.
2. **Action**:
   - Relative URL: The relative URL of the file. This is required.
   - Overwrite: File overwrite flag.
   - File path: Use the ![alt text](image-3.png) button to specify the file path in the Explorer window. This is required.
3. **Output**:
   - URL: The file URL.

### Grant Access to File Element

Grants access to a file on the SharePoint server. It includes the following properties:

1. **SharePoint**:
   - URL: The SharePoint server URL. This is required.
   - Domain: The domain name.
   - Login: The user login.
   - Password: The user password.
   - Users: The array of users.
   - Role: The access role.
2. **Action**:
   - Relative URL: The relative URL of the file. This is required.

### Download File Element

Downloads a file from the SharePoint server. It includes the following properties:

1. **SharePoint**:
   - URL: The SharePoint server URL. This is required.
   - Domain: The domain name.
   - Login: The user login.
   - Password: The user password.
2. **Action**:
   - Relative URL: The relative URL of the file. This is required.
   - Overwrite: File overwrite flag.
   - File path: Use the ![alt text](image-3.png) button to specify the file path in the Explorer window. This is required.

### Delete File Element

Deletes a file from the SharePoint server. It includes the following properties:

1. **SharePoint**:
   - URL: The SharePoint server URL. This is required.
   - Domain: The domain name.
   - Login: The user login.
   - Password: The user password.
2. **Action**:
   - Relative URL: The relative URL of the file. This is required.

### Get Directories Element

Retrieves a list of directories from the SharePoint server. It includes the following properties:

1. **SharePoint**:
   - URL: The SharePoint server URL. This is required.
   - Domain: The domain name.
   - Login: The user login.
   - Password: The user password.
2. **Action**:
   - Relative URL: The relative URL of the directory. This is required.
3. **Output**:
   - List: The list of directories.

### Get Files Element

Retrieves a list of files from the SharePoint server. It includes the following properties:

1. **SharePoint**:
   - URL: The SharePoint server URL. This is required.
   - Domain: The domain name.
   - Login: The user login.
   - Password: The user password.
2. **Action**:
   - Relative URL: The relative URL of the file. This is required.
3. **Output**:
   - List: The list of files.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.com](mailto:support@primo-rpa.com).

