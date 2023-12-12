# 1. Dim
    'Dim' is a keyword used to declare variables. The term 'Dim' stands for 'dimension'
    When you declare a variable using Dim, you are essentially specifying the type and 
    name of the variable.
    Example:
        Dim firstName As String, age As Integer, salary As Double
# 2. Range Type
    "Range" refers to a group of cells in an Excel worksheet. It can represent a single cell
    a row, a column, or a rectangular block of cells. The Range object is fundamental in VBA
    programming as it allows you to manipulate and interact with data in specific locations
    within a worksheet.
# 3. Variant Type
    Variant is a versatile data type that can hold any type of data. It is a default data type
    if you don't explicitly specify a type.
    Implicit Conversion: VBA will automatically convert the data type of a Variant variable 
    based on the assigned value.

# 4. Offset 
    In VBA, the Offset property is used to refer to a cell or a range of cells that is a 
    certain number of rows and columns away from a specified cell or range. The syntax for
    Offset is as follows:
    'expression.Offset(RowOffset, ColumnOffset)'
        * expression: This is the cell or range of cells from which you want to offset.
        * RowOffset: The number of rows, positive or negative, by which you want to offset
        the range. If positive, it moves the range down; if negative, it moves it up.
        * ColumnOffset: The number of columns, positive or negative, by which you want to 
        offset the range. If positive, it moves the range to the right; if negative, it moves
        it to the left.
# 5. Set
    In VBA, the Set keyword is used to assign an object reference to a variable. This is typicall
    used when you're working with objects like ranges, worksheets, charts, etc. The basic 
    syntax for the Set statement is:
    'Set variableName = objectReference'

# 6. vbCrLf
    vbCrLf is a constant representing a carriage return and line feed, which are used to create
    a new line in a text string. For example:
        MsgBox "Hello" & vbCrLf & "World"
    This code would display a message box with "Hello" on the first line and "World" on the 
    second line. vbCrLf is commonly used when you want to concatenate multiple lines of text.
