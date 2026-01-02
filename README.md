graph LR
    A[User Input] --> B{Valid?}
    B -- No --> C[Error Message]
    B -- Yes --> D[Process Data]
    D --> E[Update Database]
    E --> F[Success Notification]
