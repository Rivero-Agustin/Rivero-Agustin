<div align="right">
  🌎 <a href="https://github.com/Rivero-Agustin/Rivero-Agustin/blob/main/README-en.md">English</a> | 🇪🇸 <a href="https://github.com/Rivero-Agustin/Rivero-Agustin/blob/main/README.md">Español</a>
</div>

# Hi! I'm Agustin 👋

I am an IoT Product Developer and an advanced Electronic Engineering student near graduation. I specialize in bridging the physical and digital worlds, mastering everything from low-level microcontroller programming to graphical user interfaces (GUI), web applications, and enterprise process automation.

🛠️ **My Core Tech Stack:**

![C/C++](https://img.shields.io/badge/C%2FC%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![ESP-IDF](https://img.shields.io/badge/ESP--IDF-000000?style=for-the-badge&logo=espressif&logoColor=white)
![LVGL](https://img.shields.io/badge/LVGL-333333?style=for-the-badge)
![Next.js](https://img.shields.io/badge/Next.js-black?style=for-the-badge&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Power Platform](https://img.shields.io/badge/Power_Platform-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)

Below, I present some of the systems and architectures I have worked on:

## 🌟 1. Featured Open-Source Project: Cloud IoT Architecture

_Technologies: ESP32, FreeRTOS, AWS (IoT Core, SQS, IAM), Node.js, MongoDB, Docker, Grafana_

Along with the Embedded Linux Gateway, this public repository serves as my primary **code showcase**, in contrast to the rest of my portfolio developments which are protected under corporate NDAs.

[![View Code](https://img.shields.io/badge/🚀_View_Source_Code_%26_Documentation_➔-0078D4?style=for-the-badge)](https://github.com/Rivero-Agustin/enterprise-iot-telemetry-pipeline)

> **Real-Time Telemetry Visualization:**
>
> ![IoT Demo](https://github.com/Rivero-Agustin/enterprise-iot-telemetry-pipeline/blob/main/docs/demo.dashboard.grafana.gif)
>
> _👆 Grafana Dashboard: End-to-End monitoring consuming data from the AWS Serverless architecture, processed by Node.js, and orchestrated in Docker._

**Architecture & Technical Achievements:**

- **Cloud Infrastructure & Scalability:** Designed a _Serverless_ architecture on AWS, integrating IoT Core and message queuing (SQS) to ensure high-throughput data ingestion without telemetry loss.
- **Cybersecurity & Access Management:** Applied cloud security best practices through strict policy configuration and credential rotation using IAM roles.
- **Microservices Orchestration:** Deployed backend services (Node.js) and database (MongoDB) using Docker containers to guarantee portability and rapid environment replication.
- **Edge-to-Cloud Integration:** Robust connection from physical hardware (ESP32 running FreeRTOS) to the cloud, completing the full data lifecycle from microcontroller to the final visualization dashboard.

---

## 🐧 2. Open-Source Project: Custom Embedded Linux Edge Gateway

_Technologies: Buildroot, QEMU, C/C++, Python, WSL2, TCP/IP Networking_

Design and build of a custom Linux operating system to act as an Edge node. The system processes physical telemetry from UWB (Ultra-Wideband) sensors and securely manages the bridge to AWS IoT Core.

[![View Code](https://img.shields.io/badge/🚀_View_Source_Code_%26_Documentation_➔-0078D4?style=for-the-badge)](https://github.com/Rivero-Agustin/embedded-linux-iot-gateway)

> **Architecture and Networking Diagram:**
>
> ![Architecture Diagram](https://github.com/Rivero-Agustin/embedded-linux-iot-gateway/blob/main/docs/architecture.diagram.png)
>
> _👆 System Architecture: Telemetry dataflow from physical hardware across network tunnels (portproxy) in Windows/WSL2 to the emulated Linux environment and AWS._

**Architecture & Technical Achievements:**

- **Embedded Linux (Buildroot):** Built a minimal root filesystem (`rootfs`) from scratch and cross-compiled for ARM architecture (Cortex-A53).
- **Advanced Networking:** Solved "Double NAT" architectures by configuring Firewall rules, _portproxy_ tunnels, and QEMU _host forwarding_ to expose the local TCP port to physical hardware.
- **Edge Computing (Python):** Implemented local real-time data processing logic, evaluating anomalies and collision risks before dispatching critical events to the cloud, reducing latency and bandwidth consumption.
- **Hybrid Security:** Configured the Gateway as a security boundary, receiving local plaintext telemetry (offloading computation from the ESP32 node) and encapsulating upstream traffic to AWS IoT Core via MQTTS (TLS 1.2).

---

## 📱 3. Mission-Critical Embedded Systems GUI Development

_Technologies: C/C++, ESP-IDF, LVGL, SquareLine Studio, FreeRTOS_

Design and integration of native graphical user interfaces for microcontrollers (ESP32 family) in industrial environments.

> **Interface, Hardware Control, and IoT Connectivity Demonstration (ESP32-P4 with touchscreen):**
>
> https://github.com/user-attachments/assets/e358323d-e6ba-4f4c-9428-898d0fdcbe95
>
> _👆 On screen: LVGL touch UI and power hardware (top-left), Webhook API / BLE web client (top-right), and debug console (bottom)._
>
> **Technical Demo Walkthrough:**
>
> - **Initialization & Connectivity:** Boot sequence featuring Wi-Fi connection, real-time clock synchronization (RTC) via **SNTP** protocol, and initial global telemetry transmission to the cloud via HTTP POST. Menu navigation showcases non-blocking, asynchronous Wi-Fi scanning during GUI rendering.
> - **BLE Validation (Web Bluetooth):** On-demand temporary pairing. The device is securely discovered and authenticated from an external web client over Bluetooth Low Energy.
> - **Security & Rules Engine:** Local authentication via Superuser passcode (with failed attempt handling). The system evaluates concurrent states: when an active "task" is ongoing, the firmware blocks standard hardware unlocking attempts, requiring privilege escalation (Superuser) to override.
> - **Peripheral Control & Real-Time Telemetry:** Physical relay management and status LEDs (Red/Green) indicating locking and access states. The firmware follows an event-driven architecture where every physical state change triggers an instantaneous Webhook (HTTP POST) to keep the external database in sync.

**Architecture & Technical Achievements:**

- **Thread Decoupling & Concurrency:** Implemented an event-driven architecture using **FreeRTOS**, isolating the GUI rendering thread (LVGL) from asynchronous background tasks (Wi-Fi scanning, SNTP sync, HTTP requests), ensuring a smooth 60 FPS user experience with zero blocking code.
- **State Machine & Internal Rules Engine:** Designed concurrent state machine control logic for security management. The system evaluates operational constraints in real time (e.g., locking physical access during critical active tasks) and securely handles hierarchical privilege escalation (Superuser).
- **Non-Blocking Telemetry Ecosystem:** Integrated an asynchronous HTTP client that processes and dispatches JSON payloads to an external API immediately upon power peripheral state changes, optimizing RAM usage and bandwidth consumption.
- **Dual Communication Channel (Hybrid):** Dynamically configured the ESP32 wireless controller to seamlessly switch between Station Mode (Wi-Fi) for cloud data persistence and Bluetooth Low Energy (BLE) for secure provisioning and web-client validation.
- _Note: Source code and detailed schematics are omitted from this repository as they are proprietary and confidential intellectual property._

---

## ⚡ 4. Real-Time Data Acquisition System (End-to-End)

_Technologies: Next.js, React, Electron.js, C/C++, Serial Interface_

End-to-end development of a system defining test-standard workflows to acquire, process, and report physical measurements in real time, bridging custom hardware with high-level software.

> **Data Flow Demonstration:**
>
> https://github.com/user-attachments/assets/65a54fdf-90c3-4da0-abf5-b1c1f1200f7c
>
> _👆 On screen: Full system layout (Next.js desktop app on the left, console on the right, Arduino below)._
>
> - **Hardware Awareness:** Real-time detection of physical board connection/disconnection.
> - **Dynamic Logic:** Execution of 3 simulated measurement cycles. The workflow decision tree automatically adapts based on initial configuration parameters.
> - **File Handling:** Processing acquired data and rendering a final exportable technical report in PDF format.

**Architecture & Achievements:**

- Created a robust serial communication bridge between microcontroller firmware and the Node.js/Electron environment.
- Implemented a simulated data injection (Mocking) architecture to enable asynchronous UI development and stress testing in Next.js independent of physical hardware availability.
- _Note: Ongoing Electronic Engineering Capstone / Final Degree Project._

---

## 🏢 5. Low-Code Enterprise Solutions Architecture

_Technologies: Power Apps, SharePoint, Power Automate_

Digitalization and optimization of corporate workflows for the steel manufacturing industry, replacing manual processes with interactive applications.

> **System Demonstration (Tooling Management):**
>
> https://github.com/user-attachments/assets/770dc185-0d1f-432b-946a-7efe2f8fdf05
>
> _👆 On screen: Complete walkthrough (at 2x speed) of the system's frontend architecture._
>
> - **Data Structuring:** Modular navigation design allowing users to seamlessly transition between user profiles and multiple complex inventory categories.
> - **Enterprise UI/UX Design:** Implementation of clean views tailored for large volumes of data, prioritizing readability and speed.
> - **Filtering Logic:** Real-time dynamic filters to optimize querying and handling of records stored in document libraries.

> **System Demonstration (Inventory Management):**
>
> https://github.com/user-attachments/assets/0946468b-e0d4-498b-b362-3be363607da8
>
> _👆 On screen: Transactional application focused on inventory traceability and physical asset tracking._
>
> - **Access Management (RBAC):** Role-based access control system to enforce security and govern who can view or modify sensitive data.
> - **Financial & Stock Metrics:** Interactive dashboards with advanced filters generating dynamic summaries (breakdown by department, location, and real-time total cost calculation).
> - **Transactional Logic (CRUD):** Stock movement logging workflow ensuring complete traceability and maintaining an auditable transaction history.

**Architecture & Achievements:**

- Designed interactive enterprise management applications connected to SharePoint databases.
- Increased operational efficiency and reduced data entry time in high-demand industrial environments.
- _Note: Developed under corporate confidentiality agreements (NDA)._

---

📫 **Let's Connect!** Find me on [linkedin.com/in/agustin-rivero-/](https://www.linkedin.com/in/agustin-rivero-/)
