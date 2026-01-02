# 📚 Full Project Documentation: Lucy Cafe AMU Delivery System

## 📖 Table of Contents
1. [General Definition](#1-general-definition)
2. [Project Scope](#2-project-scope)
3. [Actor Responsibilities](#3-actor-responsibilities)
4. [Functional Requirements & Business Logic](#4-functional-requirements--business-logic)
5. [System Workflow](#5-system-workflow)
6. [Security & Data Integrity](#6-security--data-integrity)
7. [Technical Implementation Notes](#7-technical-implementation-notes)
8. [Glossary of Terms](#8-glossary-of-terms)

---

## 1. General Definition
The **Lucy Cafe Delivery System** is an integrated software and logistics solution designed to automate the food and beverage ordering process at **Arba Minch University (AMU)**. Unlike standard delivery apps, this system is architected to handle the complex "micro-geography" of a university campus, ensuring accurate delivery to dormitories and faculty residences while integrating with local Ethiopian payment gateways.

## 2. Project Scope
The system handles:
* **User Authentication**: Secure role-based login for Students, Instructors, Drivers, and Admins.
* **Order Processing**: Real-time management of food and drinks from selection to delivery.
* **Payment Integration**: Seamless transaction handling via CBE Birr and Telebirr.
* **Delivery Logistics**: Directing drivers to specific AMU landmarks like Dorm Blocks and Faculty Condos.

## 3. Actor Responsibilities
* **Student**: Browses food menus, places orders to dormitories, and processes digital payments.
* **Instructor**: Accesses the full menu (including drinks), places orders to condos/offices.
* **Driver**: Receives delivery tasks, navigates the campus, and updates order status to "Delivered."
* **Admin**: Manages menu inventory, pricing, user accounts, and views financial reports.

## 4. Functional Requirements & Business Logic
To ensure the system aligns with university policies, the following logic is implemented:
* **Role-Based Item Filtering**: If a user is identified as a `Student`, the system automatically hides alcohol/drink categories to comply with campus regulations.
* **Location Mapping**: The system uses a static landmark database (e.g., "Abaya Campus Block 75") to ensure accuracy where GPS might be unreliable.
* **Order Expiry**: Orders not paid within 15 minutes are automatically cancelled to prevent kitchen waste.

## 5. System Workflow
1. **Selection**: User picks items from the menu.
2. **Validation**: System verifies user permissions based on their role.
3. **Payment**: User completes a Telebirr or CBE transaction.
4. **Preparation**: The Lucy Cafe kitchen receives and prepares the order.
5. **Delivery**: A driver is assigned, picks up the order, and navigates to the AMU location.
6. **Completion**: Order is marked "Delivered" and the transaction is closed.

##
