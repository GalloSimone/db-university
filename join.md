1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

'''sql
SELECT
`students`.`id`,
`students`.`name`,
`students`.`surname`,
`students`.`registration_number`,
`degrees`.`id` AS `degrees_id`,
`degrees`.`name` AS `degrees_name`

FROM `university_db`.`students`

INNER JOIN `university_db`.`degrees`

ON `students`.`degree_id`=`degrees`.`id`

WHERE `degrees`.`name`= 'Corso di laurea in Economia'

'''

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

'''sql

SELECT 
`degrees`.`id`,
`degrees`.`department_id`,
`degrees`.`name`AS `degrees_name`,
`degrees`.`level`,
`departments`.`id`AS `department_id`,
`departments`.`name`AS `department_name`

 FROM `university_db`.`degrees`
 
 INNER JOIN `university_db`.`departments`
 
 ON `degrees`.`department_id` = `departments`.`id`
 
 WHERE `degrees`.`level`='magistrale' AND `departments`.`name`='Dipartimento di Neuroscienze'


'''


3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

'''sql

SELECT 
`courses`.`id` AS `course_id`,
`courses`.`name` AS `course_name`,
`teachers`.`id` AS `teacher_id`,
`teachers`.`name` AS `teacher_name`,
`teachers`.`surname` AS `teacher_surname`


FROM `university_db`.`courses`
INNER JOIN `university_db`.`course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `university_db`.`teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`
WHERE `teachers`.`id` = 44;



'''

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome




5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti



6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)


7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo. Successivamente,
filtrare i tentativi con voto minimo 18