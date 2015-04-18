## MyWind

MySQL version of Microsoft Access 2010 Northwind sample database.

The Northwind database is an excellent tutorial schema for a 
small-business ERP, with customers, orders, inventory, purchasing, 
suppliers, shipping, employees, and single-entry accounting. However,
I wanted to experiment with the schema using [MySQL](http://www.mysql.com). 


## Files

* Model:
    * northwind.mwb (MySQL Workbench v6.2)
* EER Diagram:
    * northwind-erd.pdf
    * northwind-erd.png
* Structure:
    * northwind.sql
    * northwind-default-current-timestamp.sql (uses DEFAULT CURRENT TIMESTAMP, requires MySQL 5.6.5+)
* Data:
    * northwind-data.sql

## Creating MyWind

* Created Northwind.aacdb using MS Access 2010 (File > New > Sample Templates > Northwind > SaveAs)
* Converted Northwind.accdb to MySQL SQL using BullZip ["Access to MySQL"](http://www.bullzip.com).[1]
* Converted CamelCase identifiers to lower_case_with_underscore
* Replaced space and slash characters in identifiers with _underscores_
* Renamed primary key columns "id"
* Renamed foreign key columns "xxx_id" (e.g. "inventory_id")
* Changed record create and modified date columns to type DATETIME to avoid TIMESTAMP range (1997 - 2038 UTC) and other limitations
* Added foreign key relationships and created EER diagrams using MySQL Workbench

----
 [1]: BullZip *Access to MySQL* version 5.1.242. *Access to MySQL* "...may be used free of charge for non-commercial purposes.", http://www.bullzip.com, accessed 2014-01-08.
