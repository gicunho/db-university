# Query GROUP BY phpMyAdmin

## 1) Contare quanti iscritti ci sono stati ogni anno
SELECT COUNT(*) AS 'totale_iscritti', `year` AS 'anno'
FROM `courses`
GROUP BY `year`;

## 2) Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT COUNT(*) AS 'numero_insegnanti_presso:', `office_address`
FROM `teachers`
GROUP BY `office_address`;

## 3) Calcolare la media dei voti di ogni appello d'esame
SELECT AVG(`vote`) as 'voto_medio', `exam_id` as 'esame'
FROM `exam_student`
GROUP BY `exam_id`;

## 4) Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT COUNT(`id`) AS 'numero_corsi', `department_id`
FROM `degrees`
GROUP BY `department_id`;

# Query JOIN phpMyAdmin
## 1) Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
SELECT students.name, students.surname, students.fiscal_code, students.enrolment_date, students.registration_number, students.email, degrees.name
FROM `students`
JOIN `degrees`
ON students.degree_id = degrees.id
WHERE degrees.name = 'Corso di Laurea in Economia';

## 2) Selezionare tutti i Corsi di Laurea del Dipartimento di Neuroscienze
SELECT courses.id, courses.name, courses.description, courses.period, courses.period, courses.year, departments.name
FROM `courses`
JOIN `degrees`
ON courses.degree_id = degrees.id
JOIN `departments`
ON degrees.department_id = departments.id
WHERE departments.name = 'Dipartimento di Neuroscienze'

## 3) Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
SELECT courses.name, courses.description, teachers.name
FROM `course_teacher`
JOIN `courses`
ON course_teacher.course_id = courses.id
JOIN `teachers`
ON course_teacher.teacher_id = teachers.id
WHERE teachers.id = 44

## 4) Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
SELECT `students`.`surname`, `students`.`name`, `degrees`.`name`, `departments`.`name`
FROM `students`
JOIN `degrees`
ON students.degree_id = degrees.id
JOIN `departments`
ON degrees.department_id = departments.id
ORDER BY `students`.`surname` ASC, `students`.`name` ASC

## 5) Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
SELECT degrees.name as 'Nome Laurea', courses.name as 'Nome Corso', teachers.name as 'Nome Insegnante', teachers.surname as 'Cognome Insegnante'
FROM `courses`
JOIN `degrees`
ON courses.degree_id = degrees.id
JOIN course_teacher
ON courses.id = course_teacher.course_id
JOIN `teachers`
ON course_teacher.teacher_id = teachers.id

## 6) Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
## 7) BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per superare ciascuno dei suoi esami