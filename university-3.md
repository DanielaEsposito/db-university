1

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql


SELECT *
FROM `students`
JOIN `degrees`
ON `students`.`degree_id`= `degrees`.`id`
WHERE `degrees`.`name` = "corso di laurea in economia";
```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
   Neuroscienze

   ```sql
   SELECT *
   FROM `degrees`
   JOIN `departments`
   ON `degrees`.`department_id`= `departments`.`id`
   WHERE
   `degrees`.`level`= "magistrale" AND
   `departments`.`id`= 7;
   ```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```SQL
SELECT *
FROM `courses`
JOIN `teachers`
ON `courses`.`id`= `teachers`.`id`
WHERE `teachers`.`id`=44
```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
   sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
   nome

```sql
SELECT
    `students`.`id` AS `student_id`,
    `students`.`name` AS `student_name`,
    `students`.`surname` AS `student_surname`,
    `degrees`.`name` AS `degree_name`,
    `departments`.`name` AS `department_name`
FROM `students`
JOIN `degrees`  ON `students`.`degree_id` = `degrees`.`id`
JOIN `departments`  ON `departments`.`id`= `degrees`.`department_id`
ORDER BY `student_name` ASC, `student_surname` ASC;
```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
   ```SQL
   SELECT *
   FROM `degrees`
   JOIN `courses`
   ON `degrees`.`id`= `courses`.`degree_id`
   JOIN `teachers`
   ON `courses`.`id`= `teachers`.`id` ;
   ```

````

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
   Matematica (54)

   ```SQL
   SELECT COUNT(*)
    FROM `teachers`
    JOIN `courses`
    ON `teachers`.`id`=`courses`.`id`
    JOIN `degrees`
    ON `degrees`.`id`= `courses`.`degree_id`
   JOIN `departments`
   ON `departments`.`id` = `degrees`.`department_id`
   WHERE `departments`.`name`="Dipartimento di Matematica"
   GROUP BY `teachers`.`id`;
   ```
````

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
   per ogni esame, stampando anche il voto massimo. Successivamente,
   filtrare i tentativi con voto minimo 18.

```

```

```

```

```

```
