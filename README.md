# Lucy Cafe Food Delivery System

## 1. Use Case Diagram
```mermaid
graph LR
    subgraph Actors
        C((Customer))
        S((Staff))
    end
    subgraph System
        UC1(Place Order)
    end
    C --- UC1
    S --- UC1
