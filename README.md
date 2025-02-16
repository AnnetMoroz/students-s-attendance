
/*Данные — небольшой датасет реальных данных, описывающих посещаемость небольшого кружка. Все данные анонимизированы и представлены в виде идентификаторов. 
Данные содержаться в гугл-таблице, на вкладке data находятся собственно данные, на вкладке description находится описание данных.
Сделайте на основе данных визуализацию.Например, постройте график средней посещаемости по дням, или любые другие графики по вашему усмотрению. Визуализацию можно делать в BI-платформе, например, в Datalens. Попробуйте найти интересные закономерности в данных и показать их.Например, посчитать среднюю посещаемость по каждой из тренировок, или любые другие метрики по вашему усмотрению.(SQL)*/

--SQL запросы: 
SELECT customer_id
FROM test
GROUP BY customer_id
HAVING SUM(is_attend) = 0; --возвращет тех учеников, кто не посетил ни одного занятия

SELECT customer_id
FROM test
GROUP BY customer_id
HAVING
SUM(is_attend) = COUNT(event_id); --покажет учеников, которые посетили все занятия

SELECT COUNT(event_id) AS total_events
FROM test; --покажет, сколько всего было занятий за все время (в датасете)

SELECT event_date,
COUNT(event_id) AS events_count
FROM test
GROUP BY event_date
ORDER BY event_date; --покажет, сколько занятий было за каждый день
