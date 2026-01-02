### 1. Lucy Cafe Class Diagram
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
