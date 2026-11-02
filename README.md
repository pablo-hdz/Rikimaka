# Rikimaka — Sistema Integral de Gestión Humana

Sistema web para la gestión de talento humano y proyectos, orientado a centralizar la administración de colaboradores, solicitudes de vacaciones, registro de labores, gestión de proyectos y generación de información para análisis operativo.

En el **Avance II**, el proyecto presenta la maquetación de interfaces mediante **HTML5 y CSS3**, con organización de estilos, navegación entre páginas y adaptación a distintos tamaños de pantalla. Se utiliza Git y GitHub para el trabajo colaborativo. La lógica funcional y la persistencia de datos forman parte del desarrollo futuro.

**Curso:** SOFT-06 Diseño y Programación Web · Universidad CENFOTEC · Sección SCV · Periodo 2026-C3  
**Docente:** Stephanie Delgado Brenes  
**Entrega actual:** Avance II – Implementación de pantallas HTML/CSS.

| Recurso | Enlace |
| --- | --- |
| Repositorio | [github.com/pablo-hdz/Rikimaka](https://github.com/pablo-hdz/Rikimaka) |
| Wireframes (PDF, 22 páginas) | [`docs/wireframes-rikimaka.pdf`](docs/wireframes-rikimaka.pdf) |
| Detalle de pantallas y conexiones | [`docs/wireframes.md`](docs/wireframes.md) |
| Flujo de navegación (draw.io, editable) | [`docs/diagrams/flujo-navegacion.drawio`](docs/diagrams/flujo-navegacion.drawio) |
| Documentación de accesibilidad | [`docs/accesibilidad.md`](docs/accesibilidad.md) |

### Integrantes

| Integrante | Rol | Responsabilidades principales |
| --- | --- | --- |
| **Pablo Daniel Hernández Meléndez** | Líder de proyecto y desarrollador frontend | Coordinación del equipo, revisión de Pull Requests, integración en `main` y desarrollo de módulos. |
| **Fiorella María Pérez López** | Diseñadora UX/UI | Wireframes, sistema de componentes, flujo de navegación e identidad visual. |
| **Mariana Cubero Sanchez** | Desarrolladora frontend y responsable de accesibilidad | Maquetación HTML/CSS y revisión de criterios de accesibilidad. |

---

## Tabla de contenido

1. [Descripción del proyecto](#1-descripción-del-proyecto)
2. [Alcance funcional](#2-alcance-funcional)
3. [Arquitectura](#3-arquitectura)
4. [Stack tecnológico](#4-stack-tecnológico)
5. [Estructura del proyecto](#5-estructura-del-proyecto)
6. [Organización de la implementación](#6-organización-de-la-implementación)
7. [Roles y permisos](#7-roles-y-permisos)
8. [Requerimientos funcionales](#8-requerimientos-funcionales)
9. [Requerimientos no funcionales](#9-requerimientos-no-funcionales)
10. [Validación y manejo de errores](#10-validación-y-manejo-de-errores)
11. [Control de versiones y estrategia de branches](#11-control-de-versiones-y-estrategia-de-branches)
12. [Convención de commits](#12-convención-de-commits)
13. [Desarrollo iterativo](#13-desarrollo-iterativo)
14. [Diseño de interfaz – Avances I y II](#14-diseño-de-interfaz--avances-i-y-ii)
15. [Documentación](#15-documentación)
16. [Instalación y ejecución](#16-instalación-y-ejecución)
17. [Despliegue](#17-despliegue)
18. [Evidencia visual](#18-evidencia-visual)
19. [Roadmap](#19-roadmap)
20. [Equipo](#20-equipo)
21. [Licencia](#21-licencia)

---

## 1. Descripción del proyecto

Rikimaka es una aplicación web orientada a la gestión de procesos relacionados con talento humano y administración operativa de proyectos.

El sistema contempla tres perfiles principales:

* Administrador de Talento Humano.
* Colaborador / Trabajador.
* Personal de TI.

La solución busca centralizar información relacionada con vacaciones, feriados, actividades laborales, horas trabajadas, proyectos, recursos y colaboradores. En el Avance II se desarrollan las interfaces visuales de Colaborador y Talento Humano a partir de los wireframes del Avance I.

### Objetivos

* Centralizar la información relacionada con la gestión humana.
* Digitalizar el proceso de solicitud y revisión de vacaciones.
* Registrar las actividades laborales realizadas por los colaboradores.
* Relacionar horas trabajadas con proyectos específicos.
* Administrar información de proyectos y recursos.
* Facilitar la generación de información consolidada para análisis.
* Mantener trazabilidad sobre las operaciones realizadas dentro del sistema.

Estos objetivos describen el alcance general previsto y no implican que todas las funcionalidades estén operativas en el Avance II.

---

## 2. Alcance funcional

Las funcionalidades descritas a continuación corresponden al **alcance planificado**. En el Avance II se implementan sus pantallas y elementos visuales, sin procesamiento real de datos.

### 2.1 Talento Humano

El módulo de Talento Humano contempla:

* Gestión de feriados.
* Gestión de períodos de vacaciones.
* Consulta de solicitudes.
* Revisión de solicitudes.
* Aprobación y rechazo de solicitudes.
* Consulta de información consolidada.
* Visualización de estadísticas y reportes.

### 2.2 Colaborador

El módulo del colaborador contempla:

* Solicitud de vacaciones.
* Consulta del calendario laboral.
* Visualización de feriados.
* Registro diario de labores.
* Asociación de actividades con proyectos.
* Registro de horas trabajadas.
* Registro del estado de las actividades.

### 2.3 Gestión de proyectos

El sistema contempla para etapas posteriores:

* Creación de proyectos.
* Consulta y modificación de proyectos.
* Registro de presupuesto.
* Registro de recursos.
* Asociación de colaboradores.
* Seguimiento del estado de los proyectos.

### 2.4 Reportes

La información que registre el sistema podrá utilizarse para analizar:

* Horas trabajadas por proyecto.
* Horas utilizadas frente a recursos planificados.
* Distribución de carga laboral.
* Utilización de recursos.
* Información de productividad.
* Seguimiento operativo de proyectos.

En este avance se presenta la interfaz de estadísticas y reportes; los cálculos y datos dinámicos quedan pendientes.

### 2.5 Fuera de alcance del Avance II

* Backend, base de datos real y autenticación segura.
* Almacenamiento persistente mediante `localStorage` u otros mecanismos.
* Procesamiento efectivo de solicitudes, reportes y formularios.
* Envío real de correos electrónicos.
* Integración con sistemas de planilla, nómina o control de asistencia.
* Aplicación móvil nativa (se plantea una interfaz web responsive).

### 2.6 Reglas de negocio

Reglas definidas para la futura implementación funcional:

* Los días de vacaciones se calculan en días hábiles: se excluyen fines de semana y feriados.
* Solo se pueden solicitar vacaciones dentro de los períodos permitidos y con saldo suficiente.
* Un colaborador solo puede reportar horas en los proyectos a los que está asignado.
* El total reportado en un día no puede superar 24 horas.
* Rechazar una solicitud requiere un comentario para el colaborador.

### 2.7 Supuestos

* **Creación de proyectos:** el enunciado indica que el Personal de TI crea el catálogo de proyectos, pero también menciona «proyectos creados por Recursos Humanos». Asumimos que **TI crea y mantiene los proyectos** y que **Talento Humano los consulta** para sus reportes. Se validará con el cliente en una revisión posterior.
* Cada usuario tiene un único rol.
* El saldo de vacaciones de cada colaborador vendrá precargado en los datos de ejemplo cuando se implemente la lógica correspondiente.

### 2.8 Alcance por avance

| Avance | Contenido |
| --- | --- |
| Avance I | README, wireframes de las funcionalidades para Colaborador y Talento Humano, flujo de navegación y procesos del negocio. |
| Avance II | Maquetación de pantallas HTML/CSS para Colaborador y Talento Humano, navegación mediante enlaces y diseño responsive. |
| Siguientes | Lógica funcional, validaciones, módulos adicionales —incluido Personal de TI—, pruebas e iteraciones según retroalimentación. |

---

## 3. Arquitectura

La implementación actual es una solución frontend estática que separa la estructura del contenido y su presentación visual.

```text
┌─────────────────────────────────────────┐
│                  HTML5                  │
│       Estructura y semántica            │
└────────────────────┬────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────┐
│                  CSS3                   │
│     Presentación y diseño responsive    │
└────────────────────┬────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────┐
│              Navegador web              │
│    Visualización y enlaces entre vistas │
└─────────────────────────────────────────┘
```

### Principios técnicos

El diseño del proyecto considera:

* Separación de responsabilidades.
* Modularización y organización de archivos.
* Bajo acoplamiento y alta cohesión como objetivos de diseño.
* Reutilización de estilos y componentes visuales.
* Mantenibilidad y escalabilidad.
* Trazabilidad de cambios mediante Git.

La incorporación de JavaScript y una futura API se considera para siguientes etapas, no para la implementación actual.

---

## 4. Stack tecnológico

| Tecnología | Uso |
| --- | --- |
| HTML5 | Estructura semántica de las pantallas. |
| CSS3 | Estilos, distribución visual y diseño responsive. |
| Git | Control de versiones. |
| GitHub | Repositorio y colaboración. |
| draw.io | Flujo de navegación y diagramas. |
| Visual Studio Code | Edición del proyecto. |

**Previsto para etapas posteriores:** JavaScript ES6+ para lógica e interacción, y GitHub Pages como posible plataforma de publicación.

---

## 5. Estructura del proyecto

```text
Rikimaka/
│
├── src/
│   ├── index.html
│   ├── login.html
│   ├── colaborador.html
│   ├── administrador.html
│   ├── vacaciones.html
│   ├── calendario.html
│   ├── reporte-diario.html
│   ├── historial.html
│   ├── solicitudes.html
│   ├── estadisticas.html
│   ├── formulario-feriado.html
│   ├── confirmar-vacaciones.html
│   ├── confirmar-reporte.html
│   └── ayuda.html
│
├── assets/
│   ├── css/
│   │   ├── base.css
│   │   ├── layout.css
│   │   └── components.css
│   └── img/
│       └── iconos/
│
├── docs/
│   ├── wireframes-rikimaka.pdf
│   ├── wireframes.md
│   ├── accesibilidad.md
│   └── diagrams/
│       └── flujo-navegacion.drawio
│
├── LICENSE
└── README.md
```

> **Estado actual (Avance II):** las páginas se encuentran en `src/`, los estilos en `assets/css/` y los recursos gráficos en `assets/img/iconos/`. La documentación del Avance I se conserva en `docs/`. El esquema anterior destaca los archivos principales y no necesariamente enumera todos los archivos auxiliares del repositorio.

---

## 6. Organización de la implementación

La implementación actual separa las pantallas HTML de los archivos de estilos CSS.

### Pantallas HTML

```text
src/
├── index.html
├── login.html
├── colaborador.html
├── administrador.html
├── vacaciones.html
├── calendario.html
├── reporte-diario.html
├── historial.html
├── solicitudes.html
├── estadisticas.html
├── formulario-feriado.html
├── confirmar-vacaciones.html
├── confirmar-reporte.html
└── ayuda.html
```

### Archivos CSS

```text
assets/css/
├── base.css
├── layout.css
└── components.css
```

* `base.css`: estilos generales.
* `layout.css`: distribución de las páginas.
* `components.css`: estilos de elementos y componentes de interfaz.

### Flujo visual de navegación

```text
Usuario
   │
   ▼
Bienvenida (index.html)
   │
   ▼
Inicio de sesión (login.html)
   │
   ├──► Pantallas del colaborador
   │
   └──► Pantallas de Talento Humano
                │
                ▼
       Secciones y formularios
```

La navegación del Avance II se plantea mediante enlaces HTML. Los formularios y controles representan visualmente los procesos, pero no ejecutan operaciones reales ni guardan información.

---

## 7. Roles y permisos

| Funcionalidad | Talento Humano | Colaborador | TI |
| --- | :---: | :---: | :---: |
| Gestionar feriados | Sí | No | No |
| Gestionar períodos de vacaciones | Sí | No | No |
| Solicitar vacaciones | No | Sí | No |
| Revisar solicitudes | Sí | No | No |
| Registrar labores | No | Sí | No |
| Consultar proyectos | Sí | Sí | Sí |
| Gestionar proyectos | No | No | Sí |
| Consultar reportes | Sí | No | Según permisos |

Esta tabla refleja los **permisos previstos** para el sistema completo. En el Avance II se muestran interfaces diferenciadas para Colaborador y Talento Humano, sin control real de acceso o autenticación.

---

## 8. Requerimientos funcionales

| ID | Requerimiento |
| --- | --- |
| RF-01 | Gestionar feriados y períodos de vacaciones. |
| RF-02 | Registrar solicitudes de vacaciones. |
| RF-03 | Revisar y gestionar solicitudes. |
| RF-04 | Registrar actividades laborales diarias. |
| RF-05 | Asociar actividades con proyectos. |
| RF-06 | Registrar horas y estado de actividades. |
| RF-07 | Gestionar proyectos y colaboradores. |
| RF-08 | Registrar presupuesto y recursos de proyectos. |
| RF-09 | Consolidar información para análisis y reportes. |

Los requerimientos se mantienen como referencia del proyecto. En el Avance II se desarrolla su **representación visual**, no la totalidad de su comportamiento funcional.

---

## 9. Requerimientos no funcionales

### RNF-01 — Usabilidad

La interfaz debe permitir identificar y recorrer las operaciones principales de manera clara y consistente.

### RNF-02 — Responsive Design

La aplicación debe adaptarse a diferentes resoluciones y dispositivos mediante CSS.

### RNF-03 — Mantenibilidad

El código debe mantenerse organizado por responsabilidades y archivos.

### RNF-04 — Escalabilidad

La estructura debe permitir incorporar nuevas pantallas y funcionalidades.

### RNF-05 — Trazabilidad

Se mantiene el historial de cambios del proyecto mediante Git. La trazabilidad de operaciones de usuarios dentro del sistema se implementará posteriormente.

### RNF-06 — Integridad de datos

Los formularios y operaciones deberán aplicar reglas de validación cuando se incorpore la lógica de procesamiento. La presencia de campos en HTML no garantiza por sí sola todas las validaciones de negocio.

### RNF-07 — Accesibilidad

El proyecto utiliza como referencia los criterios de accesibilidad definidos en [`docs/accesibilidad.md`](docs/accesibilidad.md), que plantea objetivos de **WCAG 2.2 nivel AAA**. Entre los aspectos de diseño considerados se incluyen contraste, navegación con teclado, claridad de formularios y ayudas visuales.

**Importante:** el nivel AAA se mantiene como **objetivo documentado**, no como certificación de cumplimiento de todas las pantallas. Su verificación requiere pruebas específicas.

---

## 10. Validación y manejo de errores

El sistema contempla, para etapas funcionales posteriores, validaciones de:

* Campos obligatorios.
* Tipos de datos.
* Valores numéricos.
* Rangos de fechas.
* Horas trabajadas.
* Estados permitidos.
* Relaciones entre proyectos y colaboradores.
* Operaciones críticas.
* Datos inconsistentes o incompletos.

Durante el Avance II se diseñan los campos, mensajes y pantallas asociados a estos procesos. Las validaciones de negocio y el manejo efectivo de errores todavía no se consideran implementados.

---

## 11. Control de versiones y estrategia de branches

El desarrollo utiliza Git como sistema de control de versiones y GitHub como plataforma de colaboración.

La rama `main` contiene la versión integrada del proyecto. Se propone utilizar ramas independientes para nuevas funcionalidades y correcciones.

Ejemplo de creación de una rama:

```bash
git checkout -b feature/gestion-vacaciones
```

### Tipos de rama

| Rama | Propósito | Ejemplo |
| --- | --- | --- |
| `main` | Versión integrada del proyecto; cada avance puede marcarse con una etiqueta. | `v1.0-avance1` |
| `feature/<modulo>-<descripcion>` | Nueva funcionalidad. | `feature/vacaciones-calendario` |
| `fix/<descripcion>` | Corrección de errores. | `fix/calculo-dias-habiles` |
| `docs/<descripcion>` | Documentación y diseño. | `docs/wireframes-avance-1` |

### Flujo de trabajo propuesto

1. Desarrollar cambios en una rama independiente cuando corresponda.
2. Registrar los cambios mediante commits descriptivos.
3. Crear un Pull Request para revisión del equipo cuando se utilicen ramas.
4. Integrar los cambios revisados en `main`.
5. Identificar las entregas mediante etiquetas si el equipo así lo acuerda.

> Estas son pautas de colaboración del proyecto. Durante la carga inicial del Avance II también se incorporaron archivos directamente en `main`, por lo que no se afirma que todos los cambios hayan seguido un proceso de Pull Requests.

Flujo recomendado:

```text
feature/*
     │
     ▼
Desarrollo
     │
     ▼
Pruebas
     │
     ▼
Commit
     │
     ▼
Push
     │
     ▼
Pull Request
     │
     ▼
Code Review
     │
     ▼
Merge
     │
     ▼
main
```

---

## 12. Convención de commits

| Prefijo | Descripción |
| --- | --- |
| `feat` | Nueva funcionalidad. |
| `fix` | Corrección de errores. |
| `refactor` | Reestructuración del código. |
| `style` | Cambios de formato o presentación. |
| `docs` | Documentación. |
| `test` | Pruebas. |
| `chore` | Mantenimiento. |
| `a11y` | Mejoras de accesibilidad. |

Ejemplos de mensajes recomendados:

```bash
git commit -m "feat: implementar solicitud de vacaciones"
git commit -m "fix: validar rango de fechas"
git commit -m "refactor: separar lógica de proyectos"
git commit -m "docs: actualizar documentación técnica"
git commit -m "docs(wireframes): agregar wireframes del avance I"
```

Convención propuesta: mensajes en español, en imperativo, de hasta 72 caracteres y un commit por cambio lógico. Opcionalmente se indica el módulo entre paréntesis: `tipo(modulo): descripción`.

---

## 13. Desarrollo iterativo

El proyecto contempla un proceso de desarrollo basado en iteraciones y retroalimentación.

### Iteración 1

```text
Requerimientos
      ↓
Análisis
      ↓
Diseño
      ↓
Implementación inicial
      ↓
Retroalimentación
```

### Iteración 2

```text
Correcciones
      ↓
Refinamiento
      ↓
Pruebas
      ↓
Retroalimentación
      ↓
Ajustes
```

Este proceso permite validar progresivamente la solución. El Avance I se concentró en el diseño y la documentación; el Avance II desarrolla las pantallas HTML/CSS correspondientes.

---

## 14. Diseño de interfaz – Avances I y II

### Avance I: wireframes

Los wireframes del Avance I están en [`docs/wireframes-rikimaka.pdf`](docs/wireframes-rikimaka.pdf) (22 páginas). Cada pantalla incluye su código, rol, objetivo, anotaciones numeradas de comportamiento y accesibilidad, y el destino previsto de cada botón.

#### Contenido del PDF

| Páginas | Contenido |
| --- | --- |
| 1–2 | Portada e índice. |
| 3 | Proceso de diseño: pasos, iteraciones y decisiones. |
| 4–5 | Leyenda de símbolos y sistema de componentes. |
| 6–18 | 13 pantallas (W00–W09 y 3 ventanas de confirmación). |
| 19–20 | Flujo de navegación y tabla de 23 conexiones. |
| 21 | Procesos del negocio (vacaciones y reporte diario) con su resultado. |
| 22 | Resultado final: vista general de todas las pantallas. |

#### Funcionalidades diseñadas

| # | Funcionalidad | Rol | Pantallas |
| --- | --- | --- | --- |
| — | Bienvenida e inicio de sesión | Todos | W00, W01 |
| F1 | Panel personal | Colaborador | W02 |
| F2 | Solicitar vacaciones con calendario de feriados | Colaborador | W03, W03b |
| F3 | Registrar reporte diario de actividades | Colaborador | W04 |
| F4 | Historial de reportes | Colaborador | W05 |
| F5 | Panel administrativo | Talento Humano | W06 |
| F6 | Aprobar o rechazar vacaciones | Talento Humano | W07, W07b |
| F7 | Gestionar feriados y períodos permitidos | Talento Humano | W08, W08b |
| F8 | Estadísticas y reportes | Talento Humano | W09 |

Las pantallas del Personal de TI —catálogo de proyectos, asignaciones y usuarios— se mantienen como parte del alcance previsto para el proyecto, pero no se presentan como implementadas en este avance.

### Avance II: maquetación HTML/CSS

Se desarrollan pantallas en `src/` basadas en los diseños y flujos documentados. La entrega incluye vistas de bienvenida, inicio de sesión, paneles de Colaborador y Talento Humano, vacaciones, calendario, reportes, historial, solicitudes, estadísticas, feriados, confirmaciones y ayuda.

La presentación se organiza en los archivos `base.css`, `layout.css` y `components.css`. El objetivo de este avance es mostrar una interfaz coherente, con enlaces entre páginas y adaptación visual a diferentes tamaños de pantalla.

### Identidad visual

* Inspiración en sitios de hotelería premium: imágenes amplias, títulos en mayúsculas, tarjetas y espacio en blanco.
* Paleta en grises con el carmesí `#9E0033` para acciones principales.
* Títulos en serif y texto en Inter como referencias del diseño original.
* Criterios de contraste y accesibilidad documentados en el Avance I, sujetos a verificación en la implementación.

---

## 15. Documentación

La documentación técnica se organiza en `docs/` y conserva los materiales elaborados durante el Avance I.

```text
docs/
├── wireframes-rikimaka.pdf
├── wireframes.md
├── accesibilidad.md
└── diagrams/
    └── flujo-navegacion.drawio
```

La documentación del proyecto contempla:

* Requerimientos funcionales y no funcionales.
* Diagramas y flujo de navegación.
* Decisiones de diseño.
* Evidencias de retroalimentación.
* Documentación técnica de los avances.

---

## 16. Instalación y ejecución

### Requisitos

* Navegador web moderno.
* Git, si se desea clonar el repositorio.
* Visual Studio Code, opcional para revisar o editar los archivos.
* Live Server, opcional para visualizar los cambios durante el desarrollo.

### Clonar el repositorio

```bash
git clone https://github.com/pablo-hdz/Rikimaka.git
```

### Acceder al proyecto

```bash
cd Rikimaka
```

### Ejecutar

Abrir el archivo **`src/index.html`** en un navegador web. También se puede abrir la carpeta del proyecto en Visual Studio Code y utilizar Live Server.

Los archivos HTML enlazan los estilos ubicados en `assets/css/`. Para visualizar correctamente las páginas y los íconos, se debe conservar la estructura de carpetas del repositorio.

No es necesario instalar dependencias ni ejecutar un servidor backend para visualizar la maquetación del Avance II.

---

## 17. Despliegue

El proyecto puede publicarse mediante GitHub Pages en una etapa posterior para disponer de una demostración accesible desde internet.

```text
Repositorio GitHub
       │
       ▼
GitHub Pages (si se configura)
       │
       ▼
Demostración web
```

### Demo

**Estado:** No se incluye en este README un enlace público de GitHub Pages porque su publicación no se ha confirmado.

**Acceso actual:** la maquetación puede visualizarse descargando o clonando el repositorio y abriendo `src/index.html`.

**Repositorio:** [Rikimaka en GitHub](https://github.com/pablo-hdz/Rikimaka).

---

## 18. Evidencia visual

Los wireframes del Avance I, incluida la vista general de todas las pantallas (página 22), están en [`docs/wireframes-rikimaka.pdf`](docs/wireframes-rikimaka.pdf).

Las pantallas implementadas del Avance II pueden revisarse directamente en los archivos HTML de `src/`. Las capturas de pantalla adicionales, si se requieren, podrán incorporarse posteriormente a la documentación.

Entre las vistas disponibles se encuentran:

* Bienvenida e inicio de sesión.
* Panel del colaborador.
* Panel administrativo.
* Vacaciones y calendario.
* Registro diario de labores e historial.
* Solicitudes y estadísticas.
* Gestión visual de feriados.
* Pantallas de confirmación y ayuda.

---

## 19. Roadmap

* [x] Levantamiento inicial de requerimientos.
* [x] Definición del alcance.
* [x] Configuración inicial del repositorio.
* [x] Diseño de interfaz: wireframes, flujo de navegación y procesos (Avance I).
* [x] Incorporación de pantallas HTML para Colaborador y Talento Humano (Avance II).
* [x] Incorporación de archivos CSS y recursos gráficos (Avance II).
* [ ] Verificación integral de enlaces, adaptación responsive y accesibilidad de todas las pantallas.
* [ ] Implementación de la lógica funcional de los módulos.
* [ ] Implementación de validaciones de negocio.
* [ ] Pruebas funcionales de operaciones y procesamiento de datos.
* [ ] Iteraciones basadas en retroalimentación.
* [ ] Ampliación de la documentación técnica.
* [ ] Despliegue mediante GitHub Pages, si se decide publicar la aplicación.

Los elementos se marcan como completados únicamente cuando su realización está confirmada. La presencia de una pantalla HTML no equivale a tener implementada su funcionalidad de negocio.

---

## 20. Equipo

| Integrante | Rol |
| --- | --- |
| **Pablo Daniel Hernández Meléndez** | Líder de proyecto y desarrollador frontend |
| **Fiorella María Pérez López** | Diseñadora UX/UI |
| **Mariana Cubero Sanchez** | Desarrolladora frontend y responsable de accesibilidad |

El proyecto se desarrolla de forma colaborativa utilizando Git y GitHub, con organización de tareas, integración de archivos y revisión conjunta del avance.

---

## 21. Licencia

Este proyecto se distribuye bajo la licencia **MIT**.

Para consultar los términos completos de la licencia, revisar el archivo [`LICENSE`](LICENSE).
