# Resumen de la reunión con el cliente
**Proyecto:** Software de gestión de tareas familiares

## 1. Objetivo general
- Desarrollar un sistema para la organización, asignación y seguimiento de tareas dentro de grupos (familia, trabajo, etc.).
- Permitir la creación de tareas y subtareas con niveles infinitos (recursividad).
- Facilitar la colaboración entre diferentes agentes con horarios y ubicaciones distintas.

## 2. Gestión de agentes y grupos
- Los agentes representan a los usuarios (por ejemplo, miembros de una familia).
- Cada agente puede tener tareas asignadas individualmente o compartidas.
- Se pueden crear grupos independientes (familia, trabajo, etc.) para evitar conflictos.
- El sistema debe detectar y evitar solapamientos de horarios entre tareas de distintos grupos.

## 3. Gestión de tareas y subtareas
- Una tarea puede ser realizada por un agente concreto, varios agentes o cualquiera del grupo.
- Las tareas pueden contener subtareas infinitas (estructura recursiva).
- Las tareas pueden relacionarse con otras por localización, agente o identificador común.
- Ejemplo:  
  - Agente1 - comprar - lista de la compra (compuesta por varios elementos).  
  - Agente2 - recoger - paquete (Amazon Locker [localización]).

## 4. Localización y optimización
- Las tareas incluyen ubicación y horario (rígido o flexible).
- El sistema debe ordenar las tareas según la proximidad geográfica y la disponibilidad horaria.
- Se plantea la conexión con el navegador o servicios de mapas para calcular la ruta más óptima.

## 5. Recordatorios y seguimiento
- Cada usuario puede configurar recordatorios personalizados antes de cada tarea.
- El sistema debe permitir confirmar la realización de la tarea.
- En caso de no realizarse, el sistema debe preguntar si se desea reprogramarla para otro día.

## 6. Interfaz y roles
- **Vista de administrador:**
  - Crear, asignar y editar tareas.
  - Gestionar grupos y resolver conflictos de horarios.
- **Vista de usuario:**
  - Visualizar solo las tareas asignadas.
  - Marcar tareas como realizadas o reprogramadas.

## 7. Relación entre tareas
- Las tareas pueden estar relacionadas por:
  - Localización común.
  - Agente común.
  - Identificador o localizador compartido.

## 8. Edición y flexibilidad
- Las tareas deben poder editarse en cualquier momento (nombre, agente, prioridad, jerarquía, etc.).
- Se permite reestructurar subtareas dentro de otras.

## 9. Ejemplos prácticos
- “Comprar lista de la compra” → tarea con subtareas por producto.
- “Recoger paquete en Amazon Locker” → tarea con ubicación específica.
- “Reunión de trabajo” y “llevar al hijo al colegio” → el sistema detecta conflicto y propone reprogramar.

## 10. Aspectos pendientes para próximas reuniones
- Definir niveles de permisos por usuario.
- Evaluar integración con calendarios externos (Google, Outlook).
- Analizar posible sincronización con asistentes de voz o aplicaciones móviles.
