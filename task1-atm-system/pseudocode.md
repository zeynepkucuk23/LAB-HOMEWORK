 Pseudocode in plain English

# ATM System Pseudocode

1.  **START**
2.  **DISPLAY** "Please insert your card."
3.  **READ** Card input.
4.  **PROMPT** user to "Enter PIN."
5.  **READ** PIN input.
6.  **IF** PIN is correct:
    * **DISPLAY** Main Menu (1. Check Balance, 2. Withdraw Cash, 3. Deposit Cash, 4. Exit).
    * **WAIT** for user selection.
    
    * **IF** User selects "Check Balance":
        * **DISPLAY** "Your current balance is: [Balance Amount]"
        * **GO TO** Step 6 (Main Menu).

    * **IF** User selects "Withdraw Cash":
        * **PROMPT** "Enter amount to withdraw."
        * **READ** withdrawal amount.
        * **IF** amount <= Current Balance:
            * **SUBTRACT** amount from Balance.
            * **DISPENSE** cash.
            * **DISPLAY** "Transaction successful. New balance: [Balance]."
        * **ELSE**:
            * **DISPLAY** "Insufficient funds."
        * **GO TO** Step 6 (Main Menu).

    * **IF** User selects "Deposit Cash":
        * **PROMPT** "Insert cash into the slot."
        * **READ** deposited amount.
        * **ADD** amount to Balance.
        * **DISPLAY** "Deposit successful. New balance: [Balance]."
        * **GO TO** Step 6 (Main Menu).

    * **IF** User selects "Exit":
        * **GO TO** Step 8.

7.  **ELSE** (If PIN is incorrect):
    * **DISPLAY** "Invalid PIN. Please try again."
    * **REPEAT** Step 4 (Up to 3 attempts).
    * **IF** 3 attempts fail:
        * **DISPLAY** "Card blocked. Please contact your bank."
        * **GO TO** Step 8.

8.  **EJECT** Card.
9.  **DISPLAY** "Thank you for using our ATM. Have a nice day!"
10. **END**
