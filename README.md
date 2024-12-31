# Shell Script Large File Processing Bug

This repository demonstrates a common error in shell scripts when processing large files: exceeding system limits. The script attempts to read and process a large file line by line, which can cause issues if the file is larger than the system's available memory or buffer size.

## Bug
The original script attempts to process the file line by line using a `while` loop and `read`.  This method is inefficient and may fail with a large file. 

## Solution
The improved script processes the file in smaller chunks. This makes it more robust. It also includes error handling to detect issues during processing.

## How to reproduce
1. Create a large file named `large_file.txt` (e.g., using `head /dev/urandom | tr -dc A-Za-z0-9\n | head -c 10M > large_file.txt`)
2. Run `bug.sh`
3. Run `bugSolution.sh`

Observe the difference in behavior.