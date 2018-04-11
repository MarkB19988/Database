# Database

### Relational Database System Design

#### Tools and Techniques Used

#### Techniques
I created a Entity Relationship Diagram to show how the tables in my database system are related to eachother.

I also created a Data Dictionary to show what information will be stored in each table.

#### Tools
To create my Entity Relationship Diagram I used an online tool called 'draw.io' that cna be used to create a wide variety of table and charts.

To create my Data Dictionary I used Microsoft Excel, a tool used to create tables and graphs and can be used to store values in a spreadsheet

![ERD](https://i.imgur.com/S1zF9uD.jpg)
###### My Entity Relationship Diagram

![DataDictionary](https://i.imgur.com/qYy0eRL.png)
###### My Data Dictionary

#### User Stories

###### As a user I would like to be able to look up my heroes level

###### As a user I would like to be able to look up my enemies level

###### As a user I would like to be able to look up my heroes current health

###### As a user I would like to be able to look up my enemies current health

###### As a user I would like to see how much damage my spells do

###### As a user I would like to see the range of my different spells

###### As a user I would like to see how much damage the enemy does

###### As a user I would like to see the name of my enemies

###### As a user I would like to add new enemies using a form

###### As a user I would like to delete data entries using a form

###### As a user I would like to add new heroes using a form

###### As a user I would like to create a report

###### As a user I would like to use SQL code to add new tables to the database


### Code I Used To Create My Database

Below are some of the SQL code snippets that I used to create my databse, they come under the following types:

#### Insert
This command is used to insert values and data into tables.

INSERT INTO ENEMIES VALUES( 
    1, 50,'MAGE', 150,'HEALTHY'
);

#### Create
This command is used to create new tables with new values.

CREATE TABLE ENEMIES(
         ID INT NOT NULL PRIMARY KEY,
         LEVEL INT NOT NULL,
         NAME VARCHAR(50) NOT NULL,
         DAMAGE FLOAT NOT NULL,
         HP FLOAT NOT NULL
);

CREATE TABLE HEROES(
         ID INT NOT NULL PRIMARY KEY,
         LEVEL INT NOT NULL,
         NAME VARCHAR(50) NOT NULL,
         CLASS VARCJAR(50) NOT NULL,
         HP FLOAT NOT NULL
);

CREATE TABLE SPELLS(
         ID INT NOT NULL PRIMARY KEY,
         DAMAGEHEALING INT NOT NULL,
         NAME VARCHAR(50) NOT NULL,
         RANGE INT NOT NULL,     
);

CREATE TABLE ENEMY_SKILLS(
         ENEMY_ID INT NOT NULL PRIMARY KEY,
         SPELL_ID INT NOT NULL PRIMARY KEY,
         LEVEL INT NOT NULL,    
);

CREATE TABLE HERO_SKILLS(
         HERO_ID INT NOT NULL PRIMARY KEY,
         SPELL_ID INT NOT NULL PRIMARY KEY,
         LEVEL INT NOT NULL,    
);


#### Update
This command is used to update the value of data within a table without having to create a new table.

UPDATE HEROES
    SET LEVEL = 4
    WHERE ID = 1;
    
UPDATE HEROES
    SET DAMAGE = 12.4
    WHERE NAME = BOI;

UPDATE SPELLS
    SET RAGE = 4
    WHERE ID = 4;
   
UPDATE SPELLS
    SET DAMAGEHEALING = 4
    WHERE NAME = FIREBALL;
    
#### Delete
This command is used to delete values from tables, the type of data can be specified.

#### Select
This command is used to search the database for any data that matches the paramaters you inpud into the command, it will then return any found data that fits these paramaters to you.

SELECT H.CLASS, H.LEVEL, S.NAME, HS.LEVEL
FROM HERO H, SKILLS S, HERO_SKILLS HS
WHERE HS.HERO_ID = H.ID AND HS.SKILL_ID = S.ID
AND S.NAME LIKE 'Fire%';

SELECT * FROM HERO;

SELECT LEVEL, CLASS FROM HERO
WHERE ID = 2;

SELECT MAX(H.LEVEL), MIN(H.LEVEL) FROM HERO H;

SELECT AVG(H.LEVEL) FROM HERO H;

