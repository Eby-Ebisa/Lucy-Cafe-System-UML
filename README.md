graph LR
    %% Actors
    subgraph Actors
        C((Customer))
        S((Cafe Staff))
        D((Delivery Driver))
        A((Admin))
    end

    %% System Boundary
    subgraph "Lucy Cafe System"
        UC1(Browse Menu)
        UC2(Place Order)
        UC3(Process Payment)
        UC4(Manage Inventory)
        UC5(Track Order)
        UC6(Prepare Food)
        UC7(Update Delivery)
    end

    %% Connections
    C --- UC1
    C --- UC2
    C --- UC5
    S --- UC4
    S --- UC6
    D --- UC7
    A --- UC4

    %% Include Relationship
    UC2 -.->|include| UC3
