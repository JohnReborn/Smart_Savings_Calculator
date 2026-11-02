# Smart Savings Calculator

## 1. Project Overview

The Smart Savings Calculator is a Java application that helps users estimate how long it will take to reach a financial savings goal.

Users provide a savings target, their current savings balance and the amount they intend to save each week. The application calculates the remaining amount and the estimated number of weeks required to reach the target.

The initial version will focus on basic savings projections without interest calculations or database storage.

## 2. Problem Statement

People who want to save for specific goals may find it difficult to estimate how long they need to save to reach their targets.

The Smart Savings Calculator aims to simplify this process by providing clear, accurate and easy-to-understand savings projections.

## 3. Project Objectives

- Accept a user's savings target.
- Accept the user's current savings balance.
- Accept the planned weekly contribution.
- Calculate the amount remaining.
- Estimate the number of weeks required to reach the target.
- Validate financial inputs.
- Provide clear results and error messages.
- Use automated tests to verify calculation accuracy.
- Use GitHub Actions to automate building and testing.

## 4. Functional Requirements

- FR-01: The application shall accept a savings target.
- FR-02: The application shall accept a current savings balance.
- FR-03: The application shall accept a weekly contribution.
- FR-04: The application shall calculate the remaining amount.
- FR-05: The application shall calculate the number of weeks required.
- FR-06: The application shall reject negative monetary values.
- FR-07: The application shall reject a zero weekly contribution when a positive amount remains to be saved.
- FR-08: The application shall recognise when the target has already been reached.
- FR-09: The application shall display results clearly.
- FR-10: The application may calculate an estimated completion date.

## 5. Non-Functional Requirements

- NFR-01: Financial calculations shall be accurate.
- NFR-02: Inputs shall be validated before calculations are performed.
- NFR-03: Error messages shall explain invalid inputs.
- NFR-04: Calculation logic shall be independently testable.
- NFR-05: Automated unit tests shall verify calculation behaviour.
- NFR-06: GitHub Actions shall automatically build and test the application.
- NFR-07: The README shall explain how to build and run the application.

## 6. Inputs and Outputs

### Inputs

- Savings target, expressed in euros.
- Current savings balance, expressed in euros.
- Weekly contribution, expressed in euros.

### Outputs

- Remaining amount.
- Estimated number of weeks required.
- A message indicating whether the target has already been reached.
- An estimated completion date, if implemented.

## 7. Calculation Rules

Remaining amount:

Remaining Amount = Savings Target - Current Savings

Weeks required:

Weeks Required = Ceiling(Remaining Amount / Weekly Contribution)

The number of weeks shall be zero when the current savings balance equals or exceeds the target.

The initial version will not calculate interest or account for changing contribution amounts.

## 8. Validation Rules

- Monetary inputs must not be negative.
- A positive weekly contribution is required when the target has not been reached.
- A savings target of zero is valid and is considered already achieved.
- If current savings equal or exceed the target, the application shall report that the target has been reached.
- Invalid inputs shall produce clear error messages.

## 9. Scope

### Included

- Basic savings calculations.
- Input validation.
- Error handling.
- Automated unit tests.
- GitHub version control.
- GitHub Actions continuous integration.
- Project documentation.

### Excluded from the Initial Version

- User registration and login.
- Database storage.
- Bank integrations.
- Interest calculations.
- Multiple savings goals.
- Cloud deployment.
- Financial advice.

## 10. Acceptance Criteria

The initial version will be considered complete when:

1. A user can provide valid savings inputs.
2. The application calculates the remaining amount correctly.
3. The application calculates the required number of weeks correctly.
4. Invalid monetary values are rejected.
5. A zero contribution is handled appropriately.
6. Targets that have already been reached are recognised.
7. Automated tests cover normal and exceptional scenarios.
8. GitHub Actions successfully builds and tests the project.
9. The README explains how to run the application.
