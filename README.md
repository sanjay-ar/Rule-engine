# Rule Engine
Rule Engine with AST This is a 3-tier application to evaluate user eligibility using rules based on Abstract Syntax Tree (AST).


# Rule Engine Application
Hosted link: https://zeotap-internship-assignment1.onrendewwwr.com

## Overview

This application is a rule engine that determines user eligibility based on attributes such as age, department, salary, and experience. It uses an Abstract Syntax Tree (AST) to represent and manage conditional rules, allowing for dynamic rule creation, combination, and evaluation.

<img width="943" alt="image" src="1.png">


## Features

- **Create Rules:** Define rules using a string format that gets converted into an AST.
  
  <img width="377" alt="image" src="2.png">


- **Combine Rules:** Combine multiple rules into a single AST for more complex evaluations.
  
  <img width="376" alt="image" src="3.png">

  
- **Evaluate Rules:** Check if the given data meets the criteria defined by the AST.
  
  <img width="375" alt="image" src="4.png">


- **Tree Visualization:** Define or Combine Rule would should show Tree Representation.

## Tech Stack

- **Backend:** Node.js, Express.js
- **Database:** MongoDB

## Getting Started

### Prerequisites

- Node.js and npm installed
- MongoDB installed and running

### Installation

1. **Clone the Repository**
   ```bash
   git clone "https://github.com/sanjay-ar/zeotap-internship-assignment1"
   cd zeotap-internship-assignment1
   ```

2. **Install Backend Dependencies**

   ```bash
   npm install
   ```
   
3. **Start MongoDB**

   Ensure that MongoDB is running on your local machine:

   ```bash
   mongod
   ```

4. **Start the Backend Server**

   ```bash
   nodemon server.js
   ```

## API Endpoints

1. **Create a Rule**
   - **Endpoint:** `/api/create_rule`
   - **Method:** POST
   - **Body:**

     ```json
     {
       "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)",
       "ruleName": "Rule 1"
     }
     ```
use appropriate spaces in Rules for correct results.

Rule should be in follow format:
variable operator value 

   - **Response:**

     ```json
     {
       "_id": "605c72ef1f4e3a001f4d2e9a",
       "rule_name": "Rule1",
       "rule_ast": { ... }
     }
     ```

2. **Combine Rules**
   - **Endpoint:** `/api/rules/combine_rules`
   - **Method:** POST
   - **Body:**

     ```json
     {
       "ruleIds": ["605c72ef1f4e3a001f4d2e9a", "605c730f1f4e3a001f4d2e9b"]
       "operators: op
     }
     ```
   - **Response:**

     ```json
     {
       "type": "operator",
       "value": operator,
       "left": { ... },
       "right": { ... }
     }
     ```

3. **Evaluate a Rule**
   - **Endpoint:** `/api/rules/evaluate_rule`
   - **Method:** POST
   - **Body:**

     ```json
     {"age": 35,
      "department": "Sales", "salary": 60000, "experience": 3}
     ```
   - **Response:**

     ```json
     {
       "result": true
     }
     ```

---

### 🚀 Maintained by [Sanjay A R](https://github.com/sanjay-ar)

[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-blue?style=flat-square&logo=vercel)](https://portfolio-ar.vercel.app/)  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sanjay%20A%20R-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/sanjay-ar/)  
[![GitHub](https://img.shields.io/badge/GitHub-sanjay--ar-black?style=flat-square&logo=github)](https://github.com/sanjay-ar)

> 💡 *Like this project? Leave a ⭐ and connect with me!*

