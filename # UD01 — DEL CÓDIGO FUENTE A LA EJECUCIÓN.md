# UD01 — DEL CÓDIGO FUENTE A LA EJECUCIÓN

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 8 periodos lectivos  
**Resultado de Aprendizaje:** RA1  
**Práctica evaluable:** P01.1  
**Instrumento:** I-RA1-01  
**JDK de referencia:** Eclipse Temurin JDK 25 LTS  

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

Cuando comenzamos a programar solemos concentrarnos en escribir algo parecido a esto:

```java
public class HolaMundo {

    public static void main(String[] args) {
        System.out.println("Hola, mundo");
    }
}
```

Pulsamos **Run** y el mensaje aparece en pantalla.

Pero entre:

```text
código que escribe el programador
```

y:

```text
programa ejecutándose
```

ocurren muchas cosas.

En esta unidad vamos a descubrirlas.

---

# 2. Resultado de Aprendizaje

## RA1

**Reconoce los elementos y herramientas que intervienen en el desarrollo de un programa informático, analizando sus características y las fases en las que actúan hasta llegar a su puesta en funcionamiento.**

El Real Decreto 405/2023 mantiene este RA dentro del módulo 0487 y establece para él siete criterios de evaluación.

---

# 3. Criterios de evaluación de UD01

En esta unidad se trabajan y evalúan exclusivamente:

### RA1.a

**Se ha reconocido la relación de los programas con los componentes del sistema informático: memoria, procesador, periféricos, entre otros.**

### RA1.c

**Se han diferenciado los conceptos de código fuente, objeto y ejecutable.**

### RA1.d

**Se han reconocido las características de la generación de código intermedio para su ejecución en máquinas virtuales.**

### RA1.e

**Se han clasificado los lenguajes de programación, identificando sus características.**

### RA1.f

**Se ha evaluado la funcionalidad ofrecida por las herramientas utilizadas en el desarrollo de software.**

Los criterios **RA1.b** y **RA1.g** se desarrollarán y evaluarán en **UD02**.

---

# 4. Contenidos curriculares relacionados

Los contenidos básicos oficiales relacionados con esta unidad incluyen:

- concepto de programa informático;
- código fuente, código objeto y código ejecutable;
- tecnologías de virtualización;
- tipos y paradigmas de lenguajes;
- características de lenguajes de programación;
- proceso de obtención de código ejecutable a partir del código fuente;
- herramientas implicadas en dicho proceso.

---

# 5. ¿Qué aprenderemos?

Al finalizar la unidad deberás poder explicar con tus propias palabras:

- qué es realmente un programa informático;
- qué relación tiene con procesador, memoria, almacenamiento, sistema operativo y periféricos;
- qué diferencia existe entre código fuente, código objeto, código intermedio y ejecutable;
- cómo se transforma un programa desde que lo escribe el desarrollador hasta que puede ejecutarse;
- qué ocurre específicamente en Java;
- qué es el bytecode;
- qué función desempeña la JVM;
- para qué sirven `javac`, `java` y `javap`;
- cómo se pueden clasificar los lenguajes de programación;
- qué herramientas participan en un proceso profesional de desarrollo.

---

# 6. ¿Para qué sirve profesionalmente?

Un desarrollador no debería limitarse a saber:

> «Pulso Run y funciona».

Debe comprender qué está haciendo realmente el entorno.

Esta comprensión permite diagnosticar situaciones como:

```text
El código compila pero no arranca.

El programa funciona en un equipo y no en otro.

No se encuentra una clase.

El sistema utiliza otra versión de Java.

Existe el .java pero no aparece el .class.

El programa consume mucha memoria.

El ejecutable necesita una biblioteca externa.

Un archivo puede ejecutarse en una JVM pero no directamente por el procesador.
```

Comprender la cadena completa proporciona una base para prácticamente todo lo que estudiaremos después.

---

# 7. Conocimientos previos

No necesitas conocimientos avanzados de programación.

Sí es conveniente saber:

```text
qué es un archivo

qué es una carpeta

qué es un programa

qué es un sistema operativo

cómo abrir una terminal
```

y reconocer un fragmento sencillo de Java.

---

# 8. Programa informático

Un programa informático puede entenderse como un conjunto organizado de instrucciones y datos destinado a realizar una tarea mediante un sistema informático.

Ejemplos:

```text
navegador web

procesador de textos

videojuego

servidor web

aplicación bancaria

aplicación móvil

programa Java realizado en clase
```

El programa no existe aislado.

Necesita recursos físicos y software del sistema para poder funcionar.

---

# 9. Programa y proceso

Debemos diferenciar:

## Programa

Es la representación almacenada del software.

Por ejemplo:

```text
Calculadora.class
```

o un ejecutable instalado en el disco.

## Proceso

Es una instancia de un programa que se encuentra ejecutándose.

Podemos tener:

```text
1 programa
```

pero varias ejecuciones simultáneas:

```text
Proceso 1
Proceso 2
Proceso 3
```

Cada una posee su propio estado de ejecución.

---

# 10. Del almacenamiento a la ejecución

De forma simplificada:

```text
ALMACENAMIENTO
     │
     │ contiene programa
     ▼
SISTEMA OPERATIVO
     │
     │ prepara ejecución
     ▼
MEMORIA
     │
     │ contiene código y datos necesarios
     ▼
PROCESADOR
     │
     │ ejecuta instrucciones
     ▼
RESULTADOS
```

Los periféricos permiten además introducir o mostrar información.

---

# 11. El procesador

El procesador o CPU ejecuta instrucciones de máquina.

Una CPU no comprende directamente:

```java
System.out.println("Hola");
```

El procesador trabaja finalmente con instrucciones de su arquitectura.

Por eso necesitamos mecanismos que traduzcan o ejecuten nuestro código en una forma compatible con la máquina.

---

# 12. Memoria principal

Durante la ejecución se necesita memoria para almacenar temporalmente:

```text
código

variables

objetos

datos

estructuras internas

estado de ejecución
```

Cuando un programa intenta utilizar más memoria de la disponible pueden aparecer:

```text
lentitud

intercambio con almacenamiento

errores de memoria

finalización del proceso
```

dependiendo del sistema y la situación.

---

# 13. Almacenamiento

El almacenamiento conserva información incluso cuando apagamos el equipo.

Por ejemplo:

```text
SSD

HDD
```

Puede contener:

```text
código fuente

programas compilados

bibliotecas

configuración

datos del usuario
```

Pero un archivo almacenado no está necesariamente ejecutándose.

---

# 14. Sistema operativo

El sistema operativo coordina el acceso a recursos como:

```text
procesador

memoria

archivos

dispositivos

red
```

Cuando ejecutamos un programa, el sistema operativo participa en la creación y gestión de su proceso.

---

# 15. Periféricos

Un programa puede interactuar con dispositivos como:

```text
teclado

ratón

pantalla

impresora

cámara

almacenamiento externo

interfaces de red
```

Estas interacciones suelen producirse mediante servicios proporcionados por el sistema operativo y sus controladores.

---

# 16. Caso profesional — CartagoParking

Imaginemos un programa que controla la entrada de vehículos de un aparcamiento.

Necesita:

```text
leer matrícula
↓
registrar hora
↓
calcular precio
↓
guardar información
↓
mostrar resultado
```

Podríamos relacionarlo con el sistema de esta manera:

```text
TECLADO / LECTOR
      │
      ▼
PROGRAMA CARTAGOPARKING
      │
      ├──── MEMORIA
      │
      ├──── PROCESADOR
      │
      ├──── ALMACENAMIENTO
      │
      ▼
PANTALLA / IMPRESORA
```

La aplicación necesita todos esos recursos para realizar su trabajo.

---

# 17. Actividad guiada A01.1 — Relaciona programa y sistema

Analiza una aplicación que:

> Lee un archivo de alumnos, calcula sus medias y genera un informe en pantalla.

Explica el papel de:

```text
almacenamiento

memoria

procesador

sistema operativo

pantalla
```

No basta con definir cada componente.

Debes relacionarlo con el programa concreto.

---

# 18. Código fuente

El **código fuente** es el texto escrito por el desarrollador mediante un lenguaje de programación.

Ejemplo:

```java
public class Saludo {

    public static void main(String[] args) {
        System.out.println("Hola");
    }
}
```

Archivo:

```text
Saludo.java
```

El código fuente está pensado fundamentalmente para:

```text
ser escrito

leído

comprendido

modificado
```

por personas y herramientas de desarrollo.

---

# 19. Código máquina

El procesador trabaja finalmente con instrucciones codificadas para su arquitectura.

De forma conceptual:

```text
LENGUAJE DE ALTO NIVEL
          │
          ▼
      TRADUCCIÓN
          │
          ▼
INSTRUCCIONES EJECUTABLES
POR LA MÁQUINA
```

Sin embargo, no todos los lenguajes siguen exactamente la misma ruta.

---

# 20. Código objeto

En un proceso de compilación nativo tradicional, un compilador puede producir **código objeto**.

Un archivo objeto contiene código traducido, pero normalmente todavía puede necesitar combinarse con otros objetos y bibliotecas antes de obtener un ejecutable final.

Modelo simplificado:

```text
main.c
   │
   ▼
COMPILADOR
   │
   ▼
main.o
   │
   │
   ├──── biblioteca.o
   │
   ▼
ENLAZADOR
   │
   ▼
PROGRAMA EJECUTABLE
```

---

# 21. Ejecutable

Un ejecutable es un artefacto preparado para que el sistema pueda iniciar su ejecución dentro de la plataforma para la que ha sido construido.

En un modelo nativo:

```text
FUENTE
↓
OBJETO
↓
ENLAZADO
↓
EJECUTABLE
```

Este esquema es muy útil para comprender compiladores tradicionales.

---

# 22. Java introduce un modelo diferente

Java utiliza normalmente un paso intermedio.

Partimos de:

```text
Programa.java
```

Ejecutamos:

```bash
javac Programa.java
```

y obtenemos:

```text
Programa.class
```

La documentación oficial de Java 25 indica que `javac` lee archivos fuente Java y los compila a archivos de clase que se ejecutan sobre la Java Virtual Machine.

---

# 23. Precisión importante: `.class` no es un ejecutable nativo

Debemos evitar la simplificación:

```text
.java → ejecutable
```

y también:

```text
.class = ejecutable nativo
```

El `.class` contiene:

# BYTECODE JAVA

que está destinado a ser interpretado/ejecutado dentro del entorno de la JVM.

---

# 24. Código intermedio

Llamamos **código intermedio** a una representación que se sitúa entre:

```text
código fuente
```

y:

```text
instrucciones nativas ejecutadas finalmente por el procesador.
```

En Java:

```text
Java source
   │
   ▼
 javac
   │
   ▼
bytecode
   │
   ▼
 JVM
   │
   ▼
ejecución sobre la máquina
```

---

# 25. Java Virtual Machine

La JVM es la máquina virtual encargada de ejecutar el bytecode Java.

Esto permite que un archivo `.class` pueda utilizar una representación independiente de una CPU concreta, siempre que exista una JVM compatible en la plataforma.

La especificación y documentación de Java SE 25 mantienen este modelo basado en la Java Virtual Machine.

---

# 26. Esquema completo de Java

```text
┌────────────────────┐
│     Programa.java  │
│    CÓDIGO FUENTE   │
└──────────┬─────────┘
           │
           │ javac
           ▼
┌────────────────────┐
│     Programa.class │
│      BYTECODE      │
└──────────┬─────────┘
           │
           │ JVM
           ▼
┌────────────────────┐
│ EJECUCIÓN EN EQUIPO│
└────────────────────┘
           │
           ▼
 CPU + MEMORIA + SO
```

---

# 27. ¿Qué significa «Write once, run...» conceptualmente?

La idea de una máquina virtual es desacoplar en parte:

```text
código compilado
```

de:

```text
arquitectura física concreta.
```

En lugar de generar directamente código para:

```text
CPU A

CPU B

CPU C
```

generamos una representación para:

```text
JVM
```

y cada plataforma proporciona la implementación correspondiente de esa máquina virtual.

---

# 28. ¿La CPU ejecuta bytecode directamente?

Normalmente no.

La JVM debe convertir o ejecutar las instrucciones de bytecode mediante sus mecanismos internos.

Entre ellos puede existir:

```text
interpretación

compilación JIT
```

según la implementación y las decisiones del runtime.

---

# 29. JIT

JIT significa:

```text
Just-In-Time compilation
```

Una JVM puede identificar código que se ejecuta frecuentemente y compilarlo a código nativo durante la propia ejecución para mejorar su rendimiento.

No necesitamos conocer todavía los algoritmos internos del JIT.

Lo importante es comprender:

```text
bytecode
↓
JVM
↓
posible traducción dinámica
↓
código nativo
↓
CPU
```

---

# 30. Herramienta `javac`

`javac` es el compilador de Java incluido en el JDK.

Ejemplo:

```bash
javac Saludo.java
```

Si no existen errores de compilación, obtendremos normalmente:

```text
Saludo.class
```

---

# 31. Herramienta `java`

Después podemos ejecutar:

```bash
java Saludo
```

No escribimos:

```bash
java Saludo.class
```

porque proporcionamos a `java` el nombre de la clase que debe cargar.

---

# 32. Herramienta `javap`

`javap` permite examinar información contenida en archivos de clase.

Con:

```bash
javap -c Saludo
```

podemos visualizar las instrucciones bytecode de sus métodos.

La documentación oficial de Java 25 describe `javap` como una herramienta para desensamblar archivos de clase y señala que la opción `-c` muestra sus instrucciones bytecode.

---

# 33. Laboratorio guiado A01.2 — Primera compilación

Crea:

```java
public class Saludo {

    public static void main(String[] args) {
        System.out.println("Colegio Miralmonte");
    }
}
```

Guárdalo como:

```text
Saludo.java
```

Desde la terminal:

```bash
javac Saludo.java
```

Comprueba que aparecen:

```text
Saludo.java
Saludo.class
```

Después:

```bash
java Saludo
```

Resultado:

```text
Colegio Miralmonte
```

---

# 34. Capturas previstas

**[CAPTURA UD01-01 — Comprobación del JDK]**  
Terminal mostrando `java --version` y `javac --version`. La captura debe permitir reconocer que el equipo utiliza el JDK de referencia del curso.

**[CAPTURA UD01-02 — Código fuente]**  
Archivo `Saludo.java` abierto en el editor. Debe señalarse la extensión `.java`.

**[CAPTURA UD01-03 — Resultado de compilación]**  
Carpeta antes y después de `javac`, destacando la aparición de `Saludo.class`.

**[CAPTURA UD01-04 — Bytecode]**  
Salida de `javap -c Saludo`, destacando que ya no vemos las instrucciones Java originales.

---

# 35. Actividad guiada A01.3 — Observa el bytecode

Ejecuta:

```bash
javap -c Saludo
```

Compara la salida con:

```java
System.out.println("Colegio Miralmonte");
```

Responde:

1. ¿Aparece el código Java exactamente como lo escribiste?
2. ¿Qué ha ocurrido entre ambos?
3. ¿Qué archivo analiza `javap`?
4. ¿Puede la CPU interpretar directamente el texto Java?
5. ¿Qué papel desempeña la JVM?

---

# 36. El JDK

El **JDK** incluye herramientas necesarias para desarrollar aplicaciones Java.

Entre ellas encontramos:

```text
javac

java

javap

javadoc

otras herramientas del JDK
```

En esta unidad utilizaremos principalmente las tres primeras.

Eclipse Temurin 25 está clasificado por Adoptium como una versión **LTS** de Java 25.

---

# 37. JDK y entorno de desarrollo no son lo mismo

## JDK

Proporciona:

```text
compilador

runtime

herramientas Java
```

## IDE

Proporciona una interfaz integrada para facilitar tareas como:

```text
editar

navegar

compilar

ejecutar

depurar

organizar proyectos
```

El IDE puede utilizar internamente un JDK.

---

# 38. CONOCIMIENTO AUXILIAR NO EVALUADO EN ESTA UNIDAD

La instalación, configuración, personalización y comparación profunda de IDE pertenecen evaluativamente a:

# RA2

y se trabajarán en UD03 y UD04.

En UD01 solo necesitamos reconocer:

```text
qué función ofrece un IDE
```

como una herramienta dentro del proceso de desarrollo.

No se evaluará aquí:

```text
instalación de IntelliJ

plugins

actualizaciones

configuración del IDE
```

---

# 39. Herramientas del desarrollo de software

Un desarrollador utiliza distintas herramientas.

## Editor

Permite escribir y modificar código.

## Compilador

Traduce código fuente a otra representación.

## Enlazador

Combina módulos objeto y bibliotecas en determinados procesos de construcción nativos.

## Máquina virtual / runtime

Proporciona el entorno en el que se ejecuta determinado código.

## Debugger

Permite observar y controlar una ejecución.

## IDE

Integra múltiples herramientas en una única aplicación.

## Herramienta de construcción

Automatiza tareas como compilar, probar o empaquetar.

## Control de versiones

Permite registrar la evolución de los archivos.

---

# 40. No todas las herramientas pertenecen a la misma fase

Ejemplo:

```text
ESCRITURA
→ editor

TRADUCCIÓN
→ compilador

CONSTRUCCIÓN
→ build tool

EJECUCIÓN
→ runtime / VM

DIAGNÓSTICO
→ debugger

HISTORIAL
→ control de versiones
```

RA1.f exige comprender qué funcionalidad aporta cada herramienta.

No exige dominar todavía todas ellas.

---

# 41. Actividad guiada A01.4 — ¿Qué herramienta necesito?

Relaciona:

```text
A. Quiero convertir código Java en bytecode.
B. Quiero escribir código.
C. Quiero observar instrucciones de un .class.
D. Quiero registrar versiones.
E. Quiero investigar una ejecución paso a paso.
F. Quiero ejecutar bytecode Java.
```

con:

```text
editor
javac
javap
Git
debugger
JVM / java
```

Justifica cada respuesta.

---

# 42. Lenguajes de programación

Un lenguaje de programación proporciona reglas para expresar algoritmos y construir programas.

Existen muchos lenguajes porque presentan diferencias de:

```text
propósito

paradigma

nivel de abstracción

sistema de tipos

forma de ejecución

ecosistema

plataforma
```

No existe una única clasificación universal capaz de describirlos perfectamente.

---

# 43. Clasificación por nivel de abstracción

Podemos distinguir de forma introductoria:

## Bajo nivel

Más próximo a la arquitectura del hardware.

Ejemplo:

```text
ensamblador
```

## Alto nivel

Proporciona abstracciones más alejadas de la máquina.

Ejemplos:

```text
Java
Python
Kotlin
C#
JavaScript
```

Esta clasificación es relativa y simplificada.

---

# 44. Clasificación por paradigma

Un paradigma representa una forma de organizar y razonar sobre los programas.

Podemos encontrar:

```text
imperativo

procedimental

orientado a objetos

funcional

declarativo

lógico
```

Un lenguaje moderno puede admitir:

# MÁS DE UN PARADIGMA.

Por ejemplo, decir:

```text
Java = únicamente orientado a objetos
```

sería una simplificación excesiva.

---

# 45. Clasificación por sistema de tipos

Podemos observar características como:

```text
tipado estático

tipado dinámico
```

Por ejemplo:

```text
Java
→ tipado estático

Python
→ tipado dinámico
```

Esto no implica por sí solo que un lenguaje sea:

```text
mejor

peor

más rápido

más profesional
```

Son características distintas.

---

# 46. Clasificación por mecanismo de ejecución

Es frecuente escuchar:

```text
compilado
```

frente a:

```text
interpretado
```

pero muchos entornos modernos combinan varias técnicas.

Ejemplo Java:

```text
fuente
↓
javac
↓
bytecode
↓
JVM
↓
interpretación/JIT según runtime
```

Por eso es mejor describir:

```text
el proceso real
```

que utilizar etiquetas absolutas sin explicación.

---

# 47. Tabla comparativa introductoria

| Lenguaje | Tipado habitual | Paradigmas destacados | Modelo de ejecución simplificado |
|---|---|---|---|
| Java | Estático | OO, imperativo, funcional parcial | Bytecode + JVM |
| C | Estático | Procedimental | Compilación nativa habitual |
| Python | Dinámico | Imperativo, OO, funcional | Runtime/intérprete |
| JavaScript | Dinámico | Multiparadigma | Motor JS con interpretación/JIT |
| Kotlin | Estático | OO, funcional | JVM entre otros destinos |

La tabla pretende introducir criterios de comparación, no reducir cada lenguaje a una única característica.

---

# 48. Actividad guiada A01.5 — Clasificación razonada

Para:

```text
Java
Python
C
JavaScript
Kotlin
```

indica:

- nivel aproximado de abstracción;
- sistema de tipos;
- paradigmas relevantes;
- modelo general de ejecución.

No basta con escribir:

```text
Java = compilado
Python = interpretado
```

Debes explicar el proceso con algo más de precisión.

---

# 49. Caso profesional — Elegir herramientas

Un equipo desarrolla una aplicación Java.

Durante su trabajo necesita:

```text
escribir código
compilar
ejecutar
localizar errores
automatizar construcción
registrar versiones
```

Una posible correspondencia sería:

| Necesidad | Herramienta |
|---|---|
| Escribir | Editor / IDE |
| Compilar Java | `javac` |
| Ejecutar | JVM / `java` |
| Inspeccionar bytecode | `javap` |
| Diagnosticar ejecución | debugger |
| Automatizar construcción | Maven/Gradle |
| Historial | Git |

En otras unidades aprenderemos a utilizar profesionalmente varias de ellas.

---

# 50. Buenas prácticas

## Comprender antes de automatizar

Antes de depender completamente del botón **Run** de un IDE, resulta útil conocer:

```text
qué herramienta está utilizando
```

por debajo.

## Utilizar nombres y extensiones correctas

Diferencia siempre:

```text
.java
.class
.jar
.exe
```

No los trates como si representaran lo mismo.

## Identificar la plataforma de ejecución

Pregunta siempre:

```text
¿lo ejecuta directamente el sistema?

¿necesita una VM?

¿necesita un runtime?

¿requiere bibliotecas?
```

## Evitar clasificaciones absolutas

Describe las características reales del lenguaje.

---

# 51. Errores frecuentes

### Error 1

> «El procesador ejecuta Java».

Corrección:

La CPU ejecuta finalmente instrucciones de máquina; el entorno Java proporciona la capa necesaria para ejecutar el bytecode.

### Error 2

> «Un `.class` es un `.exe`».

Corrección:

Un `.class` contiene bytecode destinado a la JVM.

### Error 3

> «Compilar siempre produce un ejecutable».

Corrección:

Depende del lenguaje, herramientas y modelo de ejecución.

### Error 4

> «Código objeto y código fuente son lo mismo».

Corrección:

Representan etapas diferentes del proceso.

### Error 5

> «Un lenguaje solo puede pertenecer a un paradigma».

Corrección:

Muchos lenguajes son multiparadigma.

### Error 6

> «El IDE es el compilador».

Corrección:

El IDE integra herramientas; puede invocar un compilador externo o incluido en el SDK/JDK.

---

# 52. Ejercicio resuelto

Tenemos:

```java
public class Precio {

    public static void main(String[] args) {
        double precio = 25.0;
        int unidades = 3;

        System.out.println(precio * unidades);
    }
}
```

## Paso 1 — Fuente

Archivo:

```text
Precio.java
```

Representación:

```text
código fuente
```

## Paso 2 — Compilación

```bash
javac Precio.java
```

Resultado:

```text
Precio.class
```

## Paso 3 — Naturaleza

`Precio.class` contiene:

```text
bytecode
```

## Paso 4 — Inspección

```bash
javap -c Precio
```

## Paso 5 — Ejecución

```bash
java Precio
```

Resultado:

```text
75.0
```

## Paso 6 — Sistema

Durante la ejecución intervienen:

```text
almacenamiento
→ contiene .class

memoria
→ carga código/datos

JVM
→ ejecuta bytecode

CPU
→ ejecuta finalmente instrucciones nativas

SO
→ gestiona recursos

pantalla
→ muestra salida
```

---

# 53. Ejercicios de consolidación

1. Diferencia programa y proceso.
2. ¿Qué función desempeña la memoria durante la ejecución?
3. ¿Qué relación tiene el sistema operativo con un programa?
4. Define código fuente.
5. ¿Qué caracteriza al código objeto en un proceso nativo?
6. ¿Qué entendemos por ejecutable?
7. ¿Qué contiene normalmente un `.class`?
8. ¿Qué herramienta genera el `.class`?
9. ¿Qué función desempeña la JVM?
10. ¿Qué permite observar `javap -c`?
11. Explica por qué Java no se describe bien simplemente como «interpretado».
12. ¿Qué es JIT?
13. Diferencia JDK e IDE.
14. ¿Para qué sirve un compilador?
15. ¿Para qué sirve un debugger?
16. ¿Puede un lenguaje pertenecer a varios paradigmas?
17. Diferencia tipado estático y dinámico.
18. Pon un ejemplo de herramienta de control de versiones.
19. ¿Por qué `.class` y `.exe` no son equivalentes?
20. Describe la cadena completa desde `Programa.java` hasta su ejecución.

---

# 54. Actividad de ampliación

## Investiga tu propio equipo

Ejecuta:

```bash
java --version
```

y:

```bash
javac --version
```

Investiga:

```text
versión del JDK
distribución
arquitectura del sistema
sistema operativo
```

Después responde:

> ¿Qué elementos cambiarían si ejecutaras el mismo `.class` en otro sistema operativo o arquitectura?

**Actividad no evaluable.**

---

# 55. Resumen de la unidad

Un programa necesita un sistema informático para ejecutarse.

Sus instrucciones terminan utilizando:

```text
CPU

memoria

almacenamiento

sistema operativo

dispositivos
```

En un modelo nativo podemos encontrar:

```text
FUENTE
↓
OBJETO
↓
ENLACE
↓
EJECUTABLE
```

En Java:

```text
.java
↓ javac
.class
↓ JVM
ejecución
```

El `.class` contiene:

```text
BYTECODE
```

y puede inspeccionarse con:

```text
javap -c
```

Los lenguajes pueden clasificarse mediante distintos criterios y las herramientas de desarrollo desempeñan funciones diferentes dentro del proceso.

---

# 56. Glosario

**Bytecode:** representación intermedia utilizada por la JVM para ejecutar programas Java.

**Código ejecutable:** artefacto preparado para ser iniciado en una plataforma de ejecución determinada.

**Código fuente:** representación del programa escrita en un lenguaje de programación.

**Código objeto:** resultado intermedio habitual de determinados procesos de compilación nativa que puede requerir enlace posterior.

**Compilador:** herramienta que transforma código desde una representación a otra.

**CPU:** procesador encargado de ejecutar finalmente instrucciones de máquina.

**Debugger:** herramienta para observar y controlar la ejecución de un programa.

**IDE:** entorno integrado que reúne distintas herramientas del desarrollo.

**JDK:** conjunto de herramientas para desarrollar aplicaciones Java.

**JIT:** técnica de compilación realizada durante la ejecución.

**JVM:** máquina virtual responsable de ejecutar bytecode Java.

**Lenguaje de programación:** sistema formal utilizado para expresar programas.

**Proceso:** instancia de un programa en ejecución.

**Programa:** conjunto organizado de instrucciones y datos destinado a realizar una tarea informática.

**Runtime:** entorno necesario para ejecutar determinado software.

---

# 57. Autoevaluación

### 1

¿Cuál de estos archivos contiene normalmente código fuente Java?

A. `.class`  
B. `.java`  
C. `.exe`  
D. `.dll`

### 2

¿Qué genera `javac` normalmente a partir de una clase Java?

A. `.java`  
B. `.class`  
C. `.png`  
D. `.docx`

### 3

¿Qué contiene un `.class`?

A. únicamente texto Java  
B. bytecode  
C. siempre código nativo x86  
D. un documento UML

### 4

¿Qué herramienta permite inspeccionar bytecode?

A. `javap`  
B. `git`  
C. `javadoc`  
D. `ping`

### 5

¿Quién ejecuta finalmente instrucciones físicas?

A. SSD  
B. CPU  
C. editor  
D. compilador

### 6

¿Qué papel tiene la JVM?

A. sustituir el código fuente  
B. proporcionar el entorno de ejecución del bytecode  
C. almacenar permanentemente los archivos  
D. diseñar UML

### 7

Un IDE:

A. es necesariamente el lenguaje  
B. integra distintas herramientas de desarrollo  
C. sustituye siempre al JDK  
D. es un procesador físico

### 8

Java:

A. no puede compilarse  
B. utiliza habitualmente bytecode y JVM  
C. genera siempre un `.exe` de Windows  
D. únicamente funciona en Linux

### 9

Un lenguaje puede:

A. pertenecer a más de un paradigma  
B. tener exactamente un paradigma siempre  
C. no tener sintaxis  
D. ejecutarse sin ninguna forma de traducción o runtime

### 10

La función de un debugger es principalmente:

A. escribir documentos  
B. analizar y controlar una ejecución  
C. sustituir el procesador  
D. generar código fuente automáticamente

---

# 58. PRÁCTICA EVALUABLE P01.1

# DEL CÓDIGO FUENTE A LA EJECUCIÓN

**Modalidad:** individual  
**RA:** RA1  
**CE evaluados:** RA1.a, RA1.c, RA1.d, RA1.e, RA1.f

---

# 59. Objetivo de la práctica

Demostrar que puedes:

```text
relacionar un programa con el sistema

diferenciar representaciones del código

explicar el modelo Java/JVM

clasificar lenguajes

identificar la función de herramientas de desarrollo
```

mediante evidencias técnicas reales.

---

# 60. Recursos necesarios

```text
Eclipse Temurin JDK 25 LTS

editor de texto o IntelliJ IDEA

terminal

documentación de la unidad
```

El IDE se utiliza únicamente como editor cuando resulte conveniente.

Su configuración no se evalúa en esta unidad.

---

# 61. Punto de partida

Crea el archivo:

```text
Pedido.java
```

con:

```java
public class Pedido {

    public static void main(String[] args) {

        String producto = "Teclado";
        int cantidad = 3;
        double precioUnitario = 24.95;

        double total =
                cantidad * precioUnitario;

        System.out.println(
                "Producto: " + producto
        );

        System.out.println(
                "Cantidad: " + cantidad
        );

        System.out.println(
                "Total: " + total + " €"
        );
    }
}
```

---

# 62. Tarea 1 — El programa y el sistema

Explica qué ocurre desde que:

```text
Pedido.class
```

se encuentra almacenado hasta que aparece la información en pantalla.

Debes incluir al menos:

```text
almacenamiento

sistema operativo

memoria

JVM

procesador

pantalla
```

Incluye un diagrama propio.

**CE:** RA1.a

---

# 63. Tarea 2 — Identificación de representaciones

Documenta:

```text
Pedido.java
```

antes de compilar.

Ejecuta:

```bash
javac Pedido.java
```

Documenta:

```text
Pedido.class
```

después.

Explica:

1. qué es el código fuente;
2. qué significa código objeto en un proceso de compilación tradicional;
3. qué entendemos por ejecutable;
4. por qué `Pedido.class` debe describirse específicamente como bytecode/código intermedio de Java.

**CE:** RA1.c

---

# 64. Tarea 3 — Código intermedio

Ejecuta:

```bash
javap -c Pedido
```

Incluye evidencia de la salida.

Selecciona al menos tres instrucciones de bytecode y explica, a nivel introductorio, qué observas.

No es necesario memorizar el juego de instrucciones JVM.

Debes explicar la cadena:

```text
Pedido.java
↓
javac
↓
Pedido.class
↓
JVM
↓
ejecución
```

**CE:** RA1.d

---

# 65. Tarea 4 — Clasificación de lenguajes

Completa:

| Lenguaje | Tipado | Paradigmas | Modelo de ejecución aproximado | Observación |
|---|---|---|---|---|
| Java | | | | |
| Python | | | | |
| C | | | | |
| JavaScript | | | | |
| Kotlin | | | | |

Después responde:

> ¿Por qué resulta insuficiente clasificar todos los lenguajes únicamente como «compilados» o «interpretados»?

**CE:** RA1.e

---

# 66. Tarea 5 — Herramientas

Completa:

| Necesidad | Herramienta | Función |
|---|---|---|
| Escribir código | | |
| Compilar Java | | |
| Ejecutar Java | | |
| Inspeccionar bytecode | | |
| Diagnosticar ejecución | | |
| Automatizar construcción | | |
| Registrar versiones | | |

Después explica qué herramientas has utilizado realmente en la práctica.

**CE:** RA1.f

---

# 67. Entregable

Archivo:

```text
P01.1_Apellidos_Nombre.pdf
```

Debe contener:

1. portada;
2. identificación del alumno;
3. Tarea 1;
4. diagrama programa-sistema;
5. Tarea 2;
6. evidencia de `Pedido.java`;
7. evidencia de `Pedido.class`;
8. Tarea 3;
9. evidencia de `javap -c`;
10. Tarea 4;
11. Tarea 5;
12. conclusión personal breve.

---

# 68. Evidencias que deben conservarse

## RA1.a

```text
E-RA1.a-01
Diagrama y explicación programa ↔ componentes del sistema.
```

## RA1.c

```text
E-RA1.c-01
Identificación de fuente, objeto/intermedio y ejecutable.
```

## RA1.d

```text
E-RA1.d-01
Compilación y salida de javap.

E-RA1.d-02
Explicación de bytecode/JVM.
```

## RA1.e

```text
E-RA1.e-01
Tabla razonada de clasificación de lenguajes.
```

## RA1.f

```text
E-RA1.f-01
Relación necesidad ↔ herramienta ↔ función.
```

---

# 69. Instrumento I-RA1-01

**Instrumento:** I-RA1-01  
**RA evaluado:** RA1  
**CE:** RA1.a, RA1.c, RA1.d, RA1.e, RA1.f  
**Tipo:** práctica técnica individual  
**Actividad:** P01.1 – Del código fuente a la ejecución  
**Producto:** dossier técnico PDF y evidencias de ejecución  
**Duración orientativa:** sesiones 7 y 8, apoyada por el trabajo de las sesiones anteriores  
**Modalidad:** individual  
**Material permitido:** UD01, terminal y documentación oficial de las herramientas utilizadas  

La práctica genera una calificación independiente **0–10 para cada CE**.

No existe una ponderación interna distinta entre los cinco CE.

---

# 70. Rúbrica definitiva I-RA1-01

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA1.a** | Relaciona la ejecución de un programa con los componentes del sistema | Confunde los componentes o no explica su intervención | Identifica los elementos esenciales y alguna relación | Explica correctamente almacenamiento, SO, memoria, JVM, CPU y E/S en el escenario | Explica además el flujo completo y diferencia claramente programa almacenado y proceso en ejecución | **100 % del CE** |
| **RA1.c** | Diferencia fuente, objeto/intermedio y ejecutable | Mezcla los conceptos o identifica incorrectamente los artefactos | Distingue los conceptos principales con alguna imprecisión | Diferencia correctamente las representaciones y sitúa `.java` y `.class` en su contexto | Compara además con el proceso nativo y evita equivalencias incorrectas entre `.class`, objeto y ejecutable nativo | **100 % del CE** |
| **RA1.d** | Explica generación y ejecución de código intermedio | No comprende bytecode/JVM | Reconoce que Java genera un `.class` ejecutado por una JVM | Explica correctamente `javac`, bytecode, JVM y ejecución | Relaciona además de forma precisa JVM, JIT y máquina física sin simplificaciones incorrectas | **100 % del CE** |
| **RA1.e** | Clasifica lenguajes identificando características | Clasificación incorrecta o basada en una única etiqueta | Clasifica ejemplos sencillos | Utiliza correctamente varios criterios: tipado, paradigma y ejecución | Justifica que las clasificaciones pueden solaparse y describe modelos híbridos con precisión | **100 % del CE** |
| **RA1.f** | Evalúa la funcionalidad de herramientas utilizadas en desarrollo | Confunde las herramientas o sus funciones | Identifica herramientas básicas | Relaciona correctamente necesidades profesionales con herramientas | Explica además cómo cooperan varias herramientas dentro de un flujo de desarrollo | **100 % del CE** |

Cada fila genera directamente:

```text
NOTA CE = 0,00–10,00
```

La nota resumen de la práctica, si se muestra al alumno, será:

```text
(RA1.a + RA1.c + RA1.d + RA1.e + RA1.f) / 5
```

y tendrá carácter informativo.

---

# 71. Temporalización de UD01

| Sesión | Contenido | Actividades |
|---:|---|---|
| 1 | Programa, proceso y componentes del sistema | A01.1 |
| 2 | Código fuente, objeto y ejecutable | Ejemplos guiados |
| 3 | Java: `.java`, `.class`, bytecode y JVM | A01.2 |
| 4 | `javac`, `java`, `javap` y JIT | A01.3 |
| 5 | Clasificación de lenguajes | A01.5 |
| 6 | Herramientas del desarrollo | A01.4 + consolidación |
| 7 | P01.1 — desarrollo | Práctica evaluable |
| 8 | P01.1 — finalización y evidencia | I-RA1-01 |

**Total: 8 periodos.**

---

# 72. Autoevaluación — soluciones

```text
1 → B
2 → B
3 → B
4 → A
5 → B
6 → B
7 → B
8 → B
9 → A
10 → B
```

---

# PARTE B — MATERIAL DEL PROFESOR

# 73. Finalidad docente

Esta unidad pretende evitar desde el inicio varias concepciones erróneas frecuentes:

```text
IDE = compilador

.class = .exe

Java = simplemente interpretado

CPU = ejecuta directamente el fuente

compilar = producir siempre un ejecutable nativo
```

No se busca todavía profundizar en arquitectura de computadores ni en internals de HotSpot.

El nivel esperado es:

```text
comprensión conceptual sólida
+
capacidad de observar el proceso real
```

---

# 74. Solución A01.1

Para la aplicación que calcula medias:

## Almacenamiento

Contiene:

```text
programa

archivo de alumnos
```

de forma persistente.

## Sistema operativo

Gestiona:

```text
proceso

acceso a archivo

memoria

pantalla
```

## Memoria

Almacena temporalmente:

```text
programa cargado

datos leídos

variables

resultados
```

## Procesador

Ejecuta las instrucciones finales necesarias para realizar los cálculos.

## Pantalla

Recibe la salida que el programa solicita mostrar.

---

# 75. Solución A01.3

### 1

No aparece el código Java exactamente como se escribió.

### 2

`javac` lo ha traducido a bytecode.

### 3

`javap` analiza información de la clase compilada.

### 4

La CPU no ejecuta directamente el texto fuente Java.

### 5

La JVM proporciona el entorno de ejecución del bytecode y realiza las operaciones necesarias para que termine ejecutándose sobre la máquina real.

---

# 76. Solución A01.4

| Necesidad | Herramienta |
|---|---|
| Convertir Java en bytecode | `javac` |
| Escribir | editor/IDE |
| Inspeccionar `.class` | `javap` |
| Registrar versiones | Git |
| Investigar ejecución | debugger |
| Ejecutar bytecode Java | JVM / `java` |

---

# 77. Solución orientativa A01.5

| Lenguaje | Tipado | Paradigmas | Ejecución simplificada |
|---|---|---|---|
| Java | Estático | OO, imperativo, funcional parcial | `javac` → bytecode → JVM |
| Python | Dinámico | OO, imperativo, funcional | Runtime/intérprete |
| C | Estático | Procedimental/imperativo | Compilación nativa habitual |
| JavaScript | Dinámico | Multiparadigma | Motor JS con técnicas de interpretación/JIT |
| Kotlin | Estático | OO y funcional | JVM, entre otros destinos |

Debe aceptarse una respuesta equivalente razonada.

---

# 78. Solución orientativa P01.1 — RA1.a

El esquema debería aproximarse conceptualmente a:

```text
ALMACENAMIENTO
Pedido.class
     │
     ▼
SISTEMA OPERATIVO
crea/gestiona proceso
     │
     ▼
MEMORIA
JVM + clases + datos
     │
     ▼
JVM
interpreta/compila dinámicamente
     │
     ▼
CPU
ejecuta instrucciones finales
     │
     ▼
PANTALLA
muestra salida
```

Debe valorarse la relación causal, no la calidad gráfica.

---

# 79. Solución orientativa P01.1 — RA1.c

### Código fuente

```text
Pedido.java
```

Texto Java escrito por el programador.

### Código objeto

Resultado intermedio característico de determinados procesos de compilación nativa, normalmente previo al enlazado.

### Ejecutable

Artefacto preparado para iniciar ejecución dentro de una plataforma concreta.

### `Pedido.class`

Debe identificarse específicamente como:

```text
archivo de clase Java
que contiene bytecode
destinado a la JVM.
```

No exigir que el alumno utilice una única terminología si demuestra la distinción conceptual correctamente.

---

# 80. Solución orientativa P01.1 — RA1.d

Cadena:

```text
Pedido.java
    │
    │ javac
    ▼
Pedido.class
    │
    │ contiene bytecode
    ▼
JVM
    │
    ├── carga/verifica/ejecuta
    └── puede aplicar JIT
    ▼
CPU
```

No debe exigirse interpretación exhaustiva de las instrucciones de `javap`.

Es suficiente que el alumno comprenda que observa instrucciones del bytecode y pueda distinguirlas del fuente original.

---

# 81. Solución orientativa P01.1 — RA1.e

La respuesta avanzada debe reconocer que:

```text
compilado / interpretado
```

no siempre constituye una división binaria adecuada.

Debe valorar:

```text
tipado

paradigmas

modelo de ejecución

nivel de abstracción
```

y aceptar enfoques técnicamente fundamentados.

---

# 82. Solución orientativa P01.1 — RA1.f

Ejemplo:

| Necesidad | Herramienta | Función |
|---|---|---|
| Escribir | editor/IDE | edición de código |
| Compilar | `javac` | fuente Java → `.class` |
| Ejecutar | `java`/JVM | carga y ejecución de clases |
| Inspeccionar | `javap` | información/desensamblado de clases |
| Diagnosticar | debugger | controlar y observar ejecución |
| Construir | Maven/Gradle | automatizar construcción |
| Versionar | Git | registrar evolución |

No se evalúa todavía el dominio técnico de Maven, Git o debugger.

Solo su función general dentro del proceso.

---

# 83. Errores previsibles en P01.1

### Error

Definir `Pedido.class` como:

```text
ejecutable de Windows
```

### Intervención

Solicitar que el alumno intente explicar:

```text
qué programa necesita para ejecutarlo.
```

---

### Error

Confundir:

```text
javac
```

con:

```text
java.
```

### Intervención

Preguntar:

```text
¿cuál transforma?

¿cuál ejecuta?
```

---

### Error

Describir Python como:

```text
"no se compila nunca"
```

### Intervención

Recordar que en esta unidad interesa describir modelos de ejecución sin absolutismos innecesarios.

---

# 84. Medidas de apoyo

Para alumnado con dificultades se puede proporcionar:

```text
diagrama incompleto para completar

tabla fuente/intermedio/ejecución

lista cerrada de herramientas

comandos preparados

ejemplo previo diferente al evaluable
```

sin proporcionar la solución de `Pedido.java`.

Puede permitirse repetir:

```text
javac

java

javap
```

en un ejemplo de entrenamiento antes de comenzar P01.1.

---

# 85. Ampliación para alumnado avanzado

Puede investigarse:

```text
javap -verbose Pedido
```

para observar:

```text
constant pool

versión del class file

métodos

atributos
```

No forma parte de I-RA1-01.

Tampoco debe introducirse:

```text
análisis de rendimiento

profiling

optimización JIT avanzada
```

porque excede el objetivo de la unidad.

---

# 86. Recuperación asociada

Instrumento:

# IR-RA1-01

Se activarán únicamente los bloques correspondientes a CE que necesiten nueva evidencia dentro de un RA1 no superado.

Bloques disponibles:

```text
RA1.a
RA1.b
RA1.c
RA1.d
RA1.e
RA1.f
RA1.g
```

Para UD01 pueden resultar directamente afectados:

```text
RA1.a
RA1.c
RA1.d
RA1.e
RA1.f
```

La recuperación no requiere repetir P01.1 completa si únicamente existe un CE pendiente.

---

# 87. Trazabilidad de UD01

| RA | CE | Contenido principal | Actividad formativa | Evaluación | Evidencia |
|---|---|---|---|---|---|
| RA1 | a | Programa y componentes del sistema | A01.1 | P01.1 / I-RA1-01 | E-RA1.a-01 |
| RA1 | c | Fuente, objeto/intermedio y ejecutable | ejemplos + A01.2 | P01.1 / I-RA1-01 | E-RA1.c-01 |
| RA1 | d | Bytecode, JVM y código intermedio | A01.2–3 | P01.1 / I-RA1-01 | E-RA1.d-01/02 |
| RA1 | e | Clasificación de lenguajes | A01.5 | P01.1 / I-RA1-01 | E-RA1.e-01 |
| RA1 | f | Herramientas del desarrollo | A01.4 | P01.1 / I-RA1-01 | E-RA1.f-01 |

---

# 88. CE expresamente no evaluados en UD01

```text
RA1.b
→ fases del desarrollo
→ UD02

RA1.g
→ metodologías ágiles
→ UD02
```

Aunque alguna herramienta o ejemplo pueda anticipar que el desarrollo posee distintas actividades, no se generará aquí calificación de:

```text
RA1.b
RA1.g
```

---

# 89. CONTROL DE AISLAMIENTO DEL RA

**RA principal de esta unidad:** RA1

**CE trabajados evaluativamente:**

```text
RA1.a
RA1.c
RA1.d
RA1.e
RA1.f
```

**¿Se introduce contenido perteneciente evaluativamente a otro RA?**

# NO

La mención a IDE, debugger, Maven o Git se limita a explicar la funcionalidad de herramientas requerida por RA1.f.

El dominio operativo de esas herramientas se reserva a sus RA correspondientes.

**¿Algún instrumento evalúa otro RA?**

# NO

```text
I-RA1-01
→ exclusivamente RA1
```

---

# 90. Checklist de cierre de UD01

```text
☑ Portada.

☑ RA identificado.

☑ CE oficiales.

☑ CE b/g excluidos y remitidos a UD02.

☑ Contenidos oficiales relacionados.

☑ Objetivos didácticos.

☑ Utilidad profesional.

☑ Conocimientos previos.

☑ Teoría completa.

☑ Programa ↔ hardware/SO.

☑ Código fuente.

☑ Código objeto.

☑ Ejecutable.

☑ Java bytecode.

☑ JVM.

☑ JIT.

☑ javac.

☑ java.

☑ javap.

☑ Clasificación de lenguajes.

☑ Herramientas del desarrollo.

☑ Caso CartagoParking.

☑ Ejemplo resuelto.

☑ Actividades guiadas.

☑ Consolidación.

☑ Ampliación.

☑ Resumen.

☑ Glosario.

☑ Autoevaluación.

☑ P01.1.

☑ I-RA1-01.

☑ Cinco CE con nota propia 0–10.

☑ Rúbrica armonizada.

☑ Evidencias codificadas.

☑ Soluciones del profesor.

☑ Medidas de apoyo.

☑ Recuperación IR-RA1-01.

☑ Marcadores de capturas.

☑ Conocimiento auxiliar identificado.

☑ Sin ponderación provisional antigua.

☑ Trazabilidad completa.

☑ Control de aislamiento superado.
```

# UD01 — VERSIÓN MAESTRA DEFINITIVA