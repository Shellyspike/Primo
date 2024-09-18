# Primo.Office.PowerPoint

**Primo.Office.PowerPoint** is a library that allows automating tasks related to the creation and editing of presentations in MS PowerPoint format.

## General Information

**Primo.Office.PowerPoint** provides a user-friendly interface for automating processes related to presentations. The library supports the creation, editing, and management of slides, as well as interaction with various multimedia elements and objects.

## Getting Started Instructions

To install the **Primo.Office.PowerPoint** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Dependency Management`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo.Office.PowerPoint** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.Office.PowerPoint** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For more detailed information on configuring and using **Primo.Office.PowerPoint**, visit the [documentation on our website](https://docs.primo-rpa.com).

## Library Composition

The library includes the following features:

- PowerPoint presentation
- Add media-file
- Paste item
- Add data table
- Add text
- Add file
- Add new slide
- Replace text
- Run macro
- Copy-paste slide
- Edit shape
- Delete slide
- Save presentation

## Usage Examples of Primo.Office.PowerPoint

### Inserting a Media File

```csharp
app.AddMedia(1, "Shape1", "C:\\file.avi", 10, 20, 100, 50);
```

### Inserting an Object

```csharp
app.PasteItem(1, "Shape1", 10, 20, 100, 50);
```

### Inserting a Table

```csharp
app.AddDataTable(1, "Shape1", tbl, true, Primo.Office.PowerPoint.Model.AddTableTypes.CreateNewTable, 2, 3);
```

### Inserting Text

```csharp
app.AddText(1, "Shape1", "text", false);
```

### Inserting a File

```csharp
app.AddFile(1, "Shape1", "C:\\file.txt", "File title");
```

### Adding a Slide

```csharp
int newidx = app.AddNewSlide(1, "LayoutText", "Default");
```

### Replacing Text

```csharp
int cnt = app.AddFile("old text", "new text", true, true, false);
```

### Running a Macro

```csharp
object res = app.RunMacro("mscro1", new List<object>() { 10 });
```

### Saving the Document

```csharp
app.Save();
app.SaveAs("C:\\file.pptx");
```

### Deleting a Slide

```csharp
app.DeleteSlide(4);
```

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

### Element "PowerPoint presentation"

All of the components listed below are added to the workspace within the **PowerPoint presentation** element. This component establishes a connection to the PowerPoint application. If the specified file is not available, a new one will be created. The **PowerPoint presentation** element includes the following properties:

1. **PowerPoint**:
   - Byte array – A byte array of the document.
   - File path – You can specify the file path using the button ![alt text](image-3.png) in the Explorer window.

### Element "Add media-file"

Inserts a media file into the presentation. It includes the following properties:

1. **PowerPoint**:
   - Slide index
   - File – file path.
   - Shape – name of the shape for insertion.
2. **Coordinates**:
   - Height
   - Top – top margin.
   - Left – left margin.
   - Width

### Element "Paste item"

Inserts an object into the presentation. It includes the following properties:

1. **PowerPoint**:
   - Slide index
   - Shape – name of the shape for insertion.
2. **Coordinates**:
   - Height
   - Top – top margin.
   - Left – left margin.
   - Width

### Element "Add data table"

Inserts a table into the presentation. It includes the following properties:

1. **PowerPoint**:
   - Slide index
   - Omit headers – exclude headers from the table.
   - Overwrite from column – overwrite starting from the specified column.
   - Overwrite from row – overwrite starting from the specified row.
   - Mode – data insertion mode.
   - Table – table data for insertion.
   - Shape – name of the shape for insertion.

### Element "Add text"

Inserts text into the presentation. It includes the following properties:

1. **PowerPoint**:
   - Slide index
   - Shape – name of the shape for insertion.
   - Text
   - Clear – clear existing text.

### Element "Add file"

Inserts a file into the presentation. It includes the following properties:

1. **PowerPoint**:
   - Title – title of the file icon.
   - Slide index
   - File – file path.
   - Shape – name of the shape for insertion.

### Element "Add new slide"

Adds a new slide to the presentation. It includes the following properties:

1. **PowerPoint**:
   - Layout – layout of the slide.
   - Index – insertion index. If not specified, the slide is added at the end.
   - Theme – slide theme design.
2. **Result**:
   - New index – index of the new slide.

### Element "Replace text"

Replaces text in the presentation. It includes the following properties:

1. **PowerPoint**:
   - Replace – required field. Text to replace.
   - Replace all – replace all occurrences of the text.
   - Text – required field.
   - Case – case sensitivity.
   - Whole word – replace whole words only.
2. **Result**:
   - Replace count

### Element "Run macro"

Executes a PowerPoint macro. It includes the following properties:

1. **PowerPoint** (required fields):
   - Arguments – macro arguments.
   - Macro – name of the macro.
2. **Result**:
   - Result

### Element "Copy-paste slide"

Copies and pastes a slide within the presentation. It includes the following properties:

1. **PowerPoint**:
   - Slide index
   - Destination slide index
   - Move – perform a slide transfer.
   - Destination file – file path.

### Element "Edit shape"

Edits a shape in the presentation. It includes the following properties:

1. **PowerPoint** (required fields):
   - Slide index
   - Shape – name of the shape for editing.
2. **Z-order**:
   - Change z-order – flag for changing the layer position.
   - Z-order change type – type of z-order change.
3. **Font**:
   - Size

### Element "Save presentation"

Saves the PowerPoint file. If the file path is not specified, the file opened within the current PowerPoint container will be saved. It includes the following properties:

1. **Misc**:
   - File path

### Element "Delete slide"

Deletes a slide from the presentation. It includes the following properties:

1. **PowerPoint**:
   - Index – slide index. If not specified, the last slide is deleted.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.com](mailto:support@primo-rpa.com).
