# Task 1: ATM System Design

## System Description
This project simulates the logic of a standard Automatic Teller Machine (ATM). The system follows a structured flow to ensure secure and accurate banking transactions.

### Key Features:
- **PIN Verification:** Users must enter a valid PIN to access the system.
- **Main Menu:** Offers four primary options:
  1. **Check Balance:** Displays the current account balance.
  2. **Deposit:** Allows users to add funds to their account.
  3. **Withdraw:** Enables cash withdrawal after checking for sufficient funds.
  4. **Exit:** Safely logs out the user and terminates the session.
- **Error Handling:** Provides feedback for invalid PINs or insufficient balance during withdrawal.

## Design Tools
- **Graphviz (DOT):** Used for creating a professional, structured architectural flowchart.
- **Mermaid:** Used for a developer-friendly, markdown-compatible flow diagram.
- **Pseudocode:** Written in plain English to describe the logic step-by-step before visualization.

## Personal Notes
- During this task, I focused on creating a loop-based logic where the user returns to the main menu after each transaction until they choose to exit.
- Ensuring the "Insufficient Funds" check was a critical logic step in the withdrawal process.
- Using both DOT and Mermaid helped me understand the differences between static graph generation and live markdown-based rendering.

## How to View Diagrams
1. Open `flowchart dot.png` to see the Graphviz output.
2. Open `flowchart mermaid.png` to see the Mermaid Live output.
3. Raw codes are available in `flowchart.dot` and `flowchart.mmd`.
