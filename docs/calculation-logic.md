# Smart Savings Calculator — Calculation Logic and Algorithm Design

## 1. Introduction

This document defines the mathematical calculations, business rules and algorithms used by the Smart Savings Calculator.

The purpose is to establish the application's calculation behaviour before implementation.

## 2. Calculation Inputs

| Input | Data Type | Description |
|---|---|---|
| targetAmount | BigDecimal | Desired savings target |
| currentSavings | BigDecimal | Current savings balance |
| weeklyContribution | BigDecimal | Weekly savings contribution |
| startDate | LocalDate | Date from which the savings timeline is calculated |

## 3. Calculation Outputs

| Output | Data Type | Description |
|---|---|---|
| remainingAmount | BigDecimal | Amount remaining to reach target |
| weeksRequired | long | Number of weeks required |
| completionDate | LocalDate | Estimated date of reaching the target |

## 4. Mathematical Formulas

### 4.1 Remaining Savings

Formula:

Remaining = max(0, Target Amount - Current Savings)

Example:

Target: €5,000  
Current Savings: €1,000  
Remaining: €4,000

### 4.2 Weeks Required

Formula:

Weeks Required = Ceiling(Remaining Amount / Weekly Contribution)

Example:

Remaining: €4,000  
Weekly Contribution: €150  
Weeks Required: 27

### 4.3 Estimated Completion Date

Formula:

Completion Date = Start Date + (Weeks Required × 7 days)

Example:

Start Date: 05/11/2026  
Weeks Required: 40  
Completion Date: 12/08/2027

## 5. Business Rules

- The target amount must be greater than zero.
- Current savings cannot be negative.
- Weekly contributions must be positive if the target has not been achieved.
- If current savings equal or exceed the target, remaining savings must be zero.
- Weeks required must always be rounded upwards.
- Contributions are assumed to occur once every seven days.
- Interest and investment returns are excluded from version 1.
- The completion date is calculated from the supplied start date.

## 6. Algorithm Design

### Algorithm 1: Calculate Remaining Amount

1. Receive target amount and current savings.
2. Subtract current savings from target amount.
3. If the result is negative, return zero.
4. Otherwise, return the calculated remaining amount.

### Algorithm 2: Calculate Weeks Required

1. Receive remaining amount and weekly contribution.
2. If remaining amount is zero, return zero.
3. If weekly contribution is zero or negative, return a validation error.
4. Divide remaining amount by weekly contribution.
5. Round the result upwards.
6. Return the number of weeks.

### Algorithm 3: Calculate Completion Date

1. Receive starting date and weeks required.
2. Multiply weeks required by seven.
3. Add the resulting days to the starting date.
4. Return the estimated completion date.

## 7. Assumptions

- The user saves a fixed amount every week.
- The first contribution occurs seven days after the start date.
- Contributions are not missed.
- No interest is earned.
- No withdrawals occur.
- All monetary values are represented using BigDecimal.

## 8. Edge Cases

Document and handle:

- Savings target already achieved.
- Current savings exceeding the target.
- Zero weekly contribution.
- Negative weekly contribution.
- Negative current savings.
- Contribution greater than remaining savings.
- Fractional weeks.
- Invalid monetary input.

## 9. Conclusion

The defined calculations provide the foundation for implementing the Smart Savings Calculator business logic in Java.

The algorithms will be implemented in the SavingsCalculator class and validated through automated JUnit tests.