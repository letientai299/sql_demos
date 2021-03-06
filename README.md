# sql_demos - Brendan's repo for interesting SQL<div id="topOfVisibleArea"></div>

This project stores the SQL code for solutions to interesting problems I have looked at on my blog,
or elsewhere. It includes installation scripts with object creation and data setup, and scripts to
run the SQL on the included datasets.

The idea is that anyone with the pre-requisites should be able to reproduce my results within a few 
minutes of downloading the repo.

The installation scripts will create a common objects schema, bren, and a separate schema for each
problem, of which there are five at present. The SYS and bren objects are in the folder bren, with
the problem-specific scripts in a separate folder for each one.

Links to blog or other sources:

- knapsack<br />
<a href="http://aprogrammerwrites.eu/?p=560" target="_blank">A Simple SQL Solution for the Knapsack Problem (SKP-1)</a>, January 2013<br />
<a href="http://aprogrammerwrites.eu/?p=635" target="_blank">An SQL Solution for the Multiple Knapsack Problem (SKP-m)</a>, January 2013

- bal_num_part<br />
<a href="http://aprogrammerwrites.eu/?p=803" target="_blank">SQL for the Balanced Number Partitioning Problem</a>, May 2013

- fan_foot<br />
<a href="http://aprogrammerwrites.eu/?p=878" target="_blank">SQL for the Fantasy Football Knapsack Problem</a>, June 2013

- tsp<br />
<a href="http://aprogrammerwrites.eu/?p=896" target="_blank">SQL for the Travelling Salesman Problem</a>, July 2013

- shortest_path<br />
<a href="http://aprogrammerwrites.eu/?p=1391" target="_blank">SQL for Shortest Path Problems</a>, April 2015<br />
<a href="http://aprogrammerwrites.eu/?p=1415" target="_blank">SQL for Shortest Path Problems 2: A Branch and Bound Approach</a>, May 2015

Here is a summary article that embeds all of the above plus another couple of relevant articles: <a href="http://aprogrammerwrites.eu/?p=2232" target="_blank">Knapsacks and Networks in SQL</a>, December 2017

Pre-requisites
==============
In order to install this project you need to have SYS access to an Oracle database, minimum version
11.2, along with a suitable database server directory to use for loading data via external tables.

Install steps
=============
        
1. Update the logon script SYS.bat for your own credentials for the SYS schema
2. Update the logon scripts bren.bat, knapsack.bat, bal_num_part.bat, fan_foot.bat,
shortest_path.bat, tsp.bat with your own connect string
3. Update Install_SYS.sql with the name of an input directory on your database server that
can be used for external tables to read from, and place all the files in db_server_input there
4. Run Install_SYS.sql in SYS schema from SQL*Plus, or other SQL client, to set up the bren
common schema, and the problem-specific schemas
5. Run Install_bren.sql in bren schema to create the bren schema common objects
6. Run the install script for each schema to create the schema objects:
- knapsack:      Install_Knapsack.sql
- bal_num_part:  Install_Bal_Num_Part.sql
- fan_foot:      Install_Fan_Foot.sql
- tsp:           Install_TSP.sql
- shortest_path: Install_Shortest_Path.sql
7. Run Main_*.sql as desired in the specific schemas to run the SQL for the different datasets and
get execution plans and results logs. For example, for fan_foot: Main_Bra.sql and Main_Eng.sql are
the driving scripts

Video
=====
The installation is demonstrated in a short video (8 minutes). It doesn't cover the most recent schemas but the same pattern if followed for those. As it is 170MB in size I placed it in a
shared Microsoft One-Drive location:
https://1drv.ms/v/s!AtGOr6YOZ-yVh_1a6_g7XwX0TTBTgA