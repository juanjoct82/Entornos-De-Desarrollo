# UD02 — INGENIERÍA DEL SOFTWARE, CICLO DE VIDA Y METODOLOGÍAS ÁGILES

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 9 periodos lectivos  
**Resultado de Aprendizaje:** RA1  
**Práctica evaluable:** P02.1  
**Instrumento:** I-RA1-02  

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

En UD01 aprendimos qué sucede desde que escribimos código hasta que un programa puede ejecutarse.

Pero en un proyecto profesional el trabajo no empieza escribiendo:

```java
public class Aplicacion {
}
```

Antes debemos responder preguntas como:

```text
¿Qué problema debemos resolver?

¿Quién utilizará la aplicación?

¿Qué necesita realmente el cliente?

¿Cómo organizaremos el trabajo?

¿Qué construiremos primero?

¿Cómo comprobaremos que funciona?

¿Qué ocurrirá cuando cambien los requisitos?

¿Qué haremos después de publicar el software?
```

Desarrollar software profesional es mucho más que programar.

---

# 2. Resultado de Aprendizaje

## RA1

**Reconoce los elementos y herramientas que intervienen en el desarrollo de un programa informático, analizando sus características y las fases en las que actúan hasta llegar a su puesta en funcionamiento.**

---

# 3. Criterios de evaluación de UD02

En esta unidad se evalúan exclusivamente:

## RA1.b

**Se han identificado las fases de desarrollo de una aplicación informática.**

## RA1.g

**Se han identificado las características y escenarios de uso de las metodologías ágiles de desarrollo de software.**

Estas formulaciones corresponden al currículo estatal vigente del módulo 0487.

---

# 4. CE reforzado pero NO recalificado

Durante la unidad volveremos a mencionar herramientas del desarrollo:

```text
IDE

repositorio

herramientas de gestión

testing

documentación

CI
```

Esto refuerza:

```text
RA1.f
```

pero:

# RA1.f NO SE EVALÚA DE NUEVO EN UD02.

Su fuente de calificación definitiva continúa siendo:

```text
I-RA1-01
```

de UD01.

---

# 5. Contenidos curriculares relacionados

El currículo incluye expresamente dentro de este bloque:

```text
fases del desarrollo de una aplicación:

análisis

diseño

codificación

pruebas

documentación

explotación

mantenimiento

entre otras
```

y:

```text
metodologías ágiles

técnicas

características
```


---

# 6. ¿Qué aprenderemos?

Al finalizar la unidad deberás poder:

- explicar por qué el desarrollo de software necesita organización;
- identificar las fases principales del desarrollo;
- distinguir análisis, diseño, implementación, pruebas, despliegue y mantenimiento;
- comprender que las fases no siempre tienen que ejecutarse una única vez y en secuencia rígida;
- distinguir ciclo de vida, modelo de proceso, metodología, framework y práctica;
- reconocer modelos secuenciales, iterativos e incrementales;
- comprender el enfoque en cascada;
- comprender el modelo en V;
- reconocer un desarrollo iterativo e incremental;
- explicar qué significa trabajar de forma ágil;
- reconocer las principales características de Scrum;
- comprender el uso de un tablero Kanban;
- diferenciar Scrum y Kanban a un nivel introductorio;
- seleccionar razonadamente un enfoque de desarrollo según un escenario profesional;
- reconocer cuándo un enfoque ágil puede aportar valor y cuándo determinadas condiciones requieren mayor planificación previa.

---

# 7. ¿Para qué sirve profesionalmente?

Un desarrollador profesional casi nunca trabaja solo con una lista de instrucciones como:

```text
Haz una aplicación.
```

El trabajo real necesita:

```text
requisitos

prioridades

planificación

coordinación

entregas

comprobaciones

documentación

mantenimiento
```

Comprender el proceso permite participar correctamente en equipos donde existen perfiles como:

```text
desarrolladores

analistas

diseñadores

responsables de producto

QA / testers

administradores

usuarios y clientes
```

---

# 8. Caso inicial — Miralmonte ReservaLab

El Colegio Miralmonte quiere una aplicación que permita reservar determinadas aulas y laboratorios.

Petición inicial:

> Queremos que los profesores puedan consultar espacios disponibles y reservar un aula.

Aparentemente es sencillo.

Pero empezamos a preguntar:

```text
¿Quién puede reservar?

¿Pueden reservar los alumnos?

¿Puede haber reservas simultáneas?

¿Se pueden cancelar?

¿Con cuánta antelación?

¿Existen aulas restringidas?

¿Debe aprobar alguien una reserva?

¿Debe enviarse confirmación?

¿Qué ocurre si cambia el horario?

¿Se necesita historial?
```

Acabamos de descubrir una idea fundamental:

# PROGRAMAR NO ES EL PRIMER PROBLEMA.

Antes debemos comprender qué necesitamos construir.

---

# 9. Ingeniería del software

La ingeniería del software aplica procesos, métodos, técnicas y herramientas para desarrollar y mantener software de manera organizada.

Busca controlar aspectos como:

```text
complejidad

calidad

coste

tiempo

riesgo

mantenibilidad

evolución
```

No significa convertir el desarrollo en un procedimiento rígido.

Significa evitar depender únicamente de:

```text
"vamos programando y ya veremos".
```

---

# 10. Proyecto pequeño frente a proyecto profesional

Para un ejercicio de diez líneas podemos:

```text
pensar
↓
escribir
↓
ejecutar
```

Pero para una aplicación con:

```text
40.000 líneas

varios desarrolladores

clientes

base de datos

usuarios reales

varios años de mantenimiento
```

esa estrategia deja de ser suficiente.

---

# 11. Ciclo de vida del software

El **ciclo de vida del software** representa las etapas por las que pasa un producto desde que surge la necesidad hasta que deja de utilizarse.

Una representación general puede ser:

```text
NECESIDAD
    │
    ▼
ANÁLISIS
    │
    ▼
DISEÑO
    │
    ▼
IMPLEMENTACIÓN
    │
    ▼
PRUEBAS
    │
    ▼
DESPLIEGUE / EXPLOTACIÓN
    │
    ▼
MANTENIMIENTO
```

La documentación puede aparecer durante todo el proceso.

---

# 12. Una advertencia importante

Este esquema:

```text
análisis
↓
diseño
↓
codificación
↓
pruebas
```

NO significa necesariamente que todos los proyectos deban realizar una sola vez cada fase y en ese orden rígido.

Podemos:

```text
analizar una parte

diseñarla

implementarla

probarla

obtener feedback

volver a analizar

mejorarla
```

Esto nos conduce a modelos iterativos e incrementales.

---

# 13. Fase 1 — Necesidad y planificación inicial

Todo proyecto aparece porque existe alguna necesidad.

Ejemplos:

```text
automatizar reservas

vender productos

gestionar empleados

controlar inventario

tramitar incidencias
```

Antes de programar es necesario determinar:

```text
objetivo

alcance inicial

restricciones

usuarios

recursos

riesgos básicos
```

---

# 14. Fase 2 — Análisis

El análisis intenta responder:

# ¿QUÉ DEBE HACER EL SISTEMA?

No:

```text
¿Cómo lo programaremos?
```

sino:

```text
¿Qué problema debe resolver?
```

En ReservaLab podríamos identificar:

```text
consultar disponibilidad

crear reserva

cancelar reserva

consultar mis reservas

evitar solapamientos
```

---

# 15. Requisitos

Un requisito expresa una necesidad o condición que debe satisfacer el sistema.

Ejemplo:

> El sistema debe impedir que dos reservas ocupen el mismo espacio en el mismo intervalo.

Mejor que:

> Debe funcionar bien.

---

# 16. Requisitos funcionales

Describen comportamientos o servicios.

Ejemplos:

```text
registrar usuario

crear reserva

calcular precio

cancelar pedido
```

---

# 17. Requisitos no funcionales

Expresan características o restricciones.

Por ejemplo:

```text
seguridad

rendimiento

accesibilidad

disponibilidad

compatibilidad

usabilidad
```

Ejemplo:

> Una consulta de disponibilidad debe responder en menos de dos segundos en condiciones normales.

---

# 18. Error frecuente: empezar por la solución

Cliente:

> Necesito gestionar reservas.

Desarrollador:

> Perfecto, usaré Java, PostgreSQL y React.

Todavía no conocemos suficientemente el problema.

Primero:

```text
NECESIDAD
↓
REQUISITOS
```

Después decidiremos:

```text
DISEÑO
+
TECNOLOGÍAS.
```

---

# 19. Fase 3 — Diseño

El diseño responde principalmente:

# ¿CÓMO ORGANIZAREMOS LA SOLUCIÓN?

Podemos tomar decisiones sobre:

```text
estructura

componentes

datos

interfaces

responsabilidades

arquitectura

interacciones
```

Ejemplo conceptual:

```text
Usuario
    │
    ▼
Aplicación
    │
    ├── Gestión de reservas
    ├── Gestión de usuarios
    └── Gestión de espacios
            │
            ▼
        Base de datos
```

---

# 20. CONOCIMIENTO AUXILIAR NO EVALUADO EN ESTA UNIDAD

En futuras unidades utilizaremos UML para representar formalmente algunos diseños.

Esto pertenece evaluativamente a:

```text
RA5
RA6
```

En UD02 únicamente utilizamos esquemas informales para comprender el proceso.

No se evalúa UML.

---

# 21. Fase 4 — Implementación o codificación

Ahora convertimos el diseño en software.

Podemos utilizar:

```text
Java

Kotlin

JavaScript

SQL

HTML/CSS

frameworks

librerías
```

según el proyecto.

Es la fase en la que habitualmente pensamos cuando hablamos de:

```text
programar.
```

Pero solo representa una parte del ciclo completo.

---

# 22. Fase 5 — Pruebas

Debemos comprobar si:

```text
el sistema hace lo que debe
```

y detectar defectos.

Ejemplos:

```text
¿permite reservar?

¿impide solapamientos?

¿rechaza datos inválidos?

¿funciona después de un cambio?
```

---

# 23. CONOCIMIENTO AUXILIAR NO EVALUADO EN ESTA UNIDAD

El diseño y ejecución profesional de pruebas pertenece a:

```text
RA3
```

y se desarrollará en UD09 y UD10.

Aquí únicamente identificamos:

```text
PRUEBAS
```

como fase del desarrollo.

No se evalúan técnicas de testing.

---

# 24. Fase 6 — Documentación

La documentación puede dirigirse a:

```text
usuarios

desarrolladores

administradores

clientes

mantenimiento
```

Ejemplos:

```text
manual de usuario

documentación técnica

comentarios de API

decisiones de arquitectura

procedimientos de instalación
```

No debe entenderse necesariamente como:

```text
"algo que hacemos al terminar".
```

Puede construirse y actualizarse durante todo el proyecto.

---

# 25. Fase 7 — Despliegue y explotación

Cuando el software está preparado debemos ponerlo a disposición de sus usuarios.

Puede implicar:

```text
instalación

configuración

migración de datos

publicación

monitorización

formación de usuarios
```

Una aplicación que:

```text
funciona en mi ordenador
```

todavía puede tener problemas al desplegarse en otro entorno.

---

# 26. Fase 8 — Mantenimiento

Después de publicar empieza una etapa que puede durar años.

Podemos necesitar:

```text
corregir errores

adaptar requisitos

mejorar rendimiento

añadir funcionalidades

actualizar dependencias

adaptarnos a nuevas plataformas
```

El software no suele permanecer congelado.

---

# 27. Tipos de mantenimiento

Podemos distinguir de forma introductoria:

## Correctivo

Corrige defectos.

## Adaptativo

Adapta el software a cambios externos.

Ejemplo:

```text
nuevo sistema operativo
```

## Perfectivo o evolutivo

Añade mejoras o funcionalidades.

## Preventivo

Busca reducir futuros problemas de mantenimiento.

No necesitas memorizar una clasificación rígida; debes comprender que mantener software significa mucho más que reparar bugs.

---

# 28. Diagrama general

**[DIAGRAMA UD02-01 — Ciclo de vida del software]**

```text
                 ┌───────────────┐
                 │   NECESIDAD   │
                 └───────┬───────┘
                         ▼
                 ┌───────────────┐
                 │   ANÁLISIS    │
                 └───────┬───────┘
                         ▼
                 ┌───────────────┐
                 │    DISEÑO     │
                 └───────┬───────┘
                         ▼
                 ┌───────────────┐
                 │IMPLEMENTACIÓN │
                 └───────┬───────┘
                         ▼
                 ┌───────────────┐
                 │    PRUEBAS    │
                 └───────┬───────┘
                         ▼
                 ┌───────────────┐
                 │  DESPLIEGUE   │
                 └───────┬───────┘
                         ▼
                 ┌───────────────┐
                 │ MANTENIMIENTO │
                 └───────────────┘
```

La edición gráfica definitiva deberá mostrar también flechas de retroalimentación.

---

# 29. Actividad A02.1 — Ordena el proyecto

Una empresa quiere desarrollar una aplicación para registrar incidencias TIC.

Ordena y relaciona:

```text
programar la aplicación

entrevistar usuarios

publicar versión

diseñar estructura

corregir problemas posteriores

comprobar requisitos

redactar documentación
```

con las fases del desarrollo.

Después explica por qué en un proyecto real:

```text
el orden puede no ser estrictamente lineal.
```

---

# 30. Modelo de proceso

Un **modelo de proceso** describe una forma general de organizar las actividades del desarrollo.

Ejemplos:

```text
cascada

modelo en V

iterativo

incremental
```

No debemos confundir:

```text
FASES
```

con:

```text
MODELO.
```

Las fases pueden ser similares.

Lo que cambia es:

```text
cómo se organizan

cuándo se repiten

cómo se relacionan.
```

---

# 31. Modelo en cascada

El modelo clásico en cascada suele representarse de manera secuencial:

```text
REQUISITOS
    ↓
DISEÑO
    ↓
IMPLEMENTACIÓN
    ↓
PRUEBAS
    ↓
DESPLIEGUE
```

La idea básica es completar una etapa antes de avanzar significativamente a la siguiente.

---

# 32. Ventajas conceptuales de un enfoque secuencial

Puede facilitar:

```text
planificación previa

documentación

hitos claros

control de fases
```

especialmente cuando:

```text
el alcance es estable

los requisitos están muy definidos

existen fuertes restricciones documentales
```

---

# 33. Limitaciones del enfoque rígido

Puede resultar problemático si:

```text
los requisitos cambian mucho

el cliente descubre sus necesidades al ver el producto

la validación útil llega demasiado tarde
```

Ejemplo:

```text
6 meses desarrollando
↓
primera versión visible
↓
cliente:
"Esto no es exactamente lo que necesitábamos".
```

---

# 34. Modelo en V

El modelo en V enfatiza la relación entre:

```text
actividades de definición/diseño
```

y:

```text
actividades de verificación/validación.
```

Representación simplificada:

```text
REQUISITOS                ACEPTACIÓN
     \                       /
      \                     /
     DISEÑO SISTEMA     PRUEBAS SISTEMA
        \                 /
         \               /
        DISEÑO DETALLE  PRUEBAS
              \         /
               \       /
              IMPLEMENTACIÓN
```

No estudiaremos formalmente sus tipos de pruebas en esta unidad.

---

# 35. Desarrollo iterativo

En un enfoque iterativo realizamos varias pasadas.

Ejemplo:

```text
ITERACIÓN 1
↓
primera solución

ITERACIÓN 2
↓
mejora

ITERACIÓN 3
↓
nueva mejora
```

Cada iteración permite revisar lo anterior.

---

# 36. Desarrollo incremental

En un enfoque incremental construimos el sistema por partes utilizables.

Ejemplo ReservaLab:

```text
INCREMENTO 1
login

INCREMENTO 2
consulta de aulas

INCREMENTO 3
crear reservas

INCREMENTO 4
cancelaciones

INCREMENTO 5
notificaciones
```

El sistema crece progresivamente.

---

# 37. Iterativo e incremental pueden combinarse

Un proyecto puede:

```text
añadir funcionalidad
```

y simultáneamente:

```text
mejorar lo ya construido.
```

Por eso es habitual encontrar:

```text
iterativo + incremental
```

en un mismo proceso.

---

# 38. Actividad A02.2 — Incrementos de ReservaLab

Divide ReservaLab en cinco incrementos razonables.

Para cada incremento indica:

```text
qué funcionalidad aporta

qué usuario obtiene valor

qué podría comprobarse al terminar.
```

No existe una única solución correcta.

---

# 39. ¿Qué significa ágil?

Trabajar de forma ágil no significa:

```text
programar rápido

no documentar

no planificar

no diseñar

hacer lo que queramos

cambiar todo continuamente
```

Un enfoque ágil intenta responder eficazmente al cambio y entregar valor de forma frecuente.

---

# 40. El Manifiesto Ágil

El Manifiesto Ágil plantea cuatro valores que priorizan:

```text
personas y colaboración

software funcionando

colaboración con cliente

respuesta al cambio
```

sin afirmar que procesos, documentación, contratos o planes carezcan de valor.

Sus principios promueven, entre otros aspectos, entrega frecuente, colaboración continua, adaptación al cambio, sostenibilidad y mejora periódica.

---

# 41. Importante: ágil no significa ausencia de planificación

En un equipo ágil también existe:

```text
planificación

priorización

estimación

seguimiento

revisión

documentación
```

La diferencia está en que:

```text
el plan puede adaptarse
```

cuando aparece nueva información.

---

# 42. Características habituales de los enfoques ágiles

Podemos reconocer:

```text
entregas pequeñas y frecuentes

feedback temprano

priorización continua

adaptación al cambio

trabajo colaborativo

mejora continua

visibilidad del trabajo
```

Estas características ayudan especialmente cuando:

```text
el problema tiene incertidumbre

los requisitos evolucionan

el cliente puede participar

es posible entregar progresivamente.
```

---

# 43. Escenario adecuado para agilidad

Proyecto:

> Una startup está creando una nueva aplicación deportiva. Tiene una idea inicial, pero todavía no sabe qué funcionalidades valorarán realmente sus usuarios.

Existen:

```text
incertidumbre

cambios frecuentes

feedback disponible

posibilidad de construir incrementos
```

Un enfoque ágil puede resultar especialmente apropiado.

---

# 44. Escenario diferente

Proyecto:

> Debe sustituirse un pequeño componente de un sistema industrial regulado. La interfaz, requisitos y certificaciones están fijados contractualmente.

Puede requerirse:

```text
mucha planificación inicial

documentación formal

trazabilidad estricta

control de cambios
```

Esto no significa automáticamente:

```text
"ágil prohibido".
```

Significa que el contexto condiciona cómo organizamos el trabajo.

---

# 45. No existe una metodología universalmente mejor

Pregunta incorrecta:

> ¿Qué metodología es la mejor?

Pregunta profesional:

> ¿Qué enfoque resulta adecuado para este proyecto y por qué?

Debemos analizar:

```text
estabilidad de requisitos

tamaño del equipo

criticidad

regulación

participación del cliente

frecuencia de entrega

incertidumbre

riesgo
```

---

# 46. Scrum

Scrum es un marco para abordar problemas complejos mediante un proceso iterativo e incremental.

La **Scrum Guide 2020** sigue siendo la versión oficial vigente publicada por sus autores.

No convertiremos esta unidad en una certificación Scrum.

Solo necesitamos comprender sus elementos esenciales.

---

# 47. Responsabilidades principales en Scrum

Scrum define un equipo con responsabilidades diferenciadas:

```text
Product Owner

Scrum Master

Developers
```

---

# 48. Product Owner

Se ocupa especialmente de maximizar el valor del producto y gestionar eficazmente el:

```text
Product Backlog.
```

A nivel introductorio podemos pensar que ayuda a responder:

```text
¿Qué es más importante construir ahora?
```

---

# 49. Developers

Son las personas que crean un incremento utilizable del producto durante el Sprint.

No debemos reducir:

```text
Developer
```

únicamente a:

```text
persona que escribe Java.
```

El trabajo puede incluir las actividades necesarias para producir el incremento.

---

# 50. Scrum Master

Ayuda al equipo y a la organización a comprender y aplicar Scrum correctamente.

No debe confundirse con:

```text
jefe que reparte tareas.
```

---

# 51. Sprint

Scrum organiza el trabajo dentro de periodos denominados:

```text
Sprints.
```

Dentro de ellos se persigue un objetivo y se crea un incremento de producto.

Conceptualmente:

```text
BACKLOG
   │
   ▼
SPRINT
   │
   ▼
INCREMENTO
   │
   ▼
FEEDBACK
   │
   └────→ siguiente adaptación
```

---

# 52. Product Backlog

Es una lista ordenada y evolutiva de aquello que puede ser necesario para mejorar el producto.

Ejemplo ReservaLab:

```text
consultar disponibilidad

crear reserva

cancelar reserva

notificar cambios

gestionar espacios

generar informes
```

El orden puede cambiar cuando aparecen nuevas prioridades.

---

# 53. Sprint Backlog

Representa el trabajo seleccionado y el plan realizado para conseguir el objetivo del Sprint.

No debe entenderse simplemente como:

```text
una copia pequeña del Product Backlog.
```

---

# 54. Incremento

Es el resultado acumulado que acerca el producto hacia su objetivo y cumple la definición de terminado aplicable.

Para nuestro nivel:

```text
incremento
=
parte integrada y utilizable del producto.
```

---

# 55. Eventos que reconoceremos

A nivel introductorio:

```text
Sprint Planning

Daily Scrum

Sprint Review

Sprint Retrospective
```

y el propio:

```text
Sprint.
```

No necesitas memorizar cada regla de duración.

Debes comprender su finalidad.

---

# 56. Sprint Planning

Ayuda a decidir:

```text
por qué es valioso el Sprint

qué puede realizarse

cómo se abordará.
```

---

# 57. Daily Scrum

Es un evento breve de inspección del progreso hacia el objetivo del Sprint y adaptación del trabajo de los Developers.

No debe convertirse en:

```text
un informe diario al profesor/jefe.
```

---

# 58. Sprint Review

Permite revisar el resultado del Sprint con los interesados y decidir posibles adaptaciones futuras.

Pregunta clave:

```text
¿Qué hemos construido
y qué hemos aprendido?
```

---

# 59. Sprint Retrospective

Se orienta a mejorar:

```text
calidad

eficacia

forma de trabajar
```

Pregunta conceptual:

```text
¿Cómo podemos trabajar mejor
en el siguiente Sprint?
```

---

# 60. Actividad A02.3 — Scrum en ReservaLab

Tenemos un Sprint cuyo objetivo es:

> Permitir que un profesor consulte espacios libres y cree una reserva.

Propón:

```text
Product Backlog relacionado

elementos del Sprint Backlog

incremento esperado

qué revisaríamos al finalizar

una posible mejora para retrospectiva.
```

---

# 61. Kanban

Kanban puede utilizar un tablero visual para representar el flujo de trabajo.

Ejemplo sencillo:

| POR HACER | EN CURSO | REVISIÓN | TERMINADO |
|---|---|---|---|
| Login | Reservas | Validación | Modelo Usuario |
| Notificaciones | | | |

Esto permite visualizar:

```text
qué trabajo existe

qué está en curso

dónde se acumula trabajo

qué se ha terminado.
```

---

# 62. Limitar trabajo en curso

Una idea importante de los sistemas Kanban es evitar acumular demasiadas tareas simultáneamente.

Ejemplo problemático:

```text
10 tareas
→ EN CURSO

0
→ TERMINADAS
```

Es preferible favorecer:

```text
terminar
```

antes que:

```text
empezar continuamente.
```

---

# 63. Flujo

Imaginemos:

```text
POR HACER: 2

DESARROLLO: 2

REVISIÓN: 12

TERMINADO: 1
```

Tenemos un posible cuello de botella en:

```text
REVISIÓN.
```

Visualizar el trabajo permite detectar este tipo de problemas.

---

# 64. DIAGRAMA UD02-02 — Tablero Kanban

La edición definitiva deberá incluir un tablero visual como:

```text
┌────────────┬────────────┬────────────┬────────────┐
│ POR HACER  │ EN CURSO   │ REVISIÓN   │ TERMINADO  │
├────────────┼────────────┼────────────┼────────────┤
│ US-04      │ US-02      │ US-01      │ US-00      │
│ US-05      │ US-03      │            │            │
└────────────┴────────────┴────────────┴────────────┘
```

con límites de trabajo en curso señalados cuando proceda.

---

# 65. Scrum y Kanban no son simplemente lo mismo

Simplificando:

## Scrum

Organiza el trabajo mediante:

```text
Sprints

objetivos

responsabilidades

eventos

backlogs.
```

## Kanban

Pone especial atención en:

```text
visualizar flujo

gestionar trabajo en curso

mejorar flujo
```

Pueden existir equipos que combinen técnicas, pero no debemos afirmar que:

```text
usar columnas To Do / Doing / Done
=
estar aplicando Scrum.
```

---

# 66. Historias de usuario

En entornos ágiles es frecuente expresar necesidades mediante formatos sencillos como:

```text
Como [tipo de usuario]

quiero [objetivo]

para [beneficio].
```

Ejemplo:

> Como profesor, quiero consultar las aulas disponibles para poder elegir un espacio antes de crear una reserva.

Este formato ayuda a mantener el foco en:

```text
usuario

necesidad

valor.
```

---

# 67. Historia de usuario ≠ especificación completa

La historia:

> Como profesor quiero reservar un aula.

no especifica todavía:

```text
validaciones

reglas de negocio

casos límite

interfaz

permisos.
```

Necesitamos conversación y criterios que concreten el comportamiento esperado.

---

# 68. Criterios de aceptación

Ejemplo para:

> Como profesor quiero reservar un aula disponible.

Podríamos concretar:

```text
- no se permiten solapamientos;

- la fecha debe ser futura;

- solo pueden reservarse espacios habilitados;

- una reserva correcta queda registrada.
```

En esta UD los usamos para comprender el proceso.

El diseño formal de casos de prueba se reserva para RA3.

---

# 69. Actividad A02.4 — Historias de usuario

Para ReservaLab redacta historias para:

```text
consultar disponibilidad

crear reserva

cancelar reserva

administrar espacios
```

Después selecciona una y escribe tres criterios de aceptación.

---

# 70. Priorización

No todo tiene la misma importancia.

Si disponemos de:

```text
4 semanas
```

debemos decidir qué aporta más valor primero.

Ejemplo:

```text
1. consultar disponibilidad

2. crear reserva

3. cancelar

4. notificaciones

5. estadísticas avanzadas
```

Esta lista puede modificarse.

---

# 71. Feedback

Una ventaja de las entregas frecuentes es obtener información antes.

```text
CONSTRUIR
   ↓
MOSTRAR
   ↓
OBTENER FEEDBACK
   ↓
ADAPTAR
   ↓
CONSTRUIR
```

Así reducimos el riesgo de descubrir demasiado tarde que:

```text
hemos construido algo
que el usuario no necesita.
```

---

# 72. Actividad A02.5 — Cambio de requisitos

Durante el desarrollo de ReservaLab el cliente comunica:

> Las reservas de laboratorios de informática deben ser aprobadas por Jefatura de Estudios, pero las aulas normales no.

Responde:

1. ¿Qué partes del trabajo podrían verse afectadas?
2. ¿Qué ocurriría en un enfoque totalmente secuencial si el cambio aparece muy tarde?
3. ¿Cómo podría gestionarse en un proceso iterativo?
4. ¿Qué elemento del backlog modificarías?
5. ¿Qué nueva historia o criterio podría aparecer?

---

# 73. Herramientas que apoyan el proceso

Un equipo puede utilizar herramientas para:

```text
gestionar requisitos

organizar backlog

visualizar trabajo

guardar documentación

coordinar versiones

automatizar tareas
```

Pero:

# UNA HERRAMIENTA NO ES UNA METODOLOGÍA.

Utilizar un tablero no significa automáticamente:

```text
"somos ágiles".
```

---

# 74. CE REFORZADO NO RECALIFICADO — RA1.f

En UD01 ya evaluamos la funcionalidad general de herramientas del desarrollo.

Aquí simplemente observamos que pueden intervenir en distintas fases:

| Fase/necesidad | Ejemplo de herramienta |
|---|---|
| Requisitos | gestor de tareas/documentación |
| Diseño | herramienta de modelado |
| Código | IDE |
| Pruebas | framework de testing |
| Versionado | Git |
| Coordinación | tablero de trabajo |
| Construcción | Maven |
| CI | GitHub Actions |

Esta tabla:

```text
NO genera nueva nota RA1.f.
```

---

# 75. Error frecuente: herramienta = proceso

Incorrecto:

> Usamos GitHub, por tanto somos ágiles.

Incorrecto:

> Usamos Jira, por tanto aplicamos Scrum.

Incorrecto:

> Tenemos un tablero Kanban, por tanto nuestro proceso es perfecto.

Las herramientas ayudan.

El proceso depende de:

```text
cómo se organiza realmente el trabajo.
```

---

# 76. Error frecuente: agile = sin documentación

El enfoque ágil prioriza software funcionando frente a documentación exhaustiva, pero no afirma:

```text
documentación = 0.
```

La pregunta correcta es:

```text
¿Qué documentación aporta valor
y necesita este proyecto?
```

---

# 77. Error frecuente: Scrum Master = jefe

El Scrum Master no debe describirse simplemente como:

```text
jefe del equipo.
```

Scrum establece responsabilidades diferentes y un equipo autogestionado.

---

# 78. Error frecuente: sprint = mini cascada

Un error habitual es pensar:

```text
día 1 análisis

día 2 diseño

días 3–8 programación

día 9 pruebas

día 10 documentación
```

como si cada Sprint fuera automáticamente una cascada pequeña.

Dentro de un Sprint las actividades necesarias para producir valor pueden solaparse y repetirse.

---

# 79. Buenas prácticas

## Comprender antes de elegir metodología

No adoptar un enfoque únicamente porque:

```text
está de moda.
```

## Mantener visible el objetivo

Las tareas deben relacionarse con:

```text
valor

requisito

objetivo.
```

## Obtener feedback temprano

Reducir el tiempo entre:

```text
construir
```

y:

```text
validar.
```

## Trabajar con incrementos manejables

Es más sencillo validar:

```text
una pequeña capacidad usable
```

que cientos de cambios simultáneos.

## Revisar el proceso

Preguntarnos periódicamente:

```text
¿Qué está funcionando?

¿Qué debemos mejorar?
```

---

# 80. Caso profesional completo — ReservaLab

## Situación

El centro quiere una aplicación para gestionar reservas.

## Iteración inicial

Objetivo:

```text
permitir consultar espacios.
```

## Segundo incremento

```text
crear reserva.
```

## Tercer incremento

```text
cancelar reserva.
```

## Feedback

Los profesores solicitan:

```text
reserva recurrente.
```

## Adaptación

La funcionalidad se analiza, prioriza e incorpora al backlog.

Este ejemplo muestra:

```text
incremento
+
feedback
+
adaptación.
```

---

# 81. Ejercicio resuelto — elegir un enfoque

Caso:

> Una empresa quiere crear una aplicación móvil novedosa. Solo dispone de una hipótesis de producto. Podrá mostrar nuevas versiones a usuarios piloto cada dos semanas.

## Análisis

Requisitos:

```text
inestables
```

Feedback:

```text
frecuente
```

Posibilidad de incrementos:

```text
alta
```

Incertidumbre:

```text
alta
```

## Propuesta

Un enfoque:

```text
iterativo
+
incremental
+
ágil
```

puede resultar apropiado.

## Justificación

Permite:

```text
entregar pronto

obtener feedback

repriorizar

reducir riesgo de construir
funcionalidades poco valiosas.
```

No basta responder:

```text
"Scrum porque es mejor".
```

---

# 82. Ejercicios de consolidación

1. ¿Qué diferencia existe entre programar y desarrollar software?
2. Define ciclo de vida.
3. ¿Qué pregunta principal responde el análisis?
4. ¿Qué pregunta principal responde el diseño?
5. Diferencia requisito funcional y no funcional.
6. ¿Qué ocurre durante implementación?
7. ¿Para qué sirven las pruebas dentro del ciclo?
8. ¿Cuándo aparece el mantenimiento?
9. Pon un ejemplo de mantenimiento correctivo.
10. Pon un ejemplo de mantenimiento adaptativo.
11. ¿Qué es un modelo de proceso?
12. Describe cascada.
13. ¿Qué caracteriza al modelo en V?
14. Diferencia iterativo e incremental.
15. ¿Pueden combinarse?
16. ¿Qué significa trabajar de forma ágil?
17. Cita dos errores habituales sobre agilidad.
18. ¿Qué significa feedback temprano?
19. ¿Qué es Scrum?
20. ¿Qué es un Sprint?
21. ¿Qué es el Product Backlog?
22. ¿Qué diferencia conceptual existe entre Product Backlog y Sprint Backlog?
23. ¿Qué es un incremento?
24. ¿Cuál es la finalidad de la Sprint Review?
25. ¿Cuál es la finalidad de la Retrospective?
26. ¿Qué visualiza un tablero Kanban?
27. ¿Qué problema puede provocar demasiado trabajo en curso?
28. ¿Qué es una historia de usuario?
29. ¿Qué es un criterio de aceptación?
30. ¿Por qué no existe una única metodología adecuada para todos los proyectos?

---

# 83. Actividad de ampliación

## Diseña tu propio proceso

Elige uno:

```text
aplicación de citas médicas

tienda online

gestor de tareas

aplicación de rutas deportivas
```

Diseña:

```text
fases

primeros incrementos

mecanismo de feedback

organización del trabajo

estrategia ante cambios.
```

Después compara:

```text
enfoque secuencial

vs.

enfoque iterativo/ágil.
```

**Actividad no evaluable.**

---

# 84. Resumen

El desarrollo profesional incluye fases como:

```text
análisis

diseño

implementación

pruebas

documentación

despliegue

mantenimiento.
```

Estas fases pueden organizarse mediante distintos modelos.

Un enfoque secuencial:

```text
avanza principalmente
fase a fase.
```

Un enfoque iterativo:

```text
repite ciclos de mejora.
```

Un enfoque incremental:

```text
añade partes utilizables.
```

Los enfoques ágiles buscan especialmente:

```text
entrega frecuente

feedback

adaptación

colaboración

mejora continua.
```

Scrum proporciona un marco basado en Sprints, responsabilidades, eventos y artefactos.

Kanban ayuda a visualizar y gestionar el flujo de trabajo.

La elección de un proceso debe depender del:

```text
contexto del proyecto.
```

---

# 85. Glosario

**Agilidad:** capacidad de organizar el desarrollo favoreciendo entrega de valor, feedback y adaptación.

**Análisis:** fase orientada a comprender qué necesita el sistema.

**Backlog:** conjunto ordenado de trabajo potencial relacionado con el producto.

**Ciclo de vida:** conjunto de etapas por las que atraviesa el software.

**Criterio de aceptación:** condición utilizada para concretar cuándo un comportamiento satisface lo esperado.

**Daily Scrum:** evento de Scrum para inspeccionar progreso hacia el Sprint Goal y adaptar el plan.

**Despliegue:** puesta del software a disposición de sus usuarios o entorno objetivo.

**Diseño:** definición de cómo se organizará la solución.

**Feedback:** información obtenida sobre un resultado para decidir adaptaciones posteriores.

**Historia de usuario:** formato breve para expresar una necesidad desde la perspectiva de quien recibe valor.

**Incremental:** desarrollo en el que se añaden progresivamente partes utilizables.

**Incremento:** resultado integrado que amplía el producto.

**Iterativo:** desarrollo basado en ciclos sucesivos de revisión y mejora.

**Kanban:** enfoque de gestión del flujo que suele apoyarse en visualización del trabajo y control del trabajo en curso.

**Mantenimiento:** modificación del software después de su puesta en uso.

**Metodología/enfoque de desarrollo:** conjunto organizado de principios, prácticas y formas de gestionar el trabajo.

**Product Backlog:** lista ordenada y evolutiva de aquello necesario para mejorar un producto.

**Product Owner:** responsabilidad Scrum orientada a maximizar el valor y gestionar eficazmente el Product Backlog.

**Scrum:** framework ligero para abordar problemas complejos y generar valor mediante soluciones adaptativas.

**Sprint:** periodo de Scrum en el que se trabaja para conseguir un objetivo y generar valor.

**Sprint Backlog:** selección y plan de trabajo orientados al objetivo del Sprint.

**Sprint Review:** evento orientado a inspeccionar el resultado y determinar adaptaciones futuras.

**Sprint Retrospective:** evento orientado a mejorar la forma de trabajo.

---

# 86. Autoevaluación

### 1

La fase que intenta responder principalmente qué necesita el sistema es:

A. análisis  
B. compilación  
C. despliegue  
D. mantenimiento

### 2

Un requisito funcional describe:

A. una funcionalidad o servicio  
B. siempre un lenguaje  
C. una CPU  
D. únicamente rendimiento

### 3

Un desarrollo incremental:

A. entrega progresivamente partes del producto  
B. nunca realiza pruebas  
C. elimina requisitos  
D. utiliza obligatoriamente Scrum

### 4

Un enfoque iterativo:

A. realiza ciclos sucesivos de revisión y mejora  
B. solo puede ejecutarse una vez  
C. impide cambios  
D. significa no planificar

### 5

Ágil significa:

A. no documentar  
B. adaptarse y entregar valor frecuentemente  
C. no diseñar  
D. programar sin requisitos

### 6

En Scrum, el Product Backlog:

A. puede evolucionar  
B. nunca cambia  
C. contiene exclusivamente bugs  
D. es una lista del sistema operativo

### 7

Un Sprint produce:

A. progreso hacia un incremento de valor  
B. únicamente documentación  
C. un JDK  
D. una JVM

### 8

La Sprint Retrospective busca:

A. mejorar la forma de trabajo  
B. sustituir el código fuente  
C. instalar el IDE  
D. compilar Java

### 9

Kanban ayuda especialmente a:

A. visualizar y gestionar flujo  
B. compilar código  
C. crear bytecode  
D. sustituir requisitos

### 10

La metodología adecuada:

A. depende del contexto  
B. siempre es Scrum  
C. siempre es cascada  
D. siempre es Kanban

---

# 87. PRÁCTICA EVALUABLE P02.1

# DISEÑANDO EL PROCESO DE DESARROLLO DE CARTAGOFIT

**Modalidad:** individual  
**RA:** RA1  
**CE evaluados:** RA1.b y RA1.g  
**Instrumento:** I-RA1-02

---

# 88. Escenario profesional

La empresa **CartagoFit** quiere desarrollar una nueva plataforma para pequeños centros deportivos.

Versión inicial solicitada:

```text
gestionar clientes

reservar clases

cancelar reservas

consultar plazas disponibles
```

Datos adicionales:

```text
El equipo tiene 4 desarrolladores.

Existe un responsable de producto.

Dos gimnasios participarán como usuarios piloto.

Se quiere disponer de una primera versión útil
en aproximadamente un mes.

Los gimnasios podrán proponer cambios
después de probar cada versión.

No todos los requisitos están cerrados.

El presupuesto obliga a priorizar.
```

---

# 89. Objetivo

Debes diseñar y justificar un proceso de desarrollo adecuado para CartagoFit.

No se pide programar la aplicación.

Se evaluará tu capacidad para:

```text
identificar fases

organizar el desarrollo

reconocer características ágiles

seleccionar un enfoque según el escenario.
```

---

# 90. Tarea A — Fases del proyecto

Identifica al menos:

```text
análisis

diseño

implementación

pruebas

documentación

despliegue

mantenimiento
```

Para cada fase indica:

1. finalidad;
2. una actividad concreta en CartagoFit;
3. un posible producto o resultado de esa fase.

**CE:** RA1.b

---

# 91. Tabla de trabajo orientativa

| Fase | ¿Qué se hace? | Ejemplo CartagoFit | Resultado |
|---|---|---|---|
| Análisis | | | |
| Diseño | | | |
| Implementación | | | |
| Pruebas | | | |
| Documentación | | | |
| Despliegue | | | |
| Mantenimiento | | | |

---

# 92. Tarea B — Organización del ciclo

Explica si organizarías CartagoFit principalmente mediante:

```text
enfoque secuencial

iterativo

incremental

o combinación.
```

Debes justificar tu respuesta mediante datos concretos del escenario.

**CE:** RA1.b

---

# 93. Tarea C — Primeros incrementos

Propón al menos:

```text
4 incrementos
```

ordenados por valor.

Ejemplo de formato:

| Incremento | Funcionalidad | Valor aportado |
|---:|---|---|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |

**CE:** RA1.b

---

# 94. Tarea D — ¿Es adecuado un enfoque ágil?

Analiza CartagoFit respecto a:

```text
estabilidad de requisitos

feedback disponible

capacidad de entregar incrementos

tamaño del equipo

necesidad de priorización

frecuencia de cambios.
```

Concluye razonadamente:

```text
¿resulta adecuado
un enfoque ágil?
```

**CE:** RA1.g

---

# 95. Tarea E — Propuesta ágil

Si utilizas Scrum o elementos inspirados en Scrum, describe:

```text
Product Owner

Developers

Scrum Master

Product Backlog

Sprint

incremento

Review

Retrospective
```

aplicados específicamente a CartagoFit.

No basta con copiar definiciones.

**CE:** RA1.g

---

# 96. Tarea F — Product Backlog inicial

Propón al menos ocho elementos.

Ejemplo:

```text
gestionar cliente

consultar clases

reservar plaza
...
```

Ordénalos por prioridad y explica:

```text
por qué tus tres primeros
deben realizarse antes.
```

**CE:** RA1.g

---

# 97. Tarea G — Tablero de flujo

Representa un tablero sencillo:

```text
POR HACER

EN CURSO

REVISIÓN

TERMINADO
```

con al menos ocho elementos de trabajo.

Identifica:

```text
un posible límite de trabajo en curso
```

y explica su finalidad.

**CE:** RA1.g

---

# 98. Tarea H — Cambio durante el proyecto

Después de la primera versión, los gimnasios solicitan:

> Los usuarios solo podrán reservar clases si tienen una cuota activa.

Explica:

1. qué fase o actividades se ven afectadas;
2. cómo actualizarías el trabajo pendiente;
3. cómo lo gestionarías dentro del enfoque elegido;
4. por qué el proceso debería permitir adaptarse al cambio.

**CE:** RA1.g

---

# 99. Entregable

Archivo:

```text
P02.1_Apellidos_Nombre.pdf
```

Debe incluir:

1. portada;
2. identificación;
3. fases;
4. modelo de proceso elegido;
5. incrementos;
6. análisis del escenario;
7. propuesta ágil;
8. backlog;
9. tablero;
10. tratamiento del cambio;
11. conclusión.

---

# 100. Evidencias

## RA1.b

```text
E-RA1.b-01
Identificación y aplicación de las fases.

E-RA1.b-02
Organización razonada del ciclo de vida.

E-RA1.b-03
Propuesta de incrementos.
```

## RA1.g

```text
E-RA1.g-01
Análisis del escenario de uso.

E-RA1.g-02
Propuesta de enfoque ágil.

E-RA1.g-03
Backlog/priorización.

E-RA1.g-04
Tablero y flujo.

E-RA1.g-05
Respuesta a cambio de requisitos.
```

---

# 101. Instrumento I-RA1-02

**Instrumento:** I-RA1-02  
**RA evaluado:** RA1  
**CE:** RA1.b y RA1.g  
**Tipo:** caso práctico de planificación de desarrollo  
**Actividad:** P02.1 – Diseñando el proceso de CartagoFit  
**Producto:** memoria técnica y modelos de organización del trabajo  
**Modalidad:** individual  
**Material permitido:** UD01, UD02 y documentación oficial indicada por el profesor  

Se obtiene:

```text
NOTA RA1.b = 0–10

NOTA RA1.g = 0–10
```

independientemente.

---

# 102. Rúbrica definitiva I-RA1-02

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA1.b** | Identifica y organiza las fases de desarrollo de una aplicación informática | Confunde fases, omite etapas esenciales o las aplica incoherentemente | Reconoce las fases principales y proporciona ejemplos básicos | Relaciona correctamente análisis, diseño, implementación, pruebas, documentación, despliegue y mantenimiento con CartagoFit y propone una organización coherente | Distingue además fase, iteración e incremento, justifica relaciones y adapta razonadamente la organización al contexto | **100 % del CE** |
| **RA1.g** | Identifica características y escenarios de uso de metodologías ágiles | Confunde agilidad con ausencia de planificación o aplica términos sin relación con el caso | Reconoce algunas características ágiles y propone una organización sencilla | Analiza el escenario, justifica el enfoque, prioriza trabajo y relaciona correctamente feedback, adaptación, iteraciones/incrementos y prácticas ágiles | Compara alternativas, identifica límites del enfoque elegido y diseña una respuesta especialmente coherente ante cambios y restricciones | **100 % del CE** |

La nota resumen informativa de P02.1 será:

```text
(RA1.b + RA1.g) / 2
```

pero no sustituye las notas individuales de cada CE.

---

# 103. Temporalización definitiva

| Sesión | Contenido | Actividades |
|---:|---|---|
| 1 | Ingeniería del software y ciclo de vida | A02.1 |
| 2 | Análisis, diseño, implementación, pruebas, despliegue y mantenimiento | ReservaLab |
| 3 | Modelos de proceso: cascada, V, iterativo e incremental | A02.2 |
| 4 | Principios y características de agilidad | casos comparados |
| 5 | Scrum: responsabilidades, eventos y artefactos | A02.3 |
| 6 | Kanban, flujo y trabajo en curso | tablero + ejercicio |
| 7 | Historias, criterios, prioridad y feedback | A02.4–5 |
| 8 | P02.1 — desarrollo | CartagoFit |
| 9 | P02.1 — finalización/evaluación | I-RA1-02 |

**Total: 9 periodos.**

---

# 104. Autoevaluación — soluciones

```text
1 → A
2 → A
3 → A
4 → A
5 → B
6 → A
7 → A
8 → A
9 → A
10 → A
```

---

# PARTE B — MATERIAL DEL PROFESOR

# 105. Finalidad docente

El principal objetivo no es que el alumnado memorice:

```text
Scrum = esto

Kanban = aquello
```

sino que comprenda:

```text
el software sigue un proceso

las fases existen aunque
puedan organizarse de formas diferentes

el contexto condiciona el proceso

agilidad implica adaptación,
no ausencia de disciplina.
```

---

# 106. Distinciones que deben quedar claras

## Fase

Ejemplo:

```text
análisis.
```

## Modelo de proceso

Ejemplo:

```text
cascada.
```

## Framework

Ejemplo:

```text
Scrum.
```

## Técnica/práctica

Ejemplo:

```text
historia de usuario

tablero

retrospectiva.
```

No conviene penalizar terminología secundaria cuando el alumno demuestra el concepto, pero sí corregir confusiones estructurales.

---

# 107. Solución A02.1

| Acción | Fase principal |
|---|---|
| entrevistar usuarios | análisis |
| diseñar estructura | diseño |
| programar | implementación |
| comprobar requisitos | pruebas |
| redactar documentación | documentación |
| publicar versión | despliegue |
| corregir problemas posteriores | mantenimiento |

Debe aceptarse:

```text
una acción puede aparecer
en más de una fase
```

si está bien justificado.

---

# 108. Solución A02.2

Una posibilidad:

```text
Incremento 1
autenticación

Incremento 2
consultar disponibilidad

Incremento 3
crear reservas

Incremento 4
cancelar

Incremento 5
notificaciones
```

Lo evaluable es:

```text
orden razonable

valor progresivo

capacidad de validación.
```

---

# 109. Solución A02.3

Ejemplo:

## Product Backlog

```text
consultar disponibilidad

crear reserva

cancelar reserva

gestionar espacios
```

## Sprint

Objetivo:

```text
consultar y reservar.
```

## Incremento

Aplicación capaz de:

```text
mostrar disponibilidad
+
crear una reserva válida.
```

## Review

Recoger feedback de profesores.

## Retrospective

Ejemplo:

> Las tareas llegan demasiado grandes; en el siguiente Sprint las dividiremos antes de comenzar.

---

# 110. Solución A02.4

Historia:

> Como profesor quiero consultar espacios disponibles para elegir uno antes de reservar.

Posibles criterios:

```text
solo mostrar espacios habilitados

excluir intervalos ocupados

mostrar fecha/hora
```

Debe aceptarse cualquier formulación coherente.

---

# 111. Solución A02.5

El nuevo requisito:

```text
aprobación de laboratorios
```

puede afectar:

```text
análisis

diseño

implementación

pruebas

documentación.
```

En un proceso iterativo puede incorporarse al backlog y repriorizarse.

Debe valorarse que el alumno comprenda:

```text
el cambio no afecta únicamente
a "programar una condición".
```

---

# 112. Solución orientativa P02.1 — RA1.b

Una respuesta adecuada podría incluir:

## Análisis

```text
identificar usuarios

requisitos de reservas

reglas de plazas

cancelaciones.
```

## Diseño

```text
organizar componentes

datos

interacción.
```

## Implementación

```text
desarrollar funcionalidades.
```

## Pruebas

```text
comprobar reservas

plazas

cancelaciones

reglas.
```

## Documentación

```text
uso

decisiones técnicas.
```

## Despliegue

```text
publicar piloto.
```

## Mantenimiento

```text
corregir

adaptar

añadir necesidades.
```

---

# 113. Organización esperable de CartagoFit

Los datos:

```text
requisitos incompletos

pilotos disponibles

feedback frecuente

equipo pequeño

necesidad de versión temprana
```

apoyan especialmente un desarrollo:

```text
iterativo

incremental

con prácticas ágiles.
```

No debe exigirse necesariamente:

```text
Scrum completo
```

como única respuesta.

---

# 114. Posibles incrementos P02.1

Ejemplo:

```text
1. gestión básica de clientes

2. catálogo/consulta de clases

3. reserva de plazas

4. cancelaciones

5. validación de cuota

6. mejoras posteriores
```

Otra secuencia puede ser mejor si está correctamente justificada.

---

# 115. Solución orientativa RA1.g

El alumno debería identificar aspectos como:

```text
cambios previsibles

usuarios piloto

feedback disponible

prioridades cambiantes

entregas progresivas.
```

Por tanto, puede justificar:

```text
enfoque ágil apropiado.
```

Una respuesta avanzada deberá reconocer también límites:

```text
necesidad de planificación

calidad

documentación necesaria

restricciones presupuestarias.
```

---

# 116. Backlog orientativo

```text
1. Crear/gestionar clientes

2. Consultar clases

3. Consultar plazas

4. Reservar plaza

5. Cancelar reserva

6. Validar cuota activa

7. Notificar confirmaciones

8. Gestionar clases

9. Informes

10. Estadísticas
```

No debe corregirse simplemente por coincidencia con este orden.

La justificación importa más.

---

# 117. Tablero orientativo

```text
POR HACER
- Validar cuota
- Cancelación
- Notificación

EN CURSO [WIP 2]
- Reserva
- Plazas

REVISIÓN
- Consulta clases

TERMINADO
- Cliente
- Login
```

El alumno debe explicar que:

```text
WIP
```

pretende limitar acumulación de trabajo simultáneo.

---

# 118. Cambio de requisito

Nuevo requisito:

```text
cuota activa
```

Posible tratamiento:

```text
añadir/modificar elemento de backlog

revisar prioridad

analizar impacto

actualizar criterios

incorporar en próximo incremento
o Sprint según prioridad.
```

No debe aceptarse como respuesta completa:

```text
"añado un if".
```

porque RA1.g evalúa el proceso, no la codificación.

---

# 119. Errores previsibles

## Error 1

> Primero programamos y luego preguntamos al cliente.

Intervención:

```text
¿cómo sabemos qué debemos programar?
```

## Error 2

> Scrum es una metodología para hacer software rápido.

Intervención:

Reorientar hacia:

```text
inspección

adaptación

entrega de valor

trabajo iterativo.
```

## Error 3

> Agile significa no documentar.

Intervención:

Diferenciar:

```text
priorizar
```

de:

```text
eliminar.
```

## Error 4

> Kanban = cuatro columnas.

Intervención:

Preguntar:

```text
¿qué información aporta el flujo?

¿qué es trabajo en curso?
```

## Error 5

> Cascada siempre está mal.

Intervención:

Buscar un escenario con:

```text
requisitos estables

fuerte regulación

entregables contractuales.
```

---

# 120. Medidas de apoyo

Para alumnado con dificultades:

- proporcionar tarjetas con fases para ordenar;
- utilizar un caso sencillo antes de CartagoFit;
- proporcionar plantilla de backlog;
- facilitar un tablero vacío;
- dar ejemplos de situaciones y pedir elegir enfoque;
- utilizar una tabla comparativa de modelos.

No proporcionar la justificación final del caso evaluable.

---

# 121. Ampliación para alumnado avanzado

Puede pedirse comparar:

```text
Scrum

Kanban

Scrumban

cascada

proceso híbrido
```

para un mismo proyecto.

También puede analizar:

```text
coste de cambiar requisitos
```

en diferentes momentos del desarrollo.

No genera CE adicional.

---

# 122. Recuperación asociada

Instrumento:

# IR-RA1-01

Bloques directamente relacionados con UD02:

```text
RA1.b

RA1.g
```

Si el RA1 no está superado y únicamente:

```text
RA1.g
```

necesita nueva evidencia, el alumno realizará únicamente:

```text
bloque RA1.g.
```

No repetirá P02.1 completa.

---

# 123. Trazabilidad UD02

| RA | CE | Contenido | Actividad formativa | Instrumento | Evidencia |
|---|---|---|---|---|---|
| RA1 | b | fases y organización del ciclo de vida | A02.1–2 | P02.1 / I-RA1-02 | E-RA1.b-01/03 |
| RA1 | g | características y escenarios ágiles | A02.3–5 | P02.1 / I-RA1-02 | E-RA1.g-01/05 |

---

# 124. Situación completa de RA1 tras UD02

## UD01

```text
RA1.a → evaluado
RA1.c → evaluado
RA1.d → evaluado
RA1.e → evaluado
RA1.f → evaluado
```

## UD02

```text
RA1.b → evaluado
RA1.g → evaluado
```

Resultado:

```text
RA1.a ✔
RA1.b ✔
RA1.c ✔
RA1.d ✔
RA1.e ✔
RA1.f ✔
RA1.g ✔
```

# RA1 COMPLETAMENTE CUBIERTO

---

# 125. Cálculo definitivo de RA1

Cada CE tiene el mismo peso:

```text
1 / 7
```

Por tanto:

```text
RA1 =
(
 RA1.a
+RA1.b
+RA1.c
+RA1.d
+RA1.e
+RA1.f
+RA1.g
) / 7
```

I-RA1-02 no recibe un porcentaje arbitrario.

Su influencia deriva exclusivamente de:

```text
RA1.b

RA1.g.
```

---

# 126. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA1

**CE evaluados:**

```text
RA1.b
RA1.g
```

**CE reforzado sin nueva calificación:**

```text
RA1.f
```

**¿Se introduce contenido perteneciente evaluativamente a otro RA?**

# NO

Las menciones a UML, testing, Git, CI u otras herramientas se limitan a contexto del proceso.

Cuando aparece contenido perteneciente a otros RA queda expresamente identificado como conocimiento auxiliar.

**¿Algún instrumento evalúa otro RA?**

# NO

```text
I-RA1-02
→ exclusivamente RA1
```

---

# 127. Checklist final UD02

```text
☑ 9 periodos.

☑ RA1 único.

☑ RA1.b oficial.

☑ RA1.g oficial.

☑ RA1.f solo reforzado.

☑ Ciclo de vida.

☑ Análisis.

☑ Requisitos.

☑ Diseño.

☑ Implementación.

☑ Pruebas como fase.

☑ Documentación.

☑ Despliegue.

☑ Mantenimiento.

☑ Cascada.

☑ Modelo V.

☑ Iterativo.

☑ Incremental.

☑ Agilidad.

☑ Manifiesto Ágil.

☑ Scrum.

☑ Roles/responsabilidades.

☑ Eventos.

☑ Backlogs.

☑ Sprint.

☑ Incremento.

☑ Kanban.

☑ WIP.

☑ Historias de usuario.

☑ Criterios de aceptación.

☑ Priorización.

☑ Feedback.

☑ Gestión del cambio.

☑ ReservaLab.

☑ CartagoFit.

☑ Actividades guiadas.

☑ Consolidación.

☑ Ampliación.

☑ Resumen.

☑ Glosario.

☑ Autoevaluación.

☑ P02.1.

☑ I-RA1-02.

☑ RA1.b con nota 0–10.

☑ RA1.g con nota 0–10.

☑ Rúbrica armonizada.

☑ Evidencias.

☑ Soluciones profesor.

☑ Recuperación.

☑ Diagramas previstos.

☑ Sin ponderación antigua.

☑ Trazabilidad.

☑ Aislamiento superado.

☑ RA1 cerrado.
```

# UD02 — VERSIÓN MAESTRA DEFINITIVA