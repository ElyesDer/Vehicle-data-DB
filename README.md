# Vehicule-data-DB
Vehicule data collection of over 28311 Models, +90 Makers manufactured between 1800 to 2017 in sql, json, and csv format.

- [Features](#features)
- [Getting Started](#Getting_Started)
- [Requirement](#Requirement)
- [Installing](#Installing)
- [Requirement](#requirement)
- [Installation](#installation)
- [Setup](#setup)
- [Running](#Running)
  - [List of Ferrari's made between 2000 and 2017](#q1)
  - [List of manufactures who produced cars between 2000 and 2017](#q2)
- [Extra](#Extra)
- [Acknowledgments](#Acknowledgments)

### Features<a name="features"></a>

Automobile manufacturers, models, version & production end data of 28 311 Car only.
SQL Database exported to JSON, CSV format.
Mysql Database contains one table with following columns :
```
# +------+-------+--------+---------------+------------------+
# | year | maker | model  | FULLMODELNAME | production end   |
# +------+-------+--------+---------------+------------------+
```

## Getting Started<a name="Getting_Started"></a>

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Requirement<a name="Requirement"></a>
* Mysql.
* Csv editor ( i.e : Excel ) for csv format.
* Json editor.

### Installing<a name="Installing"></a>
```
$ git clone https://github.com/WiildchiilD/Vehicule-data-DB.git
$ cd ./Vehicule-data-DB
```

##### Setting up Database

Mysql
```
$ mysql -uroot dbName < mysqldata.sql 
```

CSV
```
Open csvdata.csv in your favorite editor.
```

## Running<a name="Running"></a>

List of Ferrari's made between 2000 and 2016

```sql
mysql> SELECT `YEAR`,`MODEL`,`FULLMODELNAME` FROM `vehicule` 
WHERE `MAKER` ='ferrari' AND YEAR BETWEEN '2000' and '2017'

# +------+---------------------+-----------------------+
# | YEAR |	  MODEL            |	 FULLMODELNAME	     |
# +------+---------------------+-----------------------+
# | 2014 |  458 Speciale A     | 	4.5 V8 7AT (605 HP)	 |
# | 2013 |  458 Speciale       | 	4.5 V8 7AT (605 HP)	 |
# | 2009 |  458 Italia         | 	4.5 V8 7AT (570 HP)	 |
# | 2016 |  LaFerrari Aperta   | 	6.3 V12 7AT (963 HP) |	
# | 2011 |  458 Spider         | 	4.5 7AT (570 HP)	   |
# | 2014 |  California T       | 	3.8 V8 7AT (560 HP)	 |
# | 2015 |  488 GTB            | 	3.9 V8 7AT (670 HP)	 |
# | 2016 |  488 Spider         | 	3.9 V8 7AT (670 HP)	 |
# | 2015 |  F12tdf             | 	6.3 V12 7AT (780 HP) |	
# | 2016 |  GTC4Lusso          | 	6.3 V12 7AT (690 HP) |	
# | 2011 |  FF                 | 	6.3 V12 7AT (660 HP) |	
# | 2013 |  LaFerrari          | 	6.3 V12 7AT (963 HP) |	
# | 2002 |  Enzo               | 	6.0 V12 6AT (660 HP) |	
# | 2012 |  F149 California    | 	4.3 V8 7AT (490 HP)	 |
# | 2008 |  F149 California    | 	4.3 V8 6MT (460 HP)	 |
# | 2008 |  F149 California    | 	4.3 V8 7AT (460 HP)	 |
# | 2008 |  F149 California    | 	4.3 V8 7AT (490 HP)	 |
# | 2007 |  430 Scuderia       | 	4.3 V8 6AT (510 HP)	 | 
# | 2004 |  F430               | 	4.3 V8 6AT (490 HP)	 | 
# | 2004 |  F430               | 	4.3 V8 6MT (490 HP)	 | 
# | 2005 |  F430 Spider        | 	4.3 V8 6AT (490 HP)	 |
# | 2005 |  F430 Spider        | 	4.3 V8 6MT (490 HP)	 |
# | 2004 |  612 Scaglietti     | 	5.7 V12 6AT (540 HP) |	
# | 2004 |  612 Scaglietti     | 	5.7 V12 6MT (540 HP) |	
# | 2005 |  575 M Superamerica | 	5.7 V12 6AT (540 HP) |	
# +------+---------------------+-----------------------+
38 rows in set ( 0.0671 sec)
```
List of manufactures who produced cars between 2000 and 2017

```sql
SELECT COUNT(DISTINCT(`MAKER`)) AS manufacture_count FROM `vehicule` 
WHERE `YEAR` BETWEEN '2000' and '2017'
# +---------------------------+
# | manufacture_count         |
# +---------------------------+
# |                        96 |
# +---------------------------+
# 1 row in set (0.00 sec)

ETC..
```

# EXTRA<a name="EXTRA"></a>
If you need more data specification per vehicule, you can purchase my full solution containing 33 Columns for the all 28 311 Models
```
# +---------------------------------------------------------------------------------------------------------------------------+
YEAR | MAKER | MODEL | FULLMODELNAME | PRODUCTION END | BODY | CYLINDERS | DISPLACEMENT | POWER | TORQUE | FUEL SYSTEM | FUEL | TOP SPEED | ACCELERATION 0-100 KM/H | CO2 EMISSIONS | CITY | HIGHWAY | COMBINED | DRIVE TYPE | GEARBOX - GEARS | FRONT | REAR | TIRE SIZE | OVERALL LENGTH | WIDTH | HEIGHT | FRONT/REAR TRACK | WHEELBASE | CLEARANCE | TRUNK VOLUME | MIN WEIGHT | MAX WEIGHT
# +---------------------------------------------------------------------------------------------------------------------------+
```

#### Extra Feature

An update will be pushed every two to four months, keeping the data collection up to date with latest available data.

#### Extra sample


```sql
SELECT * FROM `vehicule` WHERE `MODEL` = 'f40'
# | 1987 |
# | FERRARI |
# | F40 |
# | 2.9 V8 5MT (478 HP) |
# | 1992 |
# | coupes |
# | V8 |
# | 2936 cm3 |
# | 352 KW @ 7000 RPM 478 HP @ 7000 RPM 472 BHP @ 7000... |
# | 426 lb-ft @ 4000 RPM 577 Nm @ 4000 RPM |
# | Turbocharged Multipoint Inject |
# | Gasoline |
# | 201 mph 323 km/h |
# | 4.1 s |
# | null |
# |  18.4 L/100Km |
# |  10.3 L/100Km |
# |  12.4 L/100Km |
# | Rear Wheel Drive |
# | 5-speed manual |
# | Ventilated Discs |
# | Ventilated Discs |
# | 235/45ZR-17 || 335/35ZR-17 |
# |  4430 mm |
# |  1981 mm |
# |  1130 mm |
# |  1,595/1,610 mm |
# |  2451 mm |
# |  124 mm |
# |  31 L |
# |  1250 kg |
# |  1430 kg |
```
#### PayPal Payment

[![Buy Now](https://www.paypalobjects.com/en_US/i/btn/btn_buynowCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=2LF6FNTP5SQNC)

Hope you enjoy this Extra..

## Acknowledgments<a name="Acknowledgments"></a>

* Data are collected from manufacturer official web sites, spec flyers , etc ..
