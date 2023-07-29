---
layout: single
title: "Alogorithm and DB"
---

# DB 관련 문제
1. SQL 쿼리 문제 :
    - 주어진 "Students"테이블에서 성적이 90점 이상인 학생들의 이름과 점수를 검색하는 SQL 쿼리를 작성하세요.
    - 예시 답안
    ```
    SELECT 
        name,
        score
    FROM Students
    WHERE score >= 90;
    ```

2. 쿼리 최적화 문제 :
    - 다음 쿼리를 실행하는데 가장 효율적인 방법을 선택하세요.(인덱스가 "date" 열에 존재한다고 가정)
    ```
    SELECT 
        *
    FROM Orders
    WHERE date BETWEEN '2023-01-01' AND '2023-07-01';
    ```
    - 예시 답안
        - 주어진 쿼리는 'date'열에 인덱스가 있으므로 인덱스 스캔을 통해 효율적으로 처리될 수 있다.

3. 데이터 모델링 문제 :
    - 사용자(User)와 상품(Product) 간의 관계를 나타내는 데이터베이스 스키마를 설계하세요. 하나의 사용자는 여러 개의 상품을 소유할 수 있으며, 하나의 상품은 여러 명의 사용자에게 속할 수 있습니다.
    - 예시 답안
    ```
    CREATE TABLE User (
    user_id INT PRIMARY KEY,
    username VARCHAR(50)
    );

    CREATE TABLE Product (
        product_id INT PRIMARY KEY,
        product_name VARCHAR(100),
        owner_id INT,
        FOREIGN KEY (owner_id) REFERENCES User(user_id)
    );
    ```

4. 트랜잭션 관리와 무결성 문제 :
    - 주문(Order)을 처리하는 도중 오류가 발생하여 해당 주문을 취소해야 합니다. 주문을 최소하는 SQL 쿼리와 함께 이를 트랜잭션으로 묶는 방법을 설명하세요.
    - 예시 답안
    ```
    BEGIN TRANSACTION;

    UPDATE Orders
    SET status = 'CANCELLED'
    WHERE order_id = 123;

    COMMIT;
    ```

5. 인덱스 설계와 성능 최적화 문제 :
    - 다음 쿼리를 실행하는데 가장 효율적인 인덱스를 설계하세요.
    ```
    SELECT 
           *
      FROM Employees
     WHERE department = 'Engineering' AND salary >= 50000;
    ```
    - 예시 답안
        - "department"와 "salary"열에 복합  인덱스를 생성하여 효율적으로 처리할 수 있다.
        ```
        CREATE INDEX idx_department_salary ON Employees (department, salary);
        ```