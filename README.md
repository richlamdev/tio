# tio

````tio```` is a simple and limited CLI to Tenable.IO, written in Python.

Basic usage:

````python3 tio.py [command] [flags]````

## Features:

1) Show scan configuration and history of each configured scan.
2) Export specific scan to local disk in csv/pdf/html/nessus. 
   Note: PDF & HTML option only available within 90 days of the scan.
3) Show server information.
4) Foundational work to expand features in the future.

## Dependencies to run this script are:

1) Linux or Unix Operating System.  Will not work on Windows in present form.
2) Python 3
3) PyTenable Python module
   Install by using:
   pip3 install pytenable


## API Requirement:
Script automatically checks for the presence of API keys at ~/.tio/client.json.
If API keys are not present, the user is prompted for keys on first use and saved.
Note: Secure your keys! In present form they will be stored unencypted on your local drive.


## Examples:
````python3 tio.py info````

````python3 tio.py info -s 1337````
Note, syntax uses history_id to be consistent with Pytenable API documentation, despite returned information is displayed as "id".


````python3 tio.py export -s 1337 -hid 12345678 latest_scan pdf html nessus csv````

````python3 tio.py server````


## To Do:
1) Add color!
2) Provide user friendly error message when pdf or html format is requested for scan older than 90 days.
   Tenable.io will not generate pdf/html for scans older than 90 days.


## Reference:
https://pytenable.readthedocs.io/en/stable/

https://github.com/tenable/pyTenable
