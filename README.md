# PowerAutomate_Benefits-of-Select-Action

There is more to the Power Automate Select action than just picking the array's designated columns. It allows us to edit current values in an array, add new columns, add an index number, and more.<br>
You will probably be surprised by the examples below and be inspired to consider more use cases.

<h2>Select The Specified Columns Of An Array</h2>
<br>
The Power Automate Select action can be used to select specific columns from an array and remove the other columns. For example, assume there is an array of test scores with the columns Maker, Model, Year. We can select the Maker and Model columns and drop the Year column.
<br><br>

<p align="center">
<img src="https://github.com/user-attachments/assets/aa6a0e46-8c90-42fe-bae5-15d694c540e5" alt=PowerAutomate">
</p>

---

<br><br>

<p align="center">
<img src="https://github.com/user-attachments/assets/c89e9407-813b-44e9-aeaa-851cd21863a4" alt=PowerAutomate">
</p>

---

<br><br>

<p align="center">
<img src="https://github.com/user-attachments/assets/778dd0e3-0ce7-4119-9d3a-90f4507bc83f" alt=PowerAutomate">
</p>
<br><br>
Code for Select action

```
Maker: item()?['Maker']
Model: item()?['Model']
```

**Result**

Select: Maker and Model columns from Array
<p align="center">
<img src="https://github.com/user-attachments/assets/c9acb01d-313e-46d6-a001-8ecf9af83408" alt=PowerAutomate">
</p>

<h2>Add A New Column To An Array</h2>
<br>
To add a new column to a Power Automate array we can use a combination of the select action and the addProperty function. First we switch the select action map field to text mode we make it display a single field. Then we input the addProperty function with the new column name and value. The select action loops over each row in the array and adds the new column.
<br><br>
<p align="center">
<img src="https://github.com/user-attachments/assets/99eb06c3-a461-4cb4-91a7-986fdc5e9c9a" alt=PowerAutomate">
</p>

---

<br><br>
<p align="center">
<img src="https://github.com/user-attachments/assets/28d84663-aea3-4362-a336-1c9d65cb2fbc" alt=PowerAutomate">
</p>

**Code**

```
addProperty(item(),'Electric',contains(item()?['Maker'],'EV'))
```

**Result**
<p align="center">
<img src="https://github.com/user-attachments/assets/578334bf-4b8c-48ac-a565-91c93b00b213" alt=PowerAutomate">
</p>

<br><br>

<h2>Create An Array List Of Values With No Column Names</h2>
A Power Automate array list is a list of values with no column names. They are helpful for finding a list of unique values and doing contains/does not contain comparisons. To create an array list add a select action and change the map field to text mode. Then we add the dynamic value for the field we want to create the array list for.

<br><br>

<p align="center">
<img src="https://github.com/user-attachments/assets/aa6a0e46-8c90-42fe-bae5-15d694c540e5" alt=PowerAutomate">
</p>

---
<br><br>

<p align="center">
<img src="https://github.com/user-attachments/assets/b86ff5fc-2bf0-45e3-8e8e-3abfb4b8b269" alt=PowerAutomate">
</p>

**Code**

```
item()?['Maker']
```

**Result**
<br><br>

<p align="center">
<img src="https://github.com/user-attachments/assets/8a7f4623-0dee-4332-917f-271c805ccd7f" alt=PowerAutomate">
</p>

<br><br>

<h2>Convert Text To A Number Column In An Array</h2>
Often times numbers are found as a text data type inside of an array. The setProperty function can be used to change a string column to a number column. We do this by adding the setProperty function to the map property of a select action supplying the column name and a function to convert to a new data type. In this example we use the int function to change the text string to an integer. We could also use the decimal function or the float function as well.

<br><br>
<p align="center">
<img src="https://github.com/user-attachments/assets/f82eaa5b-2872-4f7a-b862-ac88f3de0e66" alt=PowerAutomate">
</p>

---

<br><br>
<p align="center">
<img src="https://github.com/user-attachments/assets/4ebda78d-d01c-43d3-bebd-8683c20d0963" alt=PowerAutomate">
</p>

<br><br>

**Code**

```
setProperty(item(),'Year',int(item()?['Year']))
```

**Result**
<br><br>

<p align="center">
<img src="https://github.com/user-attachments/assets/97ea065d-531a-4d39-9e35-bf7677e06119" alt=PowerAutomate">
</p>

<br><br>
