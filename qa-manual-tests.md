### Test Case 01 : Unauthorized Access to Live Betting Page

###### PRECONDITIONS
- User is NOT logged in

###### TEST STEPS
- Enter Live Betting page URL directly in browser

###### EXPECTED RESULT
- User is redirected to Login page
- Live betting data is NOT accessible

STATUS : Pass / Fail


### Test Case 02 : Successful Bet Placement

###### PRECONDITIONS
- User is logged in
- Wallet balance = 100
- Active live football match available

###### TEST STEPS
- Navigate to Live Betting page
- Select active football match
- Select valid betting market (Match Winner)
- Select outcome
- Enter stake = 25
- Click "Place Bet"
- Confirm bet

###### EXPECTED RESULT
- Bet is successfully placed
- Confirmation message is displayed
- Bet ID is generated
- Wallet balance becomes 75
- Bet visible under "My Bets"

STATUS : Pass / Fail


### Test Case 03 : Insufficient Balance Validation

###### PRECONDITIONS
- User is logged in
Wallet balance = 10
Active market available

###### TEST STEPS
- Navigate to Live Betting page
- Select match
- Select market
- Select outcome
- Enter stake = 50
- Click "Place Bet"

###### EXPECTED RESULT
- Error message displayed:
"Insufficient balance. Please deposit to continue."
- Bet is NOT created
- Wallet balance remains 10
- No transaction recorded

STATUS : Pass / Fail


### Test Case 04 : Exact Balance Usage

###### PRECONDITIONS
- User is logged in
- Wallet balance = 20
- Active market available

###### TEST STEPS
- Select match
- Select market
- Select outcome
- Enter stake = 20
- Confirm bet

###### EXPECTED RESULT
- Bet is accepted
- Wallet balance becomes 0
- No negative balance
- Bet visible under "My Bets"

STATUS : Pass / Fail


### Test Case 05 : Stake Below Minimum Limit

###### PRECONDITIONS
- User is logged in
- Wallet balance = 100
- Minimum stake configured = 1.00
- Active market available

###### TEST STEPS
- Navigate to Live Betting page
- Select match
- Select market
- Select outcome
- Enter stake = 0.50
- Click "Place Bet"

###### EXPECTED RESULT

- Validation message displayed:
"Minimum stake is 1.00"
- Bet is NOT created
- Wallet balance remains 100
- No transaction recorded

STATUS : Pass / Fail


### Test Case 06 : Odds Revalidation Before Confirmation

###### PRECONDITIONS
- User is logged in
- Odds update mechanism active
- Live event available

###### TEST STEPS
- Select match
- Select outcome
- Wait for odds to change
- Click "Place Bet"

###### EXPECTED RESULT
- System detects odds change
- User prompted to accept updated odds
- Bet NOT auto-placed with old odds
- Bet placed only after user confirms new odds

STATUS : Pass / Fail


### Test Case 07 : Bet Persistence After Page Refresh

###### PRECONDITIONS
- User is logged in
- Sufficient wallet balance
- Event open for betting

###### TEST STEPS
- Place a valid bet
- Verify confirmation message
- Refresh browser page
- Navigate to "My Bets"

###### EXPECTED RESULT
- Bet remains visible in "My Bets"
- No duplicate bet created

STATUS : Pass / Fail


### Test Case 08 : Concurrent Bets from Two Devices


###### PRECONDITIONS
- Same user logged in on two devices
- Wallet balance = 50

###### TEST STEPS
- On Device A, place bet of 40
- At the same time on Device B, place bet of 40

###### EXPECTED RESULT
- Only one bet accepted if balance insufficient for both

STATUS : Pass / Fail


### Test Case 09 : Audit and Transaction Logging

###### PRECONDITIONS
- User successfully places a bet

###### TEST STEPS
- Place valid bet
- Verify transaction record in database or logs

###### EXPECTED RESULT
Bet record contains:
- Bet ID
- User ID
- Stake amount
- Odds snapshot
- Timestamp
- Event and market details
- Audit trail is available and traceable

STATUS : Pass / Fail


### Test Case 10: Maximum Stake Limit Enforcement

###### PRECONDITIONS
- User is logged in
- Wallet balance = 2000
- Maximum allowed stake = 1000
- Active market available

###### TEST STEPS
- Navigate to Live Betting page
- Select match and market
- Enter stake = 1500
- Click "Place Bet"

###### EXPECTED RESULT
- Validation message displayed: "Maximum stake is 1000"
- Bet NOT created
- Wallet balance remains unchanged

STATUS : Pass / Fail


### Test Case 11: Bet Cancellation Before Confirmation

###### PRECONDITIONS
- User is logged in
- Wallet balance = 100
- Active market available

###### TEST STEPS
- Navigate to Live Betting page
- Select match, market, and outcome
- Enter stake
- Click "Place Bet"
- Cancel bet on confirmation popup

###### EXPECTED RESULT
- Bet is NOT created
- Wallet balance remains unchanged
- No transaction recorded

STATUS : Pass / Fail


### Test Case 12: Session Expiry During Bet Placement

###### PRECONDITIONS
- User is logged in
- Wallet balance = 100
- Session timeout = 5 minutes
- Active market available

###### TEST STEPS
- Start placing bet
- Wait for session to expire
- Click "Place Bet"

###### EXPECTED RESULT
- User is redirected to login page
- Bet NOT placed
- Wallet balance remains unchanged

STATUS : Pass / Fail


### Most critical test cases:

- Test Case 02 : Successful Bet PlacementInsufficient Balance
- Test Case 01 : Unauthorized Access to Live Betting Page
- Test Case 06 : Odds Revalidation Before Confirmation
- Test Case 04 : Exact Balance Usage
- Test Case 08 : Concurrent Bets from Two Devices

