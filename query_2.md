# Query 2 phpMyAdmin

## 1) Contare quanti iscritti ci sono stati ogni anno
SELECT COUNT(*) AS 'totale_iscritti', `year` AS 'anno'
FROM `courses`
GROUP BY `year`

## 2) Contare gli insegnanti che hanno l'ufficio nello stesso edificio
SELECT COUNT(*) AS 'numero_insegnanti_presso:', `office_address`
FROM `teachers`
GROUP BY `office_address`

## 3) Calcolare la media dei voti di ogni appello d'esame
SELECT AVG(`vote`) as 'voto_medio', `exam_id` as 'esame'
FROM `exam_student`
GROUP BY `exam_id`

## 4) Contare quanti corsi di laurea ci sono per ogni dipartimento