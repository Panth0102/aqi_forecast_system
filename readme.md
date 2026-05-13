# AirSense AI — AQI Visualizer & Forecast App

An AI-powered Air Quality Intelligence platform built with Flutter.  
AirSense AI delivers real-time AQI monitoring, predictive forecasting, health insights, pollution analytics, and environmental intelligence for underserved regions.

This project combines satellite data, ground monitoring stations, machine learning forecasting, and modern mobile engineering into a production-grade cross-platform application.

---

# Preview

## Core Features

- Real-time AQI monitoring
- 24h / 7-day AQI forecasting
- Interactive pollution heatmaps
- AI-powered health recommendations
- Historical AQI analytics
- Satellite + ground station integration
- Smart alerts & notifications
- City-wise pollution comparison
- Offline cached data
- Weather + pollution correlation
- Environmental risk visualization

---

# Tech Stack

## Frontend

- Flutter
- Dart
- Riverpod / Provider (State Management)
- Material 3 UI
- Google Maps Flutter
- FL Chart / Syncfusion Charts

## Backend

- Node.js
- Express.js
- REST API Architecture

## Database

- PostgreSQL
- Redis (Caching Layer)

## AI / Forecasting

- Python
- Scikit-learn
- TensorFlow / XGBoost
- Pandas + NumPy

## Cloud & DevOps

- Docker
- Firebase Cloud Messaging
- GitHub Actions
- AWS / Railway / Render

---

# System Architecture

```text
Flutter App
     ↓
REST API (Node.js)
     ↓
PostgreSQL Database
     ↓
ML Forecasting Engine (Python)
     ↓
External AQI + Weather APIs
```

---

# APIs Used

## Air Quality APIs

- OpenWeather Air Pollution API
- WAQI API
- IQAir API

## Weather APIs

- OpenWeather API
- WeatherAPI

## Geolocation APIs

- Google Maps API
- Geocoding API

---

# Folder Structure

```bash
lib/
│
├── core/
│   ├── constants/
│   ├── theme/
│   ├── services/
│   └── utils/
│
├── features/
│   ├── auth/
│   ├── home/
│   ├── forecast/
│   ├── analytics/
│   ├── maps/
│   └── settings/
│
├── models/
├── providers/
├── repositories/
├── widgets/
└── main.dart
```

---

# Key Learning Outcomes

This project demonstrates production-level engineering skills.

## Mobile Engineering

- Flutter architecture
- Cross-platform development
- State management
- API integration
- Performance optimization
- Offline-first design

## Backend Engineering

- REST API development
- Authentication systems
- Database design
- Caching strategies
- Cloud deployment

## AI / Data Science

- Time-series forecasting
- AQI prediction models
- Data preprocessing
- Feature engineering
- Environmental data analysis

## DevOps

- Dockerization
- CI/CD pipelines
- Cloud hosting
- Monitoring & logging

---

# Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/airsense-ai.git
cd airsense-ai
```

---

# Flutter Setup

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

## Install Backend Dependencies

```bash
cd backend
npm install
```

## Start Server

```bash
npm run dev
```

---

# ML Engine Setup

## Install Python Dependencies

```bash
pip install -r requirements.txt
```

## Start ML Service

```bash
python app.py
```

---

# Environment Variables

Create a `.env` file:

```env
OPENWEATHER_API_KEY=your_key
WAQI_API_KEY=your_key
GOOGLE_MAPS_API_KEY=your_key

DATABASE_URL=your_database_url
REDIS_URL=your_redis_url

JWT_SECRET=your_secret
```

---

# Screens Included

- Home Dashboard
- AQI Detail Screen
- Forecast Screen
- Pollution Heatmap
- Health Advisory Panel
- Historical Analytics
- Alert Configuration
- City Comparison Dashboard

---

# AI Forecasting Model

The forecasting engine predicts AQI levels using:

- Historical AQI data
- Weather conditions
- Humidity
- Temperature
- Wind speed
- Seasonal patterns
- Traffic & industrial indicators

Models explored:

- Random Forest
- XGBoost
- LSTM
- Prophet

---

# Performance Goals

| Metric | Target |
|---|---|
| API Response Time | < 300ms |
| Forecast Accuracy | > 85% |
| App Startup Time | < 2s |
| Crash-free Sessions | > 99% |

---

# Security

- JWT Authentication
- HTTPS APIs
- Environment-based secrets
- Input validation
- Rate limiting
- Secure token storage

---

# Future Improvements

- AI chatbot for health advice
- IoT sensor integration
- WearOS / Apple Watch support
- Real-time crowd pollution reporting
- Smart route planning based on AQI
- Carbon footprint tracking
- AI anomaly detection

---

# Why This Project Matters

Most AQI apps are glorified dashboards.  
This project focuses on predictive environmental intelligence.

The differentiation:

- Forecasting instead of static AQI
- Granular underserved-region coverage
- AI-driven health recommendations
- Scalable architecture
- Real-world environmental impact

This is resume-grade engineering work, not tutorial-level CRUD.

---

# Challenges Solved

- Handling inconsistent environmental datasets
- Forecasting noisy AQI data
- Real-time caching optimization
- Battery-efficient background updates
- Geospatial visualization performance
- Multi-source API normalization

---

# Deployment

## Flutter App

- Android Play Store
- iOS App Store

## Backend

- Railway
- Render
- AWS EC2

## Database

- Neon PostgreSQL
- Supabase

---

# Contributing

Pull requests are welcome.

For major changes:

1. Fork repository
2. Create feature branch
3. Commit changes
4. Push branch
5. Open PR

---

# License

MIT License

---

# Author

Developed by Panth Sutaria

---

# Resume Impact

This project demonstrates:

- Full-stack mobile engineering
- AI/ML integration
- Production architecture
- Cloud deployment
- Real-world problem solving
- Scalable application design

A weak portfolio has clone apps.

A strong portfolio has infrastructure, forecasting, architecture, and data engineering.

This project sits in the second category.