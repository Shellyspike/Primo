# Package Description for Primo.Passwords

The **Primo.Passwords** package provides tools for automating password management that can be used for various services and applications. The library helps in generating new passwords, which is especially relevant for automated systems where regular credential updates are required.

## General Information

In situations where passwords have a limited lifespan and require regular updates, **Primo.Passwords** automates this process by creating new passwords according to specified requirements. This is particularly useful in scenarios where bots use accounts to access applications, and regular password changes are necessary for security.

## Installation and Setup

To install the **Primo.Passwords** package, use the Visual Studio Dependency Manager or download it from [NuGet.org](https://www.nuget.org/).

### Installation via Dependency Manager:

1. **Open the Dependency Manager:**
   - In the main menu of Primo RPA Studio, select `Manage Dependencies`.
   - Or right-click in the project panel and choose `Dependencies` from the context menu.

2. In the opened window, navigate to the **NuGet.org** section and enter **Primo RPA** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.Passwords** and click **Install**.

4. Click **Save**.

5. In the modal window click **Install** and then **Close** to complete the installation. The package will be added to your project.

6. After installing the library, a new item, "Generate random password," will appear in the **Cryptography** group, under the **Passwords** subgroup, in the elements panel.

## Documentation

More detailed documentation is available on the [Primo RPA website](https://docs.primo-rpa.com).

## Library Contents

The library includes the "Generate random password" element. The use of this element simplifies workflows where the generation of new passwords is required after the expiration of old ones.

Password requirements must be specified in the element's properties:

1. **Output**:
   - Password – the generated password.
2. **General**:
   - Continue on exception: The script will continue running even if an error occurs during the execution of the element.
   - Disable logging: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to `File > Settings > General > Elements` and set the desired value in the `Disable logging for new elements` checkbox.
   - Name: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical elements are used.
   - Screenshot on error: A screenshot will be taken if an error occurs.
   - Screenshot on finish: Allows taking a screenshot upon the element's completion. All screenshots are saved in the `.Screenshots` folder, which is automatically created inside the process folder.
   - Wait after (ms): Pause after the element is executed.
   - Wait before (ms): Adds a pause before the element is executed.
3. **Password**:
   - Uppercase — minimum number of uppercase letters required.
   - Allowed special characters – special characters allowed in the password. These can include punctuation marks, mathematical symbols, various brackets, and symbols like `#`, `@`, etc. Example: `@#+`.
   - Max length — maximum password length.
   - Min length — minimum password length.
   - Required digits — minimum number of digits required in the password.
   - Lowercase — minimum number of lowercase letters required.
   - Special characters — minimum number of special characters required.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
