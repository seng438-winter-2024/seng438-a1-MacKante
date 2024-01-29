# Exploratory Bug Reports

## Start ATM
### 1. Attempt using ATM without turning it on
- **Current State:** off
- **Steps to Reproduce:**
    1. Click on .jar file
    2. Press abuttons except `on`
- **Expected Outcome:** No response from buttons except `on` button
- **Actual Outcome:** Expected outcome

### 2. Turn on ATM machine
- **Current State:** off
- **Steps to Reproduce:**
    1. Click on `on` button
- **Expected Outcome:** ATM turns on and requests amount of bills
- **Actual Outcome:** Expected outcome

<br/>

## Authentication
### 1. Try using ATM withhout card:
- **Current State:** On
- **Steps to Reproduce:**
    1. just try to use it
- **Expected Outcome:** doesnt work
- **Actual Outcome:** expected

### 2. Entering incorrect credentials:
- **Current State:** On
- **Steps to Reproduce:**
    - Enter incorrect card number, ex. 3
    - Enter incorrect pin, 83
- **Expected Outcome:** No entry, go back to home
- **Actual Outcome:** System freezes

### 3. Entering correct credenials:
- **Current State:** On
- **Steps to Reproduce:**
    - Enter correct card number, 1 or 2
    - Enter incorrect pin, 42 or 1234
- **Expected Outcome:** Access granted for both
- **Actual Outcome:** Expected outcome

### 4. Account Number on display:
spoiler: its 1 more than its supposed to be
1 is 2, and 2 is 3

### 5. Card Number on Receipt (Account 1)
- **Current State:** on
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose any Transaction Type
- **Expected Outcome:**
    - card number is 1 in receipt
- **Actual Outcome:**
    - card number is 2 in receipt

### 6. Card Number on Receipt (Account 2)
- **Current State:** on
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose any Transaction Type
- **Expected Outcome:**
    - card number is 2 in receipt
- **Actual Outcome:**
    - card number is 3 in receipt

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
- **Actual Balance:** **`$100`**

### 2. To Money Market (Account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials1
    3. Choose deposit, then money market
    4. Enter ammount: 10 dollars
    5. press enter, then insert envelope
- **Expected Balance:** **`$5010`**
- **Actual Balance:** **`$5000`**available

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
- **Actual Balance:** **`$100`**available

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
- **Actual Balance:** **`$5010`**available

### 5. To Chequing (Account 1)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose deposit, then chequing account
    4. Enter ammount: 10 dollars
    5. press enter, then insert envelope
- **Expected Outcome:** available balance should be $110
- **Actual Outcome:** 100

### 6. To Savings (Account 1)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose deposit, then savings account
    4. Enter ammount: 10 dollars
- **Expected Outcome:** deposited $1010 to savings
- **Actual Outcome:** available balance is $1000

<br/>

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
        - total: $100
        - available: $80
- **Actual Outcome:**
    - $40:
        - amount: $40
        - total: $100
        - available: $60

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
        - Actual Amount: $40
        - Actual Total/Available Balance: $60
    - **Withdrawn:** $40
        - Actual Amount: $60
        - Actual Total/Available Balance: $40
    - **Withdrawn:** $60
        - Actual Amount: $100
        - Actual Total/Available Balance: $0
    - **Withdrawn:** $100
        - Insufficient Funds
    - **Withdrawn:** $200
        - Amount: $20 Withdrawn
        - Actual Total/Available Balance: $80

### 4. From Savings (Account 2)
- expected: invalid account
- actual: invalid

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
        - Actual Amount: $40
        - Actual Total/Available Balance: $4960
    - **Withdrawn:** $40
        - Actual Amount: $60
        - Actual Total/Available Balance: $4940
    - **Withdrawn:** $60
        - Actual Amount: $100
        - Actual Total/Available Balance: $4900
    - **Withdrawn:** $100
        - Actual Amount: $200
        - Actual Total/Available Balance: $4800
    - **Withdrawn:** $200
        - Amount: $20 Withdrawn
        - Actual Total/Available Balance: $4980

### 6. Click Button for Withdrawal Outside 1-5
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose withdraw, then chequing account
    4. Click 6, 7, 8, 9, or 0
- **Expected Outcome:** No response to buttons
- **Actual Outcome:** System freezes   

<br/>

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
- **Actual Outcome:** Chequing to Money Market, ammount is $99.50 dollars, available balance is $5099.50

### Money Market -> Chequing (Account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert card and put credentials
    3. Select Transfer
    4. Select Money Market to Checking
    5. Enter 100 dollars
- **Expected Outcome:** Money Market to chequing, amount is 100 dollars, available balance is $200.
- **Actual Outcome:** Money Market to chequing, ammount is $99.50 dollars, available balance is $199.50

### Savings (account 2)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert card and put credentials
    3. Select Transfer
    4. Select Savings to and from anywhere
- **Expected Outcome:** Invalid Account
- **Actual Outcome:** Invalid Account

<br/>

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

<br/>

## Transfering Money

### Savings -> Chequings (Account 1)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card 1 and put credentials
    3. Select Transfer
    4. Select Savings to Chequing
    5. Enter 10 dollars
- **Expected Outcome:** Saving to chequing, ammount is 10 dollars, available balance is $110.
- **Actual Outcome:** Chequing to Savings, ammount is $9.50 dollars, available balance is $109.50

### Chequings -> Savings (Account 1)
- **Current State:** On
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card 1 and put credentials
    3. Select Transfer
    4. Select Chequing to Saving
    5. Enter 10 dollars
- **Expected Outcome:** Chequing to Saving, ammount is 10 dollars, available balance is $1010.
- **Actual Outcome:** Saving to Chequing, ammount is $9.50 dollars, available balance is $1009.50

<br/>

## Account Inquiry
### 1. Account Inquiry from Chequing (Account 1)
- **Current State:** on
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose Balance Inquiry, then chequing account
- **Expected Outcome:**
    - total: $100
    - available: $100
    - card number is 1
- **Actual Outcome:**
    - total: $100
    - available: $100
    - card number is 2

### . Account Inquiry from Savings (Account 1)
- **Current State:** on
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose Balance Inquiry, then money market
- **Expected Outcome:**
    - Choose Savings
    - Prints Receipt with Inquiry from savings
    - Total and Available Balance should be $1000
    - Card Number is 1
- **Actual Outcome:**
    - Invalid Account Type

### 3. Account Inquiry from Chequing (Account 2)
- **Current State:** on
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose Balance Inquiry, then chequing account
- **Expected Outcome:**
    - total: $100
    - available: $100
    - card number is 2
- **Actual Outcome:**
    - total: $100
    - available: $100
    - card number is 3

### 4. Account Inquiry from Money Market (Account 2)
- **Current State:** on
- **Steps to Reproduce:**
    1. Turn on ATM Machine
    2. Insert Card and put credentials
    3. Choose Balance Inquiry, then money market
- **Expected Outcome:**
    - Choose Money Market
    - Prints Receipt with Inquiry from Money Market
    - Total and Available Balance should be $5000
    - Card Number is 2
- **Actual Outcome:**
    - Invalid account type


<br/>

- Pressing inputs other than display when trying to cancel
    - State: cancel balance inquiry prior to choosing account
    - Input: anything other than displayed inputs (1, 2)
    - Expected: do nothing
    - Actual: 
        User presses any pin number during cancellation, displays the ammount.
        User presses any pin number, displays the ammount before choosing a transaction type. Prints money dipensed in the log.