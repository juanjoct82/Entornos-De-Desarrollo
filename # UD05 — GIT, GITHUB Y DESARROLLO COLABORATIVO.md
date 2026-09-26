# UD05 — GIT, GITHUB Y DESARROLLO COLABORATIVO

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 10 periodos lectivos  
**Resultado de Aprendizaje:** RA4  
**Práctica evaluable:** P05.1  
**Instrumento:** I-RA4-01  

**IDE de referencia:** IntelliJ IDEA 2026.2  
**Sistema de control de versiones:** Git  
**Repositorio remoto:** GitHub  
**JDK:** Eclipse Temurin JDK 25 LTS  

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

Hasta ahora hemos trabajado principalmente con proyectos almacenados en nuestro propio equipo.

Imaginemos que tenemos:

```text
CartagoParking/
├── src/
│   └── ...
└── ...
```

y realizamos durante varias semanas:

```text
cambio 1
cambio 2
cambio 3
cambio 4
...
```

Entonces aparece un problema:

> La aplicación funcionaba ayer. Hoy he realizado varios cambios y ya no funciona.

O algo peor:

> He sobrescrito el archivo bueno y no recuerdo cómo estaba.

Y en un equipo:

> Dos personas han modificado el mismo proyecto. ¿Cómo combinamos sus cambios?

Estas situaciones son precisamente las que ayudan a resolver los:

# SISTEMAS DE CONTROL DE VERSIONES.

---

# 2. Resultado de Aprendizaje

## RA4

**Optimiza código empleando las herramientas disponibles en el entorno de desarrollo.**

---

# 3. Criterios de evaluación de UD05

En esta unidad se evalúan exclusivamente:

## RA4.f

**Se ha realizado el control de versiones integrado en el entorno de desarrollo.**

## RA4.h

**Se han utilizado repositorios remotos para el desarrollo de código colaborativo.**

Estas son las formulaciones oficiales vigentes del módulo 0487.

---

# 4. CE de RA4 que NO se evalúan todavía

Quedan reservados para UD11:

```text
RA4.a
→ patrones de refactorización

RA4.b
→ pruebas asociadas a refactorización

RA4.c
→ analizador de código

RA4.d
→ configuración del analizador

RA4.e
→ refactorización mediante herramientas del IDE

RA4.g
→ documentación de clases

RA4.i
→ integración continua
```

Por tanto:

# GITHUB ACTIONS NO FORMA PARTE DE LA EVALUACIÓN DE UD05.

---

# 5. ¿Qué aprenderemos?

Al terminar la unidad deberás poder:

- explicar por qué necesitamos control de versiones;
- distinguir Git y GitHub;
- comprender repositorio, commit, historial y working tree;
- reconocer el área de preparación o *staging*;
- identificar cambios mediante *diff*;
- realizar commits coherentes;
- redactar mensajes de commit útiles;
- utilizar Git integrado en IntelliJ IDEA;
- consultar el historial;
- recuperar razonadamente una versión mediante nuevas operaciones de Git;
- utilizar `.gitignore`;
- comprender ramas;
- crear y cambiar de rama;
- integrar ramas;
- resolver conflictos;
- diferenciar repositorio local y remoto;
- comprender `origin`;
- publicar un repositorio en GitHub;
- clonar un repositorio;
- utilizar `push`, `fetch` y `pull`;
- colaborar mediante ramas;
- crear una Pull Request;
- revisar cambios;
- responder a una revisión;
- fusionar cambios;
- sincronizar posteriormente el repositorio local.

---

# 6. Utilidad profesional

En desarrollo profesional es habitual que:

```text
varios desarrolladores
        ↓
modifiquen
        ↓
el mismo proyecto
```

sin trabajar directamente todos sobre:

```text
una única carpeta compartida.
```

Necesitamos conocer:

```text
quién cambió qué

cuándo

por qué

qué versión funcionaba

qué cambios pertenecen a una funcionalidad

cómo integrar trabajo de varias personas.
```

---

# 7. ¿Qué es un sistema de control de versiones?

Un sistema de control de versiones registra la evolución de un conjunto de archivos.

Nos permite conservar algo parecido a:

```text
VERSIÓN A
   ↓
VERSIÓN B
   ↓
VERSIÓN C
   ↓
VERSIÓN D
```

pero con mucha más información que guardar:

```text
proyecto-final.zip

proyecto-final2.zip

proyecto-final-bueno.zip

proyecto-final-ahora-si.zip
```

---

# 8. Git

Git es un sistema de control de versiones distribuido.

Un repositorio Git local contiene información suficiente para consultar y trabajar con su historial.

Conceptualmente:

```text
PROYECTO
   │
   ▼
REPOSITORIO GIT LOCAL
   │
   ├── historial
   ├── ramas
   ├── commits
   └── referencias
```

---

# 9. GitHub

GitHub es una plataforma que permite alojar repositorios Git y añadir funciones de colaboración.

Entre ellas:

```text
repositorios remotos

Pull Requests

revisión de código

permisos

issues

colaboración web
```

GitHub define un repositorio remoto como un repositorio almacenado en GitHub y utiliza las Pull Requests para proponer cambios de una rama hacia otra.

---

# 10. Git ≠ GitHub

Debemos diferenciar:

```text
GIT
→ sistema de control de versiones
```

de:

```text
GITHUB
→ plataforma que aloja
   repositorios Git
   y añade colaboración
```

Podemos utilizar Git:

```text
sin GitHub.
```

Y podemos alojar Git en otras plataformas.

---

# 11. Repositorio

Un repositorio es el proyecto sometido a control de versiones junto con la información de su historial.

Al iniciar Git en un proyecto aparece internamente:

```text
.git/
```

Esta carpeta contiene datos fundamentales del repositorio.

---

# 12. No manipules `.git` manualmente

En el trabajo normal:

```text
NO
```

debemos entrar en:

```text
.git/
```

para modificar archivos manualmente.

Utilizaremos:

```text
Git

o

las herramientas integradas del IDE.
```

---

# 13. Working tree

El **working tree** o directorio de trabajo contiene los archivos que estamos editando actualmente.

Ejemplo:

```text
CartagoParking/
├── src/
│   └── TarifaParking.java
├── README.md
└── .gitignore
```

Cuando editamos:

```text
TarifaParking.java
```

hemos cambiado nuestro directorio de trabajo.

Eso no significa todavía que exista:

```text
un nuevo commit.
```

---

# 14. Commit

Un commit registra un estado coherente del proyecto dentro del historial.

Podemos pensar conceptualmente:

```text
C0
↓
C1
↓
C2
↓
C3
```

Cada commit:

```text
identifica cambios

posee autor

fecha

mensaje

referencia al historial anterior.
```

---

# 15. Un commit no es simplemente “guardar”

Pulsar:

```text
Ctrl + S
```

guarda un archivo.

Crear:

```text
COMMIT
```

registra una versión lógica dentro del historial Git.

Son acciones diferentes.

---

# 16. Estado del archivo

Un archivo puede encontrarse en situaciones conceptuales como:

```text
sin seguimiento

sin modificar

modificado

preparado para commit

confirmado
```

Estas categorías nos ayudan a comprender qué cambios formarán parte del siguiente commit.

---

# 17. Staging area

Git dispone de un área intermedia conocida habitualmente como:

```text
staging area

index
```

que permite decidir:

> ¿Qué cambios quiero incluir exactamente en el próximo commit?

Modelo:

```text
WORKING TREE
     │
     ▼
STAGING AREA
     │
     ▼
COMMIT
     │
     ▼
REPOSITORY
```

---

# 18. IntelliJ y staging

IntelliJ IDEA 2026.2 permite trabajar con integración Git y ofrece opcionalmente un modelo explícito de **staging area**.

En:

```text
Settings
→ Version Control
→ Git
```

puede activarse:

```text
Enable staging area
```

para visualizar qué cambios están preparados para el commit.

En esta unidad utilizaremos este modo para hacer más visible el flujo de Git.

---

# 19. CAPTURA UD05-01 — Git configurado

Debe mostrar:

```text
Settings
→ Version Control
→ Git
```

y permitir comprobar:

```text
ruta de Git

Test correcto

staging area activada.
```

---

# 20. Git integrado en IntelliJ

Esto es especialmente importante porque:

# RA4.f NO PIDE SIMPLEMENTE SABER GIT.

Pide:

> control de versiones integrado en el entorno de desarrollo.

Por tanto, la evidencia principal se obtendrá utilizando:

```text
IntelliJ IDEA
→ integración Git.
```

La documentación actual de IntelliJ incluye desde el IDE creación de repositorios, commits, push, ramas, merges, resolución de conflictos e historial.

---

# 21. CONOCIMIENTO AUXILIAR NO EVALUADO

Podremos mostrar algunos comandos Git para comprender conceptos.

Ejemplo:

```bash
git status
```

Pero:

```text
dominar Git exclusivamente
desde terminal
```

NO constituye por sí solo evidencia suficiente de:

```text
RA4.f.
```

La evaluación exigirá utilización integrada en IntelliJ.

---

# 22. Crear un repositorio

Podemos crear un proyecto con:

```text
Create Git repository
```

o activar posteriormente:

```text
VCS
→ Enable Version Control Integration
→ Git
```

IntelliJ asocia entonces el proyecto con Git.

---

# 23. CAPTURA UD05-02 — Git habilitado

Debe mostrar:

```text
Git / Version Control
```

activo en el proyecto.

---

# 24. Primer estado

Creamos:

```java
public class CartagoParking {

    public static void main(String[] args) {

        System.out.println(
            "CartagoParking iniciado"
        );
    }
}
```

Antes del primer commit podemos comprobar qué archivos están:

```text
nuevos

modificados

ignorados.
```

---

# 25. `.gitignore`

No todos los archivos deben guardarse en el repositorio.

Por ejemplo, habitualmente evitamos versionar:

```text
artefactos generados

directorios temporales

determinada configuración personal

credenciales
```

Un archivo:

```text
.gitignore
```

permite definir patrones de archivos que Git debe ignorar.

---

# 26. Ejemplo `.gitignore`

En un proyecto Java/IntelliJ puede contener, según el proyecto:

```gitignore
out/
target/
*.class
```

La configuración concreta dependerá del sistema de construcción y de qué configuración de proyecto decida conservar el equipo.

---

# 27. Secretos

Nunca debemos utilizar Git para publicar accidentalmente:

```text
contraseñas

tokens

claves API

credenciales
```

Una vez publicados en un repositorio remoto:

```text
borrarlos del archivo
```

no implica necesariamente que hayan desaparecido del historial.

---

# 28. Diff

Antes de crear un commit debemos revisar:

```text
qué ha cambiado.
```

Un **diff** muestra diferencias entre versiones.

Ejemplo conceptual:

```diff
- private static final double TARIFA = 2.0;
+ private static final double TARIFA = 2.5;
```

---

# 29. CAPTURA UD05-03 — Diff

Debe mostrar el visor de diferencias de IntelliJ con:

```text
líneas eliminadas

líneas añadidas.
```

---

# 30. ¿Por qué revisar el diff?

Evita confirmar accidentalmente:

```text
código de pruebas temporales

cambios irrelevantes

datos personales

credenciales

archivos que no queríamos modificar.
```

---

# 31. Commit atómico

Una buena práctica consiste en que cada commit represente:

# UN CAMBIO LÓGICO COHERENTE.

Ejemplo bueno:

```text
Añade cálculo de tarifa por horas
```

Ejemplo problemático:

```text
Añade tarifa
+
cambia nombres
+
modifica README
+
borra otra clase
+
reformatea todo
```

sin relación entre cambios.

---

# 32. Mensajes de commit

Un mensaje debe explicar:

```text
qué cambio lógico registra.
```

Ejemplos útiles:

```text
Añade cálculo de tarifa básica

Valida duración de la estancia

Corrige límite de tarifa diaria

Documenta ejecución del proyecto
```

Evita:

```text
cambios

cosas

prueba

final

asdf
```

---

# 33. Primer commit

Seleccionamos:

```text
archivos iniciales
```

y realizamos desde IntelliJ:

```text
Commit
```

con un mensaje como:

```text
Crea estructura inicial de CartagoParking
```

---

# 34. CAPTURA UD05-04 — Commit

Debe permitir observar:

```text
archivos incluidos

diff

mensaje

acción Commit.
```

---

# 35. Historial

Después podemos consultar:

```text
Git
→ Log
```

o la ventana de control de versiones.

Veremos algo parecido a:

```text
C3  Añade descuento
│
C2  Calcula tarifa
│
C1  Crea estructura inicial
```

---

# 36. El historial cuenta la evolución

Un historial útil permite responder:

```text
¿Cuándo apareció este comportamiento?

¿Qué commit añadió esta clase?

¿Quién realizó este cambio?

¿Qué cambió exactamente?
```

---

# 37. CAPTURA UD05-05 — Git Log

Debe mostrar varios commits con:

```text
mensaje

autor

orden

rama.
```

---

# 38. Ramas

Una rama permite desarrollar una línea de trabajo sin modificar inmediatamente otra rama.

Partimos de:

```text
main
```

y creamos:

```text
feature-descuento
```

Modelo:

```text
A──B──C   main
       \
        D──E   feature-descuento
```

---

# 39. Para qué sirven las ramas

Podemos aislar:

```text
nueva funcionalidad

corrección

experimento

trabajo de otro desarrollador
```

sin mezclarlo inmediatamente con:

```text
main.
```

GitHub recomienda precisamente utilizar ramas para aislar trabajo antes de proponer su integración.

---

# 40. Crear rama en IntelliJ

Desde el selector de rama:

```text
Git Branches
```

creamos:

```text
feature-descuento
```

y trabajamos en ella.

---

# 41. CAPTURA UD05-06 — Ramas

Debe mostrar:

```text
main

feature-descuento

rama actual.
```

---

# 42. Trabajo en la rama

Añadimos:

```java
public static double aplicarDescuento(
        double importe,
        boolean abonado) {

    return abonado
            ? importe * 0.90
            : importe;
}
```

Commit:

```text
Añade descuento para abonados
```

---

# 43. Merge

Cuando el trabajo está preparado podemos integrar:

```text
feature-descuento
```

dentro de:

```text
main.
```

Operación:

```text
merge.
```

Conceptualmente:

```text
main       A──B───────F
              \     /
feature        C──D
```

---

# 44. Merge automático

Si los cambios no interfieren, Git puede combinararlos automáticamente.

Eso no significa:

```text
que siempre pueda hacerlo.
```

---

# 45. Conflicto

Supongamos que dos ramas modifican exactamente la misma línea.

Rama:

```text
main
```

contiene:

```java
private static final double TARIFA = 2.50;
```

Otra rama contiene:

```java
private static final double TARIFA = 3.00;
```

Git no sabe cuál queremos conservar.

Tenemos:

# CONFLICTO.

---

# 46. Un conflicto no significa que Git esté roto

Significa:

> Git necesita una decisión humana.

Tenemos que comprender:

```text
versión actual

versión entrante

resultado deseado.
```

---

# 47. IntelliJ Merge Tool

IntelliJ dispone de una herramienta visual para resolver conflictos.

Cuando varias modificaciones afectan a las mismas líneas, el IDE presenta las versiones implicadas y permite construir el resultado final.

---

# 48. CAPTURA UD05-07 — Conflicto

Debe mostrar:

```text
versión propia

versión entrante

resultado.
```

La captura debe corresponder a un conflicto real creado para el ejercicio.

---

# 49. No resuelvas un conflicto pulsando botones al azar

Antes de decidir:

```text
Accept Yours

Accept Theirs
```

o realizar una mezcla manual:

```text
LEE EL CÓDIGO.
```

Pregunta:

> ¿Cuál debe ser el comportamiento final?

---

# 50. Actividad A05.1 — Primer historial

Crea un proyecto y realiza:

```text
Commit 1
→ estructura inicial

Commit 2
→ cálculo básico

Commit 3
→ validación
```

Después abre el Log y reconstruye:

```text
qué añadió cada commit.
```

---

# 51. Actividad A05.2 — Rama

Crea:

```text
feature-mensaje
```

modifica un mensaje, realiza commit e integra la rama en:

```text
main.
```

Comprueba el gráfico del historial.

---

# 52. Actividad A05.3 — Conflicto controlado

Crea:

```text
feature-tarifa
```

Modifica una misma línea:

```text
en main

y

en feature-tarifa
```

con valores distintos.

Realiza el merge y resuelve el conflicto con IntelliJ.

Explica:

```text
por qué apareció

qué resultado elegiste

por qué.
```

---

# 53. Recuperar cambios

Git permite volver a situaciones anteriores mediante distintas operaciones.

Debemos evitar pensar:

```text
"volver atrás"
```

como una sola acción universal.

---

# 54. Revert

Una estrategia especialmente útil cuando un cambio ya forma parte del historial compartido es:

```text
crear un nuevo commit
que deshace los efectos
de otro commit.
```

Esto permite mantener visible:

```text
qué ocurrió.
```

---

# 55. Por qué no enseñamos “borrar historial” como primera solución

En colaboración, reescribir un historial que otras personas ya utilizan puede provocar problemas.

Para primero trabajaremos preferentemente con estrategias que:

```text
conserven
la trazabilidad.
```

---

# 56. Actividad A05.4 — Deshacer sin ocultar

Realiza un pequeño cambio incorrecto y crea un commit.

Después utiliza desde el flujo Git del IDE una operación apropiada para:

```text
revertir el efecto
```

conservando evidencia en el historial.

Compara:

```text
commit problemático

commit de reversión.
```

---

# 57. Del repositorio local al remoto

Hasta ahora tenemos:

```text
REPOSITORIO LOCAL
```

en nuestro ordenador.

Para colaborar necesitamos:

```text
REPOSITORIO REMOTO.
```

---

# 58. Remote

Un **remote** representa una referencia a otro repositorio.

Habitualmente, al clonar o conectar un repositorio principal aparece:

```text
origin
```

como nombre del remoto.

`origin` es:

```text
un nombre convencional
```

no una palabra obligatoria de Git.

---

# 59. Local y remoto

```text
ORDENADOR
┌──────────────────┐
│ repositorio local│
└─────────┬────────┘
          │
     red  │
          ▼
┌──────────────────┐
│     GitHub       │
│ repositorio      │
│ remoto           │
└──────────────────┘
```

---

# 60. Publicar el proyecto

IntelliJ permite compartir un proyecto Git en GitHub dentro de su flujo integrado.

La documentación actual incluye crear repositorio Git, compartir el proyecto en GitHub y realizar `push` desde el propio IDE.

---

# 61. Push

`push` envía commits locales hacia un repositorio remoto.

Conceptualmente:

```text
LOCAL
A──B──C
      │
      │ push
      ▼
REMOTO
A──B──C
```

---

# 62. Push no significa guardar archivos sueltos

Lo que sincronizamos fundamentalmente son:

```text
commits

ramas

referencias
```

del repositorio.

---

# 63. CAPTURA UD05-08 — Push

Debe mostrar:

```text
commits pendientes de push

rama

remote

acción Push.
```

---

# 64. Clone

Si otra persona necesita trabajar con el repositorio puede:

```text
clone.
```

Clonar crea una copia local del repositorio remoto y su historial.

IntelliJ puede abrir directamente proyectos desde un repositorio remoto Git.

---

# 65. Fetch

`fetch` consulta cambios del remoto y actualiza las referencias remotas:

```text
sin integrar necesariamente
esos cambios
en nuestra rama actual.
```

Nos permite saber:

```text
qué existe en remoto.
```

---

# 66. Pull

De forma simplificada para esta unidad:

```text
pull
=
obtener cambios remotos
+
integrarlos en el trabajo local
```

El resultado concreto depende de la estrategia configurada.

---

# 67. Pull no debe hacerse mecánicamente

Antes de sincronizar:

```text
comprueba tu estado local.
```

Si tenemos:

```text
cambios sin confirmar
```

pueden complicar la integración.

---

# 68. Flujo básico de sincronización

```text
trabajo local
↓
commit
↓
pull / sincronización necesaria
↓
resolver si procede
↓
push
```

No debe interpretarse como una receta invariable, sino como un flujo introductorio seguro.

---

# 69. Desarrollo colaborativo

Imaginemos:

```text
ANA
+
JUAN
```

trabajando en:

```text
CartagoParking.
```

No queremos:

```text
los dos editando
continuamente main
sin coordinación.
```

Podemos trabajar mediante:

```text
ramas
+
commits
+
repositorio remoto
+
Pull Requests.
```

---

# 70. Pull Request

Una Pull Request propone integrar cambios de:

```text
una rama
```

en:

```text
otra rama.
```

GitHub la utiliza como espacio para:

```text
describir cambios

revisarlos

discutirlos

aprobarlos

solicitar modificaciones

fusionarlos.
```


---

# 71. Pull Request ≠ push

`push`:

```text
envía commits al remoto.
```

Pull Request:

```text
propone integrar
unos cambios
en otra rama.
```

Son conceptos diferentes.

---

# 72. Flujo profesional simplificado

```text
main
 │
 ├── crear rama
 │
 ▼
feature-validacion
 │
 ├── modificar
 ├── commit
 ├── push
 │
 ▼
PULL REQUEST
 │
 ├── revisión
 ├── comentarios
 ├── cambios adicionales
 │
 ▼
MERGE
 │
 ▼
main
```

---

# 73. CAPTURA UD05-09 — Pull Request

Debe mostrar:

```text
rama origen

rama destino

título

descripción

cambios.
```

---

# 74. Una buena Pull Request

Debe permitir entender:

```text
qué cambia

por qué

cómo comprobarlo.
```

Ejemplo:

**Título**

```text
Añade validación de matrícula
```

**Descripción**

```text
Impide registrar matrículas vacías.
Se añade validación antes de crear
la estancia.
```

---

# 75. Cambios pequeños son más revisables

Una Pull Request con:

```text
25 líneas relacionadas
```

suele ser más fácil de revisar que:

```text
4.000 líneas

15 funcionalidades

refactorizaciones

formato

documentación
```

mezcladas.

---

# 76. Revisión de código

GitHub permite comentar líneas, realizar sugerencias y enviar una revisión.

La revisión puede:

```text
comentar

aprobar

solicitar cambios.
```


---

# 77. Revisión ≠ ataque personal

Comentario útil:

> Este método acepta matrícula vacía. ¿Podemos validar el parámetro antes de guardar?

Comentario no profesional:

> Esto está fatal.

Revisamos:

```text
el cambio
```

no:

```text
a la persona.
```

---

# 78. Responder a una revisión

Si el revisor solicita un cambio:

```text
NO
```

necesitamos cerrar la Pull Request y empezar otra.

Podemos:

```text
modificar la misma rama
↓
commit
↓
push
```

y la Pull Request se actualiza.

---

# 79. CAPTURA UD05-10 — Review

Debe mostrar un comentario o sugerencia concreta sobre líneas cambiadas.

---

# 80. Merge de Pull Request

Una vez revisado el trabajo puede integrarse en:

```text
main.
```

GitHub ofrece varias estrategias de merge, entre ellas:

```text
merge commit

squash and merge

rebase and merge
```


Para esta unidad utilizaremos normalmente:

# MERGE COMMIT

salvo indicación del profesor, porque hace visible el punto de integración en el historial.

---

# 81. Después del merge

El colaborador debe actualizar su repositorio local.

Por ejemplo:

```text
main local
↓
actualización desde origin/main
↓
main actualizado
```

---

# 82. Actividad A05.5 — Colaboración por parejas

Alumno A:

```text
publica repositorio

añade colaborador.
```

Alumno B:

```text
clona

crea rama

modifica

commit

push

Pull Request.
```

Alumno A:

```text
revisa

solicita o comenta

aprueba

merge.
```

Alumno B:

```text
actualiza main local.
```

Después intercambiáis roles en un cambio pequeño.

---

# 83. `.gitignore` y colaboración

Si un alumno publica:

```text
out/

target/

archivos temporales
```

todos los demás pueden recibir archivos innecesarios.

Por eso:

```text
.gitignore
```

forma parte de una higiene básica del repositorio.

---

# 84. Qué sí debe compartirse

En general:

```text
código fuente

archivos necesarios del proyecto

configuración compartida pertinente

documentación
```

---

# 85. Qué no debemos compartir

```text
credenciales

tokens

archivos temporales

resultados generados innecesarios

datos sensibles
```

---

# 86. Conflicto remoto

Dos personas pueden trabajar correctamente y aun así crear un conflicto.

Ejemplo:

```text
Alumno A
→ modifica TARIFA

Alumno B
→ modifica TARIFA
```

Uno integra primero.

El segundo deberá:

```text
actualizar

resolver

comprobar

continuar.
```

---

# 87. Conflicto no significa mala colaboración

Los conflictos son normales cuando:

```text
el trabajo se solapa.
```

Lo profesional consiste en:

```text
reconocerlos

comprenderlos

resolverlos correctamente.
```

---

# 88. Actividad A05.6 — Conflicto colaborativo

Dos alumnos modifican deliberadamente la misma línea en ramas distintas.

Después:

```text
uno integra primero

el otro actualiza

aparece conflicto

se resuelve

se comprueba resultado

se completa integración.
```

Documenta el proceso.

---

# 89. GitHub Actions — fuera de esta unidad

Al abrir una Pull Request puedes observar elementos relacionados con:

```text
Checks

Actions

automatizaciones.
```

En UD05:

# NO LOS CONFIGURAMOS NI LOS EVALUAMOS.

La integración continua pertenece a:

```text
RA4.i
→ UD11.
```

---

# 90. Refactorización — fuera de esta unidad

Puede ocurrir que una rama contenga una refactorización.

Pero la capacidad de:

```text
identificar

aplicar

proteger con pruebas
```

patrones de refactorización pertenece a:

```text
UD11.
```

No se evalúa aquí.

---

# 91. Errores frecuentes

## Error 1 — Commit enorme

```text
"Trabajo de toda la semana"
```

con cientos de cambios sin relación.

### Mejora

Crear commits más pequeños y coherentes.

---

# 92. Error 2 — Mensajes inútiles

```text
final

final2

cosas

cambios.
```

### Mejora

Explicar el propósito del cambio.

---

# 93. Error 3 — Trabajar siempre en main

Puede funcionar en ejercicios individuales muy pequeños, pero limita:

```text
aislamiento

revisión

colaboración.
```

Aprenderemos a utilizar ramas.

---

# 94. Error 4 — Push sin revisar

Antes de publicar:

```text
revisar diff

comprobar estado

verificar commit.
```

---

# 95. Error 5 — Commit de secretos

Nunca:

```text
token GitHub

password

API key
```

aunque después pensemos:

> Ya lo borraré.

---

# 96. Error 6 — Resolver conflicto eligiendo “Yours” siempre

Eso puede eliminar trabajo correcto del compañero.

Primero:

```text
comprender ambas versiones.
```

---

# 97. Error 7 — confundir pull y Pull Request

```text
pull
→ sincronización Git

Pull Request
→ propuesta/revisión de integración
   en GitHub.
```

---

# 98. Error 8 — terminal como única evidencia

Podemos saber muchísimo Git mediante terminal.

Pero en:

```text
RA4.f
```

la norma exige:

```text
control integrado
en el entorno de desarrollo.
```

La práctica debe contener evidencia del uso integrado.

---

# 99. Buenas prácticas

## Commit frecuente pero significativo

No:

```text
cada 10 segundos
```

ni:

```text
una vez al mes.
```

Debe corresponder a unidades lógicas.

## Revisar antes de confirmar

Utilizar:

```text
diff.
```

## Mantener una historia comprensible

Mensajes claros.

## Trabajar en ramas

Cuando el cambio lo justifique.

## Sincronizar antes de integrar

Evitar sorpresas.

## Revisar Pull Requests

No hacer merge sin mirar.

## Proteger secretos

Siempre.

---

# 100. Caso profesional — CartagoParkingGit

Partimos de una pequeña aplicación para calcular precios de aparcamiento.

Evolución:

```text
C1
Estructura inicial

C2
Tarifa básica

C3
Validación

branch feature-descuento
C4
Descuento abonado

merge

branch feature-matricula
C5
Validación matrícula
Pull Request
Review
Merge
```

Este historial cuenta una historia técnica.

---

# 101. Ejercicio resuelto — historial

Supongamos:

```text
C1 Crea proyecto

C2 Añade cálculo

C3 Añade validación

C4 Corrige mensaje
```

Pregunta:

> ¿En qué commit apareció la validación?

Respuesta:

```text
C3.
```

Si queremos comprender el cambio:

```text
abrimos diff de C3.
```

---

# 102. Ejercicio resuelto — conflicto

`main`:

```java
private static final double TARIFA = 2.50;
```

`feature-tarifa`:

```java
private static final double TARIFA = 3.25;
```

Requisito final:

> La nueva tarifa aprobada es 3,25 €.

Resultado correcto:

```java
private static final double TARIFA = 3.25;
```

Lo importante no es:

```text
"elegí Theirs"
```

sino:

```text
"comprendí qué versión
cumplía el requisito".
```

---

# 103. Ejercicios de consolidación

1. ¿Qué problema resuelve un sistema de control de versiones?
2. Diferencia Git y GitHub.
3. ¿Qué es un repositorio?
4. ¿Qué es el working tree?
5. ¿Qué es un commit?
6. ¿Para qué sirve la staging area?
7. ¿Qué muestra un diff?
8. ¿Qué significa commit atómico?
9. Pon un buen mensaje de commit.
10. ¿Para qué sirve `.gitignore`?
11. ¿Debemos guardar contraseñas en Git?
12. ¿Qué es una rama?
13. ¿Por qué usamos ramas?
14. ¿Qué es merge?
15. ¿Qué es un conflicto?
16. ¿Por qué Git no puede resolver siempre un conflicto?
17. ¿Qué ventaja ofrece el merge tool del IDE?
18. ¿Qué significa revertir un commit?
19. ¿Qué es un repositorio remoto?
20. ¿Qué suele significar `origin`?
21. ¿Qué hace `push`?
22. ¿Qué hace `clone`?
23. ¿Qué diferencia conceptual existe entre `fetch` y `pull`?
24. ¿Qué es una Pull Request?
25. Diferencia `push` y Pull Request.
26. ¿Para qué sirve la revisión de código?
27. ¿Puede actualizarse una Pull Request después de una revisión?
28. ¿Qué ocurre tras hacer merge?
29. ¿Qué CE exige uso integrado de Git en el IDE?
30. ¿Qué CE exige repositorio remoto colaborativo?
31. ¿Pertenece GitHub Actions a esta unidad?
32. ¿Qué RA/CE evaluará la integración continua?

---

# 104. Actividad de ampliación

Investiga, sin utilizarlo todavía como flujo obligatorio:

```text
squash merge

rebase merge

protected branches

forks
```

y explica en qué situaciones pueden resultar útiles.

**No evaluable.**

---

# 105. Resumen

Git permite:

```text
registrar cambios

crear historial

trabajar con ramas

integrar cambios

resolver conflictos.
```

IntelliJ permite realizar estas operaciones mediante:

```text
control de versiones integrado.
```

GitHub añade:

```text
repositorio remoto

colaboración

Pull Requests

reviews.
```

Flujo profesional simplificado:

```text
RAMA
↓
CAMBIOS
↓
COMMIT
↓
PUSH
↓
PULL REQUEST
↓
REVIEW
↓
MERGE
↓
ACTUALIZACIÓN LOCAL
```

---

# 106. Glosario

**Branch / rama:** línea de desarrollo dentro del historial.

**Clone:** creación de una copia local de un repositorio remoto.

**Commit:** registro identificado de cambios en el historial.

**Conflict:** situación en la que Git no puede decidir automáticamente cómo combinar cambios.

**Diff:** representación de las diferencias entre estados o versiones.

**Fetch:** operación que obtiene información/cambios del remoto sin implicar necesariamente su integración inmediata en la rama actual.

**Git:** sistema distribuido de control de versiones.

**GitHub:** plataforma de alojamiento y colaboración basada en repositorios Git.

**Merge:** integración de una línea de desarrollo en otra.

**Origin:** nombre convencional utilizado frecuentemente para el remoto principal.

**Pull:** operación para obtener e integrar cambios remotos según la estrategia configurada.

**Pull Request:** propuesta de integración de cambios con mecanismos de revisión y discusión.

**Push:** envío de commits/referencias locales hacia un remoto.

**Remote:** referencia a otro repositorio, habitualmente alojado en otro sistema.

**Repository:** proyecto y metadatos de control de versiones.

**Review:** revisión formal de cambios propuestos.

**Staging area:** área donde se seleccionan cambios para el siguiente commit.

**Working tree:** archivos actuales sobre los que trabaja el desarrollador.

---

# 107. Autoevaluación

### 1
Git es:

A. un sistema de control de versiones  
B. un IDE  
C. un JDK  
D. UML

### 2
GitHub es:

A. la JVM  
B. una plataforma que puede alojar repositorios Git  
C. un compilador  
D. Java

### 3
Un commit:

A. registra un cambio en el historial  
B. es lo mismo que guardar  
C. siempre publica en GitHub  
D. borra la rama

### 4
La staging area permite:

A. decidir qué incluir en el siguiente commit  
B. compilar Java  
C. crear UML  
D. ejecutar tests

### 5
Una rama:

A. permite aislar una línea de trabajo  
B. es un plugin  
C. sustituye al repositorio  
D. es un conflicto

### 6
Un conflicto:

A. siempre implica corrupción  
B. requiere una decisión cuando Git no puede combinar automáticamente ciertos cambios  
C. elimina el repositorio  
D. solo existe en GitHub

### 7
`push`:

A. publica commits hacia el remoto  
B. crea una Pull Request automáticamente siempre  
C. ejecuta Java  
D. compila

### 8
Una Pull Request:

A. propone integrar cambios  
B. sustituye a Git  
C. instala IntelliJ  
D. es un JDK

### 9
RA4.f exige:

A. control de versiones integrado en el entorno  
B. CI  
C. UML  
D. testing

### 10
GitHub Actions:

A. se evalúa en UD05  
B. queda reservado para UD11  
C. pertenece a RA2  
D. sustituye Git

---

# 108. PRÁCTICA EVALUABLE P05.1

# CONTROL DE VERSIONES Y COLABORACIÓN EN CARTAGOPARKING

**Modalidad:** trabajo técnico individual con fase colaborativa por parejas  
**Calificación:** individual  
**RA:** RA4  
**CE evaluados:** RA4.f y RA4.h  
**Instrumento:** I-RA4-01  

---

# 109. Objetivo

Demostrar que puedes:

```text
mantener un historial coherente

utilizar Git integrado en IntelliJ

trabajar con ramas

resolver conflictos

utilizar un repositorio remoto

colaborar mediante GitHub

crear/revisar Pull Requests
```

sin evaluar todavía:

```text
CI

refactorización

testing

documentación automática.
```

---

# 110. Proyecto inicial

Proyecto:

```text
CartagoParkingGit
```

Código inicial:

```java
public class TarifaParking {

    private static final double TARIFA_HORA =
            2.50;

    public static double calcularPrecio(
            int horas) {

        return horas * TARIFA_HORA;
    }
}
```

---

# 111. PARTE A — Crear el repositorio

Desde IntelliJ:

```text
habilita Git

comprueba integración

crea .gitignore

revisa archivos.
```

Primer commit:

```text
Crea estructura inicial de CartagoParking
```

---

# 112. PARTE B — Historial individual

Realiza al menos estos cambios en commits separados:

## Commit 2

```text
Valida duración positiva
```

## Commit 3

```text
Añade tarifa máxima diaria
```

Debes demostrar:

```text
diff revisado

commit integrado desde IntelliJ

Git Log.
```

---

# 113. PARTE C — Rama `feature-descuento`

Desde IntelliJ:

```text
main
↓
feature-descuento
```

Implementa descuento de:

```text
10 %
```

para clientes abonados.

Commit:

```text
Añade descuento para abonados
```

Integra después la rama en:

```text
main.
```

---

# 114. PARTE D — Conflicto obligatorio

Crea:

```text
feature-tarifa
```

En ella modifica:

```java
TARIFA_HORA
```

a:

```text
3.25
```

Mientras tanto modifica en:

```text
main
```

la misma constante a otro valor proporcionado por el profesor.

Al intentar integrar:

# DEBE APARECER UN CONFLICTO REAL.

---

# 115. Resolver el conflicto

Requisito final:

```text
TARIFA_HORA = 3.25
```

Utiliza:

```text
IntelliJ Merge Tool
```

para construir el resultado final.

Después:

```text
commit del merge

comprobar historial.
```

---

# 116. Evidencias RA4.f

```text
E-RA4.f-01
Repositorio Git reconocido por IntelliJ.

E-RA4.f-02
Diff y selección de cambios.

E-RA4.f-03
Historial con commits coherentes.

E-RA4.f-04
Rama feature-descuento.

E-RA4.f-05
Merge de rama.

E-RA4.f-06
Conflicto real resuelto con IntelliJ.

E-RA4.f-07
Git Log final.
```

---

# 117. PARTE E — Publicar en GitHub

Publica:

```text
CartagoParkingGit
```

en un repositorio remoto.

Debes identificar:

```text
remote

origin

main

URL/nombre del repositorio.
```

No incluyas credenciales en el informe.

---

# 118. PARTE F — Colaborador

Añade al compañero asignado como colaborador cuando el tipo de repositorio utilizado lo requiera.

El colaborador deberá:

```text
clonar
```

el repositorio en su propio equipo.

---

# 119. PARTE G — Rama colaborativa

El colaborador crea:

```text
feature-validacion
```

y añade una validación acordada.

Ejemplo:

```java
if (horas < 1) {
    throw new IllegalArgumentException(
            "Horas no válidas"
    );
}
```

Realiza:

```text
commit

push.
```

---

# 120. PARTE H — Pull Request

El colaborador abre:

```text
feature-validacion
→ main
```

mediante una Pull Request.

Debe contener:

```text
título útil

descripción

cambio acotado.
```

---

# 121. PARTE I — Review

El propietario revisa el cambio.

Debe existir al menos:

```text
un comentario concreto
sobre código
```

y posteriormente:

```text
aprobación
```

o:

```text
solicitud de modificación
+
corrección.
```

---

# 122. PARTE J — Actualización tras review

Si existe modificación solicitada:

```text
colaborador
↓
edita rama
↓
commit
↓
push
↓
Pull Request actualizada.
```

---

# 123. PARTE K — Merge

Una vez aceptada:

```text
merge
```

de la Pull Request en:

```text
main.
```

Para la práctica utilizaremos normalmente:

```text
Create a merge commit
```

para conservar claramente la integración.

---

# 124. PARTE L — Sincronización

El colaborador debe actualizar su:

```text
main local
```

hasta contener el cambio integrado.

Debe demostrar:

```text
repositorio local actualizado

historial coherente.
```

---

# 125. PARTE M — Explicación técnica

Responde:

1. ¿Qué diferencia existe entre Git y GitHub?
2. ¿Qué función tiene la staging area?
3. ¿Por qué dividiste los cambios en varios commits?
4. ¿Qué ventaja proporcionó `feature-descuento`?
5. ¿Por qué apareció el conflicto?
6. ¿Cómo decidiste la resolución correcta?
7. ¿Qué es `origin`?
8. Diferencia `push` y Pull Request.
9. ¿Qué función tuvo la review?
10. ¿Por qué el compañero tuvo que actualizar `main` después del merge?
11. ¿Por qué GitHub Actions no forma parte de esta práctica?
12. ¿Por qué utilizar únicamente comandos de terminal no sería evidencia suficiente de RA4.f?

---

# 126. Entregables

```text
P05.1_Apellidos_Nombre.pdf
```

más referencia al:

```text
repositorio GitHub
```

utilizado.

El dossier debe contener:

```text
historial

ramas

conflicto

resolución

remote

Pull Request

review

merge

sincronización final.
```

---

# 127. Evidencias RA4.h

```text
E-RA4.h-01
Repositorio remoto publicado.

E-RA4.h-02
Clonado por colaborador.

E-RA4.h-03
Rama remota de colaboración.

E-RA4.h-04
Push colaborativo.

E-RA4.h-05
Pull Request.

E-RA4.h-06
Review.

E-RA4.h-07
Merge.

E-RA4.h-08
Sincronización local posterior.
```

---

# 128. Instrumento I-RA4-01

**Instrumento:** I-RA4-01  
**RA:** RA4  
**CE:** RA4.f y RA4.h  
**Actividad:** P05.1 – Control de versiones y colaboración en CartagoParking  
**Tipo:** laboratorio técnico individual con interacción colaborativa  
**Calificación:** individual

Cada alumno obtiene:

```text
NOTA RA4.f = 0–10

NOTA RA4.h = 0–10
```

independientemente.

---

# 129. Rúbrica definitiva I-RA4-01

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA4.f** | Realiza control de versiones integrado en el entorno de desarrollo | El historial es incoherente, las operaciones se realizan únicamente fuera del IDE o no demuestra ramas/merge de forma funcional | Utiliza Git integrado para commits y operaciones básicas, aunque necesita ayuda o presenta un historial poco organizado | Utiliza IntelliJ de forma correcta para revisar cambios, crear commits coherentes, consultar historial, gestionar ramas, integrar y resolver un conflicto real | Además mantiene una historia especialmente clara, selecciona cambios con precisión, justifica sus decisiones y resuelve el conflicto comprendiendo el resultado en vez de aceptar automáticamente una versión | **100 % del CE** |
| **RA4.h** | Utiliza repositorios remotos para desarrollo de código colaborativo | No existe colaboración real o el remoto se limita a almacenar una copia del proyecto | Publica/clona/sincroniza un remoto y participa en alguna operación colaborativa con ayuda | Trabaja correctamente con remoto, rama colaborativa, push, Pull Request, review, merge y actualización posterior | Además mantiene un flujo limpio y reproducible, responde correctamente a revisión, interpreta diferencias local/remoto y documenta la colaboración con autonomía profesional | **100 % del CE** |

---

# 130. Nota informativa de P05.1

Si se muestra una nota resumen:

```text
(
 RA4.f
+RA4.h
) / 2
```

pero en el registro se conservan de manera independiente:

```text
RA4.f

RA4.h.
```

---

# 131. Temporalización definitiva

| Sesión | Contenido | Actividades |
|---:|---|---|
| 1 | Git, repositorio, working tree, staging y commits | A05.1 |
| 2 | Diff, historial, `.gitignore`, buenas prácticas | A05.1 |
| 3 | Ramas y merge | A05.2 |
| 4 | Conflictos y herramienta visual | A05.3 |
| 5 | Reversión e historial | A05.4 |
| 6 | Remotos, origin, clone, fetch, pull y push | laboratorio guiado |
| 7 | Pull Requests y reviews | A05.5 |
| 8 | Colaboración y conflictos remotos | A05.6 |
| 9 | P05.1 — desarrollo | I-RA4-01 |
| 10 | P05.1 — colaboración, cierre y evidencias | I-RA4-01 |

**Total: 10 periodos.**

---

# 132. Autoevaluación — soluciones

```text
1 → A
2 → B
3 → A
4 → A
5 → A
6 → B
7 → A
8 → A
9 → A
10 → B
```

---

# PARTE B — MATERIAL DEL PROFESOR

# 133. Finalidad docente

La unidad debe conseguir que el alumno deje de entender Git como:

```text
una nube para guardar código
```

y comprenda:

```text
historial

commit

rama

integración

conflicto

remoto

colaboración.
```

Debe quedar especialmente clara la separación:

```text
RA4.f
→ control de versiones integrado
   en IntelliJ

RA4.h
→ colaboración mediante
   repositorio remoto.
```

---

# 134. La terminal no es el objeto de evaluación

Puede usarse para:

```text
explicar

diagnosticar

reforzar conceptos.
```

Pero un alumno que entregue exclusivamente:

```text
git add
git commit
git branch
git merge
```

sin evidencias de integración con IntelliJ:

```text
NO ha demostrado completamente RA4.f.
```

La redacción oficial especifica que el control de versiones se realiza integrado en el entorno de desarrollo.

---

# 135. IntelliJ como estándar de evaluación

La documentación actual de IntelliJ 2026.2 cubre:

```text
crear repositorio

commit

push

ramas

merge

conflictos

historial.
```

Esto hace posible mantener toda la evaluación principal dentro del entorno profesional adoptado en el curso.

---

# 136. Staging area

Para facilitar la comprensión inicial recomiendo activar:

```text
Enable staging area
```

durante esta UD.

Así el alumno observa explícitamente:

```text
modified
↓
staged
↓
committed.
```

IntelliJ mantiene actualmente esta opción en la configuración Git.

---

# 137. Commit atómico

No es necesario exigir una definición formal.

Debe observarse si el alumno es capaz de:

```text
separar trabajos diferentes
```

en commits distintos.

Ejemplo:

```text
Añade validación de horas
```

frente a:

```text
He hecho cosas.
```

---

# 138. `.gitignore`

La plantilla concreta dependerá del proyecto.

No imponer una lista memorizada.

Evaluar que el alumno entienda:

```text
qué debe ignorarse

y por qué.
```

---

# 139. Conflicto obligatorio

La práctica debe generar un conflicto:

# DELIBERADAMENTE.

Así evitamos evaluar RA4.f mediante:

```text
"si aparece algún conflicto".
```

Todos los alumnos tendrán evidencia comparable.

---

# 140. Conflicto propuesto

En:

```text
main
```

profesor/alumno establece:

```java
TARIFA_HORA = 2.80;
```

En:

```text
feature-tarifa
```

se establece:

```java
TARIFA_HORA = 3.25;
```

Requisito:

```text
La tarifa definitiva aprobada
es 3,25 €.
```

Resultado:

```java
TARIFA_HORA = 3.25;
```

---

# 141. Qué evaluar en el conflicto

No únicamente:

```text
conflicto resuelto.
```

Debe existir evidencia de que el alumno:

```text
identificó las dos versiones

interpretó el requisito

construyó el resultado

comprobó el archivo final

completó el merge.
```

---

# 142. Revert

Puede utilizarse una pequeña actividad guiada.

No convertir UD05 en un curso avanzado sobre:

```text
reset

rebase

reflog

cherry-pick

bisect.
```

No son necesarios para los CE.

---

# 143. Colaboración real

RA4.h exige:

```text
desarrollo de código colaborativo.
```

Por tanto:

```text
publicar un repositorio
y no compartirlo con nadie
```

es evidencia insuficiente.

Debe existir:

```text
segunda persona

rama

cambio

push

PR

review

merge.
```

---

# 144. Evaluación individual en trabajo por parejas

Aunque dos alumnos colaboren:

# LA NOTA ES INDIVIDUAL.

Cada alumno deberá demostrar:

```text
su propio control integrado

y

su participación en colaboración.
```

La mejor solución es:

```text
intercambiar roles
```

en una segunda modificación pequeña o conservar claramente evidencias de las acciones de cada alumno.

---

# 145. Pull Request

GitHub mantiene las Pull Requests como espacio para:

```text
proponer

discutir

revisar

integrar
```

cambios antes de incorporarlos a la rama base.

No exigir conocimientos avanzados de:

```text
rulesets

merge queue

CODEOWNERS.
```

---

# 146. Review mínima obligatoria

Debe existir al menos:

```text
un comentario técnico real
```

sobre el cambio.

No aceptar únicamente:

```text
"bien"
```

como review avanzada.

Ejemplo válido:

> La validación comprueba valores menores que 1, pero ¿qué sucede con una estancia superior a 24 horas?

---

# 147. CI fuera de evaluación

GitHub puede mostrar:

```text
Checks
```

dentro de una Pull Request.

No explicar todavía cómo configurarlos salvo comentario contextual.

Evitar introducir:

```text
GitHub Actions

workflow YAML

mvn verify
```

como tareas evaluables.

Eso corresponde a:

```text
UD11
→ RA4.i.
```

---

# 148. Capturas previstas

```text
CAPTURA UD05-01
Git settings / staging

CAPTURA UD05-02
VCS habilitado

CAPTURA UD05-03
Diff

CAPTURA UD05-04
Commit

CAPTURA UD05-05
Git Log

CAPTURA UD05-06
Branches

CAPTURA UD05-07
Merge conflict tool

CAPTURA UD05-08
Push

CAPTURA UD05-09
Pull Request

CAPTURA UD05-10
Review
```

---

# 149. Medidas de apoyo

Puede proporcionarse:

```text
checklist Git

mapa visual
working tree → staging → commit

lista de acciones IntelliJ

repositorio de entrenamiento

conflicto guiado previo.
```

No proporcionar:

```text
los commits finales
de la práctica

la resolución final
del conflicto evaluable

la review final.
```

---

# 150. Actividades de ampliación

Alumnado avanzado puede investigar:

```text
fork

rebase

squash

branch protection

Git tags

reflog
```

sin convertirlas en requisitos del CE.

---

# 151. Recuperación

Instrumento:

# IR-RA4-01

Bloques relacionados directamente con UD05:

```text
RA4.f

RA4.h
```

Ejemplo:

```text
RA4.f = 8
RA4.h = 3
```

Si RA4 permanece no superado y solo necesita nueva evidencia de:

```text
RA4.h
```

se asignará exclusivamente:

```text
bloque RA4.h
```

de IR-RA4-01.

No repetirá necesariamente toda P05.1.

---

# 152. Trazabilidad de UD05

| RA | CE | Contenido | Actividades | Instrumento | Evidencias |
|---|---|---|---|---|---|
| RA4 | f | Git integrado, commits, ramas, merge, conflicto, historial | A05.1–4 | P05.1 / I-RA4-01 | E-RA4.f-01/07 |
| RA4 | h | remoto, clone, push/pull, PR, review, colaboración | A05.5–6 | P05.1 / I-RA4-01 | E-RA4.h-01/08 |

---

# 153. Estado de RA4 tras UD05

```text
RA4.a → PENDIENTE UD11

RA4.b → PENDIENTE UD11

RA4.c → PENDIENTE UD11

RA4.d → PENDIENTE UD11

RA4.e → PENDIENTE UD11

RA4.f → EVALUADO UD05

RA4.g → PENDIENTE UD11

RA4.h → EVALUADO UD05

RA4.i → PENDIENTE UD11
```

RA4 permanece:

# ABIERTO.

---

# 154. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA4

**CE evaluados:**

```text
RA4.f

RA4.h
```

### ¿Se introduce código Java?

Sí.

Es únicamente:

```text
objeto sobre el que
se practica control de versiones.
```

No se evalúa programación.

### ¿Se evalúa testing?

# NO.

### ¿Se evalúa refactorización?

# NO.

### ¿Se evalúa documentación Javadoc?

# NO.

### ¿Se evalúa integración continua?

# NO.

Aunque GitHub pueda mostrar Checks/Actions, se reserva a:

```text
RA4.i
→ UD11.
```

### ¿Se evalúa el terminal?

# NO COMO COMPETENCIA INDEPENDIENTE.

### ¿Algún instrumento evalúa otro RA?

# NO.

```text
I-RA4-01
→ exclusivamente RA4.
```

---

# 155. Checklist de cierre UD05

```text
☑ 10 periodos.

☑ RA4 único.

☑ RA4.f oficial.

☑ RA4.h oficial.

☑ RA4.a-e/g/i reservados.

☑ Git ≠ GitHub.

☑ Repositorio.

☑ Working tree.

☑ Staging area.

☑ IntelliJ Git integration.

☑ Diff.

☑ Commit.

☑ Commit atómico.

☑ Mensajes de commit.

☑ .gitignore.

☑ Secretos excluidos.

☑ Git Log.

☑ Ramas.

☑ Merge.

☑ Conflicto obligatorio.

☑ Merge Tool.

☑ Revert contextualizado.

☑ Remotos.

☑ origin.

☑ push.

☑ clone.

☑ fetch.

☑ pull.

☑ GitHub.

☑ Colaboración real.

☑ Pull Request.

☑ Review.

☑ Merge PR.

☑ Actualización posterior.

☑ CI expresamente fuera.

☑ Refactorización expresamente fuera.

☑ 10 capturas previstas.

☑ Actividades guiadas.

☑ Consolidación.

☑ Ampliación.

☑ Resumen.

☑ Glosario.

☑ Autoevaluación.

☑ P05.1.

☑ I-RA4-01.

☑ RA4.f nota propia 0–10.

☑ RA4.h nota propia 0–10.

☑ Rúbrica armonizada.

☑ Evidencias codificadas.

☑ Evaluación individual.

☑ Material profesor.

☑ Recuperación modular.

☑ Trazabilidad.

☑ Sin ponderaciones antiguas.

☑ Aislamiento superado.
```

# UD05 — VERSIÓN MAESTRA DEFINITIVA