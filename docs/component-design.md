# Smart Savings Calculator — Component Design

## 1. Introduction

This document identifies the main components of the Smart Savings Calculator and defines their responsibilities, attributes, operations and relationships.

The purpose is to ensure that each component has a clearly defined responsibility and that the application follows separation of concerns.

## 2. Component Overview

The application will initially contain five main components:

1. Main
2. ConsoleUI
3. InputValidator
4. SavingsGoal
5. SavingsCalculator

## 3. Component Specifications

### 3.1 Main

**Purpose:** Application entry point and coordinator.

**Responsibilities:**
- Start the application.
- Initialise the required components.
- Coordinate the application workflow.

**Main operation:**
- `main(String[] args)`

### 3.2 ConsoleUI

**Purpose:** Handle interaction between the application and user.

**Responsibilities:**
- Display application instructions.
- Request savings information.
- Receive user input.
- Display validation errors.
- Display calculation results.

**Potential operations:**
- `displayWelcomeMessage()`
- `getSavingsInformation()`
- `displayResults()`
- `displayError()`

### 3.3 InputValidator

**Purpose:** Validate user-provided information.

**Responsibilities:**
- Ensure the target amount is positive.
- Ensure current savings are not negative.
- Ensure weekly contribution is positive when a target remains.
- Reject invalid input formats.

**Potential operations:**
- `validateTargetAmount()`
- `validateCurrentSavings()`
- `validateWeeklyContribution()`

### 3.4 SavingsGoal

**Purpose:** Represent a user's savings goal.

**Attributes:**
- `targetAmount: BigDecimal`
- `currentSavings: BigDecimal`
- `weeklyContribution: BigDecimal`

**Responsibilities:**
- Store savings goal information.
- Provide access to savings goal attributes.
- Represent the state of a savings goal.

### 3.5 SavingsCalculator

**Purpose:** Perform savings-related calculations.

**Responsibilities:**
- Calculate the remaining savings amount.
- Calculate the number of weeks required.
- Calculate the estimated completion date.

**Potential operations:**
- `calculateRemainingAmount()`
- `calculateWeeksRequired()`
- `calculateCompletionDate()`

## 4. Component Relationships

- Main coordinates the application.
- ConsoleUI manages interaction with the user.
- InputValidator validates user-provided information.
- SavingsGoal represents the savings information.
- SavingsCalculator performs calculations using SavingsGoal data.
- ConsoleUI displays the results returned by SavingsCalculator.

## 5. Design Principles

The application will follow these principles:

- **Single Responsibility Principle:** Each component should have one primary responsibility.
- **Separation of Concerns:** User interaction, validation, domain data and calculations should be separated.
- **Encapsulation:** Internal class data should be protected and accessed through appropriate methods.
- **Reusability:** The calculation logic should be independent of the console interface.

## 6. Future Improvements

Future versions may introduce:
- Multiple savings goals.
- Savings categories.
- Interest calculations.
- Database persistence.
- REST API integration.

These features are outside the scope of the first version.