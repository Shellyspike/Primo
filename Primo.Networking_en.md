# Package Description: Primo.Networking

The **Primo.Networking** package provides a powerful set of tools for working with HTTP and SOAP requests on the Linux platform. This package is especially useful for developers working with external service integration and process automation.

## General Information

**Primo.Networking** is a comprehensive set of elements designed for performing HTTP and SOAP requests in a Linux environment. It allows for easy configuration of requests, management of authentication, and handling of responses.

## Getting Started

To install the **Primo.Networking** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - In the Primo RPA Studio main menu, select `Manage Dependencies`.

2. In the opened window, go to the **NuGet.org** section and enter **Primo RPA** in the search box.

3. Click on the funnel icon to display the list of available libraries. Find **Primo.Networking** and click **Install**.

4. In the modal window that appears, agree to install **Primo.Networking.Linux**.

5. Click **Save** to complete the installation.

## Documentation

For more detailed information on configuring and using **Primo.Networking**, visit [our documentation site](https://docs.primo-rpa.com).

## Usage Examples

The library includes the following capabilities:

- HTTP request
- SOAP request

To use an element, drag it into the workspace of the Primo RPA Studio project.

### HTTP Request Examples

1. Configure the HTTP request by specifying:
   - **Basic Authentication**:
     - Login
     - Password
     - Secure password
   - **Client Certificate Authentication**:
     - Certificate password
     - Check SSL
     - Client SSL
     - Secure password
   - **General**:
     - Continue on exception
     - Disable logging
     - Name
     - Screenshot on error
     - Screenshot on finish
     - Timeout
     - Wait after (ms)
     - Wait before (ms)
   - **Input**:
     - Format
     - Method
     - URL
   - **OAuth1**:
     - Consumer key
     - Consumer secret
     - OAuth1 secret
     - OAuth1 token
   - **OAuth2**:
     - OAuth2 token
   - **Output**:
     - Content
     - Headers
     - Status
   - **Parameters**:
     - Attachments
     - Body
     - Cookies
     - Format
     - Headers
     - Parameters
     - Resource path
     - URL segments

2. **Troubleshooting HTTP Request Configuration:**
   - The message "Operation timeout expired" might indicate an incorrectly set timeout.
   - The message "Unable to connect to the remote server" might be related to system OS limitations.

### SOAP Request Examples

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

2. **SOAP Request Properties:**
   - **Authentication**:
     - Authentication
   - **Certificate**:
     - Certificate
     - Certificate password
     - Secure certificate password
   - **General**:
     - Continue on exception
     - Disable logging
     - Name
     - Screenshot on error
     - Screenshot on finish
     - Timeout
     - Wait after (ms)
     - Wait before (ms)
   - **Output**:
     - Headers
     - Response
   - **Simple**:
     - Login
     - Password
     - Secure password
   - **SOAP**:
     - Contract
     - Endpoint
     - Method
     - Parameters
     - Timeout

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
