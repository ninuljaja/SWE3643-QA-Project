# KSU SWE 3643 Software Testing and Quality Assurance Semester Project: Web-Based Calculator

This repository contains the semester project for the KSU SWE 3643 Software Testing and Quality Assurance course. The project is a web-based calculator application designed to demonstrate software testing principles, including unit testing, end-to-end testing, and test coverage analysis. It also includes a final video presentation showcasing the project's outcomes.

## Table of Contents
1. [Team Members](#team-members)
2. [Architecture](#architecture)
3. [Environment](#environment)
4. [Executing the Web Application](#executing-the-web-application)
5. [Executing Unit Tests](#executing-unit-tests)
6. [Reviewing Unit Test Coverage](#reviewing-unit-test-coverage)
7. [Executing End-To-End Tests](#executing-end-to-end-tests)
8. [Final Video Presentation](#final-video-presentation)

## Team Members
- Member 1: Lan Vu, Documentation
- Member 2: Nino, Developer

## Architecture
![alt text](umlDiagram.png)
## Calculator Logic Module
This module encapsulates the core logic of the calculator app. Each class and method is responsible for a distinct task, ensuring modularity and maintainability:

1. **DescriptiveStatistics**  
   Handles descriptive statistical computations, such as calculating the mean, standard deviation, and other summary statistics.

2. **LinearRegression**  
   Handles calculations related to linear regression, including generating formulas and predicting values based on input data.

3. **ValidationFunctions**  
   Ensures input data is validated for accuracy, completeness, and adherence to expected formats.

4. **LogicFunctions**  
   Provides utility methods that serve as helpers for core calculations. These methods are reusable across different modules.

5. **CalculationResult**  
   A utility class designed to encapsulate the results of computations. It provides a standardized way of returning the calculation outputs along with relevant metadata, such as error messages or calculation status.

Both DescriptiveStatistics and LinearRegression utilize ValidationFunctions and LogicFunctions.
CalculationResult is used across modules to standardize the computation output.

# Testing Frameworks: Unit Testing and E2E Tools

## Calculator Logic Unit Tests via JUnit
This component tests the core functionality of the logic module using unit tests written in **JUnit**. These tests ensure the reliability and correctness of the core calculations.

![alt text](UnitTestUML.png)
### Test Cases:
1. **DescriptiveStatistics_NullValueList_ThrowsException()**  
   Ensures that null values are handled properly and appropriate exceptions are thrown.

2. **DescriptiveStatistics_ValidValues_ReturnsMean()**  
   Tests the computation of the mean for valid input values.

3. **LinearRegression_EmptyInput_ReturnsError()**  
   Validates that an error is returned when the input for linear regression is empty.

4. **LinearRegression_ValidPairs_ReturnsFormula()**  
   Tests the generation of the linear regression formula for valid input pairs.

---

## Calculator End-to-End Tests via Playwright
These tests verify the system's functionality as a whole by simulating real-world scenarios using **Playwright** for browser automation. The focus is on ensuring that the application behaves as expected from the user's perspective.
![alt text](EndtoEndUML.png)
### Test Cases:
1. **CalculatorUI_PageTitle_ReturnsCalculator()**  
   Validates that the page title is displayed correctly in the browser.

2. **CalculatorUI_ComputeMean_ReturnsResult()**  
   Tests the user interface flow for calculating the mean and returning a result.

3. **CalculatorUI_EmptyInput_DisplaysError()**  
   Ensures that the application displays proper error messages when the input field is empty.

4. **CalculatorUI_ComputeLinearRegression_ReturnsFormula()**  
   Tests the UI flow for performing linear regression and displaying the resulting formula.



This combination of unit and end-to-end testing ensures both the correctness of individual components and the seamless integration of the entire system.

- **Deployment:** [Hosting platform/environment]

## Environment
To set up and run the project, the following environment is required:
Java 21 is required 

Check Java Installation 

Open a terminal (Command Prompt, PowerShell, or a Linux/Mac terminal) and type: 

java -version 
<img src="terminalJava.png" style="zoom: 50%;" />

If Java is Not Installed: You'll see an error like 'java' is not recognized as an internal or external command.... 

Verify JDK Installation 

To confirm the JDK is correctly installed, type: 

javac -version 

Expected Output: 
<img src ="C:\Users\lanvu\Downloads\javac_cmd.png>

Check JAVA_HOME Environment Variable 

On Windows: 

echo %JAVA_HOME% 

## Executing the Web Application

To execute the web application locally:
1. Clone the repository:  
   ```bash
   git clone https://github.com/ninuljaja/SWE3643-QA-Project.git
