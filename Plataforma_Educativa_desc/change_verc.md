# Registro de cambios

Este archivo registra los cambios realizados en la documentación y diseño de la Plataforma Educativa.

El objetivo es mantener un historial de versiones del proyecto para identificar qué se fue agregando, modificando o corrigiendo durante el desarrollo.

---

## [1.1.0] - 2026-06-17

### Agregado

- Se incorporó el patrón MVC al diseño general del sistema.
- Se separó el sistema en paquetes: modelo, vista, controlador, servicio e ia.
- Se incorporó el patrón de diseño Facade mediante la clase PlataformaEducativaFacade.
- Se agregó la clase AsistenteIA para proyectar una futura funcionalidad de inteligencia artificial.
- Se agregó el caso de uso CU-08: Generar retroalimentación asistida por IA.
- Se agregó el método generarRetroalimentacionIA en la fachada del sistema.
- Se agregó el atributo retroalimentacionIA en la clase Resultado.
- Se incorporaron vistas relacionadas con la interfaz gráfica, como LoginVista, MenuDocenteVista, RealizarCuestionarioVista y RetroalimentacionIAVista.
- Se incorporaron controladores para organizar la comunicación entre la vista y la lógica del sistema.

### Modificado

- Se actualizó el diagrama de clases para incluir MVC, Facade e IA.
- Se actualizó la explicación del diseño para justificar la elección de los patrones.
- Se actualizaron los requerimientos de software para incluir decisiones de diseño.
- Se actualizaron los casos de uso para reflejar la intervención de controladores y fachada.
- Se mejoró la organización del sistema para facilitar su futura implementación en Java.

### Corregido

- Se ajustó la numeración de algunos flujos principales.
- Se aclaró la diferencia entre modelo, vista y controlador.
- Se aclaró que la inteligencia artificial no reemplaza la corrección automática, sino que funciona como apoyo para la retroalimentación.

---

## [1.0.0] - 2026-06-16

### Agregado

- Se creó la primera versión de la especificación de requisitos de software.
- Se definió el propósito de la Plataforma Educativa.
- Se definieron los usuarios principales: Docente y Estudiante.
- Se establecieron las funciones principales del sistema.
- Se definieron los requisitos funcionales y no funcionales.
- Se crearon los primeros casos de uso.
- Se creó el primer diagrama de clases del sistema.
- Se definieron las clases principales del modelo:
  - Usuario.
  - Docente.
  - Estudiante.
  - Categoria.
  - Pregunta.
  - OpcionRespuesta.
  - Cuestionario.
  - RespuestaEstudiante.
  - Resultado.
  - HistorialResultados.
  - Estadistica.

---

## [0.1.0] - 2026-06-16

### Agregado

- Se inició el proyecto de Plataforma Educativa.
- Se definió la idea general del sistema.
- Se planteó que la aplicación permitirá crear y resolver cuestionarios de opción múltiple.
- Se decidió trabajar con Java, Programación Orientada a Objetos y Java Swing.
- Se definió el uso de archivos de texto para almacenamiento local.