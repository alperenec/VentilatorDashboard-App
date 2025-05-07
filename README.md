# Ventilator Dashboard

⚠️ **The source code is not shared in this repository due to privacy and company policies. However, this README provides a comprehensive overview of the project, including its functionality, architecture, and techs used.**

---

## 📌 Overview
Ventilator Dashboard is a real-time monitoring system designed to track and display ventilator data from multiple patients simultaneously across hospital departments. The system combines data from two sources:

**Hospital API Integration** - Connects to hospital information systems via REST API

**MQTT Device Monitoring** - Direct real-time data from ventilator devices


This dual-source approach provides comprehensive monitoring with both administrative context and live medical device data, helping healthcare professionals monitor critical patient parameters in real-time.
</hr>

![image](https://github.com/user-attachments/assets/311c0027-a141-4638-b2e4-3bdd795a3c39)

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

**1️⃣ Multi-Source Data Collection**

**Hospital API Integration 🏥**

Dashboard connects to hospital information system via REST API
Retrieves department structure and ventilator configuration
Uses secure token-based authentication
Refreshes data periodically to maintain synchronization

**Direct Device Monitoring via MQTT 📡**

Ventilators send HL7-based messages over MQTT
The backend subscribes to department-specific topics (hl7/ventilator/{department_id})
Processes incoming data in real-time for immediate display

**2️⃣ Processing & Storage 🗄️**

Backend parses HL7 messages from different ventilator manufacturers
Data is structured and normalized for consistent display
Departmental organization maintains clinical workflow structure

**3️⃣ Real-Time UI Updates 🖥️**

Processed data is pushed to the frontend using SignalR
UI dynamically updates without needing page refreshes
Visual indicators differentiate between API and MQTT data sources

---

## 🛠️ Technologies Used

**Backend:** ASP.NET Core, MQTTnet, SignalR, RESTful API

**Frontend:** JavaScript (Vanilla JS), HTML, CSS

**Communication:** MQTT, SignalR, HTTP/REST

**Data Processing:** HL7 message parsing
