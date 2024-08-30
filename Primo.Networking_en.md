# Package Description: Primo.Networking

The **Primo.Networking** package provides a powerful set of tools for working with HTTP and SOAP requests. This package is especially useful for developers working with external service integration and process automation.

## General Information

**Primo.Networking** is a comprehensive set of elements designed for performing HTTP and SOAP requests. It allows for easy configuration of requests, management of authentication, and handling of responses.

## Getting Started

To install the **Primo.Networking** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - In the Primo RPA Studio main menu, select `Manage Dependencies`.

2. In the opened window, go to the **NuGet.org** section and enter **Primo RPA** in the search box.

3. Click on the funnel icon to display the list of available libraries. Find **Primo.Networking** and click **Install**.

4. Click **Save** to complete the installation.

## Documentation

For more detailed information on configuring and using **Primo.Networking**, visit [our documentation site](https://docs.primo-rpa.com).

## Library Components

The library includes the following features:

- HTTP request
- SOAP request

To use an element, drag it into the workspace of the Primo RPA Studio project.

### Element Properties

#### General Properties
The following properties are common across multiple elements and are defined under the **General** section:

- **Continue on exception**: The script will continue running even if an error occurs during the execution of the element.
- **Disable logging**: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to `File > Settings > General > Elements` and set the desired value in the `Disable logging for new elements` checkbox.
- **Name**: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical components are used.
- **Screenshot on error**: A screenshot will be taken if an error occurs.
- **Screenshot on finish**: Allows taking a screenshot upon the element's completion. All screenshots are saved in the `.Screenshots` folder, which is automatically created inside the process folder.
- **Wait after (ms)**: Pause after the element is executed.
- **Wait before (ms)**: Adds a pause before the element is executed.

#### HTTP Request

1. The element includes the following properties:

- **Basic Authentication**:
  - Login
  - Password
  - Secure password: A password encrypted using `SecureString`.

- **Client Certificate Authentication**:
  - Certificate password
  - Check SSL: Enable this option if SSL certificate verification is required.
  - Client SSL
  - Secure password: Encrypted certificate password. The password encrypted with `SecureString` is not stored in plain text. You can retrieve it, for example, from the "Credential Manager" application.

- **Input**:
  - Format: Select the response format required from the server. The default is `ANY` - any format.
  - Method: Select the request method. The default is `GET`.
  - URL: Required. The URL to which the request is made.

- **OAuth1**:
  - Consumer key
  - Consumer secret
  - OAuth1 secret
  - OAuth1 token

- **OAuth2**:
  - OAuth2 token

- **Output**:
  - Content: The content of the server's response.
  - Headers: The response headers.
  - Status: The status of the server's response.

- **Parameters**:
  - Attachments: An array of file paths to upload in the request.
  - Body: The request body. Note that quotation marks in the request body must be escaped using the `\` symbol. Example of escaping for JSON format: `"{\"title\":\"MyTitle\"}"`.
  - Cookies
  - Format: Specify the body format. The default is `XML`.
  - Headers: The request headers.
  - Parameters: The request parameters.
  - Resource path: The path for saving the file received from the request.
  - URL segments: A dictionary of segments added to the URL. Specified in the format `{key}`.

2. **Troubleshooting HTTP Request Configuration**:
   - The message "Operation timeout expired" might indicate an incorrectly set timeout.
   - The message "Unable to connect to the remote server" might be related to system OS limitations.

#### SOAP Request

1. When dragging the "SOAP Request" element into the project workspace, a "Wizard" button appears on the element panel. Clicking the button opens the "Wizard" panel where you can specify the following settings:
   - **Service Description** (WSDL schema URL).
   - **Get** (extracting information from the WSDL file).
   - **Contract and Method** (configuring SOAP methods).
   - **Authentication**:
     - None (authentication is not required by default),
     - Simple (SOAP service requires simple authentication by login and password),
     - Windows (Windows authentication),
     - Client Certificate (authentication by client certificate).
   - **Method Parameters**:
     - Name,
     - Type,
     - Value,
     - Execute (button to perform the request).

2. The element includes the following properties:

- **Authentication**:
  - Authentication: Select the authentication type from the dropdown list. Available options:
    1. None - No authentication required by default.
    2. Simple - Simple authentication using login and password.
    3. Windows - Windows credentials are used.
    4. Client Certificate - Client certificate authentication.

- **Certificate** - Parameters for the Client Certificate authentication type:
  - Certificate: Specify the path to the certificate file or the Subject in the Root store.
  - Certificate password: Specify the certificate password.
  - Secure certificate password: If using an encrypted certificate password, provide it in this field as a `SecureString` variable.

- **Output**:
  - Headers: The headers of the response received from the SOAP request.
  - Response: The service's response.

- **Simple** - Parameters for the Simple authentication type:
  - Login
  - Password
  - Secure password: If using an encrypted password, provide it in this field as a `SecureString` variable. Such a password is not stored in plain text in the computer's memory. It can be retrieved, for example, from the Credential Manager.

- **SOAP**:
  - Contract: Required. The service contract.
  - Endpoint: Required. Specify the location of the WSDL schema.
  - Method: Required. The method name.
  - Parameters: An array of method parameters. **Important!** Classes are not supported in data types, only simple types.
  - Timeout: Request timeout in milliseconds. Specify the maximum wait time for a server response in ms, after which, if no response is received, the request will be terminated with an error status. The default is 20000.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
