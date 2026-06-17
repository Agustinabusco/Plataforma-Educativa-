# Diseño del sistema

## Plataforma Educativa

Este documento describe las principales decisiones de diseño tomadas para el desarrollo de la Plataforma Educativa. El sistema tiene como objetivo permitir que docentes creen cuestionarios de opción múltiple y que estudiantes puedan resolverlos, obtener una corrección automática y consultar sus resultados.

El diseño se basa en Programación Orientada a Objetos y se organiza utilizando el patrón MVC junto con el patrón de diseño Facade. Además, se incorpora una clase relacionada con inteligencia artificial para una futura ampliación del proyecto.

---

## 1. Elección del patrón MVC

El patrón MVC significa Modelo, Vista y Controlador. Se eligió este patrón porque permite separar las responsabilidades del sistema y evitar que toda la lógica quede mezclada en las mismas clases.

### Modelo

El modelo contiene las clases principales del sistema, es decir, aquellas que representan los datos y la lógica del dominio.

En este proyecto, el modelo está formado por clases como:

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

Estas clases representan los elementos centrales de la plataforma educativa.

### Vista

La vista contiene las pantallas que verá el usuario. En este proyecto, las vistas serán desarrolladas con Java Swing.

Algunas vistas previstas son:

- LoginVista.
- MenuDocenteVista.
- MenuEstudianteVista.
- GestionCategoriasVista.
- GestionPreguntasVista.
- CrearCuestionarioVista.
- RealizarCuestionarioVista.
- HistorialVista.
- EstadisticasVista.
- RetroalimentacionIAVista.

Las vistas se encargan de mostrar información y recibir datos del usuario, pero no deben contener la lógica principal del sistema.

### Controlador

El controlador recibe las acciones realizadas por el usuario desde la vista y coordina la respuesta del sistema.

Algunos controladores previstos son:

- LoginController.
- CategoriaController.
- PreguntaController.
- CuestionarioController.
- TestController.
- HistorialController.
- EstadisticaController.

Por ejemplo, cuando un estudiante finaliza un cuestionario, la vista informa la acción al controlador. Luego, el controlador se comunica con la fachada para realizar la corrección y guardar el resultado.

---

## 2. Elección del patrón Facade

El patrón Facade se utiliza para simplificar el acceso a las funcionalidades principales del sistema.

En este proyecto, la clase que representa la fachada es:

PlataformaEducativaFacade

Esta clase funciona como punto de entrada principal para las operaciones del sistema. En lugar de que los controladores tengan que comunicarse directamente con muchas clases del modelo, lo hacen a través de la fachada.

Algunos métodos de la fachada son:

- iniciarSesion.
- crearCategoria.
- crearPregunta.
- crearCuestionario.
- obtenerCuestionariosDisponibles.
- realizarCuestionario.
- consultarHistorial.
- consultarEstadisticas.
- generarRetroalimentacionIA.

La ventaja de utilizar Facade es que el sistema queda más ordenado. Los controladores no necesitan conocer todos los detalles internos de las clases del modelo, sino que acceden a las funcionalidades mediante una clase intermediaria.

---

## 3. Relación entre MVC y Facade

La comunicación general del sistema se organiza de la siguiente manera:

Vista → Controlador → PlataformaEducativaFacade → Modelo / Servicios / IA

Esto significa que:

1. El usuario interactúa con una vista.
2. La vista comunica la acción al controlador.
3. El controlador llama a PlataformaEducativaFacade.
4. La fachada coordina las clases necesarias del modelo, servicios o IA.

Ejemplo aplicado al caso de realizar un cuestionario:

RealizarCuestionarioVista → TestController → PlataformaEducativaFacade → Cuestionario / Resultado / HistorialResultados / AsistenteIA

Esta organización permite separar responsabilidades y facilita futuras modificaciones.

---

## 4. Incorporación de inteligencia artificial

El proyecto incorpora una clase llamada AsistenteIA. Esta clase se incluye pensando en una futura etapa del proyecto, especialmente relacionada con la materia Inteligencia Artificial.

La clase AsistenteIA tendrá como objetivo generar retroalimentación personalizada a partir de los resultados obtenidos por los estudiantes.

Algunos métodos previstos son:

- generarRetroalimentacionPersonalizada.
- sugerirCategoriaDeRefuerzo.

Por ejemplo, si un estudiante responde incorrectamente varias preguntas de una misma categoría, el sistema podría sugerirle repasar ese tema.

En esta primera etapa, la inteligencia artificial queda planteada en el diseño. Su implementación completa podrá realizarse más adelante.

---

## 5. Organización propuesta de paquetes

La estructura propuesta del proyecto es la siguiente:

src/
  modelo/
  vista/
  controlador/
  servicio/
  ia/

### modelo

Contiene las clases principales del dominio del problema.

### vista

Contiene las ventanas gráficas desarrolladas con Java Swing.

### controlador

Contiene las clases que reciben las acciones del usuario y coordinan las operaciones.

### servicio

Contiene clases que prestan funcionalidades generales, como la fachada y la gestión de archivos.

### ia

Contiene las clases relacionadas con inteligencia artificial.

---

## 6. Justificación general

Se eligió MVC porque ayuda a separar la interfaz gráfica, la lógica de control y las clases del modelo. Esto permite que el sistema sea más claro y fácil de mantener.

Se eligió Facade porque permite simplificar la comunicación entre los controladores y las clases internas del sistema. Esto evita que cada controlador dependa directamente de muchas clases.

La incorporación de AsistenteIA permite dejar preparado el sistema para futuras ampliaciones relacionadas con inteligencia artificial. De esta forma, el proyecto no solo resuelve los requisitos actuales, sino que también queda abierto a nuevas funcionalidades.

---

## 7. Estado actual del diseño

Actualmente el proyecto se encuentra en etapa de documentación y diseño. Se cuenta con:

- Especificación de requisitos.
- Casos de uso.
- Diagrama de clases.
- Organización mediante MVC.
- Incorporación del patrón Facade.
- Proyección de una funcionalidad asistida por IA.

La implementación en Java se realizará en etapas posteriores.
