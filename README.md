<div align="center">

## Hide & Disable Columns in DataGrid


</div>

### Description

This few lines of Code demonstrate how to Hide & Disable(lock) columns in Datagrid. Taking example from Northwind database it allows user to modify only ContactName,Phone and Fax columns.

Add this code in Form load event and modify the Connection string if required.

also add Imports System.Data.SqlClient in your code.

hope it helps you.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Syed](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/syed.md)
**Level**          |Beginner
**User Rating**    |4.2 (25 globes from 6 users)
**Compatibility**  |VB\.NET
**Category**       |[Databases](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/databases__10-5.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/syed-hide-disable-columns-in-datagrid__10-624/archive/master.zip)





### Source Code

```
Dim CN As New SqlConnection("server=(local);Database=Northwind;User ID=sa;password=;")
 CN.Open()
 Dim DA As New SqlDataAdapter("Select CustomerID, CompanyName, ContactName, Phone, Fax from Customers order by 1", CN)
 Dim DS As New DataSet()
 'DA.FillSchema(DS, SchemaType.Source, "Cust")
 DA.Fill(DS, "Cust")
 DS.Tables("Cust").Columns("CustomerID").ColumnMapping = MappingType.Hidden
 DS.Tables("Cust").Columns("CompanyName").ReadOnly = True
 DataGrid1.SetDataBinding(DS, "Cust")
```

