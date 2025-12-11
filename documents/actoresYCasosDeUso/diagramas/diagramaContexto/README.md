# Sistema de Gestión de Tareas > Diagramas de Contexto por Actor


## Introducción

Este documento presenta los diagramas de contexto del sistema descompuestos por los actores principales. Esta aproximación modular mejora la comprensión de los flujos de trabajo específicos: la complejidad de la gestión y configuración (Administrador), la sencillez de la operación diaria (Miembro) y los procesos automáticos (Tiempo).

---

## Propósito

- Mostrar la perspectiva específica de cada actor dentro del sistema.
- Especificar la secuencialidad de navegación mediante estados y transiciones.
- Definir las precondiciones de navegación de forma visual para cada contexto.
- Facilitar la comprensión de la separación de responsabilidades entre los actores.

---

# Diagramas por Actor

## 1. Administrador (Gestión y Configuración)

Este diagrama modela el flujo de trabajo del usuario con privilegios de gestión. Incluye la creación, edición, eliminación y configuración de tareas, grupos y planificación.

<div align="center">

|![Diagrama de Contexto - Gestor de Tareas](diagramaContextoAdmin.png)
|-
|**Código fuente:** [diagramaContextoAdmin](diagramaContextoAdmin.puml)

</div>

---

## 2. Miembro (Usuario Operacional)

Este diagrama representa el flujo de trabajo esencial para un usuario estándar, centrándose en el acceso a la gestión y consulta de tareas.

<div align="center">

|![Diagrama de Contexto - Gestor de Tareas](diagramaContextoMiembro.png)
|-
|**Código fuente:** [diagramaContextoMiembro](diagramaContextoMiembro.puml)

</div>

---

## 3. Tiempo (Automatización)

Este diagrama ilustra los flujos que se activan automáticamente por el sistema, como la detección y resolución de conflictos de horario.

<div align="center">

|![Diagrama de Contexto - Gestor de Tareas](diagramaContextoTiempo.png)
|-
|**Código fuente:** [diagramaContextoTiempo](diagramaContextoTiempo.puml)

</div>

---

# Estados Consolidados del Sistema

| Estado | Descripción | Actores Relevantes | Función principal |
|--------|-------------|---------------------|--------------------|
| **SESION_CERRADA** | Estado inicial del sistema | Administrador, Miembro, Tiempo | Punto de entrada, requiere autenticación |
| **SISTEMA_DISPONIBLE** | Hub central de navegación | Administrador, Miembro, Tiempo | Punto de acceso a los módulos |
| **GESTION_TAREAS_ABIERTO** | Módulo principal de gestión | Administrador, Miembro | Gestión general de tareas |
| **CREACION_TAREA_ABIERTO** | Creación de una tarea | Administrador | Recolección de datos mínimos |
| **PLANIFICACION_ABIERTO** | Módulo de detalles y horarios | Administrador | Configuración de horarios y recordatorios |
| **ORGANIZACION_GRUPOS_ABIERTO** | Gestión de grupos | Administrador | Creación, unión y visualización |
| **GRUPO_ABIERTO** | Grupo específico | Administrador | Gestión de miembros y tareas |
| **AUTOMATIZACION_ACTIVA** | Monitoreo automático | Tiempo, Administrador | Ejecución automática |
| **CONFLICTO_ABIERTO** | Resolución de conflictos | Tiempo | Manejo de conflictos |
| **CONSULTA_TAREAS_ABIERTO** | Consulta específica | Administrador | Visualización de tareas |

---

# Transiciones por Actor

## 1. Administrador (Gestión)

| Transición | Origen → Destino | Descripción |
|-----------|------------------|-------------|
| `iniciarSesion()` | SESION_CERRADA → SISTEMA_DISPONIBLE | Acceso al sistema |
| `cerrarSesion()` | SISTEMA_DISPONIBLE → SESION_CERRADA | Cierre de sesión |
| `abrirTareas()` | SISTEMA_DISPONIBLE → GESTION_TAREAS_ABIERTO | Acceso a la lista |
| `abrirPlanificacion()` | SISTEMA_DISPONIBLE → PLANIFICACION_ABIERTO | Configuración de horarios |
| `abrirGrupos()` | SISTEMA_DISPONIBLE → ORGANIZACION_GRUPOS_ABIERTO | Gestión de grupos |
| `crearTarea()` | GESTION_TAREAS_ABIERTO → CREACION_TAREA_ABIERTO | Inicia creación |
| `editarTarea()` | GESTION_TAREAS_ABIERTO / GRUPO_ABIERTO → CREACION_TAREA_ABIERTO | Edita tarea |
| `guardarTarea()` | CREACION_TAREA_ABIERTO → GESTION_TAREAS_ABIERTO | Guarda tarea |
| `establecerHorario()` / `vincularTareas()` | PLANIFICACION_ABIERTO → PLANIFICACION_ABIERTO | Acción autorreflexiva |
| `crearGrupo()` / `editarGrupo()` | ORGANIZACION_GRUPOS_ABIERTO / GRUPO_ABIERTO → GRUPO_ABIERTO | Gestión de grupos |
| `asignarTareaAUsuario()` / `invitarUsuario()` | GRUPO_ABIERTO → GRUPO_ABIERTO | Gestión de miembros |
| `visualizarTareasGrupo()` | GRUPO_ABIERTO → CONSULTA_TAREAS_ABIERTO | Consulta de tareas dentro de cada grupo |
| `completarGestion()` / `volverAInicio()` | Cualquier Estado Secundario → SISTEMA_DISPONIBLE | Retorno al menú |

---

## 2. Miembro (Operacional)

| Transición | Origen → Destino | Descripción |
|-----------|------------------|-------------|
| `iniciarSesion()` | SESION_CERRADA → SISTEMA_DISPONIBLE | Acceso |
| `cerrarSesion()` | SISTEMA_DISPONIBLE → SESION_CERRADA | Cierre |
| `abrirTareas()` | SISTEMA_DISPONIBLE → GESTION_TAREAS_ABIERTO | Acceso a tareas |
| `marcarCompletada()` | GESTION_TAREAS_ABIERTO → GESTION_TAREAS_ABIERTO | Marca la tarea completada |
| `completarGestion()` | GESTION_TAREAS_ABIERTO / CONSULTA_TAREAS_CONCEPTUAL_ABIERTO → SISTEMA_DISPONIBLE | Regreso |

---

## 3. Actor Tiempo (Automatización)

| Transición | Origen → Destino | Descripción |
|-----------|------------------|-------------|
| `iniciarAutomatizacion()` | SISTEMA_DISPONIBLE → AUTOMATIZACION_ACTIVA | Comienza monitoreo |
| `detectarConflicto()` | AUTOMATIZACION_ACTIVA → CONFLICTO_ABIERTO | Detecta conflicto |
| `resolverConflicto()` | CONFLICTO_ABIERTO → AUTOMATIZACION_ACTIVA | Resuelve conflicto |
| `ignorarConflicto()` | CONFLICTO_ABIERTO → AUTOMATIZACION_ACTIVA | Ignora conflicto |
| `volverAInicio()` | AUTOMATIZACION_ACTIVA → SISTEMA_DISPONIBLE | Detiene automatización |

---

# Precondiciones visuales

## Autenticación requerida
El diagrama hace explícito que para acceder a **SISTEMA_DISPONIBLE**, el usuario debe completar `iniciarSesion()` desde el estado **SESION_CERRADA**.

## Navegación centralizada desde menú
El acceso a los módulos principales requiere pasar por **SISTEMA_DISPONIBLE**.

---

# Flujos de trabajo

## Flujo de Administrador
Requiere transitar por estados específicos como **CREACION_TAREA_ABIERTO** u **ORGANIZACION_GRUPOS_ABIERTO** para cualquier operación de configuración o modificación de estructura.

## Flujo de Miembro
Las operaciones están restringidas a:
- La lectura (**GESTION_TAREAS_ABIERTO**)
- Acciones autorreflexivas sobre tareas asignadas (`marcarCompletada()`)

## Flujo de Tiempo
- La activación (`iniciarAutomatizacion()`) debe ocurrir en **SISTEMA_DISPONIBLE**
- La gestión de excepciones solo es posible en **CONFLICTO_ABIERTO**

---

# Validación de Flujos

## Separación de Contexto

- El flujo de **Administrador** es expansivo e incluye todas las transiciones de configuración, creación y gestión de infraestructura.
- El flujo de **Miembro** es minimalista, enfocado solo en consumir y modificar el estado de sus tareas.    
- El flujo de **Tiempo** está aislado a las transiciones de monitoreo y manejo de excepciones (conflictos de planificación).

## Cobertura de casos de uso

- **Gestión de Tareas (Administrador):** creación, modificación, eliminación y asignación a miembros y grupos.    
- **Grupos (Administrador):** creación, unión, gestión de miembros y consulta de tareas por grupo.  
- **Planificación (Administrador):** definición de detalles espaciales y temporales de la tarea.
- **Operación de Tareas (Administrador/Miembro):** visualización y marcado de completado de sus tareas asignadas.  
- **Automatización (Tiempo):** detección, resolución e ignorancia de conflictos de horario.

---

# Optimización del flujo

## Patrón radial
Mantiene **SISTEMA_DISPONIBLE** como el hub central, facilitando una navegación intuitiva para todos los actores.

## Operaciones in situ
Las operaciones de modificación simple (ej. `marcarCompletada()`) son autorreflexivas, minimizando cambios de estado y mejorando la eficiencia.

---

# Características del diseño

## Patrón Hub Central
**SISTEMA_DISPONIBLE** actúa como punto central, concentrando el inicio de todos los flujos principales para los tres actores.

## Granularidad Descriptiva
Los estados son lo suficientemente específicos (ej. **CREACION_TAREA_ABIERTO** vs. **GESTION_TAREAS_ABIERTO**) para distinguir las fases de interacción de cada actor.

## Separación de Responsabilidades
- **Flujo de Tareas:** segmentado entre funciones de Administrador (creación/configuración) y Miembro (ejecución/consumo).  
- **Control de Acceso:** la dependencia estricta de `iniciarSesion()` asegura el control de acceso en la transición **SESION_CERRADA → SISTEMA_DISPONIBLE**.  
- **Retorno Consistente:** el uso de `completarGestion()` o `volverAInicio()` garantiza una navegación predecible hacia el menú principal.
