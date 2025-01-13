![logo](https://github.com/user-attachments/assets/cb173f37-f937-4da2-b989-d094c1281e8a)

# Smart Home System

## Overview

The **Smart Home System** is an application designed to centralize control over various home resources, such as blinds and temperature sensors, enhancing comfort, efficiency, and ease of management. This system seamlessly integrates with physical devices and provides a user-friendly web interface for monitoring and control.

## Features

### Frontend

- **Web Application**: Built with React
- **Real-time Monitoring**: View sensor data, such as temperature and humidity, updated in real-time.
- **Blinds Control (not yet implemented)**: Effortlessly open, close, and adjust blinds remotely.
- **Authentication and Role Management**: Secure login functionality with permissions to manage access and visibility.
- **Responsive Design**: Optimized for both desktop and mobile devices.

### Backend

- **API Management**: Powered by Nest.js for robust and scalable backend operations.
- **Database Integration**: Uses PostgreSQL to securely store sensor readings, user information, and other necessary data.
- **Data Analytics**: Provides endpoints for analyzing historical sensor data.
- **Device Integration**: Facilitates communication between frontend and smart devices.

### Devices

1. **MASTER Module** (NodeMCU with nRF24L01+):

   - Connects to the backend via MQTT protocol for data synchronization and device management.
   - Coordinates with SLAVE modules for data transmission and control.

2. **SLAVE Modules**:

   - **SLAVE Type 1**: Arduino Pro Mini + nRF24L01 + DHT11
     - Sends temperature and humidity data to the MASTER every 10 minutes.
     - Operates on battery with energy-efficient deep sleep functionality.
   - **SLAVE Type 2 (not yet ready)**: ESP8266 (ESP-01) for Blinds Control
     - Receives commands from the MASTER for blind positioning.
     - Sends feedback about current blind positions.

3. **Wireless Communication**:
   - Utilizes the nRF24L01 module for efficient and low-power communication between MASTER and SLAVE modules.
   - Data packets use JSON format for flexibility and simplicity.

## Deployment

The application is deployed on a **VPS** running Alpine Linux and accessible at [smart-home.org.pl](http://smart-home.org.pl). Both frontend and backend components are containerized using Docker for scalability and consistency.

## How It Works

1. **Sensor Data Collection**:

   - SLAVE modules measure environmental parameters (e.g., temperature, humidity) and transmit the data to the MASTER.
   - The MASTER forwards the information to the backend using MQTT protocol for storage and processing.

2. **User Interface**:
   - View live sensor readings, analyze historical data, and control devices via the sleek web dashboard.

## Key Technologies

- **Frontend**: React, Tailwind CSS
- **Backend**: Nest.js, PostgreSQL
- **Device Communication**: nRF24L01 modules, NodeMCU, ESP8266/Arduino
- **Deployment**: Docker, Alpine Linux

## Getting Started

1. **Access the application**: Visit [smart-home.org.pl](http://smart-home.org.pl).
2. **Login**: Use your credentials to sign in and access the dashboard.

```bash
Email: test@user.com
Password: TestPassword!234
```

3. **Explore Features**:
   - Monitor live sensor data.
   - Control blinds or other devices. **(not yet implemented)**
   - Manage settings and user roles.

## Future Plans

- Expand support for additional smart devices (e.g., RGB lighting control).
- Enhance analytics for richer insights into home resource usage.
- Develop mobile applications for iOS and Android.
