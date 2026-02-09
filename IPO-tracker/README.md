# 📈 IPO Monitoring and Notification System

An automated system that monitors daily U.S. IPO listings, validates eligible offerings, generates AI-powered summaries, and delivers insights via a frontend interface and optional email notifications.

The system is designed with a modular architecture, scheduled execution, and guardrail validation to ensure reliable and high-quality outputs.

---

## 🚀 Features

- ⏰ Scheduled daily execution at **09:00 Asia/Dubai**
- 📡 Monitors IPOs listed for the current day
- ✅ Filters and validates eligible IPOs
- 🧠 AI-powered IPO summarization using an LLM
- 🛡️ Guardrail validation before AI processing
- 🌐 Frontend delivery of IPO summaries
- 📧 Optional email notifications

---

## 🏗️ Architecture Overview

```text
Scheduler (scheduler.py)
        |
        v
IPO Pipeline (pipeline.py)
        |
        v
Guardrail Validation
        |
        v
LLM Summarization
        |
        v
Frontend Display / Email Notification

```
---

## 🧩 System Components

-  Scheduler Service

Runs continuously as a background process

Triggers the workflow at 09:00 Asia/Dubai

Invokes the IPO processing pipeline

-  IPO Processing Pipeline

Monitors IPOs listed for the current day

Applies eligibility criteria

Returns only validated IPOs in structured JSON format

-  Guardrail Layer

Performs additional validation and compliance checks

Ensures only valid IPO data is passed to the LLM

-  LLM-Based Summarization

Generates concise, investor-friendly IPO summaries

Converts structured IPO data into human-readable insights

-  Delivery Layer

Displays summaries on the frontend

Sends summaries via email when enabled

---


## 🛠️ Technology Stack


Programming Language: Python

Scheduling: APScheduler / Cron

Backend Services: Python-based modular services

Data Source: IPO Market Data API

Data Format: JSON

AI Layer: Large Language Model (LLM)

Validation: Guardrail framework

Notifications: SMTP-based email service

Frontend: Web-based UI

Configuration: Environment variables (.env)

Logging: Python logging framework


## 🔁 Execution Flow


Scheduler triggers the job at 09:00 Asia/Dubai

IPO pipeline fetches and filters IPOs for the day

Eligible IPOs are returned in JSON format

Guardrail validates IPO data

LLM generates IPO summaries

Summaries are delivered to the frontend and optionally via email
