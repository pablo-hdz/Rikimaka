# Rikimaka — Sistema Integral de Gestión Humana

Sistema web para la gestión de talento humano y proyectos, orientado a centralizar la administración de colaboradores, solicitudes de vacaciones, registro de labores, gestión de proyectos y generación de información para análisis operativo.

El proyecto está desarrollado bajo una arquitectura frontend basada en **HTML5, CSS3 y JavaScript ES6+**, aplicando separación de responsabilidades, modularización, control de versiones y desarrollo colaborativo mediante Git y GitHub.

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

---

## 5. Estructura del proyecto

```text
sistema-gestion-humana/
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
│   ├── requirements/
│   ├── diagrams/
│   └── feedback/
│
├── LICENSE
└── README.md
```

> Esta estructura debe mantenerse sincronizada con la estructura real del repositorio.

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

## 11. Control de versiones

El desarrollo utiliza Git como sistema de control de versiones y GitHub como plataforma de colaboración.

La rama `main` representa la versión estable del proyecto.

Las nuevas funcionalidades se desarrollan mediante ramas independientes:

```bash
git checkout -b feature/gestion-vacaciones
```

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

Ejemplos:

```bash
git commit -m "feat: implementar solicitud de vacaciones"
git commit -m "fix: validar rango de fechas"
git commit -m "refactor: separar lógica de proyectos"
git commit -m "docs: actualizar documentación técnica"
```

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

## 14. Documentación

La documentación técnica se organiza mediante:

```text
docs/
│
├── requirements/
├── diagrams/
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

## 15. Instalación y ejecución

### Requisitos

* Navegador web moderno.
* Git.
* Visual Studio Code.
* Live Server, opcional.

### Clonar el repositorio

```bash
git clone URL_DEL_REPOSITORIO
```

### Acceder al proyecto

```bash
cd sistema-gestion-humana
```

### Ejecutar

El proyecto puede ejecutarse mediante `index.html` o utilizando Live Server durante el desarrollo.

---

## 16. Despliegue

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
`ENLACE_DE_LA_DEMO`

**Repositorio:**
`ENLACE_DEL_REPOSITORIO`

---

## 17. Evidencia visual

Las capturas de pantalla se almacenarán en:

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

## 18. Roadmap

* [x] Levantamiento inicial de requerimientos
* [x] Definición del alcance
* [x] Configuración inicial del repositorio
* [ ] Diseño de interfaz
* [ ] Implementación de módulos
* [ ] Implementación de validaciones
* [ ] Pruebas funcionales
* [ ] Iteraciones basadas en retroalimentación
* [ ] Documentación técnica
* [ ] Despliegue mediante GitHub Pages

Los elementos deben marcarse como completados únicamente después de haber sido implementados y validados.

---

## 19. Equipo

### Autor principal

**Pablo Daniel Hernández Meléndez**
* Colaborador 1
* Colaborador 2
* Colaborador 3

El proyecto se desarrolla mediante un modelo colaborativo utilizando Git y GitHub, con ramas independientes, commits descriptivos y Pull Requests para integración y revisión del código.

---

## 20. Licencia

Este proyecto se distribuye bajo la licencia **MIT**.

Para consultar los términos completos de la licencia, revisar el archivo [`LICENSE`](LICENSE).
