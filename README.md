List team members including names, and student numbers
Student name: 
Student number: 
Course code: 

Student name: 
Student number: 
Course code: 

Name: 
Student Number: 
Section: 




Include your ER model (as an image and links to any raw files):


![](Images/ER_model.png)


Include your relational model (as an image and links to any raw files):

![](Images/Relational_model.png)

Instructions on how you created your ER and Relational model
A reference to your SQL schema (and how to run it)
Additional example queries to show INSERT, UPDATE, SELECT, DELETE on your database


- Exemple SQL pour insertion de données

INSERT INTO athlete (FirstName, LastName, DateOfBirth, Sex)

VALUES
	('Bob','Test','1997-07-22','M'),
        ('Bob2','Test2','1998-07-22','M'),
	('Sab','Test3','1999-07-22','F');

- Exemple SQL pour mettre-à-jour les données

UPDATE athlete
SET lastname = 'Test1'
WHERE firstname='Bob';

UPDATE athlete
SET firstName='Sabrina'
WHERE lastname='Test3';


- Exemple SQL pour sélectionner les données

SELECT * FROM athlete;
SELECT firstName FROM athlete;
SELECT sex FROM athlete;
SELECT dateofbirth FROM athlete WHERE firstName='Bob';

- Exemple SQL pour effacer les données

DELETE FROM athlete
WHERE lastname='Test3';

DELETE FROM athlete
WHERE dateofbirth='1998-07-22';



