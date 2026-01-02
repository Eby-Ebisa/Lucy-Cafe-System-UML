classDiagram
    class User {
        +int userID
        +string name
        +string email
        +login()
    }

    class Customer {
        +string deliveryAddress
        +string phoneNumber
        +placeOrder()
    }

    class Driver {
        +string vehicleDetails
        +string currentLatLong
        +bool isAvailable
        +updateStatus()
    }

    class Order {
        +int orderID
        +datetime timestamp
        +string status
        +float totalAmount
        +calculateTotal()
    }

    class FoodItem {
        +int itemID
        +string name
        +float price
        +string category
    }

    class DeliveryDetails {
        +int deliveryID
        +datetime estimatedTime
        +string deliveryStatus
        +trackLocation()
    }

    User <|-- Customer
    User <|-- Driver
    Customer "1" --> "0..*" Order : places
    Order "1" *-- "1..*" FoodItem : contains
    Order "1" -- "1" DeliveryDetails : manages
    Driver "1" -- "0..*" DeliveryDetails : assigned_to
