# Simulated Device Monitoring and Alert System

Student Name: Marjorie Cosadio
Student Number: 2601323
Section: 1 - CPE B

## Project Description
This Python program monitors simulated device-temperature readings. It stores an initial list of readings and allows a user to add valid readings, classify temperatures, and generate a numerical summary. It reports the overall monitoring status based on the classification rules provided in the CPP102 Week 17 module.

## Features
- View all stored temperature readings with their positions.
- Add a whole-number reading from 0 to 100 inclusive.
- Reject empty, non-numeric, negative, and over-100 readings.
- Classify readings as NORMAL, WARNING, or CRITICAL.
- Calculate total, average, minimum, maximum, category counts, and percentages.
- Determine the overall status.
- Repeat the menu until Exit is selected.
- Reject invalid menu choices without closing the program.

## Requirements
- Python 3
- No external packages are required.

## How to Run
1. Open a terminal in the `Week17` folder.
2. Run:

   ```bash
   python device_monitor.py
   ```

   If your system uses `python3`, run:

   ```bash
   python3 device_monitor.py
   ```

## Sample Output
The initial readings are `[28, 31, 35, 37, 29]`. Choosing option 4 displays this summary:

```text
MONITORING SUMMARY
------------------
Number of readings : 5
Total of readings : 160
Average temperature : 32.00 °C
Minimum temperature : 28 °C
Maximum temperature : 37 °C

NORMAL : 2 (40.00%)
WARNING : 2 (40.00%)
CRITICAL : 1 (20.00%)

Overall Status: ATTENTION REQUIRED
```

## Test Cases
Ten required test cases are listed in [test_cases.md](test_cases.md). Run the program and confirm the Actual Result and Pass/Fail columns on your own computer before submission. Do not claim a test passed unless you observed the result.

## Known Limitations
- Readings are stored in memory only and are lost when the program closes.
- The program uses simulated readings; it does not connect to a real device or sensor.
- The program accepts whole-number temperatures only.

## Reflection
This project combines lists, loops, selection statements, functions, input validation, and numerical processing in one program. One important part was handling invalid input before converting it to an integer or adding it to the list. Boundary values such as 30 °C and 35 °C must both be classified as WARNING. I would improve the project in the future by adding a way to save readings, if file handling were allowed.

## Program Structure
The `main()` function controls the menu loop. Helper functions display readings, validate and add new input, classify temperatures, calculate numerical results, count categories, and determine the overall status.

## Classification Rules
- Below 30 °C: `NORMAL`
- 30 °C through 35 °C inclusive: `WARNING`
- Above 35 °C: `CRITICAL`

## Numerical Processing
The total, minimum, and maximum are calculated with loops. The program uses `len()` to count readings and displays the average and category percentages to two decimal places.

## GitHub Submission
Place `device_monitor.py`, `README.md`, and `test_cases.md` in a folder named `Week17` inside your CPP102 GitHub repository. Make at least four meaningful commits from your own computer and push them to GitHub.
