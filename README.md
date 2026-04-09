# ¡Hola! Soy Agustin 👋

Soy Desarrollador de Productos IoT y estudiante avanzado de Ingeniería Electrónica pronto a recibirme. Me especializo en conectar el mundo físico con el digital, dominando desde la programación a bajo nivel en microcontroladores hasta el desarrollo de interfaces gráficas, aplicaciones web y automatización de procesos corporativos.

🛠️ **Mi Stack Principal:** C/C++ | ESP-IDF | LVGL | Next.js | React | Power Platform

A continuación, presento algunos de los sistemas y arquitecturas en los que he trabajado:

---

## 📱 1. Desarrollo de GUI para Sistemas Embebidos Críticos
*Tecnologías: C/C++, ESP-IDF, LVGL, SquareLine Studio, FreeRTOS*

Diseño e integración de interfaces gráficas nativas para microcontroladores (familia ESP32) en entornos industriales.

> **Demostración de Interfaz y Conectividad IoT (ESP32-P4 con pantalla táctil):**

https://github.com/user-attachments/assets/73d16119-5ce9-4c0a-a165-f54a0c9f41f1

> *👆 En pantalla: UI táctil LVGL (arriba-izq), Consola de debug (abajo) y cliente Web Bluetooth (arriba-der).*
> * **Gestión de Memoria y Red:** Secuencia de booteo con recuperación de variables de entorno (NVS) y conexión Wi-Fi automática con escaneo de redes asíncrono sin bloquear la interfaz gráfica.
> * **Conectividad BLE (Web Bluetooth):** Habilitación del periférico Bluetooth Low Energy bajo demanda para establecer un canal de validación bidireccional con un cliente web externo.
> * **Seguridad y Control de Estados:** Autenticación local en el dispositivo (Superusuario) para la gestión de permisos, y accionamiento seguro de bloqueos físicos del sistema.

**Arquitectura y Logros:**
* Implementación de una arquitectura orientada a eventos para renderizar componentes visuales dinámicos (ej. notificaciones asíncronas).
* Gestión eficiente de la memoria y los recursos del hardware mediante FreeRTOS, garantizando fluidez en la interfaz sin interrumpir procesos críticos de background.
* *Nota: El código fuente es propiedad intelectual privada de la empresa.*

---

## ⚡ 2. Sistema de Adquisición de Datos en Tiempo Real (End-to-End)
*Tecnologías: Next.js, Electron.js, C/C++, Interfaz Serial*

Desarrollo integral de un sistema que define el flujo de trabajo según normas de ensayo, el cual lee, procesa y genera informes de mediciones físicas en tiempo real, conectando hardware a medida con software de alto nivel. 

> **Demostración del flujo de datos:**

https://github.com/user-attachments/assets/6464c240-882c-43ea-876d-9d2d3b87a54d

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

https://github.com/user-attachments/assets/885ce026-786b-4f30-be76-d8af930617bd

> *👆 En pantalla: Recorrido integral (en velocidad 2x) por la arquitectura front-end del sistema.*
> * **Estructuración de Datos:** Diseño de navegación modular que permite al usuario transicionar fluidamente entre su perfil y múltiples categorías de inventario complejo.
> * **Manejo de UI/UX Corporativo:** Implementación de vistas limpias para grandes volúmenes de información, priorizando la legibilidad.
> * **Lógica de Filtrado:** Uso de filtros dinámicos en tiempo real para optimizar la búsqueda y manipulación de datos provenientes de la base documental.

> **Demostración del sistema (Gestión de Inventario):**

https://github.com/user-attachments/assets/3bf55eeb-3ebf-47e0-8daf-1c5f8260c7cf

> *👆 En pantalla: Aplicación transaccional enfocada en la trazabilidad de inventario y control de activos físicos.*
> * **Gestión de Accesos:** Implementación de un sistema de roles y permisos para garantizar la seguridad y controlar quién puede visualizar o alterar información crítica.
> * **Métricas Financieras y de Stock:** Diseño de paneles interactivos con filtros avanzados para generar resúmenes dinámicos (agrupación por sector, ubicación y cálculo de costos totales en tiempo real).
> * **Lógica Transaccional:** Flujo de registro de movimientos de stock, asegurando la trazabilidad absoluta y manteniendo un historial auditable de las operaciones.

**Arquitectura y Logros:**
* Diseño de aplicaciones de gestión interactivas conectadas a bases de datos en SharePoint.
* Aumento de la eficiencia operativa y reducción de tiempos de carga de datos en entornos industriales de alta demanda.
* *Nota: Desarrollo realizado bajo normas de confidencialidad corporativa.*

---

📫 **¿Conectamos?** Encontrame en [https://www.linkedin.com/in/agustin-rivero-/]
