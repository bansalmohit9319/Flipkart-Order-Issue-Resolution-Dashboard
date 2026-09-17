# Flipkart Order Issue Resolution Dashboard

## About the Project

I built this project as a Python-based order issue resolution dashboard for analyzing different types of customer and order-related problems.

The main idea behind the project is simple: when there are many orders, refunds, complaints, and support tickets, it can become difficult to identify which cases need attention first.

This dashboard brings the data together and helps identify issues such as delayed deliveries, refund problems, repeated complaints, and escalated support tickets. Based on these different signals, the project assigns an issue priority and suggests a suitable action.

This project is created for educational and demonstration purposes and uses synthetic data.

## What This Project Does

The project works with multiple datasets related to:

- Orders
- Customers
- Sellers
- Refunds
- Customer Complaints
- Support Tickets
- Status Notes

The data is first loaded and checked for common data quality problems. After that, it is cleaned and standardized so that it can be used for further analysis.

The project then looks at different areas of the order lifecycle, including delivery delays, refunds, complaints, and support tickets.

## Main Features

### Data Loading

The project loads data from different file formats such as CSV, Excel, JSON, and TXT.

### Data Validation

I added validation checks for:

- Required columns
- Duplicate order IDs
- Customer and seller relationships
- Orphan records
- Invalid dates
- Suspicious order amounts
- Suspicious refund amounts

Invalid records are not deleted silently. They are flagged for review.

### Data Cleaning

The cleaning step includes:

- Removing unnecessary whitespace
- Standardizing text and status values
- Converting dates into proper datetime format
- Converting amount and time fields into numeric values

I used helper functions so the same cleaning logic does not have to be repeated for every dataset.

### Delivery Delay Analysis

The project compares the promised delivery date with the actual delivery date to calculate delivery delays.

Pending orders are also checked to see whether their promised delivery date has already passed.

The delays are grouped into different categories such as:

- On Time
- Minor Delay
- Moderate Delay
- Severe Delay

### Refund Risk Analysis

Refund-related information is analyzed to identify cases such as:

- Pending refunds
- Failed refunds
- Refunds crossing the defined SLA
- Refund amount mismatches
- Refunds connected with delayed orders

### Customer Complaint Analysis

Customer complaints are aggregated at the order level.

The project also identifies:

- Negative complaints
- Angry complaints
- Repeated complaints
- Complaint-related risk

### Support Ticket Analysis

Support tickets are also mapped to orders.

The analysis includes:

- Number of tickets
- Escalated tickets
- SLA breaches
- Resolution time
- Repeated support issues

### Issue Prioritization

One of the main parts of the project is issue prioritization.

Instead of looking at only one problem, I combine multiple signals such as delivery delays, refund issues, complaints, and support escalations.

The final issue score is used to classify cases into:

- Critical
- High
- Medium
- Low

### Recommended Action

After identifying the issue priority, the project generates a recommended operational action for the case.

This makes the dashboard more useful for support and operations analysis because it does not only show the problem, but also suggests what type of action may be required.

### AI-Ready Prompt

The project also generates an AI-ready prompt preview for each case.

The prompt contains the important case details in a structured format so that it can be used for possible future AI integration.

No external AI API is called by this project.

## Project Workflow

```text
Load Data
   ↓
Validate Data
   ↓
Clean & Standardize
   ↓
Delivery Analysis
   ↓
Refund Analysis
   ↓
Complaint Analysis
   ↓
Support Ticket Analysis
   ↓
Create Final Feature Table
   ↓
Calculate Issue Score
   ↓
Assign Issue Priority
   ↓
Generate Recommended Action
   ↓
Generate AI-Ready Prompt
   ↓
Final Report
