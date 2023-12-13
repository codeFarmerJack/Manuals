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

# 7. CDbl
    CDbl is a conversion function that stands for "Convert to Double." It is used to convert 
    a value to a double data type.

# 8. Trim
    The Trim function is used to remove leading and trailing spaces from a string. It does not
    remove spaces between words.
 # 9. Val
     The Val function is used to extract the numetric value from a string. It reads characters 
     from the beginning of the string until it encouners a character that is not a valid part 
     of a number and returns the numeric value formed by those characters.

# 10. Exit
    The Exit statement is used to immediately exit a loop or a subroutine (a function or a procedure).
    It is often used in combination with conditional statement to control the flow of the program.

# 11. IsNumeric
    The IsNumeric function is used to determine whether a given expression can be evaluated as a 
    number. It returns a Boolean value indicating whether the expression is numeric (True) or not (False).

# 12. Ways to read a value from a cell 
## 12.1 Direct Access:
    Access the cell value directly using its address.
        Dim myValue As Variant
        myValue = Range("A1").Value
## 12.2 Using Cells Property:
    Use the Cells property to reference a cell by row and column
        Dim myValue As Variant
        myValue = Cells(1, 1).Value    ' Refers to cell A1
## 12.3 With Worksheets:
    Specify the worksheet to avoid ambiguity.
        Dim myValue As Variant
        myValue = Worksheets("Sheet1").Range("A1").Value
## 12.4 With Range Object:
    Use the Range object with more flexibility.
        Dim myValue As Variant
        Dim myCell As Range
        Set myCell = Range("A1")
        myValue = myCell.Value
## 12.5 Reading Specific Data Types:
    Use specific methods based on the data type you expect.   
        Dim stingValue As String
        stringValue = Range("A1").Text    ' Get the displayed text
## 12.6 Reading Formulas:
    To read the formula instead of the result, use the Formula property.
        Dim formulaString As String
        formulaString = Range("A1").Formula
## 12.7 Reading Numeric Values:
    Use Val or CDbl to convert text to numeric values
        Dim numericValue As Double
        numericValue = CDbl(Range("A1").Value)
## 12.8 Reading Dates
    If the cell contains a date, use CDate.
        Dim myDate As Date
        myDate = CDate(Range("A1").Value)
