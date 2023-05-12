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
+--------------+
| name         |
+--------------+
| Lauro        |
| Matilde      |
| Marieva      |
| Marco        |
| Maika        |
| Fabiano      |
| Amedeo       |
| Tolomeo      |
| Eriberto     |
| Harry        |
| Ursula       |
| Pietro       |
| Harry        |
| Marino       |
| Cira         |
| Damiana      |
| Elda         |
| Maika        |
| Augusto      |
| Cira         |
| Boris        |
| Marcella     |
| Boris        |
| Egisto       |
| Laura        |
| Prisca       |
| Samira       |
| Flaviana     |
| Secondo      |
| Oreste       |
| Kociss       |
| Albino       |
| Mirko        |
| Tancredi     |
| Enrica       |
| Gianmarco    |
| Miriana      |
| Rodolfo      |
| Iacopo       |
| Cosetta      |
| Artemide     |
| Nayade       |
| Ethan        |
| Davis        |
| Olimpia      |
| Brigitta     |
| Laura        |
| Ruth         |
| Selvaggia    |
| Nazzareno    |
| Lucia        |
| Furio        |
| Carlo        |
| Tolomeo      |
| Raniero      |
| Danthon      |
| Erminia      |
| Giacinta     |
| Ortensia     |
| Costanzo     |
| Elio         |
| Ubaldo       |
| Rufo         |
| Rosalino     |
| Violante     |
| Samira       |
| Morgana      |
| Rudy         |
| Germano      |
| Elga         |
| Kristel      |
| Vania        |
| Rita         |
| Samira       |
| Manuele      |
| Donatella    |
| Folco        |
| Iacopo       |
| Pablo        |
| Cleros       |
| Silverio     |
| Damiana      |
| Primo        |
| Dindo        |
| Amos         |
| Monia        |
| Assia        |
| Boris        |
| Olimpia      |
| Jole         |
| Ivano        |
| Lauro        |
| Iacopo       |
| Mauro        |
| Shaira       |
| Gianleonardo |
| Erminia      |
| Leone        |
| Noemi        |
| Pietro       |
| Silverio     |
| Graziano     |
| Graziano     |
| Cassiopea    |
| Fortunata    |
| Maruska      |
| Claudia      |
| Giuliano     |
| Rita         |
| Timothy      |
| Fortunata    |
| Bibiana      |
| Vitalba      |
| Irene        |
| Zelida       |
| Bibiana      |
| Caligola     |
| Ileana       |
| Ausonio      |
| Clea         |
| Cleopatra    |
| Gaetano      |
| Gavino       |
| Egisto       |
| Carlo        |
| Vera         |
| Vania        |
| Ninfa        |
| Davis        |
| Adriano      |
| Danuta       |
| Noemi        |
| Carlo        |
| Ivano        |
| Isira        |
| Deborah      |
| Raniero      |
| Guendalina   |
| Anastasio    |
| Lidia        |
| Jelena       |
| Kris         |
| Leonardo     |
| Violante     |
| Gregorio     |
| Marieva      |
| Ingrid       |
| Concetta     |
| Valdo        |
| Danny        |
| Giulietta    |
| Giancarlo    |
| Carlo        |
| Bacchisio    |
| Ivano        |
| Terzo        |
| Grazia       |
| Alan         |
| Cleros       |
| Silverio     |
+--------------+
160 rows in set, 1 warning (0.00 sec)