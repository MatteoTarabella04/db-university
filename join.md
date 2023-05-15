# Join

## Requests:

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia :
SELECT `students`.*, `degrees`.`name` AS `degree_name`
FROM `students`
JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia'

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze :
SELECT `degrees`.*, `departments`.`name` AS `department_name`
FROM `degrees`
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
WHERE `degrees`.`level` = 'magistrale'
AND `departments`.`name` = 'Dipartimento di Neuroscienze'

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44) : 
SELECT `courses`.*, `teachers`.`name` AS `teacher_name`
FROM `courses`
JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
WHERE `course_teacher`.`teacher_id` = 44

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il
relativo dipartimento, in ordine alfabetico per cognome e nome :
 SELECT `students`.`name`, `students`.`surname`, `degrees`.`name` AS `degrere_name`, `degrees`.`level`, `degrees`.`address` AS `degree_address`, `degrees`.`email` AS `degree_email`, `degrees`.`website` AS `degree website`, `departments`.`name` AS `Department Name`, `departments`.`phone`, `departments`.`address` AS `department_address`, `departments`.`email` AS `department_email`, `departments`.`website` AS `departments_website`, `departments`.`head_of_department`
 FROM `students`
 JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id`
 JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
 ORDER BY `students`.`surname`, `students`.`name`;

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti :


6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

7. BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per
superare ciascuno dei suoi esami