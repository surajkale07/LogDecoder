# Log Decoder Script

## Overview

This Python script processes log files to extract and analyze key information for cybersecurity-related tasks. 
The script is designed to meet the following requirements:

1. **Count Requests per IP Address**
2. **Identify the Most Frequently Accessed Endpoint**
3. **Detect Suspicious Activity**
4. **Output Results to a CSV File**

## Features

- **Requests per IP Address**: Counts the number of requests made by each IP address and sorts them in descending order.
- **Most Accessed Endpoint**: Identifies the most frequently accessed resource or URL from the log file.
- **Suspicious Activity Detection**: Flags IP addresses with failed login attempts exceeding a configurable threshold (default is 10).
- **CSV Output**: Saves the results in a structured CSV file named `log_analysis_results.csv`. The CSV contains three sections: 
  - Requests per IP
  - Most Accessed Endpoint
  - Suspicious Activity

## Input

The script processes log files in a format similar to the sample below:

```
192.168.1.1 - - [03/Dec/2024:10:12:34 +0000] "GET /home HTTP/1.1" 200 512
203.0.113.5 - - [03/Dec/2024:10:12:35 +0000] "POST /login HTTP/1.1" 401 128 "Invalid credentials"
...
```

## Output

The script generates a CSV file with the following structure:

### Requests per IP
| IP Address       | Request Count |
|------------------|---------------|
| 192.168.1.1      | 6             |
| 203.0.113.5      | 10            |

### Most Accessed Endpoint
| Endpoint         | Access Count  |
|------------------|---------------|
| /home            | 6             |

### Suspicious Activity
| IP Address       | Failed Login Count |
|------------------|---------------------|
| 203.0.113.5      | 10                  |
| 192.168.1.100    | 6                   |

## Usage

1. **Run the script**: Execute the Python script on a terminal or IDE with the log file `sample.log` in the same directory.
2. **View Results**: The analysis results will be displayed on the terminal and saved in the `log_analysis_results.csv` file.

## Configuration

- **Threshold for Suspicious Activity**: Change the `FAILED_LOGIN_THRESHOLD` variable in the script to customize the limit for failed login attempts.

## File Structure

- `sample.log`: Example input log file.
- `log_analysis_results.csv`: Output CSV file.
- `log_analysis_script.py`: The Python script performing the analysis.

## Example

**Command**:
```
python log_analysis_script.py
```

**Output on Terminal**:
```
Requests per IP:
192.168.1.1          6
203.0.113.5          10

Most Frequently Accessed Endpoint:
/home (Accessed 6 times)

Suspicious Activity Detected:
203.0.113.5          10
192.168.1.100        6
```

## Dependencies

- Python 3.x
- No additional libraries required (uses standard Python libraries).

## Author

Nandini Kokare  
