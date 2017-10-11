# Fill GridView Control with Dummy Data (`ASP.NET`)

Quickly Populate a GridView With Dummy Data

Maybe the database table isn’t ready yet, but you’d like to start working on a new GridView. What you need is a quick and dirty way to load up a GridView control with sample data.

## Drop a GridView Control onto the .ASPX Page

```asp
<asp:GridView ID="gvExample" runat="server" />
```

## Helper Functions

In the article [Generating Random Number and String in C#](http://www.c-sharpcorner.com/article/generating-random-number-and-string-in-C-Sharp/), author Mahesh Chand wrote 2 random functions:

1. RandomNumber
1. RandomString

I modified them slightly by making the random variable public. This will allow us to get a fresh random number with each call.

## LoadGridView

The parameters for this function are:

* **columnCount:** Number of columns
* **rowCount:** Number of rows
* **useNumeric:** Use Numeric Data (true/false)
* **rowLength:** Length of Text inside rows
* **minNumber:** Lower range of numeric data
* **maxNumber:** Upper range of numeric data

_created: July 23, 2007_