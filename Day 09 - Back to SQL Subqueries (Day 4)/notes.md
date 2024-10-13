### 1. **Subqueries**

- **Definition**: A subquery is a query nested inside another SQL query. It is used to perform operations that require data from multiple steps or tables.
- **Example**: Find employees who earn more than the average salary.
    
    ```sql
    SELECT name
    FROM employees
    WHERE salary > (SELECT AVG(salary) FROM employees);
    
    ```
    

### 2. **Subqueries Example**

- **Use Case**: Fetch customers who placed orders in the last month.
- **Example**:
    
    ```sql
    SELECT customer_id, customer_name
    FROM customers
    WHERE customer_id IN (SELECT customer_id FROM orders WHERE order_date > '2024-09-01');
    
    ```
    

### 3. **Subqueries with Aggregation**

- **Definition**: Using aggregate functions like `SUM()`, `AVG()`, `MIN()`, `MAX()`, etc., in subqueries.
- **Example**: Get departments where the total salary exceeds $100,000.
    
    ```sql
    SELECT department_name
    FROM departments
    WHERE (SELECT SUM(salary) FROM employees WHERE employees.department_id = departments.department_id) > 100000;
    ```
    

### 4. **Subquery vs. Join**

- **Definition**: While subqueries can be used to retrieve data based on the results of another query, joins directly combine multiple tables to get the data.
- **Subquery Example**:
    
    ```sql
    
    SELECT name
    FROM employees
    WHERE department_id = (SELECT department_id FROM departments WHERE department_name = 'Sales');
    
    ```
    
- **Join Example**:
    
    ```sql
    SELECT employees.name
    FROM employees
    INNER JOIN departments ON employees.department_id = departments.department_id
    WHERE departments.department_name = 'Sales';
    
    ```
    

### 5. **ALL Keyword**

- **Definition**: The `ALL` keyword allows comparison of a value against all values in a subquery.
- **Example**: Find products priced higher than all products in the 'Electronics' category.
    
    ```sql
    
    SELECT product_name
    FROM products
    WHERE price > ALL (SELECT price FROM products WHERE category = 'Electronics');
    
    ```
    

### 6. **ANY Keyword**

- **Definition**: The `ANY` keyword allows comparison of a value against any value in a subquery.
- **Example**: Find employees who earn more than any employee in the 'HR' department.
    
    ```sql
    
    SELECT name
    FROM employees
    WHERE salary > ANY (SELECT salary FROM employees WHERE department = 'HR');
    
    ```
    

### 7. **Correlated Subquery**

- **Definition**: A correlated subquery references columns from the outer query and is executed once for each row processed by the outer query.
- **Example**: List employees who earn more than the average salary of their department.
    
    ```sql
    
    SELECT name
    FROM employees e1
    WHERE salary > (SELECT AVG(salary) FROM employees e2 WHERE e1.department_id = e2.department_id);
    
    ```
    

### 8. **EXISTS Operator**

- **Definition**: The `EXISTS` operator checks for the existence of rows returned by a subquery.
- **Example**: Find customers who have placed at least one order.
    
    ```sql
    SELECT customer_name
    FROM customers
    WHERE EXISTS (SELECT 1 FROM orders WHERE customers.customer_id = orders.customer_id);
    
    ```
    

### 9. **Subquery in SELECT**

- **Definition**: Subqueries can be used in the `SELECT` clause to compute additional values.
- **Example**: Display the total sales for each department.
    
    ```sql
    
    SELECT department_name, (SELECT SUM(sales) FROM employees WHERE employees.department_id = departments.department_id) AS total_sales
    FROM departments;
    
    ```
    

### 10. **Subquery in FROM**

- **Definition**: A subquery can act as a derived table within the `FROM` clause.
- **Example**: List departments with more than 5 employees.
    
    ```sql
    
    SELECT department_name
    FROM (SELECT department_id, COUNT(*) AS num_employees FROM employees GROUP BY department_id) AS dept_summary
    WHERE num_employees > 5;
    
    ```