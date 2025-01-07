1. Selezionare tutti gli studenti nati nel 1990 (160)

'''sql

SELECT `id`, `name`,`date_of_birth`
FROM `university_db`.`students`
WHERE YEAR(`date_of_birth`) = 1990;

'''

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

'''sql

SELECT*
FROM `university_db`.`courses`
WHERE `cfu` > 10;

'''

3. Selezionare tutti gli studenti che hanno più di 30 anni

'''sql
SELECT `id`, `name`,`date_of_birth`
FROM `university_db`.`students`
WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) > 30;

'''

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)


'''sql

SELECT `id`,`name`,`cfu`,`year`,`period`
FROM `university_db`.`courses`
WHERE `period`= "I semestre" AND`year`=1

'''



5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

'''sql
SELECT `id`,`date`,`hour`
FROM `university_db`.`exams`
WHERE `date`= "2020-06-20" AND`hour`>"14:00:00"
'''

6. Selezionare tutti i corsi di laurea magistrale (38)

'''sql
SELECT `id`,`level`
FROM `university_db`.`degrees`
WHERE `level`= "magistrale" 
'''

7. Da quanti dipartimenti è composta l'università? (12)

'''sql
SELECT COUNT(*)
FROM `university_db`.`departments`
'''


8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

'''sql
SELECT `id`,`name`,`phone`
FROM `university_db`.`teachers`
WHERE `phone` IS NULL
'''


9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)

'''sql
INSERT INTO `university_db`.`students` 
(`degree_id`, `name`, `surname`, `date_of_birth`, `fiscal_code`, `enrolment_date`, `registration_number`)
VALUES 
("55", "simone", "gallo", "2005-12-14", "FGH98Y24C352O", "2016-07-02", "7864345");

'''

10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

'''sql
UPDATE `university_db`.`teachers`
SET `office_number` = "126"
WHERE `name` = "Pietro";
'''

11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9