





# ¡Hola! Soy Agustin 👋

Soy Desarrollador de Productos IoT y estudiante avanzado de Ingeniería Electrónica pronto a recibirme. Me especializo en conectar el mundo físico con el digital, dominando desde la programación a bajo nivel en microcontroladores hasta el desarrollo de interfaces gráficas, aplicaciones web y automatización de procesos corporativos.

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
*Pipeline de telemetría Cloud Native End-to-End (ESP32 ➔ AWS Serverless ➔ Node.js ➔ Docker ➔ Grafana)*

Mientras que el resto de los proyectos en este portfolio son desarrollos de código cerrado o bajo acuerdos de confidencialidad, este repositorio público funciona como mi **prueba de código**. Demuestra mi capacidad técnica para construir **infraestructuras escalables en la nube**, aplicar buenas prácticas de **ciberseguridad (rotación de credenciales y roles IAM)**, **orquestar microservicios** e **integrar hardware (Edge) con la nube**.

[![Ver Código](https://img.shields.io/badge/🚀_Ver_Código_Fuente_y_Documentación_➔-2ea44f?style=for-the-badge)](https://github.com/Rivero-Agustin/enterprise-iot-telemetry-pipeline)

![Demo IoT](https://github.com/Rivero-Agustin/enterprise-iot-telemetry-pipeline/blob/main/docs/demo.dashboard.grafana.gif)

**Stack Tecnológico:** `ESP32 / FreeRTOS` | `AWS (IoT Core, SQS, IAM)` | `Node.js` | `MongoDB` | `Docker` | `Grafana`

---

## 🐧 2. Proyecto Open-Source: Custom Embedded Linux Edge Gateway
*Tecnologías: Buildroot, QEMU, C/C++, Python, WSL2, Redes TCP/IP*

Diseño y compilación de un sistema operativo Linux personalizado para actuar como nodo Edge. El sistema procesa telemetría física de sensores UWB (Ultra-Wideband) y gestiona de forma segura el puente hacia AWS IoT Core.

[![Ver Código](https://img.shields.io/badge/🚀_Ver_Código_Fuente_y_Documentación_➔-0078D4?style=for-the-badge)](https://github.com/Rivero-Agustin/embedded-linux-iot-gateway)

> **Diagrama de Arquitectura y Redes:**
>
> ![Diagrama de Arquitectura](https://github.com/Rivero-Agustin/embedded-linux-iot-gateway/blob/main/docs/architecture.diagram.png)
> 
> *👆 Arquitectura del sistema: Flujo de telemetría desde el hardware físico, atravesando túneles de red (portproxy) en Windows/WSL2, hasta el entorno Linux emulado y AWS.*

**Arquitectura y Logros Técnicos:**
* **Embedded Linux (Buildroot):** Construcción desde cero de un sistema de archivos raíz (`rootfs`) mínimo y compilación cruzada para arquitectura ARM (Cortex-A53).
* **Networking Avanzado:** Resolución de arquitecturas "doble NAT" configurando reglas de Firewall, túneles *portproxy* y *host forwarding* en QEMU para exponer el puerto TCP local hacia el hardware físico.
* **Edge Computing (Python):** Implementación de lógica local para el procesamiento de datos en tiempo real, evaluando anomalías y riesgos de colisión antes de despachar eventos críticos a la nube, reduciendo la latencia y el consumo de ancho de banda.
* **Seguridad Híbrida:** Configuración del Gateway como barrera de seguridad, recibiendo telemetría local en texto plano (optimizando la carga computacional del nodo ESP32) y encapsulando la salida hacia AWS IoT Core mediante MQTTS (TLS 1.2).

---

## 📱 3. Desarrollo de GUI para Sistemas Embebidos Críticos
*Tecnologías: C/C++, ESP-IDF, LVGL, SquareLine Studio, FreeRTOS*

Diseño e integración de interfaces gráficas nativas para microcontroladores (familia ESP32) en entornos industriales.

> **Demostración de Interfaz, Control de Hardware y Conectividad IoT (ESP32-P4 con pantalla táctil):**
>
> https://github.com/user-attachments/assets/e358323d-e6ba-4f4c-9428-898d0fdcbe95
> 
> *👆 En pantalla: UI táctil LVGL y hardware de potencia (arriba-izq), Webhook API / cliente web BLE (arriba-der) y consola de debug (abajo).*
> **Flujo de la Demostración Técnica:**
> * **Inicialización y Conectividad:** Secuencia de booteo con conexión Wi-Fi, sincronización de reloj en tiempo real (RTC) mediante protocolo **SNTP**, y transmisión inicial de telemetría global hacia la nube vía HTTP POST. Exploración de menú mostrando el escaneo asíncrono de redes Wi-Fi sin bloquear el renderizado gráfico.
> * **Validación BLE (Web Bluetooth):** Emparejamiento temporal bajo demanda. El dispositivo es detectado y validado de forma segura desde un cliente web externo a través de Bluetooth Low Energy.
> * **Seguridad y Motor de Reglas:** Autenticación local mediante contraseña de Superusuario (con manejo de intentos fallidos). El sistema evalúa estados concurrentes: al tener una "tarea" activa, el firmware bloquea los intentos estándar de apertura de hardware, requiriendo un escalamiento de privilegios (Superusuario) para forzar la acción.
> * **Control de Periféricos y Telemetría en Tiempo Real:** Gestión de relés físicos e indicadores LED (Rojo/Verde) para representar bloqueos y accesos. El firmware sigue una arquitectura orientada a eventos, donde cada cambio de estado físico dispara instantáneamente un Webhook (HTTP POST) para mantener sincronizada la base de datos externa.

**Arquitectura y Logros Técnicos:**
* **Desacoplamiento de Hilos y Concurrencia:** Implementación de una arquitectura orientada a eventos bajo **FreeRTOS**, aislando el hilo de renderizado de la interfaz gráfica (LVGL) de las tareas asíncronas de background (escaneo Wi-Fi, sincronización SNTP y peticiones HTTP), garantizando una navegación fluida a 60 FPS sin bloqueos (*blocking code*).
* **Máquina de Estados y Motor de Reglas Interno:** Diseño de una lógica de control basada en máquinas de estado concurrentes para la gestión de seguridad. El sistema evalúa en tiempo real las restricciones operativas (ej. bloquear accesos físicos si hay tareas críticas activas) y administra de forma segura el escalamiento jerárquico de privilegios (Superusuario).
* **Ecosistema de Telemetría No Bloqueante:** Integración de un cliente HTTP asíncrono que procesa y despacha cargas útiles (*payloads* JSON) hacia la API externa inmediatamente después de cada cambio de estado en los periféricos de potencia, optimizando el consumo de ancho de banda y memoria RAM.
* **Canal de Comunicación Dual (Híbrido):** Configuración dinámica del controlador inalámbrico del ESP32 para alternar eficientemente entre el modo Estación (Wi-Fi) para persistencia de datos en la nube, y el periférico Bluetooth Low Energy (BLE) para la provisión y validación segura desde clientes web.
* *Nota: El código fuente y los diagramas esquemáticos detallados se omiten en este repositorio por ser propiedad intelectual privada y confidencial de la empresa.*

---

## ⚡ 4. Sistema de Adquisición de Datos en Tiempo Real (End-to-End)
*Tecnologías: Next.js, React, Electron.js, C/C++, Interfaz Serial*

Desarrollo integral de un sistema que define el flujo de trabajo según normas de ensayo, el cual lee, procesa y genera informes de mediciones físicas en tiempo real, conectando hardware a medida con software de alto nivel.

> **Demostración del flujo de datos:**
> 
> https://github.com/user-attachments/assets/65a54fdf-90c3-4da0-abf5-b1c1f1200f7c
> 
> *👆 En pantalla: Layout completo del sistema (App de escritorio con Next.js a la izq., Consola a la der., Arduino abajo).*
> * **Hardware Awareness:** Detección en tiempo real de la conexión/desconexión de la placa física.
> * **Lógica Dinámica:** Ejecución de 3 ciclos de medición simulada. El árbol de decisión del flujo se adapta automáticamente según los parámetros de configuración iniciales.
> * **Manejo de Archivos:** Procesamiento de los datos adquiridos y renderizado final de un reporte técnico exportable en PDF.

**Arquitectura y Logros:**
* Creación de un puente de comunicación serial robusto entre el firmware del microcontrolador y el entorno Node.js/Electron.
* Implementación de arquitectura con inyección de datos simulados (Mocking) para permitir el desarrollo asíncrono y pruebas de estrés de la UI de Next.js independiente del hardware final.
* *Nota: Proyecto final de ingeniería electrónica en curso.*

---

## 🏢 5. Arquitectura de Soluciones Corporativas Low-Code
*Tecnologías: Power Apps, SharePoint, Power Automate*

Digitalización y optimización de flujos de trabajo corporativos para la industria siderúrgica, reemplazando procesos manuales por aplicaciones interactivas.

> **Demostración del sistema (Gestión de Herramental):**
> 
> https://github.com/user-attachments/assets/770dc185-0d1f-432b-946a-7efe2f8fdf05
> 
> *👆 En pantalla: Recorrido integral (en velocidad 2x) por la arquitectura front-end del sistema.*
> * **Estructuración de Datos:** Diseño de navegación modular que permite al usuario transicionar fluidamente entre su perfil y múltiples categorías de inventario complejo.
> * **Manejo de UI/UX Corporativo:** Implementación de vistas limpias para grandes volúmenes de información, priorizando la legibilidad.
> * **Lógica de Filtrado:** Uso de filtros dinámicos en tiempo real para optimizar la búsqueda y manipulación de datos provenientes de la base documental.

> **Demostración del sistema (Gestión de Inventario):**
> 
> https://github.com/user-attachments/assets/0946468b-e0d4-498b-b362-3be363607da8
> 
> *👆 En pantalla: Aplicación transaccional enfocada en la trazabilidad de inventario y control de activos físicos.*
> * **Gestión de Accesos (RBAC):** Implementación de un sistema de roles y permisos para garantizar la seguridad y controlar quién puede visualizar o alterar información crítica.
> * **Métricas Financieras y de Stock:** Diseño de paneles interactivos con filtros avanzados para generar resúmenes dinámicos (agrupación por sector, ubicación y cálculo de costos totales en tiempo real).
> * **Lógica Transaccional (CRUD):** Flujo de registro de movimientos de stock, asegurando la trazabilidad absoluta y manteniendo un historial auditable de las operaciones.

**Arquitectura y Logros:**
* Diseño de aplicaciones de gestión interactivas conectadas a bases de datos en SharePoint.
* Aumento de la eficiencia operativa y reducción de tiempos de carga de datos en entornos industriales de alta demanda.
* *Nota: Desarrollo realizado bajo normas de confidencialidad corporativa.*

---

📫 **¿Conectamos?** Encontrame en [linkedin.com/in/agustin-rivero-/](https://www.linkedin.com/in/agustin-rivero-/)
