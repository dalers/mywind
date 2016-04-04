## MyWind

MyWind is a MySQL version of the Microsoft Access 2010 *Northwind* sample database.

The Northwind database is an excellent tutorial schema for a 
small-business ERP, with customers, orders, inventory, purchasing, 
suppliers, shipping, employees, and single-entry accounting. However,
I wanted to experiment with the schema using [MySQL](http://www.mysql.com). 

The Northwind sample database provided with Microsoft Access is a tutorial schema for managing small business customers, orders, inventory, purchasing, suppliers, shipping, and employees. My problem was I wanted to experiment with the Northwind schema using [MySQL](http://www.mysql.com).

## WARNING

* northwind.mdb -> northwind-02.mdb (and other new/modifed files in this commit) may be the result of correcting or improving the ERD model where it relates to sales orders and shipping (as presumed by addition of northwind-02-sales-orders-and-shipping.png). Whoever walks this way, please figure this out and deal with it appropriately.

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

* Created Northwind.aacdb using MS Access 2010 (File > New > Sample Templates > Northwind > SaveAs).
* Created basic SQL equivalent of Northwind schema for MySQL using using BullZip ["Access to MySQL"](http://www.bullzip.com).[1]
* Replaced CamelCase identifier names with lower_case_with_underscore identifier names.
* Replaced " " (space) and "/" (forward slash) characters in identifiers with _underscores_.
* Renamed table primary keys "id".
* Renamed table foreign keys "xxx_id" (e.g. "inventory_id").
* Changed record-create and modify-date columns to type DATETIME (to avoid the 1997 - 2038 UTC date range restriction of TIMESTAMP, and also other limitations).
* Added foreign key relationships and created ERD using MySQL Workbench.
* Imported SQL into MySQL Workbench
    * Added foreign key relationships visually
    * Exported EER Diagrams

----
 [1]: BullZip *Access to MySQL* version 5.1.242. *Access to MySQL* "...may be used free of charge for non-commercial purposes.", http://www.bullzip.com, accessed 2014-01-08.
