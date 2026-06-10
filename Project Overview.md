# Pharmacy-QA-Portfolio
# PROJECT OVERVIEW

This project is a web-based pharmacy prescription management system, designed to support efficient interaction between the pharmacy manager, pharmacists and customers. The system enables users to manage prescriptions, dispense medication, place medication orders, register employees and track prescription progress. 

The application was developed using ASP.NET CORE, C#, SQL SERVER, JavaScript and Azure services.

In this project, I contributed as both a developer and a tester. As a developer, I worked on the pharmacist subsystem. As a tester, I was responsible for performing software testing activities, including designing test cases, executing tests, and reporting defects to ensure the system met both functional and non-functional requirements.

## Test Modules
### Pharmacy Manager Modules
1. Active Ingredient Management
- Add active ingredients
- Delete active ingredients
- Mark ingredients as inactive

2. Dosage Form Management
- Add dosage forms
- Delete dosage forms

3. Supplier Management
- Add supplier
- Edit supplier details
- Delete supplier

4. Pharmacy Details Management
- Add and edit pharmacy details
- Restrict to single entry 

5. Employee Registration
- Register new employees(pharmacists)
- Generate system credentials(password)
- Send email with login details
- Email confirmation/account activation

6. Reports
- View reports
- Filter reports(date, category,etc.)
- Retrieve specific data

### Pharmacist Modules
1. Authentication
- Login with received credentials

2. Dashboard 
- View current date
- View total number of prescriptions, and pending prescriptions,
- View total number of customers
- View low stock alerts
- View weekly prescriptions(graph) 
- View weekly medication statistics

3.Prescription Management
- Upload prescription document
- Select or create customer
- Select doctor or create doctor
- Select Medication
- Trigger allergy alerts
- Dispense prescription 

4. Prescription Order Processing
- Select requested medications
- Dispense medications
- Automatically update repeats
- Dispense multiple medications
- Automatically update prescription status

5. Walk-In Customer Prescriptions
- Add customer
- View prescription 
- Select Medications 
- Dispense

6. Reports
- Retrieve dispensed prescriptions
- Filter by medication, name or date

7. Profile Management
- Update personal details
- Change password

### Customer
1. Authentication
- Register
- Login

2. Customer Medication Order Management
- Place order
- Edit order
- View order details
- View Order history

3. Reports
- Retrieve prescription records
- Filter by date

#### Test Suites
#### AUTHENTICATION TEST SUITES 
Standard authentication validation scenarios (e.g. empty fields, invalid formats, incorrect credentials, and account lockout) are covered under Customer Authentication and apply across all user roles.
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
- Login
- Session Management

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
- Supplier Management
- Pharmacy Details Management
- Employee Management

