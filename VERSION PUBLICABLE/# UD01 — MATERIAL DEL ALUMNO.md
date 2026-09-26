# COLEGIO MIRALMONTE  
## FORMACIÓN PROFESIONAL

# 0487 — ENTORNOS DE DESARROLLO

# UD01 — DEL CÓDIGO FUENTE A LA EJECUCIÓN

**1.º DAM / 1.º DAW**  
**Curso 2026/2027**

**Resultado de Aprendizaje:** RA1  
**Duración:** 8 periodos lectivos  
**Práctica evaluable:** P01.1 — Del código fuente a la ejecución: Pedido  
**Instrumento:** I-RA1-01  
**JDK de referencia:** Eclipse Temurin JDK 25 LTS

---

## FICHA DE LA UNIDAD

| Elemento | Información |
|---|---|
| Módulo | 0487 — Entornos de Desarrollo |
| Unidad | UD01 |
| Título | Del código fuente a la ejecución |
| RA | RA1 |
| CE evaluados | RA1.a, RA1.c, RA1.d, RA1.e, RA1.f |
| Duración | 8 periodos |
| Práctica | P01.1 |
| Instrumento | I-RA1-01 |
| Herramientas principales | JDK 25, terminal, editor/IDE |

> **EN ESTA UNIDAD SE EVALÚA:** RA1.a, c, d, e y f.  
> **NO SE EVALÚA TODAVÍA:** RA1.b — fases de desarrollo; RA1.g — metodologías ágiles. Se trabajarán en UD02.

---

# 1. Punto de partida: ¿qué ocurre cuando ejecutamos un programa?

Cuando pulsamos **Run** en un IDE parece que el ordenador realiza una acción muy sencilla:

```text
escribimos código
      ↓
pulsamos Run
      ↓
aparece un resultado
```

Sin embargo, entre ambos extremos intervienen diferentes elementos:

```text
código fuente
compilador
archivos intermedios
sistema operativo
memoria
procesador
máquina virtual
bibliotecas
herramientas de desarrollo
```

Un desarrollador debe comprender al menos de forma general qué ocurre entre:

```text
ESCRIBIR EL PROGRAMA
```

y:

```text
EJECUTARLO.
```

Ésa será la finalidad de nuestra primera unidad.

---

# 2. Resultado de Aprendizaje

## RA1

**Reconoce los elementos y herramientas que intervienen en el desarrollo de un programa informático, analizando sus características y las fases en las que actúan hasta llegar a su puesta en funcionamiento.**

---

# 3. Criterios de evaluación

## RA1.a

**Se ha reconocido la relación de los programas con los componentes del sistema informático: memoria, procesador, periféricos, entre otros.**

## RA1.c

**Se han diferenciado los conceptos de código fuente, objeto y ejecutable.**

## RA1.d

**Se han reconocido las características de la generación de código intermedio para su ejecución en máquinas virtuales.**

## RA1.e

**Se han clasificado los lenguajes de programación, identificando sus características.**

## RA1.f

**Se ha evaluado la funcionalidad ofrecida por las herramientas utilizadas en el desarrollo de software.**

---

# 4. ¿Qué aprenderemos?

Al finalizar la unidad deberás ser capaz de:

- explicar dónde se almacena un programa;
- relacionar software, memoria y procesador;
- distinguir almacenamiento y memoria principal;
- comprender el papel básico del sistema operativo;
- diferenciar código fuente, código objeto y ejecutable;
- comprender el proceso básico de compilación;
- explicar qué es un enlazador;
- comprender qué es el código intermedio;
- explicar la finalidad de una máquina virtual;
- comprender el flujo de ejecución de Java;
- reconocer archivos `.java` y `.class`;
- clasificar lenguajes de programación desde distintas perspectivas;
- diferenciar compilación nativa, interpretación y ejecución mediante máquina virtual;
- reconocer que las clasificaciones no siempre son absolutas;
- identificar la finalidad de las principales herramientas de desarrollo;
- utilizar `javac`;
- utilizar `java`;
- inspeccionar bytecode mediante `javap`;
- reconstruir el camino seguido desde un fichero fuente hasta su ejecución.

---

# 5. Utilidad profesional

Imagina que un compañero te dice:

> «El código compila, pero el programa no arranca en su ordenador».

Para investigar el problema necesitamos distinguir cuestiones diferentes:

```text
¿Existe el código fuente?

¿Se ha compilado?

¿Qué archivo se ha generado?

¿Necesita una máquina virtual?

¿Existe una versión compatible del runtime?

¿El sistema operativo puede ejecutarlo?

¿Qué herramienta está fallando?
```

Comprender estos conceptos será necesario posteriormente para trabajar correctamente con:

```text
IDE

Maven

testing

depuración

CI

despliegue.
```

---

# 6. Programa y sistema informático

Un programa no funciona de forma aislada.

Cuando ejecutamos software intervienen diferentes componentes del sistema.

## 6.1. Procesador

La CPU ejecuta instrucciones.

En última instancia, el procesador trabaja con:

```text
instrucciones máquina
```

propias de una arquitectura concreta.

Ejemplos de arquitecturas:

```text
x86-64
ARM64
```

El procesador no entiende directamente:

```java
System.out.println("Hola");
```

Ese código debe recorrer previamente un proceso de traducción o ejecución.

---

## 6.2. Memoria principal

La RAM mantiene temporalmente:

```text
programas en ejecución

datos utilizados

estructuras necesarias
durante la ejecución.
```

Cuando iniciamos una aplicación, parte de la información necesaria se carga:

```text
almacenamiento
     ↓
RAM
```

para que pueda ser utilizada durante la ejecución.

---

## 6.3. Almacenamiento

SSD, disco u otros dispositivos conservan de forma persistente:

```text
código fuente

programas

bibliotecas

configuración

datos.
```

Por ejemplo:

```text
Pedido.java
```

permanece almacenado aunque:

```text
el ordenador se apague.
```

---

## 6.4. Periféricos

El programa puede recibir o producir información mediante:

```text
teclado

ratón

pantalla

impresora

red

otros dispositivos.
```

---

## 6.5. Sistema operativo

El sistema operativo actúa como intermediario entre:

```text
programas

y

hardware.
```

Gestiona, entre otros:

```text
procesos

memoria

archivos

dispositivos

permisos.
```

---

## 6.6. Ejemplo de ejecución

Supongamos que tenemos:

```text
Pedido.class
```

almacenado en el SSD.

Cuando ejecutamos:

```bash
java Pedido
```

simplificando mucho, ocurre:

```text
Pedido.class
     ↓
almacenamiento
     ↓
proceso Java / JVM
     ↓
RAM
     ↓
CPU
     ↓
sistema operativo
     ↓
salida por pantalla
```

---

## ACTIVIDAD A01.1 — ¿Qué componente interviene?

Relaciona:

| Situación | Componente principal |
|---|---|
| El programa está guardado aunque apaguemos el PC | |
| Una aplicación se encuentra actualmente ejecutándose | |
| Se realizan las instrucciones finalmente traducidas | |
| El resultado aparece en el monitor | |
| Se gestionan procesos y archivos | |

**Actividad formativa. No genera calificación independiente.**

---

# 7. Lenguajes de programación

Un lenguaje de programación permite expresar:

```text
instrucciones

datos

algoritmos

comportamientos
```

mediante una notación que pueda ser transformada o procesada para ser ejecutada.

No existe una única forma de clasificar los lenguajes.

---

# 8. Clasificación por nivel de abstracción

## 8.1. Lenguaje máquina

Está formado por instrucciones directamente relacionadas con la arquitectura del procesador.

Es:

```text
muy cercano al hardware

difícil de escribir manualmente

dependiente de arquitectura.
```

---

## 8.2. Lenguaje ensamblador

Utiliza representaciones simbólicas de instrucciones máquina.

Ejemplo conceptual:

```text
MOV
ADD
JMP
```

Necesita un:

```text
ensamblador
```

para producir código máquina.

---

## 8.3. Lenguajes de alto nivel

Utilizan abstracciones mucho más cercanas a la forma de razonar de los programadores.

Ejemplos:

```text
Java
C
Python
Kotlin
JavaScript
```

Permiten escribir:

```java
double total = unidades * precio;
```

en lugar de manejar directamente instrucciones del procesador.

---

# 9. Clasificación por modelo de ejecución

Una clasificación introductoria habitual distingue entre:

```text
compilados

interpretados

basados en código intermedio
y máquina virtual.
```

Pero debemos introducir una precisión importante:

> Los lenguajes modernos no siempre encajan en una única categoría absoluta.

Una implementación puede combinar:

```text
compilación

interpretación

bytecode

JIT.
```

---

# 10. Compilación nativa

Modelo simplificado:

```text
CÓDIGO FUENTE
      ↓
COMPILADOR
      ↓
CÓDIGO OBJETO
      ↓
ENLAZADOR
      ↓
EJECUTABLE NATIVO
```

El resultado final contiene instrucciones destinadas a una determinada plataforma.

---

# 11. Interpretación

En un modelo interpretado:

```text
CÓDIGO
  ↓
INTÉRPRETE
  ↓
EJECUCIÓN
```

el software intérprete procesa las instrucciones necesarias durante la ejecución.

En la práctica, muchas implementaciones modernas utilizan sistemas más complejos.

---

# 12. Código intermedio

Existe otra estrategia:

```text
CÓDIGO FUENTE
      ↓
COMPILADOR
      ↓
CÓDIGO INTERMEDIO
      ↓
MÁQUINA VIRTUAL
      ↓
EJECUCIÓN
```

Java constituye nuestro ejemplo principal.

---

# 13. Clasificación por paradigma

También podemos clasificar los lenguajes según la forma de estructurar la solución.

Algunos paradigmas importantes son:

```text
imperativo

procedimental

orientado a objetos

funcional

lógico.
```

Muchos lenguajes actuales son:

# MULTIPARADIGMA.

Por ejemplo, Java posee una fuerte orientación a objetos, pero también permite programación imperativa e incorpora características funcionales.

---

## ACTIVIDAD A01.2 — Clasifica

Completa una tabla razonada:

| Lenguaje | Nivel | Modelo de ejecución habitual | Paradigmas relevantes |
|---|---|---|---|
| Java | | | |
| C | | | |
| Python | | | |
| JavaScript | | | |
| Kotlin/JVM | | | |

No se valorará únicamente colocar una etiqueta. Debes justificar los casos que admiten matices.

---

# 14. Código fuente

El código fuente es:

```text
el texto escrito
en un lenguaje de programación
```

antes de producir los artefactos necesarios para su ejecución.

Ejemplo:

```java
public class Pedido {

    public static void main(String[] args) {

        int unidades = 3;
        double precioUnidad = 12.50;

        double total =
                unidades * precioUnidad;

        System.out.printf(
                "Total del pedido: %.2f €%n",
                total
        );
    }
}
```

Archivo:

```text
Pedido.java
```

---

# 15. Código objeto

En un flujo de compilación nativa, un compilador puede generar:

```text
código objeto
```

habitualmente almacenado en archivos como:

```text
.o
.obj
```

El código objeto:

```text
ya ha sido traducido

pero normalmente todavía
no constituye por sí solo
el programa final ejecutable.
```

---

# 16. Enlazado

Un programa puede estar formado por:

```text
varios archivos objeto

bibliotecas

código externo.
```

El:

```text
LINKER
o
ENLAZADOR
```

combina los componentes necesarios y genera el ejecutable final.

---

# 17. Código ejecutable

Un ejecutable nativo es un artefacto preparado para ser cargado y ejecutado en una plataforma concreta.

Ejemplos típicos:

```text
.exe
```

en Windows u otros formatos ejecutables en distintos sistemas.

---

# 18. No confundir los tres conceptos

```text
CÓDIGO FUENTE
≠
CÓDIGO OBJETO
≠
EJECUTABLE
```

Flujo conceptual:

```text
programa.c
   ↓
compilador
   ↓
programa.obj
   ↓
linker
   ↓
programa.exe
```

---

# 19. ¿Y qué ocurre con Java?

Java utiliza un modelo diferente.

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

El fichero:

```text
Pedido.class
```

contiene:

# BYTECODE DE LA JVM.

No debemos describirlo simplemente como:

```text
un .obj nativo
```

ni como:

```text
un .exe.
```

---

# 20. Código intermedio

El bytecode se diseña para ser ejecutado por:

```text
una máquina virtual Java
```

y no directamente como instrucciones nativas de un procesador concreto.

La idea general es:

```text
MISMO BYTECODE
     ↓
JVM para Windows

JVM para Linux

JVM para macOS
```

siempre que las condiciones del programa y la plataforma lo permitan.

---

# 21. Máquina virtual

Una máquina virtual de ejecución proporciona un entorno abstracto capaz de interpretar, ejecutar o transformar el código intermedio.

En Java utilizamos:

# JVM — Java Virtual Machine.

La JVM se ocupa de cuestiones como:

```text
carga de clases

ejecución de bytecode

gestión de memoria

interacción con la plataforma.
```

---

# 22. JIT

Las JVM modernas pueden utilizar:

```text
Just-In-Time compilation
```

para transformar durante la ejecución determinadas partes del bytecode en:

```text
código máquina nativo.
```

Por tanto, decir simplemente:

> «Java es interpretado»

es demasiado simplificado.

Una descripción mejor es:

```text
Java se compila a bytecode
para la JVM

y la JVM puede interpretar
y/o compilar dinámicamente
ese bytecode.
```

---

# 23. El JDK

El **Java Development Kit** contiene herramientas necesarias para desarrollar aplicaciones Java.

En este curso utilizaremos:

```text
Eclipse Temurin JDK 25 LTS.
```

Entre las herramientas estándar encontraremos:

```text
javac
java
javap
jar
javadoc
```

En esta unidad nos interesan especialmente:

```text
javac

java

javap.
```

---

# 24. `javac`

`javac` es el compilador Java.

Transforma:

```text
.java
```

en:

```text
.class
```

Ejemplo:

```bash
javac Pedido.java
```

Resultado:

```text
Pedido.class
```

---

# 25. `java`

`java` lanza una aplicación Java.

Ejemplo:

```bash
java Pedido
```

Salida:

```text
Total del pedido: 37,50 €
```

La representación decimal concreta puede variar con la configuración regional del entorno.

---

# 26. `javap`

`javap` permite examinar información contenida en archivos de clase.

Utilizaremos:

```bash
javap -c Pedido
```

para observar las instrucciones de bytecode de forma legible.

No necesitamos memorizar esas instrucciones.

El objetivo es comprobar que:

```text
Pedido.class
```

contiene algo distinto de:

```text
nuestro código fuente Java.
```

---

# 27. Laboratorio guiado — Pedido

## Paso 1 — comprobar Java

En terminal:

```bash
java -version
```

y:

```bash
javac -version
```

Debemos comprobar que ambos corresponden al JDK configurado para el curso.

---

## Paso 2 — crear el archivo

Crea:

```text
Pedido.java
```

con:

```java
public class Pedido {

    public static void main(String[] args) {

        int unidades = 3;
        double precioUnidad = 12.50;

        double total =
                unidades * precioUnidad;

        System.out.printf(
                "Total del pedido: %.2f €%n",
                total
        );
    }
}
```

---

## Paso 3 — observar

Antes de compilar tenemos:

```text
Pedido.java
```

Pregunta:

> ¿Qué tipo de artefacto es?

Respuesta:

```text
código fuente.
```

---

## Paso 4 — compilar

```bash
javac Pedido.java
```

Después aparecen:

```text
Pedido.java

Pedido.class
```

---

## Paso 5 — identificar

```text
Pedido.java
→ fuente

Pedido.class
→ bytecode / class file
  para la JVM
```

---

## Paso 6 — inspeccionar

```bash
javap -c Pedido
```

Observa que aparecen instrucciones como:

```text
aload
getstatic
ldc
invokevirtual
return
```

o instrucciones equivalentes según el código y compilador.

No debes aprenderlas de memoria.

---

## Paso 7 — ejecutar

```bash
java Pedido
```

Resultado:

```text
Total del pedido: 37,50 €
```

---

## Paso 8 — modificar

Cambia:

```java
int unidades = 4;
```

y ejecuta directamente:

```bash
java Pedido
```

sin recompilar.

Pregunta:

> ¿Ha cambiado el resultado?

Probablemente no.

¿Por qué?

Porque has cambiado:

```text
Pedido.java
```

pero estás ejecutando:

```text
Pedido.class
```

generado anteriormente.

---

## Paso 9 — recompilar

```bash
javac Pedido.java
java Pedido
```

Ahora sí:

```text
el nuevo código fuente
```

ha producido:

```text
un nuevo bytecode.
```

---

# 28. Herramientas del desarrollo de software

Durante un proyecto intervienen distintas herramientas.

## Editor

Permite:

```text
escribir y modificar texto fuente.
```

---

## IDE

Integra en una sola aplicación muchas funcionalidades:

```text
edición

proyecto

ejecución

compilación

navegación

otras herramientas.
```

Trabajaremos los IDE con detalle en:

```text
RA2.
```

---

## Compilador

Traduce un lenguaje o representación a otra.

Ejemplo:

```text
javac.
```

---

## Enlazador

Combina código objeto y bibliotecas para generar un artefacto ejecutable en los modelos que lo requieren.

---

## Máquina virtual / runtime

Proporciona:

```text
entorno necesario
para ejecutar el programa.
```

Ejemplo:

```text
JVM.
```

---

## Herramienta de construcción

Automatiza tareas como:

```text
compilar

probar

empaquetar.
```

Posteriormente utilizaremos:

```text
Maven.
```

---

## Depurador

Ayuda a:

```text
examinar la ejecución

detenerla

inspeccionar datos.
```

Se trabajará evaluativamente en:

```text
RA3.
```

---

## Control de versiones

Permite:

```text
registrar cambios

comparar versiones

colaborar.
```

Se trabajará evaluativamente en:

```text
RA4.
```

---

# 29. Qué se evalúa aquí sobre las herramientas

En RA1.f no necesitamos todavía dominar todas esas herramientas.

Debemos ser capaces de:

```text
identificar la herramienta

explicar su función

seleccionar cuál necesitamos
para una determinada tarea.
```

---

## ACTIVIDAD A01.3 — ¿Qué herramienta necesito?

Selecciona la herramienta adecuada:

1. Traducir `Pedido.java` a bytecode.
2. Ejecutar `Pedido.class`.
3. Seguir la ejecución línea por línea.
4. Registrar versiones del proyecto.
5. Generar un ejecutable nativo a partir de varios archivos objeto.
6. Automatizar compilación, tests y empaquetado.
7. Editar cómodamente un proyecto con múltiples clases.

Justifica cada respuesta.

---

# 30. Diferencias fundamentales

Debemos acabar la unidad dominando estas comparaciones.

## Fuente vs objeto

```text
fuente
→ escrito en el lenguaje
  de programación

objeto
→ resultado intermedio
  de una compilación nativa
```

## Objeto vs ejecutable

```text
objeto
→ todavía puede necesitar enlazado

ejecutable
→ artefacto final ejecutable
  de ese flujo nativo
```

## `.class` vs ejecutable nativo

```text
.class
→ bytecode JVM

.exe nativo
→ instrucciones destinadas
  a una plataforma nativa
```

## Compilador vs máquina virtual

```text
compilador
→ transforma código

máquina virtual
→ proporciona el entorno
  donde se ejecuta código intermedio
```

---

# 31. Errores frecuentes

## Error 1 — «Si compila, funciona»

Compilar comprueba determinados aspectos del programa.

No garantiza:

```text
que haga
lo que debería hacer.
```

---

## Error 2 — llamar ejecutable a cualquier archivo generado

No todos los archivos producidos por una compilación son:

```text
ejecutables nativos.
```

---

## Error 3 — llamar `.obj` a `Pedido.class`

`Pedido.class` contiene:

```text
bytecode JVM.
```

No es equivalente al archivo objeto tradicional de un flujo de compilación nativa.

---

## Error 4 — pensar que Java ejecuta `.java` sin más

En el flujo tradicional estudiado:

```text
.java
↓
javac
↓
.class
↓
JVM
```

---

## Error 5 — clasificar un lenguaje con una sola etiqueta

Decir:

```text
Java = compilado

Python = interpretado
```

sin más explicación puede resultar excesivamente simplificado.

---

## Error 6 — confundir JDK y JVM

```text
JDK
→ conjunto de herramientas
  para desarrollar

JVM
→ máquina virtual
  de ejecución.
```

---

# 32. Buenas prácticas

- comprender qué archivo estamos ejecutando;
- diferenciar fuente y artefactos generados;
- conservar separados archivos fuente y salidas de compilación;
- conocer la finalidad de las herramientas antes de utilizarlas;
- no memorizar etiquetas sin comprender el modelo de ejecución;
- verificar siempre la versión del JDK del proyecto;
- utilizar nombres de archivos y clases significativos.

---

# 33. Caso profesional integrador — Pedido

Una pequeña empresa dispone del siguiente programa:

```java
public class Pedido {

    public static void main(String[] args) {

        int unidades = 3;
        double precioUnidad = 12.50;

        double total =
                unidades * precioUnidad;

        System.out.printf(
                "Total del pedido: %.2f €%n",
                total
        );
    }
}
```

Un técnico debe explicar:

```text
dónde se almacena el fuente

qué hace javac

qué archivo genera

qué contiene el .class

quién lo ejecuta

qué componentes del sistema
participan

qué herramientas intervienen.
```

Éste será el contexto de nuestra primera práctica evaluable.

---

# 34. PRÁCTICA EVALUABLE P01.1

# DEL CÓDIGO FUENTE A LA EJECUCIÓN — PEDIDO

| Campo | Información |
|---|---|
| Código | P01.1 |
| Modalidad | Individual |
| RA | RA1 |
| CE | a, c, d, e, f |
| Instrumento | I-RA1-01 |
| Herramientas | JDK 25, terminal, editor/IDE |
| Entregable | `P01.1_Apellidos_Nombre.pdf` |

---

## 34.1. Objetivo

Demostrar que puedes reconstruir y explicar el proceso que transforma un programa escrito por una persona en una aplicación que llega a ejecutarse.

---

## 34.2. Tarea A — Programa y hardware

**CE: RA1.a**

Construye un esquema propio que muestre la relación entre:

```text
Pedido.class

almacenamiento

RAM

JVM

sistema operativo

CPU

pantalla.
```

Debajo del esquema explica con tus propias palabras la función de cada elemento.

### Evidencia

```text
E-RA1.a-01
Mapa razonado
programa → sistema informático.
```

---

## 34.3. Tarea B — Fuente, objeto y ejecutable

**CE: RA1.c**

Completa y explica:

| Elemento | Clasificación | Justificación |
|---|---|---|
| `Pedido.java` | | |
| `modulo.obj` | | |
| `aplicacion.exe` | | |
| `Pedido.class` | | |

Debes explicar especialmente por qué:

```text
Pedido.class
```

no debe equipararse sin más con:

```text
modulo.obj
```

ni con:

```text
aplicacion.exe.
```

### Evidencia

```text
E-RA1.c-01
Tabla y explicación
fuente/objeto/ejecutable.
```

---

## 34.4. Tarea C — Java y código intermedio

**CE: RA1.d**

Realiza:

```bash
javac Pedido.java
```

después:

```bash
javap -c Pedido
```

y finalmente:

```bash
java Pedido
```

Incluye evidencias de:

```text
Pedido.java

Pedido.class

javap -c

resultado de ejecución.
```

Explica:

1. qué genera `javac`;
2. qué contiene conceptualmente `.class`;
3. para qué sirve la JVM;
4. por qué el bytecode se considera código intermedio;
5. qué ventaja aporta separar bytecode y plataforma concreta.

### Evidencia

```text
E-RA1.d-01
Compilación y bytecode.

E-RA1.d-02
Explicación del papel de la JVM.
```

---

## 34.5. Tarea D — Clasificación de lenguajes

**CE: RA1.e**

Clasifica:

```text
Java

C

Python

JavaScript

Kotlin/JVM
```

según:

```text
nivel de abstracción

modelo de ejecución habitual

paradigma(s).
```

Incluye al menos:

```text
una observación
```

que demuestre por qué no siempre podemos asignar a un lenguaje una única etiqueta.

### Evidencia

```text
E-RA1.e-01
Matriz razonada
de lenguajes.
```

---

## 34.6. Tarea E — Herramientas

**CE: RA1.f**

Completa:

| Herramienta | Función | Ejemplo |
|---|---|---|
| Editor | | |
| IDE | | |
| Compilador | | |
| Linker | | |
| Runtime / VM | | |
| Build tool | | |
| Debugger | | |
| Control de versiones | | |

Después selecciona la herramienta adecuada para:

1. convertir Java a bytecode;
2. ejecutar bytecode Java;
3. generar un ejecutable nativo a partir de objetos;
4. automatizar un build;
5. investigar un programa en ejecución.

### Evidencia

```text
E-RA1.f-01
Mapa herramienta → función.

E-RA1.f-02
Selección razonada
de herramientas.
```

---

# 35. Entregable

Entrega:

```text
P01.1_Apellidos_Nombre.pdf
```

con:

1. portada;
2. mapa hardware/software;
3. fuente/objeto/ejecutable;
4. evidencias de compilación;
5. explicación de bytecode/JVM;
6. clasificación de lenguajes;
7. tabla de herramientas;
8. conclusión personal breve.

Las capturas deberán:

```text
ser legibles

mostrar únicamente
la información necesaria

tener un pequeño pie explicativo.
```

---

# 36. Rúbrica P01.1 — I-RA1-01

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA1.a** | Relaciona la ejecución del programa con memoria, procesador, almacenamiento, sistema operativo y dispositivos | Confunde los componentes o no explica su participación | Reconoce los componentes principales con explicaciones parciales | Explica correctamente cómo intervienen almacenamiento, RAM, CPU, SO, JVM y salida durante la ejecución | Además reconstruye de forma especialmente clara el recorrido del programa y distingue persistencia, proceso y ejecución | **100 % del CE** |
| **RA1.c** | Diferencia código fuente, objeto y ejecutable | Confunde los tres conceptos | Identifica los conceptos básicos con alguna imprecisión | Distingue correctamente fuente, objeto y ejecutable y clasifica adecuadamente los ejemplos | Además explica con precisión por qué un `.class` Java no equivale a un objeto nativo ni a un ejecutable nativo | **100 % del CE** |
| **RA1.d** | Reconoce la generación y ejecución de código intermedio | No comprende el papel del bytecode o la máquina virtual | Reconoce que Java genera `.class` y necesita JVM | Explica correctamente `.java → javac → .class → JVM → ejecución` y obtiene evidencias reales | Además relaciona bytecode, portabilidad y transformación/ejecución en la JVM con precisión técnica | **100 % del CE** |
| **RA1.e** | Clasifica lenguajes identificando sus características | Clasifica de forma incorrecta o únicamente memorística | Clasifica correctamente varios lenguajes mediante categorías básicas | Utiliza nivel, modelo de ejecución y paradigma y justifica las clasificaciones | Además identifica modelos híbridos/multiparadigma y evita clasificaciones excesivamente simplistas | **100 % del CE** |
| **RA1.f** | Evalúa la funcionalidad de herramientas utilizadas en desarrollo | Confunde la finalidad de las herramientas | Reconoce varias herramientas y funciones básicas | Relaciona correctamente editor, IDE, compilador, linker, runtime, build, debugger y control de versiones con su finalidad | Además selecciona justificadamente herramientas según distintas necesidades del proceso de desarrollo | **100 % del CE** |

---

# 37. Ejercicios de consolidación

1. ¿Dónde permanece almacenado normalmente un archivo `.java`?
2. ¿Qué papel desempeña la RAM durante la ejecución?
3. ¿Qué componente ejecuta finalmente instrucciones nativas?
4. ¿Qué papel desempeña el sistema operativo?
5. Define código fuente.
6. Define código objeto.
7. Define ejecutable.
8. ¿Para qué sirve un linker?
9. ¿Qué genera `javac`?
10. ¿Qué contiene un `.class`?
11. ¿Qué función realiza la JVM?
12. ¿Qué significa bytecode?
13. ¿Por qué Java no encaja bien en la simple etiqueta «interpretado»?
14. Diferencia JDK y JVM.
15. ¿Qué hace `java`?
16. ¿Qué hace `javap`?
17. ¿Qué diferencia existe entre un compilador y una máquina virtual?
18. ¿Qué función tiene un build tool?
19. ¿Qué función tiene un debugger?
20. ¿Por qué una clasificación de lenguajes puede admitir varias dimensiones?

---

# 38. Ampliación

## ¿Qué ocurre dentro de una JVM moderna?

Investiga de forma introductoria:

```text
intérprete

JIT

código nativo

HotSpot.
```

Explica por qué una JVM puede:

```text
comenzar ejecutando
un código intermedio

y

optimizar posteriormente
partes de la aplicación.
```

**Actividad de ampliación. No evaluable.**

---

# 39. Resumen

## Programa y hardware

```text
almacenamiento
↓
memoria
↓
CPU
```

con intervención de:

```text
sistema operativo
y runtime.
```

## Compilación nativa

```text
fuente
↓
compilador
↓
objeto
↓
linker
↓
ejecutable.
```

## Java

```text
.java
↓
javac
↓
.class / bytecode
↓
JVM
↓
ejecución.
```

## Lenguajes

Pueden clasificarse según:

```text
nivel de abstracción

modelo de ejecución

paradigma.
```

## Herramientas

Cada herramienta resuelve una necesidad distinta:

```text
editar

compilar

enlazar

ejecutar

construir

depurar

versionar.
```

---

# 40. Glosario

**Bytecode:** código intermedio destinado a una máquina virtual.

**Código ejecutable:** artefacto preparado para la ejecución en una determinada plataforma o entorno.

**Código fuente:** texto escrito por el desarrollador en un lenguaje de programación.

**Código objeto:** resultado intermedio típico de una compilación nativa antes del enlazado final.

**Compilador:** herramienta que transforma código de una representación a otra.

**CPU:** procesador encargado de ejecutar instrucciones.

**IDE:** entorno integrado que agrupa herramientas de desarrollo.

**JDK:** conjunto de herramientas necesarias para desarrollar aplicaciones Java.

**JIT:** compilación realizada durante la ejecución.

**JVM:** máquina virtual encargada de ejecutar código compatible con la Java Virtual Machine.

**Linker:** herramienta que enlaza objetos y bibliotecas para generar un artefacto final.

**RAM:** memoria principal utilizada durante la ejecución.

**Runtime:** entorno necesario para ejecutar un programa.

---

# 41. Autoevaluación

### 1
¿Cuál es código fuente?

A. `Pedido.java`  
B. `Pedido.class`  
C. `pedido.exe`  
D. RAM

### 2
En un flujo nativo, el código objeto:

A. es siempre el fuente  
B. suele ser un resultado intermedio  
C. es la CPU  
D. es un IDE

### 3
`javac`:

A. ejecuta Git  
B. genera class files a partir de Java  
C. crea UML  
D. es el sistema operativo

### 4
Un `.class` contiene principalmente:

A. código fuente Java  
B. bytecode JVM  
C. un PDF  
D. código objeto `.obj` de Windows

### 5
La JVM:

A. es un editor  
B. proporciona el entorno para ejecutar bytecode Java  
C. es un lenguaje  
D. es un periférico

### 6
El linker:

A. enlaza código objeto/bibliotecas en los modelos que lo requieren  
B. escribe código Java  
C. sustituye la RAM  
D. es un teclado

### 7
Una clasificación multiparadigma significa:

A. el lenguaje puede soportar diferentes estilos de programación  
B. solo puede existir un paradigma  
C. el programa no se compila  
D. no necesita CPU

### 8
El JDK:

A. contiene herramientas de desarrollo Java  
B. es únicamente la JVM  
C. es un sistema operativo  
D. es código fuente

### 9
`javap -c` nos ayuda a:

A. inspeccionar instrucciones de un class file  
B. borrar Java  
C. instalar Windows  
D. crear un repositorio

### 10
RA1.b y RA1.g:

A. se evalúan también en esta práctica  
B. se reservan para UD02  
C. pertenecen a RA3  
D. no existen

---

# 42. Antes de terminar la unidad

Debes ser capaz de explicar sin memorizar un esquema:

> Escribo `Pedido.java`. `javac` lo compila y genera `Pedido.class`, que contiene bytecode. La JVM puede cargar y ejecutar ese código intermedio sobre la plataforma correspondiente. Durante la ejecución intervienen el sistema operativo, la memoria y el procesador.

Si puedes explicar además en qué se diferencia este flujo de:

```text
fuente
→ objeto
→ ejecutable nativo
```

has comprendido la idea central de UD01.

---

**Fin del material del alumno — UD01**