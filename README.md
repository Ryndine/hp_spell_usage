# Harry Potter Spell Usage
[Ryan Mangeno](https://github.com/Ryndine) | [Anny Tritchler](https://github.com/tritchlin/)

## Sources: 
https://www.kaggle.com/gulsahdemiryurek/harry-potter-dataset/version/5  
* Characters.csv,   
* Harry Potter 1.csv (Sorcerer's Stone Movie Script),   
* Harry Potter 2.csv (Chamber of Secrets Movie Script),   
* Harry Potter 3.csv (Prisoner of Azkaban Movie Script)  
* Spells.csv

## Transformations Neeeded: 
Cleaning, Joining, Filtering. 

## Database:
**Type:** Relational database (PgAdmin 4)  
**Content:** Character, Gender, House, Blood Status, Loyalty, Spells  
**Observations:** How often are spells used by each character across the 3 movies?  

## ETL Process:

**Extract:** Multiple CSV files were downloaded from the referenced Kaggle dataset. All CSVs use a semicolon delimiter.

**Transform:** CSV files containing the script from three separate movies had to be combined, then filtered using the spells list, so we had one table that only contained the lines in which a spell name was cast, along with the name of the wizard casting it. 

Data cleaning was necessary on all spreadsheets to deal with issues such as: inconsistent case formatting, inconsistent data types, hidden leading, trailing, and inner spaces, removing NaN or “None” values, and removing duplicates.

Final joining was done using SQLAlchemy, joining columns from the Characters csv to the filtered wizards/spells table.

**Load:** The table is loaded as an object-relational database to PostGres using SQLAlchemy, with the database name “harry_potter”.
