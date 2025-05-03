# SentraLogix - AI-Powered Event Insight Tool

A smarter, AI-powered alternative to the traditional Windows Event Viewer.

---

## Table of Contents
- [Overview](#overview)
- [Project Objective](#project-objective)
- [Why This Tool?](#why-this-tool)
- [Core Features](#core-features)
  - [1. Log Ingestion Engine](#1-log-ingestion-engine)
  - [2. Normalization and Storage](#2-normalization-and-storage)
  - [3. Backend API Service](#3-backend-api-service)
  - [4. Frontend UI](#4-frontend-ui)
  - [5. AI & NLP Modules](#5-ai--nlp-modules)
  - [6. Anomaly Detection System](#6-anomaly-detection-system)
  - [7. User & Role Management](#7-user--role-management)
  - [8. Alerting and Notifications](#8-alerting-and-notifications)
  - [9. Reports and Exporting](#9-reports-and-exporting)
- [Technologies Used](#technologies-used)
- [How It Works](#how-it-works)
- [Comparison with Windows Event Viewer](#comparison-with-windows-event-viewer)
- [Planned Roadmap](#planned-roadmap)

---

## Overview

**LogiSage** is an advanced event monitoring and analysis tool designed as a modern, AI-enhanced replacement for the default Windows Event Viewer. It offers real-time log collection, intuitive user interfaces, anomaly detection, and smart insights via AI.

## Project Objective

The goal is to provide a modernized, user-friendly, and intelligent platform for IT administrators, cybersecurity professionals, and analysts to:

- Monitor system events
- Detect anomalies and suspicious behaviors
- Understand patterns through AI-generated summaries
- Search logs using natural language

## Why This Tool?

While Windows Event Viewer provides access to logs, it lacks advanced search capabilities, context, correlation, visualization, and intelligent insights. This tool addresses those limitations through:

- Full-text and AI-powered search
- Custom alerts and real-time analysis
- Timeline visualization of events
- AI-generated summaries
- User-friendly, modern interface

## Core Features

### 1. Log Ingestion Engine

- Collects logs from:
  - Windows Event Logs via Win32 APIs or PowerShell
  - Application logs
  - External sources (planned feature)
- Supports real-time streaming and scheduled pulls

### 2. Normalization and Storage

- Converts raw log entries into structured format (JSON)
- Stores logs in PostgreSQL for relational access
- Uses Elasticsearch for fast text search and filtering

### 3. Backend API Service

- Built using **FastAPI**
- Provides RESTful endpoints for:
  - Log retrieval and filtering
  - User management
  - AI queries
  - Exporting data
- Includes task queue (Celery/RQ) for background jobs

### 4. Frontend UI

- Built with **React** and **Tailwind CSS**
- Core Views:
  - **Dashboard**: Stats and charts
  - **Log Table**: Searchable and filterable
  - **Event Details**: Full log with metadata
  - **Timeline**: Event flow by timestamp
  - **Alerts**: List of triggered alerts
  - **AI Panel**: Summaries, trends, insights

### 5. AI & NLP Modules

- **Natural Language Search**:
  - Accepts input like "show login failures from last week"
  - Uses transformers or spaCy for parsing
- **AI Summarizer**:
  - Groups logs by frequency, user, or action
  - Generates human-readable summaries
- **Log Classification**:
  - Uses pre-trained models or custom-trained classifiers
  - Tags logs as Security, Warning, Error, Info

### 6. Anomaly Detection System

- Uses unsupervised ML algorithms (Isolation Forest, Autoencoders)
- Detects patterns such as:
  - Sudden spikes in login attempts
  - System file access by non-admins
  - Irregular process launches
- Optional supervised models based on training data

### 7. User & Role Management

- Built-in authentication and role system:
  - Admin, Analyst, Viewer
- Login via JWT
- Each user can customize preferences and save filters

### 8. Alerting and Notifications

- Custom alert rules based on event types or thresholds
- Supports in-app notifications, email, and Slack/webhooks
- Scheduled or real-time

### 9. Reports and Exporting

- Generate PDF/CSV/Markdown reports
- Includes daily, weekly summaries
- Option to export filtered logs

## Technologies Used

- **Frontend**: React, Tailwind CSS, Chart.js
- **Backend**: FastAPI, PostgreSQL, Elasticsearch, Celery, Python
- **AI/NLP**: spaCy, Hugging Face Transformers, scikit-learn, OpenAI API
- **Deployment**: Docker, Nginx, Supervisor (for services)
- **Other**: Log parsing tools, Windows APIs, PowerShell scripts

## How It Works

1. **Log Collection**: System agent or service collects logs and sends them to the backend
2. **Storage**: Logs are normalized and stored in a database and Elasticsearch
3. **UI Access**: Users log into the dashboard and use advanced filters/search
4. **AI Analysis**: Periodic jobs analyze logs for summaries and anomalies
5. **Alerts**: Alerts are triggered and displayed in the UI or sent via channels
6. **Reports**: Users can export logs or view automated summaries

## Comparison with Windows Event Viewer

| Feature                | Windows Event Viewer | LogiSage |
|------------------------|----------------------|----------|
| Basic log viewing      | Yes                  | Yes      |
| Filtering & search     | Limited              | Advanced + NLP |
| Real-time updates      | No                   | Yes      |
| Visual timeline        | No                   | Yes      |
| AI summaries           | No                   | Yes      |
| Anomaly detection      | No                   | Yes      |
| Alerts                 | Minimal              | Fully configurable |
| Exporting              | Basic                | Advanced (PDF/CSV/Markdown) |
| Multi-user roles       | No                   | Yes      |
| Remote logs            | No                   | Planned  |

## Planned Roadmap

1. **MVP Phase**
   - Log ingestion, table view, filters

2. **Phase 2**
   - Charts, exporting, visual timeline

3. **Phase 3**
   - Natural language search, AI summaries

4. **Phase 4**
   - Anomaly detection, correlation engine

5. **Phase 5**
   - Plugins, remote agents, desktop app (Electron)

---

**Stay tuned for development updates**
