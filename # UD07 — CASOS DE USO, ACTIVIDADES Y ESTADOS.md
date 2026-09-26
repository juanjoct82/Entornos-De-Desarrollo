# UD07 — CASOS DE USO, ACTIVIDADES Y ESTADOS

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 7 periodos lectivos  
**Resultado de Aprendizaje:** RA6  
**Práctica evaluable:** P07.1  
**Instrumento:** I-RA6-01  

**Herramienta CASE:** Umbrello UML Modeller 26.08.1  
**Estándar conceptual:** UML  
**Diagramas principales:** casos de uso, actividad y estados

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

En UD06 hemos modelado:

```text
qué elementos existen
en un sistema
```

mediante diagramas de clases.

Por ejemplo:

```text
Cliente

Entrada

Evento

Reserva
```

Pero todavía no hemos explicado:

```text
¿Qué puede hacer un usuario?

¿Qué pasos sigue un proceso?

¿Qué decisiones aparecen?

¿Qué estados atraviesa un objeto?

¿Qué eventos provocan cambios?
```

Ahora cambiaremos de perspectiva.

Pasaremos de:

```text
ESTRUCTURA
```

a:

# COMPORTAMIENTO.

---

# 2. Resultado de Aprendizaje

## RA6

**Genera diagramas de comportamiento valorando su importancia en el desarrollo de aplicaciones y empleando herramientas específicas.**

---

# 3. Criterios de evaluación trabajados

En UD07 se evalúan exclusivamente:

## RA6.a

**Se han identificado los distintos tipos de diagramas de comportamiento.**

## RA6.b

**Se ha reconocido el significado de los diagramas de casos de uso.**

## RA6.e

**Se ha interpretado el significado de diagramas de actividades.**

## RA6.f

**Se han elaborado diagramas de actividades sencillos.**

## RA6.g

**Se han interpretado diagramas de estados.**

## RA6.h

**Se han planteado diagramas de estados sencillos.**


---

# 4. Criterios reservados a UD08

No se evaluarán en esta unidad:

```text
RA6.c
→ interpretar diagramas de interacción

RA6.d
→ elaborar diagramas de interacción sencillos
```

Estos criterios pertenecen íntegramente a:

# UD08.

---

# 5. ¿Qué aprenderemos?

Al finalizar la unidad deberás poder:

- distinguir estructura y comportamiento;
- identificar los principales diagramas de comportamiento utilizados en este módulo;
- explicar para qué sirve un diagrama de casos de uso;
- identificar actores;
- identificar casos de uso;
- reconocer la frontera del sistema;
- interpretar asociaciones actor–caso;
- comprender relaciones `include`;
- comprender relaciones `extend`;
- reconocer generalizaciones cuando proceda;
- evitar utilizar casos de uso para describir algoritmos internos;
- interpretar diagramas de actividad;
- reconocer actividad inicial y final;
- interpretar acciones;
- interpretar decisiones y guardas;
- interpretar bifurcaciones y uniones;
- reconocer actividades paralelas;
- elaborar diagramas de actividad sencillos;
- interpretar diagramas de estados;
- distinguir estado, evento y transición;
- reconocer estado inicial y final;
- comprender guardas y acciones asociadas a transiciones;
- elaborar máquinas de estados sencillas;
- seleccionar el tipo de diagrama adecuado según la información que queremos representar.

---

# 6. Utilidad profesional

Imaginemos una aplicación para venta de entradas.

Con un diagrama de clases podemos representar:

```text
Cliente

Evento

Entrada

Pago
```

Pero necesitamos otras perspectivas.

## Casos de uso

```text
¿Qué puede hacer el cliente?
```

## Actividades

```text
¿Qué pasos sigue la compra?
```

## Estados

```text
¿Qué estados puede atravesar una entrada?
```

Son preguntas distintas.

Por tanto:

# NECESITAMOS DIAGRAMAS DISTINTOS.

---

# 7. Estructura vs comportamiento

## Diagramas estructurales

Responden principalmente:

```text
¿Qué elementos forman
el sistema?
```

Ejemplo:

```text
diagrama de clases.
```

## Diagramas de comportamiento

Responden principalmente:

```text
¿Qué sucede?

¿Qué acciones ocurren?

¿Cómo cambia el sistema?
```

---

# 8. CONOCIMIENTO AUXILIAR NO EVALUADO EN ESTA UNIDAD

El diagrama de clases pertenece a:

```text
RA5
```

y ya fue evaluado en UD06.

En UD07 podremos mencionar clases u objetos para contextualizar procesos y estados, pero:

# RA5 NO SE RECALIFICA.

---

# 9. Tipos de diagramas de comportamiento

Dentro del alcance de este módulo trabajaremos especialmente:

```text
casos de uso

actividades

estados

secuencia

comunicación
```

Umbrello soporta precisamente estos tipos, aunque su interfaz denomina al diagrama de comunicación como **Collaboration Diagram**.

---

# 10. Mapa conceptual de RA6

```text
COMPORTAMIENTO
      │
      ├── ¿qué puede hacer un actor?
      │      ↓
      │   CASOS DE USO
      │
      ├── ¿qué pasos sigue un proceso?
      │      ↓
      │   ACTIVIDADES
      │
      ├── ¿cómo cambia un objeto?
      │      ↓
      │   ESTADOS
      │
      └── ¿cómo colaboran objetos
          mediante mensajes?
             ↓
        INTERACCIONES
        UD08
```

---

# 11. Actividad A07.1 — Elige diagrama

Relaciona cada necesidad con el diagrama más apropiado:

```text
1. Mostrar funciones que puede realizar
   un cliente.

2. Representar el proceso completo
   de devolución de una compra.

3. Mostrar cómo pasa una incidencia
   de abierta a cerrada.

4. Representar mensajes entre
   ServicioPedido y Repositorio.

5. Mostrar las clases Cliente,
   Pedido y Producto.
```

Justifica.

---

# 12. Diagrama de casos de uso

Un diagrama de casos de uso representa principalmente:

```text
ACTORES

FUNCIONES DEL SISTEMA

RELACIONES
```

y ayuda a comprender:

# QUÉ DEBE HACER EL SISTEMA DESDE EL PUNTO DE VISTA EXTERNO.

La documentación de Umbrello recalca expresamente que estos diagramas sirven para mostrar funciones y comunicación con usuarios, pero no las interioridades ni cómo se implementa el sistema.

---

# 13. Actor

Un actor representa:

```text
un rol externo
```

que interactúa con el sistema.

Puede ser:

```text
una persona

otro sistema

un dispositivo

un servicio externo
```

si actúa externamente respecto al sistema que modelamos.

---

# 14. Actor ≠ persona concreta

Incorrecto:

```text
Juan José García
```

como actor si lo que representa realmente es:

```text
Cliente
```

El actor representa:

# UN ROL.

---

# 15. Ejemplos de actores

Sistema de venta de entradas:

```text
Cliente

Administrador

Pasarela de pago
```

Sistema escolar:

```text
Alumno

Profesor

Secretaría
```

---

# 16. Caso de uso

Un caso de uso representa una función del sistema que produce un resultado útil para un actor.

Ejemplos:

```text
Comprar entrada

Consultar evento

Cancelar compra

Gestionar evento
```

---

# 17. Nombres de casos de uso

Es recomendable utilizar:

```text
VERBO + OBJETO
```

Ejemplos:

```text
Comprar entrada

Consultar disponibilidad

Registrar usuario

Cancelar reserva
```

Evita:

```text
Entrada

Pantalla compra

Botón pagar

Base de datos
```

cuando queremos representar funcionalidad.

---

# 18. Frontera del sistema

Podemos dibujar un rectángulo que representa:

```text
el sistema que estamos modelando
```

Dentro:

```text
casos de uso
```

Fuera:

```text
actores.
```

Ejemplo:

```text
 Cliente

    |
    v

┌──────────────────────────┐
│   CartagoTickets         │
│                          │
│  (Consultar eventos)     │
│  (Comprar entrada)       │
│                          │
└──────────────────────────┘
```

---

# 19. ¿Por qué es importante la frontera?

Porque obliga a decidir:

```text
¿Qué forma parte
del sistema?

¿Qué está fuera?
```

Ejemplo:

```text
Pasarela de pago
```

puede ser:

```text
actor externo
```

si CartagoTickets consume un servicio de pago que no controla.

---

# 20. Asociación actor–caso

Una línea entre:

```text
actor
```

y:

```text
caso de uso
```

indica participación/interacción.

Ejemplo:

```text
Cliente ───── (Comprar entrada)
```

---

# 21. No representa orden temporal

Este diagrama:

```text
Cliente ───── (Consultar evento)
Cliente ───── (Comprar entrada)
```

NO significa necesariamente:

```text
primero consultar

después comprar.
```

Para representar flujo:

# UTILIZAREMOS DIAGRAMA DE ACTIVIDADES.

---

# 22. Relación `include`

`include` representa reutilización obligatoria de comportamiento común.

Ejemplo conceptual:

```text
(Comprar entrada)
      |
      | <<include>>
      v
(Validar pago)
```

Interpretación:

```text
al ejecutar Comprar entrada,
se incorpora necesariamente
el comportamiento Validar pago
según el modelo.
```

---

# 23. ¿Cuándo usar `include`?

Puede ser útil cuando varios casos de uso comparten:

```text
un comportamiento obligatorio
y reutilizable.
```

Ejemplo:

```text
(Comprar entrada)
        \
         <<include>>
              \
           (Autenticar usuario)

(Consultar mis compras)
        /
  <<include>>
      /
(Autenticar usuario)
```

---

# 24. Error frecuente con `include`

No utilizarlo simplemente para:

```text
dividir cualquier caso
en pequeños pasos.
```

Un diagrama de casos de uso:

# NO ES UN DIAGRAMA DE ACTIVIDAD.

---

# 25. Relación `extend`

`extend` representa comportamiento adicional que puede incorporarse bajo determinadas condiciones en un punto de extensión.

Ejemplo conceptual:

```text
(Aplicar descuento)
       |
       | <<extend>>
       v
(Comprar entrada)
```

condición:

```text
[cliente tiene cupón]
```

---

# 26. `include` vs `extend`

De forma introductoria:

## `include`

```text
comportamiento reutilizado
como parte necesaria
del caso base
```

## `extend`

```text
comportamiento adicional
condicionado/opcional
respecto al caso base
```

---

# 27. No memorices solo flechas

La pregunta importante es:

```text
¿El comportamiento forma parte
siempre del caso base?

¿O aparece únicamente
bajo determinadas condiciones?
```

---

# 28. Generalización de actores

Puede ocurrir:

```text
Usuario
  ▲
  │
 ┌┴──────────┐
 │           │
Cliente   Administrador
```

si diferentes actores especializados comparten comportamiento del rol general.

No es obligatorio utilizar generalización en todo modelo.

---

# 29. Generalización de casos de uso

También puede modelarse especialización de casos de uso cuando existe una relación semántica adecuada.

En primer curso:

```text
la utilizaremos
solo cuando aporte claridad.
```

No es necesario forzarla.

---

# 30. CAPTURA UD07-01 — Use Case Diagram

Debe mostrar en Umbrello:

```text
New
→ Use Case Diagram
```

y permitir reconocer:

```text
actor

use case

system boundary.
```

---

# 31. Umbrello y casos de uso

La documentación oficial de Umbrello define los diagramas de casos de uso como una representación de actores, casos de uso y sus relaciones. También recuerda que muestran **qué** debe hacer el sistema y no **cómo** debe hacerlo.

---

# 32. Caso guiado — CartagoTickets

Requisitos iniciales:

```text
Un cliente puede consultar eventos.

Puede comprar entradas.

Puede consultar sus compras.

Puede cancelar una entrada
si todavía no ha sido validada.

Un administrador puede crear
y modificar eventos.

Una pasarela externa procesa
los pagos.
```

---

# 33. Actores candidatos

```text
Cliente

Administrador

Pasarela de pago
```

---

# 34. Casos candidatos

```text
Consultar eventos

Comprar entrada

Consultar compras

Cancelar entrada

Crear evento

Modificar evento

Procesar pago
```

---

# 35. Primer modelo

```text
Cliente ───── (Consultar eventos)

Cliente ───── (Comprar entrada)

Cliente ───── (Consultar compras)

Cliente ───── (Cancelar entrada)

Administrador ───── (Crear evento)

Administrador ───── (Modificar evento)

Pasarela pago ───── (Procesar pago)
```

---

# 36. Relación posible

Podemos modelar:

```text
(Comprar entrada)
     |
 <<include>>
     |
(Procesar pago)
```

si el procesamiento del pago es parte necesaria de la compra.

La pasarela participa en:

```text
Procesar pago.
```

---

# 37. Actividad A07.2 — Interpreta un caso de uso

Dado un diagrama proporcionado por el profesor, responde:

1. ¿Cuál es la frontera del sistema?
2. ¿Qué actores existen?
3. ¿Qué funciones puede realizar cada actor?
4. ¿Existe `include`?
5. ¿Existe `extend`?
6. ¿Qué significado tiene cada relación?
7. ¿Aparece algún detalle que no debería estar en este tipo de diagrama?

---

# 38. Actividad A07.3 — Corrige el diagrama

El profesor entrega:

```text
Cliente → (Pantalla azul)

Cliente → (Base de datos)

Cliente → (Pulsar botón)

Cliente → (Comprar)
```

Explica:

```text
qué elementos
no son buenos casos de uso

y por qué.
```

Propón una versión mejor.

---

# 39. Diagramas de actividad

Un diagrama de actividad representa:

```text
flujo de acciones
```

y puede incluir:

```text
secuencia

decisiones

condiciones

paralelismo

inicio

final.
```

Umbrello describe estos diagramas como representaciones de actividades y cambios entre actividades, incluyendo ejecución secuencial o paralela.

---

# 40. Diferencia fundamental

## Caso de uso

```text
¿Qué función ofrece
el sistema?
```

## Actividad

```text
¿Cómo fluye
un proceso?
```

---

# 41. Nodo inicial

Representa:

```text
inicio del flujo.
```

Suele mostrarse mediante un:

```text
círculo negro.
```

---

# 42. Acción / actividad

Representa un paso del proceso.

Ejemplos:

```text
Seleccionar evento

Elegir entradas

Introducir datos

Realizar pago

Emitir entrada
```

---

# 43. Flujo de control

Las flechas indican:

```text
cómo avanza
la ejecución
entre acciones.
```

Ejemplo:

```text
Seleccionar evento
        ↓
Elegir entrada
        ↓
Realizar pago
```

---

# 44. Nodo final

Representa:

```text
fin del flujo
```

o terminación del comportamiento representado, según el tipo de final utilizado.

Para esta unidad utilizaremos una representación sencilla de:

```text
final del proceso.
```

---

# 45. Decisión

Una decisión representa:

```text
una bifurcación
según una condición.
```

Ejemplo:

```text
        ¿Pago correcto?
        /            \
      sí              no
      |                |
      v                v
Emitir entrada    Mostrar error
```

---

# 46. Guardas

Las condiciones se escriben entre:

```text
[ ]
```

Ejemplo:

```text
[pago aceptado]

[pago rechazado]
```

---

# 47. Las guardas deben diferenciar caminos

Mala representación:

```text
[correcto]

[correcto]
```

Mejor:

```text
[pago aceptado]

[pago rechazado]
```

---

# 48. Merge de decisión

Después de varios caminos alternativos podemos volver a un flujo común.

Ejemplo:

```text
[pago tarjeta] ──┐
                 ├──> Registrar pago
[pago bizum] ────┘
```

---

# 49. Paralelismo

Existen procesos donde dos actividades pueden avanzar de forma concurrente o independiente.

Ejemplo tras una compra:

```text
             ┌──> Enviar email
Compra ──────┤
             └──> Actualizar estadísticas
```

---

# 50. Fork

Un **fork** divide:

```text
un flujo
```

en:

```text
varios flujos concurrentes.
```

---

# 51. Join

Un **join** sincroniza:

```text
varios flujos
```

antes de continuar.

---

# 52. Fork ≠ decisión

## Decisión

```text
se elige un camino
según condiciones.
```

## Fork

```text
se activan
varios caminos.
```

Ésta es una diferencia esencial.

---

# 53. Particiones / swimlanes

Podemos dividir el diagrama por:

```text
responsabilidades.
```

Ejemplo:

```text
CLIENTE

SISTEMA

PASARELA DE PAGO
```

Así podemos ver:

```text
quién realiza
cada acción.
```

---

# 54. CAPTURA UD07-02 — Activity Diagram

Debe mostrar:

```text
New
→ Activity Diagram
```

y reconocer:

```text
inicio

acción

decisión

flujo

final.
```

---

# 55. CAPTURA UD07-03 — Fork / Join

Debe mostrar en Umbrello un ejemplo de:

```text
bifurcación paralela

sincronización.
```

---

# 56. Caso guiado — Compra de entrada

Proceso:

```text
Inicio
↓
Consultar eventos
↓
Seleccionar evento
↓
Seleccionar entradas
↓
Introducir datos
↓
Solicitar pago
↓
¿Pago aceptado?
```

Si:

```text
sí
```

entonces:

```text
crear entrada

enviar confirmación

fin
```

Si:

```text
no
```

entonces:

```text
mostrar error

permitir reintento
o cancelar.
```

---

# 57. Diagrama conceptual

```text
●
|
v
[Seleccionar evento]
|
v
[Elegir entradas]
|
v
[Realizar pago]
|
v
   ◇ ¿aceptado?
  / \
sí   no
|     |
v     v
[Crear] [Mostrar error]
|
v
◎
```

---

# 58. Actividad A07.4 — Interpreta actividades

El profesor proporciona un diagrama de:

```text
tramitación de devolución.
```

Explica:

- inicio;
- acciones;
- decisiones;
- guardas;
- caminos posibles;
- posibles actividades paralelas;
- final.

---

# 59. Procedimiento de interpretación

## Paso 1

Localiza:

```text
inicio.
```

## Paso 2

Sigue:

```text
flujo principal.
```

## Paso 3

Identifica:

```text
decisiones.
```

## Paso 4

Lee:

```text
guardas.
```

## Paso 5

Busca:

```text
forks / joins.
```

## Paso 6

Localiza:

```text
finales.
```

## Paso 7

Reconstruye:

```text
el proceso completo
con palabras.
```

---

# 60. Actividad A07.5 — Construye actividad

Modela:

# RESERVA DE UNA PISTA DEPORTIVA

Requisitos:

```text
el usuario selecciona fecha

consulta disponibilidad

si no hay pista:
muestra aviso

si hay:
elige pista

confirma reserva

sistema registra reserva

envía confirmación
```

Incluye:

```text
inicio

acciones

decisión

guardas

final.
```

---

# 61. Actividad A07.6 — Añade paralelismo

Amplía el modelo anterior.

Después de registrar:

```text
reserva
```

el sistema debe ejecutar:

```text
enviar email

actualizar estadísticas
```

antes de finalizar.

Representa:

```text
fork

join.
```

---

# 62. Errores frecuentes en actividad

## Error 1

Usar:

```text
casos de uso
```

como si fueran acciones del flujo sin pensar en el nivel de detalle.

## Error 2

Crear una decisión:

```text
sin condiciones.
```

## Error 3

Dibujar:

```text
dos salidas
```

pero no explicar cuándo se sigue cada una.

## Error 4

Usar fork cuando solo puede ejecutarse un camino.

## Error 5

No indicar inicio o final cuando son necesarios para interpretar el proceso.

---

# 63. Diagrama de estados

Un diagrama de estados representa:

```text
los estados relevantes
que atraviesa un objeto

y

los eventos que provocan
transiciones.
```

Umbrello lo describe como un diagrama que muestra estados, cambios de estado y eventos en un objeto o parte del sistema.

---

# 64. Estado

Un estado representa una situación significativa durante la vida de un objeto.

Ejemplo:

```text
Entrada
```

podría encontrarse:

```text
Reservada

Pagada

Validada

Cancelada
```

---

# 65. No todo valor de atributo es un estado

La documentación de Umbrello recuerda que solo deben modelarse como estados aquellos cambios internos que afectan de manera significativa al comportamiento.

Ejemplo:

```text
nombreCliente = "Ana"
```

no suele justificar un estado:

```text
NombreAna.
```

---

# 66. Estado inicial

Representa:

```text
punto de comienzo
de la máquina de estados.
```

No es un estado normal del negocio.

---

# 67. Estado final

Representa:

```text
finalización
del ciclo modelado.
```

La documentación de Umbrello distingue expresamente estados inicial y final como elementos especiales.

---

# 68. Transición

Una transición conecta:

```text
estado origen
```

con:

```text
estado destino
```

como respuesta a un evento o condición.

Ejemplo:

```text
Reservada
    |
 pagar
    v
Pagada
```

---

# 69. Evento

Un evento representa algo que ocurre y puede provocar una transición.

Ejemplos:

```text
pagar

cancelar

validar

expirar
```

---

# 70. Guarda

Una transición puede ejecutarse únicamente si:

```text
se cumple una condición.
```

Ejemplo:

```text
cancelar [no validada]
```

---

# 71. Acción asociada

Una transición puede incluir una acción.

Representación conceptual:

```text
evento [guarda] / acción
```

Ejemplo:

```text
pagar [importe correcto] / emitirConfirmacion()
```

En primer curso:

```text
no será obligatorio
utilizar todas estas partes
en cada transición.
```

---

# 72. Estado vs actividad

## Estado

```text
situación estable/relevante
del objeto
```

Ejemplo:

```text
Pagada.
```

## Actividad

```text
acción o proceso
que se realiza
```

Ejemplo:

```text
Procesar pago.
```

---

# 73. Error frecuente

Modelar como estados:

```text
Pulsando botón

Escribiendo tarjeta

Consultando base de datos
```

cuando el dominio que queremos representar es:

```text
vida de una Entrada.
```

Debemos escoger estados:

```text
significativos
para el objeto.
```

---

# 74. Caso guiado — Incidencia

Una incidencia puede encontrarse:

```text
Nueva

Asignada

En resolución

Resuelta

Cerrada

Cancelada
```

---

# 75. Eventos

Ejemplos:

```text
asignar técnico

iniciar resolución

resolver

cerrar

reabrir

cancelar
```

---

# 76. Modelo conceptual

```text
●
|
v
Nueva
 |
 | asignar
 v
Asignada
 |
 | iniciar
 v
En resolución
 |
 | resolver
 v
Resuelta
 |
 | cerrar
 v
Cerrada
 |
 v
◎
```

Podemos añadir:

```text
Resuelta
   |
 reabrir
   |
   v
En resolución
```

si el requisito lo permite.

---

# 77. CAPTURA UD07-04 — State Diagram

Debe mostrar:

```text
New
→ State Diagram
```

y distinguir:

```text
estado inicial

estado

transición

estado final.
```

---

# 78. CAPTURA UD07-05 — Transición con evento

Debe mostrar una transición configurada con:

```text
evento

y, cuando proceda,
guarda.
```

---

# 79. Interpretar estados

Cuando recibas un diagrama:

## Paso 1

Pregunta:

```text
¿Qué objeto o concepto
está siendo modelado?
```

## Paso 2

Identifica:

```text
estado inicial.
```

## Paso 3

Enumera:

```text
estados posibles.
```

## Paso 4

Identifica:

```text
eventos.
```

## Paso 5

Lee:

```text
guardas.
```

## Paso 6

Busca:

```text
transiciones imposibles
o caminos de retorno.
```

## Paso 7

Identifica:

```text
estado final.
```

---

# 80. Actividad A07.7 — Interpreta estados

El profesor entrega un diagrama para:

```text
Pedido
```

con estados:

```text
Creado

Pagado

Preparado

Enviado

Entregado

Cancelado
```

Responde:

1. ¿Qué estados existen?
2. ¿Qué evento permite pasar a Pagado?
3. ¿Desde qué estados puede cancelarse?
4. ¿Puede volver de Entregado a Preparado?
5. ¿Existe algún camino imposible?
6. ¿Qué regla de negocio puede deducirse?

---

# 81. Actividad A07.8 — Crea una máquina

Modela:

# PRÉSTAMO DE MATERIAL

Estados:

```text
Solicitado

Aprobado

Entregado

Devuelto

Rechazado

Cancelado
```

Define:

```text
eventos

transiciones

al menos una guarda
si tiene sentido.
```

---

# 82. Actividad A07.9 — Detecta errores

El profesor entrega una máquina donde:

```text
Devuelto
→ Entregado

Rechazado
→ Aprobado

Estado inicial
→ todos los estados

Cancelado
→ cualquier estado
```

sin justificación.

Debes:

```text
detectar incoherencias

proponer reglas

corregir transiciones.
```

---

# 83. Elegir el diagrama adecuado

Caso:

> Necesitamos saber qué funciones puede realizar un cliente.

Usamos:

```text
CASOS DE USO.
```

---

# 84. Otro caso

> Queremos conocer todos los pasos desde que el cliente comienza el pago hasta que recibe la entrada.

Usamos:

```text
ACTIVIDAD.
```

---

# 85. Otro caso

> Queremos saber cuándo una entrada puede pasar de Reservada a Pagada o Cancelada.

Usamos:

```text
ESTADOS.
```

---

# 86. Otro caso

> Queremos saber qué mensajes intercambian ControladorCompra, ServicioPago y Repositorio.

Usaremos:

```text
DIAGRAMA DE INTERACCIÓN
```

pero se estudiará en:

# UD08.

---

# 87. Una misma funcionalidad admite varias perspectivas

Compra de entrada:

## Casos de uso

```text
Comprar entrada.
```

## Actividad

```text
pasos del proceso de compra.
```

## Estados

```text
estados de la Entrada.
```

## Interacción

```text
mensajes entre objetos
durante la compra.
```

No son diagramas duplicados.

Representan:

# INFORMACIÓN DIFERENTE.

---

# 88. Error frecuente — querer meter todo en un diagrama

Un diagrama de casos de uso con:

```text
secuencia de pasos

variables

condiciones internas

estados

mensajes técnicos
```

pierde su función.

Cada modelo debe responder:

```text
una pregunta concreta.
```

---

# 89. Buenas prácticas — casos de uso

- actores como roles;
- casos con verbos;
- evitar detalles de interfaz;
- no modelar algoritmos;
- utilizar `include`/`extend` solo cuando aportan significado;
- definir claramente la frontera del sistema.

---

# 90. Buenas prácticas — actividades

- acciones con nombres claros;
- guardas comprensibles;
- decisiones mutuamente interpretables;
- paralelismo solo cuando existe;
- flujo legible;
- nivel de detalle coherente.

---

# 91. Buenas prácticas — estados

- modelar un objeto/concepto concreto;
- estados significativos;
- eventos claros;
- evitar transiciones imposibles;
- representar reglas del ciclo de vida;
- no confundir acción con estado.

---

# 92. Caso profesional evaluable — CartagoTickets

CartagoTickets gestiona venta de entradas para eventos.

Requisitos:

```text
Un cliente puede consultar eventos.

Puede seleccionar un evento
y comprar entradas.

Para comprar debe realizarse
el pago.

Si dispone de un cupón válido
puede aplicarse un descuento.

Una entrada recién creada
queda reservada.

Cuando el pago se acepta,
queda pagada.

Una entrada pagada puede
validarse en el acceso.

Una entrada reservada o pagada
puede cancelarse mientras
no haya sido validada.

Una entrada validada
no puede cancelarse.

Tras una compra correcta,
el sistema envía confirmación
y actualiza las plazas disponibles.

Un administrador puede
crear, modificar y cancelar eventos.
```

---

# 93. Análisis previo

Tenemos diferentes preguntas.

## Funciones externas

```text
casos de uso.
```

## Flujo de compra

```text
actividad.
```

## Ciclo de vida de Entrada

```text
estados.
```

---

# 94. PRÁCTICA EVALUABLE P07.1

# MODELANDO EL COMPORTAMIENTO DE CARTAGOTICKETS

**Modalidad:** individual  
**RA:** RA6  
**CE:** RA6.a, b, e, f, g, h  
**Instrumento:** I-RA6-01  
**Herramienta:** Umbrello 26.08.1

---

# 95. Tarea A — Selección de diagramas

Para cada pregunta indica el diagrama adecuado y justifica:

1. ¿Qué puede hacer el Cliente?
2. ¿Qué pasos sigue una compra?
3. ¿Qué estados atraviesa una Entrada?
4. ¿Qué mensajes intercambiarían los objetos durante el pago?
5. ¿Qué clases forman el dominio?

Debes distinguir:

```text
RA6

RA5

y

UD08.
```

**CE:** RA6.a

---

# 96. Evidencia RA6.a

```text
E-RA6.a-01
Selección de tipo de diagrama.

E-RA6.a-02
Justificación de la finalidad
de cada tipo.
```

---

# 97. Tarea B — Interpretación de casos de uso

El profesor proporcionará un diagrama:

```text
CartagoCinema
```

diferente al caso evaluable.

Debes identificar:

```text
actores

frontera

casos

asociaciones

include

extend

generalización
si existe
```

y explicar en lenguaje natural:

```text
qué funcionalidades ofrece
el sistema a cada actor.
```

**CE:** RA6.b

---

# 98. Tarea C — Aplicación a CartagoTickets

Crea en Umbrello un diagrama que incluya como mínimo:

```text
Cliente

Administrador

Pasarela de pago
```

y funciones:

```text
Consultar eventos

Comprar entrada

Consultar compras

Cancelar entrada

Crear evento

Modificar evento

Cancelar evento

Procesar pago
```

Puedes añadir:

```text
Aplicar descuento
```

cuando lo modeles de forma coherente.

---

# 99. Nota sobre RA6.b

Aunque construyas un diagrama para demostrar comprensión:

# LO QUE SE CALIFICA EN RA6.b ES EL SIGNIFICADO Y LA CORRECTA INTERPRETACIÓN DE LOS CASOS DE USO.

No existe un CE independiente de:

```text
“crear casos de uso”
```

en el currículo de RA6.

---

# 100. Evidencias RA6.b

```text
E-RA6.b-01
Interpretación de CartagoCinema.

E-RA6.b-02
Identificación de actores/casos.

E-RA6.b-03
Interpretación de include/extend.

E-RA6.b-04
Aplicación razonada
a CartagoTickets.
```

---

# 101. Tarea D — Interpretación de actividad

El profesor proporciona un diagrama de:

```text
solicitud de devolución.
```

Debes describir:

- inicio;
- flujo principal;
- decisiones;
- guardas;
- caminos alternativos;
- fork/join si existe;
- final.

**CE:** RA6.e

---

# 102. Evidencias RA6.e

```text
E-RA6.e-01
Reconstrucción del flujo.

E-RA6.e-02
Interpretación de decisiones
y guardas.

E-RA6.e-03
Interpretación de paralelismo.
```

---

# 103. Tarea E — Diagrama de actividad

Modela en Umbrello:

# COMPRAR ENTRADA

Debe incluir:

```text
inicio

seleccionar evento

seleccionar entradas

introducir datos

comprobar/aplicar cupón
cuando proceda

solicitar pago

decisión pago aceptado/rechazado

crear/confirmar entrada

fork para:
- enviar confirmación
- actualizar plazas

join

final
```

**CE:** RA6.f

---

# 104. Requisitos de calidad RA6.f

El diagrama debe distinguir correctamente:

```text
decisión
```

de:

```text
fork.
```

Las guardas deben ser comprensibles:

```text
[pago aceptado]

[pago rechazado]
```

No:

```text
[sí]

[no]
```

si el contexto no permite comprender qué significan.

---

# 105. Evidencias RA6.f

```text
E-RA6.f-01
Diagrama de actividad completo.

E-RA6.f-02
Decisiones y guardas.

E-RA6.f-03
Fork/join correctamente aplicado.

E-RA6.f-04
Modelo editable Umbrello.
```

---

# 106. Tarea F — Interpretación de estados

El profesor entrega la máquina de estados de:

```text
PedidoOnline
```

Debes identificar:

```text
estado inicial

estados

eventos

transiciones

guardas

estado final

transiciones imposibles.
```

**CE:** RA6.g

---

# 107. Evidencias RA6.g

```text
E-RA6.g-01
Identificación de estados.

E-RA6.g-02
Interpretación de eventos
y transiciones.

E-RA6.g-03
Deducción de reglas
del ciclo de vida.
```

---

# 108. Tarea G — Máquina de estados de Entrada

Modela en Umbrello:

```text
Entrada
```

con estados como:

```text
Reservada

Pagada

Validada

Cancelada
```

y las transiciones necesarias.

Debe cumplirse:

```text
Reservada
→ Pagada

Reservada
→ Cancelada

Pagada
→ Validada

Pagada
→ Cancelada
si todavía no está validada

Validada
→ NO Cancelada
```

**CE:** RA6.h

---

# 109. Evitar contradicción redundante

No necesitas modelar:

```text
Pagada
→ Cancelada
[no validada]
```

si estar en:

```text
Pagada
```

ya implica que todavía no se ha producido:

```text
validación
```

salvo que el dominio incluya alguna variable adicional.

La guarda debe aportar:

```text
información real.
```

---

# 110. Evidencias RA6.h

```text
E-RA6.h-01
Máquina de estados de Entrada.

E-RA6.h-02
Eventos/transiciones.

E-RA6.h-03
Reglas de cancelación/validación.

E-RA6.h-04
Modelo editable Umbrello.
```

---

# 111. Tarea H — Comparación final

Explica qué información diferente aporta cada uno:

```text
casos de uso

actividad

estados
```

sobre CartagoTickets.

No se admite como respuesta:

```text
“son tres formas
de dibujar lo mismo”.
```

---

# 112. Entregables

Archivo:

```text
P07.1_Apellidos_Nombre.pdf
```

más:

```text
P07.1_Apellidos_Nombre.xmi
```

o archivo nativo utilizado por Umbrello.

El PDF debe contener:

1. selección de diagramas;
2. interpretación de casos de uso;
3. diagrama CartagoTickets;
4. interpretación de actividad;
5. actividad Comprar entrada;
6. interpretación de estados;
7. máquina de estados Entrada;
8. comparación final.

---

# 113. Instrumento I-RA6-01

**Instrumento:** I-RA6-01  
**RA:** RA6  
**CE:** a, b, e, f, g, h  
**Actividad:** P07.1  
**Tipo:** práctica individual de modelado e interpretación UML

Cada CE obtiene:

```text
NOTA 0,00–10,00
```

independientemente.

---

# 114. Rúbrica definitiva I-RA6-01

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA6.a** | Identifica el tipo de diagrama de comportamiento adecuado según la información que se necesita representar | Confunde estructura, casos de uso, actividades, estados e interacciones | Distingue los tipos principales en situaciones sencillas | Selecciona correctamente casos de uso, actividad, estados o interacción según la pregunta planteada | Además justifica límites de cada representación y distingue con precisión perspectivas complementarias del mismo escenario | **100 % del CE** |
| **RA6.b** | Reconoce e interpreta el significado de diagramas de casos de uso | Confunde actores, casos, frontera o significado de las relaciones | Reconoce actores y casos principales y explica funcionalidades básicas | Interpreta correctamente actores, casos, asociaciones, frontera, `include` y `extend` cuando aparecen | Además detecta errores de modelado, deduce responsabilidades externas y explica por qué determinados detalles no pertenecen al diagrama | **100 % del CE** |
| **RA6.e** | Interpreta el significado de diagramas de actividades | No reconstruye correctamente el proceso | Reconoce acciones y flujo principal | Interpreta inicio, acciones, decisiones, guardas, finales y paralelismo | Además reconstruye caminos alternativos, detecta incoherencias y explica correctamente fork/join frente a decisión/merge | **100 % del CE** |
| **RA6.f** | Elabora diagramas de actividades sencillos | El flujo resulta incoherente o incompleto | Representa el proceso principal con algunas imprecisiones | Modela correctamente acciones, decisiones, guardas, inicio/final y paralelismo cuando procede | Además produce un modelo especialmente claro, consistente, con nivel de detalle adecuado y sin utilizar elementos innecesarios | **100 % del CE** |
| **RA6.g** | Interpreta diagramas de estados | Confunde estados, acciones, eventos o transiciones | Reconoce los estados principales y algunas transiciones | Interpreta correctamente estado inicial/final, estados, eventos, guardas y transiciones | Además deduce reglas del ciclo de vida, identifica transiciones imposibles y detecta incoherencias | **100 % del CE** |
| **RA6.h** | Plantea diagramas de estados sencillos | La máquina de estados contradice las reglas del dominio | Representa estados y transiciones principales con algunas carencias | Modela correctamente estados relevantes, eventos, transiciones, inicio/final y guardas cuando proceden | Además representa con precisión restricciones del ciclo de vida, evita estados artificiales y justifica las decisiones de modelado | **100 % del CE** |

---

# 115. Nota informativa P07.1

Si se muestra una nota resumen:

```text
(
 RA6.a
+RA6.b
+RA6.e
+RA6.f
+RA6.g
+RA6.h
) / 6
```

pero el registro conservará:

```text
seis notas CE independientes.
```

---

# 116. Temporalización definitiva

| Sesión | Contenido | Actividad |
|---:|---|---|
| 1 | Diagramas de comportamiento y selección del tipo | A07.1 |
| 2 | Casos de uso: actores, casos, frontera, relaciones | A07.2–3 |
| 3 | Actividades: flujo, decisiones y guardas | A07.4 |
| 4 | Actividades: fork/join y construcción | A07.5–6 |
| 5 | Estados: estado, evento, transición, guarda | A07.7 |
| 6 | Elaboración y depuración de máquinas de estados | A07.8–9 |
| 7 | P07.1 — CartagoTickets | I-RA6-01 |

**Total: 7 periodos.**

---

# 117. Resumen de la unidad

## Casos de uso

```text
¿Qué funciones ofrece
el sistema a actores externos?
```

## Actividad

```text
¿Qué flujo sigue
un proceso?
```

## Estados

```text
¿Cómo evoluciona
un objeto o concepto?
```

## Interacción

```text
¿Cómo colaboran
objetos mediante mensajes?
```

se estudiará en:

```text
UD08.
```

---

# 118. Glosario

**Actor:** rol externo que interactúa con el sistema.

**Actividad:** acción o comportamiento dentro de un flujo.

**Caso de uso:** función del sistema que aporta un resultado relevante a un actor.

**Decisión:** nodo que dirige el flujo hacia caminos alternativos según condiciones.

**Diagrama de actividad:** modelo del flujo de acciones de un proceso.

**Diagrama de casos de uso:** modelo de actores y funciones externas del sistema.

**Diagrama de estados:** modelo del ciclo de vida de un objeto o concepto.

**Estado:** situación relevante de un objeto durante su vida.

**Evento:** suceso que puede provocar una transición.

**Extend:** relación de extensión condicionada de un caso de uso.

**Fork:** división de un flujo en caminos concurrentes.

**Frontera del sistema:** límite de aquello que pertenece al sistema modelado.

**Guarda:** condición que debe cumplirse para seguir un flujo o transición.

**Include:** relación mediante la que un caso de uso incorpora comportamiento común.

**Join:** sincronización de caminos concurrentes.

**Multiplicidad:** concepto estructural de UML trabajado en RA5; no se utiliza como elemento central de estos diagramas.

**Swimlane / partición:** división visual de responsabilidades en una actividad.

**Transición:** cambio entre estados.

**UML:** Unified Modeling Language.

---

# 119. Autoevaluación

### 1

¿Qué diagrama representa las funciones que puede realizar un actor?

A. Clase  
B. Casos de uso  
C. Estados  
D. Actividad

### 2

Un actor representa:

A. siempre una persona concreta  
B. un rol externo  
C. una clase Java  
D. una variable

### 3

`include` suele representar:

A. comportamiento común incorporado por el caso base  
B. una herencia Java  
C. un estado final  
D. paralelismo

### 4

`extend` suele representar:

A. comportamiento adicional condicionado  
B. una multiplicidad  
C. una clase abstracta  
D. un commit

### 5

Una decisión en un diagrama de actividad:

A. selecciona caminos según condiciones  
B. ejecuta siempre varios caminos  
C. representa una clase  
D. crea objetos

### 6

Un fork:

A. activa caminos concurrentes  
B. selecciona necesariamente solo uno  
C. representa un actor  
D. termina el diagrama

### 7

Un estado representa:

A. una situación relevante de un objeto  
B. siempre una acción  
C. un caso de uso  
D. una clase padre

### 8

Una transición:

A. conecta estados ante un evento/condición  
B. conecta clases por herencia  
C. es un commit  
D. es una actividad paralela

### 9

RA6.c y RA6.d:

A. se evalúan en UD07  
B. se reservan para UD08  
C. pertenecen a RA5  
D. pertenecen a RA4

### 10

Un mismo proceso puede estudiarse con varios diagramas porque:

A. todos representan exactamente la misma información  
B. cada diagrama ofrece una perspectiva diferente  
C. UML obliga a duplicar todo  
D. solo uno es correcto

---

# 120. Soluciones de autoevaluación

```text
1 → B
2 → B
3 → A
4 → A
5 → A
6 → A
7 → A
8 → A
9 → B
10 → B
```

---

# PARTE B — MATERIAL DEL PROFESOR

# 121. Finalidad docente

La principal meta es evitar que el alumnado aprenda:

```text
“dibujos UML”
```

de manera aislada.

Debe comprender:

```text
PREGUNTA
↓
PERSPECTIVA
↓
TIPO DE DIAGRAMA
```

Ejemplo:

```text
¿Qué puede hacer el cliente?
↓
Casos de uso
```

```text
¿Cómo se procesa la compra?
↓
Actividad
```

```text
¿Cómo cambia una entrada?
↓
Estados
```

---

# 122. RA6.a no es memorizar nombres

No basta con:

```text
casos de uso
actividad
estado
secuencia
comunicación
```

Debe demostrar:

```text
cuándo utilizar
cada perspectiva.
```

---

# 123. RA6.b — especial cuidado

La norma dice:

```text
“Se ha reconocido el significado
de los diagramas de casos de uso.”
```

Por tanto, el indicador definitivo se centra en:

```text
comprensión

interpretación

significado.
```

La creación de un caso de uso en P07.1:

```text
refuerza esa comprensión
```

pero no se convierte artificialmente en un séptimo CE.

---

# 124. Casos de uso — qué penalizar

Penalizar técnicamente:

```text
actores internos
sin justificación

casos llamados “Base de datos”

casos llamados “Botón aceptar”

uso del diagrama como flowchart

include/extend arbitrarios.
```

No penalizar:

```text
diferencias menores
de distribución gráfica
```

si la semántica es correcta.

---

# 125. `include` y `extend`

Para primero conviene evitar discusiones excesivamente formales.

La idea pedagógica:

```text
include
→ reutilización necesaria
  del comportamiento incluido

extend
→ comportamiento añadido
  bajo determinadas condiciones
```

Debe enseñarse siempre con:

```text
ejemplos
+
interpretación.
```

---

# 126. Dirección de las relaciones

El profesor debe comprobar visualmente en Umbrello:

```text
dirección de las dependencias
```

al construir `include` y `extend`.

No debe evaluarse solo:

```text
la posición del texto.
```

La relación semántica es lo importante.

---

# 127. RA6.e vs RA6.f

## RA6.e

```text
interpreta.
```

Por tanto debe existir:

```text
un diagrama ajeno
al alumno.
```

## RA6.f

```text
elabora.
```

Por tanto debe existir:

```text
un requisito textual
que el alumno transforma
en actividad.
```

---

# 128. Fork vs decisión

Este es probablemente el error más frecuente.

Preguntar:

```text
¿se elige un camino?

o

¿se ejecutan varios?
```

## Si se elige

```text
decisión.
```

## Si se ejecutan varios

```text
fork.
```

---

# 129. RA6.g vs RA6.h

La misma separación:

## RA6.g

```text
diagrama ajeno
→ interpretación.
```

## RA6.h

```text
requisito/ciclo
→ creación del alumno.
```

---

# 130. Estado vs acción

Ejemplo malo:

```text
Procesando pago
```

como estado de:

```text
Entrada
```

si lo relevante son:

```text
Reservada

Pagada

Validada.
```

Preguntar:

> ¿Puede el objeto permanecer significativamente en esa situación?

Ayuda a decidir.

---

# 131. CartagoTickets — solución orientativa de casos

Actores:

```text
Cliente

Administrador

Pasarela de pago
```

Casos:

```text
Consultar eventos

Comprar entrada

Consultar compras

Cancelar entrada

Crear evento

Modificar evento

Cancelar evento

Procesar pago
```

Relación razonable:

```text
Comprar entrada
<<include>>
Procesar pago
```

`Aplicar descuento` puede modelarse de varias formas según el nivel de abstracción elegido.

Debe aceptarse una alternativa bien justificada.

---

# 132. Solución orientativa de actividad

```text
Inicio
↓
Seleccionar evento
↓
Seleccionar entradas
↓
Introducir datos
↓
¿cupón?
├─ [válido] → Aplicar descuento
└─ [no] ───────────────┐
                       ↓
                 Solicitar pago
                       ↓
                 ¿aceptado?
                   /       \
             [sí]           [no]
               |              |
               v              v
          Crear entrada   Mostrar error
               |
              FORK
             /    \
            v      v
      Enviar mail  Actualizar plazas
             \    /
              JOIN
               |
               v
              Fin
```

No exigir exactamente este diseño si otro satisface los requisitos.

---

# 133. Solución orientativa de estados

```text
Inicio
↓
Reservada
├── pagar ───────────→ Pagada
└── cancelar ────────→ Cancelada

Pagada
├── validar ─────────→ Validada
└── cancelar ────────→ Cancelada
```

Estados terminales según el alcance:

```text
Validada

Cancelada
```

pueden conectar con final.

---

# 134. ¿Debe existir Expirada?

No, salvo que:

```text
el requisito
lo indique
```

o el alumno lo introduzca como extensión claramente justificada.

No debemos premiar automáticamente:

```text
añadir más estados.
```

---

# 135. Herramienta

Umbrello 26.08.1 continúa siendo adecuada porque soporta de forma directa:

```text
Use Case Diagram

Activity Diagram

State Diagram
```

además de los diagramas de interacción que utilizaremos en UD08.

---

# 136. Capturas previstas

```text
CAPTURA UD07-01
Use Case Diagram

CAPTURA UD07-02
Activity Diagram

CAPTURA UD07-03
Fork / Join

CAPTURA UD07-04
State Diagram

CAPTURA UD07-05
Transición con evento/guarda

CAPTURA UD07-06
CartagoTickets — casos de uso

CAPTURA UD07-07
CartagoTickets — actividad

CAPTURA UD07-08
CartagoTickets — estados
```

---

# 137. Medidas de apoyo

Puede proporcionarse:

```text
plantilla de símbolos

caso de uso incompleto

flujo textual numerado

lista de estados posibles

tabla evento/origen/destino

diagramas de entrenamiento.
```

No proporcionar:

```text
los tres modelos finales
de CartagoTickets.
```

---

# 138. Plantilla útil para estados

| Estado origen | Evento | Guarda | Estado destino |
|---|---|---|---|
| | | | |

El alumno puede completar esta tabla antes de dibujar.

---

# 139. Plantilla útil para actividades

| Paso | Acción | Decisión/condición | Responsable |
|---:|---|---|---|
| | | | |

Ayuda especialmente a alumnado con dificultades de organización.

---

# 140. Ampliación

Alumnado avanzado puede estudiar:

```text
estados compuestos

entry / exit

history states

subactividades

particiones complejas

generalización de actores/casos
```

sin incorporarlo a los mínimos evaluables.

---

# 141. Recuperación

Instrumento:

# IR-RA6-01

Bloques relacionados con UD07:

```text
RA6.a

RA6.b

RA6.e

RA6.f

RA6.g

RA6.h
```

Ejemplo:

```text
a = 7
b = 6
e = 4
f = 3
g = 7
h = 6
```

Si RA6 finalmente queda no superado y necesitan nueva evidencia:

```text
RA6.e

RA6.f
```

se activan únicamente esos bloques.

---

# 142. Trazabilidad UD07

| RA | CE | Contenido | Actividades | Instrumento | Evidencias |
|---|---|---|---|---|---|
| RA6 | a | tipos de comportamiento | A07.1 | P07.1 / I-RA6-01 | E-RA6.a-01/02 |
| RA6 | b | casos de uso | A07.2–3 | P07.1 / I-RA6-01 | E-RA6.b-01/04 |
| RA6 | e | interpretación de actividades | A07.4 | P07.1 / I-RA6-01 | E-RA6.e-01/03 |
| RA6 | f | elaboración de actividades | A07.5–6 | P07.1 / I-RA6-01 | E-RA6.f-01/04 |
| RA6 | g | interpretación de estados | A07.7 | P07.1 / I-RA6-01 | E-RA6.g-01/03 |
| RA6 | h | elaboración de estados | A07.8–9 | P07.1 / I-RA6-01 | E-RA6.h-01/04 |

---

# 143. Estado de RA6 tras UD07

```text
RA6.a → EVALUADO

RA6.b → EVALUADO

RA6.c → PENDIENTE UD08

RA6.d → PENDIENTE UD08

RA6.e → EVALUADO

RA6.f → EVALUADO

RA6.g → EVALUADO

RA6.h → EVALUADO
```

RA6 continúa:

# ABIERTO.

---

# 144. Cálculo parcial

No se calculará RA6 definitivamente hasta disponer también de:

```text
RA6.c

RA6.d.
```

Tras UD08:

```text
RA6 =
(a+b+c+d+e+f+g+h) / 8
```

---

# 145. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA6

**CE evaluados:**

```text
RA6.a

RA6.b

RA6.e

RA6.f

RA6.g

RA6.h
```

### ¿Se utiliza RA5?

Solo como conocimiento previo:

```text
clases

objetos

estructura.
```

# NO SE RECALIFICA.

### ¿Se interpretan diagramas de interacción?

Solo se mencionan para:

```text
clasificarlos en RA6.a.
```

No se trabaja su interpretación técnica.

### ¿Se elaboran diagramas de interacción?

# NO.

RA6.c y RA6.d quedan para UD08.

### ¿Se evalúa programación?

# NO.

### ¿Algún instrumento mezcla RA?

# NO.

```text
I-RA6-01
→ exclusivamente RA6.
```

---

# 146. Checklist final UD07

```text
☑ 7 periodos.

☑ RA6 único.

☑ RA6.a oficial.

☑ RA6.b oficial.

☑ RA6.e oficial.

☑ RA6.f oficial.

☑ RA6.g oficial.

☑ RA6.h oficial.

☑ RA6.c/d reservados.

☑ Estructura vs comportamiento.

☑ Clasificación de diagramas.

☑ Casos de uso.

☑ Actor.

☑ Frontera.

☑ Use case.

☑ Asociación.

☑ include.

☑ extend.

☑ Generalización contextualizada.

☑ Caso de uso ≠ flujo.

☑ Actividades.

☑ Inicio/final.

☑ Acciones.

☑ Decisiones.

☑ Guardas.

☑ Merge.

☑ Fork.

☑ Join.

☑ Swimlanes contextualizadas.

☑ Fork ≠ decisión.

☑ Estados.

☑ Evento.

☑ Transición.

☑ Guarda.

☑ Estado inicial/final.

☑ Estado ≠ actividad.

☑ Selección del tipo adecuado.

☑ Umbrello 26.08.1.

☑ CartagoTickets.

☑ 8 capturas previstas.

☑ Actividades guiadas.

☑ Consolidación.

☑ P07.1.

☑ I-RA6-01.

☑ 6 notas CE 0–10.

☑ Rúbrica armonizada.

☑ Evidencias codificadas.

☑ Autoevaluación.

☑ Resumen.

☑ Glosario.

☑ Material profesor.

☑ Recuperación modular.

☑ Trazabilidad completa.

☑ Aislamiento superado.
```

# UD07 — VERSIÓN MAESTRA DEFINITIVA