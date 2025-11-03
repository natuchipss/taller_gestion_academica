# taller_gestion_academica

**Materia:** Fundamentos y Bases de Datos Relacionales  
**Programa:** Ingeniería de Software – FESC  
**Estudiantes:** Natalia Salcedo Ortega, Jose David Cuberos 
**Año:** 2025  

---

## Descripción General

Este proyecto desarrolla un sistema de gestión académica para una institución educativa.  
Permite administrar departamentos, profesores, estudiantes, cursos, matrículas y calificaciones.  
Está implementado en **PostgreSQL** y busca aplicar los conceptos de diseño relacional, integridad referencial, triggers, funciones y consultas avanzadas.

---

## Contenido del Repositorio

- **/scripts/**: contiene el archivo `taller_gestion_academica.sql` con toda la estructura del sistema.  
- **/diagramas/**: incluye el diagrama entidad-relación (ER) del modelo de datos.  
- **README.md**: documento con la descripción y las instrucciones de instalación.

---

## Estructura de la Base de Datos

El sistema se organiza dentro del esquema **acad**, compuesto por las siguientes tablas:

| Tabla | Descripción |
|-------|--------------|
| department | Registra los departamentos académicos. |
| teacher | Contiene los datos de los profesores y su departamento. |
| student | Almacena la información de los estudiantes y su fecha de inscripción. |
| course | Define los cursos, créditos, capacidad y docente asignado. |
| enrollment | Administra las matrículas de los estudiantes en los cursos. |
| grade | Registra las calificaciones asociadas a cada matrícula. |

---

## Funciones y Triggers

- **fn_check_capacity()**: verifica que un curso no supere su capacidad antes de registrar una nueva matrícula.  
- **trg_check_capacity**: trigger que ejecuta la función anterior antes de insertar en la tabla `enrollment`.  
- **fn_grade_sets_completed()**: actualiza automáticamente el estado de una matrícula a “completed” al registrar una calificación.  
- **trg_grade_completed**: trigger que ejecuta la función anterior después de insertar en la tabla `grade`.

---

## Datos de Ejemplo

El script incluye información inicial para probar el funcionamiento del sistema:

- Departamentos: *Computer Science*, *Mathematics*  
- Profesores: *Laura Martínez*, *Carlos Rojas*  
- Estudiantes: *Ana Pérez*, *Luis Gómez*, *María Torres*, *Sofía Díaz*  
- Cursos: *Intro to Databases*, *Advanced Math*  
- Matrículas y calificaciones de ejemplo

---

## Consultas Incluidas

1. **Top 5 de estudiantes con mayor promedio:** muestra los cinco estudiantes con mejor rendimiento.  
2. **Clasificación de notas por asignatura:** ordena las calificaciones por curso y calcula el promedio general.  
3. **Porcentaje de abandonos por curso:** calcula la tasa de deserción de cada asignatura.

---

## Requisitos Técnicos

- **Sistema gestor:** PostgreSQL 15 o superior  
- **Herramienta recomendada:** DBeaver o pgAdmin  
- **Lenguaje:** SQL con extensiones PL/pgSQL  

   ```bash
   git clone https://github.com/tuusuario/taller_gestion_academica.git
