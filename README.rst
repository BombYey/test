===
SQL
===

Learning the Structured Query Language (SQL) requires practice -- it's no
different than learning any other programming language. This programming
exercise (PEX) offers an opportunity to practice various types of SQL queries.

Expected duration
  8--10 hours

Learning Objectives
===================

* Use SQL to query a database

Help Policy
===========

Authorized Resources
  Any, except posted solutions

Notes
  Never copy another person's work and submit it as your own

  Do not jointly work on this homework, but you may ask classmates questions
  about SQL syntax

  You must document all help received from all sources, including the
  instructor and instructor-provided course material (including your textbook),
  *except* for the following:

  * Resources related to SQL syntax (e.g., `PostgreSQL's reference for SQL
    commands`_)

.. _`PostgreSQL's reference for SQL commands`: http://bit.do/frGDF

Instructions
============

If the ConstructCo and LargeCo databases don't already exist in your PostgreSQL
cluster, create them and load the corresponding files to populate the data for
this assignment. Both files are in the Git repository.

The exercises are adapted from *Database Systems: Design, Implementation, &
Management* (Coronel and Morris 2017). Modify the file in the ``src`` directory
that corresponds to each query. For example, write the query for the first
exercise in the file ``src/01.sql``. The SQL comment that appears at the
beginning of the file is for your convenience and may remain in the file. Do
*not* modify any files in the ``test`` directory; doing so could prevent the
automated tests from running correctly.

ConstructCo
-----------

The ConstructCo database stores data for a consulting company that tracks all
charges to projects. The charges are based on the hours each employee works on
each project.

1. Write the SQL code that will create the table structure for a table named
   EMP_1. This table is a subset of the EMPLOYEE table. The basic EMP_1 table
   structure is summarized in the following table. Note that JOB_CODE is a
   foreign key to JOB. (Problem 7.1)

   +------------------------+------------------+
   | Attribute (Field) Name | Data Declaration |
   +========================+==================+
   | EMP_NUM                | INTEGER          |
   +------------------------+------------------+
   | EMP_LNAME              | VARCHAR(15)      |
   +------------------------+------------------+
   | EMP_FNAME              | VARCHAR(15)      |
   +------------------------+------------------+
   | EMP_INITIAL            | CHAR(1)          |
   +------------------------+------------------+
   | EMP_HIREDATE           | DATE             |
   +------------------------+------------------+
   | JOB_CODE               | INTEGER          |
   +------------------------+------------------+

2. Having created the table structure in the prior problem, write the SQL code
   to enter the first two rows for the following table. (Problem 7.2)

   +---------+------------+-----------+-------------+--------------+----------+
   | EMP_NUM | EMP_LNAME  | EMP_FNAME | EMP_INITIAL | EMP_HIREDATE | JOB_CODE |
   +=========+============+===========+=============+==============+==========+
   | 101     | News       | John      | G           | 2000-11-08   | 502      |
   +---------+------------+-----------+-------------+--------------+----------+
   | 102     | Senior     | David     | H           | 1989-07-12   | 501      |
   +---------+------------+-----------+-------------+--------------+----------+
   | 103     | Arbough    | June      | E           | 1995-12-01   | 500      |
   +---------+------------+-----------+-------------+--------------+----------+
   | 104     | Ramoras    | Anne      | K           | 1987-11-15   | 501      |
   +---------+------------+-----------+-------------+--------------+----------+
   | 105     | Johnson    | Alice     | K           | 1993-02-01   | 502      |
   +---------+------------+-----------+-------------+--------------+----------+
   | 106     | Smithfield | William   |             | 2004-06-22   | 500      |
   +---------+------------+-----------+-------------+--------------+----------+
   | 107     | Alonzo     | Maria     | D           | 1993-10-10   | 500      |
   +---------+------------+-----------+-------------+--------------+----------+
   | 108     | Washington | Ralph     | B           | 1991-07-22   | 501      |
   +---------+------------+-----------+-------------+--------------+----------+
   | 109     | Smith      | Larry     | W           | 1997-07-18   | 501      |
   +---------+------------+-----------+-------------+--------------+----------+

3. Assuming that the data shown in the EMP_1 table have been entered (see prior
   table), write the SQL code that will list all attributes for a job code of
   502. Sort the results by employee number in ascending order. (Problem 7.3)
4. Write SQL code to change the job code to 501 for the person whose employee
   number (EMP_NUM) is 107. (Problem 7.4)
5. Write the SQL code to delete the row for William Smithfield, who was hired
   on June 22, 2004, and whose job code is 500. Hint: Use logical operators to
   include all of the information given in this problem. (Problem 7.5)

LargeCo
-------

The LargeCo database stores data for a company that sells paint products. The
company tracks the sale of products to customers. The database keeps data on
customers (``LGCUSTOMER``), sales (``LGINVOICE``), products (``LGPRODUCT``),
which products are on which invoices (``LGLINE``), employees (``LGEMPLOYEE``),
the salary history of each employee (``LGSALARY_HISTORY``), departments
(``LGDEPARTMENT``), product brands (``LGBRAND``), vendors (``LGVENDOR``), and
which vendors supply each product (``LGSUPPLIES``). Some of the tables contain
only a few rows of data, while other tables are quite large; for examples,
there are only eight departments, but more than 3300 invoices containing over
11000 invoice lines.

6.  Write a query to display the SKU (stock keeping unit), description, type,
    base, category, and price for all products that have a PROD_BASE of water
    and a PROD_CATEGORY of sealer. (Problem 7.45)

    +----------+----------+-----------+-----------+----------+------------+
    | PROD_SKU | PROD_DES | PROD_TYPE | PROD_BASE | PROD_CAT | PROD_PRICE |
    |          | CRIPT    |           |           | EGORY    |            |
    +==========+==========+===========+===========+==========+============+
    | 1403-TUY | Sealer,  | Interior  | Water     | Sealer   |      42.99 |
    |          | Water Ba |           |           |          |            |
    |          | sed, for |           |           |          |            |
    |          | Concrete |           |           |          |            |
    |          | Floors   |           |           |          |            |
    +----------+----------+-----------+-----------+----------+------------+

7.  Write a query to display the first name, last name, and email address of
    employees hired from January 1, 2003, to December 31, 2012. Sort the output
    by last name and then by first name. (Problem 7.46)

    +-----------+-----------+-----------------------------+
    | EMP_FNAME | EMP_LNAME | EMP_EMAIL                   |
    +===========+===========+=============================+
    | Sue       | Ash       | s.ash98@lgcompany.com       |
    +-----------+-----------+-----------------------------+
    | Alida     | Blackwell | a.blackwell99@lgcompany.com |
    +-----------+-----------+-----------------------------+
    | Phoebe    | Bledsoe   | p.bledso99@lgcompany.com    |
    +-----------+-----------+-----------------------------+
    | Valarie   | Bledsoe   | v.bledso99@lgcompany.com    |
    +-----------+-----------+-----------------------------+
    | Wilford   | Burgos    | w.burgos6@lgcompany.com     |
    +-----------+-----------+-----------------------------+
    | Kasey     | Cash      | k.cash0@lgcompany.com       |
    +-----------+-----------+-----------------------------+
    | Danica    | Castle    | c.danica99@lgcompany.com    |
    +-----------+-----------+-----------------------------+
    | Doug      | Caudill   | c.doug0@lgcompany.com       |
    +-----------+-----------+-----------------------------+
    | Lucio     | Caudill   | l.caudil4@lgcompany.com     |
    +-----------+-----------+-----------------------------+
    | Hannah    | Coleman   | h.colema7@lgcompany.com     |
    +-----------+-----------+-----------------------------+
    | Phillis   | Conklin   | p.conkli4@lgcompany.com     |
    +-----------+-----------+-----------------------------+
    | Lee       | Connor    | l.connor99@lgcompany.com    |
    +-----------+-----------+-----------------------------+

8.  Write a query to display the first name, last name, phone number, title,
    and department number of employees who work in department 300 or have the
    title "CLERK I." Sort the output by last name and then by first name.
    (Problem 7.47)

    +-----------+-----------+-----------+-----------------------+----------+
    | EMP_FNAME | EMP_LNAME | EMP_PHONE | EMP_TITLE             | DEPT_NUM |
    +===========+===========+===========+=======================+==========+
    | Lavina    | Acevedo   | 862-6787  | Associate             | 300      |
    +-----------+-----------+-----------+-----------------------+----------+
    | Lauren    | Avery     | 550-2270  | Senior Associate      | 300      |
    +-----------+-----------+-----------+-----------------------+----------+
    | Rosalba   | Baker     | 632-8197  | Associate             | 300      |
    +-----------+-----------+-----------+-----------------------+----------+
    | Fern      | Carpenter | 735-4820  | Purchasing Specialist | 300      |
    +-----------+-----------+-----------+-----------------------+----------+
    | LeeAnn    | Clinton   | 616-9615  | Clerk I               | 600      |
    +-----------+-----------+-----------+-----------------------+----------+
    | Tanika    | Crane     | 449-6336  | Purchasing Specialist | 300      |
    +-----------+-----------+-----------+-----------------------+----------+
    | Sammy     | Diggs     | 525-2101  | Senior Associate      | 300      |
    +-----------+-----------+-----------+-----------------------+----------+
    | Lana      | Dowdy     | 471-8795  | Senior Associate      | 300      |
    +-----------+-----------+-----------+-----------------------+----------+
    | Stephanie | Dunlap    | 618-8203  | Buyer - Raw Materials | 300      |
    +-----------+-----------+-----------+-----------------------+----------+
    | Hal       | Fisher    | 676-3662  | Senior Associate      | 300      |
    +-----------+-----------+-----------+-----------------------+----------+
    | Lindsay   | Good      | 337-9570  | Clerk I               | 600      |
    +-----------+-----------+-----------+-----------------------+----------+
    | LeeAnn    | Horn      | 828-4361  | Senior Associate      | 300      |
    +-----------+-----------+-----------+-----------------------+----------+

9.  Write a query to display the employee number, last name, first name, salary
    "from" date, salary end date, and salary amount for employees 83731, 83745,
    and 84039. Sort the output by employee number and salary "from" date.
    (Problem 7.48)

    +---------+-----------+-----------+-----------+-----------+------------+
    | EMP_NUM | EMP_LNAME | EMP_FNAME | SAL_FROM  | SAL_END   | SAL_AMOUNT |
    +=========+===========+===========+===========+===========+============+
    | 83731   | Vargas    | Sheron    | 7/15/2012 | 7/14/2013 | 43740      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 83731   | Vargas    | Sheron    | 7/15/2013 | 7/13/2014 | 48110      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 83731   | Vargas    | Sheron    | 7/14/2014 | 7/14/2015 | 49550      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 83731   | Vargas    | Sheron    | 7/15/2015 |           | 51040      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 83745   | Spicer    | Dwain     | 8/2/2009  | 8/1/2010  | 56020      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 83745   | Spicer    | Dwain     | 8/2/2010  | 8/2/2011  | 57700      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 83745   | Spicer    | Dwain     | 8/3/2011  | 8/1/2012  | 63470      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 83745   | Spicer    | Dwain     | 8/2/2012  | 8/1/2013  | 68550      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 83745   | Spicer    | Dwain     | 8/1/2013  | 7/31/2014 | 71980      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 83745   | Spicer    | Dwain     | 8/1/2014  | 8/1/2015  | 74140      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 83745   | Spicer    | Dwain     | 8/2/2015  |           | 76360      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 84039   | Coleman   | Hannah    | 6/28/2012 | 6/27/2013 | 47380      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 84039   | Coleman   | Hannah    | 6/27/2013 | 6/26/2014 | 51170      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 84039   | Coleman   | Hannah    | 6/27/2014 | 6/27/2015 | 52700      |
    +---------+-----------+-----------+-----------+-----------+------------+
    | 84039   | Coleman   | Hannah    | 6/28/2015 |           | 54280      |
    +---------+-----------+-----------+-----------+-----------+------------+

10. Write a query to display the first name, last name, street, city, state,
    and zip code of any customer who purchased a Foresters Best brand top coat
    between July 15, 2015, and July 31, 2015. If a customer purchased more than
    one such product, display the customer's information only once in the
    output. Sort the output by state, last name, and then first name. (Problem
    7.49)

    +-----------+-----------+-----------+-----------+-----------+-----------+
    | CUST_FNAM | CUST_LNAM | CUST_STRE | CUST_CITY | CUST_STAT | CUST_ZIP  |
    | E         | E         | ET        |           | E         |           |
    +===========+===========+===========+===========+===========+===========+
    | Lupe      | Sanitana  | 1292 West | Phenix    | AL        | 36867     |
    |           |           | 70th      | City      |           |           |
    |           |           | Place     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Hollis    | Stiles    | 1493      | Snow Hill | AL        | 36778     |
    |           |           | Dolly     |           |           |           |
    |           |           | Madison   |           |           |           |
    |           |           | Circle    |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Lisette   | Whittaker | 339       | Montgomer | AL        | 36197     |
    |           |           | Horthpark | y         |           |           |
    |           |           | Drive     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Deadndre  | Jamison   | 1571      | Miami     | FL        | 33169     |
    |           |           | Hanes     |           |           |           |
    |           |           | Street    |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Cathleen  | Whitman   | 1712      | Marshallv | GA        | 31057     |
    |           |           | Northfiel | ille      |           |           |
    |           |           | d         |           |           |           |
    |           |           | Drive     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Sherie    | Stover    | 640       | Parksvill | KY        | 40464     |
    |           |           | Mountain  | e         |           |           |
    |           |           | View      |           |           |           |
    |           |           | Drive     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Bryce     | Hogan     | 1860      | Newbury   | MA        | 01951     |
    |           |           | Imlach    |           |           |           |
    |           |           | Drive     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Shelby    | Salas     | 486       | North     | MA        | 02568     |
    |           |           | Susitna   | Tisbury   |           |           |
    |           |           | View      |           |           |           |
    |           |           | Court     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Jermaine  | Hancock   | 1627      | Ellicott  | MD        | 21041     |
    |           |           | Sunders   | City      |           |           |
    |           |           | Road      |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Whitney   | Whitfield | 1259      | Phippsbur | ME        | 04567     |
    |           |           | Rhone     | g         |           |           |
    |           |           | Street    |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Monroe    | Allison   | 272       | Kalamazoo | MI        | 49002     |
    |           |           | Schodde   |           |           |           |
    |           |           | Street    |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Darleen   | Parra     | 561       | Madison   | MS        | 39130     |
    |           |           | Collie    |           |           |           |
    |           |           | Hill Way  |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Clinton   | Aguirre   | 1651      | Franklinv | NC        | 27248     |
    |           |           | Vanguard  | ille      |           |           |
    |           |           | Drive     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Tommie    | Palmer    | 933       | Arapahoe  | NC        | 28510     |
    |           |           | Elcadore  |           |           |           |
    |           |           | Circle    |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Jefferey  | McBride   | 1043      | Glenwood  | NJ        | 07418     |
    |           |           | Rockridge |           |           |           |
    |           |           | Drive     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Sidney    | Garza     | 772       | Fair      | NY        | 11706     |
    |           |           | Sheppard  | Harbor    |           |           |
    |           |           | Drive     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Tamela    | Guidry    | 1873      | Brooklyn  | NY        | 11252     |
    |           |           | Baxter    |           |           |           |
    |           |           | Road      |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Karen     | Levine    | 1534      | Cincinnat | OH        | 45218     |
    |           |           | Palmer    | i         |           |           |
    |           |           | Court     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Stephenie | McKenzie  | 1039      | Wilkes    | PA        | 18763     |
    |           |           | Delaware  | Barre     |           |           |
    |           |           | Place     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Lan       | Nichols   | 367       | Pittsburg | PA        | 15262     |
    |           |           | Lakeview  | h         |           |           |
    |           |           | Drive     |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Kasey     | Sosa      | 975 West  | Kinzer    | PA        | 17535     |
    |           |           | 96th      |           |           |           |
    |           |           | Avenue    |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Shelby    | Thayer    | 1634      | Bordeaux  | SC        | 29835     |
    |           |           | Ruane     |           |           |           |
    |           |           | Road      |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Wilson    | Bell      | 1127      | Louisvill | TN        | 37777     |
    |           |           | Cunningha | e         |           |           |
    |           |           | m         |           |           |           |
    |           |           | Street    |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Renate    | Ladd      | 652 Lewis | Crystal   | VA        | 22202     |
    |           |           | Street    | City      |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+
    | Melonie   | Jimenez   | 848       | East      | VT        | 05443     |
    |           |           | Downey    | Monkton   |           |           |
    |           |           | Finch     |           |           |           |
    |           |           | Lane      |           |           |           |
    +-----------+-----------+-----------+-----------+-----------+-----------+

11. Write a query to display the employee number, last name, email address,
    title, and department name of each employee whose job title ends in the
    word "ASSOCIATE." Sort the output by department name, employee title, and
    employee number. (Problem 7.50)

    +---------+-----------+--------------------------+-----------+------------------+
    | EMP_NUM | EMP_LNAME | EMP_EMAIL                | EMP_TITLE | DEPT_NAME        |
    +=========+===========+==========================+===========+==================+
    | 83378   | Dunham    | f.dunham5@hgcompany.com  | Associate | Accounting       |
    +---------+-----------+--------------------------+-----------+------------------+
    | 83517   | Albright  | so.albri96@lgcompany.com | Associate | Accounting       |
    +---------+-----------+--------------------------+-----------+------------------+
    | 83538   | Rollins   | m.rollin99@lgcompany.com | Associate | Accounting       |
    +---------+-----------+--------------------------+-----------+------------------+
    | 83661   | Finn      | d.finn87@lgcompany.com   | Associate | Accounting       |
    +---------+-----------+--------------------------+-----------+------------------+
    | 84386   | Rivera    | d.rivera76@lgcompany.com | Associate | Accounting       |
    +---------+-----------+--------------------------+-----------+------------------+
    | 84526   | Lassiter  | f.lassit8@lgcompany.com  | Associate | Accounting       |
    +---------+-----------+--------------------------+-----------+------------------+
    | 83341   | Cortez    | c.cortez85@lgcompany.com | Associate | Customer Service |
    +---------+-----------+--------------------------+-----------+------------------+
    | 83415   | Whalen    | c.whalen5@lgcompany.com  | Associate | Customer Service |
    +---------+-----------+--------------------------+-----------+------------------+
    | 83451   | Ellis     | r.ellis81@lgcompany.com  | Associate | Customer Service |
    +---------+-----------+--------------------------+-----------+------------------+
    | 83465   | Trujillo  | h.trujil10@lgcompany.com | Associate | Customer Service |
    +---------+-----------+--------------------------+-----------+------------------+
    | 83534   | Nadeau    | b.nadeau2@lgcompany.com  | Associate | Customer Service |
    +---------+-----------+--------------------------+-----------+------------------+
    | 83545   | Taylor    | j.taylor86@lgcompany.com | Associate | Customer Service |
    +---------+-----------+--------------------------+-----------+------------------+

    (12 of 168 records shown)

12. Write a query to display a brand name and the number of products of that
    brand that are in the database. Sort the output by the brand name. (Problem
    7.51)

    +-------------------+-------------+
    | BRAND_NAME        | NUMPRODUCTS |
    +===================+=============+
    | Binder Prime      | 27          |
    +-------------------+-------------+
    | Busters           | 25          |
    +-------------------+-------------+
    | Foresters Best    | 15          |
    +-------------------+-------------+
    | Home Comfort      | 36          |
    +-------------------+-------------+
    | Le Mode           | 36          |
    +-------------------+-------------+
    | Long Haul         | 41          |
    +-------------------+-------------+
    | Olde Tyme Quality | 27          |
    +-------------------+-------------+
    | Stuttenfurst      | 27          |
    +-------------------+-------------+
    | Valu-Matte        | 18          |
    +-------------------+-------------+

13. Write a query to display the number of products in each category that have
    a water base. Sort the results by product category. (Problem 7.52)

    +---------------+-------------+
    | PROD_CATEGORY | NUMPRODUCTS |
    +===============+=============+
    | Cleaner       | 2           |
    +---------------+-------------+
    | Filler        | 2           |
    +---------------+-------------+
    | Primer        | 16          |
    +---------------+-------------+
    | Sealer        | 1           |
    +---------------+-------------+
    | Top Coat      | 81          |
    +---------------+-------------+

14. Write a query to display the number of products within each base and type
    combination. Sort the results by product base and type. (Problem 7.53)

    +-----------+-----------+-------------+
    | PROD_BASE | PROD_TYPE | NUMPRODUCTS |
    +===========+===========+=============+
    | Solvent   | Exterior  | 67          |
    +-----------+-----------+-------------+
    | Solvent   | Interior  | 83          |
    +-----------+-----------+-------------+
    | Water     | Exterior  | 39          |
    +-----------+-----------+-------------+
    | Water     | Interior  | 63          |
    +-----------+-----------+-------------+

15. Write a query to display the total inventory -- that is, the sum of all
    products on hand for each brand ID. Sort the output by brand ID in
    descending order. (Problem 7.54)

    +----------+----------------+
    | BRAND_ID | TOTALINVENTORY |
    +==========+================+
    | 35       | 2431           |
    +----------+----------------+
    | 33       | 2158           |
    +----------+----------------+
    | 31       | 1117           |
    +----------+----------------+
    | 30       | 3012           |
    +----------+----------------+
    | 29       | 1735           |
    +----------+----------------+
    | 28       | 2200           |
    +----------+----------------+
    | 27       | 2596           |
    +----------+----------------+
    | 25       | 1829           |
    +----------+----------------+
    | 23       | 1293           |
    +----------+----------------+

16. Write a query to display the employee number, first name, last name, and
    largest salary amount for each employee in department 200. Sort the output
    by largest salary in descending order and employee number in ascending
    order. (Problem 7.57)

    +---------+-----------+-----------+---------------+
    | EMP_NUM | EMP_FNAME | EMP_LNAME | LARGESTSALARY |
    +=========+===========+===========+===============+
    | 83509   | Franklyn  | Stover    | 210000        |
    +---------+-----------+-----------+---------------+
    | 83705   | Jose      | Barr      | 147000        |
    +---------+-----------+-----------+---------------+
    | 83537   | Cleo      | English   | 136000        |
    +---------+-----------+-----------+---------------+
    | 83565   | Lourdes   | Abernathy | 133000        |
    +---------+-----------+-----------+---------------+
    | 83593   | Rosannie  | Nash      | 129000        |
    +---------+-----------+-----------+---------------+
    | 83621   | Fonda     | Gonzalez  | 126000        |
    +---------+-----------+-----------+---------------+
    | 83649   | Delma     | Jacob     | 123000        |
    +---------+-----------+-----------+---------------+
    | 83677   | Herb      | Manning   | 120000        |
    +---------+-----------+-----------+---------------+
    | 83936   | Bradford  | Bray      | 117000        |
    +---------+-----------+-----------+---------------+
    | 83734   | Inez      | Rocha     | 112000        |
    +---------+-----------+-----------+---------------+
    | 84049   | Lane      | Brandon   | 110000        |
    +---------+-----------+-----------+---------------+
    | 83763   | Jamie     | Felton    | 107000        |
    +---------+-----------+-----------+---------------+

17. Write a query to display the customer code, first name, last name, and sum
    of all invoice totals for customers with cumulative invoice totals greater
    than $1,500. Sort the output by the sum of invoice totals in descending
    order. (Problem 7.58)

    +-----------+------------+------------+--------------+
    | CUST_CODE | CUST_FNAME | CUST_LNAME | TOTALINVOICE |
    +===========+============+============+==============+
    | 215       | Charmaine  | Bryan      | 3134.15      |
    +-----------+------------+------------+--------------+
    | 98        | Valentin   | Marino     | 3052.46      |
    +-----------+------------+------------+--------------+
    | 152       | Lisette    | Whittaker  | 3042.78      |
    +-----------+------------+------------+--------------+
    | 117       | Karon      | Mta        | 3009.63      |
    +-----------+------------+------------+--------------+
    | 97        | Erwin      | Anderson   | 2895.49      |
    +-----------+------------+------------+--------------+
    | 112       | Lan        | Nichols    | 2867.14      |
    +-----------+------------+------------+--------------+
    | 118       | Jessie     | Hicks      | 2786.55      |
    +-----------+------------+------------+--------------+
    | 220       | Abraham    | Platt      | 2187.26      |
    +-----------+------------+------------+--------------+
    | 103       | Corrina    | Gifford    | 2122.07      |
    +-----------+------------+------------+--------------+
    | 302       | Shirlene   | Fitch      | 2046.31      |
    +-----------+------------+------------+--------------+
    | 173       | Ingrid     | Hardy      | 2040.31      |
    +-----------+------------+------------+--------------+
    | 132       | Janis      | Dubois     | 2014.62      |
    +-----------+------------+------------+--------------+

18. Write a query to display the employee number, last name, first name, and
    sum of invoice totals for all employees who completed an invoice. Sort the
    output by employee last name and then by first name. (Problem 7.61)

    +---------+-----------+-----------+---------------+
    | EMP_NUM | EMP_LNAME | EMP_FNAME | TOTALINVOICES |
    +=========+===========+===========+===============+
    | 83565   | Abernathy | Lourdes   | 19158.54      |
    +---------+-----------+-----------+---------------+
    | 83792   | Andersen  | Wally     | 20627.47      |
    +---------+-----------+-----------+---------------+
    | 83705   | Barr      | Jose      | 22098.88      |
    +---------+-----------+-----------+---------------+
    | 84049   | Brandon   | Lane      | 20683.06      |
    +---------+-----------+-----------+---------------+
    | 83936   | Bray      | Bradford  | 21139.94      |
    +---------+-----------+-----------+---------------+
    | 84248   | Castle    | Danica    | 17700.42      |
    +---------+-----------+-----------+---------------+
    | 84420   | Caudill   | Doug      | 11308.21      |
    +---------+-----------+-----------+---------------+
    | 83393   | Cortes    | Sang      | 17436.88      |
    +---------+-----------+-----------+---------------+
    | 84021   | Dickinson | Jarod     | 20437.35      |
    +---------+-----------+-----------+---------------+
    | 84163   | Easley    | Gwen      | 24813.26      |
    +---------+-----------+-----------+---------------+
    | 83537   | English   | Cleo      | 18883.13      |
    +---------+-----------+-----------+---------------+
    | 84078   | Erwin     | Diego     | 23839.85      |
    +---------+-----------+-----------+---------------+

19. Write a query to display the brand ID, brand name, brand type, and average
    price of products for the brand that has the largest average product price.
    (Problem 7.63)

    Hint: Use PostgreSQL's `round function`_ to round a numeric data type to a
    specified number of decimal places. For example, ``round (42.4382, 2)``
    returns 42.44.

    +----------+------------+------------+----------+
    | BRAND_ID | BRAND_NAME | BRAND_TYPE | AVGPRICE |
    +==========+============+============+==========+
    | 29       | Busters    | VALUE      | 22.59    |
    +----------+------------+------------+----------+

.. _`round function`: http://bit.do/frGb6

20. Write a query to display the invoice number, line numbers, product SKUs,
    product descriptions, and brand ID for sales of sealer and top coat
    products of the same brand on the same invoice with the sealer information
    appearing before top coat. Sort the results by invoice number, sealer line
    number, and top coat line number in ascending order. (Problem 8.22)

    +---------+----------+----------+----------+----------+----------+
    | INV_NUM | LINE_NUM | PROD_SKU | LINE_NUM | PROD_SKU | BRAND_ID |
    +=========+==========+==========+==========+==========+==========+
    | 115     | 2        | 5140-RTG | 1        | 1203-AIS | 35       |
    +---------+----------+----------+----------+----------+----------+
    | 118     | 2        | 5140-RTG | 5        | 5046-TTC | 35       |
    +---------+----------+----------+----------+----------+----------+
    | 135     | 5        | 3036-PCT | 2        | 1074-VVJ | 25       |
    +---------+----------+----------+----------+----------+----------+
    | 153     | 2        | 3701-YAW | 1        | 3955-NWD | 30       |
    +---------+----------+----------+----------+----------+----------+
    | 222     | 1        | 1336-FVM | 3        | 8199-YRF | 33       |
    +---------+----------+----------+----------+----------+----------+
    | 234     | 4        | 5728-ZPO | 3        | 9272-LTP | 27       |
    +---------+----------+----------+----------+----------+----------+
    | 234     | 4        | 5728-JPO | 2        | 9126-PWF | 27       |
    +---------+----------+----------+----------+----------+----------+
    | 243     | 1        | 4072-SWV | 3        | 5653-RTU | 23       |
    +---------+----------+----------+----------+----------+----------+
    | 287     | 1        | 8894-LUR | 5        | 9838-FUF | 27       |
    +---------+----------+----------+----------+----------+----------+
    | 333     | 1        | 3701-YAW | 6        | 2584-CIJ | 30       |
    +---------+----------+----------+----------+----------+----------+
    | 333     | 1        | 3701-YAW | 5        | 4784-SLU | 30       |
    +---------+----------+----------+----------+----------+----------+
    | 369     | 2        | 1403-TUY | 1        | 8726-ZNM | 29       |
    +---------+----------+----------+----------+----------+----------+

    (Note: This table omits the product descriptions for brevity, but they
    should be included in the actual query result. In addition only 12 of 130
    are shown.)

21. The Binder Prime Company wants to recognize the employee who sold the most
    of its products during a specified period. Write a query to display the
    employee number, employee first name, employee last name, email address,
    and total units sold for the employee who sold the most Binder Prime
    products between November 1, 2015, and December 5, 2015. If there is a tie
    for most units sold, sort the output by employee last name. (Problem
    8.23)

    +---------+-----------+-----------+--------------------------+-------+
    | EMP_NUM | EMP_FNAME | EMP_LNAME | EMP_EMAIL                | TOTAL |
    +=========+===========+===========+==========================+=======+
    | 84134   | Rosalie   | Garlan    | g.rosali98@lgcompany.com | 23    |
    +---------+-----------+-----------+--------------------------+-------+
    | 83850   | Rusty     | Miles     | m.rusty95@lgcompany.com  | 23    |
    +---------+-----------+-----------+--------------------------+-------+

22. Write a query to display the customer code, first name, and last name of
    all customers who have had at least one invoice completed by employee 83649
    and at least one invoice completed by employee 83677. Sort the output by
    customer last name and then first name. (Problem 8.24)

    +-----------+------------+------------+
    | CUST_CODE | CUST_FNAME | CUST_LNAME |
    +===========+============+============+
    | 684       | Wendi      | Bean       |
    +-----------+------------+------------+
    | 340       | Marcia     | Burris     |
    +-----------+------------+------------+
    | 211       | Gerald     | Caudill    |
    +-----------+------------+------------+
    | 292       | Valarie    | Dillard    |
    +-----------+------------+------------+
    | 293       | Cair       | Erickson   |
    +-----------+------------+------------+
    | 416       | Tatiana    | Howe       |
    +-----------+------------+------------+
    | 996       | Ezra       | Lyon       |
    +-----------+------------+------------+
    | 98        | Valentin   | Marino     |
    +-----------+------------+------------+
    | 121       | Peter      | Small      |
    +-----------+------------+------------+
    | 1157      | Lucio      | Staley     |
    +-----------+------------+------------+
    | 617       | Cesar      | Talley     |
    +-----------+------------+------------+
    | 457       | Shauna     | Werner     |
    +-----------+------------+------------+
    | 131       | Sal        | Whaley     |
    +-----------+------------+------------+

23. LargeCo is planning a new promotion in Alabama (AL) and wants to know about
    the largest purchases made by customers in that state. Write a query to
    display the customer code, customer first name, last name, full address,
    invoice date, and invoice total of the largest purchase made by each
    customer in Alabama. Be certain to include any customers in Alabama who
    have never made a purchase; their invoice dates should be ``NULL`` and the
    invoice totals should display as 0.00. Order the results by the customers'
    last and first names. (Problem 8.25)

    Hint: Use the `COALESCE function`_ to replace ``NULL`` with another value,
    such as 0.00.

    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | CUST | CUST  | CUST  | CUST  | CUST | CUST  | CUS | INV | LARGEST  |
    | _COD | _FNAM | _LNAM | _STRE | _CIT | _STAT | T_Z | _DA | INVOICE  |
    | E    | E     | E     | ET    | Y    | E     | IP  | TE  |          |
    +======+=======+=======+=======+======+=======+=====+=====+==========+
    | 903  | Robin | Addis | 323   | Mobi | AL    | 366 | 8/2 | 230.63   |
    |      |       | on    | Loret | le   |       | 93  | 6/2 |          |
    |      |       |       | ta    |      |       |     | 015 |          |
    |      |       |       | Place |      |       |     |     |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 643  | Nina  | Allen | 680   | Robe | AL    | 365 | 6/2 | 11.99    |
    |      |       |       | Red   | rtsd |       | 74  | 1/2 |          |
    |      |       |       | Talon | ale  |       |     | 015 |          |
    |      |       |       | Drive |      |       |     |     |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 295  | Dorot | Austi | 829   | Diam | AL    | 366 | 4/2 | 589.75   |
    |      | hy    | n     | Big   | ond  |       | 14  | 4/2 |          |
    |      |       |       | Bend  | Sham |       |     | 015 |          |
    |      |       |       | Loop  | rock |       |     |     |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 393  | Foste | Berna | 1299  | Birm | AL    | 352 |     | 0.00     |
    |      | r     | l     | East  | ingh |       | 80  |     |          |
    |      |       |       | 3rd   | am   |       |     |     |          |
    |      |       |       | Avenu |      |       |     |     |          |
    |      |       |       | e     |      |       |     |     |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 853  | Gaylo | Bolto | 1069  | Mont | AL    | 361 | 11/ | 372.68   |
    |      | rd    | n     | Lugen | gome |       | 31  | 25/ |          |
    |      |       |       | e     | ry   |       |     | 201 |          |
    |      |       |       | Lane  |      |       |     | 5   |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 925  | Alana | Booke | 1874  | Mccu | AL    | 365 | 12/ | 208.85   |
    |      |       | r     | I     | llou |       | 02  | 12/ |          |
    |      |       |       | Stree | gh   |       |     | 201 |          |
    |      |       |       | t     |      |       |     | 5   |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 1248 | Lisa  | Brady | 491   | Daph | AL    | 365 | 12/ | 414.47   |
    |      |       |       | Lowla | ne   |       | 77  | 5/2 |          |
    |      |       |       | nd    |      |       |     | 015 |          |
    |      |       |       | Avenu |      |       |     |     |          |
    |      |       |       | e     |      |       |     |     |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 538  | Chiqu | Caldw | 1501  | Norm | AL    | 357 | 5/2 | 143.90   |
    |      | ita   | ell   | Brigg | al   |       | 62  | 6/2 |          |
    |      |       |       | s     |      |       |     | 015 |          |
    |      |       |       | Court |      |       |     |     |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 89   | Monic | Cantr | 697   | Loac | AL    | 368 | 3/3 | 516.58   |
    |      | a     | ell   | Adak  | hapo |       | 65  | 1/2 |          |
    |      |       |       | Circl | ka   |       |     | 015 |          |
    |      |       |       | e     |      |       |     |     |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 1233 | Natha | Churc | 1802  | Napi | AL    | 363 | 11/ | 160.96   |
    |      | lie   | h     | Snowy | ar   |       | 03  | 24/ |          |
    |      |       |       | Owl   | Fiel |       |     | 201 |          |
    |      |       |       | Circl | d    |       |     | 5   |          |
    |      |       |       | e     |      |       |     |     |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 304  | Gertr | Conno | 1042  | Geor | AL    | 360 | 12/ | 376.32   |
    |      | ude   | rs    | Pleas | gian |       | 33  | 29/ |          |
    |      |       |       | ant   | a    |       |     | 201 |          |
    |      |       |       | Drive |      |       |     | 5   |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 1131 | Carma | Corne | 767   | Kill | AL    | 356 | 10/ | 265.12   |
    |      |       | tt    | Chisa | en   |       | 45  | 25/ |          |
    |      |       |       | na    |      |       |     | 201 |          |
    |      |       |       | Way   |      |       |     | 5   |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+
    | 1407 | Felic | Cruz  | 643   | Coal | AL    | 350 | 1/6 | 387.94   |
    |      | ia    |       | Turna | burg |       | 68  | /20 |          |
    |      |       |       | gain  |      |       |     | 16  |          |
    |      |       |       | Parkw |      |       |     |     |          |
    |      |       |       | ay    |      |       |     |     |          |
    +------+-------+-------+-------+------+-------+-----+-----+----------+

.. _`COALESCE function`: http://bit.do/frGao

24. One of the purchasing managers is interested in the impact of product
    prices on the sale of products of each brand. Write a query to display the
    brand name, brand type, average price of products of each brand, and total
    units sold of products of each brand. Even if a product has been sold more
    than once, its price should only be included once in the calculation of the
    average price. However, you must be careful because multiple products of
    the same brand can have the same price, and each of those products must be
    included in the calculation of the brand's average price. Be sure to round
    the average price to two decimal places. Sort the results in ascending
    order by the brand name. (Problem 8.26)

    +-------------------+------------+---------------+------------+
    | BRAND_NAME        | BRAND_TYPE | AVERAGE PRICE | UNITS SOLD |
    +===================+============+===============+============+
    | Binder Prime      | PREMIUM    | 16.12         | 3753       |
    +-------------------+------------+---------------+------------+
    | Busters           | VALUE      | 22.59         | 3727       |
    +-------------------+------------+---------------+------------+
    | Foresters Best    | VALUE      | 20.94         | 2086       |
    +-------------------+------------+---------------+------------+
    | Home Comfort      | CONTRACTOR | 21.80         | 4842       |
    +-------------------+------------+---------------+------------+
    | Le Mode           | PREMIUM    | 19.22         | 5284       |
    +-------------------+------------+---------------+------------+
    | Long Haul         | CONTRACTOR | 20.12         | 5728       |
    +-------------------+------------+---------------+------------+
    | Olde Tyme Quality | CONTRACTOR | 18.33         | 3614       |
    +-------------------+------------+---------------+------------+
    | Stuttenfurst      | CONTRACTOR | 16.47         | 3671       |
    +-------------------+------------+---------------+------------+
    | Valu-Matte        | VALUE      | 16.84         | 2485       |
    +-------------------+------------+---------------+------------+

25. The purchasing manager is still concerned about the impact of price on
    sales. Write a query to display the brand name, brand type, product SKU,
    product description, and price of any products that are not a premium
    brand, but that cost more than the most expensive premium brand products.
    (Problem 8.27)

    +-------------+-------------+----------+-----------------+-------------+
    | BRAND_NAME  | BRAND_TYPE  | PROD_SKU | PROD_DESCRIPT   | PROD_PRICE  |
    +=============+=============+==========+=================+=============+
    | Long Haul   | CONTRACTOR  | 1964-OUT | Fire Reistant   | 78.49       |
    |             |             |          | Top Coat, for   |             |
    |             |             |          | Interior Wood   |             |
    +-------------+-------------+----------+-----------------+-------------+

Submission
==========

Create an archive of your Git repository (you can use GitHub's "Clone or
download" button when viewing your repository for this purpose) and submit that
archive to Blackboard. Be sure to include your documentation statement as part
of the submission.

GitHub Classroom also tags the latest commit at the due date for the
assignment.

Grading
-------

The following grading rubric will be used for this assignment:

+---------------------------+-----------------+
|                           |     Points      |
+---------------------------+--------+--------+
| Description               |  Total | Earned |
+===========================+========+========+
| Queries (@ 4 points each) |    100 |        |
+---------------------------+--------+--------+

Each query is worth the same amount. No partial credit will be awarded for
queries that fail the automated tests unless you can prove that a test case
rejected valid input!

You are strongly encouraged to complete this assignment several days prior to
the due date so that you have time to resolve any failures for the automated
tests. If you have questions regarding how to interpret their output, do not
hesitate to ask the instructor.
