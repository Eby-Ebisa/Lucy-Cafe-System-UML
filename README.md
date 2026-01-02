---
title: Lucy Cafe Food Delivery System
---
```mermaid
classDiagram
    %% --- CLASSES ---
    class User {
        +int userID
        +string name
        +string email
        +login()
        +logout()
    }

    class Customer {
        +string address
        +string phone
        +browseMenu()
        +placeOrder()
    }

    class Driver {
        +string vehicleID
        +bool isAvailable
        +updateLocation()
        +completeDelivery()
    }

    class Order {
        +int orderID
        +string status
        +float totalAmount
        +updateStatus()
        +cancelOrder()
    }

    class MenuItem {
        +int itemID
        +string name
        +float price
        +string category
    }

    class Payment {
        +int paymentID
        +string method
        +float amount
        +process()
    }

    %% --- RELATIONSHIPS ---
    User <|-- Customer : Inherits
    User <|-- Driver : Inherits
    Customer "1" --> "0..*" Order : places
    Order "1" *-- "1..*" MenuItem : contains
    Order "1" -- "1" Payment : paid_by
    Order "1" -- "0..1" Driver : assigned_to
```
---
title: Delivery Flow (Sequence Diagram)
---
sequenceDiagram
    participant C as Customer
    participant S as Cafe System
    participant D as Driver

    C->>S: Places Order & Pays
    S-->>C: Order Confirmed
    S->>S: Preparing Food...
    S->>D: Dispatch Request
    D->>S: Accept Delivery
    S-->>C: Driver Out for Delivery
    D->>C: Food Delivered
    D->>S: Update Status: Completed
