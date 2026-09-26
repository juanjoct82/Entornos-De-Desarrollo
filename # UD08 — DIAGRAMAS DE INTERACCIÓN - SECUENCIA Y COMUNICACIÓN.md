# UD08 — DIAGRAMAS DE INTERACCIÓN: SECUENCIA Y COMUNICACIÓN

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 7 periodos lectivos  
**Resultado de Aprendizaje:** RA6  
**Práctica evaluable:** P08.1  
**Instrumento:** I-RA6-02  

**Herramienta CASE:** Umbrello UML Modeller 26.08.1  
**Diagramas principales:** secuencia y comunicación/colaboración

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

En UD07 aprendimos a responder preguntas como:

```text
¿Qué funciones ofrece el sistema?
→ casos de uso

¿Qué pasos sigue un proceso?
→ actividades

¿Qué estados atraviesa un objeto?
→ estados
```

Todavía falta otra pregunta fundamental:

# ¿CÓMO COLABORAN LOS OBJETOS PARA REALIZAR UNA OPERACIÓN?

Por ejemplo:

```text
Usuario
↓
ControladorReserva
↓
ServicioReserva
↓
RepositorioReserva
↓
ServicioNotificacion
```

Queremos conocer:

```text
quién envía un mensaje

a quién

en qué orden

qué operación solicita

qué respuesta recibe.
```

Eso es el objeto de los:

# DIAGRAMAS DE INTERACCIÓN.

---

# 2. Resultado de Aprendizaje

## RA6

**Genera diagramas de comportamiento valorando su importancia en el desarrollo de aplicaciones y empleando herramientas específicas.**

---

# 3. Criterios de evaluación de UD08

En esta unidad se evalúan exclusivamente:

## RA6.c

**Se han interpretado diagramas de interacción.**

## RA6.d

**Se han elaborado diagramas de interacción sencillos.**

Son los dos criterios oficiales que completan RA6.

---

# 4. Situación respecto a UD07

Ya han sido evaluados:

```text
RA6.a
RA6.b
RA6.e
RA6.f
RA6.g
RA6.h
```

Por tanto:

# NO SE RECALIFICAN EN UD08.

---

# 5. ¿Qué aprenderemos?

Al terminar la unidad deberás poder:

- explicar qué es una interacción;
- diferenciar clase y objeto;
- identificar participantes;
- comprender una línea de vida;
- interpretar mensajes;
- reconocer orden temporal;
- diferenciar mensajes síncronos y asíncronos a nivel introductorio;
- interpretar retornos cuando sean relevantes;
- reconocer activaciones;
- interpretar creación y destrucción cuando aparezcan;
- comprender fragmentos sencillos `alt`, `opt` y `loop`;
- leer un diagrama de secuencia;
- transformar un escenario textual en una interacción;
- elaborar un diagrama de secuencia sencillo;
- comprender la perspectiva de comunicación;
- relacionar secuencia y comunicación;
- interpretar numeración de mensajes;
- elaborar un diagrama de comunicación sencillo;
- seleccionar cuál de las dos vistas resulta más útil según la información que se quiera destacar.

---

# 6. Utilidad profesional

Imaginemos este requisito:

> Un profesor reserva un aula. El sistema comprueba disponibilidad, registra la reserva y envía una confirmación.

Un diagrama de actividad puede mostrar:

```text
comprobar
↓
registrar
↓
confirmar
```

Pero no responde claramente:

```text
¿Qué objeto comprueba?

¿Quién registra?

¿Quién llama al repositorio?

¿Quién solicita el envío?

¿En qué orden se intercambian
los mensajes?
```

Para eso utilizamos:

# DIAGRAMAS DE INTERACCIÓN.

---

# 7. ¿Qué es una interacción?

Una interacción representa:

```text
varios participantes
+
mensajes intercambiados
+
colaboración para conseguir
un comportamiento.
```

Los participantes suelen ser:

```text
objetos

instancias

componentes conceptuales

actores
```

según el nivel del modelo.

---

# 8. CONOCIMIENTO AUXILIAR NO EVALUADO

Los conceptos:

```text
clase

objeto

instancia
```

fueron trabajados evaluativamente en:

```text
RA5
UD06.
```

Aquí los reutilizamos únicamente porque los diagramas de interacción muestran:

```text
objetos/participantes colaborando.
```

# RA5 NO SE RECALIFICA.

---

# 9. Dos diagramas complementarios

Trabajaremos:

```text
DIAGRAMA DE SECUENCIA
```

y:

```text
DIAGRAMA DE COMUNICACIÓN
```

Umbrello mantiene para el segundo la denominación:

```text
Collaboration Diagram
```

en parte de su interfaz y documentación.

La documentación actual explica que ambos representan interacciones similares, pero el diagrama de secuencia enfatiza el **orden temporal**, mientras que el de colaboración/comunicación enfatiza las **relaciones entre objetos y su topología**.

---

# 10. Terminología adoptada

En el material utilizaremos:

# DIAGRAMA DE COMUNICACIÓN

y añadiremos:

```text
Collaboration Diagram
(en Umbrello)
```

cuando hagamos referencia a la herramienta.

---

# 11. Diagrama de secuencia

Un diagrama de secuencia muestra:

```text
participantes

líneas de vida

mensajes

orden temporal
```

de una interacción concreta.

Umbrello lo describe precisamente como un diagrama que muestra el intercambio de mensajes entre objetos y destaca el orden en el que se producen.

---

# 12. Ejemplo inicial

Escenario:

> Un cliente consulta el precio de una reserva.

Podemos representar:

```text
Cliente
   |
   | consultarPrecio()
   v
Controlador
   |
   | calcularPrecio()
   v
Servicio
```

Pero un diagrama de secuencia añade una dimensión fundamental:

# EL TIEMPO.

---

# 13. Eje temporal

En un diagrama de secuencia:

```text
ARRIBA
→ antes

ABAJO
→ después
```

Por tanto:

```text
mensaje situado arriba
```

ocurre antes que:

```text
mensaje situado abajo.
```

---

# 14. Participante

Un participante representa uno de los elementos que intervienen en la interacción.

Ejemplo:

```text
cliente : Cliente

controlador : ControladorReserva

servicio : ServicioReserva
```

---

# 15. Notación objeto : clase

Podemos utilizar:

```text
reserva : Reserva
```

donde:

```text
reserva
→ nombre del objeto

Reserva
→ clase/tipo
```

También puede aparecer:

```text
: Reserva
```

cuando el nombre concreto del objeto no resulta relevante.

---

# 16. Línea de vida

La línea de vida representa:

```text
existencia del participante
durante la interacción.
```

Conceptualmente:

```text
┌─────────────────┐
│ servicio        │
└────────┬────────┘
         │
         │
         │
         │
         │
```

Umbrello muestra los objetos en la parte superior y una línea vertical discontinua descendente que representa su línea de vida.

---

# 17. Mensaje

Un mensaje representa una comunicación entre participantes.

Ejemplo:

```text
controlador
    |
    | crearReserva(datos)
    v
servicio
```

Debe nombrarse preferentemente mediante:

```text
una operación

o

una intención clara.
```

---

# 18. Mensajes demasiado vagos

Evita:

```text
hacer()

procesar()

cosa()

llamar()
```

si existe un nombre más significativo:

```text
comprobarDisponibilidad()

crearReserva()

guardar()

enviarConfirmacion()
```

---

# 19. Mensaje síncrono

En una llamada síncrona:

```text
el emisor
espera la finalización
de la operación
```

antes de continuar normalmente su flujo.

Ejemplo:

```text
Controlador
    |
    | calcularPrecio()
    v
Servicio
```

La documentación de Umbrello diferencia expresamente mensajes síncronos y asíncronos.

---

# 20. Mensaje asíncrono

En una comunicación asíncrona:

```text
el emisor
no necesita esperar
a que termine completamente
el receptor
```

para continuar.

Ejemplo conceptual:

```text
ServicioReserva
        |
        | publicarEvento()
        v
BusEventos
```

---

# 21. No usar asincronía gratuitamente

No debemos utilizar:

```text
mensaje asíncrono
```

solo porque:

```text
la flecha sea diferente
y parezca más avanzada.
```

Debemos poder justificar:

> El emisor puede continuar sin esperar la finalización de la operación.

---

# 22. Mensaje de retorno

Cuando sea útil podemos representar:

```text
resultado
```

que vuelve al emisor.

Ejemplo:

```text
Servicio
   |
   | disponibilidad
   v
Controlador
```

No es necesario dibujar:

```text
todos los retornos triviales
```

si saturan el modelo.

---

# 23. Activación

Una activación representa de forma aproximada:

```text
el periodo durante el cual
un participante ejecuta
una operación.
```

Visualmente suele mostrarse como:

```text
un rectángulo estrecho
sobre la línea de vida.
```

---

# 24. CAPTURA UD08-01 — Sequence Diagram

Debe mostrar en Umbrello:

```text
New
→ Sequence Diagram
```

y permitir reconocer:

```text
objeto

línea de vida

mensaje.
```

---

# 25. Primer ejemplo completo

Escenario:

> El usuario solicita ver sus reservas.

Participantes:

```text
usuario

controlador

servicio

repositorio
```

Interacción:

```text
Usuario
   |
   | consultarReservas()
   v
Controlador
   |
   | obtenerReservas(usuarioId)
   v
Servicio
   |
   | buscarPorUsuario(usuarioId)
   v
Repositorio
   |
   | listaReservas
   v
Servicio
   |
   | listaReservas
   v
Controlador
   |
   | mostrarReservas
   v
Usuario
```

---

# 26. Cómo interpretar un diagrama de secuencia

## Paso 1

Identifica:

```text
escenario.
```

## Paso 2

Localiza:

```text
participantes.
```

## Paso 3

Lee mensajes:

```text
de arriba hacia abajo.
```

## Paso 4

Para cada mensaje pregunta:

```text
¿quién lo envía?

¿quién lo recibe?

¿qué solicita?
```

## Paso 5

Reconstruye:

```text
el comportamiento completo
en lenguaje natural.
```

---

# 27. Actividad A08.1 — Lee una secuencia

El profesor proporciona un diagrama de:

# CAMBIO DE CONTRASEÑA

Participantes:

```text
usuario

controlador

servicioUsuarios

repositorio
```

Debes explicar:

- orden de mensajes;
- responsabilidad de cada participante;
- qué información se solicita;
- dónde se comprueba el usuario;
- dónde se guarda la nueva contraseña;
- qué respuesta vuelve al actor.

---

# 28. Orden temporal

Supongamos:

```text
1. buscarUsuario()

2. validarPasswordActual()

3. guardarPasswordNueva()
```

No podemos invertir arbitrariamente:

```text
3
↓
1
↓
2
```

porque:

```text
la interacción
tiene significado temporal.
```

---

# 29. Autollamada

Un objeto puede enviarse conceptualmente:

```text
un mensaje a sí mismo.
```

Ejemplo:

```text
ServicioReserva
     |
     | calcularDuracion()
     └────────────┐
                  |
                  └→ mismo objeto
```

No debemos abusar de las autollamadas para mostrar:

```text
cada línea de código.
```

---

# 30. Creación de objetos

En algunos escenarios un mensaje provoca:

```text
la creación
de un nuevo objeto.
```

Ejemplo:

```text
Servicio
   |
   | crear(...)
   v
Reserva
```

La línea de vida del objeto puede comenzar:

```text
en el momento
de su creación.
```

---

# 31. Destrucción

También puede representarse el final de la vida de un objeto cuando resulta relevante.

En aplicaciones de gestión sencillas:

```text
no será un requisito habitual
de nuestras prácticas.
```

---

# 32. Fragmentos combinados

Una interacción puede contener:

```text
condiciones

alternativas

repeticiones.
```

En UML podemos utilizar fragmentos como:

```text
alt

opt

loop
```

En esta unidad trabajaremos estos tres de forma sencilla.

---

# 33. `alt`

Representa:

```text
caminos alternativos
```

según condiciones.

Ejemplo:

```text
alt

[pago aceptado]
    crearEntrada()

[pago rechazado]
    mostrarError()
```

---

# 34. `alt` y actividad

En un diagrama de actividad utilizamos:

```text
decisión + guardas.
```

En una interacción podemos utilizar:

```text
fragmento alt.
```

Representan perspectivas diferentes.

# RA6.e/f NO SE RECALIFICAN.

---

# 35. `opt`

Representa:

```text
comportamiento opcional
```

que ocurre si se cumple una condición.

Ejemplo:

```text
opt [cupón válido]

aplicarDescuento()
```

---

# 36. `loop`

Representa:

```text
repetición.
```

Ejemplo:

```text
loop [por cada línea]

calcularSubtotal()
```

---

# 37. No convertir el diagrama en pseudocódigo

Un diagrama de secuencia no debería intentar representar:

```text
cada variable

cada asignación

cada incremento

cada línea Java
```

Debe conservar un nivel de abstracción útil.

---

# 38. CAPTURA UD08-02 — Mensajes

Debe mostrar:

```text
mensaje síncrono

retorno

activación
```

en un ejemplo sencillo.

---

# 39. CAPTURA UD08-03 — Fragmento alternativo

Debe mostrar un ejemplo:

```text
alt
```

con dos guardas claramente identificadas.

---

# 40. Caso guiado — Reserva de aula

Escenario:

> Un profesor solicita reservar un aula. El sistema comprueba disponibilidad. Si está disponible, crea y guarda la reserva y envía una confirmación.

Participantes:

```text
profesor

controlador

servicioReserva

repositorioReserva

notificador
```

---

# 41. Secuencia principal

```text
Profesor
   |
   | reservar(datos)
   v
Controlador
   |
   | crearReserva(datos)
   v
ServicioReserva
   |
   | existeSolapamiento(datos)
   v
RepositorioReserva
```

---

# 42. Respuesta

```text
RepositorioReserva
   |
   | false
   v
ServicioReserva
```

Después:

```text
ServicioReserva
   |
   | guardar(reserva)
   v
RepositorioReserva
```

y:

```text
ServicioReserva
   |
   | enviarConfirmacion(reserva)
   v
Notificador
```

---

# 43. Alternativa

Si:

```text
[hay solapamiento]
```

entonces:

```text
ServicioReserva
→ Controlador
→ Profesor
```

debe indicar:

```text
reserva no disponible.
```

---

# 44. Actividad A08.2 — Completa la reserva

Construye un diagrama de secuencia para el caso anterior.

Debe contener:

```text
5 participantes

consulta de disponibilidad

alt

creación/guardado

notificación

resultado.
```

---

# 45. Responsabilidades

Una ventaja de estos diagramas es detectar:

```text
responsabilidades mal asignadas.
```

Ejemplo sospechoso:

```text
Usuario
→ Repositorio
```

directamente en una arquitectura donde debería existir:

```text
Controlador
→ Servicio
→ Repositorio.
```

El diagrama puede ayudarnos a discutir diseño.

---

# 46. CONOCIMIENTO AUXILIAR NO EVALUADO

La calidad arquitectónica detallada pertenece a otros aprendizajes y módulos.

En UD08:

```text
NO calificaremos
patrones arquitectónicos
```

de forma independiente.

Lo que evaluamos es:

```text
interpretar y construir
la interacción.
```

---

# 47. Diagrama de comunicación

El segundo tipo será:

# DIAGRAMA DE COMUNICACIÓN

En Umbrello:

```text
Collaboration Diagram.
```

Muestra:

```text
objetos

enlaces entre ellos

mensajes

orden mediante numeración.
```

La documentación de Umbrello explica que esta vista enfatiza las relaciones/topología entre los objetos más que la evolución temporal visual.

---

# 48. Misma interacción, distinta perspectiva

Secuencia:

```text
A
|
| 1
v
B
|
| 2
v
C
```

Comunicación:

```text
[A] -------- [B] -------- [C]

 A → B : 1: mensaje1()

 B → C : 2: mensaje2()
```

---

# 49. Diferencia principal

## Secuencia

Destaca:

# CUÁNDO Y EN QUÉ ORDEN.

## Comunicación

Destaca:

# QUIÉN ESTÁ CONECTADO CON QUIÉN.

---

# 50. Objetos en comunicación

Los participantes se representan como objetos.

Ejemplo:

```text
controlador : ControladorReserva

servicio : ServicioReserva

repo : RepositorioReserva
```

---

# 51. Enlaces

Una línea entre objetos representa:

```text
un canal lógico
de comunicación/relación
para la interacción.
```

Sobre ese enlace aparecen mensajes.

---

# 52. Numeración

Como no tenemos un eje vertical de tiempo tan evidente, utilizamos numeración:

```text
1:

2:

3:
```

Ejemplo:

```text
1: crearReserva()

2: comprobarDisponibilidad()

3: guardar()
```

---

# 53. Numeración jerárquica

También puede aparecer:

```text
1

1.1

1.2

2
```

para expresar mensajes anidados.

Ejemplo:

```text
1: procesarReserva()

1.1: comprobar()

1.2: guardar()

2: confirmar()
```

---

# 54. Interpretar comunicación

Procedimiento:

## Paso 1

Identifica:

```text
participantes.
```

## Paso 2

Observa:

```text
enlaces.
```

## Paso 3

Ordena:

```text
mensajes por número.
```

## Paso 4

Reconstruye:

```text
la interacción.
```

---

# 55. CAPTURA UD08-04 — Collaboration Diagram

Debe mostrar:

```text
New
→ Collaboration Diagram
```

en Umbrello.

En la leyenda del material figurará:

```text
Diagrama de comunicación
(Collaboration Diagram en Umbrello)
```

---

# 56. CAPTURA UD08-05 — Mensajes numerados

Debe mostrar:

```text
1:
1.1:
2:
```

o una secuencia equivalente.

---

# 57. Actividad A08.3 — Interpreta comunicación

El profesor proporciona un diagrama de comunicación para:

# ALTA DE USUARIO

Debes reconstruir:

```text
orden de mensajes

participantes

responsabilidades

resultado final.
```

Después responde:

> ¿Qué resulta más fácil observar aquí que en un diagrama de secuencia?

---

# 58. Conversión conceptual

Una misma interacción:

```text
Usuario
→ Controlador
→ Servicio
→ Repositorio
```

puede expresarse:

```text
como secuencia
```

o:

```text
como comunicación.
```

La información básica puede ser muy similar.

Lo que cambia es:

# EL ÉNFASIS VISUAL.

---

# 59. Actividad A08.4 — Dos vistas

Partiendo de:

```text
Registrar incidencia
```

crea:

1. un diagrama de secuencia;
2. un diagrama de comunicación.

Participantes mínimos:

```text
usuario

controlador

servicio

repositorio
```

Después explica:

```text
qué información se percibe
más rápidamente
en cada vista.
```

---

# 60. Secuencia no significa actividad

Error frecuente:

> Ambos tienen flechas y orden, así que son lo mismo.

No.

## Actividad

Representa:

```text
flujo de trabajo/acciones.
```

## Secuencia

Representa:

```text
mensajes entre participantes
ordenados temporalmente.
```

---

# 61. Comunicación no significa clases

Un diagrama de comunicación:

```text
NO
```

es simplemente:

```text
un diagrama de clases
con números.
```

Las líneas representan:

```text
participación en la interacción
```

y los elementos principales son:

```text
objetos/participantes
+
mensajes.
```

---

# 62. Buenas prácticas — participantes

Utiliza únicamente:

```text
participantes relevantes
para el escenario.
```

No añadas:

```text
toda la aplicación
```

en cada interacción.

---

# 63. Buenas prácticas — nombres de mensajes

Preferir:

```text
crearReserva()

buscarDisponibles()

guardar()

enviarConfirmacion()
```

frente a:

```text
hacer()

ejecutar()

gestionar().
```

---

# 64. Buenas prácticas — nivel de detalle

Mantén un nivel coherente.

Mala mezcla:

```text
crearReserva()

incrementar i

abrirSocketTCP()

sumar 1

guardar()
```

si el objetivo es representar:

```text
la interacción funcional
de alto nivel.
```

---

# 65. Buenas prácticas — orden

Antes de dibujar:

```text
escribe los mensajes
en una lista ordenada.
```

Ejemplo:

```text
1. Actor solicita operación.

2. Controlador delega.

3. Servicio consulta repositorio.

4. Repositorio responde.

5. Servicio procesa.

6. Resultado vuelve.
```

---

# 66. Buenas prácticas — escenario concreto

No intentes modelar:

```text
“Toda la aplicación”
```

en un único diagrama de secuencia.

Modela:

```text
Comprar entrada

Registrar préstamo

Cancelar reserva

Crear usuario
```

como escenarios concretos.

---

# 67. Error frecuente — participantes como métodos

Incorrecto:

```text
guardar()

validar()

calcular()
```

como participantes.

Son normalmente:

```text
mensajes/operaciones.
```

---

# 68. Error frecuente — mensajes sin receptor

Cada mensaje debe permitir interpretar:

```text
quién lo envía

y

quién lo recibe.
```

---

# 69. Error frecuente — orden contradictorio

Ejemplo:

```text
1. guardarReserva()

2. comprobarDisponibilidad()
```

cuando el requisito exige comprobar antes de guardar.

---

# 70. Error frecuente — retorno como nueva operación

No confundir:

```text
listaReservas
```

devuelta por un método con:

```text
una nueva petición
del receptor.
```

---

# 71. Error frecuente — demasiados retornos

No es obligatorio dibujar:

```text
return
```

después de:

```text
cada mensaje
```

si no aporta claridad.

---

# 72. Error frecuente — `alt` sin condiciones

Incorrecto:

```text
alt

opción 1

opción 2
```

Mejor:

```text
[disponible]

[no disponible]
```

---

# 73. Error frecuente — `loop` para cualquier secuencia repetida

Solo utilízalo si existe:

```text
repetición real
```

en el escenario.

---

# 74. Error frecuente — comunicación sin numeración

Si todos los mensajes aparecen:

```text
sin orden
```

puede ser imposible reconstruir correctamente la interacción.

---

# 75. Error frecuente — confundir interfaz con actor

Un:

```text
ControladorReserva
```

puede ser participante interno.

Un:

```text
Profesor
```

puede actuar como actor externo.

No son la misma categoría conceptual.

---

# 76. Caso profesional — Miralmonte AulaTech

El Colegio Miralmonte utiliza una aplicación para préstamo de material tecnológico.

Escenario:

> Un profesor solicita un portátil. El sistema comprueba disponibilidad. Si existe una unidad disponible, crea un préstamo, marca el dispositivo como no disponible y envía confirmación. Si no hay unidades disponibles, informa al profesor.

---

# 77. Participantes candidatos

```text
profesor

controladorPrestamo

servicioPrestamo

repositorioMaterial

repositorioPrestamo

notificador
```

---

# 78. Secuencia esperable

```text
Profesor
↓ solicitarPortatil()

ControladorPrestamo
↓ crearPrestamo()

ServicioPrestamo
↓ buscarDisponible()

RepositorioMaterial
↑ dispositivo / null
```

---

# 79. Alternativa

```text
alt

[disponible]
    guardarPrestamo()
    marcarNoDisponible()
    enviarConfirmacion()

[no disponible]
    devolverSinDisponibilidad()
```

---

# 80. Comunicación equivalente

```text
[Profesor]
      |
1: solicitarPortatil()
      |
[Controlador]
      |
2: crearPrestamo()
      |
[Servicio]
     / \
    /   \
3: buscar()  4: guardar()
  /           \
[RepoMaterial] [RepoPrestamo]
```

La numeración exacta dependerá del modelo final.

---

# 81. Actividad A08.5 — Preparación de AulaTech

Antes de abrir Umbrello, crea una tabla:

| Nº | Emisor | Receptor | Mensaje | Condición |
|---:|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |

Después transforma la tabla en diagrama.

---

# 82. PRÁCTICA EVALUABLE P08.1

# INTERACCIONES EN MIRALMONTE AULATECH

**Modalidad:** individual  
**RA:** RA6  
**CE evaluados:** RA6.c y RA6.d  
**Instrumento:** I-RA6-02  
**Herramienta:** Umbrello 26.08.1

---

# 83. Parte A — Interpretación de secuencia

El profesor proporciona un diagrama desconocido:

# CARTAGOSHOP — CONFIRMAR PEDIDO

Participantes aproximados:

```text
cliente

controlador

servicioPedido

repositorioPedido

servicioPago
```

El alumno no recibe previamente la descripción textual completa.

---

# 84. Tarea A1

Identifica:

```text
participantes

líneas de vida

mensajes

orden temporal

retornos

fragmentos
```

que aparezcan.

---

# 85. Tarea A2

Reconstruye el escenario en lenguaje natural.

Debes explicar:

```text
qué solicita el actor

cómo progresa la interacción

qué participante realiza
cada responsabilidad

qué resultado obtiene.
```

---

# 86. Tarea A3

Si existe:

```text
alt

opt

loop
```

explica exactamente:

```text
qué condición

o repetición
```

representa.

---

# 87. Parte B — Interpretación de comunicación

Se proporciona:

# CARTAGOSHOP — ACTUALIZAR STOCK

en forma de diagrama de comunicación.

Debes:

```text
ordenar los mensajes

identificar participantes

reconstruir el escenario

explicar la topología.
```

---

# 88. Evidencias RA6.c

```text
E-RA6.c-01
Interpretación de secuencia.

E-RA6.c-02
Reconstrucción textual
del escenario.

E-RA6.c-03
Interpretación de mensajes
y fragmentos.

E-RA6.c-04
Interpretación de comunicación.

E-RA6.c-05
Reconstrucción por numeración.

E-RA6.c-06
Comparación de ambas perspectivas.
```

---

# 89. Parte C — Escenario evaluable AulaTech

Debes modelar:

# SOLICITAR PORTÁTIL

Requisitos:

```text
El profesor solicita
un portátil para una fecha.

El controlador recibe
la petición.

El servicio consulta
si existe un portátil disponible.

Si no existe:
se devuelve un resultado
de no disponibilidad.

Si existe:
se crea un préstamo.

El préstamo se almacena.

El portátil queda marcado
como no disponible.

Se envía una confirmación
al profesor.

El resultado de la operación
vuelve al actor.
```

---

# 90. Tarea C1 — Participantes

Define al menos:

```text
profesor

controladorPrestamo

servicioPrestamo

repositorioMaterial

repositorioPrestamo

notificador
```

Puedes simplificar alguno si justificas correctamente el nivel del modelo.

---

# 91. Tarea C2 — Tabla previa

Antes del diagrama entrega:

| Nº | Emisor | Receptor | Mensaje |
|---:|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

Debe coincidir con:

```text
el diagrama final.
```

---

# 92. Tarea C3 — Diagrama de secuencia

Debe incluir:

```text
participantes

líneas de vida

mensajes ordenados

alt

[disponible]

[no disponible]

resultado final.
```

---

# 93. Mensajes orientativos

Pueden existir:

```text
solicitarPrestamo(datos)

crearPrestamo(datos)

buscarDisponible(fecha)

guardar(prestamo)

marcarNoDisponible(id)

enviarConfirmacion(...)

resultado
```

Los nombres exactos pueden variar si son técnicamente coherentes.

---

# 94. Tarea C4 — Diagrama de comunicación

Representa:

```text
EL MISMO ESCENARIO
```

mediante:

```text
Communication Diagram
(Collaboration Diagram en Umbrello)
```

Debe conservar:

```text
mismos participantes esenciales

mismos mensajes esenciales

misma lógica
```

pero expresados desde la nueva perspectiva.

---

# 95. Numeración

La numeración debe permitir reconstruir inequívocamente:

```text
el orden.
```

Por ejemplo:

```text
1:
2:
2.1:
2.2:
3:
```

si la estructura de mensajes lo requiere.

---

# 96. Tarea C5 — Comparación

Explica:

### Secuencia

¿Qué información se reconoce más fácilmente?

### Comunicación

¿Qué información se reconoce más fácilmente?

### Conclusión

¿Por qué ambos diagramas son:

```text
complementarios
```

y no simplemente duplicados?

---

# 97. Tarea C6 — Revisión crítica

Identifica:

```text
una posible mejora
```

en tu propio modelo.

Ejemplo:

```text
mensaje demasiado genérico

participante innecesario

retorno redundante

numeración mejorable

nivel de detalle desigual.
```

Corrige el modelo antes de entregar.

---

# 98. Evidencias RA6.d

```text
E-RA6.d-01
Tabla de interacción previa.

E-RA6.d-02
Diagrama de secuencia AulaTech.

E-RA6.d-03
Participantes/líneas de vida.

E-RA6.d-04
Mensajes y orden temporal.

E-RA6.d-05
Fragmento alt correcto.

E-RA6.d-06
Diagrama de comunicación.

E-RA6.d-07
Numeración de mensajes.

E-RA6.d-08
Comparación y revisión crítica.
```

---

# 99. Entregables

```text
P08.1_Apellidos_Nombre.pdf
```

más:

```text
P08.1_Apellidos_Nombre.xmi
```

o archivo nativo de Umbrello.

El PDF debe contener:

1. interpretación del diagrama de secuencia;
2. reconstrucción textual;
3. interpretación del diagrama de comunicación;
4. tabla de mensajes de AulaTech;
5. diagrama de secuencia;
6. diagrama de comunicación;
7. comparación de perspectivas;
8. revisión final.

---

# 100. Instrumento I-RA6-02

**Instrumento:** I-RA6-02  
**RA:** RA6  
**CE:** RA6.c y RA6.d  
**Actividad:** P08.1  
**Tipo:** interpretación y modelado UML individual

Cada CE obtiene:

```text
NOTA 0,00–10,00
```

por separado.

---

# 101. Rúbrica definitiva I-RA6-02

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA6.c** | Interpreta diagramas de interacción y reconstruye correctamente el escenario representado | Confunde participantes, mensajes u orden y no consigue explicar la interacción | Identifica participantes y mensajes principales, aunque presenta imprecisiones en orden, retornos o condiciones | Interpreta correctamente diagramas de secuencia y comunicación, reconstruyendo participantes, mensajes, orden, condiciones y resultado | Además relaciona ambas perspectivas, interpreta con precisión fragmentos/numeración, detecta incoherencias y justifica responsabilidades | **100 % del CE** |
| **RA6.d** | Elabora diagramas de interacción sencillos coherentes con un escenario | El diagrama no representa correctamente el escenario o mezcla elementos sin semántica clara | Construye una interacción básica con participantes y mensajes, aunque presenta errores de orden o notación | Elabora correctamente secuencia y comunicación con participantes, mensajes, orden, alternativa y numeración coherentes | Además mantiene un nivel de abstracción especialmente adecuado, elimina ruido, justifica participantes y produce dos vistas plenamente consistentes entre sí | **100 % del CE** |

---

# 102. Nota informativa de P08.1

Puede mostrarse:

```text
(
 RA6.c
+RA6.d
) / 2
```

pero el registro conserva:

```text
RA6.c

RA6.d
```

de forma independiente.

---

# 103. Temporalización definitiva

| Sesión | Contenido | Actividad |
|---:|---|---|
| 1 | Interacciones, participantes y líneas de vida | A08.1 |
| 2 | Mensajes, retornos, activaciones y orden temporal | ejercicios guiados |
| 3 | `alt`, `opt`, `loop` y construcción de secuencias | A08.2 |
| 4 | Diagramas de comunicación y numeración | A08.3 |
| 5 | Secuencia vs comunicación | A08.4–5 |
| 6 | P08.1 — interpretación y diseño | I-RA6-02 |
| 7 | P08.1 — AulaTech, revisión y cierre | I-RA6-02 |

**Total: 7 periodos.**

---

# 104. Ejercicios de consolidación

1. ¿Qué representa un diagrama de interacción?
2. ¿Qué es un participante?
3. ¿Qué representa una línea de vida?
4. ¿Cómo se interpreta el eje temporal?
5. ¿Qué es un mensaje?
6. ¿Qué diferencia básica existe entre mensaje síncrono y asíncrono?
7. ¿Es obligatorio mostrar todos los retornos?
8. ¿Qué representa una activación?
9. ¿Qué es una autollamada?
10. ¿Qué representa `alt`?
11. ¿Qué representa `opt`?
12. ¿Qué representa `loop`?
13. Diferencia actividad y secuencia.
14. ¿Qué enfatiza un diagrama de secuencia?
15. ¿Qué enfatiza un diagrama de comunicación?
16. ¿Por qué se numeran mensajes en comunicación?
17. ¿Qué significa `1.2`?
18. ¿Deben tener secuencia y comunicación participantes compatibles si representan el mismo escenario?
19. ¿Qué nombre utiliza Umbrello para el diagrama de comunicación?
20. ¿Qué CE evalúa interpretación?
21. ¿Qué CE evalúa elaboración?
22. ¿Se vuelve a evaluar RA6.a en esta unidad?
23. ¿Se evalúa arquitectura software?
24. ¿Se evalúa Programación?
25. ¿Por qué conviene preparar primero una tabla de mensajes?

---

# 105. Actividad de ampliación

Investiga los fragmentos:

```text
par

break

critical
```

en diagramas de secuencia.

Explica:

```text
qué tipo de interacción
podrían representar.
```

**No evaluable.**

---

# 106. Resumen

Un diagrama de interacción representa:

```text
participantes
+
mensajes
+
colaboración.
```

## Secuencia

Destaca:

```text
ORDEN TEMPORAL.
```

## Comunicación

Destaca:

```text
RELACIONES ENTRE PARTICIPANTES.
```

Secuencia utiliza especialmente:

```text
líneas de vida

posición vertical

mensajes.
```

Comunicación utiliza:

```text
objetos

enlaces

mensajes numerados.
```

Ambos pueden representar:

# LA MISMA INTERACCIÓN DESDE PERSPECTIVAS DIFERENTES.

---

# 107. Glosario

**Activación:** intervalo visual durante el cual un participante ejecuta una operación.

**Alt:** fragmento que representa alternativas condicionadas.

**Collaboration Diagram:** denominación utilizada por Umbrello para el diagrama de comunicación.

**Comunicación:** diagrama de interacción que enfatiza relaciones entre participantes y mensajes numerados.

**Fragmento combinado:** región utilizada para representar estructuras como alternativas o repeticiones.

**Interacción:** colaboración entre participantes mediante intercambio de mensajes.

**Línea de vida:** representación de la existencia de un participante durante la interacción.

**Loop:** fragmento que representa repetición.

**Mensaje:** comunicación dirigida de un participante hacia otro.

**Mensaje asíncrono:** mensaje en el que el emisor no necesita esperar la finalización del receptor para continuar.

**Mensaje síncrono:** llamada en la que el flujo espera normalmente la finalización de la operación invocada.

**Opt:** fragmento de comportamiento opcional.

**Participante:** elemento que interviene en una interacción.

**Retorno:** información devuelta como resultado de una llamada.

**Secuencia:** diagrama que enfatiza el orden temporal de mensajes.

---

# 108. Autoevaluación

### 1

Un diagrama de secuencia enfatiza:

A. estructura de clases  
B. orden temporal de mensajes  
C. estados  
D. requisitos

### 2

Una línea de vida pertenece principalmente a:

A. diagrama de secuencia  
B. diagrama de clases  
C. caso de uso  
D. actividad

### 3

El tiempo en secuencia se interpreta normalmente:

A. de abajo hacia arriba  
B. de arriba hacia abajo  
C. de derecha a izquierda  
D. no existe orden

### 4

`alt` representa:

A. alternativas  
B. herencia  
C. composición  
D. una clase

### 5

`loop` representa:

A. repetición  
B. caso de uso  
C. estado inicial  
D. actor

### 6

Un diagrama de comunicación enfatiza:

A. topología y relaciones entre participantes  
B. clases abstractas  
C. actividades paralelas  
D. estados

### 7

La numeración de mensajes en comunicación permite:

A. reconstruir su orden  
B. definir multiplicidad  
C. definir herencia  
D. crear commits

### 8

Umbrello denomina actualmente a este tipo en su interfaz/documentación:

A. Collaboration Diagram  
B. Deployment Diagram  
C. Package Diagram  
D. Git Diagram

### 9

RA6.c evalúa:

A. interpretación de interacciones  
B. creación de clases  
C. Git  
D. testing

### 10

RA6.d evalúa:

A. elaboración de interacciones sencillas  
B. diagramas de clases  
C. estados únicamente  
D. compilación

---

# 109. Soluciones de autoevaluación

```text
1 → B
2 → A
3 → B
4 → A
5 → A
6 → A
7 → A
8 → A
9 → A
10 → A
```

---

# PARTE B — MATERIAL DEL PROFESOR

# 110. Finalidad docente

La unidad debe conseguir que el alumno deje de interpretar un diagrama de secuencia como:

```text
“un dibujo con flechas”
```

y empiece a leer:

```text
PARTICIPANTE
↓
MENSAJE
↓
RESPONSABILIDAD
↓
ORDEN
↓
RESULTADO.
```

---

# 111. RA6.c necesita diagramas ajenos

Para demostrar:

```text
INTERPRETACIÓN
```

el alumnado debe recibir:

```text
diagramas no elaborados
previamente por él.
```

Por eso P08.1 incluye:

```text
CartagoShop
```

como escenario de interpretación.

---

# 112. RA6.d necesita transformación

Para demostrar:

```text
ELABORACIÓN
```

el alumno recibe:

```text
requisito textual
```

y debe convertirlo:

```text
requisito
↓
tabla de mensajes
↓
secuencia
↓
comunicación.
```

---

# 113. Secuencia y comunicación

No exigir:

```text
dos diseños funcionalmente distintos.
```

Precisamente interesa que el alumno comprenda que:

```text
mismo escenario
→ dos perspectivas.
```

---

# 114. Terminología

Utilizar en clase:

```text
Diagrama de comunicación
(Collaboration Diagram en Umbrello)
```

porque la documentación actual de KDE conserva `Collaboration Diagram`, mientras que la ficha actual de la aplicación incluye “comunicación” entre los diagramas soportados.

---

# 115. Umbrello 26.08.1

La versión de referencia sigue siendo:

```text
26.08.1
```

publicada el:

```text
10/09/2026.
```

La aplicación actual soporta:

```text
Sequence Diagram

Communication/Collaboration Diagram
```

además de los otros diagramas utilizados en el curso.

---

# 116. Mensajes síncronos/asíncronos

No convertir este apartado en:

```text
concurrencia avanzada.
```

El nivel esperado:

## Síncrono

```text
llamo
y necesito esperar
el resultado/fin.
```

## Asíncrono

```text
envío la comunicación
sin bloquear necesariamente
el flujo hasta su finalización.
```

---

# 117. Fragmentos

Para primero:

```text
alt

opt

loop
```

son suficientes.

No introducir como requisito:

```text
par

break

critical

neg

assert
```

aunque puedan aparecer en ampliación.

---

# 118. AulaTech — solución orientativa

Participantes:

```text
profesor : Profesor

controlador : ControladorPrestamo

servicio : ServicioPrestamo

repoMaterial : RepositorioMaterial

repoPrestamo : RepositorioPrestamo

notificador : Notificador
```

---

# 119. Secuencia orientativa

```text
Profesor
  |
  | solicitarPortatil(fecha)
  v
Controlador
  |
  | crearPrestamo(profesor, fecha)
  v
Servicio
  |
  | buscarDisponible(fecha)
  v
RepoMaterial
```

Retorno:

```text
portatil / null
```

---

# 120. Rama disponible

```text
[portatil != null]

Servicio
→ RepoPrestamo:
guardar(prestamo)

Servicio
→ RepoMaterial:
marcarNoDisponible(portatil)

Servicio
→ Notificador:
enviarConfirmacion(...)

Servicio
→ Controlador:
prestamoCreado

Controlador
→ Profesor:
confirmación
```

---

# 121. Rama no disponible

```text
[portatil == null]

Servicio
→ Controlador:
sinDisponibilidad

Controlador
→ Profesor:
informarNoDisponible
```

---

# 122. ¿Debe crear `Prestamo` explícitamente?

Puede aparecer:

```text
create
```

como mensaje de creación o quedar implícito dentro de:

```text
crearPrestamo()
```

según el nivel de detalle.

No convertirlo en requisito oculto.

---

# 123. ¿Debe ser Notificador asíncrono?

No necesariamente.

Puede modelarse:

```text
síncrono
```

en una solución básica.

Una solución avanzada podría justificar:

```text
asíncrono
```

si el escenario establece que:

```text
el préstamo no debe esperar
a la entrega efectiva del email.
```

No exigirlo sin requisito.

---

# 124. Calidad de mensajes

Adecuado:

```text
buscarDisponible(fecha)
```

Más débil:

```text
buscar()
```

Insuficiente si todo el diagrama utiliza:

```text
hacer()

procesar()

ejecutar()
```

sin significado.

---

# 125. Responsabilidades

No debe calificarse arquitectura con criterios de otro módulo.

Pero sí puede considerarse dentro de la coherencia de RA6.d si:

```text
un mensaje resulta imposible
o contradice el propio escenario.
```

Ejemplo:

```text
Profesor
→ base de datos física
```

cuando el propio modelo declara un controlador y servicio y después no los utiliza.

---

# 126. Fragmento `alt`

La práctica debe incluirlo deliberadamente para asegurar que todos los alumnos producen evidencia comparable de:

```text
interacción condicionada.
```

---

# 127. Comunicación

El diagrama debe conservar:

```text
mensajes esenciales
```

del de secuencia.

No es necesario trasladar:

```text
cada retorno trivial
```

si dificulta la lectura.

---

# 128. Numeración

Aceptar:

```text
1, 2, 3, 4...
```

o numeración jerárquica:

```text
1

1.1

1.2

2
```

si el orden se entiende correctamente.

La documentación de Umbrello confirma que en los diagramas de colaboración los mensajes muestran nombre, parámetros y secuencia.

---

# 129. Error grave de RA6.c

Alumno:

```text
describe únicamente
qué clases aparecen
```

pero no:

```text
qué mensajes intercambian

ni en qué orden.
```

Eso no demuestra interpretación de interacción.

---

# 130. Error grave de RA6.d

Alumno:

```text
crea un diagrama visualmente correcto
```

pero:

```text
los mensajes contradicen
el requisito.
```

La notación correcta no compensa:

```text
la interacción incorrecta.
```

---

# 131. Capturas previstas

```text
CAPTURA UD08-01
Nuevo Sequence Diagram

CAPTURA UD08-02
Mensajes y activaciones

CAPTURA UD08-03
Fragmento alt

CAPTURA UD08-04
Collaboration Diagram

CAPTURA UD08-05
Mensajes numerados

CAPTURA UD08-06
AulaTech — secuencia

CAPTURA UD08-07
AulaTech — comunicación
```

---

# 132. Medidas de apoyo

Puede proporcionarse:

```text
tabla Emisor/Receptor/Mensaje

participantes ya identificados

lista desordenada de mensajes

diagrama parcialmente completado

ejemplo guiado anterior.
```

No proporcionar:

```text
orden final
de AulaTech

ni

los dos diagramas
resueltos.
```

---

# 133. Plantilla de preparación

| Nº | Emisor | Mensaje | Receptor | Condición |
|---:|---|---|---|---|
| | | | | |

El alumnado con dificultades puede completar primero esta tabla.

---

# 134. Plantilla de interpretación

| Orden | Quién envía | Quién recibe | Qué solicita | Resultado |
|---:|---|---|---|---|
| | | | | |

Ayuda especialmente con RA6.c.

---

# 135. Recuperación

Instrumento:

# IR-RA6-01

Bloques de UD08:

```text
RA6.c

RA6.d
```

Ejemplo:

```text
RA6.c = 7

RA6.d = 3
```

Si RA6 queda no superado y solo necesita nueva evidencia de:

```text
RA6.d
```

se asignará:

```text
únicamente
bloque RA6.d.
```

---

# 136. Trazabilidad UD08

| RA | CE | Contenido | Actividades | Instrumento | Evidencias |
|---|---|---|---|---|---|
| RA6 | c | interpretación de secuencia y comunicación | A08.1, A08.3 | P08.1 / I-RA6-02 | E-RA6.c-01/06 |
| RA6 | d | elaboración de secuencia y comunicación | A08.2, A08.4–5 | P08.1 / I-RA6-02 | E-RA6.d-01/08 |

---

# 137. Situación completa de RA6

Tras UD07:

```text
a ✔
b ✔
e ✔
f ✔
g ✔
h ✔
```

Tras UD08:

```text
c ✔
d ✔
```

Resultado:

# RA6 COMPLETAMENTE CUBIERTO.

---

# 138. Cálculo definitivo de RA6

Cada CE tiene el mismo peso:

```text
1 / 8
```

Por tanto:

```text
RA6 =
(
 RA6.a
+RA6.b
+RA6.c
+RA6.d
+RA6.e
+RA6.f
+RA6.g
+RA6.h
) / 8
```

---

# 139. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA6

**CE evaluados:**

```text
RA6.c
RA6.d
```

### ¿Se utiliza RA5?

Sí, como conocimiento auxiliar:

```text
clase

objeto

instancia.
```

# NO SE RECALIFICA.

### ¿Se utiliza RA6.a?

Se recuerda que secuencia y comunicación son diagramas de comportamiento/interacción.

# NO SE RECALIFICA.

### ¿Se evalúan casos de uso?

# NO.

### ¿Se evalúan actividades?

# NO.

### ¿Se evalúan estados?

# NO.

### ¿Se evalúa programación?

# NO.

El código, si se muestra, sirve únicamente para:

```text
relacionar conceptualmente
mensajes y operaciones.
```

### ¿Se evalúa arquitectura?

# NO COMO RA INDEPENDIENTE.

### ¿Algún instrumento mezcla RA?

# NO.

```text
I-RA6-02
→ exclusivamente RA6.
```

---

# 140. Checklist final UD08

```text
☑ 7 periodos.

☑ RA6 único.

☑ RA6.c oficial.

☑ RA6.d oficial.

☑ Resto de RA6 no recalificado.

☑ Concepto de interacción.

☑ Participantes.

☑ Objetos.

☑ Líneas de vida.

☑ Eje temporal.

☑ Mensajes.

☑ Mensajes síncronos.

☑ Mensajes asíncronos.

☑ Retornos.

☑ Activaciones.

☑ Autollamadas.

☑ Creación contextualizada.

☑ alt.

☑ opt.

☑ loop.

☑ Interpretación de secuencia.

☑ Elaboración de secuencia.

☑ Comunicación/Collaboration.

☑ Enlaces.

☑ Numeración.

☑ Numeración jerárquica.

☑ Interpretación de comunicación.

☑ Elaboración de comunicación.

☑ Secuencia vs comunicación.

☑ Actividad ≠ secuencia.

☑ Comunicación ≠ clase.

☑ Umbrello 26.08.1.

☑ Terminología actual normalizada.

☑ Miralmonte AulaTech.

☑ CartagoShop para interpretación.

☑ P08.1.

☑ I-RA6-02.

☑ RA6.c nota 0–10.

☑ RA6.d nota 0–10.

☑ Rúbrica armonizada.

☑ Evidencias codificadas.

☑ 7 capturas previstas.

☑ Consolidación.

☑ Ampliación.

☑ Autoevaluación.

☑ Resumen.

☑ Glosario.

☑ Material profesor.

☑ Recuperación modular.

☑ Trazabilidad completa.

☑ Aislamiento superado.

☑ RA6 cerrado.
```

# UD08 — VERSIÓN MAESTRA DEFINITIVA