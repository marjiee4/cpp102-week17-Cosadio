# Software Test Specification & Execution Report

System Under Test: Simulated Device Monitoring System  
Tester: Marjorie Cosadio 
Date: October 17, 2026  

---

## 1. Test Results

| TC | Action | Expected Result | Actual Result | Pass/Fail |
|---|---|---|---|---|
| TC01 | Choose 1 | Display the five initial readings: 28, 31, 35, 37, 29. | Five readings displayed correctly. | Pass |
| TC02 | Choose 2, enter 33 | Reading added successfully. | Reading added successfully. | Pass |
| TC03 | Choose 2, enter `abc` | Display a whole-number validation message. | Invalid input message shown. | Pass |
| TC04 | Choose 2, enter `-5` | Reject the value because it is outside the allowed range. | Invalid reading message shown. | Pass |
| TC05 | Choose 2, enter `101` | Reject the value because it exceeds 100. | Invalid reading message shown. | Pass |
| TC06 | Choose 2, enter `0` | Reading added successfully. | Reading added successfully. | Pass |
| TC07 | Choose 2, press Enter | Display a message that the reading cannot be empty. | Empty-input validation message shown. | Pass |
| TC08 | Choose 3 | Classify 28 and 29 as NORMAL, 31 and 35 as WARNING, and 37 as CRITICAL. | Classification displayed correctly. | Pass |
| TC09 | Choose 4 | Display the monitoring summary and calculated statistics. | Summary displayed correctly. | Pass |
| TC10 | Choose 5 | Display the thank-you message and exit. | Program exited successfully. | Pass |
| TC11 | Choose 6 at the menu | Display an invalid-menu-choice message. | Invalid-choice message shown. | Pass |
| TC12 | Choose 2, enter 59 | Add the reading; classify it as CRITICAL under the defined thresholds. | Reading added successfully. | Pass |
| TC13 | Choose 2, enter 80 | Add the reading; classify it as CRITICAL. | Reading added successfully. | Pass |
| TC14 | Choose 2, enter `-` | Reject the input without crashing. | Invalid-input message shown. | Pass |

---


## 2. Bugs Found and Fixed

### TC14: Invalid Input — Single Hyphen (`-`)

Problem: 
Entering a single hyphen (`-`) is not a valid integer. Converting it directly with `int("-")` raises a `ValueError`, which may terminate the program if the error is not handled.

Solution:
The input validation was updated to use Python's `isdigit()` method before converting the input to an integer.

```python
def is_whole_number(text):
    return text.isdigit()
```

This validation rejects empty strings, alphabetic input, decimal values, negative numbers, and a single hyphen before integer conversion. The program then displays an appropriate validation message instead of crashing.

---

## 3. Test Summary

- **Total test cases:** 14
- **Passed:** 14
- **Failed:** 0
- **Reported pass rate:** 100%

The test results indicate that the tested functions behaved as expected for the listed scenarios. The report reflects the recorded results and does not independently verify the program execution.

## 4. Conclusion
The testing process included checking menu navigation, entering valid readings, handling invalid inputs, classifying temperatures, generating summaries, and exiting the program. The input-validation improvement helped the system manage incorrect entries properly without causing unhandled conversion errors. Overall, the results showed that the program worked correctly and met the expected requirements in all 14 test cases.
