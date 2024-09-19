# Primo.ColorDetector Package Description

The **Primo.ColorDetector** package provides a set of tools for determining the color of a point on the screen.

## General Information

**Primo.ColorDetector** is a process automation library that provides tools for detecting the color of a pixel from the screen or from images. It integrates with Primo RPA Studio, enabling automated color analysis in various scenarios, making it easier to develop and optimize robotic processes involving visual perception.

## Getting Started Instructions

To install the **Primo.ColorDetector** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Dependency Management`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo.ColorDetector** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.ColorDetector** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For more detailed information on configuring and using **Primo.ColorDetector**, visit the [documentation on our website](https://docs.primo-rpa.com).

## Library Composition

The library includes the following features:

- Color from image
- Color from screen

To use the element, drag it into the working field of a Primo RPA Studio project.

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

### Color from image

The element searches for a color in the specified image. It includes the following properties:

1. **Output**:
  - Result — analysis result.
2. **Parameters** (required):
  - Image — the image to be processed.
  - Color scheme — the color scheme to be searched for.

### Color from screen

The element searches for a color on the screen. It includes the following properties:

1. **Output**:
  - Result — analysis result.
2. **Parameters** (required):
  - X — X coordinate.
  - Y — Y coordinate.
  - Color scheme — the color scheme to be searched for.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.com](mailto:support@primo-rpa.com).


