
# Aviation Safety: Civil Engineering Case Study

This project implements a program to enhance aviation safety by comparing the aircraft location data recorded by two different sensors. The program flags inconsistencies between the data recorded by the GPS and the air traffic control RADAR system, ensuring data consistency and reliability.

## Table of Contents

1. [Problem Statement](#problem-statement)
2. [Gathering Information](#gathering-information)
3. [Input and Output Description](#input-and-output-description)
4. [Test Cases](#test-cases)
5. [Algorithm Design](#algorithm-design)
6. [Implementation](#implementation)
7. [Usage](#usage)
8. [Acknowledgements](#acknowledgements)

## Problem Statement

Aviation safety is a high priority, with aircraft position data being of paramount importance. Two sensors (GPS and RADAR) record the aircraft's location every quarter second. The data from these sensors is compared to ensure consistency. The program calculates the distance between the recorded locations from both sensors and flags discrepancies that exceed a user-defined tolerance.

## Gathering Information

The program reads sequential (x, y, z) coordinates from two files (file1 from GPS and file2 from RADAR). It calculates the distance between the two sets of coordinates and checks if the distance exceeds a specified tolerance. Discrepancies are logged in an error file (ERR.LOG).

### Coordinates:
- **x-coordinate**: East-West location (east positive)
- **y-coordinate**: North-South location (north positive)
- **z-coordinate**: Altitude (in kilometers)

## Input and Output Description

### Input:
1. Names of the two data files containing the (x, y, z) coordinates.
2. A tolerance value (floating-point) defining the permissible distance between recorded locations.

### Output:
1. ERR.LOG file containing the times and distances where discrepancies exceeded the tolerance.
2. Display of the ERR.LOG file content in a tabular format if it exists.

## Test Cases

### Test Case 1:
**File 1:** `file1.txt`  
**File 2:** `file2.txt`  
**Tolerance:** `0.05`  

### Test Case 2:
**File 1:** `file1.txt`  
**File 2:** `file2.txt`  
**Tolerance:** `0.10`  

### Test Case 3:
**File 1:** `file1.txt`  
**File 2:** `file2.txt`  
**Tolerance:** `0.01`  

### Test Case 4:
**File 1:** `file1.txt`  
**File 2:** `file2.txt`  
**Tolerance:** `0.20`  

## Algorithm Design

### Pseudocode:
1. **Prompt User for Input:**
    - File names for file1 and file2.
    - Tolerance value.

2. **Read Data from Files:**
    - Read (x, y, z) coordinates from both files.
    - Handle cases where files are of different sizes.

3. **Calculate Distance:**
    - Calculate the Euclidean distance between corresponding coordinates from file1 and file2.

4. **Check Tolerance:**
    - If the calculated distance exceeds the tolerance, log the discrepancy in ERR.LOG.

5. **Menu Options:**
    - Calculate and log discrepancies.
    - Display ERR.LOG file content.
    - Exit program.

### Functions:
- `calculateDistance()`
- `readCoordinates()`
- `logError()`
- `displayErrors()`

## Implementation

The project is implemented in C++ using standard libraries for file input/output and mathematical computations. The program is designed to handle different file sizes and validate user inputs.

## Usage

1. **Compile the Program:**
    ```sh
    g++ -o aviation_safety main.cpp
    ```

2. **Run the Program:**
    ```sh
    ./aviation_safety
    ```

3. **Follow the Instructions:**
    - Enter the file names for the GPS and RADAR data.
    - Enter the tolerance value.
    - Choose from the menu options to calculate errors, display the error log, or exit the program.

## Acknowledgements

This project is part of the Civil Engineering Case Study for ENGR-AD 1000, Fall 2022. The assignment was supervised by Prof. Mohammad Eid.

