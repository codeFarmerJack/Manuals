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
# 13. Sub
    Sub is short for "Subrountine." It is used to define a block of code that performs
    a specific task.
# 14. Option Explicit
    The Option Explicit statement is used to enforce variable declaration. When you include 
    Option Explicit at the beginning of your module, VBA requires you to explicitly declare
    all variables using the Dim statement before using them.
# 15. Collection
    A Collection is an object that can store and manage a group of items.
    * Collection.Add is used to add items to the collection.
    * You can access items in the collection using index values, starting from 1.
## 15.1 Declaration and Initialization:
    To use a Collection, you first declare a variable of type Collection. Then use the New
    keyword to initialize it. For example:
        Dim myCollection As Collection
        Set myCollection = New Collection 
## 15.2 Adding Items:
    Add items to the collection using the Add method. Items can be of any data type, and you 
    can mix different types within the same collection. For example:
        myCollection.Add "Item 1"
        myCollection.Add 123
## 15.3 Removing Items:
    To Remove an item from the collection, you can use the Remove method. You can remove an item 
    by its index or by specifying the actual item. For example:
        myCollection.Remove 123
## 15.4 Accessing Items:
    You can access items in the collection using the index. The index starts at 1 for the first item.
    For example:
        MsgBox myCollection(1)     ' Display the first item in the collection 
## 15.5 Count Property:
    The Count Property returns the number of items in the collection. For example:
        MsgBox myCollection.Count     ' Displays the number of items in the collection
## 15.6 For Each Loop:
    You can iterate through all items in the collection using a For Each loop. For example:
        Dim item As Variant 
        For Each item In myCollection
            MsgBox item 
        Next item
## 15.7 Dynamic Structure
    One significant advantage of a Collection is that it is dynamic. You can add or remove items at 
    runtime, and the collection adjusts accordingly.
# 16. Dictionary.Add 
    This is a method of the Dictionary object used to add a key-value pair to the dictionary.
## 16.1 Dictionary.Add spdTestVal, New Collection
    Add a new key-value pair to the dictionary. The Key is spdTestVal, and the associated
    value is a new instance of a Collection.
## 16.2 Dictionary.Add spdTestVal & "_Count", 0
    * spdTestVal & "_Count": This is the key being added to the dictionary. It is formed by 
    concatenating the value of spdTestVal with "_Count". So if spdTestVal is "Test1," the resulting
    key would be "Test1_Count."
    * , 0: This part specifies the value associated with the key being added. In this case, its' the 
    numeric value 0. This is the initial value associated with the newly added key.
# 17. Right(spdTestVal, 6) = "_Count"
    This line of code checks if the rightmost 6 characters of the string variable spdTestVal are equal 
    to "_Count"
# 18. Set avgCell = outputRange.Find(Left(spdTestVal, Len(spdTestVal) - 6), LookIn:=xlValues, LookAt:=xlWhole)
    * outputRange.Find: This part of the code is calling the Find method on the outputRange object. 
    * Left(spdTestVal, Len(spdTestVal) - 6): This is the value being searched for. It's the left 
    portion of spdTestVal with the last 6 characters removed. The Left function is used to get a 
    specified number of characters from the left side of a string, and Len(spdTestVal) - 6 calculates 
    the length of spdTestVal minus 6 characters.
    * LookIn:=xlValues: This parameter specifies where to look for the value. In this case, it's set 
    to search within the values of cells in outputRange.
        - The LookIn parameter in the Find method specifies where to search for the specified value.
        - xlValues is a constant in VBA that represents the values within cells, excluding any formulas.
        So, when LookIn is set xlValues, the Find method searches for the specified value only in the
        actual content of the cells.
        - Other options for LookIn:
            + xlFormulas: Searches for the specified value in formulas within the cells
            + xlComments: Searches for the specified value in cell comments
            + xlCommentsThreaded: Searches for the specified value in threaded cell comments.
            + ...
    * LookAt:=xlWhole: This parameter specifies the type of match to be performed. xlWhole means it's 
    looking for a complete match.
    * Set avgCell = ...: This line is setting the variable avgCell to the result of the Find method. 
    If the value is found, avgCell will contain a reference to the cell where the value is found. If 
    the value is not found, avgCell will be set to Nothing.
    

