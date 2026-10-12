# Rikimaka — Sistema Integral de Gestión Humana

Sistema web para la gestión de talento humano y proyectos, orientado a centralizar la administración de colaboradores, solicitudes de vacaciones, registro de labores, gestión de proyectos y generación de información para análisis operativo.

El proyecto está desarrollado bajo una arquitectura frontend basada en **HTML5, CSS3 y JavaScript ES6+**, aplicando separación de responsabilidades, modularización, control de versiones y desarrollo colaborativo mediante Git y GitHub.

**Curso:** SOFT-06 Diseño y Programación Web · Universidad CENFOTEC · Sección SCV · Periodo 2026-C3
**Docente:** Stephanie Delgado Brenes
**Entrega actual:** Avance I – Documentación y maquetación (wireframes)

| Recurso | Enlace |
| --- | --- |
| Repositorio | [github.com/pablo-hdz/Rikimaka](https://github.com/pablo-hdz/Rikimaka) |
| Wireframes (PDF, 22 páginas) | [`docs/wireframes-rikimaka.pdf`](docs/wireframes-rikimaka.pdf) |
| Detalle de pantallas y conexiones | [`docs/wireframes.md`](docs/wireframes.md) |
| Flujo de navegación (draw.io, editable) | [`docs/diagrams/flujo-navegacion.drawio`](docs/diagrams/flujo-navegacion.drawio) |
| Accesibilidad (WCAG 2.2 AAA) | [`docs/accesibilidad.md`](docs/accesibilidad.md) |

### Integrantes

| Integrante | Rol | Responsabilidades principales |
| --- | --- | --- |
| **Pablo Daniel Hernández Meléndez** | Líder de proyecto y desarrollador frontend | Coordinación del equipo, revisión de Pull Requests, integración en `main` y desarrollo de módulos. |
| **Fiorella María Pérez López** | Diseñadora UX/UI | Wireframes, sistema de componentes, flujo de navegación e identidad visual. |
| **Mariana Cubero Sanchez** | Desarrolladora frontend y responsable de accesibilidad | Maquetación HTML/CSS, lógica en JavaScript y validación de criterios WCAG 2.2 AAA. |

---

## Tabla de contenido

1. [Descripción del proyecto](#1-descripción-del-proyecto)
2. [Alcance funcional](#2-alcance-funcional)
3. [Arquitectura](#3-arquitectura)
4. [Stack tecnológico](#4-stack-tecnológico)
5. [Estructura del proyecto](#5-estructura-del-proyecto)
6. [Organización de la lógica](#6-organización-de-la-lógica)
7. [Roles y permisos](#7-roles-y-permisos)
8. [Requerimientos funcionales](#8-requerimientos-funcionales)
9. [Requerimientos no funcionales](#9-requerimientos-no-funcionales)
10. [Validación y manejo de errores](#10-validación-y-manejo-de-errores)
11. [Control de versiones y estrategia de branches](#11-control-de-versiones-y-estrategia-de-branches)
12. [Convención de commits](#12-convención-de-commits)
13. [Desarrollo iterativo](#13-desarrollo-iterativo)
14. [Diseño de interfaz – Avance I](#14-diseño-de-interfaz--avance-i)
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

* Administrador de Talento Humano
* Colaborador / Trabajador
* Personal de TI

La solución centraliza información relacionada con vacaciones, feriados, actividades laborales, horas trabajadas, proyectos, recursos y colaboradores.

### Objetivos

* Centralizar la información relacionada con la gestión humana.
* Digitalizar el proceso de solicitud y revisión de vacaciones.
* Registrar las actividades laborales realizadas por los colaboradores.
* Relacionar horas trabajadas con proyectos específicos.
* Administrar información de proyectos y recursos.
* Facilitar la generación de información consolidada para análisis.
* Mantener trazabilidad sobre las operaciones realizadas dentro del sistema.

---

## 2. Alcance funcional

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

El sistema contempla:

* Creación de proyectos.
* Consulta y modificación de proyectos.
* Registro de presupuesto.
* Registro de recursos.
* Asociación de colaboradores.
* Seguimiento del estado de los proyectos.

### 2.4 Reportes

La información registrada puede utilizarse para analizar:

* Horas trabajadas por proyecto.
* Horas utilizadas frente a recursos planificados.
* Distribución de carga laboral.
* Utilización de recursos.
* Información de productividad.
* Seguimiento operativo de proyectos.

### 2.5 Fuera de alcance

* Backend, base de datos real y autenticación segura (los datos se simulan con `localStorage`).
* Envío real de correos electrónicos.
* Integración con sistemas de planilla, nómina o control de asistencia.
* Aplicación móvil nativa (la versión web es responsive).

### 2.6 Reglas de negocio

* Los días de vacaciones se calculan en días hábiles: se excluyen fines de semana y feriados.
* Solo se pueden solicitar vacaciones dentro de los períodos permitidos y con saldo suficiente.
* Un colaborador solo puede reportar horas en los proyectos a los que está asignado.
* El total reportado en un día no puede superar 24 horas.
* Rechazar una solicitud requiere un comentario para el colaborador.

### 2.7 Supuestos

* **Creación de proyectos:** el enunciado indica que el Personal de TI crea el catálogo de proyectos, pero también menciona "proyectos creados por Recursos Humanos". Asumimos que **TI crea y mantiene los proyectos** y que **Talento Humano los consulta** para sus reportes. Se validará con el cliente en la siguiente revisión.
* Cada usuario tiene un único rol.
* El saldo de vacaciones de cada colaborador viene precargado en los datos de ejemplo.

### 2.8 Alcance por avance

| Avance | Contenido |
| --- | --- |
| Avance I | README, wireframes de 8 funcionalidades para Colaborador y Talento Humano, flujo de navegación y procesos del negocio. |
| Avance II | Maquetación HTML/CSS y lógica JavaScript de los módulos de Colaborador y Talento Humano; wireframes del Personal de TI. |
| Siguientes | Módulo de Personal de TI, iteraciones según la retroalimentación del cliente y despliegue en GitHub Pages. |

---

## 3. Arquitectura

La aplicación se desarrolla inicialmente como una solución frontend, separando estructura, presentación y lógica de aplicación.

```text
┌─────────────────────────────────────────┐
│                  HTML5                  │
│       Estructura y semántica            │
└────────────────────┬────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────┐
│                  CSS3                   │
│     Presentación y responsive design    │
└────────────────────┬────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────┐
│             JavaScript ES6+             │
│      Lógica e interacción del sistema   │
└────────────────────┬────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────┐
│          Servicios / Gestión de datos   │
│     Capa preparada para futura API      │
└─────────────────────────────────────────┘
```

### Principios técnicos

El diseño del proyecto considera:

* Separación de responsabilidades.
* Modularización.
* Bajo acoplamiento.
* Alta cohesión.
* Reutilización de componentes.
* Mantenibilidad.
* Escalabilidad.
* Trazabilidad.

La estructura está preparada para permitir una futura integración con un backend o una API REST.

---

## 4. Stack tecnológico

| Tecnología      | Uso                                               |
| --------------- | ------------------------------------------------- |
| HTML5           | Estructura semántica y componentes de la interfaz |
| CSS3            | Diseño, layouts, estilos y responsive design      |
| JavaScript ES6+ | Lógica de aplicación e interacción                |
| Git             | Control de versiones                              |
| GitHub          | Repositorio y colaboración                        |
| GitHub Pages    | Despliegue del frontend                           |
| draw.io         | Flujo de navegación y diagramas                   |

---

## 5. Estructura del proyecto

```text
Rikimaka/
│
├── index.html
│
├── pages/
│   ├── login.html
│   ├── dashboard.html
│   ├── vacaciones.html
│   ├── labores.html
│   ├── proyectos.html
│   └── reportes.html
│
├── css/
│   ├── base/
│   ├── components/
│   ├── layouts/
│   └── styles.css
│
├── js/
│   ├── core/
│   ├── modules/
│   │   ├── auth/
│   │   ├── vacaciones/
│   │   ├── labores/
│   │   ├── proyectos/
│   │   └── reportes/
│   ├── services/
│   ├── utils/
│   └── app.js
│
├── assets/
│   ├── images/
│   ├── icons/
│   └── fonts/
│
├── docs/
│   ├── wireframes-rikimaka.pdf      ← Wireframes del Avance I
│   ├── wireframes.md                ← Fichas de pantallas y conexiones
│   ├── accesibilidad.md             ← Contrastes y criterios WCAG 2.2 AAA
│   ├── requirements/
│   ├── diagrams/
│   │   └── flujo-navegacion.drawio  ← Flujo de navegación editable
│   └── feedback/
│
├── LICENSE
└── README.md
```

> **Estado actual (Avance I):** existen `README.md`, `LICENSE`, `docs/` y `assets/CREDITOS.md`. Las carpetas de código (`pages/`, `css/`, `js/`) se crean a partir del Avance II.

---

## 6. Organización de la lógica

La lógica de JavaScript se divide por responsabilidades funcionales:

```text
js/
│
├── core/
│
├── modules/
│   ├── auth/
│   ├── vacaciones/
│   ├── labores/
│   ├── proyectos/
│   └── reportes/
│
├── services/
│
└── utils/
```

Flujo general de ejecución:

```text
Usuario
   │
   ▼
Interfaz
   │
   ▼
Módulo funcional
   │
   ▼
Lógica de aplicación
   │
   ▼
Servicios / datos
   │
   ▼
Resultado
   │
   ▼
Actualización de interfaz
```

---

## 7. Roles y permisos

| Funcionalidad                    | Talento Humano | Colaborador |       TI       |
| -------------------------------- | :------------: | :---------: | :------------: |
| Gestionar feriados               |       Sí       |      No     |       No       |
| Gestionar períodos de vacaciones |       Sí       |      No     |       No       |
| Solicitar vacaciones             |       No       |      Sí     |       No       |
| Revisar solicitudes              |       Sí       |      No     |       No       |
| Registrar labores                |       No       |      Sí     |       No       |
| Consultar proyectos              |       Sí       |      Sí     |       Sí       |
| Gestionar proyectos              |       No       |      No     |       Sí       |
| Consultar reportes               |       Sí       |      No     | Según permisos |

---

## 8. Requerimientos funcionales

| ID    | Requerimiento                                   |
| ----- | ----------------------------------------------- |
| RF-01 | Gestionar feriados y períodos de vacaciones     |
| RF-02 | Registrar solicitudes de vacaciones             |
| RF-03 | Revisar y gestionar solicitudes                 |
| RF-04 | Registrar actividades laborales diarias         |
| RF-05 | Asociar actividades con proyectos               |
| RF-06 | Registrar horas y estado de actividades         |
| RF-07 | Gestionar proyectos y colaboradores             |
| RF-08 | Registrar presupuesto y recursos de proyectos   |
| RF-09 | Consolidar información para análisis y reportes |

---

## 9. Requerimientos no funcionales

### RNF-01 — Usabilidad

La interfaz debe permitir ejecutar las operaciones principales de manera clara y consistente.

### RNF-02 — Responsive Design

La aplicación debe adaptarse a diferentes resoluciones y dispositivos.

### RNF-03 — Mantenibilidad

El código debe mantenerse organizado por responsabilidades y módulos funcionales.

### RNF-04 — Escalabilidad

La arquitectura debe permitir incorporar nuevos módulos y funcionalidades.

### RNF-05 — Trazabilidad

Las operaciones relevantes deben poder relacionarse con usuarios, proyectos, actividades y períodos.

### RNF-06 — Integridad de datos

Los formularios y operaciones deben aplicar reglas de validación antes de procesar información.

### RNF-07 — Accesibilidad

La interfaz debe cumplir las pautas **WCAG 2.2 nivel AAA**: contraste de texto de 7:1 o superior (el color de marca `#9E0033` alcanza 8.4:1), uso completo con teclado, sin límites de tiempo, migas de pan, confirmación antes de acciones importantes, ayuda en formularios y tablas equivalentes para cada gráfico. Detalle en [`docs/accesibilidad.md`](docs/accesibilidad.md).

---

## 10. Validación y manejo de errores

El sistema contempla validaciones para:

* Campos obligatorios.
* Tipos de datos.
* Valores numéricos.
* Rangos de fechas.
* Horas trabajadas.
* Estados permitidos.
* Relaciones entre proyectos y colaboradores.
* Operaciones críticas.
* Datos inconsistentes o incompletos.

---

## 11. Control de versiones y estrategia de branches

El desarrollo utiliza Git como sistema de control de versiones y GitHub como plataforma de colaboración.

La rama `main` representa la versión estable del proyecto.

Las nuevas funcionalidades se desarrollan mediante ramas independientes:

```bash
git checkout -b feature/gestion-vacaciones
```

### Tipos de rama

| Rama | Propósito | Ejemplo |
| --- | --- | --- |
| `main` | Versión estable; cada avance entregado se marca con una etiqueta. | `v1.0-avance1` |
| `feature/<modulo>-<descripcion>` | Nueva funcionalidad. | `feature/vacaciones-calendario` |
| `fix/<descripcion>` | Corrección de errores. | `fix/calculo-dias-habiles` |
| `docs/<descripcion>` | Documentación y diseño. | `docs/wireframes-avance-1` |

### Reglas

1. No se hacen commits directos en `main`.
2. Todo cambio entra mediante un **Pull Request** con descripción de lo realizado.
3. Cada Pull Request requiere la **revisión y aprobación de al menos un integrante** distinto al autor.
4. Al cerrar cada avance se crea una etiqueta (`v1.0-avance1`, `v2.0-avance2`, …).
5. Las ramas se eliminan después de fusionarse.

Flujo de integración:

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

| Prefijo    | Descripción                       |
| ---------- | --------------------------------- |
| `feat`     | Nueva funcionalidad               |
| `fix`      | Corrección de errores             |
| `refactor` | Reestructuración del código       |
| `style`    | Cambios de formato o presentación |
| `docs`     | Documentación                     |
| `test`     | Pruebas                           |
| `chore`    | Mantenimiento                     |
| `a11y`     | Mejoras de accesibilidad          |

Ejemplos:

```bash
git commit -m "feat: implementar solicitud de vacaciones"
git commit -m "fix: validar rango de fechas"
git commit -m "refactor: separar lógica de proyectos"
git commit -m "docs: actualizar documentación técnica"
git commit -m "docs(wireframes): agregar wireframes del avance I"
```

Reglas: mensajes en español, en imperativo, de 72 caracteres como máximo y un commit por cambio lógico. Opcionalmente se indica el módulo entre paréntesis: `tipo(modulo): descripción`.

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

Este proceso permite validar la solución progresivamente y realizar ajustes a partir de los resultados obtenidos durante el desarrollo.

---

## 14. Diseño de interfaz – Avance I

Los wireframes del Avance I están en [`docs/wireframes-rikimaka.pdf`](docs/wireframes-rikimaka.pdf) (22 páginas). Cada pantalla incluye su código, rol, objetivo, anotaciones numeradas de comportamiento y accesibilidad, y el destino de cada botón.

### Contenido del PDF

| Páginas | Contenido |
| --- | --- |
| 1–2 | Portada e índice |
| 3 | Proceso de diseño: pasos, iteraciones y decisiones |
| 4–5 | Leyenda de símbolos y sistema de componentes |
| 6–18 | 13 pantallas (W00–W09 y 3 ventanas de confirmación) |
| 19–20 | Flujo de navegación y tabla de 23 conexiones |
| 21 | Procesos del negocio (vacaciones y reporte diario) con su resultado |
| 22 | Resultado final: vista general de todas las pantallas |

### Funcionalidades diseñadas

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

Las pantallas del Personal de TI (catálogo de proyectos, asignaciones y usuarios) se diseñarán en el Avance II.

### Identidad visual

* Inspiración en sitios de hotelería premium: imágenes amplias, títulos en mayúsculas, tarjetas y mucho espacio en blanco.
* Paleta en grises con el carmesí `#9E0033` para acciones principales; todo el texto con contraste de 7:1 o superior.
* Títulos en serif y texto en Inter; grid de 12 columnas y espaciado en múltiplos de 8.

---

## 15. Documentación

La documentación técnica se organiza mediante:

```text
docs/
│
├── wireframes-rikimaka.pdf
├── wireframes.md
├── accesibilidad.md
├── requirements/
├── diagrams/
│   └── flujo-navegacion.drawio
└── feedback/
```

Contenido previsto:

* Requerimientos funcionales.
* Requerimientos no funcionales.
* Diagramas.
* Decisiones de diseño.
* Evidencias de retroalimentación.
* Documentación técnica.

---

## 16. Instalación y ejecución

### Requisitos

* Navegador web moderno.
* Git.
* Visual Studio Code.
* Live Server, opcional.

### Clonar el repositorio

```bash
git clone https://github.com/pablo-hdz/Rikimaka.git
```

### Acceder al proyecto

```bash
cd Rikimaka
```

### Ejecutar

El proyecto puede ejecutarse mediante `index.html` o utilizando Live Server durante el desarrollo.

---

## 17. Despliegue

El frontend puede desplegarse mediante GitHub Pages para proporcionar una instancia pública de demostración.

```text
GitHub Repository
       │
       ▼
GitHub Pages
       │
       ▼
Aplicación Web
```

### Demo

**Aplicación:**
Se publicará en GitHub Pages a partir del Avance II.

**Repositorio:**
[https://github.com/pablo-hdz/Rikimaka](https://github.com/pablo-hdz/Rikimaka)

---

## 18. Evidencia visual

Los wireframes del Avance I, incluida la vista general de todas las pantallas (página 22), están en [`docs/wireframes-rikimaka.pdf`](docs/wireframes-rikimaka.pdf).

Las capturas de pantalla de la aplicación implementada se almacenarán en:

```text
assets/images/
```

Ejemplos de vistas documentadas:

* Login.
* Dashboard.
* Gestión de vacaciones.
* Registro de labores.
* Gestión de proyectos.
* Reportes.

---

## 19. Roadmap

* [x] Levantamiento inicial de requerimientos
* [x] Definición del alcance
* [x] Configuración inicial del repositorio
* [x] Diseño de interfaz: wireframes, flujo de navegación y procesos (Avance I)
* [ ] Implementación de módulos
* [ ] Implementación de validaciones
* [ ] Pruebas funcionales
* [ ] Iteraciones basadas en retroalimentación
* [ ] Documentación técnica
* [ ] Despliegue mediante GitHub Pages

Los elementos deben marcarse como completados únicamente después de haber sido implementados y validados.

---

## 20. Equipo

| Integrante | Rol |
| --- | --- |
| **Pablo Daniel Hernández Meléndez** | Líder de proyecto y desarrollador frontend |
| **Fiorella María Pérez López** | Diseñadora UX/UI |
| **Mariana Cubero Sanchez** | Desarrolladora frontend y responsable de accesibilidad |

El proyecto se desarrolla mediante un modelo colaborativo utilizando Git y GitHub, con ramas independientes, commits descriptivos y Pull Requests para integración y revisión del código.

---

## 21. Licencia

Este proyecto se distribuye bajo la licencia **MIT**.

Para consultar los términos completos de la licencia, revisar el archivo [`LICENSE`](LICENSE).
