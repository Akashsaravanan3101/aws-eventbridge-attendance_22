# AWS EventBridge Attendance Automation

Automated HRMS attendance reporting using AWS EventBridge Scheduler, IAM, API Gateway, and notification services.

## 📌 Overview

This project demonstrates how to automate a daily HRMS attendance report using AWS services.

The workflow runs automatically at a scheduled time, authenticates the request using AWS IAM, calls an HRMS Attendance API through API Gateway, and sends the attendance report through Email and Slack.

## 🏗️ Architecture

```text
                         AWS
                          │
                          ▼
                EventBridge Scheduler
                   Every day at 8 PM
                          │
                          │
                    Assumes IAM Role
                          │
                          ▼
                    API Gateway
                  AWS_IAM Authorization
                          │
                          │ Authorized Request
                          ▼
                 HRMS Attendance API
                          │
                    ┌─────┴─────┐
                    │           │
                    ▼           ▼
                  Email        Slack
                  Report       Report
