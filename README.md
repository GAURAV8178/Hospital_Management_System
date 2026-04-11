# 🏥 Hospital Management System — DBMS Capstone Project

---

## 📋 Project Overview

A fully relational **Hospital Management System** built using **MySQL**, designed to manage all core hospital operations — from patient admissions and surgical scheduling to billing, medicine inventory, and inter-department transfers.

The system models **13 entities** with proper primary keys, foreign keys, and constraints, and includes **30+ SQL queries** covering DDL, DML, joins, aggregates, and subqueries.

---

## 🎯 Objectives

- Design a schema to manage patient records including medical history, appointments, and treatments
- Implement queries to track patient admissions, discharges, and transfers between departments
- Handle complex queries for scheduling surgeries, managing hospital resources, and ensuring patient safety
- Track billing records, payment statuses, and generate financial summaries per admission
- Manage medicine inventory, prescriptions, and alert for low-stock or expiring medicines

---

## 🗂️ Database Schema

| Table | Key Columns |
|---|---|
| `Department` | dept_id (PK), dept_name, location, head_of_dept, contact_no |
| `Doctor` | doctor_id (PK), first_name, last_name, specialization, dept_id (FK) |
| `Patient` | patient_id (PK), first_name, last_name, dob, gender, blood_group |
| `Medical_History` | history_id (PK), patient_id (FK), condition_name, treatment *(weak entity)* |
| `Room` | room_id (PK), room_number, room_type (General/Private/ICU/Emergency/OT) |
| `Admission` | admission_id (PK), patient_id (FK), doctor_id (FK), room_id (FK), status |
| `Appointment` | appointment_id (PK), patient_id (FK), doctor_id (FK), appt_date, status |
| `Nurse` | nurse_id (PK), first_name, last_name, dept_id (FK), shift |
| `Surgery` | surgery_id (PK), patient_id (FK), doctor_id (FK), surgery_name, outcome |
| `Billing` | bill_id (PK), patient_id (FK), admission_id (FK), total_amount, payment_status |
| `Medicine` | medicine_id (PK), name, category, stock_qty, expiry_date |
| `Prescription` | prescription_id (PK), patient_id (FK), doctor_id (FK), medicine_id (FK) |
| `Transfer` | transfer_id (PK), patient_id (FK), from_dept_id (FK), to_dept_id (FK) |

---

## ⚙️ Tech Stack

- **Database:** MySQL 8.0+
- **Tool:** MySQL Workbench
- **Language:** SQL (DDL + DML)
- **Frontend:** HTML, CSS, JavaScript (Dashboard UI)

---

## 🚀 How to Run

1. Open **MySQL Workbench**
2. Go to `File → Open SQL Script` and select `hospital_management_system.sql`
3. Click **Execute All** (⚡)
4. The database `HospitalDB` will be created with all tables and sample data

```sql
-- Quick start
DROP DATABASE IF EXISTS HospitalDB;
CREATE DATABASE HospitalDB;
USE HospitalDB;
```

---

## 📁 Project Structure

```
hospital-management-system/
│
├── hospital_management_system.sql   # Full SQL — tables, data, queries
├── hospital_management_system.html  # Frontend dashboard (HTML/CSS/JS)
├── HMS_Capstone_Project.docx        # Formatted capstone submission document
└── README.md
```

---

## 🔍 SQL Queries Covered

| Category | Queries |
|---|---|
| Basic Retrieval | List all patients, doctors, available rooms, scheduled appointments |
| Admissions | Currently admitted patients, discharge summary, avg length of stay |
| Transfers | Full transfer history with from/to department details |
| Surgeries | Surgical schedule, surgeon-wise count, ongoing surgeries |
| Resources | Room utilization (occupied vs available by type) |
| Billing | Outstanding bills, total revenue, department-wise billing |
| Pharmacy | Low-stock medicines, expiring medicines, most prescribed drugs |
| Complex | Monthly admission trends, patient risk scoring, top billing patients |
| DML | Discharge patient, restock medicine, cancel appointment, update room status |

---

## 💡 Key Features

- ✅ **13 relational tables** with proper FK constraints and ENUMs
- ✅ **Weak entity** — `Medical_History` depends on `Patient` (CASCADE DELETE)
- ✅ **CRUD operations** — INSERT, SELECT, UPDATE, DELETE with real use cases
- ✅ **Aggregate queries** — GROUP BY, HAVING, AVG, SUM, COUNT
- ✅ **Subqueries** — patients in above-average-cost rooms
- ✅ **Multi-table JOINs** — up to 6 tables in a single query
- ✅ **Interactive dashboard** — fully functional HTML/CSS/JS UI with modals and live stats

---

## 🖥️ Frontend Dashboard

The included `hospital_management_system.html` is a standalone dashboard with:

- Live stats cards (patients, admissions, revenue, surgeries)
- 10 navigation sections — Patients, Doctors, Admissions, Appointments, Surgeries, Rooms, Billing, Medicines, Departments, Transfers
- Add/update/cancel operations via modals
- Animated bar charts and donut chart for room utilization
- Activity timeline and toast notifications

> Open directly in any browser — no server required.

---

## 📊 Sample Data Included

| Entity | Records |
|---|---|
| Departments | 8 |
| Doctors | 10 |
| Patients | 12 |
| Admissions | 8 |
| Appointments | 12 |
| Surgeries | 6 |
| Rooms | 10 |
| Medicines | 10 |
| Billing Records | 6 |
| Transfers | 3 |

---

## 📄 License

This project is submitted as an academic capstone for **ENCS254 — Database Management System** at K.R. Mangalam University. For educational use only.
