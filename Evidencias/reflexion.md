Reflexión del agente de finanzas personales

1. ¿Qué casos fallaron y por qué? ¿Qué cambiamos para corregirlos?

Durante las pruebas del agente de finanzas personales se identificaron algunas inconsistencias en las consultas y en el registro de movimientos.

Caso 4: Consulta del total gastado en comida.

El agente respondió cantidades diferentes, $730 y $745, al preguntarle cuánto se había gastado en comida. Esto indica que el resultado no fue consistente con los registros consultados en Google Sheets. Una posible causa es que no se estuvieran considerando correctamente todos los movimientos o que existieran diferencias en los datos utilizados para calcular el total.
Para corregir este problema, es necesario revisar los registros de Google Sheets, comprobar que la herramienta de consulta obtenga los movimientos correctos y verificar que la herramienta Calculator realice la suma con los datos recibidos. La respuesta final debe coincidir con los registros reales.

Caso 5: Posible registro duplicado de un gasto.
Al registrar un gasto de $230 en comida china, el agente presentó respuestas contradictorias y un error técnico. Posteriormente confirmó el registro y se verificó el movimiento en Google Sheets.
Este caso mostró la necesidad de comprobar que el registro se complete correctamente antes de confirmar al usuario que el movimiento fue guardado. También se debe revisar si el mismo gasto ya existe para evitar duplicados cuando se repita una solicitud.
Como mejora, se debe validar la información antes de guardarla y comprobar el resultado de la operación de Google Sheets. La prevención de duplicados debe verificarse mediante pruebas adicionales.

Caso 6: Consulta de gastos por categoría.
El agente presentó los siguientes resultados: Comida $745, Accesorios $34, Transporte $18 y Escuela $40. Sin embargo, el caso quedó pendiente porque todavía se necesita comprobar que los totales incluyan todos los movimientos existentes y que no haya omisiones ni duplicados.
Para corregirlo, se deben comparar los resultados con la hoja de cálculo y revisar que la consulta recupere todos los registros necesarios antes de calcular los totales.

Caso 10: Solicitud fuera del ámbito financiero.
Este caso quedó pendiente porque no se confirmó el comportamiento del agente ante una solicitud para escribir una tarea completa sobre la Revolución Mexicana.
Se debe probar que el agente rechace amablemente solicitudes que no estén relacionadas con las finanzas personales y redirija al usuario hacia sus funciones disponibles.
En conclusión, las pruebas permitieron identificar la necesidad de mejorar la consistencia de los cálculos, la validación de los registros y el manejo de solicitudes fuera del alcance del agente.

2. Una limitación del agente que no pudimos resolver

Una limitación identificada es que el agente puede presentar cantidades inconsistentes cuando consulta los gastos por categoría. Aunque utiliza Google Sheets para obtener los movimientos y Calculator para realizar las operaciones, las respuestas no siempre coinciden entre consultas.
Esta limitación demuestra que utilizar herramientas no garantiza por sí solo que los resultados sean correctos. Es necesario validar los datos obtenidos, comprobar los cálculos y asegurar que se consideren todos los registros.
Además, el sistema todavía necesita comprobar de manera confiable si un movimiento ya fue registrado para reducir el riesgo de duplicados.

3. ¿Qué cambiaríamos si este agente fuera a producción con usuarios reales?

Si el agente se utilizara con usuarios reales, implementaríamos las siguientes mejoras:

- Validación de datos: comprobar que cada movimiento tenga un monto válido, una categoría reconocida, una fecha correcta y una descripción cuando sea necesaria.
- Prevención de duplicados: implementar un identificador único para cada movimiento y un mecanismo que permita detectar registros repetidos.
- Mayor precisión en los cálculos: validar que las consultas recuperen todos los movimientos y que los totales coincidan con los datos almacenados.
- Manejo de errores: evitar que el agente confirme un registro cuando Google Sheets no haya guardado la información correctamente.
- Privacidad y seguridad separar la información de cada usuario para impedir que una persona consulte los movimientos de otra.
- Pruebas adicionales: probar mensajes incompletos, fechas ambiguas, cantidades incorrectas, ingresos, gastos repetidos y consultas de diferentes periodos.
- Mejor control del alcance: establecer instrucciones claras para que el agente atienda solicitudes financieras personales y redirija las que no correspondan a sus funciones.
- Monitoreo y mantenimiento: registrar los errores técnicos, revisar los resultados y actualizar el flujo de trabajo cuando sea necesario.

Estas mejoras ayudarían a que el agente fuera más confiable, seguro y adecuado para su uso cotidiano.

4. ¿Qué hizo cada integrante del equipo?

El proyecto se organizó por responsabilidades para desarrollar el agente, almacenar los movimientos financieros y comprobar su funcionamiento.

Integrante responsable de Arquitectura + n8n

- Diseñó y configuró el flujo principal del agente en n8n.
- Configuró el Telegram Trigger y la comunicación con el usuario.
- Preparó el AI Agent y sus instrucciones para atender solicitudes relacionadas con las finanzas personales.
- Configuró la memoria de conversación y las herramientas utilizadas por el agente.
- Integró las operaciones necesarias para registrar y consultar movimientos financieros.

Integrante responsable de Datos + Calidad

- Creó y organizó la hoja de Google Sheets `Finanzas_Agente_Equipo5`.
- Preparó las columnas `usuario`, `monto`, `categoria`, `fecha` y `descripcion`.
- Configuró y revisó la estructura de los datos utilizados por el agente.
- Ejecutó pruebas para verificar el registro de gastos e ingresos y la consulta de movimientos.
- Comparó las respuestas del agente con los registros de Google Sheets.
- Documentó los resultados de las pruebas e identificó los casos inconsistentes o pendientes de validar.

Conclusión

La realización de estas pruebas nos permitió comprobar que el agente puede registrar ingresos y gastos, recordar información de la conversación y responder preguntas relacionadas con las finanzas personales.
Sin embargo, también identificamos aspectos que deben mejorarse principalmente la consistencia de los cálculos, la prevención de registros duplicados y la validación de las respuestas. Las pruebas fueron importantes para detectar estos problemas antes de considerar el uso del agente con usuarios reales.
