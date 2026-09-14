<div align="right">
  🌎 <a href="https://github.com/Rivero-Agustin/Rivero-Agustin/blob/main/README-en.md">English</a> | 🇪🇸 <a href="https://github.com/Rivero-Agustin/Rivero-Agustin/blob/main/README.md">Español</a>
</div>

# ¡Hola! Soy Agustin 👋

Soy Desarrollador de Sistemas Embebidos y Soluciones Cloud IoT, y estudiante avanzado de Ingeniería Electrónica pronto a recibirme. Me especializo en conectar el mundo físico con el digital, dominando desde la programación a bajo nivel en microcontroladores hasta el desarrollo de interfaces gráficas, aplicaciones web y automatización de procesos corporativos.

🛠️ **Mi Stack Principal:**

![C/C++](https://img.shields.io/badge/C%2FC%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![ESP-IDF](https://img.shields.io/badge/ESP--IDF-000000?style=for-the-badge&logo=espressif&logoColor=white)
![LVGL](https://img.shields.io/badge/LVGL-333333?style=for-the-badge)
![Next.js](https://img.shields.io/badge/Next.js-black?style=for-the-badge&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Power Platform](https://img.shields.io/badge/Power_Platform-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)

A continuación, presento algunos de los sistemas y arquitecturas en los que he trabajado:

## 🌟 1. Proyecto Open-Source Destacado: Arquitectura Cloud IoT

_Tecnologías: ESP32, FreeRTOS, AWS (IoT Core, SQS, IAM), Node.js, MongoDB, Docker, Grafana_

Junto con el Gateway IoT Edge en Linux Embebido con IA, este repositorio público funciona como mi **prueba de código** principal, contrastando con el resto de los desarrollos del portfolio que se encuentran bajo acuerdos de confidencialidad corporativa.

[![Ver Código](https://img.shields.io/badge/🚀_Ver_Código_Fuente_y_Documentación_➔-0078D4?style=for-the-badge)](https://github.com/Rivero-Agustin/enterprise-iot-telemetry-pipeline)

> **Visualización de Telemetría en Tiempo Real:**
>
> ![Demo IoT](https://github.com/Rivero-Agustin/enterprise-iot-telemetry-pipeline/blob/main/docs/demo.dashboard.grafana.gif)
>
> _👆 Dashboard en Grafana: Monitoreo End-to-End consumiendo datos desde la arquitectura Serverless en AWS, procesados por Node.js y orquestados en Docker._

**Arquitectura y Logros Técnicos:**

- **Infraestructura Cloud y Escalabilidad:** Diseño de una arquitectura _Serverless_ en AWS, integrando IoT Core y colas de mensajes (SQS) para garantizar la ingesta masiva de datos sin pérdida de telemetría.
- **Ciberseguridad y Gestión de Accesos:** Aplicación de buenas prácticas de seguridad en la nube mediante la configuración estricta de políticas y rotación de credenciales con roles IAM.
- **Orquestación de Microservicios:** Despliegue del backend (Node.js) y bases de datos (MongoDB) utilizando contenedores Docker para asegurar la portabilidad y rápida replicación del entorno.
- **Integración Edge-to-Cloud:** Conexión robusta del hardware físico (ESP32 operando con FreeRTOS) hacia la nube, cerrando el ciclo completo del dato desde el microcontrolador hasta el dashboard de visualización final.

---

## 🐧 2. Proyecto Open-Source: Gateway IoT Edge en Linux Embebido con IA & Pipeline CI/CD: Prevención de Colisiones

_Tecnologías: TinyML, Edge Impulse, Buildroot, Linux Embebido, FreeRTOS, ESP-IDF, C/C++, Python, GitHub Actions, CI/CD HIL, AWS IoT Core_

Sistema integral de prevención de colisiones industriales con arquitectura de inteligencia Edge-to-Cloud en dos niveles: clasificación de trayectorias cinemáticas y filtrado de ruido RF mediante **redes neuronales TinyML (Edge Impulse)** directamente en el microcontrolador (ESP32 + UWB), procesamiento y correlación local de eventos sobre un **Gateway Linux Embebido a medida (Buildroot)** (>80% de reducción de ancho de banda cloud), enlace seguro a **AWS IoT Core** y pipeline automatizado de **CI/CD con pruebas Hardware-in-the-Loop (HIL)** sobre hardware físico.

[![Pipeline CI/CD PlatformIO](https://github.com/Rivero-Agustin/embedded-linux-iot-gateway/actions/workflows/build.yml/badge.svg)](https://github.com/Rivero-Agustin/embedded-linux-iot-gateway/actions/workflows/build.yml)
![TinyML](https://img.shields.io/badge/TinyML-Edge_Impulse-0052CC?style=for-the-badge&logo=edgeimpulse&logoColor=white)
[![Ver Código](https://img.shields.io/badge/🚀_Ver_Código_Fuente_y_Documentación_➔-0078D4?style=for-the-badge)](https://github.com/Rivero-Agustin/embedded-linux-iot-gateway)

> **Diagrama de Arquitectura y Flujo de Datos:**
>
> ![Diagrama de Arquitectura](https://github.com/Rivero-Agustin/embedded-linux-iot-gateway/blob/main/docs/architecture.diagram.png)
>
> _👆 Arquitectura del sistema: Inferencia TinyML on-device en ESP32, flujo de telemetría hacia el Gateway Linux Embebido (Buildroot) a través de túneles portproxy en WSL2/Windows, correlación local de eventos y despacho de alertas críticas a AWS IoT Core._

> **Pipeline de CI/CD y Hardware-in-the-Loop (HIL):**
>
> ![Diagrama del Pipeline CI/CD & HIL](https://github.com/Rivero-Agustin/embedded-linux-iot-gateway/blob/main/docs/pipeline.cicd.png)
>
> _👆 Pipeline automatizado en dos etapas: validación y tests unitarios en la nube (x86) seguidos de ejecución de pruebas sobre la placa física ESP32 vía runner local y despliegue continuo (CD)._

**Arquitectura y Logros Técnicos:**

- **Inferencia TinyML On-Device (Edge Impulse C++ SDK):** Despliegue de red neuronal optimizada en ESP32 para clasificar cinemática y calidad del enlace RF en tiempo real en 4 estados (`vehicle_hazard`, `pedestrian_approach`, `static_safe` y filtrado de ruido por obstrucción `nlos_noise`), analizando multicanal UWB (`distance`, `rx_power`, `fp_power`) con ventana deslizante determinista de 15 muestras y sin asignación dinámica de memoria en el bucle caliente.
- **Embedded Linux (Buildroot):** Construcción desde cero de un sistema de archivos raíz (`rootfs`) mínimo y compilación cruzada para arquitectura ARM (Cortex-A53), emulado en QEMU con broker MQTT local y servicio Edge en Python.
- **Inteligencia en el Borde en Dos Niveles:** El Gateway actúa como segundo nivel de decisión: correlaciona las predicciones TinyML del microcontrolador (activando alertas ante `vehicle_hazard` con confianza > 60%), evalúa reglas heurísticas de respaldo (peligro sostenido y salto brusco) y reduce en más de un **80%** la ingesta de datos hacia AWS IoT Core.
- **Firmware Asimétrico Dual-Core (FreeRTOS):** Segregación física de tareas en ESP32: Core 1 para cálculo ToF UWB en nanosegundos, inferencia TinyML y actualización OLED; Core 0 para la pila Wi-Fi y colas MQTT nativas de ESP-IDF, aprovechando memoria externa PSRAM.
- **Pipeline CI/CD con Hardware-in-the-Loop (HIL):** Flujo automatizado en GitHub Actions en dos fases: compilación y tests unitarios en x86 (Unity Framework) con compilación cruzada en la nube, seguido de pruebas automáticas sobre la placa física ESP32 vía runner local self-hosted y despliegue continuo (CD) con inyección segura de credenciales.
- **Networking Avanzado y Seguridad Criptográfica:** Resolución de entornos "doble NAT" mediante túneles _portproxy_, firewall y _host forwarding_ en QEMU; encapsulación criptográfica de alertas hacia AWS IoT Core vía MQTTS (TLS 1.2 / certificados X.509).

---

## 📱 3. Desarrollo de GUI para Sistemas Embebidos Críticos

_Tecnologías: C/C++, ESP-IDF, LVGL, SquareLine Studio, FreeRTOS_

Diseño e integración de interfaces gráficas nativas para microcontroladores (familia ESP32) en entornos industriales.

> **Demostración de Interfaz, Control de Hardware y Conectividad IoT (ESP32-P4 con pantalla táctil):**
>
> https://github.com/user-attachments/assets/e358323d-e6ba-4f4c-9428-898d0fdcbe95
>
> _👆 En pantalla: UI táctil LVGL y hardware de potencia (arriba-izq), Webhook API / cliente web BLE (arriba-der) y consola de debug (abajo)._
> **Flujo de la Demostración Técnica:**
>
> - **Inicialización y Conectividad:** Secuencia de booteo con conexión Wi-Fi, sincronización de reloj en tiempo real (RTC) mediante protocolo **SNTP**, y transmisión inicial de telemetría global hacia la nube vía HTTP POST. Exploración de menú mostrando el escaneo asíncrono de redes Wi-Fi sin bloquear el renderizado gráfico.
> - **Validación BLE (Web Bluetooth):** Emparejamiento temporal bajo demanda. El dispositivo es detectado y validado de forma segura desde un cliente web externo a través de Bluetooth Low Energy.
> - **Seguridad y Motor de Reglas:** Autenticación local mediante contraseña de Superusuario (con manejo de intentos fallidos). El sistema evalúa estados concurrentes: al tener una "tarea" activa, el firmware bloquea los intentos estándar de apertura de hardware, requiriendo un escalamiento de privilegios (Superusuario) para forzar la acción.
> - **Control de Periféricos y Telemetría en Tiempo Real:** Gestión de relés físicos e indicadores LED (Rojo/Verde) para representar bloqueos y accesos. El firmware sigue una arquitectura orientada a eventos, donde cada cambio de estado físico dispara instantáneamente un Webhook (HTTP POST) para mantener sincronizada la base de datos externa.

**Arquitectura y Logros Técnicos:**

- **Desacoplamiento de Hilos y Concurrencia:** Implementación de una arquitectura orientada a eventos bajo **FreeRTOS**, aislando el hilo de renderizado de la interfaz gráfica (LVGL) de las tareas asíncronas de background (escaneo Wi-Fi, sincronización SNTP y peticiones HTTP), garantizando una navegación fluida a 60 FPS sin bloqueos (_blocking code_).
- **Máquina de Estados y Motor de Reglas Interno:** Diseño de una lógica de control basada en máquinas de estado concurrentes para la gestión de seguridad. El sistema evalúa en tiempo real las restricciones operativas (ej. bloquear accesos físicos si hay tareas críticas activas) y administra de forma segura el escalamiento jerárquico de privilegios (Superusuario).
- **Ecosistema de Telemetría No Bloqueante:** Integración de un cliente HTTP asíncrono que procesa y despacha cargas útiles (_payloads_ JSON) hacia la API externa inmediatamente después de cada cambio de estado en los periféricos de potencia, optimizando el consumo de ancho de banda y memoria RAM.
- **Canal de Comunicación Dual (Híbrido):** Configuración dinámica del controlador inalámbrico del ESP32 para alternar eficientemente entre el modo Estación (Wi-Fi) para persistencia de datos en la nube, y el periférico Bluetooth Low Energy (BLE) para la provisión y validación segura desde clientes web.
- _Nota: El código fuente y los diagramas esquemáticos detallados se omiten en este repositorio por ser propiedad intelectual privada y confidencial de la empresa._

---

## ⚡ 4. Sistema de Adquisición de Datos en Tiempo Real (End-to-End)

_Tecnologías: Next.js, React, Electron.js, C/C++, Interfaz Serial_

Desarrollo integral de un sistema que define el flujo de trabajo según normas de ensayo, el cual lee, procesa y genera informes de mediciones físicas en tiempo real, conectando hardware a medida con software de alto nivel.

> **Demostración del flujo de datos:**
>
> https://github.com/user-attachments/assets/65a54fdf-90c3-4da0-abf5-b1c1f1200f7c
>
> _👆 En pantalla: Layout completo del sistema (App de escritorio con Next.js a la izq., Consola a la der., Arduino abajo)._
>
> - **Hardware Awareness:** Detección en tiempo real de la conexión/desconexión de la placa física.
> - **Lógica Dinámica:** Ejecución de 3 ciclos de medición simulada. El árbol de decisión del flujo se adapta automáticamente según los parámetros de configuración iniciales.
> - **Manejo de Archivos:** Procesamiento de los datos adquiridos y renderizado final de un reporte técnico exportable en PDF.

**Arquitectura y Logros:**

- Creación de un puente de comunicación serial robusto entre el firmware del microcontrolador y el entorno Node.js/Electron.
- Implementación de arquitectura con inyección de datos simulados (Mocking) para permitir el desarrollo asíncrono y pruebas de estrés de la UI de Next.js independiente del hardware final.
- _Nota: Proyecto final de ingeniería electrónica en curso._

---

## 🏢 5. Arquitectura de Soluciones Corporativas Low-Code

_Tecnologías: Power Apps, SharePoint, Power Automate_

Digitalización y optimización de flujos de trabajo corporativos para la industria siderúrgica, reemplazando procesos manuales por aplicaciones interactivas.

> **Demostración del sistema (Gestión de Herramental):**
>
> https://github.com/user-attachments/assets/770dc185-0d1f-432b-946a-7efe2f8fdf05
>
> _👆 En pantalla: Recorrido integral (en velocidad 2x) por la arquitectura front-end del sistema._
>
> - **Estructuración de Datos:** Diseño de navegación modular que permite al usuario transicionar fluidamente entre su perfil y múltiples categorías de inventario complejo.
> - **Manejo de UI/UX Corporativo:** Implementación de vistas limpias para grandes volúmenes de información, priorizando la legibilidad.
> - **Lógica de Filtrado:** Uso de filtros dinámicos en tiempo real para optimizar la búsqueda y manipulación de datos provenientes de la base documental.

> **Demostración del sistema (Gestión de Inventario):**
>
> https://github.com/user-attachments/assets/0946468b-e0d4-498b-b362-3be363607da8
>
> _👆 En pantalla: Aplicación transaccional enfocada en la trazabilidad de inventario y control de activos físicos._
>
> - **Gestión de Accesos (RBAC):** Implementación de un sistema de roles y permisos para garantizar la seguridad y controlar quién puede visualizar o alterar información crítica.
> - **Métricas Financieras y de Stock:** Diseño de paneles interactivos con filtros avanzados para generar resúmenes dinámicos (agrupación por sector, ubicación y cálculo de costos totales en tiempo real).
> - **Lógica Transaccional (CRUD):** Flujo de registro de movimientos de stock, asegurando la trazabilidad absoluta y manteniendo un historial auditable de las operaciones.

**Arquitectura y Logros:**

- Diseño de aplicaciones de gestión interactivas conectadas a bases de datos en SharePoint.
- Aumento de la eficiencia operativa y reducción de tiempos de carga de datos en entornos industriales de alta demanda.
- _Nota: Desarrollo realizado bajo normas de confidencialidad corporativa._

---

📫 **¿Conectamos?** Encontrame en [linkedin.com/in/agustin-rivero-/](https://www.linkedin.com/in/agustin-rivero-/)
