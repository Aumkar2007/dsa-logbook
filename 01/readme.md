```mermaid
```mermaid
graph TD
    A([Start: Sorted Array]) --> B[Initialize Left = 0, Right = N-1]
    B --> C{Left < Right?}
    C -- No --> D([End: Return -1])
    C -- Yes --> E[Compute Sum = Array[Left] + Array[Right]]
    E --> F{Sum == Target?}
    F -- Yes --> G([End: Return Left, Right])
    F -- No --> H{Sum < Target?}
    H -- Yes --> I[Increment Left ++]
    H -- No --> J[Decrement Right --]
    I --> C
    J --> C
```

