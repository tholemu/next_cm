## Overview
Use this script as a starting point for interacting with the F5 BIG-IP Next Central Manager (CM) API. The `main()` function executes a basic workflow consisting of the following:

1. **Read** AS3 declaration from a local file
2. **Create** the AS3 declaration via the CM API (POST)
3. **Deploy** the AS3 declaration to an F5 BIG-IP Next instance from
   the CM API (POST)
4. **Search** CM's AS3 declaration API for a specific tenant
   and return the ID (GET)
5. **Delete** the deployed declaration via ID (DELETE)

**PATCH** and **PUT** methods are also plumbed into the script (as seen within the `api_call()` function), but the initial iteration of the test workflow does not leverage them. They will be added to showcase reading and deploying a newer version of an AS3 declaration from a file.

In its current state, the script, when run, will execute a static series of events, due to the fact its designed simply to execute the `main()` function and its contents. The script could, and should, be improved to accept command-line arguments which can be passed in, such as `filename` and `instances`. This would make the script more useable and dynamic rather than fixed and static.

## Prerequisites
Create a local file in the same directory as the project named `.env` and populate it with the following variables:

- `ENDPOINT`
- `USERNAME`
- `PASSWORD`

The file contents should resemble the following:

```
ENDPOINT=testcmapi.f5demo.com
USERNAME=thebestusername
PASSWORD=theworstpassword
```

## Script Execution
Run the following command to initiate the CM API test sequence:

```
python3 cm_as3_test.py
```