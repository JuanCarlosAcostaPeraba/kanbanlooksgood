# Kanban Looks Good

Plugin para GLPI que añade visualización de **Prioridad** y **Duración Planificada** en las tarjetas del Kanban de Proyectos.

## Características

- ✅ Muestra el badge de prioridad con su color configurado en GLPI
- ✅ Muestra la duración planificada formateada (igual que en el formulario de proyecto)
- ✅ Aplica color de fondo suavizado a las tarjetas según la prioridad
- ✅ Compatible con Proyectos y Tareas (ProjectTask)
- ✅ No modifica el código core de GLPI

## Requisitos

- GLPI 10.0.0 o superior
- PHP 7.4 o superior

## Instalación

1. Copia la carpeta `kanbanlooksgood` a `plugins/` de tu instalación de GLPI
2. Ve a **Configuración > Plugins**
3. Busca "Kanban Looks Good" y actívalo

## Funcionalidad

### Prioridad

- Se muestra el badge de prioridad con el mismo formato que en el resto de GLPI
- El color de la prioridad se aplica al header de la tarjeta
- El fondo de la tarjeta se suaviza con el color de prioridad para mejor legibilidad

### Duración Planificada

- Para **Proyectos**: Muestra la suma de duraciones planificadas de todas sus tareas
- Para **Tareas**: Muestra la duración planificada de la tarea
- El formato es el mismo que se usa en los formularios de GLPI

## Desarrollo

### Estructura del Plugin

```
kanbanlooksgood/
├── setup.php          # Registro del plugin y hooks
├── inc/
│   └── hook.php       # Hook para añadir metadata
├── js/
│   └── kanban.js      # JavaScript para renderizado frontend
├── css/
│   └── kanban.css     # Estilos CSS
└── README.md          # Este archivo
```

### Hooks Utilizados

- `KANBAN_ITEM_METADATA`: Añade prioridad y duración a la metadata de las tarjetas

### Eventos JavaScript

El plugin intercepta los siguientes eventos del Kanban:
- `kanban:post_build`: Después de construir el Kanban
- `kanban:refresh`: Al refrescar el Kanban
- `kanban:card_move`: Al mover una tarjeta
- `kanban:card_add`: Al añadir una tarjeta

## Licencia

GPLv2+
