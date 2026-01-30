# 🤖 AgendaBot Services

AgendaBot es un bot conversacional automatizado diseñado para ayudar usuarios a **agendar citas, gestionar tareas, hábitos, listas y recordatorios**, de forma sencilla, gratuita y sin depender de servicios pagos.

Este proyecto está pensado para funcionar con herramientas accesibles y sin requerir a plataformas premium.

---

## 📌 Objetivo del Proyecto

La organización **AgendaBot Services** requiere implementar un bot automatizado que permita:

- Agendar y administrar citas  
- Organizar tareas con estados  
- Automatizar recordatorios y hábitos  
- Gestionar listas personalizadas  
- Registrar logs y sesiones de usuario  

Todo esto bajo un enfoque conversacional simple basado en menús numéricos.

---

## ⚙️ Stack Tecnológico Implementado

El proyecto fue construido con:

| Herramienta | Rol |
|-----------|-----|
| 📲 Telegram | Interfaz conversacional |
| 🔁 n8n Community Edition | Automatización y lógica del bot |
| 📊 Google Sheets | Base de datos y almacenamiento |

---


## 🧠 Principios Conversacionales del Bot

AgendaBot sigue reglas estrictas para mantener claridad y control:

✅ El usuario siempre elige escribiendo un número  
✅ El bot siempre explica qué está haciendo  
✅ El bot muestra opciones numeradas  
✅ El bot recomienda una opción  
✅ El bot nunca asume intención  
✅ El bot siempre ofrece cancelar o volver  

---

## 🗂️ Modelo de Datos (Google Sheets)

El documento principal se llama:

📄 **AgendaBot_DB**

Debe contener las siguientes hojas:

### 📌 CITAS

- id_cita  
- fecha  
- hora  
- nombre  
- motivo  
- canal  
- estado  
- creado_por  
- timestamp_creacion  

---

### ✅ TAREAS

- id_tarea  
- titulo  
- prioridad  
- estado  
- fecha_objetivo  
- creado_por  

---

### 🔁 HABITOS

- id_habito  
- nombre  
- frecuencia  
- hora_recordatorio  
- estado  

---

### 📋 LISTAS

- id_lista  
- nombre_lista  
- tipo  
- creado_por  

---

### 🧾 ITEMS_LISTA

- id_item  
- id_lista  
- item  
- estado  

---

### 👤 USUARIOS

- telegram_user  
- nombre  
- rol  
- permitido  

---

### 🪵 LOGS

- timestamp  
- telegram_user  
- pantalla  
- opcion_elegida  
- resultado  

---

### 🔄 SESSIONS

- telegram_user  
- pantalla_actual  
- paso_actual  
- datos_parciales  
- timestamp_ultima_interaccion  

---

## 💬 Mensajería Humanizada

Cada mensaje del bot debe:

- Saludar de forma cercana  
- Explicar brevemente qué puede hacer  
- Mostrar opciones numeradas  
- Sugerir una opción recomendada  
- Indicar cómo continuar o cancelar  

---

## 👋 Mensaje de Bienvenida

Ejemplo oficial:

```
Hola, soy AgendaBot 👋

Estoy aquí para ayudarte a organizar tus citas, tareas y recordatorios
de forma sencilla y sin complicaciones.

Menú principal:
0. Ayuda
1. Agenda (citas)
2. Tareas
3. Recordatorios
4. Hábitos
5. Listas
6. Reportes
7. Configuración
8. Administrador

Tip rápido: escribe solo el número (por ejemplo: 1)
```

---

## 🚫 Opción Inválida (Global)

```
Ups, esa opción no existe en este menú.

Por favor escribe uno de los números que ves en pantalla.

Estás en: Menú principal
Opciones disponibles: 0 al 8
```

---

## 🧭 Navegación por Menús

### Menú Principal

```
0. Ayuda
1. Agenda (citas)
2. Tareas
3. Recordatorios
4. Hábitos
5. Listas
6. Reportes
7. Configuración
8. Administrador
```

Recomendación inicial:

> Si quieres empezar rápido, te recomiendo la opción 1 (Agenda).

---

## 📅 Menú Agenda

```
1. Agendar una nueva cita
2. Consultar tu agenda
3. Reprogramar una cita
4. Cancelar una cita
5. Marcar como completada
9. Volver al menú principal
```

---

## 🧩 Flujo Guiado: Agendar Nueva Cita

Wizard obligatorio de 6 pasos:

1. Fecha (YYYY-MM-DD)  
2. Hora (HH:MM)  
3. Nombre del cliente  
4. Motivo  
5. Canal (Presencial / Virtual / Llamada)  
6. Confirmación final  

---

### ✅ Confirmación Final

```
Fecha: 2025-12-20
Hora: 14:30
Cliente: Pedro Gómez
Motivo: Asesoría técnica
Canal: Virtual

1. Confirmar y guardar
2. Editar información
3. Cancelar
```

---

### 🎉 Mensaje de Éxito

```
¡Listo! Tu cita quedó agendada correctamente.

ID de la cita: CITA-014

1. Volver a Agenda
2. Ir al menú principal
```

---

## 🔁 Automatizaciones  en n8n

El sistema incluye:

- Router principal por pantalla + opción numérica  
- Flujo guiado completo de agendamiento  
- Flujo de tareas con estados  
- Resumen diario automático por Telegram  
- Registro automático en LOGS  
- Control de sesiones activas  

---

## ✅ Validaciones

AgendaBot valida:

- Opción válida según menú actual  
- Fecha y hora correctas  
- No permitir agendar en el pasado  
- Evitar doble reserva  
- Confirmación antes de guardar  
- Control de permisos por rol  

---

## 🧪 Pruebas Requeridas

| Tipo de prueba | Cantidad |
|--------------|----------|
| Navegación por menús | 30 |
| Agendamientos completos | 10 |
| Errores controlados | 10 |
| Recordatorios | 10 |
| Permisos por rol | 10 |

📌 Evidencia requerida:

- Logs en Google Sheets  
- Capturas de Telegram  
- Registro completo de sesiones  

---

## 🚀 Estado del Proyecto

📍 Completado.

---

## 👨‍💻 Autor

Valentina Delgado Rincon | https://github.com/ValentinaDelgadoRincon  
<<<<<<< Updated upstream
Michel Lorena Rodriguez  | https://github.com/michelrodriguez05  
=======

>>>>>>> Stashed changes
Proyecto desarrollado con enfoque en automatización accesible y gratuita.

