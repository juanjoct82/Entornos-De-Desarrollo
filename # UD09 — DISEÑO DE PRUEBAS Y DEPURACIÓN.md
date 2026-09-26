# UD09 — DISEÑO DE PRUEBAS Y DEPURACIÓN

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 9 periodos lectivos  
**Resultado de Aprendizaje:** RA3  
**Práctica evaluable:** P09.1  
**Instrumento:** I-RA3-01  

**IDE de referencia:** IntelliJ IDEA 2026.2  
**JDK:** Eclipse Temurin JDK 25 LTS  
**Lenguaje de trabajo:** Java  

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

Que un programa:

```text
compile
```

no significa que:

```text
funcione correctamente.
```

Este programa compila:

```java
public static double calcularPrecio(
        int horas,
        double tarifaHora) {

    return horas + tarifaHora;
}
```

Pero si:

```text
horas = 3
tarifaHora = 2.50
```

el resultado debería ser:

```text
7.50
```

y el método devuelve:

```text
5.50
```

Tenemos un:

# DEFECTO LÓGICO.

El compilador puede detectar errores de sintaxis o tipos, pero no conoce necesariamente:

```text
qué comportamiento
esperaba el cliente.
```

Por eso necesitamos:

# PRUEBAS + DEPURACIÓN.

---

# 2. Resultado de Aprendizaje

## RA3

**Verifica el funcionamiento de programas diseñando y realizando pruebas.**

---

# 3. Criterios de evaluación de UD09

En esta unidad se evalúan exclusivamente:

## RA3.a

**Se han identificado los diferentes tipos de pruebas.**

## RA3.b

**Se han definido casos de prueba.**

## RA3.c

**Se han identificado las herramientas de depuración y prueba de aplicaciones ofrecidas por el entorno de desarrollo.**

## RA3.d

**Se han utilizado herramientas de depuración para definir puntos de ruptura y seguimiento.**

## RA3.e

**Se han utilizado las herramientas de depuración para examinar y modificar el comportamiento de un programa en tiempo de ejecución.**

La redacción corresponde al currículo vigente del módulo 0487.

---

# 4. CE reservados para UD10

No se evaluarán todavía:

```text
RA3.f
→ pruebas unitarias
   de clases y funciones

RA3.g
→ pruebas automáticas

RA3.h
→ documentación de incidencias

RA3.i
→ dobles de prueba
```

Pertenecen evaluativamente a:

# UD10.

---

# 5. Contenidos curriculares relacionados

El currículo incluye expresamente:

```text
planificación de pruebas

pruebas funcionales

pruebas estructurales

pruebas de regresión

procedimientos y casos de prueba

cubrimiento

valores límite

clases de equivalencia
```

entre los contenidos de diseño y realización de pruebas.

---

# 6. ¿Qué aprenderemos?

Al finalizar la unidad deberás poder:

- explicar por qué probar software;
- distinguir error humano, defecto y fallo;
- identificar pruebas funcionales;
- identificar pruebas estructurales;
- comprender la finalidad de las pruebas de regresión;
- distinguir prueba positiva y negativa;
- identificar clases de equivalencia;
- diseñar pruebas con valores límite;
- escribir casos de prueba reproducibles;
- definir entrada, precondiciones y resultado esperado;
- distinguir resultado esperado y resultado obtenido;
- identificar herramientas de ejecución y depuración del IDE;
- diferenciar Run y Debug;
- crear puntos de ruptura;
- utilizar puntos de ruptura condicionales;
- ejecutar paso a paso;
- utilizar Step Over, Step Into y Step Out;
- utilizar Run to Cursor cuando sea útil;
- inspeccionar variables;
- interpretar la pila de llamadas;
- crear Watches;
- evaluar expresiones;
- modificar temporalmente variables durante una sesión de depuración;
- utilizar la depuración para confirmar o descartar hipótesis;
- localizar un defecto mediante evidencia y no mediante cambios aleatorios.

---

# 7. Utilidad profesional

Supongamos que recibimos esta incidencia:

> Para una estancia de 6 horas, CartagoPark cobra 18 €, pero debería cobrar 12 €.

Una estrategia poco profesional sería:

```text
abrir código
↓
cambiar líneas al azar
↓
ejecutar
↓
seguir probando
```

Una estrategia profesional:

```text
reproducir el fallo
↓
definir qué esperábamos
↓
localizar dónde diverge
↓
detener ejecución
↓
examinar variables
↓
seguir el flujo
↓
formular hipótesis
↓
comprobarla
```

---

# 8. Probar y depurar no son lo mismo

## Probar

Busca responder:

```text
¿el programa se comporta
como debería?
```

## Depurar

Busca responder:

```text
¿por qué está ocurriendo
este comportamiento?
```

---

# 9. Relación entre ambas

```text
PRUEBA
↓
detecta comportamiento incorrecto
↓
DEPURACIÓN
↓
localiza causa
↓
CORRECCIÓN
↓
NUEVA PRUEBA
```

---

# 10. Error, defecto y fallo

Utilizaremos una distinción introductoria.

## Error humano

Una persona toma una decisión equivocada.

Ejemplo:

```text
programador utiliza +
en vez de *
```

## Defecto / bug

La equivocación queda incorporada al software.

```java
return horas + tarifaHora;
```

## Fallo

Durante la ejecución observamos un comportamiento incorrecto:

```text
3 h × 2,50 €
esperado = 7,50 €

obtenido = 5,50 €
```

---

# 11. No todos los defectos producen fallos siempre

Podemos tener un defecto que solo aparezca:

```text
con determinados datos

en determinada rama

bajo determinada condición.
```

Por eso necesitamos diseñar pruebas:

# CON INTENCIÓN.

---

# 12. ¿Qué es una prueba?

Una prueba ejecuta o examina una parte del software bajo determinadas condiciones para comprobar:

```text
si el resultado observado
coincide con el esperado.
```

---

# 13. Oráculo de prueba

Necesitamos saber:

```text
qué resultado debería producirse.
```

A esa fuente de expectativa podemos llamarla:

```text
oráculo de prueba.
```

Puede proceder de:

```text
requisito

especificación

regla de negocio

resultado conocido.
```

---

# 14. Ejemplo

Requisito:

> Cada hora cuesta 2,50 €.

Entrada:

```text
3 horas
```

Resultado esperado:

```text
7,50 €
```

Si el programa devuelve:

```text
5,50 €
```

podemos afirmar que:

```text
la prueba falla.
```

---

# 15. Tipos de pruebas — visión general

El currículo cita expresamente:

```text
pruebas funcionales

pruebas estructurales

pruebas de regresión.
```


No son las únicas clasificaciones posibles.

Un mismo ensayo puede clasificarse:

```text
desde varios puntos de vista.
```

---

# 16. Pruebas funcionales

Se centran en:

# QUÉ HACE EL SOFTWARE.

Partimos de:

```text
requisitos

entradas

salidas esperadas
```

sin necesitar estudiar inicialmente todos los detalles internos.

---

# 17. Ejemplo funcional

Requisito:

> Una estancia de hasta 5 horas se cobra a 2,50 € por hora.

Caso:

```text
entrada:
4 horas

esperado:
10,00 €
```

Nos importa:

```text
resultado funcional.
```

---

# 18. Caja negra

Las pruebas funcionales suelen relacionarse con una perspectiva:

```text
CAJA NEGRA
```

porque podemos diseñarlas basándonos en:

```text
entradas
+
resultados
```

sin utilizar inicialmente la estructura interna.

---

# 19. Pruebas estructurales

Se diseñan teniendo en cuenta:

```text
la estructura interna
del código.
```

Podemos examinar:

```text
if

else

bucles

ramas

condiciones.
```

---

# 20. Caja blanca

Esta perspectiva suele denominarse:

```text
CAJA BLANCA.
```

Ejemplo:

```java
if (horas <= 5) {
    ...
} else {
    ...
}
```

Un diseño estructural puede buscar ejecutar:

```text
rama horas <= 5

y

rama horas > 5.
```

---

# 21. Cubrimiento

El currículo menciona:

```text
cubrimiento
```

como técnica relacionada con pruebas de código.

La idea introductoria es preguntarnos:

```text
¿Qué partes del código
han sido recorridas
por nuestras pruebas?
```

En UD09 no realizaremos todavía un sistema automatizado de cobertura.

---

# 22. Pruebas de regresión

Buscan comprobar que:

```text
un cambio
```

no ha estropeado:

```text
comportamiento
que ya funcionaba.
```

---

# 23. Ejemplo de regresión

Versión 1:

```text
tarifa normal
→ correcta
```

Añadimos:

```text
tarifa máxima diaria.
```

Debemos comprobar:

```text
la tarifa normal
sigue funcionando.
```

Eso es una:

# PRUEBA DE REGRESIÓN.

---

# 24. Regresión no significa repetir todo sin criterio

Idealmente seleccionamos:

```text
pruebas relevantes
```

que permitan detectar:

```text
efectos secundarios
del cambio.
```

En UD10 veremos cómo automatizar muchas de estas comprobaciones.

---

# 25. CONOCIMIENTO AUXILIAR NO EVALUADO

Las pruebas automatizadas y unitarias pertenecen evaluativamente a:

```text
RA3.f
RA3.g
```

en UD10.

Aquí podemos hablar de:

```text
regresión
```

como concepto y realizar comprobaciones manuales.

No se califica todavía:

```text
JUnit.
```

---

# 26. Pruebas positivas

Comprueban casos válidos.

Ejemplo:

```text
horas = 4
```

cuando el dominio admite:

```text
horas >= 1.
```

---

# 27. Pruebas negativas

Comprueban:

```text
datos no válidos

situaciones incorrectas

errores esperados.
```

Ejemplo:

```text
horas = -2.
```

Pregunta:

> ¿Cómo debería reaccionar el programa?

---

# 28. Clases de equivalencia

La idea consiste en agrupar valores que:

```text
esperamos que sean tratados
de forma equivalente
por el programa.
```

---

# 29. Ejemplo

Regla:

```text
1–5 horas
→ tarifa normal

6–10 horas
→ tarifa reducida

>10
→ tarifa máxima diaria
```

Podemos identificar:

```text
Clase A
1..5

Clase B
6..10

Clase C
>10

Clase D
<=0
```

---

# 30. ¿Por qué ayuda?

En vez de probar:

```text
1
2
3
4
5
6
7
8
...
```

podemos seleccionar valores representativos.

Por ejemplo:

```text
3

8

12

0.
```

Esto no garantiza ausencia de errores, pero mejora el diseño sistemático de las pruebas.

---

# 31. Valores límite

Los errores aparecen con frecuencia:

# CERCA DE LOS LÍMITES.

Si una condición dice:

```java
if (horas <= 5)
```

son especialmente interesantes:

```text
4

5

6.
```

---

# 32. Técnica alrededor del límite

Para un límite:

```text
5
```

podemos probar:

```text
5 - 1 = 4

5

5 + 1 = 6.
```

---

# 33. Error típico de frontera

Programador escribe:

```java
if (horas < 5)
```

cuando el requisito decía:

```text
hasta 5 horas incluidas.
```

Caso:

```text
horas = 5
```

detectará probablemente el problema.

---

# 34. Actividad A09.1 — Equivalencias y límites

Regla:

```text
edad < 18
→ menor

18..64
→ adulto

>=65
→ senior
```

Define:

- clases válidas;
- clases inválidas si procede;
- valores representativos;
- valores límite.

---

# 35. ¿Qué es un caso de prueba?

Un caso de prueba describe:

```text
condiciones

entrada

acción

resultado esperado
```

de forma suficientemente clara para que otra persona pueda repetirlo.

---

# 36. Plantilla básica

| Campo | Contenido |
|---|---|
| ID | CP-01 |
| Objetivo | Comprobar tarifa normal |
| Precondición | Aplicación disponible |
| Entrada | 4 horas |
| Acción | Calcular tarifa |
| Esperado | 10,00 € |
| Obtenido | Se rellena al ejecutar |
| Resultado | PASA / FALLA |

---

# 37. Un caso no es solo una entrada

Insuficiente:

```text
probar con 5.
```

Mejor:

```text
ID CP-03

entrada:
5 horas

resultado esperado:
12,50 €

objetivo:
comprobar límite superior
de tarifa normal.
```

---

# 38. Resultado esperado antes de ejecutar

No debemos ejecutar primero y después afirmar:

> Eso era lo esperado.

El resultado esperado debe derivarse de:

```text
requisito
```

antes de ver el resultado real.

---

# 39. Precondición

Una precondición especifica qué debe cumplirse:

```text
antes de ejecutar
la prueba.
```

Ejemplo:

```text
vehículo registrado

tarifa configurada en 2,50 €

estancia abierta.
```

---

# 40. Datos de entrada

Deben ser:

```text
concretos

reproducibles.
```

No:

```text
“una tarifa cualquiera”.
```

Mejor:

```text
horas = 5
tarifa = 2.50
abonado = false.
```

---

# 41. Resultado esperado

Debe poder comprobarse.

Malo:

```text
debería funcionar bien.
```

Mejor:

```text
devuelve 12.50.
```

---

# 42. Actividad A09.2 — Diseña casos

Para:

```java
public static boolean puedeAcceder(
        int edad) {

    return edad >= 18;
}
```

crea casos para:

```text
valor normal válido

límite

valor inmediatamente inferior

valor extremo

valor inválido
si el dominio lo prohíbe.
```

---

# 43. Matriz de pruebas

Para funciones sencillas podemos organizar:

| ID | Entrada | Técnica | Esperado |
|---|---|---|---|
| CP01 | 4 h | equivalencia | tarifa normal |
| CP02 | 5 h | límite | tarifa normal |
| CP03 | 6 h | límite | tarifa reducida |
| CP04 | 10 h | límite | tarifa reducida |
| CP05 | 11 h | límite | máximo diario |
| CP06 | 0 h | inválido | rechazo/error |

---

# 44. Qué es depurar

Depurar significa investigar el comportamiento del programa durante su ejecución para:

```text
comprender

localizar

confirmar

corregir
```

defectos.

---

# 45. Run vs Debug

## Run

```text
ejecuta normalmente.
```

## Debug

```text
ejecuta con el depurador
conectado
```

y nos permite:

```text
detener

inspeccionar

seguir

evaluar

modificar temporalmente
el estado.
```

IntelliJ utiliza la misma configuración básica de ejecución y puede lanzar una sesión Debug asociando el depurador a la aplicación.

---

# 46. Herramientas del IDE

IntelliJ IDEA 2026.2 proporciona, entre otras:

```text
breakpoints

Debug tool window

Frames

Variables

Watches

Evaluate Expression

stepping

Run to Cursor.
```

La ventana Debug permite examinar pila, threads, variables y watches.

---

# 47. RA3.c — identificar herramientas

Para superar RA3.c debes comprender:

```text
qué herramienta existe

qué función cumple

cuándo utilizarla.
```

No basta:

```text
“IntelliJ tiene debugger”.
```

---

# 48. CAPTURA UD09-01 — Run / Debug

Debe mostrar:

```text
ejecución Run

frente a

ejecución Debug.
```

La leyenda debe explicar:

```text
qué cambia
entre ambas.
```

---

# 49. Punto de ruptura

Un breakpoint indica:

> Cuando la ejecución llegue aquí, detente.

IntelliJ define los breakpoints como marcadores que suspenden la ejecución para poder examinar el estado y continuar paso a paso.

---

# 50. Crear breakpoint

En el editor:

```text
clic en gutter
junto al número de línea
```

o, con el keymap Windows de referencia:

```text
Ctrl + F8.
```

Los atajos dependen del keymap configurado. La documentación 2026.2 mantiene `Ctrl+F8` en el mapa Windows predeterminado.

---

# 51. CAPTURA UD09-02 — Breakpoint

Debe mostrar:

```text
breakpoint

línea seleccionada

indicador visual.
```

---

# 52. Dónde colocar un breakpoint

No siempre:

```text
en la primera línea.
```

Pregunta:

> ¿Dónde puede empezar a aparecer el comportamiento incorrecto?

Si falla:

```text
precio final
```

puede ser útil detenerse:

```text
antes o dentro
del cálculo.
```

---

# 53. Breakpoint condicional

Podemos detener únicamente cuando:

```text
se cumple una condición.
```

Ejemplo:

```text
horas == 6
```

Esto evita detenernos:

```text
50 veces
```

si buscamos únicamente un caso concreto.

IntelliJ permite condiciones adicionales en breakpoints.

---

# 54. Ejemplo

```java
for (int horas = 1;
     horas <= 24;
     horas++) {

    double precio =
            calcularPrecio(horas);
}
```

Queremos investigar:

```text
horas = 11.
```

Breakpoint condicionado:

```text
horas == 11
```

---

# 55. CAPTURA UD09-03 — Breakpoint condicional

Debe mostrar:

```text
línea

condición

horas == 11.
```

---

# 56. Seguimiento paso a paso

Una vez detenido el programa podemos controlar su ejecución.

Acciones principales:

```text
Step Over

Step Into

Step Out

Resume

Run to Cursor.
```

IntelliJ documenta actualmente todas estas acciones para la ejecución paso a paso.

---

# 57. Step Over

Ejecuta la línea actual y avanza:

```text
sin entrar
en la implementación
de los métodos llamados.
```

Keymap Windows de referencia:

```text
F8.
```


---

# 58. Ejemplo Step Over

```java
double subtotal =
        calcularSubtotal(horas);

double total =
        aplicarDescuento(subtotal);
```

Si estamos en:

```text
calcularSubtotal(...)
```

y usamos Step Over:

```text
no entramos
en calcularSubtotal.
```

Avanzamos a:

```text
aplicarDescuento(...).
```

---

# 59. Step Into

Entra dentro del método llamado.

Keymap Windows:

```text
F7.
```

Útil cuando sospechamos:

```text
que el defecto
está dentro
del método.
```


---

# 60. Step Out

Sale del método actual y vuelve al llamador.

Keymap Windows:

```text
Shift + F8.
```

Útil cuando:

```text
ya hemos inspeccionado
lo necesario
dentro del método.
```


---

# 61. Resume Program

Continúa normalmente hasta:

```text
siguiente breakpoint

final

excepción
```

según el flujo.

Keymap Windows:

```text
F9.
```


---

# 62. Run to Cursor

Continúa hasta:

```text
la línea
donde situamos
el cursor.
```

En el keymap Windows:

```text
Alt + F9.
```

No necesitamos crear un breakpoint permanente.

---

# 63. Smart Step Into

Si una línea contiene:

```java
guardar(validar(normalizar(datos)));
```

podemos querer entrar concretamente en:

```text
validar()
```

sin entrar primero en otro método.

IntelliJ ofrece:

```text
Smart Step Into
```

para seleccionar la llamada que queremos inspeccionar.

---

# 64. No memorices únicamente teclas

Las combinaciones:

```text
pueden cambiar
según sistema/keymap.
```

Lo evaluable es:

```text
comprender la operación
y utilizarla.
```

---

# 65. Variables

Cuando la ejecución está detenida podemos observar:

```text
variables locales

parámetros

campos de objetos

valores.
```

La pestaña Variables del Debug tool window permite analizar el estado actual del programa.

---

# 66. CAPTURA UD09-04 — Variables

Debe mostrar:

```text
horas

tarifa

subtotal

total
```

durante una ejecución suspendida.

---

# 67. Inspección inline

IntelliJ también puede mostrar:

```text
valores junto al código
```

mientras depuramos.

Esto permite relacionar:

```text
línea
+
estado.
```

---

# 68. Frames

La pestaña Frames permite observar:

```text
la pila de llamadas.
```

Ejemplo:

```text
main()
↓
procesarEstancia()
↓
calcularPrecio()
```

---

# 69. Pila de llamadas

Nos ayuda a responder:

```text
¿Cómo hemos llegado
hasta este método?
```

Es especialmente útil cuando:

```text
un mismo método
puede llamarse
desde varios lugares.
```

---

# 70. CAPTURA UD09-05 — Frames

Debe mostrar:

```text
al menos dos métodos
en la pila.
```

---

# 71. Watches

Un Watch permite seguir una expresión que nos interesa.

Ejemplo:

```text
horas * tarifaHora
```

o:

```text
precio > TARIFA_MAXIMA
```

IntelliJ permite gestionar watches desde el contexto de depuración.

---

# 72. ¿Para qué sirven?

En lugar de calcular mentalmente:

```text
una expresión
en cada paso
```

podemos observarla:

```text
automáticamente
mientras avanzamos.
```

---

# 73. CAPTURA UD09-06 — Watch

Debe mostrar al menos:

```text
una expresión observada

+
su valor.
```

---

# 74. Evaluate Expression

Permite evaluar una expresión:

```text
en el contexto actual
del programa suspendido.
```

Keymap Windows de referencia:

```text
Alt + F8.
```


---

# 75. Ejemplos

Podemos evaluar:

```java
horas * tarifaHora
```

o:

```java
calcularPrecio(6)
```

si el contexto lo permite.

---

# 76. Precaución

Evaluar ciertos métodos puede:

```text
modificar estado

producir efectos laterales.
```

El propio debugger advierte de que determinadas expresiones evaluadas pueden afectar al comportamiento del programa.

Por tanto:

# NO EJECUTES CUALQUIER EXPRESIÓN SIN PENSAR.

---

# 77. Modificar una variable durante Debug

Una de las capacidades más potentes consiste en:

```text
cambiar temporalmente
el valor
de una variable
```

mientras la aplicación está suspendida.

---

# 78. Ejemplo

Estado actual:

```text
horas = 6
```

Podemos cambiar temporalmente:

```text
horas = 5
```

y continuar.

Esto permite preguntar:

> ¿Cambiaría el comportamiento si el valor fuese otro?

---

# 79. Set Value

En IntelliJ podemos seleccionar una variable y utilizar:

```text
Set Value
```

o la acción equivalente.

La documentación 2026.2 indica que el valor puede modificarse desde Variables; en la configuración actual puede usarse `F2` o la opción contextual `Set Value`.

---

# 80. CAPTURA UD09-07 — Set Value

Debe demostrar:

```text
valor original

cambio temporal

valor modificado.
```

---

# 81. Cambiar en Debug no corrige el programa

Muy importante:

```text
modificar una variable
durante Debug
```

NO significa:

```text
modificar permanentemente
el código fuente.
```

Al ejecutar otra vez:

```text
el programa
volverá a seguir
el código real.
```

---

# 82. ¿Para qué sirve entonces?

Para:

```text
probar hipótesis

explorar escenarios

comprobar ramas

entender el defecto.
```

---

# 83. Hipótesis de depuración

Buena práctica:

```text
“No voy a tocar código todavía.

Creo que total supera
el máximo porque
la condición usa >=
en vez de >.

Voy a comprobarlo.”
```

---

# 84. Depuración basada en hipótesis

```text
OBSERVAR FALLO
↓
FORMULAR HIPÓTESIS
↓
ELEGIR BREAKPOINT
↓
OBSERVAR ESTADO
↓
SEGUIR EJECUCIÓN
↓
CONFIRMAR / DESCARTAR
```

---

# 85. Depuración por ensayo aleatorio

Mala estrategia:

```text
cambiar

ejecutar

cambiar

ejecutar

cambiar

ejecutar
```

sin comprender:

```text
qué está ocurriendo.
```

---

# 86. Trazado

El criterio RA3.d menciona:

```text
puntos de ruptura
y seguimiento.
```

En nuestra práctica el seguimiento se demostrará mediante:

```text
stepping

observación de variables

pila

watches

recorrido del flujo.
```

---

# 87. Logging breakpoint

IntelliJ permite configurar breakpoints que:

```text
registran información
```

sin necesariamente suspender la aplicación.

Esto puede resultar útil para:

```text
seguimiento
```

cuando no queremos detener la ejecución en cada paso.

---

# 88. Nivel requerido

No será obligatorio dominar:

```text
method breakpoints

field watchpoints

exception breakpoints avanzados

debug remoto
```

para superar UD09.

Pueden aparecer como:

```text
ampliación.
```

---

# 89. Caso guiado — TarifaParking

Código:

```java
public class TarifaParking {

    private static final double TARIFA_NORMAL =
            2.50;

    private static final double TARIFA_REDUCIDA =
            2.00;

    private static final double MAXIMO_DIA =
            20.00;

    public static double calcularPrecio(
            int horas) {

        if (horas <= 0) {
            throw new IllegalArgumentException(
                    "Horas no válidas"
            );
        }

        double precio;

        if (horas <= 5) {

            precio =
                    horas * TARIFA_NORMAL;

        } else if (horas <= 10) {

            precio =
                    horas * TARIFA_REDUCIDA;

        } else {

            precio =
                    horas * TARIFA_REDUCIDA;

            if (precio > MAXIMO_DIA) {
                precio = MAXIMO_DIA;
            }
        }

        return precio;
    }
}
```

---

# 90. Reglas

```text
1–5 horas
→ 2,50 €/h

6–10 horas
→ 2,00 €/h

>10 horas
→ 2,00 €/h
  con máximo 20 €.
```

---

# 91. Casos iniciales

| Horas | Esperado |
|---:|---:|
| 1 | 2,50 |
| 5 | 12,50 |
| 6 | 12,00 |
| 10 | 20,00 |
| 11 | 20,00 |
| 24 | 20,00 |

---

# 92. Introducir un defecto controlado

Para practicar la depuración podemos utilizar una versión con:

```java
} else if (horas < 10) {
```

en vez de:

```java
} else if (horas <= 10) {
```

Esto provoca:

```text
horas = 10
```

entre en otra rama.

---

# 93. ¿Siempre cambiará el resultado?

No necesariamente.

Éste es un aprendizaje importante.

Un defecto estructural:

```text
puede existir
```

aunque determinados datos produzcan:

```text
el mismo resultado final.
```

Por eso:

```text
casos de prueba
+
seguimiento estructural
```

pueden complementarse.

---

# 94. Segundo defecto

Podemos introducir:

```java
precio =
        horas + TARIFA_REDUCIDA;
```

en la rama de:

```text
6–10 horas.
```

Ahora:

```text
6 horas
```

produce claramente un fallo.

---

# 95. Actividad A09.3 — Diseña pruebas para TarifaParking

Define al menos:

```text
una clase inválida

tres clases válidas

límites alrededor de 5

límites alrededor de 10.
```

Incluye resultados esperados.

---

# 96. Actividad A09.4 — Localiza el defecto

Se entrega una versión defectuosa.

Procedimiento obligatorio:

```text
1. Ejecutar caso que falla.

2. Registrar esperado/obtenido.

3. Formular hipótesis.

4. Colocar breakpoint.

5. Debug.

6. Examinar variables.

7. Step Into/Over cuando proceda.

8. Identificar línea/condición responsable.

9. Explicar el defecto.
```

---

# 97. Actividad A09.5 — Variable modificada

Con el programa detenido:

```text
horas = 6
```

modifica temporalmente:

```text
horas = 5
```

y observa:

```text
qué rama sigue

qué valores cambian.
```

Después responde:

> ¿Has corregido el programa?

Respuesta esperada:

```text
No.

Solo hemos cambiado
el estado de esa ejecución.
```

---

# 98. Actividad A09.6 — Watch

Añade:

```text
precio > MAXIMO_DIA
```

como expresión observada.

Ejecuta casos:

```text
6

10

11

24.
```

Describe cuándo cambia el resultado del Watch.

---

# 99. Actividad A09.7 — Pila

Coloca el cálculo dentro de:

```text
procesarEstancia()
```

que a su vez sea llamado por:

```text
main().
```

Detén la ejecución dentro de:

```text
calcularPrecio().
```

Identifica en Frames:

```text
main

procesarEstancia

calcularPrecio.
```

---

# 100. Errores frecuentes al diseñar pruebas

## Error 1

Probar únicamente:

```text
un caso que funciona.
```

## Error 2

No probar límites.

## Error 3

No definir resultado esperado.

## Error 4

Elegir datos aleatorios sin justificar.

## Error 5

Confundir muchas pruebas con:

```text
buen diseño de pruebas.
```

---

# 101. Errores frecuentes al depurar

## Error 1

Colocar breakpoints:

```text
en todas las líneas.
```

## Error 2

Utilizar Step Into:

```text
en cada método
de las bibliotecas Java.
```

## Error 3

No mirar Variables.

## Error 4

Cambiar valores sin anotar:

```text
qué hipótesis
se está comprobando.
```

## Error 5

Corregir código antes de:

```text
localizar
la causa real.
```

---

# 102. Buenas prácticas de pruebas

- partir del requisito;
- definir esperado antes de ejecutar;
- incluir casos válidos e inválidos;
- utilizar valores límite;
- utilizar clases de equivalencia;
- conservar casos reproducibles;
- separar entrada, esperado y obtenido.

---

# 103. Buenas prácticas de depuración

- reproducir primero;
- formular hipótesis;
- colocar pocos breakpoints útiles;
- inspeccionar estado;
- utilizar stepping con intención;
- revisar pila;
- usar Watches para expresiones relevantes;
- modificar estado solo para experimentar;
- distinguir experimento de corrección definitiva.

---

# 104. CAPTURAS PREVISTAS

```text
CAPTURA UD09-01
Run frente a Debug

CAPTURA UD09-02
Breakpoint

CAPTURA UD09-03
Breakpoint condicional

CAPTURA UD09-04
Variables

CAPTURA UD09-05
Frames / call stack

CAPTURA UD09-06
Watch

CAPTURA UD09-07
Set Value

CAPTURA UD09-08
Evaluate Expression
```

---

# 105. Atajos de referencia

Con el keymap predeterminado de Windows en IntelliJ IDEA 2026.2:

| Acción | Atajo de referencia |
|---|---|
| Debug | `Shift+F9` |
| Resume | `F9` |
| Step Over | `F8` |
| Step Into | `F7` |
| Smart Step Into | `Shift+F7` |
| Step Out | `Shift+F8` |
| Run to Cursor | `Alt+F9` |
| Evaluate Expression | `Alt+F8` |
| Toggle Breakpoint | `Ctrl+F8` |
| View Breakpoints | `Ctrl+Shift+F8` |

Estos atajos son referencias del keymap Windows actual y pueden variar si el usuario modifica el mapa de teclas.

---

# 106. Ejercicios de consolidación

1. Diferencia prueba y depuración.
2. Diferencia error humano, defecto y fallo.
3. ¿Qué es una prueba funcional?
4. ¿Qué es una prueba estructural?
5. ¿Qué es regresión?
6. ¿Qué es caja negra?
7. ¿Qué es caja blanca?
8. ¿Qué es una clase de equivalencia?
9. ¿Qué es un valor límite?
10. ¿Por qué interesa probar 4, 5 y 6 si existe un límite en 5?
11. ¿Qué debe incluir un caso de prueba?
12. ¿Por qué definimos el esperado antes de ejecutar?
13. ¿Qué es una precondición?
14. Diferencia Run y Debug.
15. ¿Qué hace un breakpoint?
16. ¿Qué utilidad tiene un breakpoint condicional?
17. ¿Qué hace Step Over?
18. ¿Qué hace Step Into?
19. ¿Qué hace Step Out?
20. ¿Para qué sirve Run to Cursor?
21. ¿Qué información aparece en Variables?
22. ¿Qué muestra Frames?
23. ¿Qué es un Watch?
24. ¿Para qué sirve Evaluate Expression?
25. ¿Puede una expresión evaluada producir efectos laterales?
26. ¿Para qué sirve Set Value?
27. ¿Set Value modifica el fuente?
28. ¿Por qué conviene depurar mediante hipótesis?
29. ¿Qué CE trabaja breakpoints y seguimiento?
30. ¿Qué CE trabaja modificación del estado en ejecución?

---

# 107. Actividad de ampliación

Investiga en IntelliJ:

```text
logging breakpoints

exception breakpoints

method breakpoints.
```

Explica:

```text
qué problema
podría resolver
cada uno.
```

**Actividad no evaluable.**

---

# 108. Resumen

Las pruebas responden:

```text
¿funciona correctamente?
```

La depuración responde:

```text
¿por qué ocurre?
```

Tipos relevantes:

```text
funcionales

estructurales

regresión.
```

Técnicas de diseño:

```text
clases de equivalencia

valores límite

cubrimiento.
```

Herramientas principales:

```text
breakpoints

stepping

Variables

Frames

Watches

Evaluate Expression

Set Value.
```

---

# 109. Glosario

**Breakpoint:** punto donde el depurador puede suspender la ejecución.

**Breakpoint condicional:** breakpoint que se activa únicamente cuando se cumple una condición.

**Caja blanca:** enfoque de pruebas que considera la estructura interna.

**Caja negra:** enfoque centrado principalmente en entradas, salidas y comportamiento esperado.

**Caso de prueba:** especificación reproducible de condiciones, datos y resultado esperado.

**Clase de equivalencia:** conjunto de datos que se espera sean tratados de manera similar.

**Cubrimiento:** medida o idea relacionada con qué partes del código son recorridas por las pruebas.

**Debug:** ejecución con el depurador conectado.

**Defecto:** problema incorporado al software.

**Evaluate Expression:** herramienta para evaluar expresiones durante una ejecución suspendida.

**Fallo:** manifestación observable de comportamiento incorrecto.

**Frame:** contexto de una llamada dentro de la pila de ejecución.

**Prueba de regresión:** comprobación destinada a detectar que un cambio haya roto comportamiento previo.

**Prueba estructural:** prueba diseñada teniendo en cuenta estructura interna.

**Prueba funcional:** prueba centrada en comportamiento requerido.

**Set Value:** modificación temporal del valor de una variable durante la depuración.

**Stepping:** control paso a paso de la ejecución.

**Valor límite:** dato situado en o alrededor de una frontera relevante.

**Watch:** expresión observada durante la depuración.

---

# 110. Autoevaluación

### 1

Una prueba funcional se centra principalmente en:

A. requisitos y comportamiento  
B. colores del IDE  
C. Git  
D. UML

### 2

Una prueba estructural considera:

A. estructura interna del código  
B. únicamente interfaz gráfica  
C. hardware  
D. documentación

### 3

Una prueba de regresión pretende:

A. comprobar que un cambio no rompe comportamiento previo  
B. instalar Java  
C. crear UML  
D. versionar código

### 4

Para un límite 10 interesa probar especialmente:

A. 9, 10, 11  
B. 1, 2, 3  
C. solo 10  
D. ningún valor

### 5

Un caso de prueba debe incluir:

A. resultado esperado  
B. solo una captura  
C. una rama Git  
D. un diagrama UML

### 6

Un breakpoint:

A. puede suspender ejecución  
B. compila Java  
C. crea un JAR  
D. genera clases

### 7

Step Into:

A. entra en el método llamado  
B. termina el programa  
C. elimina el breakpoint  
D. crea una prueba JUnit

### 8

Variables permite:

A. examinar el estado actual  
B. generar UML  
C. realizar commits  
D. crear repositorios

### 9

Set Value:

A. permite cambiar temporalmente una variable durante Debug  
B. modifica siempre el fuente  
C. instala un plugin  
D. crea un test automático

### 10

RA3.f–i:

A. se reservan para UD10  
B. se evalúan todos en UD09  
C. pertenecen a RA4  
D. pertenecen a RA6

---

# 111. Soluciones de autoevaluación

```text
1 → A
2 → A
3 → A
4 → A
5 → A
6 → A
7 → A
8 → A
9 → A
10 → A
```

---

# 112. PRÁCTICA EVALUABLE P09.1

# DISEÑO DE PRUEBAS Y DEPURACIÓN DE CARTAGOPARK

**Modalidad:** individual  
**RA:** RA3  
**CE evaluados:** RA3.a, RA3.b, RA3.c, RA3.d, RA3.e  
**Instrumento:** I-RA3-01  
**IDE:** IntelliJ IDEA 2026.2  

---

# 113. Escenario

CartagoPark ha detectado errores en su módulo de cálculo de tarifas.

Reglas:

```text
1–5 horas
→ 2,50 €/hora

6–10 horas
→ 2,00 €/hora

más de 10 horas
→ 2,00 €/hora
  con máximo diario de 20 €

0 o menos
→ dato no válido
```

---

# 114. Código entregado

```java
public class TarifaCartagoPark {

    private static final double TARIFA_NORMAL =
            2.50;

    private static final double TARIFA_REDUCIDA =
            2.00;

    private static final double MAXIMO_DIA =
            20.00;

    public static double calcularPrecio(
            int horas) {

        if (horas <= 0) {
            throw new IllegalArgumentException(
                    "Horas no válidas"
            );
        }

        double precio;

        if (horas <= 5) {

            precio =
                    horas * TARIFA_NORMAL;

        } else if (horas <= 10) {

            // Código deliberadamente defectuoso
            precio =
                    horas + TARIFA_REDUCIDA;

        } else {

            precio =
                    horas * TARIFA_REDUCIDA;

            if (precio > MAXIMO_DIA) {
                precio = MAXIMO_DIA;
            }
        }

        return precio;
    }
}
```

---

# 115. Tarea A — Identificación de tipos de prueba

Para CartagoPark explica cómo aplicarías:

```text
prueba funcional

prueba estructural

prueba de regresión.
```

Para cada una debes indicar:

```text
qué comprobarías

qué información utilizarías

qué utilidad tendría.
```

**CE:** RA3.a

---

# 116. Evidencias RA3.a

```text
E-RA3.a-01
Clasificación razonada
de pruebas.

E-RA3.a-02
Aplicación de cada tipo
a CartagoPark.
```

---

# 117. Tarea B — Clases de equivalencia

Identifica al menos:

```text
horas <= 0

1..5

6..10

>10
```

y explica:

```text
por qué cada grupo
constituye una clase
relevante.
```

**CE:** RA3.b

---

# 118. Tarea C — Valores límite

Diseña pruebas alrededor de:

```text
0

5

10.
```

Incluye, cuando tenga sentido:

```text
límite - 1

límite

límite + 1.
```

---

# 119. Matriz mínima

Debes diseñar como mínimo:

| ID | Horas | Técnica | Esperado |
|---|---:|---|---:|
| CP01 | -1 | inválido/límite | excepción |
| CP02 | 0 | límite | excepción |
| CP03 | 1 | límite | 2,50 |
| CP04 | 4 | equivalencia | 10,00 |
| CP05 | 5 | límite | 12,50 |
| CP06 | 6 | límite | 12,00 |
| CP07 | 9 | equivalencia | 18,00 |
| CP08 | 10 | límite | 20,00 |
| CP09 | 11 | límite | 20,00 |
| CP10 | 24 | equivalencia | 20,00 |

Puedes añadir más.

---

# 120. Tarea D — Casos de prueba completos

Selecciona al menos:

```text
6
```

y documenta:

```text
ID

objetivo

precondición

entrada

resultado esperado

resultado obtenido

PASA/FALLA.
```

**CE:** RA3.b

---

# 121. Evidencias RA3.b

```text
E-RA3.b-01
Clases de equivalencia.

E-RA3.b-02
Análisis de límites.

E-RA3.b-03
Matriz de pruebas.

E-RA3.b-04
Casos reproducibles completos.
```

---

# 122. Tarea E — Herramientas del entorno

En IntelliJ identifica y explica:

```text
Run

Debug

Breakpoint

Breakpoint condicional

Step Over

Step Into

Step Out

Run to Cursor

Variables

Frames

Watches

Evaluate Expression

Set Value.
```

No basta con incluir capturas.

Debes explicar:

```text
para qué sirve cada herramienta.
```

**CE:** RA3.c

---

# 123. Evidencias RA3.c

```text
E-RA3.c-01
Mapa herramienta → función.

E-RA3.c-02
Captura Debug Tool Window.

E-RA3.c-03
Identificación de herramientas
utilizadas realmente.
```

---

# 124. Tarea F — Reproducir fallo

Ejecuta:

```text
CP06
horas = 6.
```

Registra:

```text
esperado:
12,00 €

obtenido:
8,00 €
```

con el código defectuoso suministrado.

No corrijas todavía el programa.

---

# 125. Tarea G — Hipótesis

Antes de depurar escribe:

> Creo que el defecto podría encontrarse en __________ porque __________.

No se evalúa que la primera hipótesis sea correcta.

Se evalúa:

```text
que exista
un razonamiento
antes de modificar código.
```

---

# 126. Tarea H — Breakpoint

Coloca un breakpoint:

```text
antes o dentro
de la selección
de tarifa.
```

Ejecuta:

```text
Debug.
```

Demuestra que:

```text
la ejecución
se suspende.
```

---

# 127. Tarea I — Seguimiento

Utiliza de manera justificada:

```text
Step Over

Step Into o Smart Step Into

Step Out

Resume / Run to Cursor
```

según proceda.

Debes explicar al menos:

```text
qué dos acciones
de stepping utilizaste

y por qué.
```

**CE:** RA3.d

---

# 128. Tarea J — Breakpoint condicional

Crea una ejecución que calcule varias tarifas.

Configura un breakpoint que se detenga:

```text
solo cuando

horas == 10
```

o en otro valor aprobado por el profesor.

---

# 129. Tarea K — Seguimiento documentado

Construye una tabla:

| Paso | Línea/método | `horas` | `precio` | Observación |
|---:|---|---:|---:|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |

**CE:** RA3.d

---

# 130. Evidencias RA3.d

```text
E-RA3.d-01
Breakpoint funcional.

E-RA3.d-02
Breakpoint condicional.

E-RA3.d-03
Seguimiento paso a paso.

E-RA3.d-04
Tabla del recorrido.

E-RA3.d-05
Identificación de la línea
donde aparece el valor erróneo.
```

---

# 131. Tarea L — Variables y Frames

Durante el caso:

```text
horas = 6
```

documenta:

```text
horas

TARIFA_REDUCIDA

precio
```

en Variables.

Incluye además:

```text
pila de llamadas
```

si el proyecto entregado contiene varios métodos.

---

# 132. Tarea M — Watch

Añade al menos:

```text
horas * TARIFA_REDUCIDA
```

como Watch.

Compara:

```text
valor que debería utilizarse
```

con:

```text
precio obtenido
por el programa.
```

---

# 133. Tarea N — Evaluate Expression

Con el programa suspendido evalúa:

```java
horas * TARIFA_REDUCIDA
```

para:

```text
horas = 6.
```

Resultado esperado:

```text
12.0
```

Compáralo con:

```text
precio.
```

---

# 134. Tarea O — Modificar estado

Antes de corregir el fuente:

```text
modifica temporalmente
el valor de precio
```

a:

```text
12.0
```

mediante:

```text
Set Value.
```

Continúa la ejecución.

Explica:

```text
qué cambia

qué no cambia.
```

---

# 135. Respuesta esperada

Cambia:

```text
resultado
de esa ejecución.
```

No cambia:

```text
el defecto
del código fuente.
```

---

# 136. Tarea P — Experimento adicional

Repite una ejecución y cambia temporalmente:

```text
horas
```

para observar otra rama.

Explica qué has aprendido del:

```text
flujo.
```

**CE:** RA3.e

---

# 137. Evidencias RA3.e

```text
E-RA3.e-01
Variables inspeccionadas.

E-RA3.e-02
Frames observados.

E-RA3.e-03
Watch funcional.

E-RA3.e-04
Evaluate Expression.

E-RA3.e-05
Set Value aplicado.

E-RA3.e-06
Explicación del efecto
de la modificación temporal.
```

---

# 138. Tarea Q — Diagnóstico final

Sin corregir todavía, indica:

```text
archivo

método

línea/expresión defectuosa

comportamiento actual

comportamiento esperado

causa.
```

Ejemplo:

```text
precio = horas + TARIFA_REDUCIDA

debería ser:

precio = horas * TARIFA_REDUCIDA.
```

---

# 139. Tarea R — Corrección

Ahora sí:

```text
corrige el defecto.
```

Ejecuta de nuevo los casos definidos.

Marca:

```text
PASA / FALLA.
```

No se evalúa todavía la automatización.

---

# 140. Tarea S — Regresión manual

Después de corregir:

```text
CP06
```

vuelve a ejecutar al menos:

```text
CP04

CP05

CP06

CP08

CP09.
```

Explica por qué:

```text
no basta
con repetir únicamente
el caso que fallaba.
```

---

# 141. Entregable

Archivo:

```text
P09.1_Apellidos_Nombre.pdf
```

Debe contener:

1. tipos de pruebas;
2. clases de equivalencia;
3. análisis de límites;
4. matriz;
5. casos de prueba;
6. herramientas del IDE;
7. fallo reproducido;
8. hipótesis;
9. breakpoints;
10. breakpoint condicional;
11. seguimiento;
12. Variables;
13. Frames;
14. Watch;
15. Evaluate Expression;
16. Set Value;
17. diagnóstico;
18. corrección;
19. regresión manual;
20. conclusión.

---

# 142. Instrumento I-RA3-01

**Instrumento:** I-RA3-01  
**RA:** RA3  
**CE:** RA3.a, b, c, d, e  
**Actividad:** P09.1 – Diseño de pruebas y depuración de CartagoPark  
**Tipo:** laboratorio técnico individual  

Cada CE recibe:

```text
NOTA 0,00–10,00
```

de forma independiente.

---

# 143. Rúbrica definitiva I-RA3-01

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA3.a** | Identifica tipos de pruebas y selecciona su finalidad | Confunde los tipos o los describe sin relación con el problema | Reconoce pruebas funcionales, estructurales y de regresión de forma básica | Distingue correctamente su finalidad y las aplica a CartagoPark | Además relaciona perspectivas funcional/estructural y justifica qué riesgo detecta cada tipo | **100 % del CE** |
| **RA3.b** | Define casos de prueba reproducibles a partir de requisitos | Los casos carecen de esperado, son arbitrarios o no cubren condiciones relevantes | Define algunos casos válidos pero con cobertura limitada | Utiliza requisitos, clases de equivalencia y valores límite para construir casos completos y reproducibles | Además selecciona un conjunto especialmente eficiente, justifica cada dato y detecta huecos relevantes en la estrategia | **100 % del CE** |
| **RA3.c** | Identifica las herramientas de prueba y depuración disponibles en el IDE y su función | No reconoce las herramientas o confunde sus funciones | Identifica Run/Debug, breakpoint y Variables con ayuda | Identifica correctamente breakpoints, stepping, Variables, Frames, Watches, Evaluate Expression y otras herramientas utilizadas | Además selecciona razonadamente qué herramienta resulta adecuada para cada necesidad de diagnóstico | **100 % del CE** |
| **RA3.d** | Utiliza puntos de ruptura y seguimiento para localizar el origen de un comportamiento | Coloca breakpoints sin estrategia o no consigue seguir el flujo | Consigue detener y avanzar por el programa con ayuda | Utiliza breakpoints, condición y stepping de forma coherente y reconstruye el flujo que conduce al defecto | Además plantea hipótesis, minimiza las paradas necesarias y justifica con precisión cada decisión de seguimiento | **100 % del CE** |
| **RA3.e** | Examina y modifica el comportamiento del programa durante la ejecución | No interpreta el estado o modifica valores sin comprender sus efectos | Examina variables y realiza alguna modificación con ayuda | Utiliza Variables, Frames, Watches/Evaluate Expression y Set Value para comprobar hipótesis sobre el comportamiento | Además diferencia claramente estado temporal y código, utiliza modificaciones controladas para explorar ramas y obtiene conclusiones técnicas fundamentadas | **100 % del CE** |

---

# 144. Nota informativa P09.1

Puede mostrarse:

```text
(
 RA3.a
+RA3.b
+RA3.c
+RA3.d
+RA3.e
) / 5
```

pero el registro definitivo conserva:

```text
cinco notas
independientes.
```

---

# 145. Temporalización definitiva

| Sesión | Contenido | Actividad |
|---:|---|---|
| 1 | Pruebas, defectos y tipos de prueba | A09.1 |
| 2 | Casos, equivalencias y valores límite | A09.2 |
| 3 | Run/Debug, herramientas y breakpoints | laboratorio guiado |
| 4 | Stepping, breakpoint condicional y seguimiento | A09.4 |
| 5 | Variables, Frames, Watches y Evaluate | A09.5–7 |
| 6 | Modificación del estado y diagnóstico por hipótesis | laboratorio |
| 7 | P09.1 — diseño de pruebas | I-RA3-01 |
| 8 | P09.1 — depuración del defecto | I-RA3-01 |
| 9 | P09.1 — corrección, regresión y cierre | I-RA3-01 |

**Total: 9 periodos.**

---

# PARTE B — MATERIAL DEL PROFESOR

# 146. Finalidad docente

La unidad debe evitar que el alumno asocie:

```text
“probar”
=
“ejecutar un par de veces”.
```

El cambio conceptual buscado es:

```text
REQUISITO
↓
RIESGO
↓
CASOS
↓
EJECUCIÓN
↓
EVIDENCIA
↓
DIAGNÓSTICO.
```

---

# 147. Separación importante

## RA3.a

Pregunta:

```text
¿reconoce qué tipos
de prueba existen
y para qué sirven?
```

## RA3.b

Pregunta:

```text
¿sabe diseñar
casos concretos?
```

No confundir ambos CE.

---

# 148. RA3.c

No debe valorarse únicamente:

```text
haber abierto
el Debugger.
```

Debe identificar:

```text
herramienta
+
función.
```

---

# 149. RA3.d

Se evalúa:

```text
uso real
de breakpoints

+
seguimiento.
```

Debe existir evidencia de:

```text
recorrido
hasta localizar
el defecto.
```

---

# 150. RA3.e

Debe incluir:

```text
examinar estado

+
modificar temporalmente
estado/comportamiento.
```

Si el alumno únicamente mira:

```text
Variables
```

pero nunca utiliza una función de modificación:

```text
la evidencia
de RA3.e
queda incompleta.
```

---

# 151. IntelliJ 2026.2

La documentación actual confirma que:

```text
Debug Tool Window
```

ofrece:

```text
Frames

Variables

Watches
```

y permite analizar y modificar el estado de un programa suspendido.

---

# 152. Set Value

La opción:

```text
Set Value
```

resulta especialmente adecuada para demostrar:

```text
RA3.e.
```

No debemos explicarla como:

```text
“arreglar el programa
sin editarlo”.
```

Es:

```text
una herramienta
de experimentación
durante esa ejecución.
```

---

# 153. Defecto evaluable

Defecto principal:

```java
precio =
        horas + TARIFA_REDUCIDA;
```

Debe ser suficientemente visible mediante:

```text
horas = 6
```

pero no tan obvio en la entrega como para que el alumno simplemente lo vea leyendo sin utilizar Debug.

---

# 154. Estrategia de entrega

Recomendación:

```text
proporcionar proyecto
ya preparado

+
no indicar
la línea defectuosa.
```

Puede contener:

```text
varios métodos
```

para que:

```text
Frames

Step Into

Step Out
```

tengan sentido.

---

# 155. Versión recomendada del proyecto

Puede utilizarse:

```text
main
↓
procesarEstancia
↓
TarifaCartagoPark.calcularPrecio
```

para generar una pila suficientemente clara.

---

# 156. Código auxiliar

Ejemplo:

```java
public class AplicacionParking {

    public static void main(String[] args) {

        procesarEstancia(6);
    }

    private static void procesarEstancia(
            int horas) {

        double precio =
                TarifaCartagoPark
                        .calcularPrecio(horas);

        System.out.println(
                "Precio: " + precio
        );
    }
}
```

---

# 157. Expected/actual

Para:

```text
6 horas
```

con el defecto:

```text
esperado
12.00

obtenido
8.00.
```

Esto crea una señal inequívoca.

---

# 158. Valores límite

Debe aparecer obligatoriamente:

```text
4

5

6

9

10

11
```

o conjunto equivalente.

Especialmente:

```text
5/6

10/11.
```

---

# 159. Caso inválido

El alumno debe probar:

```text
0

o valor negativo.
```

Debe esperar:

```text
IllegalArgumentException
```

porque forma parte del comportamiento especificado.

---

# 160. No evaluar JUnit

Aunque el profesor pueda tener tests propios para comprobar la práctica:

```text
NO se pide JUnit
al alumno.
```

Porque:

```text
RA3.f/g
→ UD10.
```

---

# 161. No evaluar documentación formal de incidencias

El PDF técnico de P09.1 documenta evidencias de los cinco CE.

Pero no debemos convertirlo todavía en:

```text
sistema formal
de registro de incidencias
```

porque:

```text
RA3.h
```

se trabajará en UD10.

---

# 162. Logging breakpoints

Puede mostrarse como:

```text
herramienta avanzada
de seguimiento.
```

No debe ser requisito mínimo.

IntelliJ 2026.2 permite configurar breakpoints de logging y evaluar expresiones en ellos.

---

# 163. Breakpoint condicional

Sí conviene exigirlo porque demuestra:

```text
seguimiento dirigido
```

y no solamente:

```text
parar siempre
en la misma línea.
```

---

# 164. Atajos

Los atajos pueden mostrarse para productividad, pero:

```text
NO forman parte
de la calificación.
```

El alumnado puede ejecutar todas las acciones:

```text
desde botones

menús

acciones contextuales.
```

---

# 165. Capturas

No aceptar:

```text
captura de IntelliJ
sin explicar
qué demuestra.
```

Cada imagen debe llevar:

```text
leyenda

CE asociado

observación relevante.
```

---

# 166. Medidas de apoyo

Puede proporcionarse:

```text
plantilla de caso de prueba

tabla de equivalencias

diagrama Run/Debug

cheatsheet de stepping

código de entrenamiento
distinto del evaluable.
```

No proporcionar:

```text
la línea defectuosa

ni

la matriz definitiva
de P09.1.
```

---

# 167. Actividad de apoyo

Antes de CartagoPark puede utilizarse:

```java
public static int mayor(
        int a,
        int b) {

    if (a > b) {
        return a;
    }

    return b;
}
```

para practicar:

```text
breakpoint

Variables

Step Over

Set Value.
```

---

# 168. Ampliación

Alumnado avanzado puede trabajar:

```text
exception breakpoints

logging breakpoints

Smart Step Into

Force Step Into

performance overhead
```

sin que sean requisitos.

---

# 169. Recuperación

Instrumento:

# IR-RA3-01

Bloques asociados a UD09:

```text
RA3.a

RA3.b

RA3.c

RA3.d

RA3.e.
```

Ejemplo:

```text
a = 7
b = 6
c = 8
d = 3
e = 4
```

Si RA3 queda no superado y necesitan nueva evidencia:

```text
RA3.d

RA3.e
```

el alumno realizará:

```text
solo los bloques
correspondientes.
```

---

# 170. Trazabilidad UD09

| RA | CE | Contenido | Actividades | Instrumento | Evidencias |
|---|---|---|---|---|---|
| RA3 | a | tipos de prueba | A09.1 | P09.1 / I-RA3-01 | E-RA3.a-01/02 |
| RA3 | b | casos, equivalencias, límites | A09.2–3 | P09.1 / I-RA3-01 | E-RA3.b-01/04 |
| RA3 | c | herramientas IDE | laboratorio | P09.1 / I-RA3-01 | E-RA3.c-01/03 |
| RA3 | d | breakpoints y seguimiento | A09.4 | P09.1 / I-RA3-01 | E-RA3.d-01/05 |
| RA3 | e | inspección/modificación en runtime | A09.5–7 | P09.1 / I-RA3-01 | E-RA3.e-01/06 |

---

# 171. Estado de RA3 tras UD09

```text
RA3.a → EVALUADO

RA3.b → EVALUADO

RA3.c → EVALUADO

RA3.d → EVALUADO

RA3.e → EVALUADO

RA3.f → PENDIENTE UD10

RA3.g → PENDIENTE UD10

RA3.h → PENDIENTE UD10

RA3.i → PENDIENTE UD10
```

RA3 continúa:

# ABIERTO.

---

# 172. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA3

**CE evaluados:**

```text
RA3.a
RA3.b
RA3.c
RA3.d
RA3.e
```

### ¿Se utiliza programación Java?

Sí, como:

```text
software sometido
a prueba y depuración.
```

No se evalúa:

```text
la competencia
de Programación.
```

### ¿Se realizan pruebas unitarias con framework?

# NO.

Reservadas a:

```text
RA3.f
→ UD10.
```

### ¿Se automatizan pruebas?

# NO.

Reservado a:

```text
RA3.g.
```

### ¿Se evalúa documentación de incidencias?

# NO.

Reservada a:

```text
RA3.h.
```

### ¿Se utilizan dobles?

# NO.

Reservados a:

```text
RA3.i.
```

### ¿Se evalúa refactorización?

# NO.

Pertenece a:

```text
RA4
→ UD11.
```

### ¿Algún instrumento evalúa otro RA?

# NO.

```text
I-RA3-01
→ exclusivamente RA3.
```

---

# 173. Checklist final UD09

```text
☑ 9 periodos.

☑ RA3 único.

☑ RA3.a oficial.

☑ RA3.b oficial.

☑ RA3.c oficial.

☑ RA3.d oficial.

☑ RA3.e oficial.

☑ RA3.f–i reservados.

☑ Prueba vs depuración.

☑ Error/defecto/fallo.

☑ Pruebas funcionales.

☑ Pruebas estructurales.

☑ Regresión.

☑ Caja negra/blanca.

☑ Clases de equivalencia.

☑ Valores límite.

☑ Cubrimiento conceptual.

☑ Casos de prueba.

☑ Resultado esperado.

☑ Precondiciones.

☑ Run vs Debug.

☑ Debugger IntelliJ 2026.2.

☑ Breakpoints.

☑ Breakpoints condicionales.

☑ Step Over.

☑ Step Into.

☑ Step Out.

☑ Smart Step Into contextualizado.

☑ Run to Cursor.

☑ Variables.

☑ Frames.

☑ Watches.

☑ Evaluate Expression.

☑ Set Value.

☑ Modificación temporal ≠ corrección.

☑ Depuración por hipótesis.

☑ CartagoPark.

☑ Defecto controlado.

☑ Regresión manual.

☑ 8 capturas previstas.

☑ Actividades guiadas.

☑ Consolidación.

☑ Ampliación.

☑ Resumen.

☑ Glosario.

☑ Autoevaluación.

☑ P09.1.

☑ I-RA3-01.

☑ Cinco CE con nota 0–10.

☑ Rúbrica armonizada.

☑ Evidencias codificadas.

☑ Material profesor.

☑ Recuperación modular.

☑ Trazabilidad completa.

☑ Aislamiento superado.
```

# UD09 — VERSIÓN MAESTRA DEFINITIVA