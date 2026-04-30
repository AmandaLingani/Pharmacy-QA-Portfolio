# Pharmacy-QA-Portfolio
# PROJECT OVERVIEW

This project is a web-based pharmacy prescription management system, designed to support efficient interaction between the pharmacy manager, pharmacists and customers. The system enables users to manage prescriptions, dispense medication, place medication orders, register employees and track prescription progress. 

The application was developed using ASP.NET CORE, C#, SQL SERVER, JavaScript and Azure services.

In this project, I contributed as both a developer and a tester. As a developer, I worked on the pharmacist subsystem. As a tester, I was responsible for performing software testing activities, including designing test cases, executing tests, and reporting defects to ensure the system met both functional and non-functional requirements.

## Test Modules
### Pharmacy Manager Modules
1.Active Ingredient Management
-Add active ingredients
-Delete active ingredients
-Mark ingredients as inactive

2.Dosage Form Management
-Add dosage forms
-Delete dosage forms

3. Supplier Management
-Add supplier
-Edit supplier details
-Delete supplier

4.Pharmacy Details Management
-Add and edit pharmacy details
-Restrict to single entry 

5.Employee Registration
-Register new employees(pharmacists)
-Generate system credentials(password)
-Send email with login details
-Email confirmation/account activation

6.Reports
-View reports
-Filter reports(date, category,etc.)
-Retrieve specific data

### Pharmacist Modules
1. Authentication
-Login with received credentials

2.Dashboard 
- View current date
- View total number of prescriptions, and pending prescriptions,
- View total number of customers
- View low stock alerts
- View weekly prescriptions(graph) 
- View weekly medication statistics

3.Prescription Management
-Upload prescription document
-Select or create customer
-Select doctor or create doctor
-Select Medication
-Trigger allergy alerts
-Dispense prescription 

4.Prescription Order Processing
- Select requested medications
- Dispense medications
- Automatically update repeats
- Dispense multiple medications
- Automatically update prescription status

5.Walk-In Customer Prescriptions
-Add customer
-View prescription 
-Select Medications 
-Dispense

6.Reports
-Retrieve dispensed prescriptions
-Filter by medication, name or date

7. Profile Management
-Update personal details
-Change password

### Customer
1. Authentication
-Register
-Login

2.Customer Medication Order Management
-Place order
-Edit order
-View order details
-View Order history

3.Reports
-Retrieve prescription records
-Filter by date

#### Test Suites
#### AUTHENTICATION TEST SUITES 
##### CUSTOMER AUTHENTICATION TEST SUITES
- Customer Registration
- Login
- Validation (email format, empty fields, invalid credentials)
  
#### PHARMACIST AUTHENTICATION TEST SUITES
- Account creation (by Pharmacy Manager)
- System-generated password
- Email delivery of credentials
- Account activation
- First-time login
- Invalid login handling

#### PHARMACY MANAGER AUTHENTICATION TEST SUITES
-Login
-Session Management

#### CUSTOMER TEST SUITES
- Medication Order Management
- Reports

#### PHARMACIST TEST SUITES
- Dashboard interaction
- Prescription Management
- Prescription Order Management
- Walk-In Prescription Management
- Reports
- Profile Management

#### PHARMACY MANAGER TEST SUITES
- Active Ingredients Management
- Dosage Form Management
- Supplier Management
- Pharmacy Details Management
- Employee Management
- Reports

##### TEST CASES 
##### CUSTOMER AUTHENTICATION TEST CASES
###### Registration
**CA_TC01 - Verify successful registration with valid details
 - Precondition: User is on registration page
               : User is not registered
 - Steps: 1. Enter valid email address
          2. Enter valid details in all required fields
          3. Click register button
 -Expected Results: Registration is successful
                  : User is redirected to customer dashboard

**CA_TC02 - Verify registration fails with incorrect email format 
  -Preconditions: User is on registration page
  -Steps: 1. Enter an invalid email format (e.g. amandalingani.com)
          2. Enter valid details in all other required fields
          3. Click register button
  -Expected Results: Registration is unsuccessful
                   : Validation error message is displayed: "Please enter a valid email address"
                   : User remains on registration page

**CA_TC03 - Verify registration fails with incorrect password format
   - Preconditions: User is on registration page
   - Steps: 1. Enter valid email address
            2. Enter incorrect password format (e.g. less than required length)
            3. Click register button
   - Expected Results: Registration is unsuccessful
                     : Validation error message is displayed:"Password must meet required criteria"
                     : User remains on registration page

**CA_TC04 - Verify that registration fails when email already exists
  -Preconditions: User is on the registration page
                : Email address is alrady registered
  - Steps: 1. Enter an existing email address
           2. Enter valid details in other required fields
           3. Click register button
  - Expected Results: Registration is unsuccessful
                    : Validation error message is displayed: "Email address already exists!" is displayed
                    : User remains on the registration page

**CA_TC05 - Verify that registration fails when required fields are empty
  -Preconditions: User is on the registration page
  -Steps: 1. Leave required fields empty(e.g. email address, password)
          2. Enter other fields
          3. Click register button
  -Expected Results: Registration is unsuccessful
                   : Validation error message is displayed: "Enter all required fields"
                   : User remains on registration page

##### Login
**CA_TC06 - Verify successful login with valid details
-Precondition: User is registered
             : User is on login page
-Steps: 1. Enter valid email address
        2. Enter valid password
        3. Click login button
-Expected Results: Login is successful
                 : User is redirected to customer dashboard
                 
**CA_TC07 - Verify login fails when email address field is empty
-Preconditions: User is registered
              : User is on the login page
-Steps: 1. Leave the email address field empty
        2. Enter valid password
        3. Click login button
-Expected Results: Login is unsuccessful
                 : Validation error message is displayed: "Email cannot be empty"
                 : User remains on login page

**CA_TC08 - Verify login fails when password field is empty
-Preconditions: User is registered
              : User is on the login page
-Steps: 1. Enter valid email address
        2. Leave password field empty
        3. Click login button
-Expected Results: Login is unsuccessful
                 : Validation error message is displayed: "Password cannot be empty"
                 : User remains on login page

**CA_TC09 – Verify login fails when email is not registered
-Preconditions: User is on the login page
-Steps: 1. Enter an unregistered email address
        2. Enter valid password
        3. Click login button
-Expected Results: Login is unsuccessful
                 : Error message is displayed: “Invalid email or password”
                 : User remains on login page

**CA_TC10 - Verify login fails when invalid format email address is entered
-Preconditions: User is registered
              : User is on the login page
-Steps: 1. Enter invalid email address
        2. Enter valid password
        3. Click login button
-Expected Results: Login is unsuccessful
                 : Validation error message is displayed: "Please enter a valid email addresss"
                 : User remains on login page

**CA_TC11 - Verify that login fails when incorrect password is entered
-Preconditions: User is registered
              : User is on the login page
-Steps: 1. Enter valid email address
        2. Enter incorrect password
        3. Click login button
-Expected Results: Login is unsuccessful
                 : Validation error message is displayed: "Invalid email or password"
                 : User remains on login page

**CA_TC12 - Verify "forgot password" option is suggested after multiple failed login attempts
-Preconditions: User is registered
              : User is on the login page
-Steps: 1. Enter valid email address
        2. Enter incorrect password 
        3. Click login button
        4. Repeat failed login attempts multiple times
- Expected Results: Login is unsuccessful
                  : System suggests password recovery option
                  : Message is displayed : "Forgot your password? click here to reset"
                  : User remains on login page

 **CA_TC13 - Verify that account is temporarily locked after multiple login attempts
  -Preconditions: User is registered
                : User is on the login page
  -Steps: 1. Enter invalid login credentials until limit is reached
  -Expected Results: Account is locked tmporarily
                   : User is prevented from logging in
                   : Lockout message is displayed: "Account temporarily locked, try again in 60 minutes"

##### PHARMACIST AUTHENTICATION TEST CASES
### PHARMACIST REGISTRATION
User account created by pharmacy manager, login credentials sent by email
**PA_TC01 - Verify successful email confirmation
-Preconditions: Pharmacist account has been created by Pharmacy Manager
              : User has received account activation email
-Steps: 1. Click the email confirmation link
-Expected Result: Message is displayed: "Thank you for confirming your email!"
                : User is redirected to login page
               
#### Login
**PA_TC02 - Verify successful login with provided credentials
-Preconditions: Pharmacist account has been created by Pharmacy Manager
              : Email has been successfully confirmed
              : User is on login page
-Steps: 1. Enter provided email address
        2. Enter provided password
        3. Click the login button
-Expected Results: Login is successful
                 : User is redirected to Pharmacist Dashboard

**PA_TC05 - Verify login fails when email is not confirmed
-Preconditions: Pharmacist account has been created by Pharmacy Manager
              : Email has NOT been confirmed
              : User is on login page
-Steps: 1. Enter valid login credentials
        2. Click the login button
-Expected Results: Login is unsuccessful
                 : Error message is displayed: "Please confirm your email before logging in"
                 : User remains on the login page

**PA_TC06 - Verify that login fails when incorrect password is entered
-Preconditions: Pharmacist account exists and email is confirmed
              : User is on the login page
-Steps: 1. Enter valid email address
        2. Enter incorrect password
        3. Click login button
-Expected Results: Login is unsuccessful
                 : Validation error message is displayed: "Invalid email or password"
                 : User remains on login page

**PA_TC07 - Verify login fails when invalid format email address is entered
-Preconditions: Pharmacist account exists and email is confirmed
              : User is on the login page
-Steps: 1. Enter invalid email address (e.g. amandalingani.com)
        2. Enter valid password
        3. Click login button
-Expected Results: Login is unsuccessful
                 : Validation error message is displayed: "Invalid email or password"
                 : User remains on login page

**PA_TC08 - Verify "forgot password" option is suggested after multiple failed login attempts
-Preconditions: Pharmacist account exists and email is confirmed
              : User is on the login page
-Steps: 1. Enter valid email address
        2. Enter incorrect password 
        3. Click login button
        4. Repeat failed login attempts multiple tims
- Expected Results: Login is unsuccessful
                  : System suggests password recovery option
                  : Message is displayed : "Forgot your password? click here to reset"
                  : User remains on login page

**PA_TC09 – Verify password reset access behaviour (pre-first login scenario)
-Preconditions: Pharmacist account exists and email is confirmed
              : User has not yet logged in
-Steps: 1. Click “Forgot Password”
-Expected Results: System responds according to defined business rule
                 : Appropriate message is displayed

 **PA_TC10 - Verify account is temporarily locked after multiple login attempts
  -Preconditions: Pharmacist account exists and email is confirmed
                : User is on the login page
  -Steps: 1. Enter invalid login credentials until limit is reached
  -Expected Results: Account is locked temporarily
                   : User is prevented from logging in
                   : Lockout message is displayed: "Account temporarily locked, try again in 60 minutes"

##### PHARMACY MANAGER AUTHENTICATION TEST CASES
### LOGIN
**PMA_TC01 - Verify login is successful with valid credentials
-Preconditions: Pharmacy manager account has been registered
              : User is on login page
-Steps: 1. Enter valid email address
        2. Enter valid password
        3. Click the login button
-Expected Results: Login is successful
                 : User is redirected to Pharmacy manager dashboard

**PMA_TC02 - Verify login fails with invalid email address format
-Preconditions: Pharmacy manager account has been created
              : User is on login page
-Steps: 1. Enter invalid email address format(e.g. amandalingani@gmail
        2. Enter valid password
        3. Click the login button
-Expected Results: Login is unsuccessful
                 : Error message is displayed: "Invalid email address, please try again"
                 : User remains on the login page

**PMA_TC03 - Verify login fails with invalid password
-Preconditions: Pharmacy manager account has been created
              : User is on login page
-Steps: 1. Enter valid email address
        2. Enter invalid password
        3. Click the login button
-Expected Results: Login is unsuccessful
                 : Error message is displayed: "Invalid password, please try again"
                 : User remains on the login page

**PMA_TC04 - Verify login fails with empty email address field
-Preconditions: User is on login page
-Steps: 1. Leave email address field empty
        2. Enter valid password
        3. Click the login button
-Expected Results: Login is unsuccessful
                 : Error message is displayed: "Email address cannot be empty, enter email address"
                 : User remains on the login page

**PMA_TC05 - Verify account is temporarily locked after multiple login attempts
  -Preconditions: User is on the login page
  -Steps: 1. Enter invalid login credentials until limit is reached
  -Expected Results: Account is locked temporarily
                   : User is prevented from logging in
                   : Lockout message is displayed: "Account temporarily locked, try again in 60 minutes"

###### Customer Test Cases
**CTC01 - Ensure prescription PDF uploads successfully
-Preconditions: User is logged in
              : User is on Prescription page
-Steps: 1. Click Upload prescription 
        2. Select a valid PDF file
        3. Click upload 
-Expected Results: File uploads successfully
                 : Success confirmation message is displayed
                 : Uploaded prescription is visible in prescription history
                 :File is stored and can be accessed later
                 : User remains on the page

**CTC02 - Confirm customer can view prescription history
-Preconditions: User is logged in
              : User has existing prescriptions
              : User is on dashboard
-Steps: 1. Click Prescription history
-Expected Results: All prescriptions are shown in a structured form
                 : Each record shows relevant details(date, medication, status)
                 : Data displayed matches stored records
              
**CTC03 - Ensure medication reorder from previous prescriptions is successful
-Preconditions: User is logged in
              : User has past prescriptions
              : Medication has repeats remaining
              : User is on prescription history page
-Steps: 1. Select prescription
        2. View prescription details
        3. Select medication to reorder
        4. Click place order 
-Expected Results: Order is created successfully
                 : Selected medication is included in the order
                 : Confirmation message is displayed
                 : User remains on the same page

**CTC04 - Ensure repeats update when prescription is dispensed
-Preconditions: User is logged in
              : User has a prescription with repeats
              : Prescription status = Dispensed (updated by Pharmacist)
-Steps: 1. Navigate to prescription history
        2. Open the prescription
-Expected Results: Number of repeats is reduced correctly
                 : Updated value is displayed accurately
                 : Change persists after refresh

**CTC05 - Ensure reorder is unsuccessful when there are no repeats remaining
-Preconditions: User is logged in
              : Selected medication has 0 remaining repeats
-Steps: 1. Navigate to prescription history
        2. View prescription details
        3. Select medication with no remaining repeats
        4. Click place order
-Expected Results: Order placement is unsuccessful
                 : Error message is displayed: "Order cannot be placed, some items in your list have 0 remaining repeats"
                 : User remains on the same page

**CTC06 - Confirm order confirmation email is sent after order is placed
-Preconditions: User is logged in
              : User has a prescription with repeats remaining
-Steps: 1. Navigate to prescription history
        2. Select medication
        3. Place order
-Expected Results: Order is placed successfully
                 : Success message is displayed
                 : User remains on the page
                 : A confirmation email is sent to the registered email address
                 : Email contains correct order details
                 
**CTC07 - Ensure upload fails with invalid file type(not pdf)
-Preconditions: User is logged in
              : User is on prescription page
-Steps: 1. Navigate prescription page
        2. Click upload prescription
        3. Select invalid file type(e.g. doc, jpeg)
        4. Click upload
-Expected Results: File upload is unsuccessful
                 : Error message is displayed: "File must be .pdf, select another file"
                 : User remains on the same page

**CTC08 - Ensure file upload is unsuccessful when no file is selected
-Preconditions: User is logged in
              : User is on prescription page
-Steps: 1. Open prescription page
        2. Click upload prescription
        3. Do not select a file
        4. Click upload
-Expected Results: Error message is displayed: "Select a file to upload"
                 : User remains on the page
