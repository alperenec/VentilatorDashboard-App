# Ventilator Dashboard

## 📌 Overview
Ventilator Dashboard is a **real-time monitoring system** designed to track and display ventilator data from multiple patients simultaneously. It leverages **MQTT** for efficient data transmission, processes incoming ventilator metrics on the backend, and provides an interactive UI that updates live using **SignalR**. This system helps healthcare professionals monitor critical patient parameters in real-time, improving decision-making and patient care.

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

## 🏗️ System Architecture
```
[Ventilator Devices] → (MQTT Broker) → [Backend Service] → (SignalR) → [Frontend Dashboard]
```

---

## 🔧 Configuration
The system relies on **MQTT settings**, which are configured in `appsettings.json`:
```json
"MQTTSettings": {
  "DefaultBrokerAddress": "YOUR_ADDRESS",
  "DefaultBrokerPort": 1883,
  "DefaultTopic": "hl7/ventilator"
}
```
Ensure the broker address and topic match your setup.

---

## 🚀 Getting Started
1️⃣ **Clone the Repository**
   ```sh
   git clone https://github.com/alperenec/VentilatorDashboard-App
   cd VentilatorDashboard-App
   ```
2️⃣ **Set Up the Backend**
   - Configure MQTT settings in `appsettings.json`.
   - Run the ASP.NET Core backend.

3️⃣ **Launch the Frontend**
   - Open `index.html` in a browser.
   - Ensure the backend is running to receive real-time updates.
