```mermaid
classDiagram
    %% --- CLASSES ---
    class User {
        +int userID
        +string name
        +login()
    }

    class Admin {
        +manageMenu()
        +viewReports()
        +resolveDisputes()
    }

    class Customer {
        +string campusRole
        +placeOrder()
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
        +string vehicleType
        +bool isAvailable
        +markDelivered()
    }

    class Order {
        +int orderID
        +string destinationType
        +float totalAmount
        +checkDrinkRestriction()
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

    %% --- RELATIONSHIPS & LOGIC ---
    User <|-- Admin
    User <|-- Customer
    User <|-- Driver
    Customer <|-- Student
    Customer <|-- Instructor

    Customer "1" -- "0..*" Order : places
    Order "1" *-- "1..*" FoodItem : includes
    Order "1" *-- "0..*" DrinkItem : includes
    Order "1" -- "1" Payment : via CBE/Telebir
    
    Admin "1" -- "0..*" User : manages
    Driver "1" -- "0..*" Order : delivers_to_AMU
```

```mermaid
useCaseDiagram
    actor Student
    actor Instructor
    actor Admin
    actor Driver

    package "Lucy Cafe AMU Delivery" {
        usecase "Browse Food Menu" as UC1
        usecase "Order Food" as UC2
        usecase "Order Drinks" as UC3
        usecase "Pay via CBE/Telebir" as UC4
        usecase "Manage Inventory" as UC5
        usecase "Track Delivery to Dorm/Condo" as UC6
    }

    Student --> UC1
    Student --> UC2
    Student --> UC4
    Student --> UC6

    Instructor --> UC1
    Instructor --> UC2
    Instructor --> UC3
    Instructor --> UC4
    Instructor --> UC6

    Driver --> UC6
    Admin --> UC5
```
