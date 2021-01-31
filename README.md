# University project

List team members including names, and student numbers

| **Name** | **Student Number** |
| ---| --- |
| Moumin Farah | 300026540 |
| André Marie Mishindu Kabeya | 300067899 |
| Joseph Nikuzabo | 300115712 |


## Liverable1


### ER Diagram

- Creating a (simplified) ER model
- Include your ER model (as an image and links to any raw files)
- Instructions on how you created your ER

The ER was created with [LucidChart](https://lucid.app)

![](Images/ER_model.png)



### Ralational Diagram

- Creating a (simplified) Relational model
- Include your relational model (as an image and links to any raw files)
- Instructions on how you created your ER relational model

The relational model was created with [LucidChart](https://lucid.app)

![](Images/Relational_model.png)




### Schema SQL

- A reference to your SQL schema (and how to run it)


The database was created using Postgres. 
```bash
> create database athlete;
```


The following sql will create the athlete schema

- The leaderboard database should only model the athletes and include details such as their name, date of birth,
and identified gender

- Implementing the SQL schema (based on your relational model) to create your database


```sql
CREATE TABLE athlete(
  firstName varchar(50) ,
  lastName varchar(50) ,
  dateOfBirth date,
  sex char(1)
 );
```

This is what our created table looks like 

 firstname | lastname | dateofbirth | sex
-----------|----------|-------------|-----




### Exemple SQL

- Additional example queries to show INSERT, UPDATE, SELECT, DELETE on your database

### INSERT


```sql
INSERT INTO athlete (FirstName, LastName, DateOfBirth, Sex)
VALUES
	('Bob','Test','1997-07-22','M'),
        ('Bob2','Test2','1998-07-22','M'),
	('Sab','Test3','1999-07-22','F');
```

Now we have 3 athletes in our database.

 firstname | lastname | dateofbirth | sex
-----------|----------|-------------|-----
 Bob       | Test     | 1997-07-22  | M
 Bob2      | Test2    | 1998-07-22  | M
 Sab       | Test3    | 1999-07-22  | F



### UPDATE


```sql
UPDATE athlete
SET lastname = 'Test1'
WHERE firstname='Bob';
```

The last name of bob has been updated from Test to Test1

 firstname | lastname | dateofbirth | sex
-----------|----------|-------------|-----
 Bob2      | Test2    | 1998-07-22  | M
 Sab       | Test3    | 1999-07-22  | F
 **Bob**       | **Test1**    | **1997-07-22**  | **M**




```sql
UPDATE athlete
SET firstName='Sabrina'
WHERE lastname='Test3';
```
We changed to first name from Sab to Sabina of the athlete with the last name Test3

 firstname | lastname | dateofbirth | sex
-----------|----------|-------------|-----
 Bob2      | Test2    | 1998-07-22  | M
 Bob       | Test1    | 1997-07-22  | M
 **Sabrina** | **Test3**    | **1999-07-22**  | **F**


### SELECT


```sql
SELECT * FROM athlete;
```
Select all the fields available in the table

 firstname | lastname | dateofbirth | sex
-----------|----------|-------------|-----
 Bob2      | Test2    | 1998-07-22  | M
 Bob       | Test1    | 1997-07-22  | M
 Sabrina   | Test3    | 1999-07-22  | F




```sql
SELECT firstName FROM athlete;
```
Selected just the firstname field in the table

 |firstname|
|----------|
 Bob2
 Bob
 Sabrina



```sql
SELECT sex FROM athlete;
```

Selected just the sex field in the table 

 |sex|
|-----|
 M
 M
 F


```sql
SELECT dateofbirth FROM athlete 
    WHERE firstName='Bob';
```

Select the field dateofbirth  of the athlete with the first name Bob

|dateofbirth|
|-------------|
 1997-07-22



### DELETE


```sql
DELETE FROM athlete
WHERE lastname='Test3';
```

We deleted the athlete with the last name Test3

 firstname | lastname | dateofbirth | sex
-----------|----------|-------------|-----
 Bob2      | Test2    | 1998-07-22  | M
 Bob       | Test1    | 1997-07-22  | M



```sql
DELETE FROM athlete
WHERE dateofbirth='1998-07-22';
```

We have deleted the athlete that was born on the date 1998-07-22

 firstname | lastname | dateofbirth | sex
-----------|----------|-------------|-----
 Bob       | Test1    | 1997-07-22  | M
