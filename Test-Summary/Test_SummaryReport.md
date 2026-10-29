# Test Summary Report

## Overview
- This portfolio project involved testing a pharmacy management system that manages prescriptions, medications, employees, and customers. Manual functional testing was performed using structured test cases to validate core system functionality. Defects identified during testing were documented and tracked using bug reports.

## Scope of Testing
- User authentication(login/register)
- Prescription upload
- Employee management
- Medication dispensing
- Medication ordering

## Test Execution Summary
- Total Test Cases: 38
- Passed: 33
- Failed: 5
- Blocked: 0

## Defect Summary
- Total defects identified: 4
- Critical: 1
- High: 2
- Medium: 1
- Low: 0

## Key Issues Identified
- Employee registration due to password validation issues
- Uploaded prescription file preview not displaying correctly
- Customer users required to log in twice before accessing dashboard
- Medication stock not updating after medication dispensing

## Risks & Impact
- Critical: Employee registration failure blocks employee onboarding
- High: Stock inconsistency may lead to inaccurate inventory tracking
- High: Login issues negatively affect user access and user experience
- Medium: File preview failure may increase risk of incorrect prescription verification

## Conclusion
- The system is partially functional, but not ready for production due to critical and high severity defects.
- Defects identified during testing should be resolved before the next testing cycle or production deployment.
