---
tags:
  - SQL
---
# Dates in SQL
## Types
in SQL we have more then one type and each type serve a need

| Type     | What Does it do?                                  |
| -------- | ------------------------------------------------- |
| DATE     | Return date in format "yyyy-mm-dd"                |
| TIME     | Return time in format "hh:mm:ss"                  |
| DATETIME | Merge between DATE and TIME "yyyy-mm-dd hh:mm:ss" |
## Getting Current Date
there is functions to get the current date in each database

| Function          | MySQL                                              | Postgres       |
| ----------------- | -------------------------------------------------- | -------------- |
| Current date      | CURRENT_DATE (not a function)                      | CURRENT_DATE() |
| Current time      | CURRENT_TIME (not a function)                      | CURRENT_TIME() |
| Current date time | NOW() or CURRENT_TIMESTAMP (for CURRENTSTAMP type) | NOW()          |
## Extracting Parts From Date
to extract date parts from a whole `DATE` or `DATETIME` we use:
- **in PostgreSQL**: we use `EXTRACT` function in this following syntax
	- `EXTRACT(YEAR FROM date)`
	- we can use `YEAR` `MONTH` `DAY` `WEEK` `HOUR` or else
- **in MySQL**: simply use the keyword and pass a date as a param
	- like `YEAR(date)` or `MONTH(date)` and it will extract the value
	
## Arithmetic on Dates (adding and removing)
- **In PostgreSQL**: it follows a certain pattern
	- we follow this `date_col + INTERVAL '1 day'`
	- for most cases this will work but when working with two dates  we can `date_col1 - date_col2` and this will return a days as integer
- **In MySQL**: function based calculations
	- **Add**: `DATE_ADD(date_col, INTERVAL 1 DAY)`
	- **Subtract**: `DATE_SUB(date_col, INTERVAL 1 DAY)`
	- **DIFF**: `DATEDIFF(date_col1, date_col2)` and this return a int representing the days
	
## Format Dates
each database have its own function to format a date
- **In PostgreSQL**: we use `TO_CHAR()` function
	- usage: `TO_CHAR(date_col, 'Mon DD, YYYY')` and you can change orders (example is a common format)
- **In MySQL**: can format date using `DATE_FORMAT()` function
	- usage: `DATE_FORMAT(date_col, '%b %d, %Y')` (this is a common format)
	
## From String to DATE
to convert we have:
- **In PostgreSQL**: using the `TO_DATE()` function
	- usage: `TO_DATE('21-Dec-2020', 'DD-Mon-YYYY')`
	- for timestamp we can use `TO_TIMESTAMP` same usage as `TO_DATE` but with extra config
- **In MySQL**: using the `STR_TO_DATE` function
	- usage: `STR_TO_DATE('21-Dec-2020', '%d-%b-%Y')`
	- for `TIMESTAMP` same function could be used
	
## Resources
- [Date Functions Section in W3School](https://www.w3schools.com/sql/func_mysql_date_format.asp)
- [PostgreSQL Date Functions](https://www.geeksforgeeks.org/postgresql/postgresql-date-functions/)