





# ¡Hola! Soy Agustin 👋

Soy Desarrollador de Productos IoT y estudiante avanzado de Ingeniería Electrónica pronto a recibirme. Me especializo en conectar el mundo físico con el digital, dominando desde la programación a bajo nivel en microcontroladores hasta el desarrollo de interfaces gráficas, aplicaciones web y automatización de procesos corporativos.

🛠️ **Mi Stack Principal:** C/C++ | ESP-IDF | LVGL | Next.js | React | Power Platform

A continuación, presento algunos de los sistemas y arquitecturas en los que he trabajado:

---

## 📱 1. Desarrollo de GUI para Sistemas Embebidos Críticos
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
*Nota: El código fuente y los diagramas esquemáticos detallados se omiten en este repositorio por ser propiedad intelectual privada y confidencial de la empresa.*

---

## ⚡ 2. Sistema de Adquisición de Datos en Tiempo Real (End-to-End)
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

## 🏢 3. Arquitectura de Soluciones Corporativas Low-Code
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
