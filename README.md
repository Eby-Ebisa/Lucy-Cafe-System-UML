
# Lucy Cafe Food Delivery System

## 🌟 Project Introduction
Lucy Cafe is a specialized food and drink delivery platform designed exclusively for the **Arba Minch University (AMU) Main Campus**. The system bridges the gap between the campus cafe and the university community, providing a seamless ordering experience for both students and staff.

The platform is tailored to the unique geography of the AMU campus, ensuring that food reaches students in their specific **Dorm Blocks** and instructors in their **Condominiums or Offices**. By integrating local digital payment solutions, the system eliminates the need for cash and speeds up the delivery process.

---

## 🛠️ Technical Features
* **Role-Based Access Control (RBAC):** Distinct interfaces and permissions for Students, Instructors, Drivers, and System Administrators.
* **Location-Specific Routing:** Automated destination tracking for AMU landmarks, including Dormitory Blocks, Faculty Condominiums, and Administrative Offices.
* **Business Logic Restrictions:** Built-in validation to enforce campus rules (e.g., Drink items are exclusive to Instructor accounts).
* **Digital Payment Integration:** Secure payment processing through **CBE Birr** and **Telebirr** APIs.
* **Real-Time Order Tracking:** A state-managed lifecycle that tracks orders from "Pending" through "AMU Main Gate" to "Delivered."

---
```mermaid
classDiagram
    %% --- CLASSES FOR AMU CAMPUS ---
    class User {
        +int userID
        +string name
        +login()
    }
    class Admin {
        +manageMenu()
        +viewReports()
    }
    class Student {
        +string dormNumber
        +string block
    }
    class Instructor {
        +string condoNumber
        +string officeNumber
    }
    class Driver {
        +string vehicleID
        +bool isAvailable
        +markDelivered()
    }
    class Order {
        +int orderID
        +string locationType
        +bool hasDrinks
    }
    class FoodItem {
        +string name
        +float price
    }
    class DrinkItem {
        +string type
        +bool isAlcoholic
    }
    class Payment {
        +int transactionID
        +string provider
        +processCBE()
        +processTelebir()
    }

    %% --- RELATIONSHIPS ---
    User <|-- Admin
    User <|-- Student
    User <|-- Instructor
    User <|-- Driver
    Student "1" -- "0..*" Order : orders_food_only
    Instructor "1" -- "0..*" Order : orders_food_and_drinks
    Order "1" *-- "1..*" FoodItem : includes
    Order "1" *-- "0..*" DrinkItem : includes
    Order "1" -- "1" Payment : via_CBE_Telebir
    Driver "1" -- "0..*" Order : delivers_to_AMU
```



```mermaid
graph LR
    %% --- ACTORS ---
    S((Student))
    I((Instructor))
    A((Admin))
    D((Driver))

    subgraph "Lucy Cafe AMU Delivery System"
        UC1(Browse Food Menu)
        UC2(Order Food)
        UC3(Order Drinks - Instructors Only)
        UC4(Pay via CBE or Telebir)
        UC5(Manage Inventory & Users)
        UC6(Delivery to Dorm/Condo/Office)
    end

    %% --- CONNECTIONS ---
    S --- UC1
    S --- UC2
    S --- UC4
    S --- UC6

    I --- UC1
    I --- UC2
    I --- UC3
    I --- UC4
    I --- UC6

    D --- UC6
    A --- UC5
```

### 3. Order Lifecycle (State Diagram)
```mermaid
stateDiagram-v2
    [*] --> Pending : Customer places order
    
    state Payment_Branch <<choice>>
    Pending --> Payment_Branch
    
    Payment_Branch --> Cancelled : Payment Failed
    Payment_Branch --> Paid : CBE/Telebir Success
    
    Paid --> Preparing : Kitchen receives order
    Preparing --> ReadyForPickup : Food/Drink is ready
    
    ReadyForPickup --> OutForDelivery : Driver accepts
    
    state OutForDelivery {
        [*] --> AtAMUMainGate
        AtAMUMainGate --> FindingLocation : Dorm/Condo/Office
    }
    
    OutForDelivery --> Delivered : Customer receives order
    Delivered --> [*]
    Cancelled --> [*]
```
