Bug ID: BUG-001

Bug title: Employee registration fails due to incorrect password validation error

Environment: Web Browser (Chrome)

Steps to Reproduce: 
   1. Login as Pharmacy Manager
   2. Navigate to Employee Registration page
   3. Enter a valid email address
   4. Enter valid employee details(Name, Last name, Identity number, etc)
   5. Select role (Pharmacist)
   6. Click "Sign up" (system auto-generates password)
          
Expected Results:
- Employee is successfully registered
- System generates password 
- An email is sent to the registered email address
- Employee data is recorded and stored in the system
  
Actual results:
- Employee registration fails
- An error message is displayed: "password must contain %,*,@"
              
Severity: Critical
Priority: P1

Evidence: To be provided
