# FXML Basics

## Basic FXML exapmle

The example will include a `Label` and a `Button`, with an event handler in the controller to update the label when the button is clicked.
```xml
<?xml version="1.0" encoding="UTF-8"?>

<?import javafx.scene.control.Button?>
<?import javafx.scene.control.Label?>
<?import javafx.scene.layout.VBox?>

<!-- Root layout is VBox -->
<VBox xmlns="http://javafx.com/javafx" xmlns:fx="http://javafx.com/fxml" fx:controller="com.example.MyController" alignment="CENTER" spacing="10">

    <Label text="Hello, World!" fx:id="label"/>
    <Button text="Click Me!" onAction="#handleButtonClick"/>

</VBox>
```

Explanation of the FXML:

- `VBox`: is the root layout, which vertically arranges the Label and Button.
- `xmlns="http://javafx.com/javafx"`
  - This is the default namespace declaration for JavaFX. It tells the XML parser that the elements within this FXML file are part of the JavaFX framework.
  - The URL "http://javafx.com/javafx" defines the JavaFX namespace, which is required in every FXML file to specify that you are using JavaFX components.
- `xmlns:fx="http://javafx.com/fxml"`
  - This is the FX namespace used for FXML-specific attributes. The fx: prefix is applied to attributes that are FXML-specific, such as fx:id, fx:controller, and fx:include.
  - The URL "http://javafx.com/fxml" defines the FXML namespace for handling FXML attributes.
- `fx:controller="com.example.MyController"`
  - This attribute links the FXML file to a controller class that manages the behavior of the user interface components defined in the FXML.
  - fx:controller="com.example.MyController" specifies that the controller class is MyController in the com.example package.
  - The controller class contains the logic to handle events and interactions with the UI components defined in the FXML file (such as button clicks, label updates, etc.).

- `Label`: is a basic UI component that displays a text
- `fx:id="label"`: This ID allows the controller to reference and modify the Label.
- `Button`: is a basic UI component that triggers an action when clicked.
- `onAction="#handleButtonClick"` This links the button click event to a method named handleButtonClick() in the controller.

## FXML components

In JavaFX, FXML files allow you to define the user interface in a declarative way, separating the layout from the logic. The basic FXML components are JavaFX UI elements such as buttons, labels, text fields, containers, and controls, which are defined as XML tags in the FXML file. Here’s a list of basic FXML components commonly used to build user interfaces in JavaFX applications.

### 1. Label

A Label is used to display static text or other non-interactive content.

```xml
<Label text="Hello, World!" fx:id="myLabel" />
```
Attributes:
- text: The text to display in the label.
- fx:id: A unique ID to reference the label in the controller.
- graphic: Adds an image or node beside the label text.
- textFill: Sets the color of the text.
- font: Controls the font family, size, and style.
- alignment: Aligns the text and graphic inside the label.
- wrapText: Enables text wrapping within the label.
- graphicTextGap: Sets the gap between the graphic and the text.
- contentDisplay: Controls the layout of text and graphic (e.g., graphic above, below, to the right).
- labelFor: Links the label to another control.

### 2. Button

A Button is an interactive component that users can click to trigger an action.

```xml
<Button text="Click Me!" onAction="#handleButtonClick"/>
```

Attributes:
- text: The text displayed on the button.
- onAction: Specifies the event handler method in the controller to call when the button is clicked.
- graphic: A Node (usually an ImageView) displayed alongside the text.
- textFill: The color of the text.
- font: The font family, size, and style of the text.
- disable: Disables the button, making it non-interactive.
- visible: Controls whether the button is visible or hidden.
- alignment: Controls how text and graphic are aligned within the button.
- graphicTextGap: The space between the graphic and the text.
- contentDisplay: Determines the position of the graphic relative to the text.
- defaultButton and cancelButton: Makes the button a default or cancel button.
- tooltip: Provides additional information when hovered over the button.
- style and styleClass: Allows inline CSS or external styling through a CSS file.


### 3. TextField

A TextField is a single-line input field where users can enter text.
```xml
<TextField fx:id="textField" promptText="Enter your name"/>
```
Attributes:
- fx:id: A unique ID to reference the text field in the controller.
- promptText: Placeholder text shown when the text field is empty.

### 4. TextArea

A TextArea is a multi-line input field that allows users to enter large amounts of text.

```xml
<TextArea fx:id="textArea" promptText="Enter your message"/>
```
Attributes:
- fx:id: A unique ID to reference the text area in the controller.
- promptText: Placeholder text shown when the text area is empty.

### 5. CheckBox

A CheckBox is a control that can be checked or unchecked, allowing users to make binary choices.

```xml
<CheckBox text="I agree to the terms" fx:id="checkBox" />
```
Attributes:
- text: The label associated with the checkbox.
- fx:id: A unique ID to reference the checkbox in the controller.

### 6. RadioButton

A RadioButton allows users to select one option from a group of options. To group RadioButtons, you need to associate them with the same ToggleGroup.

```xml
<ToggleGroup fx:id="group" />
<RadioButton text="Option 1" toggleGroup="$group" />
<RadioButton text="Option 2" toggleGroup="$group" />
```
Attributes:
- text: The label for the radio button.
- toggleGroup: Links the radio buttons to the same group so only one can be selected.

### 7. ComboBox

A ComboBox is a dropdown list from which users can select one item.
```xml
<ComboBox fx:id="comboBox">
    <items>
        <FXCollections fx:factory="observableArrayList">
            <String fx:value="Option 1"/>
            <String fx:value="Option 2"/>
            <String fx:value="Option 3"/>
        </FXCollections>
    </items>
</ComboBox>
```
Attributes:
- fx:id: A unique ID to reference the combo box in the controller.
- items: A list of items to display in the dropdown.

### 8. Slider

A Slider allows users to select a value from a range by moving a slider knob.
```xml
<Slider fx:id="slider" min="0" max="100" value="50"/>
```
Attributes:
- min: The minimum value of the slider.
- max: The maximum value of the slider.
- value: The initial value of the slider.

### 9. ProgressBar

A ProgressBar visually indicates the progress of a task.
```xml
<ProgressBar fx:id="progressBar" progress="0.5"/>
```
Attributes:
- progress: A value between 0 and 1 indicating the progress (50% in this case).

### 10. TableView

A TableView displays tabular data, often used to show lists or tables of information.

```xml

<TableView fx:id="tableView">
    <columns>
        <TableColumn text="Name"/>
        <TableColumn text="Age"/>
    </columns>
    </TableView>
```
Attributes:
- columns: Defines the columns in the table.

### 12. ListView

A ListView displays a list of items that users can select from.
```xml
<ListView fx:id="listView">
    <items>
        <FXCollections fx:factory="observableArrayList">
            <String fx:value="Item 1"/>
            <String fx:value="Item 2"/>
            <String fx:value="Item 3"/>
        </FXCollections>
    </items>
</ListView>
```


## Layout Containers

Layout containers help arrange and position the components within the UI. Common layout containers include:

### 1. VBox (Vertical Box Layout)

Arranges its children vertically.
```xml
<VBox alignment="CENTER" spacing="10">
    <Label text="Enter your details"/>
    <TextField fx:id="nameField" promptText="Name"/>
    <Button text="Submit" onAction="#handleSubmit"/>
</VBox>
```

### 2. HBox (Horizontal Box Layout)

Arranges its children horizontally.
```xml
<HBox alignment="CENTER" spacing="10">
    <Button text="Option 1"/>
    <Button text="Option 2"/>
</HBox>
```

### 3. GridPane (Grid Layout)

Arranges its children in a grid of rows and columns.
```xml
<GridPane hgap="10" vgap="10">
    <Label text="Name" GridPane.rowIndex="0" GridPane.columnIndex="0"/>
    <TextField GridPane.rowIndex="0" GridPane.columnIndex="1"/>
    <Label text="Age" GridPane.rowIndex="1" GridPane.columnIndex="0"/>
    <TextField GridPane.rowIndex="1" GridPane.columnIndex="1"/>
</GridPane>
```
### 4. BorderPane (Border Layout)

Divides the layout into five regions: top, bottom, left, right, and center.
```xml
<BorderPane>
    <top>
        <Label text="Top Section"/>
    </top>
    <center>
        <TextArea promptText="Main Content"/>
    </center>
    <bottom>
        <Button text="Submit"/>
    </bottom>
</BorderPane>
```
