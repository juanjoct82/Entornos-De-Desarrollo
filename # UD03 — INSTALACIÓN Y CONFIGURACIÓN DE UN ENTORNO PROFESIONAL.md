# UD03 — INSTALACIÓN Y CONFIGURACIÓN DE UN ENTORNO PROFESIONAL

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 8 periodos lectivos  
**Resultado de Aprendizaje:** RA2  
**Práctica evaluable:** P03.1  
**Instrumento:** I-RA2-01  

**JDK estándar:** Eclipse Temurin JDK 25 LTS  
**IDE principal:** IntelliJ IDEA 2026.2  
**IDE libre de contraste:** Eclipse IDE 2026-09 for Java Developers  

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

Hasta ahora hemos estudiado:

```text
UD01
→ cómo pasa el código a ejecución

UD02
→ cómo se organiza el proceso de desarrollo
```

Ahora vamos a preparar el lugar en el que desarrollaremos software durante el curso:

# NUESTRO ENTORNO DE DESARROLLO.

No basta con instalar un programa.

Una estación profesional debe permitir:

```text
editar

compilar

ejecutar

organizar proyectos

incorporar extensiones

automatizar tareas

actualizar componentes

reproducir una configuración
```

---

# 2. Resultado de Aprendizaje

## RA2

**Evalúa entornos integrados de desarrollo analizando sus características para editar código fuente y generar ejecutables.**

---

# 3. Criterios de evaluación de UD03

En esta unidad se trabajan y evalúan exclusivamente:

## RA2.a

**Se han instalado entornos de desarrollo, propietarios y libres.**

## RA2.b

**Se han añadido y eliminado módulos en el entorno de desarrollo.**

## RA2.c

**Se ha personalizado y automatizado el entorno de desarrollo.**

## RA2.d

**Se ha configurado el sistema de actualización del entorno de desarrollo.**

Estas son las formulaciones oficiales vigentes del módulo 0487.

---

# 4. CE reservados para UD04

No se evaluarán todavía:

```text
RA2.e
→ generar ejecutables de distintos lenguajes
   en un mismo entorno

RA2.f
→ generar ejecutables del mismo código
   con varios entornos

RA2.g
→ características comunes
   y específicas de los IDE
```

Pertenecen evaluativamente a:

# UD04.

---

# 5. ¿Qué aprenderemos?

Al terminar la unidad deberás ser capaz de:

- distinguir JDK, runtime e IDE;
- comprobar qué JDK utiliza un equipo;
- instalar y verificar Temurin JDK 25;
- instalar IntelliJ IDEA;
- instalar Eclipse IDE;
- distinguir software gratuito de software libre;
- reconocer diferencias de licencia relevantes;
- seleccionar un JDK para un proyecto;
- comprender configuración global y configuración de proyecto;
- instalar, habilitar, deshabilitar y eliminar plugins;
- personalizar el editor;
- configurar atajos o keymaps;
- crear una automatización sencilla mediante Live Templates;
- conocer mecanismos de copia/sincronización de configuración;
- configurar la política de actualizaciones;
- comprobar actualizaciones del IDE y plugins;
- documentar una instalación reproducible.

---

# 6. Utilidad profesional

Un desarrollador nuevo que se incorpora a una empresa puede recibir instrucciones como:

```text
Instala Java 25.

Configura el proyecto para usar ese JDK.

Instala el IDE.

Añade estos plugins.

Utiliza estas convenciones de editor.

Configura este template.

No uses builds EAP.

Mantén los plugins actualizados.
```

Si cada desarrollador configura el equipo de forma diferente pueden aparecer problemas como:

```text
"en mi ordenador funciona"

versiones incompatibles

plugins ausentes

JDK equivocado

configuración imposible de reproducir
```

Por ello una estación de desarrollo debe ser:

# FUNCIONAL + CONTROLADA + REPRODUCIBLE.

---

# 7. IDE

IDE significa:

```text
Integrated Development Environment
```

o:

```text
Entorno Integrado de Desarrollo.
```

Integra en una misma aplicación herramientas como:

```text
editor

navegación

construcción

ejecución

depuración

plugins

control de versiones

inspecciones

terminal
```

dependiendo del producto.

---

# 8. IDE ≠ JDK

Este error debe evitarse desde el principio.

## JDK

Proporciona herramientas de Java como:

```text
javac

java

javap

javadoc
```

## IDE

Proporciona la interfaz y herramientas integradas para trabajar cómodamente con el proyecto.

Conceptualmente:

```text
INTELLIJ / ECLIPSE
        │
        ▼
      JDK 25
        │
        ▼
compilación / ejecución
```

---

# 9. CONOCIMIENTO AUXILIAR NO EVALUADO

La diferencia entre:

```text
.java

.class

bytecode

JVM
```

pertenece a RA1 y ya fue evaluada en UD01.

Aquí la utilizamos únicamente para poder verificar que el entorno está correctamente configurado.

No se recalifica RA1.

---

# 10. Nuestro estándar Java

Durante el curso utilizaremos:

# Eclipse Temurin JDK 25 LTS

Adoptium clasifica Java 25 como versión LTS y mantiene actualmente una disponibilidad prevista al menos hasta septiembre de 2031.

---

# 11. ¿Por qué fijar una versión?

Imaginemos:

```text
Alumno A → Java 21

Alumno B → Java 25

Alumno C → Java 27

Profesor → Java 25
```

Puede ocurrir que:

```text
un proyecto compile en un equipo

pero no en otro.
```

Al fijar:

```text
Temurin 25
```

reducimos variables innecesarias.

---

# 12. Verificar Java

Antes de instalar nada:

```bash
java --version
```

y:

```bash
javac --version
```

Debemos distinguir:

```text
"Java existe"
```

de:

```text
"tengo instalado el JDK requerido".
```

---

# 13. CAPTURA UD03-01 — Estado inicial

Debe mostrar:

```text
java --version

javac --version
```

La captura debe permitir identificar:

```text
versión

distribución

disponibilidad del compilador.
```

---

# 14. Instalar Temurin 25

Proceso general:

```text
1. seleccionar JDK 25 LTS

2. elegir sistema operativo

3. elegir arquitectura

4. descargar JDK

5. instalar

6. comprobar java

7. comprobar javac
```

No debemos descargar:

```text
Java 27
```

simplemente porque sea una versión de características más reciente.

El estándar didáctico del curso es:

```text
25 LTS.
```

---

# 15. Arquitectura del equipo

Es importante distinguir, por ejemplo:

```text
x86_64

AArch64 / ARM64
```

Un instalador debe corresponder a la arquitectura utilizada.

---

# 16. PATH

El sistema utiliza la variable:

```text
PATH
```

para localizar ejecutables.

Por ejemplo, cuando escribimos:

```bash
javac
```

el sistema debe poder localizar ese comando.

---

# 17. JAVA_HOME

En muchas herramientas se utiliza:

```text
JAVA_HOME
```

para señalar la instalación de Java.

Conceptualmente:

```text
JAVA_HOME
↓
carpeta raíz del JDK
```

Por ejemplo:

```text
...\jdk-25...
```

La ruta exacta depende del sistema operativo y del método de instalación.

---

# 18. Error frecuente

Tener:

```text
JAVA_HOME → JDK 25
```

pero:

```text
PATH → otro java
```

puede provocar que:

```bash
java --version
```

muestre una versión diferente.

Siempre verificaremos el comportamiento real.

---

# 19. Actividad A03.1 — Auditoría Java

Registra:

```text
java --version

javac --version

JAVA_HOME

arquitectura del sistema
```

y responde:

> ¿Existe coherencia entre la versión configurada y la utilizada realmente?

---

# 20. IntelliJ IDEA 2026.2

Será el IDE principal del curso.

Desde IntelliJ IDEA 2025.3 JetBrains distribuye un único IntelliJ IDEA: las funciones esenciales de Java y Kotlin pueden utilizarse gratuitamente y las capacidades ampliadas se desbloquean mediante Ultimate.

Por tanto, ya no hablaremos de:

```text
Community 2026.2

vs.

Ultimate 2026.2
```

como dos instaladores separados.

---

# 21. Gratuito ≠ libre

Debemos distinguir:

## Gratuito

Podemos utilizarlo sin pagar bajo determinadas condiciones.

## Software libre / open source

Su licencia otorga libertades relacionadas con:

```text
uso

estudio

modificación

redistribución
```

según la licencia concreta.

Un producto puede ser:

```text
gratuito
```

sin que toda su distribución sea:

```text
software libre.
```

---

# 22. IntelliJ IDEA y la licencia

La distribución unificada de IntelliJ combina:

```text
núcleo abierto

funcionalidad gratuita

componentes/funciones propietarias
```

y acceso ampliado mediante Ultimate.

JetBrains explica expresamente que algunas funciones gratuitas del producto pueden seguir siendo propietarias.

Por tanto, en esta UD utilizaremos IntelliJ como ejemplo de:

```text
entorno profesional
con distribución/licenciamiento mixto
y capacidades propietarias.
```

---

# 23. Eclipse IDE 2026-09

Nuestro segundo entorno será:

# Eclipse IDE for Java Developers 2026-09

La versión 2026-09 figura actualmente como release de Eclipse IDE y el paquete Java incorpora, entre otras herramientas:

```text
Java Development Tools

Git integration

Maven integration

Gradle integration
```


---

# 24. Eclipse como software libre

Eclipse utiliza:

```text
Eclipse Public License 2.0
```

en sus componentes distribuidos bajo esa licencia.

Esto proporciona un ejemplo claro de entorno:

# LIBRE / OPEN SOURCE.


---

# 25. RA2.a: qué debemos demostrar

El criterio no se supera escribiendo:

```text
"He descargado dos IDE".
```

Debemos acreditar:

```text
instalación

arranque

selección/configuración de Java

creación o apertura de un proyecto

ejecución funcional.
```

---

# 26. Instalación de IntelliJ IDEA

Pasos conceptuales:

```text
descargar
↓
instalar
↓
arrancar
↓
configuración inicial
↓
seleccionar JDK
↓
crear proyecto
↓
ejecutar
```

IntelliJ 2026.2 está disponible para Windows, macOS y Linux.

---

# 27. CAPTURA UD03-02 — IntelliJ instalado

Mostrar:

```text
Help
→ About
```

o pantalla equivalente.

Debe distinguirse:

```text
versión 2026.2.x

sistema operativo

runtime del propio IDE
```

sin confundirlo con:

```text
JDK utilizado por nuestro proyecto.
```

---

# 28. Runtime del IDE ≠ Project SDK

IntelliJ puede ejecutarse internamente con un runtime y, al mismo tiempo, nuestro proyecto utilizar:

```text
Temurin 25
```

como JDK.

Son dos conceptos diferentes.

---

# 29. Project SDK

Al crear un proyecto Java debemos seleccionar:

```text
JDK / SDK
```

para el proyecto.

Nuestro estándar:

```text
Eclipse Temurin 25
```

---

# 30. CAPTURA UD03-03 — Project SDK

La captura debe mostrar:

```text
Project SDK / JDK

→ Temurin 25
```

y permitir comprobar que no se está utilizando accidentalmente otra versión.

---

# 31. Proyecto de verificación

Crearemos:

```java
public class EntornoOK {

    public static void main(String[] args) {

        System.out.println(
                System.getProperty("java.version")
        );

        System.out.println(
                System.getProperty("java.vendor")
        );
    }
}
```

El resultado debe permitir confirmar:

```text
Java 25

Eclipse Adoptium / Temurin
```

según la cadena exacta devuelta por la instalación.

---

# 32. Instalación de Eclipse

El paquete recomendado:

```text
Eclipse IDE for Java Developers
```

incluye las herramientas esenciales para Java.

Proceso:

```text
instalar
↓
seleccionar workspace
↓
configurar JDK
↓
crear proyecto Java
↓
ejecutar
```

---

# 33. Workspace

Eclipse utiliza el concepto:

```text
WORKSPACE
```

como espacio de trabajo.

Puede contener:

```text
proyectos

preferencias asociadas

metadatos del entorno
```

No debe confundirse con:

```text
una carpeta de código cualquiera.
```

---

# 34. CAPTURA UD03-04 — Eclipse

Debe mostrar:

```text
Eclipse IDE 2026-09

workspace

proyecto de prueba.
```

---

# 35. Configuración global y configuración de proyecto

En un IDE encontramos diferentes niveles.

IntelliJ distingue, entre otros:

```text
configuración global

configuración de proyecto

configuración de módulo
```


---

# 36. Configuración global

Puede incluir:

```text
tema

plugins

keymap

apariencia

comportamiento general.
```

Afecta normalmente al IDE en conjunto.

---

# 37. Configuración de proyecto

Puede incluir aspectos como:

```text
JDK

estilo

VCS

inspecciones

estructura
```

según el entorno.

---

# 38. ¿Por qué importa?

Si cambiamos:

```text
tema oscuro
```

no queremos necesariamente modificar un proyecto.

Si cambiamos:

```text
JDK del proyecto
```

esa decisión pertenece al contexto técnico del proyecto.

---

# 39. Plugins / módulos

Un IDE puede ampliar funcionalidad mediante:

```text
plugins

extensiones

módulos
```

La terminología depende del producto.

RA2.b exige demostrar:

```text
añadir

y eliminar
```

módulos del entorno.

---

# 40. Plugins en IntelliJ

En IntelliJ:

```text
Settings
→ Plugins
```

podemos:

```text
buscar

instalar

habilitar

deshabilitar

actualizar

eliminar
```

plugins.

JetBrains documenta estas operaciones en IntelliJ IDEA 2026.2.

---

# 41. CAPTURA UD03-05 — Plugins

Debe mostrar:

```text
Marketplace

Installed
```

y distinguir:

```text
plugin incluido/bundled

plugin instalado por el usuario.
```

---

# 42. Plugin para el laboratorio

El profesor seleccionará un plugin:

```text
gratuito

seguro

no imprescindible
```

para que pueda:

```text
instalarse

probarse

eliminarse
```

sin alterar el desarrollo normal del curso.

---

# 43. Qué NO debemos hacer

No instalaremos plugins:

```text
desconocidos

sin fuente identificada

innecesarios

incompatibles
```

solo para demostrar RA2.b.

---

# 44. Actividad A03.2 — Ciclo de un plugin

Documenta:

```text
estado inicial
↓
instalación
↓
reinicio si procede
↓
verificación
↓
deshabilitación
↓
eliminación
```

Explica:

> ¿Qué funcionalidad añadía?

---

# 45. Plugins en Eclipse

Eclipse también admite extensiones mediante:

```text
Marketplace

Install New Software

update sites
```

según el componente.

En P03.1 bastará con demostrar RA2.b en al menos uno de los entornos de forma completa, aunque el alumno deberá reconocer que ambos soportan extensiones.

---

# 46. Personalización del IDE

Personalizar significa adaptar el entorno a necesidades de trabajo.

Ejemplos:

```text
tema

fuente

code style

keymap

editor

inspecciones

plantillas.
```

RA2.c exige además:

# AUTOMATIZAR.

---

# 47. Personalización útil ≠ decoración

Cambiar:

```text
fondo azul
```

puede ser una personalización.

Pero profesionalmente nos interesan especialmente cambios que mejoren:

```text
legibilidad

consistencia

productividad

reproducibilidad.
```

---

# 48. Ejemplo: formato

Podemos configurar convenciones como:

```text
indentación

espacios

longitud de línea

imports
```

No se calificará en esta unidad la calidad del estilo Java.

Se evalúa la capacidad de:

```text
personalizar el entorno.
```

---

# 49. Keymap

Un keymap define:

```text
acciones
↔
atajos de teclado.
```

Puede adaptarse por:

```text
preferencia

compatibilidad con otro IDE

accesibilidad.
```

---

# 50. CAPTURA UD03-06 — Configuración

Debe mostrar una personalización significativa:

```text
editor

keymap

code style

o equivalente
```

con una breve explicación de:

```text
qué se cambió

por qué.
```

---

# 51. Automatización mediante Live Templates

IntelliJ permite crear plantillas que expanden abreviaturas.

Crearemos:

```text
mirlog
```

que genere:

```java
System.out.println("MIRALMONTE: ");
```

o una plantilla equivalente indicada por el profesor.

---

# 52. Ejemplo más útil

Plantilla:

```text
mirlog
```

expande a:

```java
System.out.println("$TEXT$");
```

permitiendo escribir rápidamente:

```text
mirlog + Tab
```

y completar el mensaje.

---

# 53. RA2.c

Aquí tenemos:

```text
PERSONALIZACIÓN
+
AUTOMATIZACIÓN
```

porque no solo modificamos la apariencia:

```text
automatizamos una escritura repetitiva.
```

---

# 54. CAPTURA UD03-07 — Live Template

Debe mostrar:

```text
abreviatura

descripción

template text

contexto Java.
```

---

# 55. Actividad A03.3 — Automatiza una tarea

Crea:

```text
mirlog
```

o una plantilla equivalente.

Demuestra:

```text
antes
→ escribir manualmente

después
→ abreviatura + expansión.
```

Explica el ahorro o consistencia que aporta.

---

# 56. Configuración reproducible

Un problema frecuente:

```text
He tardado meses en configurar el IDE.

Cambio de ordenador.

Empiezo de cero.
```

Un entorno profesional debe permitir conservar o reconstruir la configuración.

---

# 57. Backup / Sync / Export

Según el entorno y cuenta utilizada podemos disponer de mecanismos como:

```text
Backup and Sync

exportación/importación de settings

archivos de configuración

configuración de proyecto.
```

El método concreto puede variar con la versión.

---

# 58. Qué debemos conservar

Ejemplos:

```text
preferencias útiles

keymap

plugins necesarios

templates

configuración de proyecto.
```

No debemos sincronizar o publicar indiscriminadamente:

```text
contraseñas

tokens

secretos

credenciales.
```

---

# 59. Actividad A03.4 — Reproducibilidad

Diseña una pequeña ficha:

```text
JDK

IDE

plugins

personalizaciones

automatizaciones

política de actualización
```

de manera que otro alumno pueda reproducir tu estación.

---

# 60. Actualizaciones

RA2.d exige:

```text
configurar el sistema
de actualización
del entorno.
```

No basta con pulsar:

```text
Update
```

una vez.

---

# 61. Por qué actualizar

Las actualizaciones pueden incluir:

```text
correcciones

seguridad

compatibilidad

nuevas funciones.
```

Pero una actualización también puede:

```text
cambiar comportamiento

romper plugins

introducir incompatibilidades.
```

---

# 62. Canales de actualización

IntelliJ permite configurar la política de actualización y, según la instalación, seleccionar canales como EAP o canales estables disponibles.

Para el aula utilizaremos:

# VERSIONES ESTABLES.

---

# 63. EAP

EAP significa:

```text
Early Access Program
```

y corresponde a versiones previas orientadas a probar novedades.

No será el canal estándar del curso.

---

# 64. Política Miralmonte

Recomendación:

```text
IDE
→ canal estable

plugins
→ actualizar con revisión

JDK
→ mantener Java 25 LTS
   con actualizaciones de mantenimiento

cambios mayores
→ validar antes de aplicarlos
   a todo el aula.
```

---

# 65. Actualizaciones de IntelliJ

Ruta de referencia:

```text
Settings
→ Appearance & Behavior
→ System Settings
→ Updates
```

Desde ahí pueden configurarse:

```text
comprobación de actualizaciones

canal

plugins automáticos

comprobación manual
```

según instalación.

---

# 66. Actualización de plugins

IntelliJ puede:

```text
notificar

actualizar manualmente

actualizar plugins automáticamente
```

según configuración.

---

# 67. CAPTURA UD03-08 — Updates

Debe mostrar:

```text
política seleccionada

canal

opción de plugins
```

y explicar por qué esa política es apropiada para el aula.

---

# 68. Actividad A03.5 — Diseña una política

Compara:

## Equipo personal

Puede tolerar:

```text
actualización más rápida.
```

## Aula con 25 equipos

Puede interesar:

```text
validar primero

y después desplegar
de forma coordinada.
```

Explica por qué.

---

# 69. Eclipse y actualizaciones

Eclipse posee igualmente mecanismos de:

```text
update sites

instalación/actualización de componentes
```

y release trains periódicos.

La versión actual del curso:

```text
2026-09.
```


---

# 70. Error frecuente — actualizar todo sin comprobar

Mala política:

```text
Hay actualización.

La instalo inmediatamente
en todos los equipos
el día del examen.
```

Mejor:

```text
comprobar cambio

validar compatibilidad

planificar actualización.
```

---

# 71. Error frecuente — nunca actualizar

La política opuesta tampoco es recomendable:

```text
Si funciona,
no actualizo durante 5 años.
```

Puede provocar:

```text
problemas de seguridad

incompatibilidades

software obsoleto.
```

---

# 72. Error frecuente — IDE y JDK mezclados

Alumno:

> He instalado IntelliJ, así que ya tengo el JDK 25.

No necesariamente.

Debemos comprobar:

```text
Project SDK
```

y:

```text
java --version

javac --version.
```

---

# 73. Error frecuente — gratis = libre

IntelliJ puede utilizarse con un conjunto gratuito de funcionalidades.

Eso no significa que toda la distribución sea:

```text
software libre.
```

Del mismo modo:

```text
Eclipse
```

sí constituye nuestro ejemplo claro de IDE libre/open source.

---

# 74. Error frecuente — instalar veinte plugins

Más plugins no significa:

```text
mejor IDE.
```

Cada plugin puede añadir:

```text
consumo

complejidad

riesgo

actualizaciones

conflictos.
```

Instalamos lo necesario.

---

# 75. Error frecuente — confundir configuración personal y proyecto

Un tema oscuro puede ser:

```text
preferencia personal.
```

El JDK de compilación es:

```text
decisión técnica del proyecto.
```

Debemos distinguir ambos niveles.

---

# 76. Buenas prácticas

## Versionar la estación

Registrar:

```text
JDK

IDE

plugins relevantes.
```

## Mantener estándar

No actualizar versiones mayores individualmente sin necesidad.

## Minimizar plugins

Instalar únicamente los necesarios.

## Evitar secretos

No incorporar tokens o contraseñas a configuraciones compartidas.

## Documentar

Una instalación profesional debe poder reproducirse.

---

# 77. Caso profesional — Nueva incorporación

Una desarrolladora se incorpora a CartagoSoft.

Recibe:

```text
Java:
Temurin 25

IDE principal:
IntelliJ 2026.2

IDE de contraste:
Eclipse 2026-09

Plugin:
X

Template:
mirlog

Update policy:
stable
```

En 30 minutos debería ser capaz de reconstruir una estación equivalente.

Ese es el objetivo profesional de esta unidad.

---

# 78. Ejercicios de consolidación

1. ¿Qué diferencia existe entre JDK e IDE?
2. ¿Para qué sirve `JAVA_HOME`?
3. ¿Qué función tiene `PATH`?
4. ¿Por qué comprobamos `java` y `javac`?
5. ¿Qué significa LTS?
6. ¿Cuál es el JDK estándar del curso?
7. ¿Qué significa IDE?
8. Diferencia configuración global y de proyecto.
9. ¿Qué es un plugin?
10. ¿Qué significa deshabilitar un plugin?
11. ¿Qué diferencia existe entre deshabilitar y eliminar?
12. ¿Qué es un Live Template?
13. Pon un ejemplo de automatización dentro de un IDE.
14. ¿Por qué una estación debe ser reproducible?
15. ¿Qué problema puede introducir una actualización?
16. ¿Qué es un canal estable?
17. ¿Qué significa EAP?
18. ¿Por qué no usamos EAP como estándar de aula?
19. ¿Gratuito significa software libre?
20. ¿Qué IDE utilizamos como ejemplo libre?
21. ¿Qué IDE utilizamos como principal?
22. ¿Qué es un workspace en Eclipse?
23. ¿Por qué conviene documentar plugins?
24. ¿Por qué no instalamos plugins innecesarios?
25. Diseña una política breve de actualización para un aula.

---

# 79. Actividad de ampliación

Compara:

```text
instalación manual

vs.

configuración automatizada
de una estación
```

e investiga herramientas como:

```text
JetBrains Toolbox

package managers

scripts

dev containers
```

sin instalarlas obligatoriamente.

**No evaluable.**

---

# 80. Resumen

Una estación de desarrollo profesional necesita:

```text
JDK correcto

IDE funcional

plugins controlados

personalización coherente

automatizaciones útiles

actualizaciones configuradas.
```

Nuestro estándar:

```text
Temurin 25 LTS

IntelliJ IDEA 2026.2

Eclipse IDE 2026-09
```

RA2.a exige:

```text
instalar entornos de distinta naturaleza/licencia.
```

RA2.b:

```text
añadir y eliminar módulos.
```

RA2.c:

```text
personalizar y automatizar.
```

RA2.d:

```text
configurar actualizaciones.
```

---

# 81. Glosario

**Automatización:** configuración que permite ejecutar o generar acciones repetitivas con menor intervención manual.

**EAP:** canal de acceso anticipado a versiones en desarrollo.

**Eclipse IDE:** entorno de desarrollo libre/open source utilizado como IDE de contraste.

**IDE:** entorno integrado de desarrollo.

**JDK:** conjunto de herramientas para desarrollar software Java.

**JAVA_HOME:** variable utilizada habitualmente para señalar una instalación Java.

**Keymap:** conjunto de asignaciones entre acciones y atajos.

**Live Template:** plantilla que expande texto/código repetitivo.

**LTS:** versión con soporte a largo plazo.

**PATH:** variable que permite localizar ejecutables desde la línea de comandos.

**Plugin:** módulo que amplía o modifica funcionalidad del entorno.

**Project SDK:** JDK/SDK configurado para un proyecto.

**Software libre:** software distribuido bajo una licencia que concede determinadas libertades de uso, estudio, modificación y distribución.

**Workspace:** espacio de trabajo utilizado por Eclipse.

---

# 82. Autoevaluación

### 1
El JDK estándar es:

A. Java 8  
B. Temurin 25 LTS  
C. JavaScript  
D. Python

### 2
Un IDE:

A. sustituye siempre al JDK  
B. integra herramientas de desarrollo  
C. es un procesador  
D. es una JVM

### 3
RA2.a exige:

A. instalar un único editor  
B. instalar entornos propietarios y libres  
C. diseñar UML  
D. probar software

### 4
Un plugin:

A. amplía funcionalidad  
B. siempre es obligatorio  
C. sustituye el sistema operativo  
D. es un lenguaje

### 5
RA2.c incluye:

A. personalización y automatización  
B. únicamente cambiar el fondo  
C. Git remoto  
D. JUnit

### 6
Un Live Template:

A. automatiza escritura repetitiva  
B. actualiza Windows  
C. crea una CPU  
D. sustituye Java

### 7
EAP representa:

A. un canal de acceso anticipado  
B. el JDK  
C. un lenguaje  
D. UML

### 8
Eclipse es utilizado aquí como:

A. IDE libre  
B. JDK  
C. debugger únicamente  
D. sistema operativo

### 9
“Gratuito”:

A. siempre significa software libre  
B. no implica necesariamente software libre  
C. significa código sin licencia  
D. significa dominio público

### 10
Una buena política de aula:

A. actualiza todo sin validar  
B. mantiene versiones estables y valida cambios relevantes  
C. nunca actualiza  
D. utiliza siempre EAP

---

# 83. PRÁCTICA EVALUABLE P03.1

# CONSTRUYE UNA ESTACIÓN DE DESARROLLO REPRODUCIBLE

**Modalidad:** individual  
**RA:** RA2  
**CE evaluados:** RA2.a, RA2.b, RA2.c, RA2.d  
**Instrumento:** I-RA2-01

---

# 84. Escenario

Te incorporas a:

# CARTAGOSOFT

La empresa necesita que prepares una estación de desarrollo Java que pueda reproducirse en otro equipo.

Requisitos:

```text
Temurin JDK 25 LTS

IntelliJ IDEA 2026.2

Eclipse IDE 2026-09

un plugin de laboratorio

automatización mirlog

política de actualización estable
```

---

# 85. Tarea A — Auditoría inicial

Documenta:

```text
sistema operativo

arquitectura

java --version

javac --version

JAVA_HOME
```

Indica qué cambios son necesarios.

---

# 86. Tarea B — JDK

Instala o verifica:

```text
Eclipse Temurin JDK 25 LTS
```

Aporta evidencia de:

```text
java --version

javac --version.
```

El JDK es infraestructura necesaria.

No genera por sí solo un CE diferente.

---

# 87. Tarea C — IntelliJ

Instala/verifica IntelliJ.

Configura:

```text
Temurin 25
```

como JDK del proyecto.

Crea:

```text
EstacionMiralmonte
```

y ejecuta un programa de comprobación.

---

# 88. Tarea D — Eclipse

Instala:

```text
Eclipse IDE for Java Developers 2026-09
```

Configura Java 25.

Crea un proyecto:

```text
EstacionEclipse
```

y ejecuta un programa.

---

# 89. Evidencia RA2.a

Debes demostrar:

```text
dos entornos funcionales

distinta naturaleza/licenciamiento

JDK correctamente asociado

ejecución verificada.
```

**CE:** RA2.a

---

# 90. Tarea E — Plugin

En IntelliJ:

```text
1. documenta estado inicial

2. instala plugin asignado

3. demuestra funcionalidad

4. deshabilítalo

5. elimínalo

6. demuestra estado final
```

**CE:** RA2.b

---

# 91. Tarea F — Personalización

Realiza como mínimo:

```text
una modificación de editor

una modificación de keymap
o comportamiento equivalente
```

Explica:

```text
qué cambiaste

por qué

qué efecto tiene.
```

**CE:** RA2.c

---

# 92. Tarea G — Automatización

Crea:

```text
mirlog
```

como Live Template.

Demuestra:

```text
abreviatura
↓
expansión
↓
código generado.
```

**CE:** RA2.c

---

# 93. Tarea H — Reproducibilidad

Crea una ficha con:

```text
JDK

IDE

versión

plugins

configuración relevante

template

política de actualización.
```

Otro alumno debería poder reconstruir la estación con ella.

**CE:** RA2.c

---

# 94. Tarea I — Actualizaciones

Configura:

```text
canal estable

comprobación de updates

política de plugins
```

y justifica:

> ¿Por qué esta política es adecuada para un aula?

**CE:** RA2.d

---

# 95. Entregable

```text
P03.1_Apellidos_Nombre.pdf
```

Debe contener:

1. portada;
2. auditoría inicial;
3. Temurin 25;
4. IntelliJ;
5. Eclipse;
6. proyecto funcional en ambos;
7. plugin;
8. personalización;
9. Live Template;
10. ficha reproducible;
11. política de actualización;
12. conclusión.

---

# 96. Evidencias

## RA2.a

```text
E-RA2.a-01
IntelliJ instalado y funcional.

E-RA2.a-02
Eclipse instalado y funcional.

E-RA2.a-03
JDK 25 verificado en ambos.
```

## RA2.b

```text
E-RA2.b-01
Plugin instalado.

E-RA2.b-02
Plugin funcional.

E-RA2.b-03
Plugin deshabilitado/eliminado.
```

## RA2.c

```text
E-RA2.c-01
Personalización significativa.

E-RA2.c-02
Live Template funcional.

E-RA2.c-03
Ficha de reproducibilidad.
```

## RA2.d

```text
E-RA2.d-01
Configuración de updates.

E-RA2.d-02
Política de actualización justificada.
```

---

# 97. Instrumento I-RA2-01

**Instrumento:** I-RA2-01  
**RA:** RA2  
**CE:** RA2.a, RA2.b, RA2.c, RA2.d  
**Tipo:** laboratorio técnico individual  
**Actividad:** P03.1 – Construye una estación de desarrollo reproducible  

Cada CE obtiene:

```text
nota independiente
0,00–10,00
```

No existe una ponderación provisional interna.

---

# 98. Rúbrica definitiva I-RA2-01

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA2.a** | Instala y verifica entornos de desarrollo propietarios/no libres y libres | No consigue disponer de ambos entornos funcionales o no distingue su naturaleza | Instala ambos con ayuda y realiza una verificación básica | Instala, configura con JDK 25 y ejecuta correctamente un proyecto en IntelliJ y Eclipse | Además documenta arquitectura, versión, licencia/naturaleza y reproduce la instalación con precisión | **100 % del CE** |
| **RA2.b** | Añade y elimina módulos/plugins del entorno | No instala correctamente o desconoce el efecto del plugin | Instala o elimina con ayuda | Instala, verifica, deshabilita y elimina correctamente un plugin | Además justifica procedencia, necesidad, compatibilidad y consecuencias de mantenerlo | **100 % del CE** |
| **RA2.c** | Personaliza y automatiza el entorno | Solo realiza cambios superficiales o no consigue automatización | Realiza alguna personalización y automatización simple con ayuda | Personaliza de forma coherente y crea una automatización funcional mediante Live Template u opción equivalente | Además produce una configuración especialmente reproducible y explica qué pertenece al IDE, proyecto y usuario | **100 % del CE** |
| **RA2.d** | Configura el sistema de actualización | No localiza o configura el mecanismo | Identifica las opciones principales | Configura una política estable para IDE/plugins y la justifica | Además distingue mantenimiento, versiones mayores, canales de previsualización y estrategia de despliegue en aula/equipo | **100 % del CE** |

---

# 99. Nota informativa de P03.1

Si se desea mostrar una nota resumen:

```text
(
 RA2.a
+RA2.b
+RA2.c
+RA2.d
) / 4
```

Pero la evaluación real conserva:

```text
RA2.a

RA2.b

RA2.c

RA2.d
```

por separado.

---

# 100. Temporalización

| Sesión | Contenido | Actividad |
|---:|---|---|
| 1 | IDE, JDK y auditoría inicial | A03.1 |
| 2 | Temurin 25 + IntelliJ | instalación/verificación |
| 3 | Eclipse 2026-09 + workspace | instalación/verificación |
| 4 | Plugins/módulos | A03.2 |
| 5 | Personalización | configuración guiada |
| 6 | Automatización y reproducibilidad | A03.3–4 |
| 7 | Actualizaciones y políticas | A03.5 + inicio P03.1 |
| 8 | P03.1 / I-RA2-01 | evaluación |

**Total: 8 periodos.**

---

# 101. Autoevaluación — soluciones

```text
1 → B
2 → B
3 → B
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

# 102. Finalidad docente

La unidad debe conseguir que el alumno pase de:

```text
"Instalo programas"
```

a:

```text
"Construyo una estación
de desarrollo controlada".
```

Debe comprender especialmente:

```text
IDE ≠ JDK

gratis ≠ libre

global ≠ proyecto

plugin ≠ función esencial

actualizar ≠ aceptar todo.
```

---

# 103. Punto delicado: propietario/libre

No conviene presentar IntelliJ 2026.2 simplemente como:

```text
"IDE propietario de pago"
```

porque el producto actual es más complejo.

JetBrains mantiene:

```text
producto unificado

core gratuito

código abierto mantenido

funcionalidades propietarias

suscripción Ultimate.
```


Para RA2.a:

```text
IntelliJ
→ ejemplo profesional de distribución
   con componentes/funciones propietarias

Eclipse
→ ejemplo libre claro
   bajo EPL 2.0.
```

---

# 104. Solución A03.1

Debe comprobarse:

```text
java --version
→ 25.x

javac --version
→ 25.x
```

y coherencia con:

```text
JAVA_HOME.
```

Una instalación donde:

```text
java = 25

javac = 21
```

no debe considerarse correctamente estandarizada.

---

# 105. Solución del programa de verificación

```java
public class EntornoOK {

    public static void main(String[] args) {

        System.out.println(
            "Java: "
            + System.getProperty("java.version")
        );

        System.out.println(
            "Vendor: "
            + System.getProperty("java.vendor")
        );
    }
}
```

La cadena exacta del vendor puede variar entre builds.

Lo importante:

```text
versión 25

distribución coherente.
```

---

# 106. Plugin

Conviene seleccionar antes de la sesión un plugin que:

```text
sea compatible con 2026.2

no requiera cuenta

no altere el proyecto

pueda desinstalarse fácilmente.
```

No debe evaluarse:

```text
qué plugin concreto eligió
```

sino:

```text
gestión correcta del módulo.
```

---

# 107. Personalización RA2.c

Una evidencia insuficiente sería únicamente:

```text
cambiar tema claro → oscuro.
```

Puede formar parte de la personalización, pero debe acompañarse de una modificación profesionalmente significativa o de la automatización requerida.

La evidencia fuerte:

```text
configuración
+
Live Template
+
documentación reproducible.
```

---

# 108. Live Template orientativo

Abreviatura:

```text
mirlog
```

Contenido:

```java
System.out.println("$TEXT$");
```

El profesor puede cambiar la plantilla si futuras versiones modifican el mecanismo.

El CE no depende del nombre:

```text
mirlog.
```

Depende de:

```text
automatizar una acción
del entorno.
```

---

# 109. Actualizaciones RA2.d

Nivel básico:

```text
localiza updates.
```

Nivel adecuado:

```text
configura canal/política

+
la justifica.
```

Nivel avanzado:

```text
distingue aula
de equipo personal

+
planifica validación.
```

---

# 110. Capturas definitivas previstas

```text
CAPTURA UD03-01
java/javac

CAPTURA UD03-02
IntelliJ About

CAPTURA UD03-03
Project SDK Temurin 25

CAPTURA UD03-04
Eclipse 2026-09

CAPTURA UD03-05
Plugins

CAPTURA UD03-06
Personalización

CAPTURA UD03-07
Live Template

CAPTURA UD03-08
Updates
```

No deben añadirse capturas puramente decorativas.

---

# 111. Medidas de apoyo

Puede proporcionarse:

```text
checklist de instalación

plantilla de ficha

capturas parciales

ruta de Settings

ejemplo de Live Template distinto
```

sin entregar las evidencias evaluables finales.

---

# 112. Ampliación

Alumnado avanzado puede:

```text
exportar/importar settings

investigar Toolbox

crear plugin required

automatizar instalación
por línea de comandos
```

sin que ello otorgue automáticamente mayor nota si no mejora el desempeño del CE.

---

# 113. Recuperación

Instrumento:

# IR-RA2-01

Bloques directamente asociados:

```text
RA2.a
RA2.b
RA2.c
RA2.d
```

Ejemplo:

```text
RA2.a = 7
RA2.b = 3
RA2.c = 6
RA2.d = 7
```

Si RA2 queda pendiente y solo es necesario recuperar:

```text
RA2.b
```

el alumno realizará únicamente:

```text
bloque RA2.b
```

del IR-RA2-01.

---

# 114. Trazabilidad

| RA | CE | Contenido | Actividad | Instrumento | Evidencia |
|---|---|---|---|---|---|
| RA2 | a | instalación de entornos | A03.1 + laboratorio | P03.1 / I-RA2-01 | E-RA2.a-01/03 |
| RA2 | b | plugins/módulos | A03.2 | P03.1 / I-RA2-01 | E-RA2.b-01/03 |
| RA2 | c | personalización y automatización | A03.3–4 | P03.1 / I-RA2-01 | E-RA2.c-01/03 |
| RA2 | d | actualización | A03.5 | P03.1 / I-RA2-01 | E-RA2.d-01/02 |

---

# 115. Estado de RA2 tras UD03

```text
RA2.a → EVALUADO

RA2.b → EVALUADO

RA2.c → EVALUADO

RA2.d → EVALUADO

RA2.e → PENDIENTE UD04

RA2.f → PENDIENTE UD04

RA2.g → PENDIENTE UD04
```

RA2 permanece:

# ABIERTO.

---

# 116. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA2

**CE evaluados:**

```text
RA2.a
RA2.b
RA2.c
RA2.d
```

### ¿Se reutiliza RA1?

Sí, como conocimiento auxiliar:

```text
JDK

compilación

java/javac.
```

No se recalifica.

### ¿Se utiliza Git?

Puede venir integrado en los IDE, pero:

```text
NO se evalúa Git

NO se evalúa colaboración

NO se evalúa RA4.
```

### ¿Se generan ejecutables de distintos lenguajes?

# NO COMO EVIDENCIA.

Se reserva a UD04.

### ¿Se comparan formalmente IDE?

# NO.

Solo instalamos y utilizamos ambos.

La comparación evaluable:

```text
RA2.g
```

queda para UD04.

### ¿Algún instrumento evalúa otro RA?

# NO.

```text
I-RA2-01
→ exclusivamente RA2.
```

---

# 117. Checklist de cierre UD03

```text
☑ 8 periodos.

☑ RA2 único.

☑ RA2.a oficial.

☑ RA2.b oficial.

☑ RA2.c oficial.

☑ RA2.d oficial.

☑ RA2.e–g reservados.

☑ Temurin 25 LTS.

☑ IntelliJ 2026.2.

☑ Eclipse 2026-09.

☑ Gratuito ≠ libre.

☑ IntelliJ licensing explicado con precisión.

☑ Eclipse EPL 2.0.

☑ IDE ≠ JDK.

☑ JAVA_HOME.

☑ PATH.

☑ Project SDK.

☑ Workspace.

☑ Configuración global/proyecto.

☑ Plugins.

☑ Install/disable/remove.

☑ Personalización.

☑ Live Template.

☑ Reproducibilidad.

☑ Backup/sync contextualizado.

☑ Actualizaciones.

☑ Canal estable.

☑ EAP explicado.

☑ Política Miralmonte.

☑ 8 capturas previstas.

☑ Actividades guiadas.

☑ Consolidación.

☑ Ampliación.

☑ Resumen.

☑ Glosario.

☑ Autoevaluación.

☑ P03.1.

☑ I-RA2-01.

☑ 4 CE con nota propia 0–10.

☑ Rúbrica armonizada.

☑ Evidencias.

☑ Soluciones profesor.

☑ Recuperación modular.

☑ Trazabilidad.

☑ Sin ponderación provisional antigua.

☑ Aislamiento superado.
```

# UD03 — VERSIÓN MAESTRA DEFINITIVA