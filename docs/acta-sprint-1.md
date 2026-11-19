# Acta de Sprint Review y Sprint Retrospective, Sprint 1

Proyecto: VetCare, sistema de gestión de atención veterinaria

Curso: Administración de Proyectos Informáticos, III-26, SC-02

Sprint: Sprint 1, del 22/10/2026 al 04/11/2026

Fecha de la sesión: 18/11/2026 (simulación en clase, semana 9)

Sprint Goal: Que un propietario pueda crear su cuenta, iniciar sesión y registrar y administrar sus mascotas, con acceso diferenciado entre propietarios, médicos veterinarios y administrador.

> Esta acta corresponde a la simulación de los eventos de cierre del Sprint 1 hecha en clase. Los resultados del Incremento, las horas del burndown y la retroalimentación son el escenario que el equipo usó en la simulación. Si el avance real difiere, se actualizan las tablas de las secciones 2 y 3.

## Participantes y roles

| Integrante | Rol en la sesión |
| --- | --- |
| Jose Pablo Soto Quesada | Product Owner + Developer. Además representa a la clínica (I1, I2 e I3), según el plan de contingencia del riesgo R4. |
| Maikel Chaves Salas | Scrum Master + Developer. Facilita ambos eventos y toma notas. |
| Edgar Eliam Araya Alvarado | Developer. Presenta las pruebas funcionales y de permisos. |
| Deiver Cubero Molina | Profesor (I6), como interesado invitado a la Review. |

---

## Parte 1: Sprint Review

Duración: 45 minutos, dentro del máximo de 2 horas que corresponde a un Sprint de dos semanas (la Guía de Scrum fija 4 horas para un Sprint de un mes). La Guía de Scrum (Schwaber y Sutherland, 2020) define la Review como el evento en que se inspecciona el Incremento y se adapta el Product Backlog.

Fue una sesión de trabajo y no una presentación de diapositivas: se usó el sistema con datos ficticios frente a los interesados, se recogieron sus comentarios y los cambios se anotaron en el Product Backlog durante la misma sesión.

### 1. Incremento frente a la Definición de Terminado

Se revisó cada historia con los cinco puntos de la Definición de Terminado: (1) criterios de aceptación, (2) código en la rama principal, (3) probada por otro integrante con datos ficticios, incluidas las pruebas de permisos, (4) sin errores conocidos y (5) documentada.

| Historia | Puntos | 1 | 2 | 3 | 4 | 5 | Resultado |
| --- | :---: | :---: | :---: | :---: | :---: | :---: | --- |
| HU-01 Registro de propietarios | 3 | Sí | Sí | Sí | Sí | Sí | Terminada |
| HU-02 Inicio y cierre de sesión con acceso por rol | 3 | Sí | Sí | Sí | Sí | Sí | Terminada |
| HU-03 Registro de mascotas del propietario | 5 | Sí | Sí | Sí | Sí | Sí | Terminada |
| HU-04 Consulta y edición de mascotas | 3 | No | Sí | No | No | Sí | No terminada |
| HU-05 Registro de médicos veterinarios | 2 | Sí | Sí | Sí | Sí | Sí | Terminada |

La HU-04 no se presenta como terminada. En la prueba de permisos (tarea T-13), al cambiar el identificador de la mascota en la dirección, un propietario pudo abrir el formulario de edición de una mascota ajena. Falla el quinto criterio de aceptación. Es el disparador del riesgo R3, así que la historia volvió a En progreso, como indica su plan de contingencia.

### 2. Métricas del Sprint

| Métrica | Planificado | Real |
| --- | :---: | :---: |
| Historias | 5 | 4 terminadas |
| Puntos de historia | 16 | 13 |
| Tareas terminadas | 16 | 14 (87,5 %) |
| Horas pendientes al cierre | 0 | 4 |

Las tareas pendientes son T-12 (corrección del control de acceso en la edición) y T-13 (repetir la prueba de la HU-04). La velocidad real del Sprint 1 es de 13 puntos, dentro del rango de 12 a 18 que se había supuesto, pero por debajo de los 15 planificados.

#### Burndown registrado

| Registro | Día del Sprint | Horas pendientes ideales | Horas pendientes reales |
| --- | :---: | :---: | :---: |
| Inicio | 0 | 47 | 47 |
| Daily 1 | 2 | 38 | 42 |
| Daily 2 | 4 | 28 | 33 |
| Daily 3 | 6 | 19 | 22 |
| Daily 4 | 8 | 9 | 12 |
| Cierre | 10 | 0 | 4 |

El avance real quedó por encima del ideal desde la Daily 1. El atraso inicial vino de las tareas T-01 y T-02 (modelo de datos y configuración del proyecto), que tomaron más horas de las estimadas porque la estimación no consideró que el framework era nuevo para dos integrantes (riesgo R5).

#### Impedimentos registrados

| Fecha | Impedimento | Responsable | Acción | Estado |
| --- | --- | --- | --- | --- |
| 24/10/2026 | La configuración del proyecto y la base de datos tomó más tiempo del estimado por falta de experiencia con el framework. | Maikel Chaves | Jose Pablo hizo una sesión corta de apoyo y trabajó T-02 en pareja con Maikel. | Resuelto |
| 03/11/2026 | La prueba de permisos de la HU-04 permitió abrir una mascota ajena. | Eliam Araya | La HU-04 vuelve a En progreso y se corrige la validación en el servidor. | Abierto |

### 3. Demostración y retroalimentación

Se demostró con datos ficticios el flujo completo de las historias terminadas: un visitante se registra como propietario, inicia sesión, registra dos mascotas y ve que cada una tiene su propia información; un propietario no puede entrar a funciones de veterinario ni de administrador; el administrador registra a un veterinario y este entra con su rol.

| Quién | Comentario | Decisión |
| --- | --- | --- |
| Product Owner, como representante de la clínica | En el registro de mascotas conviene una lista de especies (perro, gato, otra) en lugar de texto libre, para evitar datos escritos de formas distintas. | Se agrega como criterio de aceptación de la HU-04, porque reutiliza el formulario de la HU-03. |
| Product Owner, como representante de la clínica | El administrador necesita ver la lista de veterinarios registrados para comprobar que no se duplicaron. | Se crea la HU-14 en el Product Backlog, con prioridad P2. |
| Profesor | La prueba de permisos debe hacerse en todas las historias y no solo al final. | Se atiende con la acción A1 de la Retrospective. |

### 4. Adaptación del Product Backlog

| Cambio | Detalle |
| --- | --- |
| HU-04 vuelve al Product Backlog | Mantiene sus 3 puntos y la prioridad P1. Se agrega el criterio de la lista de especies. Va primera en el siguiente Sprint, porque las citas dependen de que el propietario administre sus mascotas de forma segura. |
| Nueva HU-14 | "Como administrador, quiero ver la lista de médicos veterinarios registrados, para comprobar que no estén duplicados." Prioridad P2, 1 punto por estimar en planning poker. |
| Ajuste de capacidad | Con la HU-04 se suman 3 puntos al trabajo pendiente. Como la velocidad real fue de 13, el Product Owner decide que, si el burndown vuelve a quedar por encima del ideal en dos registros, la HU-07 (P2) pasa al Sprint siguiente, según el plan de contingencia de R5. |
| Velocidad para planificar | Se usa 13 puntos, la velocidad real, en lugar del supuesto inicial de 15. Si se mantiene, se confirma la necesidad del Sprint 4 (03/12/2026 al 16/12/2026). |

Los comentarios de la clínica no se tratan como un fracaso del Sprint. Son el producto ajustándose a lo que necesita el usuario, y por eso entraron al backlog en la misma Review.

### 5. Decisiones sobre prioridades, fechas y presupuesto

| Tema | Decisión | Quién decide |
| --- | --- | --- |
| Prioridades | La HU-04 va primero en el siguiente Sprint. La HU-14 queda como P2, después de las historias de citas. | Product Owner |
| Fechas | Se mantiene el plan de tres Sprints. El Sprint 4 (03/12/2026 al 16/12/2026) queda como reserva si la velocidad sigue en 13 puntos. La fecha final del curso no cambia. | Product Owner, con el visto bueno del profesor |
| Presupuesto | El proyecto no tiene presupuesto en dinero; el recurso es el tiempo del equipo. Se mantienen 47 horas por Sprint entre los tres integrantes y los servicios en planes gratuitos. | Equipo, con el Product Owner |

### 6. Resumen: qué se mostró, qué se aceptó y qué cambia

| Qué se mostró | Qué se aceptó | Qué cambia |
| --- | --- | --- |
| Registro de propietarios, inicio y cierre de sesión con acceso por rol, registro de varias mascotas y registro de veterinarios por el administrador. | HU-01, HU-02, HU-03 y HU-05 (13 puntos), porque cumplen la Definición de Terminado. | La HU-04 vuelve al backlog con el criterio nuevo de la lista de especies. |
| La edición de mascotas y el resultado de su prueba de permisos. | La HU-04 no se acepta. | Se crea la HU-14 y la planificación usa una velocidad de 13 puntos. |

---

## Parte 2: Sprint Retrospective

Duración: 45 minutos, dentro del máximo de 1,5 horas que corresponde a un Sprint de dos semanas (la Guía de Scrum fija 3 horas para un Sprint de un mes). Formato: Empezar, Dejar de, Continuar (Start, Stop, Continue). Cada integrante escribió sus notas por separado durante 5 minutos, luego se agruparon y se votaron las más importantes.

Se inspeccionó cómo trabajó el equipo en cuatro aspectos: personas, interacciones, procesos y herramientas. Al inicio se acordó que la Retrospective es un espacio seguro: se discute el proceso y no se buscan culpables, por eso las notas hablan de prácticas y no de personas.

### Notas del equipo

| Empezar | Dejar de | Continuar |
| --- | --- | --- |
| Hacer las pruebas de permisos en cada historia apenas pasa a En pruebas. | Dejar las pruebas de permisos para los últimos días del Sprint. | Probar cada historia con un integrante distinto de quien la desarrolló. |
| Registrar las horas pendientes del burndown en todas las Daily, sin saltarse ninguna. | Subir cambios directo a la rama principal sin que otro integrante los revise. | Trabajar en pareja las tareas difíciles con Jose Pablo. |
| Pedir ayuda en la Daily cuando una tarea pasa de sus horas estimadas. | Estimar las tareas de configuración sin considerar que el framework es nuevo para dos integrantes. | Mover las tarjetas en Jira en cuanto cambian de estado. |

### Lo que funcionó

- El trabajo en pareja en T-02 resolvió el atraso de la primera semana.
- La regla de que solo quien prueba mueve la tarjeta a Terminado detectó el error de la HU-04 antes de la Review.
- El límite WIP de "En pruebas" obligó a probar antes de empezar tareas nuevas.

### Lo que no funcionó

- La prueba de permisos de la HU-04 se hizo el último día, sin tiempo para corregir.
- El burndown quedó por encima del ideal en dos registros seguidos y el equipo no lo conversó con el Product Owner, como pedía el mecanismo de seguimiento.
- Las tareas de configuración se subestimaron.

### Acciones de mejora

| ID | Acción | Dueño | Fecha | Cómo se verifica |
| --- | --- | --- | --- | --- |
| A1 | Aplicar la lista de pruebas de permisos por rol (M-04) a cada historia apenas pasa a En pruebas, y no al final del Sprint. | Eliam Araya | 20/11/2026 | La lista está en el repositorio y cada historia del Sprint tiene su resultado registrado antes de pasar a Terminado. |
| A2 | Registrar el burndown en cada Daily y, si queda por encima del ideal en dos registros seguidos, avisar al Product Owner ese mismo día. | Maikel Chaves | 19/11/2026 | La tabla de burndown no tiene registros vacíos y, si se activa la alerta, queda anotada en el registro de impedimentos. |
| A3 | Configurar la rama principal para que solo reciba cambios por pull request revisado por otro integrante (M-07). | Maikel Chaves | 21/11/2026 | La regla está activa en GitHub y los cambios del siguiente Sprint aparecen como pull requests aprobados. |

Las tres acciones tienen dueño, fecha y una forma de verificarlas. Entran al Sprint Backlog del siguiente Sprint como tareas, con su responsable en Jira, y se revisan al inicio de la siguiente Retrospective.

| Aspecto inspeccionado | Hallazgo | Acción relacionada |
| --- | --- | --- |
| Personas | La experiencia con el framework está concentrada en un integrante. | Se mantiene el trabajo en pareja (Continuar). |
| Interacciones | El atraso del burndown no se comunicó a tiempo al Product Owner. | A2 |
| Procesos | Las pruebas de permisos se dejaban para el final del Sprint. | A1 |
| Herramientas | La rama principal acepta cambios sin revisión. | A3 |

---

## Cierre

| Elemento | Resultado |
| --- | --- |
| Sprint Goal | Cumplido en parte: el registro, el inicio de sesión, el acceso por rol y el registro de mascotas funcionan; la edición segura de mascotas queda pendiente. |
| Velocidad | 13 puntos |
| Historias que pasan al siguiente Sprint | HU-04 |
| Historias nuevas | HU-14 |
| Acciones de mejora | A1, A2 y A3 |

Redactó: Maikel Chaves Salas, Scrum Master.

Revisó: Jose Pablo Soto Quesada, Product Owner.
