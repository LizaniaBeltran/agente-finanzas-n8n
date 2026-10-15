# Reflexión del agente de finanzas personales

## 1. ¿Qué casos fallaron y por qué? ¿Qué cambiamos para corregirlos?

Durante las primeras pruebas del agente de finanzas personales se identificaron algunas inconsistencias en las consultas de gastos, el registro de movimientos y el manejo de solicitudes fuera del ámbito financiero. A partir de estos resultados, se revisaron las instrucciones del agente y la configuración de las herramientas conectadas a n8n, Google Sheets y Calculadora.

**Caso 4: Consulta del total gastado en comida**

Inicialmente, el agente respondió cantidades diferentes, $730 y $745, al preguntarle cuánto se había gastado en comida. Esto evidenció una inconsistencia en los resultados de las consultas. Para mejorar su funcionamiento, se revisó la recuperación de los movimientos desde Google Sheets y el uso de la herramienta Calculadora. Después de realizar los ajustes y repetir las pruebas, se buscó asegurar que los resultados coincidieran con los registros almacenados.

**Caso 5: Posible registro duplicado de un gasto**

Al registrar un gasto de $230 en comida china, el agente presentó respuestas contradictorias y un error técnico. Esto mostró la importancia de comprobar que una operación se complete correctamente antes de confirmar al usuario que el movimiento fue guardado. Se revisó el comportamiento del agente al registrar movimientos y al recibir solicitudes repetidas, con el propósito de mejorar la confirmación de las operaciones y reducir el riesgo de duplicados.

**Caso 6: Consulta de gastos por categoría**

En las primeras pruebas, el agente presentó los totales de distintas categorías, pero era necesario comprobar que se consideraran todos los movimientos existentes. Para mejorar este comportamiento, se revisó la consulta de Google Sheets y el procesamiento de los datos antes de calcular los totales. El objetivo fue evitar omisiones y lograr que los resultados fueran coherentes con los registros almacenados.

**Caso 10: Solicitud fuera del ámbito financiero**

Inicialmente, el agente respondía algunas solicitudes que no estaban relacionadas con las finanzas personales. Para corregir este comportamiento, se modificaron las instrucciones del prompt del sistema, estableciendo límites más claros sobre las funciones que puede realizar. Después de los ajustes, el agente comenzó a rechazar amablemente las solicitudes ajenas a las finanzas personales y a redirigir al usuario hacia sus funciones disponibles.

En general, las pruebas permitieron identificar áreas de mejora y realizar ajustes en el funcionamiento del agente. Las pruebas posteriores sirvieron para revisar los cambios y comprobar que los comportamientos corregidos respondieran a lo esperado.

## 2. Una limitación del agente que no pudimos resolver

Durante el desarrollo se identificó que el agente depende de la calidad y disponibilidad de los datos almacenados en Google Sheets, así como de la correcta configuración de las herramientas conectadas. Aunque se realizaron ajustes para mejorar los cálculos, las consultas y el registro de movimientos, el sistema todavía podría presentar dificultades ante errores de conexión, datos incompletos o solicitudes ambiguas.

Esta limitación muestra que un agente de inteligencia artificial no garantiza por sí solo resultados correctos en todas las situaciones. Por ello, sería conveniente incorporar mecanismos adicionales de validación, manejo de errores y supervisión para aumentar su confiabilidad.

## 3. ¿Qué cambiaríamos si este agente fuera de producción con usuarios reales?

Si el agente se utilizara con usuarios reales, implementaríamos las siguientes mejoras:

- **Validación de datos:** comprobar que cada movimiento tenga un monto válido, una categoría reconocida, una fecha correcta y una descripción adecuada.
- **Prevención de duplicados:** implementar un identificador único para cada movimiento y mecanismos que permitan detectar registros repetidos antes de guardarlos.
- **Precisión en los cálculos:** verificar que las consultas recuperen todos los movimientos correspondientes y que los totales coincidan con los datos almacenados.
- **Manejo de errores:** evitar que el agente confirme un registro cuando Google Sheets no haya guardado la información correctamente.
- **Privacidad y seguridad:** separar la información de cada usuario para impedir que una persona consulte los movimientos financieros de otra, además de proteger las credenciales de acceso.
- **Pruebas adicionales:** evaluar mensajes incompletos, fechas ambiguas, cantidades incorrectas, ingresos, gastos repetidos y consultas de diferentes periodos.
- **Control del alcance:** mantener instrucciones claras para que el agente atienda solicitudes de finanzas personales y rechace amablemente las que no correspondan a sus funciones.
- **Monitoreo y mantenimiento:** registrar los errores técnicos, revisar los resultados y actualizar el flujo de trabajo cuando sea necesario.

Estas mejoras ayudarían a que el agente fuera más confiable, seguro y adecuado para su uso cotidiano.

## 4. ¿Qué hizo cada integrante del equipo?

El proyecto se organizó mediante la división de responsabilidades para desarrollar el agente, almacenar los movimientos financieros y comprobar su funcionamiento.

### Integrante responsable de Arquitectura + n8n

- Diseñó y configuró el flujo principal del agente en n8n.
- Configuró el Telegram Trigger y la comunicación con el usuario.
- Preparó el AI Agent y sus instrucciones para atender solicitudes relacionadas con las finanzas personales.
- Configuró la memoria de conversación y las herramientas utilizadas por el agente.
- Integró las operaciones necesarias para registrar y consultar movimientos financieros.
- Revisó y ajustó el comportamiento del agente a partir de los resultados obtenidos durante las pruebas.

### Integrante responsable de Datos + Calidad

- Creó y trabajó la hoja de Google Sheets `Finanzas_Agente_Equipo5`.
- Preparó las columnas `usuario`, `monto`, `categoria`, `fecha` y `descripcion`.
- Configuró y revisó la estructura de los datos utilizados por el agente.
- Ejecutó pruebas para verificar el registro de gastos e ingresos y la consulta de movimientos.
- Comparó las respuestas del agente con los registros almacenados en Google Sheets.
- Documentó los resultados de las pruebas e identificó los casos que necesitaban ajustes o una nueva validación.

La distribución anterior debe corresponder a las actividades que realmente realizó cada integrante.

## Conclusión

El desarrollo del agente de finanzas personales permitió integrar n8n, Telegram, Google Sheets, memoria de conversación y herramientas para realizar cálculos. Las pruebas iniciales ayudaron a identificar inconsistencias en las consultas, dificultades en el registro de movimientos y la necesidad de establecer límites claros para las solicitudes fuera del ámbito financiero.

A partir de estos resultados, se realizaron ajustes en las instrucciones y en el funcionamiento del flujo. Este proceso permitió comprender la importancia de probar un agente de inteligencia artificial, revisar los resultados obtenidos y corregir los problemas detectados antes de considerar su uso con usuarios reales.

Finalmente, el proyecto permitió aplicar conocimientos de automatización, integración de herramientas, almacenamiento de datos, diseño de instrucciones para inteligencia artificial y control de calidad.
