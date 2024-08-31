# Primo.Messaging Package Description

The **Primo.Messaging** package provides integration with the Telegram messenger and the AutoFAQ chatbot, offering a toolkit for working with these platforms within the Primo RPA solution.

## Overview

**Primo.Messaging** is a convenient and powerful tool for automating messaging tasks with Telegram and AutoFAQ. The library provides access to key features of both platforms, enabling you to send and receive messages, manage chats, and handle files. Integration with AutoFAQ helps automate customer support, while Telegram features simplify communication management.

## Getting Started

To install the **Primo.Messaging** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Dependency Management`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo RPA** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.Messaging** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For more detailed information on setting up and using **Primo.Messaging**, visit [the documentation on our website](https://docs.primo-rpa.ru).

## Library Features

The library includes the following features:

- **AutoFAQ Integration**:
  - AutoFAQ connection
  - Send text
  - Chats list

- **Telegram Integration**:
  - Send contact
  - Send text
  - Send file
  - Send photo
  - Get messages
  - Get file
  - Telegram connection
  - Chats list

To use an element, simply drag and drop it onto the project workspace in Primo RPA Studio.

### Element Properties

### General Properties

The following properties are common across multiple elements and are defined under the **General** section:

- **Continue on exception**: The script will continue running even if an error occurs during the execution of the element.
- **Disable logging**: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to `File > Settings > General > Elements` and set the desired value in the `Disable logging for new elements` checkbox.
- **Name**: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical components are used.
- **Screenshot on error**: A screenshot will be taken if an error occurs.
- **Screenshot on finish**: Allows taking a screenshot upon the element's completion. All screenshots are saved in the `.Screenshots` folder, which is automatically created inside the process folder.
- **Wait after (ms)**: Pause after the element is executed.
- **Wait before (ms)**: Adds a pause before the element is executed.

#### AutoFAQ Integration

The integration includes the following elements:

**<u>AutoFAQ connection</u>**

This element connects to AutoFAQ services. It includes the following properties:

1. **AutoFAQ** — required properties:
   - Login
   - Password
   - Service ID
   - Time-out
   - URL

2. **Output**:
   - AutoFAQ connection

**<u>Send text</u>**

This element sends a text message to an AutoFAQ chat. It includes the following properties:

1. **AutoFAQ**:
   - AutoFAQ connection
   - Text — required. The text of the message.
   - User ID — required.

**<u>Chats list</u>**

This element retrieves a list of AutoFAQ chats. It includes the following properties:

1. **AutoFAQ**:
   - AutoFAQ connection

3. **Filter**:
   - Date from
   - Date to
   - Operator ID
   - Page
   - Size
   - Statuses

2. **Output**:
   - Chats

#### Telegram Integration

The integration includes the following elements:

**<u>Telegram connection</u>**

This element connects to Telegram services. It includes the following properties:

1. **Telegram** — required properties:
   - Time-out
   - Token ID

2. **Output**:
   - Telegram connection

**<u>Chats list</u>**

This element retrieves a list of Telegram chats. It includes the following properties:

1. **Output**:
   - Chats — the list of recent chats.

2. **Telegram**:
   - Telegram connection

**<u>Send contact</u>**

This element sends a contact to a Telegram chat. It includes the following properties:

1. **Telegram**:
   - Chat ID — required.
   - Name — contact's name.
   - Phone — contact's phone number.
   - Reply to message — ID of the message to reply to.
   - Surname — contact's surname.
   - Telegram connection.

**<u>Send text</u>**

This element sends a text message to a Telegram chat. It includes the following properties:

1. **Telegram**:
   - Chat ID — required.
   - Reply to message — ID of the message to reply to.
   - Telegram connection.
   - Text — required. The text of the message.

**<u>Send file</u>**

This element sends a file to a Telegram chat. It includes the following properties:

1. **Telegram**:
   - Chat ID — required.
   - File — required. The file path. You can specify the file path using the Explorer window by clicking the ![alt text](image-3.png) button.
   - Reply to message — ID of the message to reply to.
   - Telegram connection.
   - Text — the text of the message.
   
**<u>Send photo</u>**

This element sends a photo to a Telegram chat. It includes the following properties:

1. **Telegram**:
   - Chat ID — required.
   - File — required. The file path. You can specify the file path using the Explorer window by clicking the ![alt text](image-3.png) button.
   - Reply to message — ID of the message to reply to.
   - Telegram connection.
   - Text — the text of the message.

**<u>Get messages</u>**

This element retrieves messages from a Telegram chat. It includes the following properties:

1. **Telegram**:
   - Begin date — retrieves messages starting from the specified time.
   - Buffer — required. The message buffer size.
   - Chat ID — required.
   - Telegram connection.

2. **Output**:
   - Messages — an array of retrieved messages.

**<u>Get file</u>**

This element retrieves a file from a Telegram chat. It includes the following properties:

1. **Telegram**:
   - File ID.
   - File path — required. The file save path. You can specify the file path using the Explorer window by clicking the ![alt text](image-3.png) button.
   - Telegram connection.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
