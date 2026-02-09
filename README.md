# Automated UART-Based Tester: PC ↔ Arduino with Pass/Fail Reporting

## Overview

This project implements an **automated test system** that validates serial communication and data processing between a **PC application** and an **Arduino** using **UART**.

The PC application sends predefined test data packets to the Arduino.  
The Arduino scales or processes the received data and sends the result back to the PC.  
The PC then:

- Compares received values against expected results  
- Declares each test case as **PASS** or **FAIL**  
- Automatically generates a **test report** summarizing the results  

This project is designed to mimic **production-level automated testing** used in embedded systems and avionics environments.

---

## Key Features

- UART-based communication between PC and Arduino  
- Automated transmission of test data from PC  
- Arduino-side data scaling and processing  
- PC-side validation of returned data  
- Pass / Fail decision logic  
- Automatic test report generation  
- Suitable for regression and production testing  

---

## Tools & Technologies

- C / C++ (PC application)  
- Arduino (Embedded firmware)  
- UART / Serial communication  
- Visual Studio Code  
- Arduino IDE  
- Windows OS  

---

## System Architecture

PC Test Application
↓ UART
Arduino
(Data Scaling Logic)
↑ UART
PC Validation & Report Generator


---

## Test Workflow

1. PC sends raw test data to Arduino  
2. Arduino processes/scales the data  
3. Arduino sends processed data back to PC  
4. PC verifies the received values  
5. PASS / FAIL decision is made  
6. Test report is generated automatically  

---

## Setup Instructions

### 1. Clone Repository

```bash
git clone <your_repo_url>
cd <your_project_folder>

```
2. Upload Arduino Firmware

Open Arduino source code in Arduino IDE

Select correct board and COM port

Upload firmware to Arduino

3. Build & Run PC Application

Open the project in Visual Studio Code.

If using GCC / MinGW (example):
```

gcc main.c -o uart_tester
./uart_tester

```
(Adjust build commands based on your compiler and project structure.)

4. Run Automated Test

Connect Arduino to PC via USB

Ensure correct COM port selection

Run the PC test application

Observe real-time test results

Review generated test report

Pass / Fail Criteria

PASS: Received data matches expected scaled value within defined limits

FAIL: Data mismatch, timeout, or invalid response

Thresholds and scaling logic can be modified based on test requirements.

## Report Generation

After test execution, an automated report is generated containing:

Test case ID

Sent value

Expected value

Received value

PASS / FAIL status

Timestamp

## The report can be used for:

Debugging

Regression testing

Production validation records

## Use Cases

Embedded system validation

UART protocol testing

Arduino firmware verification

Automated regression testing

Hardware-in-the-loop (HIL) style testing

## Notes

Ensure baud rate and serial parameters match on both sides

Arduino must be powered and connected before running tests

Timeout handling is implemented to detect communication failures

## Future Improvements

CSV / PDF report export

GUI-based test dashboard

CRC-based packet validation

Multi-channel testing

Support for other MCUs
