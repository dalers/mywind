## MyWind

MyWind - MySQL version of MS Northwind 2010 database (MS Access)

The Northwind demo database provided with Microsoft Access is an excellent schema for a small-business ERP, with customers, orders, inventory, purchasing, suppliers, shipping, employees, and single-entry accounting. I wanted to experiment with the schema using [MySQL](http://www.mysql.com) and the [Yii Framework](http://www.yiiframework.com).

## Files

* Model:
    * northwind.mwb (MySQL Workbench v6.2)
* EER Diagram:
    * northwind-erd.pdf
    * northwind-erd.png
* Structure:
    * northwind.sql
    * northwind-default-current-timestamp (row create/modify columns are DEFAULT CURRENT TIMESTAMP, requires MySQL 5.6.5+)
* Data:
    * northwind-data.sql

## Creating MyWind

* Create Northwind.aacdb using MS Access 2010 (File > New > Sample Templates > Northwind > SaveAs)
* Convert Northwind.accdb to MySQL SQL using BullZip ["Access to MySQL"](http://www.bullzip.com).[1]
* Converted CamelCase identifiers to lower_case_with_underscore
* Replace space and slash characters in identifiers with _underscores_
* Rename primary key columns "id"
* Rename foreign key columns "xxx_id" (e.g. "inventory_id")
* Change record create and modified date columns to type DATETIME to avoid TIMESTAMP range (1997 - 2038 UTC) and other limitations
* Add foreign key relationships and create EER diagram using MySQL Workbench

----
 [1]: BullZip *Access to MySQL* version 5.1.242. *Access to MySQL* "...may be used free of charge for non-commercial purposes.", http://www.bullzip.com, accessed 2014-01-08.
