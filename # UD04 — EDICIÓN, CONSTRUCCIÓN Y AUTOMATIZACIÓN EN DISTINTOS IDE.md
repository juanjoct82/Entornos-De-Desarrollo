# UD04 — EDICIÓN, CONSTRUCCIÓN Y AUTOMATIZACIÓN EN DISTINTOS IDE

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 7 periodos lectivos  
**Resultado de Aprendizaje:** RA2  
**Práctica evaluable:** P04.1  
**Instrumento:** I-RA2-02  

**JDK estándar:** Eclipse Temurin JDK 25 LTS  
**IDE principal:** IntelliJ IDEA 2026.2  
**Segundo IDE:** Eclipse IDE 2026-09 for Java Developers  
**Entorno adicional:** Visual Studio Code + Extension Pack for Java  
**Segundo lenguaje:** Kotlin/JVM  

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

En UD03 construimos nuestra estación de desarrollo:

```text
Temurin 25
+
IntelliJ IDEA
+
Eclipse
+
plugins
+
personalización
+
actualizaciones
```

Ahora debemos responder preguntas diferentes:

```text
¿Puede un mismo entorno trabajar con lenguajes distintos?

¿Puede un mismo código construirse utilizando varios entornos?

¿Obtendremos exactamente los mismos archivos?

¿Qué tienen en común IntelliJ, Eclipse y VS Code?

¿Qué características son propias de cada uno?

¿Qué ocurre realmente cuando pulsamos Build?
```

Esta unidad no estudia ya cómo instalar el entorno.

Estudia:

# QUÉ PODEMOS HACER CON ÉL.

---

# 2. Resultado de Aprendizaje

## RA2

**Evalúa entornos integrados de desarrollo analizando sus características para editar código fuente y generar ejecutables.**

---

# 3. Criterios de evaluación de UD04

Se evalúan exclusivamente:

## RA2.e

**Se han generado ejecutables a partir de código fuente de diferentes lenguajes en un mismo entorno de desarrollo.**

## RA2.f

**Se han generado ejecutables a partir de un mismo código fuente con varios entornos de desarrollo.**

## RA2.g

**Se han identificado las características comunes y específicas de diversos entornos de desarrollo.**

Son las formulaciones oficiales vigentes.

---

# 4. CE reforzado pero no recalificado

Durante la unidad utilizaremos configuraciones y cierta automatización del entorno.

Esto puede reforzar:

```text
RA2.c
```

pero:

# RA2.c NO SE CALIFICA DE NUEVO.

Su fuente de evaluación sigue siendo:

```text
UD03
→ I-RA2-01.
```

---

# 5. ¿Qué aprenderemos?

Al terminar la unidad deberás poder:

- distinguir editar, compilar, construir y empaquetar;
- comprender qué es un artefacto;
- generar un JAR ejecutable;
- ejecutar un JAR fuera del IDE;
- trabajar con Java y Kotlin/JVM dentro de IntelliJ;
- producir ejecutables a partir de ambos lenguajes;
- trabajar con el mismo fuente Java en distintos entornos;
- generar el resultado con IntelliJ, Eclipse y VS Code;
- comprobar que el fuente no ha cambiado;
- utilizar hashes SHA-256 como evidencia de identidad;
- comprender por qué dos JAR equivalentes pueden no ser binariamente idénticos;
- comparar características comunes de varios entornos;
- identificar características específicas;
- seleccionar razonadamente un entorno según un escenario profesional.

---

# 6. Utilidad profesional

Un equipo puede utilizar:

```text
IntelliJ

Eclipse

VS Code
```

y aun así trabajar sobre:

```text
el mismo repositorio

el mismo código

el mismo JDK

los mismos requisitos.
```

También puede ocurrir lo contrario:

```text
UN SOLO IDE
     │
     ├── Java
     ├── Kotlin
     ├── SQL
     ├── JavaScript
     └── otros lenguajes
```

Un desarrollador debe distinguir:

```text
CÓDIGO
```

de:

```text
HERRAMIENTA UTILIZADA PARA TRABAJAR CON ÉL.
```

---

# 7. Editor, IDE y entorno extensible

No todos los productos se construyen del mismo modo.

## IntelliJ IDEA

Es un IDE con soporte integrado profundo para múltiples tareas de desarrollo.

## Eclipse

Es un IDE altamente modular construido sobre una plataforma extensible.

## Visual Studio Code

Es un editor de código extensible que, mediante extensiones, puede proporcionar un entorno de desarrollo completo para Java.

La documentación oficial de VS Code indica que el soporte Java procede de extensiones y recomienda **Extension Pack for Java** para disponer de edición, ejecución, depuración, testing, Maven y gestión de proyectos.

A efectos del CE hablamos de:

```text
diversos entornos de desarrollo
```

sin necesidad de afirmar que internamente estén diseñados de la misma forma.

---

# 8. Código fuente

Partimos de archivos como:

```text
Programa.java

Main.kt
```

que contienen código escrito por el desarrollador.

---

# 9. Compilar

Compilar transforma código fuente a otra representación.

En Java:

```text
.java
↓
compilación
↓
.class
```

En Kotlin/JVM:

```text
.kt
↓
compilador Kotlin
↓
bytecode JVM
```

Ambos pueden terminar ejecutándose sobre la JVM.

---

# 10. Construir

**Build** suele representar un proceso más amplio que una única compilación.

Puede incluir:

```text
compilar

procesar recursos

resolver dependencias

copiar archivos

empaquetar

generar artefactos
```

IntelliJ distingue operaciones de compilación y construcción, y puede realizar builds incrementales de proyectos Java y Kotlin.

---

# 11. Empaquetar

Empaquetar consiste en agrupar elementos necesarios para distribuir o ejecutar una aplicación.

En nuestro caso trabajaremos con:

```text
JAR
```

---

# 12. ¿Qué es un JAR?

JAR significa:

```text
Java Archive
```

y permite agrupar:

```text
clases compiladas

recursos

metadatos

manifest
```

en un único archivo.

Ejemplo:

```text
cartago-app.jar
```

---

# 13. JAR no significa necesariamente ejecutable

Un JAR puede contener:

```text
una biblioteca
```

sin tener un punto de entrada.

Para ejecutar:

```bash
java -jar aplicacion.jar
```

el paquete debe contener la información necesaria para localizar su clase principal.

---

# 14. Manifest

Un JAR ejecutable incluye normalmente información como:

```text
Main-Class
```

en:

```text
META-INF/MANIFEST.MF
```

Ejemplo conceptual:

```text
Manifest-Version: 1.0
Main-Class: ComparadorIDE
```

---

# 15. Artefacto

Llamaremos **artefacto** al resultado producido por un proceso de construcción.

Puede ser:

```text
JAR

WAR

directorio compilado

paquete

documentación generada
```

IntelliJ utiliza explícitamente el concepto de *artifact* para representar elementos ensamblados que pueden probarse, desplegarse o distribuirse.

---

# 16. CONOCIMIENTO AUXILIAR NO EVALUADO

Los conceptos:

```text
fuente

bytecode

JVM
```

pertenecen a RA1 y fueron evaluados en UD01.

Aquí únicamente se utilizan para comprender:

```text
el proceso de construcción.
```

No se vuelve a calificar RA1.

---

# 17. Primer laboratorio — JAR Java

Código:

```java
public class SaludoJava {

    public static void main(String[] args) {

        System.out.println(
            "Entornos de Desarrollo - Java"
        );
    }
}
```

Objetivo:

```text
fuente
↓
compilar
↓
empaquetar
↓
SaludoJava.jar
↓
java -jar
↓
resultado
```

---

# 18. JAR con IntelliJ

Una ruta posible en IntelliJ:

```text
File
→ Project Structure
→ Artifacts
→ +
→ JAR
→ From modules with dependencies
```

seleccionando posteriormente:

```text
Main Class
```

y construyendo mediante:

```text
Build
→ Build Artifacts
```

La documentación oficial de IntelliJ 2026.2 mantiene este flujo para crear y construir JAR ejecutables.

---

# 19. CAPTURA UD04-01 — Artifact Java

Debe mostrar:

```text
Project Structure
→ Artifacts
```

con:

```text
Main Class

output directory

manifest.
```

---

# 20. Ejecutar fuera del IDE

Después de construir:

```bash
java -jar SaludoJava.jar
```

Resultado:

```text
Entornos de Desarrollo - Java
```

Este paso es importante.

No basta demostrar:

```text
botón Run del IDE.
```

Queremos verificar que existe:

# UN ARTEFACTO EJECUTABLE.

---

# 21. RA2.e — Distintos lenguajes en un mismo entorno

Para demostrar RA2.e utilizaremos:

```text
IntelliJ IDEA
```

con:

```text
Java

Kotlin/JVM.
```

IntelliJ 2026.2 incluye soporte específico para Kotlin y el plugin Kotlin se distribuye integrado y habilitado por defecto.

---

# 22. ¿Por qué Kotlin?

Kotlin permite observar algo interesante:

```text
Java source
      │
      └────► JVM bytecode

Kotlin source
      │
      └────► JVM bytecode
```

Dos lenguajes diferentes pueden utilizar:

```text
la misma plataforma de ejecución.
```

---

# 23. Programa Kotlin

```kotlin
fun main() {

    println(
        "Entornos de Desarrollo - Kotlin"
    )
}
```

Archivo:

```text
Main.kt
```

---

# 24. Kotlin en IntelliJ

IntelliJ permite:

```text
crear proyecto Kotlin

editar

ejecutar

construir

empaquetar
```

desde el mismo entorno. La documentación oficial muestra también el empaquetado como JAR y su ejecución posterior mediante `java -jar`.

---

# 25. Particularidad de Kotlin

Para ejecutar correctamente un programa Kotlin empaquetado debemos proporcionar:

```text
Kotlin runtime
```

bien:

```text
incluido en el JAR
```

o:

```text
disponible externamente.
```

Para nuestra práctica produciremos un:

# JAR AUTOSUFICIENTE PARA EL EJERCICIO

incluyendo las dependencias necesarias.

---

# 26. CAPTURA UD04-02 — Proyecto Kotlin

Debe mostrar:

```text
IntelliJ

proyecto Kotlin

Main.kt

Temurin 25.
```

---

# 27. CAPTURA UD04-03 — JAR Kotlin

Debe mostrar:

```text
artefacto generado

y

ejecución con java -jar.
```

---

# 28. Actividad A04.1 — Dos lenguajes, un entorno

En IntelliJ:

1. construye `SaludoJava`;
2. genera `SaludoJava.jar`;
3. ejecútalo;
4. crea `SaludoKotlin`;
5. genera su JAR;
6. ejecútalo.

Completa:

| Aspecto | Java | Kotlin |
|---|---|---|
| Extensión fuente | | |
| Compilador/proceso | | |
| Resultado JVM | | |
| Artefacto generado | | |
| Comando ejecución | | |

Pregunta:

> ¿Qué demuestra este ejercicio respecto a la relación entre lenguaje y entorno?

---

# 29. Un mismo código en varios entornos

Ahora cambia la pregunta.

Ya no queremos:

```text
dos lenguajes
+
un IDE
```

sino:

```text
UN MISMO CÓDIGO
+
VARIOS ENTORNOS.
```

Esto es exactamente el núcleo de:

# RA2.f.

---

# 30. Archivo canónico

Utilizaremos:

```text
ComparadorIDE.java
```

con este contenido:

```java
public class ComparadorIDE {

    public static void main(String[] args) {

        String centro = "Miralmonte";
        int curso = 2026;

        System.out.println(
            centro + " FP " + curso
        );
    }
}
```

---

# 31. Regla fundamental de RA2.f

Está prohibido modificar el fuente al cambiar de entorno.

Debemos demostrar:

```text
MISMO ARCHIVO

MISMO CONTENIDO

DISTINTO ENTORNO
```

---

# 32. Hash SHA-256

Para demostrar objetivamente que el archivo no cambia calcularemos un:

```text
SHA-256
```

del fuente.

En PowerShell:

```powershell
Get-FileHash .\ComparadorIDE.java -Algorithm SHA256
```

En sistemas que dispongan de `sha256sum`:

```bash
sha256sum ComparadorIDE.java
```

---

# 33. Qué esperamos

Ejemplo conceptual:

```text
IntelliJ
ComparadorIDE.java
SHA256 = ABC123...

Eclipse
ComparadorIDE.java
SHA256 = ABC123...

VS Code
ComparadorIDE.java
SHA256 = ABC123...
```

Los tres hashes del:

```text
FUENTE
```

deben coincidir.

---

# 34. CAPTURA UD04-04 — Hash del fuente

Debe mostrar el SHA-256 de:

```text
ComparadorIDE.java
```

antes de comenzar la comparación.

---

# 35. Entorno 1 — IntelliJ IDEA

Importa o abre el fuente.

Configura:

```text
Temurin 25
```

sin editar `ComparadorIDE.java`.

Construye un:

```text
JAR ejecutable.
```

---

# 36. Verificación IntelliJ

Ejecuta:

```bash
java -jar ComparadorIDE-IntelliJ.jar
```

Resultado esperado:

```text
Miralmonte FP 2026
```

---

# 37. Entorno 2 — Eclipse

Utiliza exactamente el mismo:

```text
ComparadorIDE.java
```

En Eclipse puedes generar un JAR ejecutable mediante:

```text
File
→ Export
→ Java
→ Runnable JAR file.
```

La documentación oficial de Eclipse mantiene un asistente específico para generar Runnable JAR.

---

# 38. CAPTURA UD04-05 — Eclipse Runnable JAR

Debe mostrar:

```text
Launch configuration

Export destination

Library handling.
```

---

# 39. Verificación Eclipse

Ejecuta:

```bash
java -jar ComparadorIDE-Eclipse.jar
```

Resultado:

```text
Miralmonte FP 2026
```

---

# 40. Entorno 3 — Visual Studio Code

Instalaremos previamente:

```text
Extension Pack for Java
```

si no se encuentra disponible.

Este paquete agrupa las extensiones principales para:

```text
edición

depuración

testing

Maven

gestión de proyectos.
```


---

# 41. Abrir el mismo archivo

Trabajaremos nuevamente con:

```text
ComparadorIDE.java
```

sin modificarlo.

---

# 42. Exportar JAR desde VS Code

El soporte oficial Java permite utilizar:

```text
Java: Export Jar...
```

desde la Command Palette o la vista de proyectos.

Cuando proceda se seleccionará:

```text
la clase principal
```

para obtener el artefacto del ejercicio.

---

# 43. CAPTURA UD04-06 — VS Code Export Jar

Debe mostrar:

```text
Command Palette

Java: Export Jar...
```

o la acción equivalente desde Projects.

---

# 44. Verificación VS Code

Ejecuta el artefacto generado y comprueba:

```text
Miralmonte FP 2026
```

La forma final de lanzamiento utilizada debe quedar documentada.

---

# 45. Volver a calcular el hash

Después del trabajo en cada entorno vuelve a calcular:

```text
SHA-256
```

del fuente.

Tabla:

| Entorno | SHA-256 de `ComparadorIDE.java` |
|---|---|
| IntelliJ | |
| Eclipse | |
| VS Code | |

Resultado esperado:

# LOS TRES COINCIDEN.

---

# 46. ¿Deben coincidir también los hashes de los JAR?

# NO.

Esto es fundamental.

Dos JAR pueden:

```text
provenir del mismo fuente

hacer exactamente lo mismo
```

y sin embargo tener:

```text
SHA-256 diferentes.
```

---

# 47. ¿Por qué?

El artefacto puede contener diferencias en:

```text
manifest

orden de entradas

fechas internas

metadatos

estrategia de empaquetado

herramientas utilizadas.
```

Por tanto:

```text
MISMO FUENTE
≠
NECESARIAMENTE MISMO BINARIO.
```

---

# 48. Qué debemos demostrar realmente

Para RA2.f:

```text
mismo fuente
+
varios entornos
+
artefactos funcionales
+
mismo comportamiento esperado.
```

No:

```text
JAR binariamente idéntico.
```

---

# 49. Actividad A04.2 — Fuente vs artefacto

Calcula también, opcionalmente:

```text
SHA-256 de los JAR
```

y responde:

1. ¿Coinciden los hashes del fuente?
2. ¿Coinciden los hashes de los JAR?
3. ¿Tienen los tres el mismo comportamiento?
4. ¿Por qué no debemos confundir equivalencia funcional con identidad binaria?

---

# 50. Características comunes de los entornos

IntelliJ, Eclipse y VS Code con sus extensiones Java pueden proporcionar funcionalidades como:

```text
edición

coloreado sintáctico

autocompletado

navegación

compilación/construcción

ejecución

depuración

gestión de proyectos

integración con build tools

integración con Git
```

aunque:

```text
su implementación
y nivel de integración
son diferentes.
```

---

# 51. IntelliJ — características destacables

Entre otras:

```text
modelo de proyecto propio

integración Java/Kotlin profunda

artifacts

refactorizaciones

inspections

plugins

herramientas de construcción integradas.
```

IntelliJ 2026.2 mantiene soporte nativo de compilación/construcción Java y Kotlin y un sistema de artefactos propio.

---

# 52. Eclipse — características destacables

Entre otras:

```text
workspace

perspectives

views

JDT

ecosistema de plugins

Export Runnable JAR.
```

El paquete Java 2026-09 incluye JDT, Git y soporte integrado para Maven y Gradle.

---

# 53. VS Code — características destacables

Entre otras:

```text
editor ligero

Command Palette

modelo basado en extensiones

folder workspace

multi-root workspace

Extension Pack for Java

Export Jar.
```

En VS Code el concepto de proyecto Java procede de las extensiones, no del núcleo del editor.

---

# 54. CAPTURA UD04-07 — Tres entornos

La edición definitiva deberá mostrar conjuntamente:

```text
IntelliJ

Eclipse

VS Code
```

con:

```text
ComparadorIDE.java
```

abierto en los tres.

El objetivo visual es comprobar:

# MISMO CÓDIGO, DISTINTA HERRAMIENTA.

---

# 55. Common ≠ identical

Que varios entornos permitan:

```text
compilar
```

no significa que:

```text
utilicen internamente
el mismo builder
```

ni que:

```text
la interfaz sea idéntica.
```

RA2.g exige identificar:

```text
LO COMÚN
```

y:

```text
LO ESPECÍFICO.
```

---

# 56. Matriz de comparación

| Dimensión | IntelliJ | Eclipse | VS Code + Java |
|---|---|---|---|
| Gestión de proyecto | | | |
| Configuración JDK | | | |
| Editor Java | | | |
| Construcción | | | |
| Exportación JAR | | | |
| Plugins/extensiones | | | |
| Depuración | | | |
| Build tools | | | |
| Git | | | |
| Segundo lenguaje | | | |
| Modelo de workspace | | | |
| Facilidad inicial | | | |

---

# 57. No buscamos declarar un “ganador”

La conclusión:

```text
IntelliJ gana
```

no demuestra RA2.g.

Tampoco:

```text
Eclipse es peor

VS Code es mejor.
```

El criterio pide:

# IDENTIFICAR CARACTERÍSTICAS.

Una conclusión profesional puede ser:

> IntelliJ resulta apropiado para este escenario porque...

o:

> VS Code resulta suficiente para este otro porque...

si se justifica mediante características observables.

---

# 58. Selección según escenario

## Escenario A

Proyecto Java/Kotlin grande.

Puede resultar especialmente útil:

```text
un IDE con integración profunda
de ambos lenguajes.
```

## Escenario B

Edición rápida de varios lenguajes y tecnologías.

Puede ser atractivo:

```text
un editor extensible y ligero.
```

## Escenario C

Equipo que ya utiliza ampliamente:

```text
workspace

JDT

ecosistema Eclipse.
```

Eclipse puede encajar perfectamente.

---

# 59. El entorno no sustituye al conocimiento

Un IDE puede:

```text
autocompletar

crear archivos

compilar

refactorizar
```

pero el alumno debe comprender:

```text
qué está ocurriendo.
```

Esto conecta con UD01:

```text
fuente
↓
construcción
↓
artefacto
↓
ejecución.
```

---

# 60. CONOCIMIENTO AUXILIAR NO EVALUADO

La gestión profesional de Git pertenece a:

```text
RA4.f
RA4.h
```

y se evaluará en UD05.

En esta unidad solo podemos reconocer:

```text
"este entorno integra Git"
```

como característica comparativa.

No se califica el uso de Git.

---

# 61. CONOCIMIENTO AUXILIAR NO EVALUADO

La depuración pertenece evaluativamente a:

```text
RA3
```

Aunque los tres entornos dispongan de debugger, en UD04 únicamente se identifica como:

```text
característica común/específica.
```

No se evalúa la competencia de depuración.

---

# 62. Build automatizado

Un entorno puede:

```text
guardar configuraciones

delegar builds

ejecutar tareas

invocar Maven/Gradle
```

y hacer repetible el proceso de construcción.

Este contenido refuerza el concepto de:

```text
automatización
```

trabajado en UD03.

No genera una segunda nota:

```text
RA2.c.
```

---

# 63. IntelliJ y build tools

IntelliJ puede utilizar su builder propio o delegar tareas a herramientas como:

```text
Maven

Gradle.
```

Para proyectos donde el script de build contiene lógica específica, JetBrains recomienda que la construcción se delegue al build tool correspondiente.

---

# 64. VS Code y build tools

El Extension Pack for Java incorpora soporte para Maven y existen extensiones específicas para Gradle.

---

# 65. Eclipse y build tools

El paquete Java 2026-09 incorpora:

```text
Maven Integration

Gradle Integration
```

junto con JDT y Git.

---

# 66. Actividad A04.3 — ¿Qué es común?

Marca qué capacidades existen en:

```text
IntelliJ

Eclipse

VS Code + Java
```

para:

- edición Java;
- ejecución;
- depuración;
- plugins;
- Git;
- Maven;
- exportación/paquetización;
- configuración del JDK.

Después responde:

> ¿Que una característica exista en los tres significa que funciona exactamente igual?

---

# 67. Actividad A04.4 — ¿Qué es específico?

Identifica al menos:

```text
2 características
```

especialmente representativas de cada entorno.

No se admiten como respuestas suficientes:

```text
el color

el logo

me gusta más.
```

---

# 68. Actividad A04.5 — Elige entorno

Casos:

### Caso 1

Desarrollo Java + Kotlin.

### Caso 2

Proyecto Java existente basado en workspace Eclipse.

### Caso 3

Alumno que trabaja simultáneamente con Java, HTML, JavaScript y pequeños scripts.

### Caso 4

Proyecto corporativo Java con fuerte uso de inspections y refactorización.

Propón un entorno para cada uno y justifica.

No existe necesariamente una única respuesta válida.

---

# 69. Error frecuente — Run no es un ejecutable

Pulsar:

```text
Run
```

y mostrar una consola no demuestra por sí solo:

```text
RA2.e

o

RA2.f.
```

Debemos conservar un:

```text
artefacto generado
```

y comprobar su ejecución.

---

# 70. Error frecuente — modificar el código para cada IDE

Si hacemos:

```text
IntelliJ
→ código A

Eclipse
→ código B
```

no estamos demostrando correctamente:

```text
RA2.f.
```

El fuente debe ser:

# EL MISMO.

---

# 71. Error frecuente — confundir proyecto con código

Los tres entornos pueden generar:

```text
archivos de proyecto diferentes.
```

Eso es aceptable.

Lo que no cambia es:

```text
ComparadorIDE.java.
```

---

# 72. Error frecuente — exigir JAR idéntico

Incorrecto:

> Los tres JAR tienen que tener el mismo SHA-256.

No.

Lo que debe mantenerse idéntico para nuestra prueba es:

```text
el fuente.
```

Los artefactos pueden contener metadatos distintos.

---

# 73. Error frecuente — copiar la tabla de Internet

RA2.g no se demuestra copiando:

```text
"IntelliJ tiene autocompletado"
```

de una web.

Debemos comparar:

```text
los entornos utilizados
```

y relacionar las características con la experiencia técnica de la práctica.

---

# 74. Buenas prácticas

## Conservar un código canónico

Antes de comparar entornos:

```text
fuente original
+
hash.
```

## Verificar fuera del IDE

Cuando sea posible:

```bash
java -jar ...
```

## Documentar el procedimiento

Registrar:

```text
entorno

JDK

ruta de build

artefacto

resultado.
```

## Comparar hechos

No preferencias personales.

## Diferenciar fuente y metadatos

El entorno puede crear:

```text
.idea

.project

.classpath

.vscode
```

sin modificar necesariamente:

```text
el código fuente.
```

---

# 75. Ejemplo resuelto — misma aplicación

Fuente:

```java
public class Demo {

    public static void main(String[] args) {
        System.out.println("Demo");
    }
}
```

Se utiliza en:

```text
IntelliJ

Eclipse.
```

Ambos generan:

```text
Demo-IDEA.jar

Demo-Eclipse.jar
```

Ambos muestran:

```text
Demo
```

Conclusión:

```text
mismo código

+
diferente entorno

+
misma funcionalidad observable.
```

No concluimos necesariamente:

```text
mismo binario.
```

---

# 76. Ejercicios de consolidación

1. Diferencia compilar y construir.
2. ¿Qué es empaquetar?
3. ¿Qué es un artefacto?
4. ¿Qué es un JAR?
5. ¿Todo JAR es ejecutable?
6. ¿Qué función tiene `Main-Class`?
7. ¿Qué demuestra `java -jar`?
8. ¿Qué pide RA2.e?
9. ¿Qué lenguajes utilizaremos para RA2.e?
10. ¿Por qué Java y Kotlin pueden compartir la JVM?
11. ¿Qué pide RA2.f?
12. ¿Por qué debe mantenerse el mismo fuente?
13. ¿Qué utilidad tiene SHA-256?
14. ¿Qué debe coincidir en nuestra prueba?
15. ¿Deben coincidir los hashes de los JAR?
16. ¿Por qué pueden ser diferentes?
17. ¿Qué significa característica común?
18. ¿Qué significa característica específica?
19. ¿VS Code proporciona Java únicamente con el núcleo?
20. ¿Qué paquete recomendamos para Java en VS Code?
21. ¿Qué característica propia tiene el modelo de Eclipse?
22. ¿Qué permite `Java: Export Jar...`?
23. ¿Qué permite `Build Artifacts`?
24. ¿Qué permite `Runnable JAR Export`?
25. ¿Debemos elegir un entorno únicamente porque “nos gusta más”?

---

# 77. Actividad de ampliación

Investiga:

```text
reproducible builds
```

y responde:

> ¿Qué condiciones adicionales serían necesarias para intentar que dos procesos independientes generaran exactamente el mismo artefacto binario?

No es evaluable.

---

# 78. Resumen

RA2.e:

```text
DISTINTOS LENGUAJES
+
MISMO ENTORNO

Java ─────┐
          ├── IntelliJ
Kotlin ───┘
```

RA2.f:

```text
MISMO FUENTE
+
VARIOS ENTORNOS

ComparadorIDE.java
   ├── IntelliJ
   ├── Eclipse
   └── VS Code
```

RA2.g:

```text
COMPARAR
↓
características comunes
+
características específicas.
```

---

# 79. Glosario

**Artefacto:** resultado generado por un proceso de construcción.

**Build:** proceso que puede incluir compilación, recursos, dependencias y empaquetado.

**Build tool:** herramienta destinada a automatizar procesos de construcción.

**Compilación:** transformación del código fuente a otra representación.

**Entorno de desarrollo:** conjunto de herramientas utilizado para crear y trabajar con software.

**Hash:** valor calculado a partir del contenido de datos y útil, entre otras cosas, para comprobar identidad o cambios.

**JAR:** archivo Java Archive.

**Manifest:** archivo de metadatos de un JAR.

**Main-Class:** atributo que identifica la clase principal de un JAR ejecutable.

**Packaging:** proceso de empaquetado de una aplicación.

**SHA-256:** función hash utilizada aquí para demostrar identidad del archivo fuente.

**Workspace:** espacio de trabajo utilizado por determinados entornos.

---

# 80. Autoevaluación

### 1
RA2.e exige:

A. varios lenguajes en un mismo entorno  
B. varios alumnos  
C. un único lenguaje y un IDE  
D. Git

### 2
RA2.f exige:

A. distinto código en varios entornos  
B. el mismo código con varios entornos  
C. Kotlin exclusivamente  
D. UML

### 3
RA2.g evalúa:

A. características de diversos entornos  
B. depuración avanzada  
C. testing  
D. Git

### 4
Un JAR:

A. siempre es ejecutable  
B. puede ser ejecutable o biblioteca  
C. es código fuente  
D. es un IDE

### 5
Para `java -jar` es relevante:

A. Main-Class  
B. README únicamente  
C. `.idea`  
D. workspace

### 6
SHA-256 del fuente permite comprobar:

A. identidad de contenido  
B. que el programa sea correcto  
C. calidad del código  
D. licencia

### 7
Si los hashes de los JAR son diferentes:

A. RA2.f falla automáticamente  
B. puede ser completamente normal  
C. el fuente necesariamente cambió  
D. Java no funciona

### 8
VS Code para Java utiliza principalmente:

A. extensiones  
B. UML  
C. BIOS  
D. SQL exclusivamente

### 9
Eclipse permite:

A. exportar Runnable JAR  
B. solo editar texto  
C. únicamente Kotlin  
D. no usar Java

### 10
La comparación profesional debe basarse en:

A. características observables  
B. color favorito  
C. logotipo  
D. popularidad únicamente

---

# 81. PRÁCTICA EVALUABLE P04.1

# UN CÓDIGO, VARIOS ENTORNOS

**Modalidad:** individual  
**RA:** RA2  
**CE evaluados:** RA2.e, RA2.f, RA2.g  
**Instrumento:** I-RA2-02

---

# 82. Objetivo

Demostrar que eres capaz de:

```text
generar aplicaciones
de distintos lenguajes
en un mismo entorno

+

generar una aplicación
desde el mismo fuente
con varios entornos

+

comparar técnicamente
los entornos utilizados.
```

---

# 83. PARTE A — Java en IntelliJ

Crea:

```text
P04_Java
```

con:

```java
public class LenguajeJava {

    public static void main(String[] args) {

        System.out.println(
            "P04 - Java - Miralmonte"
        );
    }
}
```

Genera:

```text
LenguajeJava.jar
```

y ejecuta:

```bash
java -jar LenguajeJava.jar
```

---

# 84. PARTE B — Kotlin en IntelliJ

Crea:

```text
P04_Kotlin
```

con:

```kotlin
fun main() {

    println(
        "P04 - Kotlin - Miralmonte"
    )
}
```

Genera:

```text
LenguajeKotlin.jar
```

incluyendo lo necesario para su ejecución.

Comprueba:

```bash
java -jar LenguajeKotlin.jar
```

---

# 85. Evidencia RA2.e

Debes conservar:

```text
E-RA2.e-01
Proyecto/ejecutable Java en IntelliJ.

E-RA2.e-02
Proyecto/ejecutable Kotlin en IntelliJ.

E-RA2.e-03
Ejecución externa de ambos artefactos.

E-RA2.e-04
Explicación comparativa.
```

---

# 86. PARTE C — Fuente canónico

Crea una carpeta:

```text
P04_CANONICO
```

con:

```text
ComparadorIDE.java
```

exactamente como lo entrega el profesor.

No lo modifiques posteriormente.

---

# 87. PARTE D — Hash inicial

Calcula:

```text
SHA-256
```

y registra:

```text
HASH ORIGINAL =
____________________________
```

---

# 88. PARTE E — IntelliJ

Utiliza exactamente el fuente canónico.

Genera:

```text
ComparadorIDE-IntelliJ.jar
```

Ejecuta y conserva resultado.

Calcula nuevamente el hash del `.java`.

---

# 89. PARTE F — Eclipse

Utiliza exactamente el mismo archivo.

Genera:

```text
ComparadorIDE-Eclipse.jar
```

mediante:

```text
Runnable JAR Export.
```

Ejecuta.

Calcula el hash del fuente.

---

# 90. PARTE G — VS Code

Utiliza exactamente el mismo archivo.

Con Java Extension Pack:

```text
abre

construye/exporta

genera el JAR.
```

Artefacto:

```text
ComparadorIDE-VSCode.jar
```

Verifica su ejecución.

Calcula el hash del fuente.

---

# 91. Tabla de identidad

| Entorno | Hash fuente | Salida |
|---|---|---|
| Original | | — |
| IntelliJ | | |
| Eclipse | | |
| VS Code | | |

Conclusión obligatoria:

```text
¿El fuente permaneció idéntico?
SÍ / NO
```

Justifica.

---

# 92. PARTE H — JAR

Calcula opcionalmente los hashes de:

```text
ComparadorIDE-IntelliJ.jar

ComparadorIDE-Eclipse.jar

ComparadorIDE-VSCode.jar
```

Si difieren, explica:

> ¿Por qué no invalida eso RA2.f?

---

# 93. Evidencia RA2.f

```text
E-RA2.f-01
Fuente canónico.

E-RA2.f-02
Hashes SHA-256 iguales del fuente.

E-RA2.f-03
JAR IntelliJ ejecutado.

E-RA2.f-04
JAR Eclipse ejecutado.

E-RA2.f-05
JAR VS Code ejecutado.

E-RA2.f-06
Conclusión sobre equivalencia.
```

---

# 94. PARTE I — Comparación de entornos

Completa:

| Característica | IntelliJ | Eclipse | VS Code |
|---|---|---|---|
| Tipo de entorno | | | |
| Proyecto/workspace | | | |
| JDK | | | |
| Edición Java | | | |
| Build | | | |
| JAR | | | |
| Plugins | | | |
| Git | | | |
| Build tools | | | |
| Kotlin | | | |
| Rasgo especialmente propio | | | |

---

# 95. PARTE J — Características comunes

Identifica al menos:

```text
5 características comunes
```

y explica brevemente cómo aparecen en cada entorno.

---

# 96. PARTE K — Características específicas

Identifica al menos:

```text
2 características especialmente
representativas de cada entorno.
```

No se admiten diferencias meramente estéticas.

---

# 97. PARTE L — Selección profesional

Responde:

### Escenario 1

Proyecto Java/Kotlin grande.

¿Qué entorno elegirías y por qué?

### Escenario 2

Edición ligera de Java y tecnologías web.

¿Qué entorno elegirías y por qué?

### Escenario 3

Proyecto heredado construido alrededor de Eclipse/JDT.

¿Qué entorno elegirías y por qué?

No existe una respuesta única.

Se evalúa la justificación.

---

# 98. Evidencias RA2.g

```text
E-RA2.g-01
Matriz comparativa.

E-RA2.g-02
Características comunes.

E-RA2.g-03
Características específicas.

E-RA2.g-04
Selección razonada según escenario.
```

---

# 99. Entregables

```text
P04.1_Apellidos_Nombre.pdf
```

más:

```text
LenguajeJava.jar

LenguajeKotlin.jar

ComparadorIDE-IntelliJ.jar

ComparadorIDE-Eclipse.jar

ComparadorIDE-VSCode.jar
```

cuando la plataforma permita adjuntarlos.

También deberá conservarse:

```text
ComparadorIDE.java
```

como fuente canónico.

---

# 100. Instrumento I-RA2-02

**Instrumento:** I-RA2-02  
**RA:** RA2  
**CE:** RA2.e, RA2.f, RA2.g  
**Actividad:** P04.1 – Un código, varios entornos  
**Tipo:** laboratorio técnico individual  

Cada CE recibe:

```text
NOTA 0,00–10,00
```

de forma independiente.

---

# 101. Rúbrica definitiva I-RA2-02

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA2.e** | Genera ejecutables a partir de código fuente de diferentes lenguajes en un mismo entorno | No consigue construir artefactos funcionales de ambos lenguajes o confunde ejecución desde IDE con generación del ejecutable | Obtiene resultados básicos de Java y Kotlin con ayuda y al menos los ejecuta correctamente | Genera, empaqueta y ejecuta correctamente aplicaciones Java y Kotlin desde IntelliJ, identificando fuente, artefacto y proceso | Además compara con precisión ambos procesos, dependencias/runtime y demuestra autonomía en la construcción | **100 % del CE** |
| **RA2.f** | Genera ejecutables a partir del mismo código fuente utilizando varios entornos | Modifica el fuente, no acredita su identidad o no consigue resultados en varios entornos | Utiliza el mismo programa en al menos varios entornos pero la evidencia de identidad/construcción es incompleta | Conserva el mismo fuente, acredita SHA-256 y genera/ejecuta correctamente los artefactos en IntelliJ, Eclipse y VS Code | Además analiza diferencias de empaquetado, distingue identidad del fuente de identidad binaria y documenta de forma completamente reproducible el proceso | **100 % del CE** |
| **RA2.g** | Identifica características comunes y específicas de diversos entornos de desarrollo | La comparación es superficial, subjetiva o técnicamente incorrecta | Reconoce algunas características comunes y diferencias básicas | Compara sistemáticamente IntelliJ, Eclipse y VS Code y distingue correctamente características comunes y específicas | Además relaciona esas características con escenarios profesionales y justifica con precisión la elección de entorno según contexto | **100 % del CE** |

---

# 102. Nota informativa de P04.1

Puede mostrarse:

```text
(
 RA2.e
+RA2.f
+RA2.g
) / 3
```

pero el registro definitivo conserva:

```text
RA2.e

RA2.f

RA2.g
```

individualmente.

---

# 103. Temporalización definitiva

| Sesión | Contenido | Actividad |
|---:|---|---|
| 1 | Compilar, construir, empaquetar y artefactos | JAR Java |
| 2 | Java + Kotlin en IntelliJ | A04.1 |
| 3 | Mismo fuente en IntelliJ y Eclipse | inicio A04.2 |
| 4 | VS Code + hash + comparación de artefactos | A04.2 |
| 5 | Características comunes/específicas | A04.3–5 |
| 6 | P04.1 — desarrollo | práctica evaluable |
| 7 | P04.1 — finalización/evaluación | I-RA2-02 |

**Total: 7 periodos.**

---

# 104. Autoevaluación — soluciones

```text
1 → A
2 → B
3 → A
4 → B
5 → A
6 → A
7 → B
8 → A
9 → A
10 → A
```

---

# PARTE B — MATERIAL DEL PROFESOR

# 105. Finalidad docente

UD04 debe romper tres ideas erróneas:

```text
lenguaje = IDE

Run = ejecutable

mismo fuente = mismo binario.
```

El alumno debería terminar comprendiendo:

```text
un entorno puede soportar
varios lenguajes

y

un mismo lenguaje/fuente puede
trabajarse en diferentes entornos.
```

---

# 106. Punto crítico de RA2.e

No basta:

```text
crear un .java

crear un .kt

pulsar Run.
```

Debe aparecer evidencia de:

```text
artefacto generado

+

ejecución del artefacto.
```

---

# 107. Solución conceptual RA2.e

```text
INTELLIJ
   │
   ├── LenguajeJava.java
   │       ↓
   │   bytecode
   │       ↓
   │   Java JAR
   │
   └── Main.kt
           ↓
       bytecode JVM
           ↓
       Kotlin JAR
```

Ambos:

```text
java -jar ...
```

cuando estén correctamente empaquetados.

---

# 108. Kotlin

La versión definitiva no debe exigir memorizar:

```text
versión exacta del compilador Kotlin.
```

El estándar didáctico es:

```text
Kotlin/JVM
+
plugin compatible de IntelliJ 2026.2.
```

Así evitamos que una actualización menor invalide las instrucciones.

---

# 109. Punto crítico RA2.f

El profesor debe preparar antes de la práctica:

```text
ComparadorIDE.java
```

como archivo canónico.

Puede distribuir:

```text
hash esperado
```

o pedir al alumnado que lo calcule delante del profesor al comenzar.

---

# 110. Integridad del fuente

Si:

```text
hash IntelliJ
≠
hash Eclipse
```

debe investigarse antes de continuar.

Puede deberse, por ejemplo, a:

```text
edición accidental

cambio de fin de línea

encoding alterado.
```

Incluso una variación de bytes:

```text
cambia SHA-256.
```

---

# 111. Fin de línea

Si se copia el archivo mediante sistemas que convierten:

```text
CRLF ↔ LF
```

el hash podría cambiar aunque visualmente el código parezca igual.

Para la práctica:

```text
copiar el archivo binariamente
sin reformatear
```

es la opción preferente.

---

# 112. Si VS Code no produce JAR ejecutable directamente

El objetivo evaluativo sigue siendo:

```text
generar un artefacto
desde ese entorno.
```

El profesor puede utilizar un proyecto Java preparado cuya configuración permita al comando:

```text
Java: Export Jar...
```

identificar correctamente la clase principal.

No debe improvisarse el día de la evaluación.

---

# 113. JAR hashes

No penalizar:

```text
JAR SHA-256 distinto.
```

De hecho, puede utilizarse didácticamente para explicar:

```text
SOURCE REPRODUCIBILITY
≠
BINARY REPRODUCIBILITY.
```

---

# 114. Comparación RA2.g

La rúbrica debe evitar:

```text
IntelliJ = 10

Eclipse = 7

VS Code = 8.
```

No evaluamos qué entorno “gana”.

Evaluamos si el alumno puede:

```text
identificar

comparar

seleccionar según necesidades.
```

---

# 115. Solución orientativa de matriz

| Aspecto | IntelliJ | Eclipse | VS Code |
|---|---|---|---|
| JDK | SDK de proyecto | Installed JRE/JDK | runtime config/extensiones |
| Java | integrado | JDT | Extension Pack |
| JAR | Artifacts | Runnable JAR Export | Java: Export Jar |
| Plugins | Marketplace | Marketplace/update sites | Extensions |
| Workspace | proyecto/módulos | workspace/proyectos | folder/multi-root workspace |
| Kotlin | soporte integrado | requiere soporte adicional | extensiones según necesidad |
| Build tools | Maven/Gradle | Maven/Gradle | Maven/Gradle mediante extensiones |

Aceptar terminología equivalente técnicamente correcta.

---

# 116. Características comunes esperables

Al menos:

```text
edición Java

navegación

autocompletado

ejecución

depuración

gestión de proyectos

extensibilidad

JDK

Git

build tools.
```

No es necesario que la implementación sea idéntica.

---

# 117. Características específicas posibles

## IntelliJ

```text
Artifacts

integración Java/Kotlin

Project Structure

inspections/refactorizaciones.
```

## Eclipse

```text
workspace

perspectives/views

JDT

Runnable JAR wizard.
```

## VS Code

```text
Command Palette

arquitectura extension-driven

folder/multi-root workspace

Java: Export Jar.
```

---

# 118. Medidas de apoyo

Para alumnado con dificultades:

- proporcionar proyecto Java ya creado;
- facilitar checklist por entorno;
- entregar plantilla comparativa;
- proporcionar comandos SHA-256;
- practicar previamente con un fuente distinto;
- proporcionar rutas de menú.

No debe entregarse:

```text
la comparación final razonada.
```

---

# 119. Ampliación

Alumnado avanzado puede:

```text
comparar manifiestos

listar contenido con jar tf

comparar tamaños

estudiar reproducible builds

utilizar Maven en los tres entornos
```

sin introducir nuevos CE.

---

# 120. Recuperación

Instrumento:

# IR-RA2-01

Bloques asociados a UD04:

```text
RA2.e

RA2.f

RA2.g
```

Ejemplo:

```text
RA2.e = 7
RA2.f = 3
RA2.g = 8
```

Si RA2 queda no superado y solo necesita nueva evidencia de:

```text
RA2.f
```

se asigna únicamente:

```text
bloque RA2.f
```

del IR-RA2-01.

---

# 121. Trazabilidad

| RA | CE | Contenido | Actividades | Instrumento | Evidencia |
|---|---|---|---|---|---|
| RA2 | e | distintos lenguajes/mismo entorno | A04.1 | P04.1 / I-RA2-02 | E-RA2.e-01/04 |
| RA2 | f | mismo fuente/varios entornos | A04.2 | P04.1 / I-RA2-02 | E-RA2.f-01/06 |
| RA2 | g | características comunes/específicas | A04.3–5 | P04.1 / I-RA2-02 | E-RA2.g-01/04 |

---

# 122. Situación completa de RA2

Tras UD03:

```text
a ✔
b ✔
c ✔
d ✔
```

Tras UD04:

```text
e ✔
f ✔
g ✔
```

Resultado:

# RA2 COMPLETAMENTE CUBIERTO.

---

# 123. Cálculo definitivo RA2

Todos los CE tienen igual peso:

```text
1/7
```

Por tanto:

```text
RA2 =
(
 a+b+c+d+e+f+g
) / 7
```

I-RA2-02 no posee un peso arbitrario independiente.

---

# 124. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA2

**CE evaluados:**

```text
RA2.e
RA2.f
RA2.g
```

### ¿Se refuerza RA2.c?

Sí.

La automatización del build puede reutilizar conceptos de UD03.

# NO SE RECALIFICA.

### ¿Se evalúa Java como RA1?

# NO.

Java y Kotlin son:

```text
material sobre el que
se evalúa el entorno.
```

### ¿Se evalúa Git?

# NO.

Se identifica como característica, pero RA4 queda fuera.

### ¿Se evalúa debugging?

# NO.

Se identifica como característica común, pero pertenece a RA3.

### ¿Se evalúa testing?

# NO.

### ¿Algún instrumento mezcla RA?

# NO.

```text
I-RA2-02
→ exclusivamente RA2.
```

---

# 125. Checklist final

```text
☑ 7 periodos.

☑ RA2 único.

☑ RA2.e oficial.

☑ RA2.f oficial.

☑ RA2.g oficial.

☑ RA2.c solo reforzado.

☑ Temurin 25.

☑ IntelliJ 2026.2.

☑ Eclipse 2026-09.

☑ VS Code + Extension Pack.

☑ Kotlin/JVM.

☑ Build.

☑ Packaging.

☑ Artifact.

☑ Ejecutable JAR.

☑ Java + Kotlin mismo entorno.

☑ Mismo Java varios entornos.

☑ Fuente canónico.

☑ SHA-256.

☑ No se exige hash JAR idéntico.

☑ IntelliJ Build Artifacts.

☑ Eclipse Runnable JAR.

☑ VS Code Java: Export Jar.

☑ Comparación objetiva.

☑ Características comunes.

☑ Características específicas.

☑ Selección según escenario.

☑ 7 capturas previstas.

☑ Actividades guiadas.

☑ Consolidación.

☑ Ampliación.

☑ Resumen.

☑ Glosario.

☑ Autoevaluación.

☑ P04.1.

☑ I-RA2-02.

☑ Tres CE con nota propia 0–10.

☑ Rúbrica armonizada.

☑ Evidencias.

☑ Material del profesor.

☑ Recuperación modular.

☑ Trazabilidad completa.

☑ Sin ponderaciones antiguas.

☑ Aislamiento superado.

☑ RA2 cerrado.
```

# UD04 — VERSIÓN MAESTRA DEFINITIVA