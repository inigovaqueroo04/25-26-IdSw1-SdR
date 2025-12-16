# Gestor de tareas familiares

[![Inicio](https://img.shields.io/badge/Inicio-FFFFFF?style=for-the-badge&logo=homeassistant&logoColor=black)](../../README.md)
[![Modelo de Dominio](https://img.shields.io/badge/Modelo%20de%20Dominio-FFFFFF?style=for-the-badge&logo=bookstack&logoColor=black)](../modelosUML/modeloDeDominio/README.md)
[![Actores Y CasosDeUso](https://img.shields.io/badge/Actores%20&%20Casos%20De%20Uso-FFFFFF?style=for-the-badge&logo=people&logoColor=black)](./README.md)
[![Diagramas de Contexto](https://img.shields.io/badge/Diagramas%20de%20Contexto-FFFFFF?style=for-the-badge&logo=bookstack&logoColor=black)](./diagramaContexto/README.md)
[![Detallar & Prototipar](https://img.shields.io/badge/Detallar%20&%20Prototipar-FFFFFF?style=for-the-badge&logo=figma&logoColor=black)](./detalladoYPrototipado/README.md)


Este documento recoge los actores principales del sistema y los casos de uso organizados de forma jerárquica. La idea es mostrar de manera sencilla cómo interactúan las personas con la aplicación y qué funcionalidades se ofrecen.

# [Diagramas](./diagramas/README.md)

## Actores

### Administrador del grupo

Persona que gestiona el grupo familiar y controla toda la configuración. Puede crear y modificar miembros, tareas y reglas.

### Miembro

Personas del grupo que consultan y realizan las tareas asignadas, marcan actividades completadas y visualizan la información general.

### Tiempo

Responsable de validar información y aplicar acciones internas como controles, recordatorios o actualizaciones automáticas.

## Casos de uso

### [Gestión de sesión y navegación](./detalladoYPrototipado/gestionDeSesionYNavegacion/README.md)

1. [iniciarSesion()](./detalladoYPrototipado/gestionDeSesionYNavegacion/iniciarSesion/iniciarSesion.md)
2. [cerrarSesion()](./detalladoYPrototipado/gestionDeSesionYNavegacion/cerrarSesion/cerrarSesion.md)
3. [completarGestion()](./detalladoYPrototipado/gestionDeSesionYNavegacion/completarGestion/completarGestion.md)

### [Gestión de grupos y usuarios](./detalladoYPrototipado/gestionDeGruposYUsuarios/README.md)

1. [abrirGrupos()](./detalladoYPrototipado/gestionDeGruposYUsuarios/abrirGrupos/abrirGrupos.md)
2. [crearGrupo()](./detalladoYPrototipado/gestionDeGruposYUsuarios/crearGrupo/crearGrupo.md)
3. [editarGrupo()](./detalladoYPrototipado/gestionDeGruposYUsuarios/editarGrupo/editarGrupo.md)
4. [eliminarGrupo()](./detalladoYPrototipado/gestionDeGruposYUsuarios/eliminarGrupo/eliminarGrupo.md)
5. [unirseAGrupo()](./detalladoYPrototipado/gestionDeGruposYUsuarios/unirseAGrupo/unirseAGrupo.md)
6. [invitarUsuario()](./detalladoYPrototipado/gestionDeGruposYUsuarios/invitarUsuario/invitarUsuario.md)


### [Gestión de tareas](./detalladoYPrototipado/gestionDeTareas/README.md)

1. [abrirTareas()](./detalladoYPrototipado/gestionDeTareas/abrirTareas/abrirTareas.md)
2. [crearTarea()](./detalladoYPrototipado/gestionDeTareas/crearTarea/crearTarea.md)
3. [editarTarea()](./detalladoYPrototipado/gestionDeTareas/editarTarea/editarTarea.md)
4. [relacionarTareas()](./detalladoYPrototipado/gestionDeTareas/relacionarTareas/relacionarTareas.md)
5. [eliminarTarea()](./detalladoYPrototipado/gestionDeTareas/eliminarTarea/eliminarTarea.md)
6. [marcarCompletada()](./detalladoYPrototipado/gestionDeTareas/marcarCompletada/marcarCompletada.md)

### [Planificación y configuración](./detalladoYPrototipado/planificacionYConfiguracion/README.md)

1. [abrirPlanificacion()](./detalladoYPrototipado/planificacionYConfiguracion/abrirPlanificacion/abrirPlanificacion.md)
2. [establecerHorario()](./detalladoYPrototipado/planificacionYConfiguracion/establecerHorario/establecerHorario.md)
3. [definirLocalizacion()](./detalladoYPrototipado/planificacionYConfiguracion/definirLocalizacion/definirLocalizacion.md)
4. [configurarRecordatorio()](./detalladoYPrototipado/planificacionYConfiguracion/configurarRecordatorio/configurarRecordatorio.md)
5. [asignarTareaAUsuario()](./detalladoYPrototipado/gestionDeGruposYUsuarios/asignarTareaAUsuario/asignarTareaAUsuario.md)

### [Automatización (Actor Tiempo)](./detalladoYPrototipado/automatizacionActorTiempo/README.md)

1. [iniciarAutomatizacion()](./detalladoYPrototipado/automatizacionActorTiempo/iniciarAutomatizacion/iniciarAutomatizacion.md)
2. [detectarConflicto()](./detalladoYPrototipado/automatizacionActorTiempo/detectarConflictoHorario/detectarConflicto.md)
3. [resolverConflicto()](./detalladoYPrototipado/automatizacionActorTiempo/resolverConflicto/resolverConflicto.md)
4. [ignorarConflicto()](./detalladoYPrototipado/automatizacionActorTiempo/ignorarConflicto/ignorarConflicto.md)
5. [volverAInicio()](./detalladoYPrototipado/gestionDeSesionYNavegacion/volverAInicio/volverAInicio.md)