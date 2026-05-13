# SETUP.md — AirSense AI

Complete local development setup guide for the AirSense AI project.

---

# Prerequisites

You need these installed before touching the project.

## Required Software

| Tool | Version |
|---|---|
| Flutter | 3.22+ |
| Dart | Latest Stable |
| Android Studio | Latest |
| VS Code (Optional) | Latest |
| Node.js | 20+ |
| Python | 3.11+ |
| PostgreSQL | 15+ |
| Redis | Latest |
| Git | Latest |
| Docker | Latest |

---

# Recommended Machine Specs

Minimum:

- 16GB RAM
- SSD storage
- Intel i5 / Apple M1 or better

Reality:
ML + Android Emulator + Docker together will punish weak hardware.

8GB RAM machines become unstable fast.

---

# Install Flutter

## Verify Installation

```bash
flutter doctor
```

Fix every issue before continuing.

If `flutter doctor` shows red errors and you ignore them, you are building on a broken foundation.

---

# Install Android Studio

Install:

- Android SDK
- Android SDK Command-line Tools
- Android Emulator
- Flutter Plugin
- Dart Plugin

---

# Clone Project

```bash
git clone https://github.com/yourusername/airsense-ai.git
cd airsense-ai
```

---

# Project Structure

```bash
airsense-ai/
│
├── mobile/         # Flutter App
├── backend/        # Node.js API
├── ml-engine/      # Python Forecasting Engine
├── docs/
├── docker/
└── README.md
```

---

# Flutter App Setup

Go inside mobile app:

```bash
cd mobile
```

## Install Dependencies

```bash
flutter pub get
```

## Run Application

```bash
flutter run
```

---

# Backend Setup

Go inside backend:

```bash
cd backend
```

## Install Packages

```bash
npm install
```

## Create Environment File

Create:

```bash
.env
```

Add:

```env
PORT=5000

DATABASE_URL=postgresql://postgres:password@localhost:5432/airsense_ai

REDIS_URL=redis://localhost:6379

JWT_SECRET=super_secret_key

OPENWEATHER_API_KEY=your_api_key
WAQI_API_KEY=your_api_key
GOOGLE_MAPS_API_KEY=your_api_key
```

---

# Setup PostgreSQL

## Create Database

Open PostgreSQL shell:

```bash
psql postgres
```

Create database:

```sql
CREATE DATABASE airsense_ai;
```

---

# Run Database Migrations

Example:

```bash
npm run migrate
```

---

# Start Backend Server

```bash
npm run dev
```

Expected:

```bash
Server running on port 5000
Database connected
Redis connected
```

If database connection fails:
your `.env` is wrong.

Not PostgreSQL’s fault.

---

# Redis Setup

## Mac

```bash
brew install redis
brew services start redis
```

## Ubuntu

```bash
sudo apt install redis-server
sudo service redis start
```

Verify:

```bash
redis-cli ping
```

Expected:

```bash
PONG
```

---

# ML Engine Setup

Go inside ML engine:

```bash
cd ml-engine
```

---

# Create Virtual Environment

## Mac/Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

## Windows

```bash
python -m venv venv
venv\Scripts\activate
```

---

# Install Python Packages

```bash
pip install -r requirements.txt
```

Example packages:

```txt
fastapi
uvicorn
pandas
numpy
scikit-learn
tensorflow
xgboost
prophet
joblib
```

---

# Start ML Server

```bash
python app.py
```

Expected:

```bash
ML Forecast Engine Running
```

---

# API Keys Setup

You need accounts for:

| Service | Purpose |
|---|---|
| OpenWeather | Weather + AQI |
| WAQI | AQI Data |
| Google Maps | Maps + Geolocation |

---

# Google Maps Setup

Enable APIs:

- Maps SDK for Android
- Geocoding API
- Places API

Add key in:

```bash
android/app/src/main/AndroidManifest.xml
```

Example:

```xml
<meta-data
    android:name="com.google.android.geo.API_KEY"
    android:value="YOUR_API_KEY"/>
```

---

# Running Full System

You need 3 services running simultaneously.

## Terminal 1 — Flutter

```bash
cd mobile
flutter run
```

## Terminal 2 — Backend

```bash
cd backend
npm run dev
```

## Terminal 3 — ML Engine

```bash
cd ml-engine
python app.py
```

---

# Recommended Flutter Packages

## State Management

```yaml
flutter_riverpod:
```

## Networking

```yaml
dio:
```

## Maps

```yaml
google_maps_flutter:
```

## Local Storage

```yaml
hive:
shared_preferences:
```

## Charts

```yaml
fl_chart:
```

---

# Recommended Backend Packages

```bash
express
cors
dotenv
jsonwebtoken
bcrypt
pg
redis
axios
helmet
morgan
```

---

# Recommended Architecture

## Mobile

```text
UI
↓
State Management
↓
Repository Layer
↓
API Services
```

## Backend

```text
Routes
↓
Controllers
↓
Services
↓
Database
```

---

# Docker Setup (Optional)

## Start Containers

```bash
docker-compose up --build
```

---

# Example docker-compose.yml

```yaml
version: '3.8'

services:

  postgres:
    image: postgres:15
    environment:
      POSTGRES_DB: airsense_ai
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: password

  redis:
    image: redis

  backend:
    build: ./backend
    ports:
      - "5000:5000"

  ml-engine:
    build: ./ml-engine

```

---

# Common Problems

## 1. Gradle Build Failure

Run:

```bash
flutter clean
flutter pub get
```

---

## 2. Android Licenses Not Accepted

Run:

```bash
flutter doctor --android-licenses
```

---

## 3. Emulator Extremely Slow

Cause:
Insufficient RAM allocation.

Fix:
Use physical device testing.

---

## 4. API Rate Limits

Free AQI APIs are heavily rate-limited.

Cache aggressively.

---

## 5. TensorFlow Installation Issues

TensorFlow versions break frequently.

Pin versions in `requirements.txt`.

Never use floating dependencies in ML projects.

---

# Development Workflow

## Branch Strategy

```text
main
develop
feature/*
bugfix/*
```

---

# Git Workflow

## Create Feature Branch

```bash
git checkout -b feature/forecast-ui
```

## Commit

```bash
git commit -m "Add AQI forecast screen"
```

---

# Production Deployment

## Mobile

- Google Play Store
- Apple App Store

## Backend

- Render
- Railway
- AWS

## Database

- Neon PostgreSQL
- Supabase

---

# Recommended Milestone Order

## Phase 1

- Flutter UI
- AQI API integration
- Location services

## Phase 2

- Backend API
- Database
- Authentication

## Phase 3

- Forecasting engine
- Historical analytics

## Phase 4

- Notifications
- Heatmaps
- Optimization

## Phase 5

- Deployment
- CI/CD
- Production hardening

---

# Critical Advice

Do not try building:
- AI forecasting
- Docker
- CI/CD
- Backend
- Flutter frontend

all simultaneously.

That is beginner suicide.

Sequence matters.

Correct order:
1. Flutter frontend
2. API integration
3. Backend
4. Database
5. ML forecasting
6. Deployment

Otherwise you will drown in debugging with zero visible progress.

---

# Final Goal

This project should become:

- Portfolio-grade
- Production deployable
- Resume differentiator
- Real-world scalable

Most student projects die at:
- authentication
- architecture
- deployment
- state management
- scalability

This one should not.