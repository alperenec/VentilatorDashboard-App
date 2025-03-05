# Ventilator Dashboard

⚠️ **The source code is not shared in this repository due to privacy and company policies. However, this README provides a comprehensive overview of the project, including its functionality, architecture, and techs used.**

---

## 📌 Overview
Ventilator Dashboard is a **real-time monitoring system** designed to track and display ventilator data from multiple patients simultaneously. It leverages **MQTT** for efficient data transmission, processes incoming ventilator metrics on the backend, and provides an interactive UI that updates live using **SignalR**. This system helps healthcare professionals monitor critical patient parameters in real-time, improving decision-making and patient care.
</hr>


https://github.com/user-attachments/assets/dc329924-c694-41ad-8a8e-6566eb2ac2a9


---

## ✨ Features
✅ **Real-time Data Streaming** - Utilizes MQTT to receive ventilator data continuously.  
✅ **Live UI Updates** - SignalR ensures instant updates as new data arrives.  
✅ **Multi-Patient Monitoring** - Displays ventilator data for multiple patients at once.  
✅ **Structured Data Processing** - Parses and processes ventilator readings efficiently.  
✅ **User-Friendly Dashboard** - Clean and responsive UI for easy monitoring.  

---

## ⚙️ How It Works
1️⃣ **Data Collection via MQTT** 📡  
   - Ventilators send **HL7-based** messages over MQTT.
   - The backend subscribes to the topic (`hl7/ventilator`) to receive these messages.

2️⃣ **Processing & Storage** 🗄️  
   - The backend extracts relevant ventilator parameters from HL7 messages.
   - Data is structured and processed for real-time visualization.

3️⃣ **Real-Time UI Updates** 🖥️  
   - The processed data is pushed to the frontend using **SignalR**.
   - The UI dynamically updates without needing a full page refresh.

---

## 🛠️ Technologies Used
- **Backend**: ASP.NET Core, MQTTnet, SignalR
- **Frontend**: JavaScript (Vanilla JS), HTML, CSS
- **Messaging**: MQTT (Message Queuing Telemetry Transport)
- **Data Processing**: HL7 message parsing


---

## 📂 Project Files & Responsibilities
### 🏷️ Backend Services
- **`MQTTService.cs`** → Handles MQTT connection, subscribes to ventilator data topic, and processes incoming messages.
- **`MqttBackgroundService.cs`** → A background service that maintains the MQTT connection and ensures data flow.
- **`VentilatorDataProcessor.cs`** → Parses HL7 messages received via MQTT, extracts key ventilator metrics, and stores them for further use.
- **`VentilatorDataSenderService.cs`** → Sends processed ventilator data to the frontend using SignalR for real-time updates.
- **`RandomDataService.cs`** → Generates random ventilator data for testing purposes.

### 🏷️ Frontend & UI
- **`site.js`** → Manages real-time updates via SignalR, processes incoming data, and updates the UI dynamically.
- **`site.css`** → Defines the styling for the ventilator dashboard, ensuring a responsive design.
- **`Index.cshtml`** → The main frontend page where ventilator data is displayed.

### 🏷️ SignalR & API
- **`VentilatorDataHub.cs`** → A SignalR hub that facilitates real-time communication between the backend and frontend.
- **`Program.cs`** → Configures the application, including services, CORS policies, and SignalR setup.
- **`appsettings.json`** → Contains application configurations, including MQTT broker settings.


---

## 🏗️ System Architecture
```
[Ventilator Devices] → (MQTT Broker) → [Backend Service] → (SignalR) → [Frontend Dashboard]
```

---
