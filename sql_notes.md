# SQL Notes 
Collection of Insights from my SQL Learning Journey. Adapted from my handwritten notes on the same topic.
## 11/28/2023 
#### Began with sql-practice.com and sqlzoo
1. **Selecting Particular Strings:**
   
```sql
SELECT *
FROM table
WHERE keyword LIKE 'C_s%e';
```
This will select strings starting with C, with a single character in between, followed by s, some characters in between, and ending with e.
for example Castle

2. **Updating Column Values:**
   
```sql
UPDATE table_name
SET column_1 = value_1
WHERE condition;
```
This will change the value of column_1 in the table to value_1 whenever the condition is satisfied.

3. **Concatenate Strings:**
```sql
SELECT CONCAT(first_name,' ',last_name) AS full name
```
Self Explanatory: Concatenate the values in the columns first_name and last_name with a space in between to a new full_name column. 

4. **Selective Filtering on the Year in the Date Column:**
```sql
SELECT COUNT(*) AS total_patients
FROM patients
WHERE YEAR(birth_date)=2010;
```
Count the total Number of Patients who were born in the year 2010.

5. **Select the tallest person:**
```sql
WHERE height= (SELECT MAX(height) FROM patients);
```
Self Explanatory

6. **Cities Filtered By Province**
```sql
SELECT city
FROM patients
GROUP BY city
HAVING province_id= 'NS';
``` 

7. **Unique First Names Only**
```sql
SELECT first_name
FROM patients
GROUP BY first_name
HAVING COUNT(first_name)=1;
```

8. **Six Letter Names Starting and Ending on s**
```sql
WHERE first_name LIKE 's%s' AND LEN(first_name)>=6;
```
9. **Shortest First Names Ordered Alphabetically**
```sql
SELECT first_name
FROM patients
ORDER BY LEN(first_name),first_name;
``` 
By default, ORDER BY orders in Ascending order  
