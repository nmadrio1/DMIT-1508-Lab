# ESP document 1

This is a simple solution of normalizing the **Customer Order View** in ESP Document 1.


## Employee View


### 0NF - list all attributes

After performing Zero-normal form, a single table (entity) was generated: **Employee Detail**.

**Employee Detail** ( <b class="pk">Employee Number</b>,SIN, First Name, Last Name, Address, City, Postal Code, Home phone, Work phone, Email, Employee group code, Employee group Name, Wage)

### 1NF - Identity Repeating Group



**Nothing Changes**




###2NF

**Nothing Changes**



### 3NF


**Nothing Changes**

### ERD for Employee View

-![](ESP-1-ERD-EmployeeVIews.png)
----

## 2nd Diagram

## Book Title View


### 0NF - list all attributes

After performing Zero-normal form, a single table (entity) was generated: **OrderDetail**.

**OrderDetail** (<b class="pk">ISBN</b>, Title, Selling Price, Number in stock, Publisher code, publisherLastName, PublisherFirstName, CategoryCode, CategoryDescription,<b class="gp">{</b>Author code, Author First Name, Author Last Name<b class="gp">}</b>, )

### 1NF - Identity Repeating Group

After performing First-Normal Form, a new table was generated:**ItemDetail** .

**OrderDetail** (<b class="pk">ISBN</b>, Title, Selling Price, Number in stock, Publisher code, publisherLastName, PublisherFirstName, CategoryCode, CategoryDescription)


**ItemDetail** (<b class="pk"><u class="fk">ISNB</u>, AuthorCode</b>, AuthorFirstName, AuthorLasstName)



###2NF

After performing Second-Normal Form, another new table was generated: **AuthorID**


**ItemDetail**(<b class="pk"><u class="fk">AuthorCode</u>,<u class="fk"> ISNB</u></b>, AuthorLastName,AuthorFirstName)

**AuthorID**(<b class="pk">AuthorCode</b>, AuthorLastName, AuthorFirstName)






### 3NF
After performing Third-Normal Form, another new table was generateed:**Category**.

These are the tables/entities after normalizing the customer detail View.

**OrderDetail** (<b class="pk">ISBN</b>, Title, Selling Price, Number in stock, Publisher code, publisherLastName, PublisherFirstName, CategoryCode, CategoryDescription)

**ItemDetail**(<b class="pk"><u class="fk">AuthorCode</u>,<u class="fk"> ISNB</u></b>, AuthorLastName, AuthorFirstName)

**AuthorID**(<b class="pk">AuthorCode</b>, AuthorLastName, AuthorFirstName)


**Category** (<b class="pk">CagoryCode</b>, Title, CategoryDescription)



### ERD for Book Title View


-![](ESP-1-BookTitleVIew.png)
----





## 3rd Diagram

## Sale View


### 0NF - list all attributes

After performing Zero-normal form, a single table (entity) was generated: **Sales View**.

**Sales View** (<b class="pk"> SalesNumber</b>, CustomerNumber, Employee Number, CustomerFirstName, CustomerLastName, EmployeeFirstName,EmployeeLastName <b class="gp">{</b>ISBN, BookTitle, Price, Quantity, Amount <b class="gp">}</b>, SubTotal, Total, GST)

### 1NF - Identity Repeating Group

After performing First-Normal Form, a new table was generated: OrderDetail.

**Sales View** (<b class="pk"> SalesNumber</b>, CustomerNumber, Employee Number, CustomerFirstName, CustomerLastName, EmployeeFirstName,EmployeeLastName, SubTotal, Total, GST)


**BookInfo** (<b class="pk">ISBN,<u class="fk">SalesNumber</u></b>, BookTitle, Price,Quality, Amount)





###2NF

After performing Second-Normal Form, another new table was generated: **PrudocInfo & SalesDetail**


**BookInfo**(<b class="pk"><u class="fk">SalesNumber</u>,<u class="fk"> ISBN </u></b>, BookTitle, Price,Quality, Amount)

**ProductInfo**(<b class="pk">ISBN</b>, BookTitle)

**SaleDetail**(<b class="pk">SalesNumber</b>, Price, Amount)






### 3NF
After performing Third-Normal Form, another new table was generateed:**CustomerDetail**.


###Tables after 3<sup>rd</sup> Normal Form


These are the tables/entities after normalizing the customer detail View.

**Sales View** (<b class="pk"> SalesNumber</b>, CustomerNumber, Employee Number, CustomerFirstName, CustomerLastName, EmployeeFirstName,EmployeeLastName, SubTotal, Total, GST)

**BookInfo**(<b class="pk"><u class="fk">SalesNumber</u>,<u class="fk"> ISBN </u></b>, BookTitle, Price,Quality, Amount)

**ProductInfo**(<b class="pk">ISBN</b>, BookTitle)

**SaleDetail**(<b class="pk">SalesNumber</b>, Price, Amount)

**CustomerDetail** (<b class="pk">CustomerNumber</b>,CustomerFirstName, CustomerLastName, Address, PostalCode, City, Province)


### ERD for Sales View


-![](ESP-1-SaleVIew.png)
----


### Merged ERD AREA


-![](ESP-1-Merge.png)

----




----
<style type="text/css">
.pk {
    font-weight:bold;
    display:inline-block;
    border: solid thin blue;
    padding: 0 1px;
}
.fk {
    color:green;
    font-style: italic;
    text-decoration:wavy underline green;
}
.gp {
    color:darkorange;
    font-size:1.2em;
    font-weight:bold;
}
</style>
