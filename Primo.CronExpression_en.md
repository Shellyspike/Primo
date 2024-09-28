# Primo.CronExpression

**Primo.CronExpression** is a powerful library designed for working with CRON records and expressions, providing simplicity and flexibility in scheduling and managing CRON-based tasks.

## General Information

**Primo.CronExpression** offers a convenient API for parsing, analyzing, and calculating task execution times based on CRON expressions. The library supports standard and extended CRON formats, providing developers with powerful tools for scheduling and automating tasks in projects on the Primo RPA platform.

### Key Features:

- **CRON Expression Parsing:** Easy and accurate parsing of CRON expressions with support for various formats.
- **Run Time Calculation:** Retrieve the next run time, intervals, and a series of runs.
- **Flexible Configuration:** Specify time intervals, start dates, and end dates.

## Getting Started Instructions

To install the **Primo.CronExpression** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Manage dependecies`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo.CronExpression** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.CronExpression** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For more detailed information on configuring and using **Primo.CronExpression**, visit the [documentation on our website](https://docs.primo-rpa.com).

## Library Functionality

The library includes the following key elements:

- **Get all runs interval**: Calculates and returns all run intervals based on the specified CRON expression.
- **Get next run times**: Determines and returns a list of the next task runs.
- **Get next run time**: Determines the time of the next task run.

To use an element, simply drag it into the workspace of your Primo RPA Studio project.

### Element Properties

### General Properties

The following properties are common across multiple elements and are defined under the **General** section:

- **Continue on exception**: The script will continue running even if an error occurs during the execution of the element.
- **Disable logging**: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to `File > Settings > General > Elements` and set the desired value in the `Disable logging for new elements` checkbox.
- **Name**: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical elements are used.
- **Screenshot on error**: A screenshot will be taken if an error occurs.
- **Screenshot on finish**: Allows taking a screenshot upon the element's completion. All screenshots are saved in the `.Screenshots` folder, which is automatically created inside the process folder.
- **Wait after (ms)**: Pause after the element is executed.
- **Wait before (ms)**: Adds a pause before the element is executed.

#### Get all runs interval

This element includes the following properties:

1. **Output**:
   - **Result** — A list of time intervals calculated based on the specified CRON expression.
2. **Parameters**:
   - **Cron expression** — The CRON expression used for calculating intervals. Required.
   - **Start date** — The start date from which intervals are calculated. Required.
   - **End date** — The end date up to which intervals are calculated. Required.

#### Get next run times

This element includes the following properties:

1. **Output**:
   - **Next runs** — A list of the next run dates and times calculated based on the CRON expression.
2. **Parameters**:
   - **After time** — The date from which the next runs will be calculated.
   - **Limit** — The number of next runs to calculate.
   - **Cron expression** — The CRON expression used for calculating the next runs. Required.
   
#### Get next run time

This element includes the following properties:

1. **Output**:
   - **Next run** — The date and time of the next run calculated based on the CRON expression.
2. **Parameters**:
   - **After time** — The date from which the next run will be calculated.
   - **Cron expression** — The CRON expression used for calculating the next run. Required.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).

