# 🛡️ SQL Query Filtering for Security Tasks

This project demonstrates how SQL filters were applied to investigate and support system security operations in an organization. The queries helped detect suspicious login activity and identify employee machines requiring updates.

---

## 📘 Project Description

My organization is working to improve its system security. My role is to make sure the system stays safe, identify any potential security problems, and update employee computers as needed. Below are examples of how I used SQL with filters to handle security-related tasks.

---

## 🔍 Retrieve Failed Login Attempts After Hours

There was a possible security issue after business hours (after 6:00 PM). All login attempts that failed during this time need to be reviewed.

**SQL Query Example:**

![PICTURE1](https://i.imgur.com/qj1TBlM.png)

This query filters for failed login attempts that happened after 6:00 PM. I selected all data from the `log_in_attempts` table and used a `WHERE` clause with an `AND` operator to show only failed attempts after business hours.

- `login_time > '18:00'` filters for attempts after 6:00 PM.
- `success = FALSE` filters for failed login attempts.

---

## 📅 Retrieve Login Attempts on Specific Dates

A suspicious event took place on **2022-05-09**. Any login activity from that day or the day before needs to be checked.

**SQL Query Example:**

![PICTURE2](https://i.imgur.com/ZnzDFOa.png)

This query returns all login attempts from **2022-05-09** or **2022-05-08** by using an `OR` operator.

- `login_date = '2022-05-09'`
- `login_date = '2022-05-08'`

---

## 🌐 Retrieve Login Attempts Outside of Mexico

Login attempts from countries outside of Mexico need to be investigated.

**SQL Query Example:**

![PICTURE3](https://i.imgur.com/5HKul1E.png)

This query returns all login attempts where the country is not Mexico. I used the `NOT` keyword with `LIKE 'MEX%'` to exclude all entries labeled as "MEX" or "MEXICO".

---

## 🧑‍💼 Retrieve Employees in Marketing (East Building)

My team needs to update computers for employees in the Marketing department located in the East building.

**SQL Query Example:**

![PICTURE4](https://i.imgur.com/uOVWw5x.png)

This query filters the `employees` table using `AND` with:

- `department = 'Marketing'`
- `office LIKE 'East%'` (to match office numbers in the East building)

---

## 💼 Retrieve Employees in Finance or Sales

Finance and Sales departments require a different type of security update. We need to gather information for employees in both departments.

**SQL Query Example:**

![PICTURE5](https://i.imgur.com/qEVq2T2.png)

This query filters for employees from:

- `department = 'Finance'`
- `department = 'Sales'`

Using the `OR` operator ensures results include both departments.

---

## 🚫 Retrieve All Employees Not in IT

A final security update is needed for employees **not** in the IT department.

**SQL Query Example:**

![PICTURE6](https://i.imgur.com/PPMZsRR.png)

This query uses `NOT` to exclude any employees from the Information Technology department.

---

## 🧾 Summary

I applied filters to SQL queries to gather specific information about login attempts and employee machines. I worked with two tables: `log_in_attempts` and `employees`. I used the `AND`, `OR`, and `NOT` operators to filter the necessary data. I also used `LIKE` with the `%` wildcard to match patterns.

---

## 📌 Tools & Concepts Used

- SQL filtering (`WHERE`, `AND`, `OR`, `NOT`)
- Pattern matching with `LIKE` and `%`
- Date and time filtering
- Data investigation for security analysis

---

## 📝 Notes

This project was created as part of a hands-on security data analysis practice exercise from Google Cybersecurity Certificate using SQL queries.
