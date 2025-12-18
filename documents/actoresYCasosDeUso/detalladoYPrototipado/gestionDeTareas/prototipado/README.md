# Prototipos de Interfaz: Gestión de Tareas

## 1. Pantalla Principal: Lista de Tareas (`abrirTareas`)

Esta pantalla cubre la funcionalidad de ver el listado y contiene los botones de acción para **eliminarTarea** (papelera), **editarTarea** (lápiz), **relacionarTareas** (clip/enlace) y **marcarCompletada** (check).

### Explicación de los iconos de acción:

* **Lápiz** (`<&pencil>`): Lleva al caso de uso `editarTarea`.
* **Papelera** (`<&trash>`): Ejecuta `eliminarTarea`.
* **Clip/Enlace** (`<&link-intact>`): Abre la ventana de `relacionarTareas`.
* **Check** (`<&check>`): Ejecuta `marcarCompletada`.

| Diagrama | Código Fuente |
|----------|---------------|
| ![Prototipado Abrir Tareas](\documents\actoresYCasosDeUso\detalladoYPrototipado\gestionDeTareas\prototipado\abrirTareas\abrirTareasPrototipado.svg)| [Ver código](/documents/actoresYCasosDeUso/detalladoYPrototipado/gestionDeTareas/prototipado/abrirTareas/abrirTareaPrototipado.puml) |

## 2. Pantalla de Formulario (`crearTarea` y `editarTarea`)

Esta sería la pantalla que se abre al pulsar el botón "Crear Nueva Tarea" o el icono de "Editar" (lápiz).

| Diagrama | Código Fuente |
|----------|---------------|
| ![Prototipado Crear y Editar Tarea](\documents\actoresYCasosDeUso\detalladoYPrototipado\gestionDeTareas\prototipado\crearYEditarTarea\crearYEditarTareaPrototipado.svg)| [Ver código](\documents\actoresYCasosDeUso\detalladoYPrototipado\gestionDeTareas\prototipado\crearYEditarTarea\crearYEditarTareaPrototipado.puml) |

## 3. Pantalla de Vinculación (`relacionarTareas`)

Esta es la interfaz específica para cuando el usuario quiere relacionar una tarea con otra (al pulsar el icono del clip <&link-intact>).

| Diagrama | Código Fuente |
|----------|---------------|
| ![Prototipado Relacionar Tareas](\documents\actoresYCasosDeUso\detalladoYPrototipado\gestionDeTareas\prototipado\relacionarTareas\relacionarTareasPrototipado.svg)| [Ver código](\documents\actoresYCasosDeUso\detalladoYPrototipado\gestionDeTareas\prototipado\relacionarTareas\relacionarTareasPrototipado.puml) |
