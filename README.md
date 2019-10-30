# RealForce coding test

## Description
An application designed to calculate the salary of employees 
including an expandable system of bonuses/deductions.

● Country Tax for salaries is 20%
● If an employee older than 50 we want to add 7% to his salary
● If an employee has more than 2 kids we want to decrease his Tax by 2%
● If an employee wants to use a company car we need to deduct $500


## Situation
● Alice is 26 years old, she has 2 kids and her salary is $6000
● Bob is 52, he is using a company car and his salary is $4000
● Charlie is 36, he has 3 kids, company car and his salary is $5000


## Architecture
- Employee entity
    - Name: string, not null
    - Salary: integer, not null
    - Birthday: integer, unix timestamp, not null
    - Kids: integer, default = 0
    - UsesCar: integer (0 = false, 1 = true), default = 0
- Statement class
    - modifiers: list of bonus/deduction values
    - subTotal: Sub Total value
    - taxDiscounts: list of Tax discounts
    - taxValue: resulting Tax value
    - total: resulting value (= subTotal - taxValue)
- Rule interface    
- Specific Rules
    - AgeRule class
    - KidsRule class
    - CarRule class
- SalaryService
    - Initializes a list of Rules
    - Implements calculate function based on Rules

## How to install

1. Clone this repository and navigate to the project folder.
2. Use Composer to resolve all dependencies - run `composer install`.
2. You must have apache/php-fpm installed and tuned.
3. Open the application in your browser.

## How to test
Choose the project root, then run: ./bin/phpunit --configuration phpunit.xml.dist


