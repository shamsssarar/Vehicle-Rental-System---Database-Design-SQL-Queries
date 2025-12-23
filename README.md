# Vehicle Rental System – Database Design & SQL Queries

## 📌 Project Overview
This project implements a **Vehicle Rental System** database using relational database design principles.  
It focuses on **ERD design**, **primary & foreign key relationships**, and **SQL queries** using JOIN, EXISTS, WHERE, GROUP BY, and HAVING clauses.

The system manages:
- Users (Admins and Customers)
- Vehicles (Cars, Bikes, Trucks)
- Bookings (Vehicle rentals made by users)

---

## 🎯 Objectives
By completing this project, the following concepts are:

- Designing an ERD with One-to-Many and logical One-to-One relationships
- Understanding and applying Primary Keys and Foreign Keys
- Writing SQL queries using:
  - INNER JOIN
  - NOT EXISTS
  - WHERE
  - GROUP BY and HAVING

---

## 🗂️ Database Design (ERD Explanation)

The database consists of **three main tables**:

### 1️⃣ Users
Stores system users (Admin or Customer).

**Key Fields:**
- `user_id` (Primary Key)
- `email` (Unique)
- `role` (Admin / Customer)

Each user can make **multiple bookings**.

---

### 2️⃣ Vehicles
Stores vehicles available for rent.

**Key Fields:**
- `vehicle_id` (Primary Key)
- `registration_no` (Unique)
- `vehicle_type` (car / bike / truck)
- `availability_status` (available / rented / maintenance)

Each vehicle can appear in **multiple bookings over time**.

---

### 3️⃣ Bookings
Stores rental bookings made by users.

**Key Fields:**
- `booking_id` (Primary Key)
- `user_id` (Foreign Key → Users)
- `vehicle_id` (Foreign Key → Vehicles)
- `start_date`, `end_date`
- `booking_status`
- `total_cost`

---

### 🔗 Relationships
- **Users → Bookings**: One-to-Many  
  (One user can make multiple bookings)
- **Vehicles → Bookings**: One-to-Many  
  (One vehicle can be booked multiple times)
- **Logical One-to-One**:  
  Each booking record connects **exactly one user and one vehicle**, enforced using NOT NULL foreign keys.

---

## 🧩 Business Rules Implemented
- Each user email must be unique
- Each vehicle registration number must be unique
- A booking must belong to exactly one user and one vehicle
- Vehicles have availability status tracking
- Bookings track rental duration, status, and total cost

---

## 🧪 SQL Queries

All required queries are included in **`queries.sql`**.

### Query 1: INNER JOIN
Retrieve booking details along with customer name and vehicle name.

### Query 2: NOT EXISTS
Find vehicles that have **never been booked**.

### Query 3: WHERE
Retrieve all **available vehicles** of a specific type (e.g., cars).

### Query 4: GROUP BY & HAVING
Find vehicles that have **more than 2 bookings**.

---

## 📁 Project Structure
