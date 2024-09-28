# Package Description: Primo.Java

The **Primo.Java** package provides tools for executing code written in the Java programming language.

## General Information

**Primo.Java** is a library for integrating Java code into projects created in Primo RPA Studio. It allows you to load classes, invoke methods, and interact with Java objects.

## Getting Started

To install the **Primo.Java** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Manage dependencies`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo RPA** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.Java** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For more detailed information on setting up and using **Primo.Java**, visit [the documentation on our website](https://docs.primo-rpa.com).

## Library Features

The library includes the following features:

- Java
- Invoke method
- Load Jar
- Get field
- Convert Java object
- Create Java object

To use an element, simply drag and drop it onto the project workspace in Primo RPA Studio.

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

### Element "Java"

All of the following elements are added inside the **Java** element, which serves as the connection to Java. The **Java** element includes the following properties:

1. **Connection**:
   - java.exe path — Specify the path to `java.exe` by clicking the ![alt text](image-3.png) button, which opens a File Explorer window.
   - Time-out — Connection time-out.

### Element "Invoke Method"

This element invokes a specified method in a Java instance. It includes the following properties:

1. **Output**:
   - Result — The resulting Java object.
2. **Method**:
   - Method name — Required. The name of the method to be invoked.
   - Java object — The object in which the method needs to be invoked.
   - Parameters — The parameters of the method to be invoked (none of them should be null).
   - Type — The name of the class containing the method.

### Element "Load Jar"

This element loads a Jar file into the Java context. It includes the following properties:

1. **Jar**:
   - Path — Path to the Jar file. Use the ![alt text](image-3.png) button to specify the path through the File Explorer.

### Element "Get Field"

This element retrieves a field from a Java object. It includes the following properties:

1. **Output**:
   - Result — A reference to the retrieved result.
2. **Field**:
   - Name — Required. The name of the field.
   - Object — The Java object containing the field.
   - Type — The type that contains the field.

### Element "Convert Java Object"

This element converts a Java object to the required type. It includes the following properties:

1. **Output**:
   - Result — The resulting object.
2. **Conversion**:
   - Object — Required. The Java object to be converted.
   - Type — The data type to which the object should be converted.

### Element "Create Java Object"

This element creates a new Java object with a specified type. It includes the following properties:

1. **Output**:
   - Result — A reference to the created object.
2. **Object**:
   - Parameters — The constructor parameters (none of them should be null).
   - Type — Required. The type of the object being created.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.com](mailto:support@primo-rpa.com).

