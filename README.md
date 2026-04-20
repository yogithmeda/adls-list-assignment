ADLS File Filter & Automation Assignment
Project Overview
This repository contains a Python-based data engineering tool designed to interact with Azure Blob Storage. The primary objective of this project is to automate the process of listing and filtering specific data assets (specifically .csv.gz files) from a public dataset using GitHub Actions.

This project demonstrates proficiency in:

Cloud Data Interaction: Using the Azure SDK for Python to interface with Azure Blob Storage.

Workflow Automation: Implementing CI/CD principles via GitHub Actions to execute data tasks in an automated environment.

Data Quality & Filtering: Applying transformation logic to isolate relevant structured datasets from a large, public data lake.

Repository Structure
The repository is organized to follow standard DataOps practices:

Plaintext
.
├── .github/
│   └── workflows/
│       └── adls_list.yml       # GitHub Actions workflow configuration
└── adls_practice/
    ├── list_contents.py        # Python script for listing and filtering blobs
    └── requirements.txt        # Project dependencies (azure-storage-blob)
Technical Implementation
Core Logic
The Python script list_contents.py connects to the azurepublicdataset container. I have modified the original script to:

Filter Files: Specifically isolate files with the .csv.gz extension.

Recursive Listing: Traverse the container to ensure all relevant files are captured, even within virtual sub-directories.

Data Integrity: Provide a count of the filtered results to assist with data validation during the workflow run.

Automation Workflow
The GitHub Action is configured with a workflow_dispatch trigger, allowing for manual execution from the GitHub Actions tab. It runs on an ubuntu-latest environment using Python 3.12.

Getting Started
To view the output of this project:

Navigate to the Actions tab of this repository.

Select the "Run ADLS List Script" workflow.

Review the logs of the most recent run to see the filtered list of .csv.gz files.
