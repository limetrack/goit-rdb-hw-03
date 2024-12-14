# DQL команди

1. Напишіть SQL команду, за допомогою якої можна:

        - Вибрати всі стовпчики з таблиці products:
SELECT * FROM  `mydb`.`products`; 
<img width="1009" alt="p1_1" src="https://github.com/user-attachments/assets/de0f2032-5808-443b-b123-566f8da19b99">

        - Вибрати тільки name і phone з таблиці shippers:
SELECT name, phone FROM  `mydb`.`shippers `;
<img width="1009" alt="p1_2" src="https://github.com/user-attachments/assets/ceb75fb4-4156-44ee-af3c-6474abef0f4c">

2. Знайти середнє, максимальне та мінімальне значення стовпчика price у таблиці products:

SELECT 
    AVG(price) AS average_price,
    MAX(price) AS max_price,
    MIN(price) AS min_price
FROM `mydb`.`products`;
<img width="1005" alt="p2" src="https://github.com/user-attachments/assets/356803f0-96ce-4dc0-b4a2-639e93152bf3">

3. Обрати унікальні значення колонок category_id та price з таблиці products у порядку спадання price, вибрати тільки 10 рядків:

SELECT DISTINCT category_id, price
FROM `mydb`.`products`
ORDER BY price DESC
LIMIT 10;
<img width="1005" alt="p3" src="https://github.com/user-attachments/assets/050fdd0e-d31c-417b-a1b1-8c8f4f84322a">

4. Знайти кількість продуктів (рядків), які знаходяться в цінових межах від 20 до 100:

SELECT COUNT(*) AS product_count
FROM `mydb`.`products`
WHERE price BETWEEN 20 AND 100;
<img width="1007" alt="p4" src="https://github.com/user-attachments/assets/08ead7e8-f175-45d9-96c6-6902d09acb95">

5. Знайти кількість продуктів (рядків) та середню ціну (price) у кожного постачальника (supplier_id):

SELECT 
    supplier_id,
    COUNT(*) AS product_count,
    AVG(price) AS average_price
FROM `mydb`.`products`
GROUP BY supplier_id;
<img width="1009" alt="p5" src="https://github.com/user-attachments/assets/153ab99b-4dbd-42a8-a068-ea23b2017c1a">
