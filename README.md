# Coffee Vending Machine: Theory of Computation

## Problem Statement
Implement a Finite State Machine (FSM) for a vending machine that sells beverages, incorporating user interactions, potential errors, and appropriate feedback for a smooth experience.

## Methodology
1. **Initial State**: The machine waits for user interaction.
2. **Welcome State**: Displays available beverage options (coffee, tea, milk, hot chocolate).
3. **Selection**: User selects a beverage.
4. **Payment State**: Options for cash or UPI are presented.
   - **Cash Payment**: User inserts required cash ($5).
   - **Card Payment**: User enters a 4-bit PIN.
5. **Dispensing State**: Selected beverage is dispensed.
6. **Transaction Complete**: Displays completion message or prompts for re-selection if out of stock or payment fails.

## Alphabet Set
- **Actions (Σ)**: {w, l, c, b, q, g, a, n, d, K, o, v, t, y, s, i, j, z}
- **Events**: {r1, r2,..., r13}

## Grammar
- **Non-terminals (V)**: {A, B, C, D, E, F, G, H, I, J, K}
- **Terminals (T)**: {w, l, c, b, q, g, a, n, d, K, o, v, t, y, s, i, j, z, λ}
- **Starting Symbol (S)**: {A}

## Transition States
| Transition | From State | Input | To State       |
|------------|------------|-------|----------------|
| 1          | Start      | B     | Service        |
| 2          | Start      | S     | Select         |
| 3          | Select     | T     | Thumps Up      |
| 4          | Select     | C     | Coke           |
| 5          | Select     | M     | Mirinda        |
| 6          | Select     | H     | Red Bull       |
| 7          | Service    | L     | Start          |
| 8          | Thumps Up  | L     | Unavailable     |
| 9          | Coke       | L     | Unavailable     |
| 10         | Mirinda    | L     | Unavailable     |
| 11         | Red Bull   | L     | Unavailable     |
| 12         | Unavailable | L    | Service        |
| 13         | Thumps Up  | L     | Payment        |
| ...        | ...        | ...   | ...            |

## Turing Machine States
- Start
- Selecting
- Dispensing
- Insufficient Funds
- Complete
- Refund
- Service

## Input Symbols
- B: Button Press
- S: Selecting Beverage
- T: Thumps Up
- C: Coke
- M: Mirinda
- H: Red Bull
- N: Not Available
- F: Payment Failed
- U: UPI
- G: Cash

## Conclusion
The FSM for the coffee vending machine effectively manages user interactions and errors to ensure a smooth experience. This design serves as a reference for future research in vending machine technology.
