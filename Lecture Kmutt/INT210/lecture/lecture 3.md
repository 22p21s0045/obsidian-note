3/13/2024
#lecture-3 #tester #software-assurance #testing
[[INT210-2023-08-SoftwareTesting 1.2.pdf]]

## Goal of testing
- Determine correctness, under certain assumptions/conditions
- Find faults and failures << to fix
- Static test << review code (code not running)
- Dynamic test << test running software
- Pass/ fail criteria are determined by stakeholders << test results

## Software Assurance

1. **Security and Reliability**:
    
    - Ensuring that software is secure, reliable, and free from vulnerabilities.
    - Addressing potential risks related to security breaches, data leaks, and unauthorized access.
2. **Quality and Compliance**:
    
    - Verifying that software adheres to quality standards and industry best practices.
    - Meeting compliance requirements (such as legal, regulatory, or organizational standards).
3. **Lifecycle Management**:
    
    - Managing software throughout its entire lifecycle, from design and development to maintenance and retirement.
    - Regularly assessing and improving software to maintain its integrity.

## SQA

![](https://i.imgur.com/OSx1HvE.png)

### Verification vs Validation

**Verification**:

- Focuses on checking if the software is built correctly according to specifications.
- Involves static testing of documents, design, code, and programs.
- Aims to identify and correct defects early in the development process.
- Ensures that the software conforms to requirements and standards.

**Validation**:

- Focuses on confirming that the software meets stakeholder needs and expectations.
- Involves dynamic testing through activities like testing, reviews, and user feedback.
- Aims to ensure that the software is the right product that satisfies user requirements.
- Validates that the software functions as intended and provides value to users.


- Verify เทียบกับข้อกําหนด
- Validation 

## Unit testing
- **Definition:** Unit tests are low-level tests that focus on verifying individual methods and functions of classes, components, or modules used in the software.
- **Purpose:** They ensure that each unit of code functions correctly in isolation.
- **Scope:** Unit tests are close to the source code and are generally inexpensive to automate, running quickly by a continuous integration server.
- **Example:** Testing a specific function within a class to ensure it produces the expected output.

## Integration Testing:

- **Definition:** Integration tests verify that different modules or services used by the application work well together.
- **Purpose:** They ensure that integrated components interact correctly and function as expected as a whole system.
- **Scope:** Integration tests are more expensive to run as they require multiple parts of the application to be up and running.
- **Example:** Testing the interaction with a database or ensuring that microservices work together seamlessly.

## Acceptance testing 
critical phase in software development that evaluates whether a system meets its business and user requirements. It is the final testing stage before a system is released to production, ensuring that the software complies with specifications and quality standards.


## Regression testing
a crucial software testing process that involves re-running functional and non-functional tests to ensure that a software update or code modification has not introduced new bugs or issues. It aims to verify that the previously developed and tested software functions correctly after changes have been made. Regression testing is essential to maintain the quality and stability of the software, especially when new features are added, defects are fixed, or changes are made to the codebase.


## Functional testing vs Unit testing

| Aspect              | Functional Testing                                               | Unit Testing                                               |
| ------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------- |
| **Definition**      | Evaluates end-to-end functionality based on requirements         | Targets individual components to verify correctness        |
| **Purpose**         | Ensures software meets user expectations and functions correctly | Catches bugs early in development, validates code segments |
| **Scope**           | Tests entire application, including UI, workflows, integrations  | Tests isolated code units without external dependencies    |
| **Execution**       | Conducted by dedicated testers during application testing        | Mainly performed by developers during development cycle    |
| **Tools**           | Selenium, QTP, SoapUI, Watir                                     | JUnit, NUnit, TestNG, Mockito                              |
| **Characteristics** | Identifies issues in system functionality and user interactions  | Identifies issues in logic of specific code components     |