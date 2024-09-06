# Primo.CyberArk Package Description

The **Primo.CyberArk** package provides functional elements for secure and convenient access to accounts stored in CyberArk. This allows integrating automation processes with CyberArk, ensuring reliable management of credentials. Integration with CyberArk at the [Orchestrator](https://docs.primo-rpa.ru/primo-rpa/orchestrator/intro) level is recommended.

## General Information

**Primo.CyberArk** is an extension for Primo RPA that enables secure interaction with credentials stored in CyberArk. The package simplifies access to sensitive information, minimizing the risks associated with using credentials in automated processes.

## Installation and Setup

To install the **Primo.CyberArk** package, use the Visual Studio Dependency Manager or download it from [NuGet.org](https://www.nuget.org/).

### Installation via Dependency Manager:

1. **Open the Dependency Manager:**
   - In the main menu of Primo RPA Studio, select `Manage Dependencies`.
   - Or right-click in the project panel and choose `Dependencies` from the context menu.

2. In the opened window, navigate to the **NuGet.org** section and enter **Primo RPA** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.CyberArk** and click **Install**.

4. Click **Save**.

5. In the modal window click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

More detailed documentation is available on the [Primo RPA website](https://docs.primo-rpa.com).

## Library Components

The library includes the **Password request** element, which allows requesting credentials from CyberArk.

### Element Properties:

1. **CyberArk**:
   - **AppID** — The application identifier used to access the credentials.
   - **Encrypt** — A flag indicating whether the request should be encrypted.
   - **Folder** — The folder in CyberArk where the account is stored.
   - **Object** — The account object in CyberArk.
   - **Port** — The port for connecting to the CyberArk server.
   - **Reason** — The reason for requesting the credentials.
   - **Request type**:
      - **Rest** — Use REST API to request data.
      - **Sdk** — Use SDK to interact with CyberArk.
   - **Safe** — The secure vault where the account is stored.
   - **Time-out** — The maximum time to wait for a server response.
   - **URL** — The CyberArk server address.
   - **User Name** — The username of the account.

2. **General**:
   - **Continue on exception**: The script will continue running even if an error occurs during the execution of the element.
   - **Disable logging**: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to `File > Settings > General > Elements` and set the desired value in the `Disable logging for new elements` checkbox.
   - **Name**: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical components are used.
   - **Screenshot on error**: A screenshot will be taken if an error occurs.
   - **Screenshot on finish**: Allows taking a screenshot upon the element's completion. All screenshots are saved in the `.Screenshots` folder, which is automatically created inside the process folder.
   - **Wait after (ms)**: Pause after the element is executed.
   - **Wait before (ms)**: Adds a pause before the element is executed.

3. **Output**:
   - **Result** — The result of the request (credentials).

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).


