# Modelo de Dominio – Organización de Usuarios, Grupos y Tareas

Este documento explica de forma clara y ordenada cada clase del modelo, su papel dentro del sistema y el motivo de su colocación jerárquica. El objetivo del dominio es representar cómo **usuarios organizados en grupos gestionan tareas**, y cómo estas tareas se complementan con información de ubicación, horario, recordatorios, relaciones y posibles conflictos.

El diagrama se estructura en **niveles** porque cada elemento depende del anterior: primero las personas, luego los grupos, después las tareas y finalmente los detalles específicos de cada tarea.

---
## Nivel 1 — Tarea

### `Tarea`
Es el elemento central del sistema. Representa una acción que debe planificarse.

- Puede tener subtareas (relación *subtarea de*).
- Pertenece a un grupo y afecta a usuarios.
- Se relaciona con todos los elementos del nivel 4.
- Permite dependencias con otras tareas mediante `RelacionTareas`.

**Por qué está en el nivel 1:**  
Es el núcleo operativo del dominio: todo el sistema se organiza para gestionar y coordinar tareas.

---
## Nivel 2 — Usuario

### `Usuario`
Representa a la persona que interactúa con el sistema.

- Puede pertenecer a uno o varios grupos.  
- Es quien crea, modifica o recibe información sobre tareas.
- Recibe notificaciones cuando sus tareas presentan conflictos de horario.
- Funciona como la “entidad principal” que da sentido a los datos del sistema.

**Por qué está arriba:**  
La planificación del sistema nace en los usuarios. Todo lo demás se organiza alrededor de ellos.

---

## Nivel 3 — Grupo

### `Grupo`
Conjunto organizado de usuarios.

- Un usuario “participa en” uno o varios grupos.
- Un grupo “es gestionado” por uno o varios usuarios.
- Sirve para separar conjuntos de tareas: un usuario puede tener tareas distintas según el grupo.
- Facilita la coordinación (familia, piso compartido, equipo de estudio, proyecto, etc.).

**Por qué va debajo de Usuario:**  
Los grupos existen para agrupar usuarios; sin personas, no habría grupos.

---



