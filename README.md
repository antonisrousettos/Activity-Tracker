# Distributed Activity Tracker (Android + Java) 📱⚙️

## 📌 Project Overview
This project is a distributed activity tracking system that processes GPX files to extract fitness-related metrics such as distance, time, elevation, and speed.

The system consists of:
- An **Android frontend application**
- A **Java backend** implementing a distributed **Master–Worker architecture**

The goal is to efficiently process large GPX datasets by distributing computation across multiple worker nodes.

---

## 🧠 Key Features

- GPX file upload via Android application
- Distributed processing using Master–Worker model
- Parallel computation of activity metrics
- Real-time communication between client and server
- Visualization of results (charts & statistics)
- Aggregated user and global statistics

---

## 🏗️ System Architecture

### 🔹 Frontend (Android)
- File selection from device storage
- Sends GPX data to backend server via sockets
- Displays:
  - Per-activity results
  - Total statistics (user & global)
- Includes data visualization using bar charts

Example:
- Distance, time, elevation comparisons visualized using charts :contentReference[oaicite:0]{index=0}

---

### 🔹 Backend (Java)

#### Master Node
- Accepts client requests
- Splits GPX data into chunks
- Distributes tasks to workers (Round Robin)
- Aggregates results (Reduce phase) :contentReference[oaicite:1]{index=1}

#### Worker Nodes
- Process chunks of GPX data
- Compute:
  - Distance (Haversine formula)
  - Elevation gain
  - Time differences :contentReference[oaicite:2]{index=2}

#### Client Handler
- Manages communication with Android client
- Returns:
  - Individual GPX results
  - User totals
  - Global totals

---

## ⚙️ Technologies Used

- Java (Backend)
- Android (Frontend)
- Socket Programming
- Distributed Systems (Master–Worker model)
- GPX data processing
- MPAndroidChart (data visualization)

---

## 📊 Computed Metrics

- Total Distance (km)
- Total Time (minutes)
- Elevation Gain (meters)
- Average Speed (m/min)

---

## 🚀 How It Works

1. User selects a GPX file from the Android app
2. File is sent to the server
3. Master:
   - Splits data into chunks
   - Assigns chunks to workers
4. Workers process data in parallel
5. Results are aggregated and returned
6. App displays:
   - Activity results
   - Total statistics

---
## ⚠️ Challenges Faced

- Designing distributed task scheduling (Round Robin)
- Synchronization between threads and shared data
- Efficient parsing of GPX files
- Managing socket communication between Android and backend
- Aggregating distributed results correctly

---

## 💡 Key Learnings

- Distributed systems design (Master–Worker architecture)
- Parallel data processing
- Socket-based communication
- Android–backend integration
- Real-time data handling and visualization

---

