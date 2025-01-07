1

1. Selezionare tutti gli studenti nati nel 1990 (160)

```SQL
SELECT \*
FROM `students`
WHERE YEAR(date_of_birth) = 1990;

```

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

```SQL
SELECT *
FROM `courses`
WHERE `cfu` > 10;

```

3. Selezionare tutti gli studenti che hanno più di 30 anni

```SQL

```

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
   laurea (286)

```SQL
SELECT COUNT(*)  AS `courses_count`
FROM `courses`
WHERE `period` = "I semestre" AND `year` = 1;
```

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
   20/06/2020 (21)

```SQL
SELECT *
FROM `exams`
WHERE DATE(date) = '2020-06-20' AND TIME(hour) > '14:00:00';

```

6. Selezionare tutti i corsi di laurea magistrale (38)

```SQL
SELECT *
FROM `degrees`
WHERE `name` LIKE '%Magistrale%';

```

7. Da quanti dipartimenti è composta l'università? (12)

```SQL
SELECT COUNT(*) AS `department_count `
FROM `departments`;
```

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo
   degree_id, inserire un valore casuale)
   ```sql
   INSERT INTO `students` (degree_id,name, surname, date_of_birth,fiscal_code,enrolment_date,registration_number,email)
   VALUES (10,'Daniela', 'Esposito', '1998-09-17', 'SPSMNL98P56A757K','2020-02-21','123456', 'emaill@example.com');
   ```
10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126
11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9

```SQL

DELETE FROM `students`
WHERE `degree_id`=10 AND `name` = 'Daniela' AND `surname` = 'Esposito' AND `date_of_birth`='1998-09-17' AND `fiscal_code`='SPSMNL98P56A757K' AND `enrolment_date`='2020-02-21' AND `registration_number` = '123456' AND `email`='emaill@example.com';
```
