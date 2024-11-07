# JMeter Performance Testing Setup and Execution

This README provides instructions for setting up a JMeter performance test for API endpoints, optimizing API response time, and executing the test files in JMeter.

## Table of Contents

1. [Setting up JMeter Performance Test](#setting-up-jmeter-performance-test)
2. [Executing JMeter Tests](#executing-jmeter-tests)

---

## 1. Setting up JMeter Performance Test

### Objective
Create a JMeter script to test the performance of API endpoints with the following metrics:
- **Response Time**: Aim for an average response time of under 500 milliseconds.
- **Throughput**: Aim for at least 100 requests per minute.

### Steps
1. **Create an HTTP Request Sampler** in JMeter.
   - **Method**: Set the HTTP method (`POST`).
   - **Path**: Specify the API endpoint path (`/auth`).
   - **Body Data**: Add JSON data payload if needed.
   
2. **Add an HTTP Header Manager**.
   - Specify headers `Content-Type: application/json`.

3. **Add Assertions**.
   - **Duration Assertion**: Set a maximum response time (500 milliseconds).
   - **Response Assertion** (optional): Validate response status codes.

4. **Add Listeners** for Result Analysis.
   - **Summary Report**: Provides average response time and success rate.
   - **View Results Tree**: Displays individual request responses.

5. **Run the Test and Review Results**.
   - Review the average response time in **Summary Report** to ensure it meets the 500 ms target.

---

## 2. Executing JMeter Tests

To execute the JMeter test files after cloning the repository:

1. **Open JMeter**:
   - Open JMeter on your computer (ensure JMeter is installed and configured on your system).

2. **Load the JMeter Test File**:
   - In JMeter, go to **File** > **Open**, then navigate to the cloned repository folder and select the `.jmx` test file.

3. **Run the Test**:
   - Click on the green **Start** button (or **Run** > **Start**) to execute the test.
   - Review the **Summary Report** or **View Results Tree** for test results.

### Running JMeter Tests in Command Line (Optional)
If you prefer running the tests via the command line:

1. Use the following command to execute the `.jmx` test file in non-GUI mode (replace `test-file.jmx` with your file name):

   ```bash
   jmeter -n -t test-file.jmx -l test-results.jtl
