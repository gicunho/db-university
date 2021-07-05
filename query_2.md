# Query 2 phpMyAdmin

## 1) Contare quanti iscritti ci sono stati ogni anno
SELECT COUNT(*) AS 'totale_iscritti', `year` AS 'anno'
FROM `courses`
GROUP BY `year`