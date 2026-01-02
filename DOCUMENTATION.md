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
To make your project look like a high-level engineering solution, you should frame it as a Digital Transformation. Since the previous Lucy Cafe had no delivery system, customers had to walk to the cafe, wait in long lines, and pay with cash.

Here is the professional breakdown of the problems and how your new system solves them.

🚩 Problem Statement (The "Before")
Without a delivery system, the AMU community faced these significant challenges:

Time Inefficiency: Students in far blocks (like Abaya or Chamo) and instructors in condos had to walk long distances just to get a meal.

Crowd Congestion: During lunch and dinner peaks, the physical cafe became overcrowded, leading to long wait times and poor service.

Limited Reach: The cafe could only serve people physically present, losing potential revenue from busy staff or students studying in dorms.

Cash-Only Risks: Physical cash handling is slow, prone to errors, and requires customers to always have exact change or visit an ATM first.

Manual Communication: There was no way to know if a specific food item was "Out of Stock" until the customer arrived at the counter.

✅ Your Solution (The "After")
Your UML-designed system solves these by introducing a structured digital logistics layer:

Distance Bridging: The Use Case Diagram defines a "Driver" actor, moving the cafe from a "come-to-us" model to a "we-come-to-you" model.

Payment Modernization: By integrating CBE Birr and Telebirr in your State Diagram, you've eliminated the need for physical cash and reduced transaction time to seconds.

Precise Navigation: Your SQL Schema includes dormNumber and officeNumber, ensuring food isn't just "sent to campus" but delivered to a specific door.

Inventory Visibility: The Class Diagram includes a FoodItem class with price and type, which allows the system to show only what is currently available.

Status Transparency: The Order Lifecycle (State Diagram) lets students know exactly where their food is (e.g., "At AMU Main Gate"), reducing anxiety and phone calls to the cafe.

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
