# KSU SWE 3643 Software Testing and Quality Assurance Semester Project: Web-Based Calculator

This repository contains the semester project for the KSU SWE 3643 Software Testing and Quality Assurance course. The project is a web-based calculator application designed to demonstrate software testing principles, including unit testing, end-to-end testing, and test coverage analysis. It also includes a final video presentation showcasing the project's outcomes.

---

## Table of Contents
- [Team Members](#team-members)
- [Architecture](#architecture)
- [Environment](#environment)
- [Executing the Web Application](#executing-the-web-application)
- [Executing Unit Tests](#executing-unit-tests)
- [Reviewing Unit Test Coverage](#reviewing-unit-test-coverage)
- [Executing End-To-End Tests](#executing-end-to-end-tests)
- [Final Video Presentation](#final-video-presentation)

---

## Team Members
- Member 1: Lan Vu
- Member 2: Nino Tkabladze

## Architecture
![alt text](assets/image-10.png)
### Calculator Logic Module
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

### Testing Frameworks: Unit Testing and E2E Tools

#### Calculator Logic Unit Tests via JUnit
This component tests the core functionality of the logic module using unit tests written in **JUnit**. These tests ensure the reliability and correctness of the core calculations.

![alt text](assets/image-11.png)
#### Test Cases:
- DescriptiveStatistics_computeMean_ReceiveNullValueList_ThrowException()
Tests the computeMean method to ensure that it throws an exception when a null value list is provided."

- DescriptiveStatistics_computeMean_ReceiveEmptyValueList_ThrowException()
Validates that the computeMean method correctly throws an exception when an empty value list is given as input."

- DescriptiveStatistics_computeMean_ReceiveNonNumericValue_ThrowException()
"Ensures the computeMean method throws an exception when the input contains non-numeric values."

- LinearRegression_computeLinearRegressionFormula_ReceiveValidValues_ReturnsLinearRegressionFormula()
Tests the computeLinearRegressionFormula method to verify it returns the correct linear regression formula for valid input values."

***This is only some of the test out of the 46 test cases***

---

#### Calculator End-to-End Tests via Playwright
These tests verify the system's functionality as a whole by simulating real-world scenarios using **Playwright** for browser automation. The focus is on ensuring that the application behaves as expected from the user's perspective.
![alt text](assets/image-12.png)
#### Test Cases:
- CalculatorUI_PageTitle_ReturnsCalculator()
Validates that the Calculator UI displays the correct page title when loaded."

- CWebCalculator_ComputeZScore_ReturnResult()
Tests the ComputeZScore functionality in the Calculator UI to ensure it returns the correct result for valid inputs."

- WebCalculator_PredictY_ReturnResult()
Ensures that the PredictY functionality in the Calculator UI provides the correct predicted value for given input parameters."

- WebCalculator_ComputePopulationStdDev_ReturnsResult()
Verifies that the Calculator UI accurately computes the population standard deviation for valid inputs."

***This is only some of the test out of the 11 test cases***

This combination of unit and end-to-end testing ensures both the correctness of individual components and the seamless integration of the entire system.

---

## Environment
To set up and run the project, the following environment is required:
### Prerequisites
- **Java 21** is required.
- **Maven** is required.
- **Node.js** is required.

**Check Java Installation** 

1. Open a terminal (Command Prompt, PowerShell, or a Linux/Mac terminal) and type: 

   ```bash
   java -version

**Expected Output:** 

![alt text](assets/terminalJava.png)

If Java is Not Installed: You'll see an error like 'java' is not recognized as an internal or external command.... 

**Verify JDK Installation** 

2. To confirm the JDK is correctly installed, type: 
   ```bash
   javac -version 
    
**Expected Output:** 

![alt text](assets/javac_cmd.png)

**Check JAVA_HOME Environment Variable**

On Windows:

```terminal
echo %JAVA_HOME%
```
   Expected Output: 

   C:\Program Files\Java\jdk-21 

   On Linux/Mac: 
```bash
   echo $JAVA_HOME 
```
   Expected Output: 

   /usr/lib/jvm/java-21-openjdk-amd64 

   3. **Verify PATH Configuration** 

   Ensure the bin directory of JDK 21 is in your system PATH: 

   On Windows: 
   ```terminal
   echo %JAVA_HOME% 
   ```
**Look for:**

C:\Program Files\Java\jdk-21\bin 

![alt text](echoPath_output.png)

On Linux/Mac: 
```bash
echo $PATH 
```

***Look for:*** 

/usr/lib/jvm/java-21-openjdk-amd64/bin 


**Install Prerequisites** 

If Java 21 is not installed: 

Download and install JDK 21 from the [official site](https://www.oracle.com/java/technologies/javase-downloads.html).


- Set the ***JAVA_HOME*** environment variable and add the bin directory to your system's PATH. 

For Maven and Node.js: 

Install Maven from [Maven Downloads](https://maven.apache.org/download.cgi).


**Verify that Maven is installed** 
```bash
mvn -version 
```

Look for the Java version listed. Verify that ***Java 21*** is used. If this shows ***Java 17*** or an earlier version, Maven is not using the correct JDK. 

**Set the Correct JDK for Maven** 

Maven uses the JDK specified in your JAVA_HOME environment variable. 

- Set JAVA_HOME to the path of JDK 21: 

```bash
- set JAVA_HOME=C:\Program Files\Java\jdk-21 

- set PATH=%JAVA_HOME%\bin;%PATH% 
```
- Verify Maven now uses JDK 21:** 
```bash
mvn -v 
```

**Expected Output:** 

![alt text](assets/image-1.png)

**Install Node.js from the [official site](https://nodejs.org/).**


**Verify that Node is installed** 

node -v 

npm -v 

 ---

## Executing the Web Application

**To execute the web application locally:**
1. Clone the repository:  
   ```bash
   git clone https://github.com/ninuljaja/SWE3643-QA-Project.git


**Install Dependencies** 

2. Navigate to the root directory of the repository : 
```bash
cd SWE3643-QA-Project 
```

3. **Install Maven dependencies without running tests:** 
```terminal
mvn clean install -DskipTests 
```
![alt text](assets/image-2.png)


4. **Set up Playwright for end-to-end tests:** 
```bash
npx playwright install 
```

**Running the Application** 

To run the application locally: 

5. Navigate to the web module directory: 
```bash
cd src/web 
```

6. **Start the application:** 
```bash
mvn spring-boot:run
```
![alt text](assets/image-4.png)
![alt text](assets/image-5.png)

If you see an error like Failed to bind to http://localhost:8080, another process is using the port. Kill the process and try again

7. Once started, open a browser and connect to: 

http://localhost:8080 

![alt text](assets/image-6.png)

## Executing Unit Tests
1. Open a new command line and navigate to the root directory of a repository


2. To execute tests run: 
```bash
mvn test 
```
## Reviewing Unit Test Coverage
![alt text](assets/image-7.png)

To achieve 100% and in an attempt to catch possible all error, we use 46 test cases.

![alt text](assets/image-9.png)

100% coverage was achieved
## Executing End-To-End Tests
Since the playwright test use maven plugin, the End to end test is exectuted with the command mvn test along with Unit Test.

![alt text](assets/image-8.png)
## Final Video Presentation
[Please view our presentation here on Youtube](https://youtu.be/MBGi8_vsuww)