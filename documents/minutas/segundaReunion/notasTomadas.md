# 📘 Documento de Ideas / Requerimientos — Proyecto de Gestión de Tareas

Este documento recoge los **retoques y clarificaciones recomendados por Breñosa**, así como observaciones funcionales relacionadas con el manejo de tareas, subtareas, estados y conflictos.

---

## ✅ Refinamientos Recomendados

### 🔧 1. Refinar hora de inicio y hora de fin
- Ajustar y validar de forma más precisa los campos de **hora de inicio** y **hora de fin**.
- Garantizar que la hora de inicio sea siempre anterior a la hora de fin.
- Estos campos son obligatorios a la hora de crear una tarea.

---

### 🗂️ 2. Eliminar “conflicto horario”
El concepto **“conflicto horario” no debe ser considerado un atributo de la tarea**.

Nuevo enfoque:
- El **conflicto pertenece al usuario**, no a la tarea.
- Una tarea puede estar **finalizada y aun así existir un conflicto** para la persona.
- El conflicto **no debe paralizar** ni bloquear el avance de tareas.
- El conflicto es independiente del ciclo de vida de la tarea.

---

### 🏷️ 3. Estados de las tareas
Las tareas deben incluir un sistema de estados claro. Ejemplos:

- Creada 
- Programada
- En ejecución
- Finalizada
- Cancelada


---

## 📌 4. Subtareas

- Una tarea puede definirse como **subtarea** de otra.
- Si se elimina una **tarea padre**, deben eliminarse **todas sus subtareas** (eliminación en cascada).
- Entre **tareas hermanas**, eliminar una **no afecta** a las demás.

---

## ⚠️ 5. Concepto de conflicto (definición final)

El conflicto debe tratarse como un módulo independiente:

- **No forma parte de la tarea.**
- **Pertenece al usuario** y a su planificación personal.
- Las tareas **no se detienen** ni cambian su lógica por la existencia de conflictos.
- Un usuario puede tener conflicto incluso si todas sus tareas están finalizadas.
- El conflicto es un componente paralelo al sistema de tareas.

Ejemplo conceptual:
> Un usuario puede tener conflictos detectados en su agenda personal, pero sus tareas pueden seguir avanzando en su ciclo de vida normal.

---

