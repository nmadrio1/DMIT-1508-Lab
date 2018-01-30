# ESP document 1

This is a simple solution of normalizing the **Customer Order View** in ESP Document 1.


## customers order View


### 0NF - list all attributes

After performing Zero-normal form, a single table (entity) was generated: **Order**.

**Order** (CustomerNumber, Firstname, LastName,Address, City, 
Province, PostalCode, Phone, Date, <b class="pk">OrderNumber</b>, 
<b class="gp">{</b> ItemNumber, Description,Quantity,CurrentPrice,
 SellingPrice,Amount <b class"gp">}</b>, subtotal, Gst, Total)

### 1NF - Identity Repeating Group

After performing First-Normal Form, a new table was generated: OrderDetail.

**Order:** (<b class="pk">OrderNumber</b>, CustomerNumber, FirstName, LastName, Address,City, Province, PostalCode, Phone, Date, Subtotal, GST, Total)


**OrderDetail** (<b class="pk"><u class="fk">OrderNUmber</u>,ItemNumber</b>,Descrption, Quantity, CurrentPrice, SellingPrice,Amount)





###2NF

After performing Second-Normal Form, another new table was generated: **Item**


**OrderDetails**(<b class="pk"><u class="fk">OrderNumber</u>,<u class="fk"> ItemNumber </u></b>, Quantity, SellingPrice, Amount)

**item**(<b class="pk">ItemNumber</b>, Description, CurrentPrice)






### 3NF
After performing Third-Normal Form, another new table was generateed:**Customer**.

**Order** (<b class="pk">OrderNumber</b>, <u class="fk">CustomerNumber</u>, Date, SubTotal, GST, Total)

**Customer** (<b class="pk">CustomerNumber</b>,FirstName, LastName,Address, City, Province, PostalCode, Phone)


###Tables after 3<sup>rd</sup> Normal Form


These are the tables/entities after normalizing the customer detail View.

**Order** (<b class="pk">OrderNumebr</b>, <u class="fk">CustomerNumber</u>, Date SubTotal,Gst,total)

**OrderDetail** (<b class="pk"><u class="fk">OrderNumber</u>,<u class="fk">itemnumber</u></b>, quantity, SeliingPrice, Amount)

**Item** (<b class="pk">itemnumber</b>,description, currentPrice)








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
