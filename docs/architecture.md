# Smart Savings Calculator — Application Architecture

## 1. Architecture Overview

The Smart Savings Calculator will be developed as a monolithic Java console application using a layered architectural design.

The purpose of this architecture is to separate the application's responsibilities into logical components, making the software easier to understand, maintain, test and extend.

The application will initially operate without a database or external API.

## 2. Architectural Style

**Application type:** Console-based Java application

**Architectural style:** Monolithic architecture with a layered design.

**Programming language:** Java

**Build tool:** Apache Maven

**Testing framework:** JUnit

**Version control:** Git and GitHub

## 3. Application Layers

### 3.1 Presentation Layer

Responsible for interacting with the user.

Responsibilities:
- Request savings information.
- Receive user input.
- Display validation errors.
- Display calculation results.

Main component: `Main.java`

### 3.2 Business Logic Layer

Responsible for implementing the application's savings calculations and business rules.

Responsibilities:
- Calculate the remaining savings amount.
- Calculate the number of weeks required to reach the target.
- Calculate the estimated completion date.
- Apply savings calculation rules.

Main component: `SavingsCalculator.java`

### 3.3 Domain and Validation Components

Responsible for representing savings goal information and enforcing valid input.

Responsibilities:
- Represent the user's savings goal.
- Store target amount, current savings and weekly contribution.
- Validate monetary values.
- Prevent invalid savings calculations.

Main components:
- `SavingsGoal.java`
- `InputValidator.java`

## 4. Application Data Flow

1. The user enters their savings information.
2. The presentation component receives the information.
3. The validation component checks the supplied values.
4. A savings goal object represents the validated information.
5. The calculator performs the required calculations.
6. The result is returned to the presentation component.
7. The application displays the savings results.

## 5. Architectural Decisions

- The application will initially be a single Java application.
- The application will use a layered design to separate responsibilities.
- Monetary values will use Java `BigDecimal` for accuracy.
- JUnit will be used for automated unit testing.
- Maven will manage dependencies and project builds.
- GitHub will manage source control and project collaboration.
- GitHub Actions will automate building and testing.

## 6. Future Architectural Improvements

Future versions may introduce:
- A graphical or web-based user interface.
- Spring Boot for REST API development.
- MySQL for persistent savings data.
- User authentication and authorisation.
- Docker containerisation.
- Cloud deployment.

These improvements will be introduced in later projects as the application requirements become more advanced.

## 7. Conclusion

The selected architecture provides a simple and maintainable foundation for the Smart Savings Calculator while introducing software design principles that can be applied to larger applications such as SaveWise.
