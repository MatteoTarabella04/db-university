# Ex query con select


## Request:

1. Selezionare tutti gli studenti nati nel 1990 (160)
2. Selezionare tutti i corsi che valgono più di 10 crediti (479)
3. Selezionare tutti gli studenti che hanno più di 30 anni
4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
laurea (286)
5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
20/06/2020 (21)
6. Selezionare tutti i corsi di laurea magistrale (38)
7. Da quanti dipartimenti è composta l'università? (12)
8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

## Steps:

- Use comand C:\MAMP\bin\mysql\bin\mysql -u root -p to start the shell and enter in phpMyAdmin.
- Use show datatabses comand for look the databases. COMAND:(show databases;)
+--------------------+
| Database           |
+--------------------+
| information_schema |
| db_university      |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

- Use use comand to enter the selected database. COMAND:(USE `db_university`;)
- Use show tables comand to look the table inside the selected database. COMAND:(show tables;)
+-------------------------+
| Tables_in_db_university |
+-------------------------+
| course_teacher          |
| courses                 |
| degrees                 |
| departments             |
| exam_student            |
| exams                   |
| students                |
| teachers                |
+-------------------------+
8 rows in set (0.00 sec)

- Use describe comand to look over a selected row. COMAND:(describe "row_name")

1. Selezionare tutti gli studenti nati nel 1990 (160) :
mysql> SELECT `name`   
    -> FROM `students`
    -> WHERE `date_of_birth`
    -> LIKE '1990%';
### Use '%' after year for select also the data after the selector

2. Selezionare tutti i corsi che valgono più di 10 crediti (479) :
mysql> SELECT `name`
    -> FROM `courses`
    -> WHERE `cfu` > 10;

3. Selezionare tutti gli studenti che hanno più di 30 anni :
mysql> SELECT `name`
    -> FROM `students`    
    -> WHERE 2023 - YEAR(`date_of_birth`) > 30;
    
4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286) :
mysql> SELECT *       
    -> FROM `courses`
    -> WHERE `period` = 'I semestre'  
    -> AND YEAR = '1';

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21) :
mysql> SELECT *                   
    -> FROM `exams`
    -> WHERE HOUR(`hour`) >= 14
    -> AND `date` = '2020/06/20'; 

6. Selezionare tutti i corsi di laurea magistrale (38) :
mysql> SELECT *
    -> FROM `degrees`
    -> WHERE `level` = 'magistrale';

7. Da quanti dipartimenti è composta l'università? (12) : 
mysql> SELECT COUNT(ID)       
    -> AS Numero_Dipartimenti  
    -> FROM `departments`;

