# 🧩 Reunión de Requisitos – Software de Gestión de Tareas Familiares

## Reuniones
#### 2ª Reunión:
*📅 Fecha:* 19 de noviembre  
*🕒 Hora:* 12:00 – 12:45 

---

## 📅 Contexto
Reunión con el cliente para la aclaración de dudas sobre el *software de gestión de problemas y tareas familiares*.  

---

## 🎯 Aclaración de dudas
En esta reunión se le plantearon a nuestro cliente las dudas que nos surgieron al realizar el modelo de dominio, ya que algunos aspectos no nos quedaron del todo claros.

### 1. Proponer/definir cuándo se considera conflicto horario
**¿Cuándo estamos hablando de que hay conflicto horario?**  
El cliente nos aclaró que, si dos tareas se superponen incluso en un 1%, ya se considera que existe un conflicto de horario. Una vez detectado este conflicto, se enviará una notificación a la persona para que modifique una de las dos tareas.

### 2. ¿Tienen inicio y final las tareas?
Para evitar conflictos horarios innecesarios y para que todo quede más claro, el usuario estará obligado a introducir una hora de inicio y otra de final al crear las tareas.

### 3. ¿Hay tareas que puede hacer cualquier miembro?
Sí. Esto se resolverá permitiendo seleccionar a todos los usuarios o creando un usuario que incluya a todos, para asignar una tarea que no vaya dirigida a alguien en específico.

### 4. ¿Hay alguna diferencia entre tarea y subtarea?
No, ya que las subtareas surgen simplemente de la posibilidad de recursividad infinita dentro de las tareas.
