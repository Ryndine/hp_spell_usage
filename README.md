# ETL Project for UCSD Data Bootcamp

Sources used:
<br>https://www.kaggle.com/gulsahdemiryurek/harry-potter-dataset/version/5></br>
<br>https://github.com/theDavidBarton/the-harry-potter-database/tree/master/dataCollectors</br>


Write-up on project:
<br>https://docs.google.com/document/d/1HYP_cz7lHAs6IOeJ3bteXmnFL6-aj_RgK4v1it6j7Wk/</br>

Final Notes:
<br></br>
Extract: 
Multiple CSV files were downloaded from the referenced Kaggle dataset. All CSVs use a semicolon delimiter.
<br></br>
Transform: 
CSV files containing the script from three separate movies had to be combined, then filtered using the spells list, so we had one table that only contained the lines in which a spell name was cast, along with the name of the wizard casting it. 
<br></br>
Data cleaning was necessary on all spreadsheets to deal with issues such as: inconsistent case formatting, inconsistent data types, hidden leading, trailing, and inner spaces, removing NaN or “None” values, and removing duplicates.
<br></br>
Final joining was done using SQLAlchemy, joining columns from the Characters csv to the filtered wizards/spells table.
<br></br>
Load:
The table is loaded as an object-relational database to PostGres using SQLAlchemy, using the database name “harry_potter”.

