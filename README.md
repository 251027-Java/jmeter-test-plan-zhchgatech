[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/Gfc2lSRr)
# Lab: Create JMeter Test Plan

## Goal
Create a JMeter test plan to performance test a REST API.

## Learning Objectives
- Create Thread Groups with appropriate settings
- Configure HTTP Request samplers
- Add assertions for validation
- Use listeners to analyze results

## Pre-requisites
- JMeter installed (5.x recommended)
- Java 8+ installed

## Tasks

### Task 1: Install JMeter
1. Download from https://jmeter.apache.org/download_jmeter.cgi
2. Extract to a folder
3. Run JMeter:
   - Windows: `bin\jmeter.bat`
   - Mac/Linux: `./bin/jmeter`

### Task 2: Create New Test Plan
1. File → New
2. Rename Test Plan to "API Performance Test"

### Task 3: Add Thread Group
Configure:
- **Number of Threads (users)**: 10
- **Ramp-Up Period**: 5 seconds
- **Loop Count**: 3

### Task 4: Add HTTP Request Defaults
Add → Config Element → HTTP Request Defaults
- Server Name: `httpbin.org`
- Protocol: `https`

### Task 5: Add HTTP Requests
Create 3 HTTP Request samplers:

**Request 1: GET Request**
- Name: GET /get
- Method: GET
- Path: /get

**Request 2: POST Request**
- Name: POST /post
- Method: POST
- Path: /post
- Body Data: `{"test": "data"}`
- Add Header Manager: `Content-Type: application/json`

**Request 3: Delayed Request**
- Name: GET /delay/1
- Method: GET
- Path: /delay/1

### Task 6: Add Assertions
For each request, add:
- Response Assertion → Response Code = 200

### Task 7: Add Listeners
Add the following listeners:
1. View Results Tree
2. Summary Report
3. Aggregate Report

### Task 8: Run Test
1. Save the test plan
2. Click the green Play button
3. Observe results in listeners

### Task 9: Analyze Results
Answer these questions:
1. What was the average response time?
2. What was the throughput (requests/second)?
3. Did any requests fail?
4. Which endpoint was slowest?

## Deliverables
1. JMeter test plan file (`.jmx`)
2. Screenshot of Summary Report
3. Answers to analysis questions

## Bonus Tasks
- Add a Constant Timer (500ms) between requests
- Increase threads to 50 and observe behavior
- Export results to CSV
