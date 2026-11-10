# Gestor de estudiantes — Aplicación web con Vue 3

Aplicación web desarrollada con **HTML, CSS, JavaScript y Vue 3** para gestionar el registro y seguimiento de estudiantes. El proyecto permite registrar estudiantes, consultar sus datos, modificar sus calificaciones, aplicar filtros y visualizar estadísticas generales del grupo.

La aplicación utiliza la API de opciones de Vue (Options API), organizando la información reactiva mediante `data`, las propiedades computadas mediante `computed` y las operaciones mediante `methods`.

## Tabla de contenido

- [Descripción del proyecto](#descripción-del-proyecto)
- [Tecnologías utilizadas](#tecnologías-utilizadas)
- [Funcionalidades](#funcionalidades)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Requisitos previos](#requisitos-previos)
- [Instalación y configuración](#instalación-y-configuración)
- [Ejecución de la aplicación](#ejecución-de-la-aplicación)
- [Validaciones y reglas de negocio](#validaciones-y-reglas-de-negocio)
- [Propiedades computadas](#propiedades-computadas)
- [Métodos principales](#métodos-principales)
- [Interfaz de usuario](#interfaz-de-usuario)
- [Colaboradores](#colaboradores)
- [Licencia](#licencia)

## Descripción del proyecto

El Gestor de estudiantes es una aplicación web que permite administrar información académica de estudiantes de diferentes carreras. Su objetivo es facilitar el registro, la consulta y el seguimiento de las calificaciones mediante una interfaz sencilla e interactiva.

La aplicación utiliza Vue 3 para gestionar los datos de manera reactiva, permitiendo que los cambios realizados en los estudiantes se reflejen automáticamente en la interfaz.

La información se almacena temporalmente en memoria mediante las propiedades reactivas de Vue. Por esta razón, los registros no se conservan cuando se recarga la página.

## Tecnologías utilizadas

- **HTML5:** estructura y organización del contenido de la aplicación.
- **CSS3:** diseño visual y estilos de los elementos de la interfaz.
- **JavaScript:** implementación de la lógica y las operaciones del sistema.
- **Vue 3:** framework de JavaScript utilizado para gestionar los datos reactivos y actualizar la interfaz.
- **Vue Options API:** organización de la aplicación mediante `data`, `computed` y `methods`.
- **Visual Studio Code:** editor de código utilizado durante el desarrollo.
- **Git y GitHub:** herramientas para el control de versiones y almacenamiento del proyecto.

## Funcionalidades

### Registro de estudiantes

- Registrar estudiantes mediante un formulario.
- Asignar un identificador único a cada estudiante.
- Seleccionar una carrera.
- Registrar una calificación entre 0 y 10.
- Limpiar los campos del formulario después de un registro exitoso.

### Validación de datos

- Comprobar que el nombre sea obligatorio.
- Verificar que el nombre tenga al menos tres caracteres.
- Comprobar que se seleccione una carrera válida.
- Validar que la calificación sea numérica.
- Verificar que la calificación esté entre 0 y 10.
- Evitar el registro de estudiantes duplicados en una misma carrera.
- Controlar el cupo máximo de estudiantes.

### Gestión de estudiantes

- Consultar la lista de estudiantes registrados.
- Visualizar el identificador, nombre, carrera y calificación.
- Aumentar la calificación de un estudiante.
- Disminuir la calificación de un estudiante.
- Eliminar estudiantes individualmente.
- Eliminar todos los estudiantes registrados.

### Búsqueda y filtros

- Buscar estudiantes por nombre.
- Filtrar estudiantes por carrera.
- Consultar todos los estudiantes.
- Filtrar estudiantes aprobados.
- Filtrar estudiantes reprobados.
- Mostrar un mensaje cuando no existan estudiantes que coincidan con los filtros.

### Estadísticas del grupo

- Mostrar el total de estudiantes registrados.
- Calcular el promedio general de las calificaciones.
- Mostrar el total de estudiantes aprobados.
- Mostrar el total de estudiantes reprobados.
- Identificar al estudiante con la calificación más alta.
- Cambiar el color del promedio según el resultado obtenido.

## Estructura del proyecto

La estructura principal del proyecto es la siguiente:

```text
gestor-estudiantes-vue/
│
├── index.html
├── app.js
├── styles.css
└── README.md
```

### Responsabilidad de cada archivo

| Archivo | Descripción |
|---|---|
| `index.html` | Contiene la estructura HTML y las directivas de Vue utilizadas en la interfaz. |
| `app.js` | Contiene la lógica de la aplicación, los datos reactivos, las propiedades computadas y los métodos. |
| `styles.css` | Contiene los estilos visuales de la aplicación. |
| `README.md` | Contiene la documentación general del proyecto. |

## Requisitos previos

Antes de ejecutar el proyecto, se recomienda contar con:

- Un navegador web actualizado, como Google Chrome, Microsoft Edge u Opera.
- Visual Studio Code u otro editor de código.
- Git, si se desea clonar el repositorio.
- Conexión a Internet para cargar Vue 3 desde su CDN.

## Instalación y configuración

### 1. Clonar el repositorio

```bash
git clone https://github.com/Dlaiton738/gestor-estudiantes-vue.git
```

### 2. Ingresar al directorio

```bash
cd gestor-estudiantes-vue
```

### 3. Abrir el proyecto

Abre la carpeta del proyecto desde Visual Studio Code.

También puedes abrir directamente el archivo `index.html` desde el navegador.

## Ejecución de la aplicación

La aplicación utiliza Vue 3 mediante CDN, por lo que no necesita un proceso de compilación ni instalación de dependencias.

En el archivo `index.html` se incluye la siguiente referencia:

```html
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
```

Para ejecutar el proyecto:

1. Abre la carpeta del proyecto en Visual Studio Code.
2. Ubica el archivo `index.html`.
3. Abre el archivo utilizando un navegador web.
4. También puedes utilizar la extensión Live Server para iniciar un servidor local de desarrollo.

Una vez abierta la aplicación, podrás registrar estudiantes y utilizar las diferentes funcionalidades disponibles.

## Validaciones y reglas de negocio

El sistema implementa diferentes validaciones para garantizar que la información registrada sea correcta.

| Campo o regla | Condición |
|---|---|
| Nombre | Es obligatorio y debe tener mínimo tres caracteres. |
| Carrera | Es obligatorio y debe pertenecer a las opciones disponibles. |
| Calificación | Debe ser un valor numérico entre 0 y 10. |
| Estudiantes duplicados | No se permite registrar el mismo nombre en una misma carrera. |
| Cupo máximo | Se permite registrar hasta 10 estudiantes. |
| Aumento de calificación | No puede superar el valor de 10. |
| Disminución de calificación | No puede ser inferior a 0. |

Para identificar el estado académico de los estudiantes se utilizan las siguientes condiciones:

- **Aprobado:** calificación igual o superior a 6.
- **Reprobado:** calificación inferior a 6.

## Propiedades computadas

El proyecto utiliza `computed` de Vue 3 para obtener información calculada a partir de los datos reactivos. Estas propiedades actualizan automáticamente sus resultados cuando cambian los datos de los estudiantes o los filtros.

Las propiedades computadas implementadas son:

| Propiedad | Descripción |
|---|---|
| `estudiantesFiltrados` | Obtiene los estudiantes que coinciden con los filtros de carrera, nombre y estado académico. |
| `totalestudiantes` | Calcula la cantidad total de estudiantes registrados. |
| `promedionotas` | Calcula el promedio general de las calificaciones. |
| `colorpromedio` | Determina el color del promedio según el resultado obtenido. |
| `totalaprobados` | Cuenta los estudiantes que tienen una calificación igual o superior a 6. |
| `totalreprobados` | Cuenta los estudiantes que tienen una calificación inferior a 6. |
| `mejorEstudiante` | Identifica al estudiante que tiene la calificación más alta. |

## Métodos principales

La aplicación utiliza métodos para ejecutar las operaciones y las validaciones necesarias.

| Método | Descripción |
|---|---|
| `errorNombre()` | Valida el nombre ingresado. |
| `errorCarrera()` | Valida la carrera seleccionada. |
| `errorCalificacion()` | Comprueba que la calificación cumpla las condiciones establecidas. |
| `agregarEstudiante()` | Registra un nuevo estudiante después de comprobar las validaciones. |
| `esDuplicado()` | Comprueba si ya existe un estudiante con el mismo nombre y carrera. |
| `lugaresDisponibles(carrera)` | Calcula los cupos disponibles para una carrera. |
| `colorNota(nota)` | Determina el color correspondiente a una calificación. |
| `aumentarCalificacion(est)` | Incrementa la calificación de un estudiante. |
| `disminuirCalificacion(est)` | Disminuye la calificación de un estudiante. |
| `eliminarEstudiante(id)` | Elimina un estudiante mediante su identificador. |
| `borrarTodo()` | Elimina todos los estudiantes registrados. |

## Interfaz de usuario

La interfaz permite interactuar con las funcionalidades del sistema mediante un formulario de registro, controles de búsqueda, filtros y una lista de estudiantes.

Entre sus elementos principales se encuentran:

- Formulario para registrar estudiantes.
- Mensajes de validación y errores.
- Selector de carreras.
- Campo de búsqueda por nombre.
- Botones para filtrar por estado académico.
- Lista de estudiantes registrados.
- Controles para modificar las calificaciones.
- Estadísticas generales del grupo.
- Botones para eliminar registros.

## Colaboradores

Proyecto académico desarrollado como ejercicio práctico para aplicar los fundamentos de Vue 3, JavaScript, HTML y CSS.

Repositorio: [Dlaiton738/gestor-estudiantes-vue](https://github.com/Dlaiton738/gestor-estudiantes-vue)

## Licencia

Este proyecto tiene fines académicos y educativos. No se ha especificado una licencia de distribución para el repositorio.