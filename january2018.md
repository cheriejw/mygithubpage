## Default Code
```csharp
//For DataTables
using System;
using System.Data;
using System.Collections.Generic;
using System.Linq;
using System.Text.RegularExpressions;

namespace Rextester
{
    public class Program
    {
        public static void Main(string[] args)
        {
            //Your code goes here
            Console.WriteLine("Hello, world!");
            
            
            DataTable table = new DataTable("Orders");
      table.Columns.Add("OrderID", typeof(Int32));
      table.Columns.Add("OrderQuantity", typeof(Int32));
      table.Columns.Add("CompanyName", typeof(string));      
      table.Columns.Add("Date", typeof(DateTime));

      DataRow newRow = table.NewRow();
      newRow["OrderID"] = 1;
      newRow["OrderQuantity"] = 3;
      newRow["CompanyName"] = "NewCompanyName";

      // Add the row to the rows collection.
      table.Rows.Add(newRow);

      DataRow newRow2 = table.NewRow();
      newRow2["OrderID"] = 2;
      newRow2["OrderQuantity"] = 2;
      newRow2["CompanyName"] = "NewCompanyName1";
      table.Rows.Add(newRow2);

      DataRow newRow3 = table.NewRow();
      newRow3["OrderID"] = 3;
      newRow3["OrderQuantity"] = 2;
      newRow3["CompanyName"] = "NewCompanyName2";
      table.Rows.Add(newRow3);

      // Presuming the DataTable has a column named Date.
      string expression = "OrderID = 2";
      // string expression = "OrderQuantity = 2 and OrderID = 2";

      // Sort descending by column named CompanyName.
      string sortOrder = "CompanyName ASC";
      DataRow[] foundRows;

      // Use the Select method to find all rows matching the filter.
      foundRows = table.Select(expression, sortOrder);

            
        foreach(DataColumn column in table.Select(expression, sortOrder).Columns)
        {
            Console.WriteLine(column.ColumnName);
        }
    }
        }
}
```
```

## **Any programming language of course serves two goals:**
- Provide instructions to the computer.
- Leave a record of the intentions of the programmer.
---

## Java
[Switch with String](https://stackoverflow.com/questions/338206/why-cant-i-switch-on-a-string?rq=1)

## C#
[Casting with as](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators)
```csharp
protected void lstDistributionType_SelectedIndexChanged(object sender, EventArgs e)
{
    DropDownList list = (DropDownList)sender;
    TableCell cell = list.Parent as TableCell;
    DataGridItem item = cell.Parent as DataGridItem;
}
```

[Utilized Solution](https://www.hackerrank.com/challenges/staircase/problem)
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
class Solution {

    static void staircase(int n) {
        string pound = "";
        for (int i = 0; i < n; i++){
            pound += "#";
            Console.Write($"{{0,{n}}}\n", pound);
        }
    }

    static void Main(String[] args) {
        int n = Convert.ToInt32(Console.ReadLine());
        staircase(n);
    }
}
```

[Putting 'using' inside or outside of namespace](https://stackoverflow.com/questions/125319/should-using-statements-be-inside-or-outside-the-namespace)
Basically If you put the using outside of the nestest namespace, the code in that nested namespace file will look and use the using from the higher namespace. If you put it inside of the namespace, it will use that first. Searches its own namespace (inside of {}), then searches the namespace up (inside {}). When you put using outside of namespace and it searches your namespace it won't be there, it will be showed last on the higher level namespace.

[C#, .NET, ASP.NET](https://softwareengineering.stackexchange.com/questions/44810/relationship-between-c-net-asp-asp-net-etc)
>Though C# as a language was originally developed at Microsoft as part of .NET Framework, it was later standardised by ECMA, meaning that independent standard-compliant implementations of the language can be developed, and indeed they were. The most prominent of those is Mono.

[Switch Statement Fallthrough in C# Language Design](https://stackoverflow.com/questions/174155/switch-statement-fallthrough-in-c)
>**In summary therefore:**
-- C# no longer relates to unoptimised compiler output as directly as C code did 40 years ago (nor does C these days), which makes one of the inspirations of fall-through irrelevant.
-- C# remains compatible with C in not just having implicit break, for easier learning of the language by those familiar with similar languages, and easier porting.
-- C# removes a possible source of bugs or misunderstood code that has been well-documented as causing problems for the last four decades.
-- C# makes existing best-practice with C (document fall through) enforceable by the compiler.
-- C# makes the unusual case the one with more explicit code, the usual case the one with the code one just writes automatically.
-- C# uses the same goto-based approach for hitting the same block from different case labels as is used in C. It just generalises it to some other cases.
-- C# makes that goto-based approach more convenient, and clearer, than it is in C, by allowing  case statements to act as labels.-
**All in all, a pretty reasonable design decision**



[C# Colon](https://stackoverflow.com/questions/17034475/in-c-sharp-what-category-does-the-colon-fall-into-and-what-does-it-really)
```CS
Console.WriteLine(value: "Foo"); 
//prints Foo
Console.WriteLine(vale: "Foo");
//Error(s): (15:31) The best overload for 'WriteLine' does not have a parameter named 'vale'
```

[Datagrid, ItemDataBound, access selected.](https://msdn.microsoft.com/en-us/library/system.web.ui.webcontrols.datagrid.itemdatabound(v=vs.110).aspx)
## SQL

##### Delete Update Cascade
```SQL
ALTER TABLE [dbo].[RemitCategoryAssoc]  WITH CHECK ADD  CONSTRAINT [FK_RemitCategoryAssoc_RemitCategory] FOREIGN KEY([RemitCategoryId])
REFERENCES [dbo].[RemitCategory] ([RemitCategoryId])
ON DELETE CASCADE
GO
```

##### Relational Operations
[Relational Operations: Table to Table comparasion w/ same columns.](https://stackoverflow.com/questions/4602083/sql-compare-data-from-two-tables)
>Using relational operators:
```SQL
SELECT * FROM TableA
UNION 
SELECT * FROM TableB
EXCEPT 
SELECT * FROM TableA
INTERSECT
SELECT * FROM TableB;
```
>Change EXCEPT to MINUS for Oracle.
Slightly picky point: the above relies on operator precedence, which according to the SQL Standard is implementation dependent, so YMMV. It works for SQL Server, for which the precedence is:

Expressions in parentheses
INTERSECT
EXCEPT and UNION evaluated from left to right.

##### --- **1/8/2018** ---
> Dates are inefficient, going by topic now.

##### --- **1/5/2018** ---
> The moral of the story is ASMX is simple and because it is simple, it isn’t very powerful.  Take the time to learn about WCF because this is the future of the .Net platform, thus it will be time wisely spent.
[WCF VS ASMX](http://keithelder.net/2008/10/17/wcf-vs-asmx-webservices/)
[S.O.](https://stackoverflow.com/questions/2448472/what-are-the-differences-between-wcf-and-asmx-web-services)

ASMX is:
- easy and simple to write and configure
- only available in IIS
- only callable from HTTP

WCF can be:
- hosted in IIS, a Windows Service, a Winforms application, a console app - you have total freedom
- used with HTTP (REST and SOAP), TCP/IP, MSMQ and many more protocols
