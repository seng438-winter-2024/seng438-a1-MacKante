## Authentication
### 4. Account Number on display:
spoiler: its 1 more than its supposed to be
1 is 2, and 2 is 3

### 5. Card Number on Receipt (Account 1)
- Still an issue

### 6. Card Number on Receipt (Account 2)
- Still an issue

<br/>

## Deposit
### 1. To Chequing (Account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose deposit, then chequing account
    4. Enter ammount: 10 dollars
    5. press enter, then insert envelope
- **Expected Balance:** **`$110`**
- **Actual Balance:** **`$109.90`**

### 2. To Money Market (Account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials1
    3. Choose deposit, then money market
    4. Enter ammount: 10 dollars
    5. press enter, then insert envelope
- **Expected Balance:** **`$5010`**
- **Actual Balance:** **`$5009.90`**

### 3. 2 Consecutive to Chequing<br/>(Account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose deposit, then money market
    4. Enter ammount: 10 dollars
    5. press enter, then insert envelope
    6. Select 1 to perform another transaction
    7. Repeat steps 3-5
- **Expected Balance:** **`$120`**
- **Actual Balance:** **`$119.80`**

### 4. 2 Consecutive to Money Market<br/>(Account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose deposit, then money market
    4. Enter ammount: 10 dollars
    5. press enter, then insert envelope
    6. Select 1 to perform another transaction
    7. Repeat steps 3-5
- **Expected Balance:** **`$5020`**
- **Actual Balance:** **`$5019.80`**available

### 5. To Chequing (Account 1)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose deposit, then chequing account
    4. Enter ammount: 10 dollars
    5. press enter, then insert envelope
- **Expected Outcome:** balance should be $110
- **Actual Outcome:** 109.90

### 6. To Savings (Account 1)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose deposit, then savings account
    4. Enter ammount: 10 dollars
- **Expected Outcome:** deposited $1010 to savings
- **Actual Outcome:** available balance is $1009.90

--------------------------------------------------------------------------------------

## Withdrawal
### 1. Withdrawing money from savings (Account 1)
- **Current State:** on
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose withdraw, then chequing account
    4. Choose ammount 20
- **Expected Outcome:**
    - $20:
        - amount: $20
        - total: $1000
        - available: $980
- **Actual Outcome:**
    - $40:
        - amount: $40
        - total: $1000
        - available: $960

### 2. Withdrawing money from chequing (Account 1)
- **Current State:** on
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose withdraw, then chequing account
    4. Choose ammount 20
- **Expected Outcome:**
    - $20:
        - amount: $20
        - total: $80
        - available: $80
- **Actual Outcome:**
    - $20:
        - amount: $20
        - total: $80
        - available: $80

### 3. From Chequing (Account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose withdraw, then chequing account
    4. Choose amount...
- **Expected Outcome:**
    - **Withdrawn:** $20
        - Expected Amount: $20
        - Expected Total/Available Balance: $80
    - **Withdrawn:** $40
        - Expected Amount: $40
        - Expected Total/Available Balance: $60
    - **Withdrawn:** $60
        - Expected Amount: $60
        - Expected Total/Available Balance: $40
    - **Withdrawn:** $100
        - Expected Amount: $100
        - Expected Total/Available Balance: $0
    - **Withdrawn:** $200
        - Insufficient Funds
- **Actual Outcome:**
    - **Withdrawn:** $20
        - Actual Amount: $20
        - Actual Total/Available Balance: $80
    - **Withdrawn:** $40
        - Actual Amount: $40
        - Actual Total/Available Balance: $60
    - **Withdrawn:** $60
        - Actual Amount: $60
        - Actual Total/Available Balance: $40
    - **Withdrawn:** $100
        - Actual Amount: $100
        - Actual Total/Available Balance: $0
    - **Withdrawn:** $200
        - Insufficient Funds

### 5. From Money Market (Account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose withdraw, then money marke account
    4. Choose amount...
- **Expected Outcome:**
    - **Withdrawn:** $20
        - Expected Amount: $20
        - Expected Total/Available Balance: $4980
    - **Withdrawn:** $40
        - Expected Amount: $40
        - Expected Total/Available Balance: $4960
    - **Withdrawn:** $60
        - Expected Amount: $60
        - Expected Total/Available Balance: $4940
    - **Withdrawn:** $100
        - Expected Amount: $100
        - Expected Total/Available Balance: $4900
    - **Withdrawn:** $200
        - Expected Amount: $200
        - Expected Total/Available Balance: $4800
- **Actual Outcome:**
    - **Withdrawn:** $20
        - Actual Amount: $20
        - Actual Total/Available Balance: $4980
    - **Withdrawn:** $40
        - Actual Amount: $40
        - Actual Total/Available Balance: $4960
    - **Withdrawn:** $60
        - Actual Amount: $60
        - Actual Total/Available Balance: $4940
    - **Withdrawn:** $100
        - Actual Amount: $100
        - Actual Total/Available Balance: $4900
    - **Withdrawn:** $200
        - Amount: $200 Withdrawn
        - Actual Total/Available Balance: $4800

### 6. Click Button for Withdrawal Outside 1-5
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose withdraw, then chequing account
    4. Click 6, 7, 8, 9, or 0
- **Expected Outcome:** No response to buttons
- **Actual Outcome:** as expected

------------------------------------------------------------------------------

## Transfer
### Chequing -> Money Market (Account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert card and put credentials
    3. Select Transfer
    4. Select Chequing to Money Market
    5. Enter 100 dollars
- **Expected Outcome:** Chequing to Money Market, amount is 100 dollars, available balance is $5100.
- **Actual Outcome:** Chequing to Money Market, ammount is $100 dollars, available balance is $5100

### Money Market -> Chequing (Account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert card and put credentials
    3. Select Transfer
    4. Select Money Market to Checking
    5. Enter 100 dollars
- **Expected Outcome:** Money Market to chequing, amount is 100 dollars, available balance is $200.
- **Actual Outcome:** Money Market to chequing, ammount is $100 dollars, available balance is $200

### Savings (account 2)
- **Current State:** On
- **Steps to Reproduce:**1
    1. Turn on ATM Machine
    2. Insert card and put credentials
    3. Select Transfer
    4. Select Savings to and from anywhere
- **Expected Outcome:** Invalid Account
- **Actual Outcome:** Invalid Account

-------------------------------------------------------------------------------------

## Balance Inquiry
### Try to check balance (Account 1)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert card and put credentials
    3. Select Balance Inquiry
    4. Select Savings
- **Expected Outcome:** Show Savings account info in logs
- **Actual Outcome:** Displays Failure Screen

--------------------------------------------------------------------------------------------------