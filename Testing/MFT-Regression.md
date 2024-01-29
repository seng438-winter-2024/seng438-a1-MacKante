# Order of tests:
- Startup
- System shutdown
- Session
- Transaction
- Withdrawal
- Deposit
- Transfer
- Inquiry
- Invalid Pin

# Startup
### System is started when the switch is turned "on"
1. 
    - State: System is off
    - Input: Activate the "on" switch
    - Expected: System requests initial cash amount
    - Actual: Expected

### System accepts initial cash amount
2. 
    - State: System is requesting cash amount
    - Input: Enter a legitimate amount
    - Expected: System is on
    - Actual: Expected

### Connection to the bank is established
3. 
    - State: System has just been turned on
    - Input: Perform a legitimate inquiry transaction
    - Expected: System output should demonstrate that a connection has been established to the Bank
    - Actual: Expected
    
<br/>

# Shutdown
### System is shut down when the switch is turned “off"
4. 
    - State: System is on and not servicing a customer
    - Input: Activate the "off" switch
    - Expected: System is off
    - Actual: Expected

<br/>

# Session 
### System reads a customer's ATM card
5. 
    - State: System is on and not servicing a customer
    - Input: Insert a readable card
    - Expected: Card is accepted; System asks for entry of PIN
    - Actual: Expected

### System rejects an unreadable card
6. 
    - State: System is on and not servicing a customer
    - Input: Insert an unreadable card	
    - Expected: Card is ejected; System displays an error screen; System is ready to start a new session
    - Actual: Expected
### System accepts customer's PIN
7. 
    - State: System is asking for entry of PIN
    - Input: Enter a PIN
    - Expected: System displays a menu of transaction types
    - Actual: Expected

### System allows customer to perform a transaction
8. 
    - State: System is displaying menu of transaction types
    - Input: Perform a transaction
    - Expected: System asks whether customer wants another transaction
    - Actual: Expected

### System allows multiple transactions in one session
9. 
    - State: System is asking whether customer wants another transaction	
    - Input: Answer yes	
    - Expected: System displays a menu of transaction types	
    - Actual: Expected

### Session ends when customer chooses not to do another transaction
10. 
    - State: System is asking whether customer wants another transaction
    - Input: Answer no
    - Expected: System ejects card and is ready to start a new session
    - Actual: Expected

<br/>

# Transaction
### System handles an invalid PIN properly	
11. 
    - State: A readable card has been entered	
    - Input: Enter an incorrect PIN and then attempt a transaction	
    - Expected: The Invalid PIN exception is performed	
    - Actual: Expected

<br/>

# Withdrawal
<s>
### System asks customer to choose an account to withdraw from	
12.
    - State: Menu of transaction types is being displayed	
    - Input: Choose Withdrawal transaction	
    - Expected: System displays a menu of account types	
    - Actual: Shows accounts that card does not have
</s>

### System asks customer to choose a dollar amount to withdraw
13. 
    - State: Menu of account types is being displayed	
    - Input: Choose checking account	
    - Expected: System displays a menu of possible withdrawal amounts	
    - Actual: Expected

### System performs a legitimate withdrawal transaction properly
14. 
    - TESTED ALREADY, FAILS
    - spoiler: it works now

### System verifies that it has sufficient cash on hand to fulfill the request
15. 
    - State: System has been started up with less than the maximum withdrawal amount in cash on hand; System is requesting a withdrawal amount	
    - Input: Choose an amount greater than what the system currently has	
    - Expected: System displays an appropriate message and asks customer to choose a different amount	
    - Actual: Expected

### System verifies that customer's balance is sufficient to fulfill the request
16. 
    - State: System is requesting a withdrawal amount	
    - Input: Choose an amount that the system currently has but which is greater than the account balance	
    - Expected: System displays an appropriate message and offers customer the option of choosing to do another transaction or not.	
    - Actual: Expected

### A withdrawal transaction can be cancelled by the customer any time prior to choosing the account type
17. 
    - State: System is displaying menu of account types	
    - Input: Press "Cancel" key	
    - Expected: System displays an appropriate message and offers customer the option of choosing to do another transaction or not.	
    - Actual: Expected

### A withdrawal transaction can be cancelled by the customer any time prior to choosing the dollar amount
18. 
    - State: System is displaying menu of dollar amounts	
    - Input: Press "Cancel" key	
    - Expected: System displays an appropriate message and offers customer the option of choosing to do another transaction or not.	
    - Actual: Expected

<br/>

# Deposit
<s>### System asks customer to choose an account to deposit to
19.
    - State: Menu of transaction types is being displayed	
    - Input: Choose Deposit transaction	
    - Expected: System displays a menu of account types	
    - Actual: Shows accounts that card does not have
</s>

### System asks customer to enter a dollar amount to deposit	
20. 
    - State: Menu of account types is being displayed	
    - Input: Choose checking account	
    - Expected: System displays a request for the customer to type a dollar amount	
    - Actual: Expected

### System asks customer to insert an envelope	
21. 
    - State: System is displaying a request for the customer to type a dollar amount	
    - Input: Enter a legitimate dollar amount	
    - Expected: System requests that customer insert an envelope
    - Actual: Expected

### System performs a legitimate deposit transaction properly
22. 
    - State: System is requesting that customer insert an envelope	
    - Input: Insert an envelope	
    - Expected: System accepts envelope; System prints a correct receipt showing amount and correct updated balance; System records transaction correctly in the log (showing message to the bank, approval back, and acceptance of the envelope)
    - Actual: incorrect amounts 
    - ITS TAXING US bruh, but works actually deposits now

### A deposit transaction can be cancelled by the customer any time prior to inserting an envelope	
23. 
    - State: System is displaying menu of account types	
    - Input: Press "Cancel" key	
    - Expected: System displays an appropriate message and offers customer the option of choosing to do another transaction or not.
    - Actual: Expected
<br/><br/>

24. 
    - State: System is requesting customer to enter a dollar amount	
    - Input: Press "Cancel" key	
    - Expected: System displays an appropriate message and offers customer the option of choosing to do another transaction or not.
    - Actual: Expected
<br/><br/>

<s>25.
    - State: System is requesting customer to insert an envelope
    - Input: Press "Cancel" key	
    - Expected: System displays an appropriate message and offers customer the option of choosing to do another transaction or not.
    - Actual: Log shows transaction success (bad), but no actual money gets deposited (good)
</s>
<br/>

# Transfer
<s>
### System asks customer to choose an account to transfer from
26. 
    - State: 
    - Input: 
    - Expected: 
    - Actual: Shows accounts that card does not have
</s>

<s>
### System asks customer to choose an account to transfer to
27. 
    - State: Menu of transaction types is being displayed	
    - Input: Choose Transfer transaction	
    - Expected: System displays a menu of account types specifying transfer from
    - Actual: Shows accounts that card does not have
</s>

### System asks customer to enter a dollar amount to transfer
28. 
    - State: Menu of account types to transfer from is being displayed	
    - Input: Choose savings account	
    - Expected: System displays a request for the customer to type a dollar amount	
    - Actual: Expected

### System performs a legitimate transfer transaction properly
29. 
    - State: System is displaying a request for the customer to type a dollar amount	
    - Input: Enter a legitimate dollar amount	
    - Expected: System prints a correct receipt showing amount and correct updated balance; System records transaction correctly in the log (showing both message to the bank and approval back)	
    - Actual: Expected

### A transfer can be cancelled by the customer any time prior to entering an account type to transfer from  
30. 
    - State: System is displaying menu of account types menu of account types specifying transfer from
    - Input: Press "Cancel" key	
    - Expected: System displays an appropriate message and offers customer the option of choosing to do another	transaction or not.	
    - Actual: Expected
<br/><br/>

31. 
    - State: System is displaying menu of account types specifying transfer to	
    - Input: Press "Cancel" key	
    - Expected: System displays an appropriate message and offers customer the option of choosing to do another transaction or not.
    - Actual: Expected
<br/><br/>

32. 
    - State: System is requesting customer to enter a dollar amount	
    - Input: Press "Cancel" key	
    - Expected: System displays an appropriate message and offers customer the option of choosing to do another transaction or not.
    - Actual: Expected

# Inquiry
### System asks customer to choose an account to inquire about	
33. 
    - State: Menu of transaction types is being displayed	
    - Input: Choose Inquiry transaction	
    - Expected: System displays a menu of account types	
    - Actual: Shows accounts that account does not have

### System performs a legitimate inquiry transaction properly 
34. 
    - State: System is displaying menu of account types	
    - Input: Choose checking account	
    - Expected: System prints a correct receipt showing correct balance; System records transaction correctly in the log (showing both message to the bank and approval back)	
    - Actual: 
        - works for chequing, but not for savings (account 1)
        - works for account 2

### An inquiry transaction can be cancelled by the customer any time prior to choosing an account
35. 
    - State: System is displaying menu of account types	
    - Input: Press "Cancel" key	
    - Expected: System displays an appropriate message and offers customer the option of choosing to do another transaction or not.	
    - Actual: Expected

<br/>

# Invalid PIN
### Customer is asked to reenter PIN	
36. 
    - State: System is asking for entry of PIN	
    - Input: Enter an incorrect PIN; Attempt an inquiry transaction on the customer's checking account	
    - Expected: Customer is asked to re-enter PIN	
    - Actual: Expected

<s>### Correct re-entry of PIN is accepted
37.
    - State: Request to re-enter PIN is being displayed	
    - Input: Enter correct PIN	
    - Expected: Original transaction completes successfully	
    - Actual: Asks to re-enter PIN a third time
</s>
### Incorrect re-entry of PIN is not accepted	
38. 
    - State: Request to re-enter PIN is being displayed	
    - Input: Enter incorrect PIN	
    - Expected: An appropriate message is displayed and re-entry of the PIN is again requested	
    - Actual: Expected

<s>### Correct re-entry of PIN on the second try is accepted	
39.
    - State: Request to re-enter PIN is being displayed	
    - Input: Enter incorrect PIN the first time, then correct PIN the second time	
    - Expected: Original transaction completes successfully
    - Actual: Asks to re-enter PIN a third time
</s>
<s>### Correct re-entry of PIN on the third try is accepted
40. 
    - State: Request to re-enter PIN is being displayed	
    - Input: Enter incorrect PIN the first time and second times, then correct PIN the third time	
    - Expected: Original transaction completes successfully	
    - Actual: Asks to re-enter PIN a fourth time.
</s>