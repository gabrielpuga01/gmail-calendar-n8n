📬 Automatización de Correos y Calendario – Flujo n8n
Este flujo automatiza la gestión de correos electrónicos en Gmail: clasifica su contenido, responde con lenguaje natural y crea eventos en Google Calendar sin intervención manual.
✨ Funcionalidades
•	Clasificación automática de correos: Trabajo, Personal, Evento u Otros.
•	Generación de respuestas automáticas con IA (tono profesional-casual).
•	Extracción semántica de eventos (fecha, hora, lugar, descripción).
•	Creación validada de eventos en Google Calendar.
•	Soporte para horarios en diferentes formatos: "17:00", "5pm", "17:00 a 19:00", etc.
🧠 ¿Cómo funciona?
1.	Disparador: Se ejecuta cada minuto con el nodo Gmail Trigger.
2.	Clasificación: Se utiliza IA para categorizar el contenido del correo.
3.	Procesamiento con IA: Gemini o Mistral extraen datos relevantes y redactan respuestas.
4.	Validación:
o	Conversión de fechas/horas al formato RFC3339.
o	Interpretación flexible de frases como “en la tarde”.
5.	Resultados:
o	Respuesta automática al remitente.
o	Evento creado en Google Calendar (si los datos son válidos).
🛠 Requisitos
•	Plataforma n8n (local o vía Docker)
•	Cuenta Gmail y Google Calendar
•	Credenciales/API Keys para:
o	Google OAuth2
o	Gemini (PaLM API)
o	Mistral Cloud (Pixtral o Codestral)
🚀 Instalación
1.	Importa el flujo desde JSON en n8n.
2.	Configura las credenciales necesarias.
3.	Crea etiquetas en Gmail: Trabajo, Personal, Evento, Otros.
4.	Activa el flujo desde el editor.
> ℹ️ Zona horaria predeterminada: UTC−5. Puedes ajustar esto en el nodo de código.
🧪 Pruebas
El archivo /tests/parseTime.js puede ser probado con Jest:
bash
npx jest
Incluye pruebas para:
•	Formatos de hora (24h, 12h, rangos)
•	Fechas en español o ISO
•	Casos límite (datos incompletos, nulos o ambiguos)
🧩 Tecnologías utilizadas
•	n8n para la lógica de automatización
•	APIs de Google (Gmail & Calendar)
•	Modelos de lenguaje: Gemini, Mistral
•	JavaScript para el parseo y validación de datos

