# Docker IoT Development Stack

ชุด Docker สำหรับพัฒนา Web Application และ IoT ประกอบด้วย

- Apache Web Server + PHP
- MySQL 8.4
- phpMyAdmin
- Node-RED
- MQTT Broker (Mosquitto)
- Portainer
- Docker Network แบบ Bridge
- External Bind Mount สำหรับเก็บข้อมูลนอก Container

---

## 1. โครงสร้างโปรเจกต์

```text
my-docker-project/
│
├── docker-compose.yml
│
├── README.md
│
├── node-red/
│   └── data/
│
├── mysql/
│   └── data/
│
├── phpmyadmin/
│
├── apache/
│   └── html/
│       └── index.php
│
├── mqtt/
│   ├── config/
│   │   └── mosquitto.conf
│   ├── data/
│   └── log/
│
└── portainer/
    └── data/

# mqtt/config/mosquitto.conf
```bash
listener 1883
protocol mqtt

listener 9001
protocol websockets

allow_anonymous true

persistence true
persistence_location /mosquitto/data/

log_dest file /mosquitto/log/mosquitto.log
```