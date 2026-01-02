# 📚 Full Project Documentation: Lucy Cafe AMU Delivery System

## 📖 Table of Contents
1. [General Definition](#1-general-definition)
2. [Problem Statement: The "Before" System](#2-problem-statement-the-before-system)
3. [The Solution: Digital Transformation](#3-the-solution-digital-transformation)
4. [Project Scope](#4-project-scope)
5. [Actor Responsibilities](#5-actor-responsibilities)
6. [Functional Requirements & Business Logic](#6-functional-requirements--business-logic)
7. [System Workflow](#7-system-workflow)
8. [Security & Data Integrity](#8-security--data-integrity)
9. [Technical Implementation Notes](#9-technical-implementation-notes)
10. [Glossary of Terms](#10-glossary-of-terms)

---

## 1. General Definition
The **Lucy Cafe Delivery System** is an integrated software and logistics solution designed to automate the food and beverage ordering process at **Arba Minch University (AMU)**. Unlike standard delivery apps, this system is architected to handle the complex "micro-geography" of a university campus, ensuring accurate delivery to dormitories and faculty residences while integrating with local Ethiopian payment gateways.

## 2. Problem Statement: The "Before" System
Prior to the implementation of this system, Lucy Cafe operated as a traditional walk-in cafe with no delivery infrastructure. The AMU community faced several challenges:

* **🚩 Time Inefficiency**: Students in far blocks (like Abaya or Chamo) and instructors in condos had to walk long distances just to get a meal.
* **🚩 Crowd Congestion**: During peak hours, the physical cafe became overcrowded, leading to long wait times and poor service quality.
* **🚩 Limited Reach**: The cafe could only serve people physically present, losing revenue from busy staff or students studying in dorms.
* **🚩 Cash-Only Risks**: Physical cash handling was slow, prone to errors, and required customers to visit ATMs frequently.
* **🚩 Manual Communication**: There was no way to know if food was "Out of Stock" until the customer arrived at the counter.

## 3. The Solution: Digital Transformation
Your UML-designed system solves these problems by introducing a structured digital logistics layer:

* **✅ Distance Bridging**: Defined a **Driver actor** in the Use Case Diagram to move the cafe to a "we-come-to-you" model.
* **✅ Payment Modernization**: Integrated **CBE Birr and Telebirr** in the State Diagram to eliminate cash risks and speed up transactions.
* **✅ Precise Navigation**: Included `dormNumber` and `officeNumber` in the SQL Schema to ensure door-to-door delivery.
* **✅ Inventory Visibility**: Used the **Class Diagram** to manage menu availability in real-time.
* **✅ Status Transparency**: Implemented an **Order Lifecycle** (State Diagram) so students know exactly when food is at the AMU Main Gate.



## 4. Project Scope
The system handles:
* **User Authentication**: Secure role-based login for Students, Instructors, Drivers, and Admins.
* **Order Processing**: Real-time management of food and drinks from selection to delivery.
* **Payment Integration**: Seamless transaction handling via CBE Birr and Telebirr.
* **Delivery Logistics**: Directing drivers to specific AMU landmarks like Dorm Blocks and Faculty Condos.

## 5. Actor Responsibilities
* **Student**: Browses food menus, places orders to dormitories, and processes digital payments.
* **Instructor**: Accesses the full menu (including drinks), places orders to condos/offices.
* **Driver**: Receives delivery tasks, navigates the campus,
