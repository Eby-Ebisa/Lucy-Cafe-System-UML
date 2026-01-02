graph LR
    %% GREEN: Define the Users (Actors)
    subgraph Actors
        C((Customer))
        S((Cafe Staff))
        D((Delivery Driver))
        A((Admin))
    end

    %% GREEN: Define the System Features
    subgraph "Lucy Cafe System"
        UC1(Browse Menu)
        UC2(Place Order)
        UC3(Process Payment)
        UC4(Manage Inventory)
        UC5(Track Order Status)
        UC6(Prepare Food)
        UC7(Update Delivery)
    end

    %% GREEN: Connecting Actors to their specific Actions
    C --- UC1
    C --- UC2
    C --- UC5
    S --- UC4
    S --- UC6
    D --- UC7
    A --- UC4

    %% GREEN: Logic showing Payment is part of the Order process
    UC2 -.->|include| UC3
