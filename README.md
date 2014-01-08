northwind
=========

The Northwind demo database provided with Microsoft Access is an excellent tutorial schema for managing small business customers, orders, inventory, purchasing, suppliers, shipping, and employees. My problem was that I wanted to experiment with it using [MySQL](http://www.mysql.com) and the [Yii Framework](http://www.yiiframework.com).

Files
-----
* Model: northwind.mwb (MySQL Workbench v6.02)
* ERD: northwind-erd.pdf
* Structure 1: northwind-structure.sql
* Structure 2: northwind-structure-timestamp.sql (record create and modified columns use DEFAULT CURRENT_TIMESTAMP, requires MySQL 5.6.5+)
* Data: northwind-data.sql

Conversion Procedure
--------------------
* Northwind database template created using MS Access 2010 (MS Access 2010 > File > New > Sample Templates > Northwind > SaveAs)
* Convert Northwind.accdb to MySQL syntax using BullZip [Access to MySQL](http://www.bullzip.com) (version 5.1.242). [BullZip states Access to MySQL](http://www.bullzip.com/download.php) is "FREEWARE may be used free of charge for non-commercial purposes." (unfortunately it does not convert foreign key relationships though).
* Converted CamelCase identifiers to lower_case_with_underscore
* Replaced space and slash characters in identifiers with _underscores_
* Renamed primary key columns "id"
* Renamed foreign key columns "xxx_id" (e.g. "inventory_id")
* Changed record create and modified date columns to type DATETIME to avoid TIMESTAMP range (1997 - 2038 UTC) and other limitations
* Added foreign key relationships and created ERD using MySQL Workbench
