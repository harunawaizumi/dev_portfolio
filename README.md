# READ Me

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
# dev_portfolio
 

* hello from local to others


SELECT u.user_id, user_training_id, training_id, training_date COUNT(t.user_training_id) AS count
FROM users u
JOIN training_details t ON u.user_id = t.user_id
GROUP BY u.user_id, username, user_training_id, t.training_date
ORDER BY t.training_date DESC
HAVING COUNT(t.user_training_id) > 1


SELECT DISTINCT user_id FROM dbo.users WHERE user_id % 2 = 1 ORDER BY user_id LIMIT 100;

SELECT * FROM records WHERE id % 2 = 0;

CREATE TABLE score_table
(
    number INT,
    name    VARCHAR(20),
    class   INT,
    score   INT
)

INSERT INTO score_table VALUES (1, 'taro', 1, 57)
INSERT INTO score_table VALUES (2, 'taro', 2, 60)
INSERT INTO score_table VALUES (3, 'sanro', 1, 50)

SELECT
    class,
    DENSE_RANK() OVER(ORDER BY score DESC) AS Score,
    name,
    score
FROM
    score_table


SELECT CustomerName + '; ' FROM Customer ORDER BY CustomerID;

SELECT array_to_string(array_agg(CAPONE), '\n') FROM table

