---
title: 'Caso práctico: modelo E/R de una escuela'
---

## Solución

### Entidades y atributos

asignatura: id_asignatura, nombre, curso, horas_semana
alumno: id_alumno, nombre, apellidos, fecha_nacimiento, dirección, teléfono, email
profesor: id_profesor, nombre, apellidos, fecha_nacimiento, dirección, teléfono, email
departamento: id_departamento, nombre, teléfono, email
grupo: id_grupo, curso, letra
aula: id_aula, capacidad, ubicación

### Relaciones

se_matricula {

- entidades: alumno + grupo
- relaciones: id_alumno, id_grupo
- cardinalidad: M:N
- opcionalidad: 1:1
- atributos: fecha_matriculación, calificación
  }

enseña {

- entidades: profesor + grupo
- relaciones: id_profesor, id_grupo
- cardinalidad: M:N
- opcionalidad: 1:1
- atributos:
  }

  se divide en {

- entidades: asignatura + grupo
- relaciones: id_asignatura, id_grupo
- cardinalidad: 1:N
- opcionalidad: 1:1
- atributo:
  }

  se imparte en {

- entidades: grupo + aula
- relaciones: id_grupo, id_aula
- cardinalidad: N:M
- opcionalidad: 1:1
- atributo: dia, hora_inicio, hora_fin
  }

pertenece {

- entidades: profesor + departamento
- relaciones: id_profesor, id_departamento
- cardinalidad: N:1
- opcionalidad: 1:1
- atributo:
  }

dirige {

- entidades: profesor + departamento
- relaciones: id_profesor, id_departamento
- cardinalidad: 1:1
- atributo: desde, hasta
  }
