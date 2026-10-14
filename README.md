\# Agente de IA para Finanzas Personales con n8n



\## 1. Descripción del proyecto



Este proyecto consiste en un asistente de inteligencia artificial para finanzas personales, conectado a Telegram mediante n8n, Google Gemini y Google Sheets.



El agente permite registrar gastos e ingresos, consultar movimientos, calcular totales por categoría y obtener el saldo neto de los movimientos registrados.



\## 2. Objetivo



Desarrollar un agente de IA capaz de interpretar solicitudes en lenguaje natural, utilizar herramientas externas para consultar y registrar información financiera y mantener el contexto de una conversación.



\## 3. Tecnologías utilizadas



\- \*\*n8n:\*\* automatización del flujo de trabajo.

\- \*\*Telegram:\*\* interfaz de comunicación con el usuario.

\- \*\*Google Gemini:\*\* modelo de inteligencia artificial.

\- \*\*Google Sheets:\*\* almacenamiento de gastos e ingresos.

\- \*\*Simple Memory:\*\* memoria conversacional.

\- \*\*Calculator:\*\* herramienta para operaciones aritméticas.



\## 4. Funcionalidades



\- Registrar gastos.

\- Registrar ingresos.

\- Consultar gastos por categoría.

\- Consultar totales generales.

\- Consultar ingresos registrados.

\- Calcular el saldo neto.

\- Interpretar fechas indicadas por el usuario.

\- Evitar registros duplicados cuando se detectan situaciones ambiguas.

\- Mantener el contexto de la conversación.

\- Rechazar solicitudes ajenas a las finanzas personales.



\## 5. Flujo de trabajo



1\. El usuario envía un mensaje mediante Telegram.

2\. El nodo Telegram Trigger recibe el mensaje.

3\. El AI Agent interpreta la solicitud.

4\. Google Gemini procesa el mensaje.

5\. Simple Memory conserva el contexto conversacional.

6\. Google Sheets consulta o registra movimientos según corresponda.

7\. Calculator realiza operaciones aritméticas.

8\. El agente genera una respuesta.

9\. Telegram envía la respuesta al usuario.



\## 6. Estructura del repositorio



\- `Workflow/`: plantilla del flujo de n8n.

\- `Documentacion/`: documentación del proyecto.

\- `Evidencias/Casos\_de\_prueba/`: capturas de las pruebas realizadas.

\- `Evidencias/Google\_Sheets/`: evidencias de los registros almacenados.

\- `.gitignore`: archivos que deben excluirse del repositorio.



\## 7. Seguridad



Las credenciales de Telegram, Google Gemini y Google Sheets se configuran directamente en n8n. No deben publicarse contraseñas, tokens ni claves de API.



El archivo JSON público es una plantilla y requiere configurar las credenciales y seleccionar la hoja de cálculo antes de ejecutarse.



\## 8. Pruebas



El proyecto contempla diez casos de prueba documentados. Las capturas y los resultados se encuentran en la carpeta `Evidencias/`.



Los resultados finales deben corresponder a las pruebas realmente ejecutadas.



\## 9. Instalación y configuración



1\. Instalar o acceder a una instancia de n8n.

2\. Importar la plantilla JSON de la carpeta `Workflow/`.

3\. Configurar las credenciales de Telegram, Google Gemini y Google Sheets.

4\. Seleccionar la hoja de cálculo y verificar los encabezados.

5\. Configurar el acceso del bot de Telegram.

6\. Ejecutar los casos de prueba.

7\. Activar el workflow cuando se haya verificado su funcionamiento.



\## 10. Proyecto académico



Proyecto del primer parcial: Agente de IA con n8n.



Escenario: Finanzas personales mediante Telegram.
