# Gestor de tareas familiares
[![Inicio](https://img.shields.io/badge/Inicio-FFFFFF?style=for-the-badge&logo=homeassistant&logoColor=black)](../../README.md)
[![Modelo de Dominio](https://img.shields.io/badge/Modelo%20de%20Dominio-FFFFFF?style=for-the-badge&logo=bookstack&logoColor=black)](../modelosUML/modeloDeDominio/README.md)
[![Actores Y CasosDeUso](https://img.shields.io/badge/Actores%20&%20Casos%20De%20Uso-FFFFFF?style=for-the-badge&logo=people&logoColor=black)](./README.md)
[![Detallar & Prototipar](https://img.shields.io/badge/Detallar%20&%20Prototipar-FFFFFF?style=for-the-badge&logo=figma&logoColor=black)]()

Este documento recoge los actores principales del sistema y los casos de uso organizados de forma jerárquica. La idea es mostrar de manera sencilla cómo interactúan las personas con la aplicación y qué funcionalidades se ofrecen.

[Diagramas](./diagramas/README.md)

## Actores

### Administrador del grupo
Persona que gestiona el grupo familiar y controla toda la configuración. Puede crear y modificar miembros, tareas y reglas.

### Miembro
Personas del grupo que consultan y realizan las tareas asignadas, marcan actividades completadas y visualizan la información general.

### Tiempo
Responsable de validar información y aplicar acciones internas como controles, recordatorios o actualizaciones automáticas.

## Casos de uso

### Gestión de miembros
1. Alta de miembro  
2. Modificar datos de miembro  
3. Eliminar miembro  
4. Consultar listado de miembros  

### Gestión de grupos
1. Crear grupo  
2. Modificar grupo  
3. Eliminar grupo  
4. Añadir miembro a grupo  
5. Quitar miembro de grupo  

### Gestión de tareas
1. Crear tarea  
2. Modificar tarea  
3. Eliminar tarea  
4. Consultar tareas  
5. Asignar tarea a miembro  
6. Marcar tarea como completada  
7. Crear subtarea  

### Gestión de permisos
1. Añadir permiso  
2. Modificar permiso  
3. Eliminar permiso  
4. Consultar permiso  

### Visualización e informes
1. Ver calendario de tareas  
2. Ver carga de trabajo por miembro  
3. Ver historial de tareas
