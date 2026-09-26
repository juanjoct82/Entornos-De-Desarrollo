# UD11 — CALIDAD DEL CÓDIGO, REFACTORIZACIÓN, DOCUMENTACIÓN E INTEGRACIÓN CONTINUA

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 15 periodos lectivos  
**Resultado de Aprendizaje:** RA4  

**Prácticas evaluables:**  
P11.1 — Auditoría y mejora de CartagoQuality  
P11.2 — Integración continua de CartagoQuality  

**Instrumentos:**  
I-RA4-02  
I-RA4-03  

**Lenguaje:** Java  
**JDK:** Eclipse Temurin JDK 25 LTS  
**IDE:** IntelliJ IDEA 2026.2  
**Build:** Maven  
**Pruebas:** JUnit  
**Documentación:** Javadoc  
**Integración continua:** GitHub Actions  

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

Ya somos capaces de:

```text
escribir código

probarlo

depurarlo

versionarlo

trabajar con repositorios remotos
```

Pero existe una pregunta adicional:

# ¿ES BUENO EL CÓDIGO QUE FUNCIONA?

Un programa puede:

```text
compilar

pasar pruebas

producir el resultado correcto
```

y aun así ser:

```text
difícil de leer

duplicado

muy acoplado

difícil de modificar

mal documentado

propenso a errores futuros.
```

En esta unidad aprenderemos a:

```text
analizar

detectar problemas

refactorizar

proteger cambios con pruebas

documentar

automatizar la verificación
```

del proyecto.

---

# 2. Resultado de Aprendizaje

## RA4

**Optimiza código empleando las herramientas disponibles en el entorno de desarrollo.**

---

# 3. Criterios de evaluación de UD11

Se evalúan exclusivamente:

## RA4.a

**Se han identificado los patrones de refactorización más usuales.**

## RA4.b

**Se han elaborado las pruebas asociadas a la refactorización.**

## RA4.c

**Se ha revisado el código fuente usando un analizador de código.**

## RA4.d

**Se han identificado las posibilidades de configuración de un analizador de código.**

## RA4.e

**Se han aplicado patrones de refactorización con las herramientas que proporciona el entorno de desarrollo.**

## RA4.g

**Se han utilizado herramientas del entorno de desarrollo para documentar las clases.**

## RA4.i

**Se han utilizado herramientas para la integración continua del código.**

---

# 4. CE ya evaluados en UD05

No se vuelven a calificar:

```text
RA4.f
→ control de versiones integrado

RA4.h
→ repositorios remotos
   y colaboración
```

En UD11 utilizaremos Git y GitHub porque son necesarios para:

```text
trabajar con CI
```

pero no generarán una segunda nota para:

```text
RA4.f

RA4.h.
```

---

# 5. ¿Qué aprenderemos?

Al finalizar la unidad deberás poder:

- explicar qué significa refactorizar;
- diferenciar refactorización y nueva funcionalidad;
- reconocer problemas frecuentes de diseño;
- identificar código duplicado;
- identificar métodos excesivamente largos;
- identificar nombres poco expresivos;
- identificar clases con demasiadas responsabilidades;
- identificar listas de parámetros excesivas;
- reconocer números o cadenas mágicas;
- reconocer condicionales difíciles de mantener;
- identificar operaciones habituales de refactorización;
- aplicar Rename;
- aplicar Extract Method;
- aplicar Extract Variable;
- aplicar Extract Constant;
- aplicar Move;
- aplicar Change Signature cuando proceda;
- aplicar Inline cuando aporte claridad;
- utilizar pruebas antes y después de refactorizar;
- utilizar IntelliJ para ejecutar inspecciones;
- comprender qué es un perfil de inspección;
- cambiar inspecciones habilitadas;
- cambiar severidades;
- definir ámbitos o *scopes*;
- interpretar informes de análisis;
- distinguir problema, advertencia e información;
- decidir cuándo aplicar un *quick-fix*;
- escribir comentarios Javadoc útiles;
- generar documentación HTML;
- comprender qué es integración continua;
- distinguir CI de automatización local;
- crear un workflow de GitHub Actions;
- configurar Temurin 25 en CI;
- ejecutar Maven automáticamente;
- interpretar un workflow verde o rojo;
- relacionar un fallo de CI con pruebas o build;
- comprender por qué una Pull Request puede verificarse automáticamente.

---

# 6. ¿Qué significa optimizar código en RA4?

En esta unidad:

```text
optimizar
```

no significa únicamente:

```text
hacer que el programa
consuma menos CPU.
```

También trabajaremos:

```text
mantenibilidad

legibilidad

estructura

calidad

documentación

automatización.
```

---

# 7. Refactorización

Refactorizar consiste en:

# MODIFICAR LA ESTRUCTURA INTERNA SIN CAMBIAR EL COMPORTAMIENTO EXTERNO ESPERADO.

IntelliJ define igualmente la refactorización como mejora del código sin introducir nueva funcionalidad y ofrece operaciones específicas para aplicarla de forma asistida.

---

# 8. Refactorizar ≠ añadir funcionalidad

## Nueva funcionalidad

Antes:

```text
el sistema no permite descuentos
```

Después:

```text
permite descuentos
```

El comportamiento ha cambiado.

---

# 9. Refactorización

Antes:

```java
public double c(int h) {
    return h * 50;
}
```

Después:

```java
public double calcularPrecio(int horas) {
    return horas * TARIFA_HORA;
}
```

Si los resultados funcionales permanecen:

```text
iguales
```

hemos mejorado estructura y legibilidad.

---

# 10. ¿Por qué refactorizar?

Porque el software:

```text
evoluciona.
```

Código difícil de mantener provoca:

```text
cambios más lentos

más errores

más dificultad para probar

más coste

más miedo a modificar.
```

---

# 11. Refactorización y riesgo

Modificar código que:

```text
ya funciona
```

tiene un riesgo:

> ¿Y si rompemos algo?

Por eso un principio fundamental de UD11 será:

# REFRACTORIZAR CON UNA RED DE SEGURIDAD.

La red de seguridad será:

```text
PRUEBAS.
```

---

# 12. CONOCIMIENTO AUXILIAR NO EVALUADO

Las pruebas unitarias fueron evaluadas en:

```text
RA3.f/g
UD10.
```

En UD11 se reutilizan para una finalidad distinta:

```text
proteger una refactorización.
```

Lo que se califica aquí es:

```text
RA4.b
```

es decir:

# LA RELACIÓN ENTRE PRUEBAS Y REFACTORIZACIÓN.

No se vuelve a calificar RA3.

---

# 13. Código problemático

Observa:

```java
public double calc(
        int h,
        boolean p,
        boolean f) {

    double t = h * 50;

    if (p) {
        t = t * 0.9;
    }

    if (f) {
        t = t + 20;
    }

    System.out.println(
        "TOTAL=" + t
    );

    return t;
}
```

Funciona.

Pero podemos preguntar:

```text
¿qué significa h?

¿qué significa p?

¿qué significa f?

¿qué representa 50?

¿qué representa 0.9?

¿qué representa 20?

¿debe imprimir aquí?
```

---

# 14. Code smell

Un *code smell* es:

```text
un indicio
de que el diseño
puede mejorarse.
```

No significa necesariamente:

```text
bug.
```

Puede ser código que:

```text
funciona
```

pero resulta:

```text
difícil de entender
o mantener.
```

---

# 15. Smells trabajados

Trabajaremos principalmente:

```text
nombres poco expresivos

métodos largos

código duplicado

números mágicos

clases grandes

listas largas de parámetros

responsabilidades mezcladas

condicionales complejos.
```

---

# 16. Nombres poco expresivos

Malo:

```java
double c(int x)
```

Mejor:

```java
double calcularPrecio(int horas)
```

El nombre debe comunicar:

```text
intención.
```

---

# 17. Rename

Refactorización:

```text
Rename
```

permite cambiar:

```text
variable

método

clase

campo
```

actualizando referencias de forma segura.

En IntelliJ el atajo de referencia es:

```text
Shift + F6.
```


---

# 18. Nunca renombres globalmente a ciegas

Buscar y reemplazar texto:

```text
puede cambiar elementos
que no corresponden.
```

La refactorización del IDE entiende:

```text
símbolos

referencias

usos.
```

---

# 19. Método largo

Ejemplo:

```java
public void procesarReserva(...) {

    // validar

    // calcular precio

    // aplicar descuento

    // guardar

    // enviar correo

    // imprimir informe
}
```

Puede contener:

```text
varias responsabilidades.
```

---

# 20. Extract Method

Podemos pasar de:

```java
if (horas < 1) {
    throw new IllegalArgumentException();
}

double total = horas * 50;

if (premium) {
    total *= 0.90;
}
```

a:

```java
validarHoras(horas);

double total =
        calcularImporte(
                horas,
                premium
        );
```

---

# 21. Ventaja

Los nombres:

```text
validarHoras

calcularImporte
```

explican:

```text
qué ocurre
```

sin leer todos los detalles.

---

# 22. Extract Method en IntelliJ

Refactorización:

```text
Extract Method
```

Atajo Windows de referencia:

```text
Ctrl + Alt + M.
```

IntelliJ permite previsualizar determinadas refactorizaciones y revisar los cambios antes de aplicarlos.

---

# 23. Número mágico

Ejemplo:

```java
double total =
        horas * 50;
```

Pregunta:

> ¿Qué significa 50?

Podemos transformar:

```java
private static final double TARIFA_HORA =
        50.0;
```

y después:

```java
double total =
        horas * TARIFA_HORA;
```

---

# 24. Extract Constant

IntelliJ ofrece:

```text
Extract Constant
```

para convertir valores repetidos o significativos en constantes.

Atajo de referencia:

```text
Ctrl + Alt + C.
```


---

# 25. Extract Variable

Expresión:

```java
if (horas * TARIFA_HORA > 200
        && premium) {
```

Puede transformarse en:

```java
double importeBase =
        horas * TARIFA_HORA;

if (importeBase > 200
        && premium) {
```

si mejora la comprensión.

---

# 26. Regla importante

No extraemos variables:

```text
porque sí.
```

Una refactorización debe aportar:

```text
claridad

reutilización

reducción de complejidad

mejor estructura.
```

---

# 27. Código duplicado

Ejemplo:

```java
System.out.println(
    "Reserva: " + id
);

System.out.println(
    "Cliente: " + cliente
);
```

aparece en:

```text
tres métodos diferentes.
```

Puede indicar:

```text
duplicación.
```

IntelliJ dispone además de una inspección específica para detectar fragmentos duplicados y permite configurarla dentro de los perfiles de inspección.

---

# 28. Problemas de duplicación

Si cambiamos:

```text
el formato
```

debemos recordar modificar:

```text
todas las copias.
```

Si olvidamos una:

```text
comportamiento inconsistente.
```

---

# 29. Move

A veces un método está situado:

```text
en la clase equivocada.
```

Ejemplo:

```text
ReservaController
```

contiene lógica profunda de:

```text
cálculo de tarifas.
```

Podría ser más coherente mover esa responsabilidad a:

```text
TarifaReserva

o

ServicioTarifas.
```

---

# 30. Refactorización Move

IntelliJ ofrece:

```text
Move
```

para mover elementos de forma asistida.

Atajo habitual:

```text
F6.
```


---

# 31. Change Signature

Supongamos:

```java
crearReserva(
    String nombre,
    String email,
    int horas,
    boolean premium,
    String sala,
    LocalDate fecha
)
```

Puede existir una lista excesiva de parámetros.

Dependiendo del diseño podemos necesitar:

```text
Change Signature

o una refactorización
más profunda.
```

IntelliJ permite cambiar una firma actualizando sus usos.

---

# 32. Inline

A veces ocurre lo contrario.

Método:

```java
private double uno() {
    return 1.0;
}
```

utilizado solo una vez y que:

```text
no aporta significado.
```

Podría ser candidato a:

```text
Inline.
```

---

# 33. No existe una lista automática de refactorizaciones buenas

Una operación puede mejorar un proyecto:

```text
en un contexto
```

y empeorarlo:

```text
en otro.
```

Por eso:

```text
IDENTIFICAR PROBLEMA
↓
SELECCIONAR REFACTOR
↓
COMPROBAR RESULTADO
```

---

# 34. RA4.a

Para RA4.a debes demostrar que puedes:

```text
reconocer una situación

identificar la refactorización
adecuada

explicar qué problema resuelve.
```

No basta memorizar:

```text
Rename
Extract Method
Move.
```

---

# 35. Actividad A11.1 — Detecta smells

Código:

```java
public double x(
        int a,
        boolean b) {

    if (a <= 0) {
        throw new RuntimeException();
    }

    double c = a * 50;

    if (b == true) {
        c = c * 0.9;
    }

    System.out.println(
        "precio=" + c
    );

    return c;
}
```

Identifica al menos:

```text
4 aspectos mejorables
```

y propón:

```text
una refactorización
para cada uno.
```

---

# 36. Antes de refactorizar

Flujo profesional:

```text
1. comprobar comportamiento actual

2. ejecutar pruebas

3. asegurar estado verde

4. realizar una refactorización pequeña

5. volver a ejecutar pruebas

6. comprobar resultado

7. continuar.
```

---

# 37. Regla de oro

No empieces a refactorizar un proyecto si:

```text
las pruebas ya están rojas
```

sin saber:

```text
por qué.
```

De lo contrario no sabremos si:

```text
el fallo era previo

o

lo introdujimos nosotros.
```

---

# 38. Refactorización protegida por pruebas

```text
TEST VERDE
↓
REFACTOR
↓
TEST VERDE
```

Este ciclo será la evidencia principal de:

# RA4.b.

---

# 39. Ejemplo

Antes:

```java
public double calcular(
        int horas,
        boolean premium) {

    if (horas < 1) {
        throw new
                IllegalArgumentException();
    }

    double total = horas * 50;

    if (premium) {
        total = total * 0.90;
    }

    return total;
}
```

---

# 40. Tests previos

```java
@Test
void calculaDosHoras() {

    assertEquals(
        100.0,
        tarifa.calcular(
            2,
            false
        )
    );
}
```

```java
@Test
void aplicaPremium() {

    assertEquals(
        90.0,
        tarifa.calcular(
            2,
            true
        )
    );
}
```

---

# 41. Refactor

Aplicamos:

```text
Extract Constant

Extract Method

Rename
```

---

# 42. Después

```java
private static final double TARIFA_HORA =
        50.0;

private static final double
        DESCUENTO_PREMIUM =
        0.10;

public double calcularPrecio(
        int horas,
        boolean premium) {

    validarHoras(horas);

    double total =
            calcularImporteBase(horas);

    return premium
            ? aplicarDescuento(total)
            : total;
}
```

---

# 43. Volver a ejecutar

```bash
mvn test
```

Si:

```text
todos pasan
```

tenemos evidencia de que:

```text
el comportamiento cubierto
por las pruebas
se conserva.
```

---

# 44. Importante

Las pruebas:

```text
no demuestran
que absolutamente todo
sea idéntico.
```

Demuestran que:

```text
los comportamientos comprobados
continúan cumpliéndose.
```

---

# 45. Actividad A11.2 — Red de seguridad

1. Ejecuta suite inicial.
2. Guarda evidencia verde.
3. Aplica Rename.
4. Ejecuta pruebas.
5. Aplica Extract Method.
6. Ejecuta pruebas.
7. Aplica Extract Constant.
8. Ejecuta pruebas.
9. Documenta si apareció algún fallo.

---

# 46. Analizador de código

El IDE puede analizar el código para detectar:

```text
errores potenciales

código muerto

duplicación

estilo

problemas de mantenibilidad

usos sospechosos

problemas de documentación
```

sin necesidad de ejecutar todas las rutas del programa.

---

# 47. Inspections de IntelliJ

IntelliJ analiza código mientras escribimos y también permite ejecutar inspecciones en lote sobre:

```text
archivo

directorio

módulo

proyecto

scope personalizado.
```

El informe aparece en una ventana específica de resultados.

---

# 48. Análisis estático

A esta forma de análisis la denominamos habitualmente:

```text
análisis estático
```

porque examina:

```text
el código
```

sin necesitar necesariamente:

```text
ejecutar la aplicación.
```

---

# 49. Ejemplos de hallazgos

```text
variable sin utilizar

condición siempre verdadera

código duplicado

método demasiado complejo

problemas de nulabilidad

Javadoc incorrecto

código inalcanzable.
```

---

# 50. `Inspect Code`

Ruta de referencia:

```text
Code
→ Analyze Code
→ Inspect Code
```

o acción equivalente según interfaz.

Podemos seleccionar:

```text
Whole project

Module

Directory

Custom scope.
```

IntelliJ permite ejecutar manualmente el conjunto de inspecciones activado en un perfil y generar un informe completo del ámbito seleccionado.

---

# 51. CAPTURA UD11-01 — Inspect Code

Debe mostrar:

```text
ámbito

perfil

inicio del análisis.
```

---

# 52. Resultados

El informe puede agrupar problemas por:

```text
categoría

archivo

severidad

tipo.
```

El alumno debe poder:

```text
abrir el problema

leer la explicación

localizar el código

decidir qué hacer.
```

---

# 53. Quick-fix

IntelliJ puede ofrecer:

```text
Alt + Enter
```

para aplicar una corrección.

Pero:

# QUE EXISTA UN QUICK-FIX NO SIGNIFICA QUE DEBAMOS ACEPTARLO SIN PENSAR.

El IDE permite previsualizar y aplicar correcciones para muchas inspecciones desde el editor o desde la ventana de problemas.

---

# 54. Pregunta correcta

Antes de aplicar:

```text
¿entiendo el problema?

¿entiendo qué cambiará?

¿mantendrá el comportamiento?
```

---

# 55. Perfil de inspección

Un:

```text
Inspection Profile
```

define:

```text
qué inspecciones están habilitadas

qué severidad tienen

qué ámbito analizan

qué opciones utilizan.
```

IntelliJ distingue perfiles almacenados a nivel de IDE y perfiles almacenados dentro del proyecto.

---

# 56. CAPTURA UD11-02 — Inspection Profile

Debe mostrar:

```text
Settings
→ Editor
→ Inspections
```

con:

```text
perfil seleccionado

inspecciones

severidad.
```

---

# 57. Severidad

Una inspección puede configurarse como:

```text
error

warning

weak warning

information
```

o niveles equivalentes.

La severidad determina:

```text
cómo se presenta
el problema.
```

---

# 58. La severidad no cambia el código

Si cambiamos:

```text
Warning
→ Error
```

estamos cambiando:

```text
la forma de tratar
el hallazgo
```

no:

```text
el código fuente
directamente.
```

---

# 59. Scope

Un *scope* indica:

```text
qué parte
del proyecto
analizar.
```

Por ejemplo:

```text
production

tests

package específico

directorio

custom scope.
```

---

# 60. ¿Por qué configurar el analizador?

Una empresa puede decidir:

```text
prohibir determinados problemas

dar más importancia
a otros

ignorar determinadas reglas

aplicar reglas distintas
en tests y producción.
```

---

# 61. RA4.d

Para demostrar RA4.d debes reconocer:

```text
perfil

habilitar/deshabilitar regla

severidad

scope

opciones de una inspección.
```

No basta únicamente:

```text
ejecutar Inspect Code.
```

---

# 62. Actividad A11.3 — Perfil Miralmonte

Duplica un perfil y crea:

```text
Miralmonte-Quality
```

Configura al menos:

```text
una inspección habilitada

una inspección con severidad modificada

un scope

una regla con opciones
si la inspección lo permite.
```

Documenta:

```text
qué has cambiado

por qué.
```

---

# 63. Inspección de duplicación

IntelliJ incluye:

```text
Duplicated code fragment
```

y permite configurar aspectos de esta inspección dentro del perfil.

Podemos utilizarla como ejemplo claro de:

```text
analizador
+
configuración.
```

---

# 64. Código muerto

Un analizador puede detectar:

```text
variables

métodos

campos
```

que aparentemente no se utilizan.

Pero debemos comprobar:

```text
contexto

framework

reflexión

uso externo
```

antes de eliminar automáticamente.

---

# 65. Análisis ≠ verdad absoluta

El analizador:

```text
ayuda.
```

El desarrollador:

```text
decide.
```

Puede haber:

```text
falsos positivos

reglas no aplicables

decisiones conscientes.
```

---

# 66. Supresión

En determinadas situaciones una inspección puede:

```text
suprimirse
```

de forma justificada.

Pero:

```text
suprimir todo
```

para dejar el proyecto sin advertencias:

# NO ES CALIDAD.

---

# 67. Análisis antes y después

Proceso:

```text
ANÁLISIS INICIAL
↓
REFACTOR
↓
ANÁLISIS FINAL
```

Podemos comparar:

```text
número

tipo

severidad
```

de problemas.

---

# 68. CAPTURA UD11-03 — Resultados de inspección

Debe mostrar:

```text
problemas detectados

categorías

archivos.
```

---

# 69. Refactorización con herramientas del IDE

RA4.e exige expresamente:

```text
usar herramientas
del entorno.
```

Por tanto:

```text
editar manualmente
todos los nombres
```

no demuestra completamente este CE.

---

# 70. Herramientas que utilizaremos

```text
Rename

Extract Method

Extract Variable

Extract Constant

Move

Inline

Change Signature
```

cuando proceda.

IntelliJ 2026.2 mantiene estas refactorizaciones asistidas y permite revisar conflictos y previsualizar muchos cambios antes de aplicarlos.

---

# 71. CAPTURA UD11-04 — Refactor This

Debe mostrar:

```text
Refactor
→ Refactor This
```

o:

```text
Ctrl + Alt + Shift + T
```

con distintas operaciones disponibles.

---

# 72. CAPTURA UD11-05 — Preview

Debe mostrar:

```text
usos afectados

cambios previstos

acción final.
```

---

# 73. Refactor pequeño

Es preferible:

```text
Rename
↓
tests

Extract Method
↓
tests

Move
↓
tests
```

que:

```text
cambiar 50 cosas
↓
ejecutar una vez
```

porque facilita localizar:

```text
qué cambio
introdujo un problema.
```

---

# 74. Documentación del código

Código legible:

```text
reduce necesidad
de comentarios innecesarios.
```

Pero seguimos necesitando documentar:

```text
API

contratos

parámetros

retornos

excepciones

comportamientos relevantes.
```

---

# 75. Comentario inútil

```java
// suma uno
contador++;
```

No aporta:

```text
información nueva.
```

---

# 76. Comentario útil

```java
/**
 * Calcula el precio de una reserva.
 *
 * @param horas número de horas reservadas
 * @param premium indica si se aplica
 *                tarifa premium
 * @return importe final de la reserva
 * @throws IllegalArgumentException
 *         si horas es menor que uno
 */
public double calcularPrecio(
        int horas,
        boolean premium) {
```

---

# 77. Javadoc

Javadoc es una herramienta del JDK que genera documentación de API a partir de:

```text
comentarios estructurados
en el código.
```

IntelliJ 2026.2 permite crear ayudas para comentarios Javadoc, detectar problemas y generar la referencia HTML del proyecto.

---

# 78. Tags principales

Trabajaremos:

```text
@param

@return

@throws
```

y descripciones de:

```text
clase

método

responsabilidad.
```

---

# 79. No documentar lo obvio

Malo:

```java
/**
 * Devuelve el nombre.
 */
public String getNombre()
```

puede resultar poco útil si no existe ninguna particularidad.

Más importante es documentar:

```text
contratos

restricciones

efectos

excepciones.
```

---

# 80. Tools → Generate Javadoc

IntelliJ permite generar la referencia mediante:

```text
Tools
→ Generate Javadoc
```

seleccionando:

```text
scope

directorio de salida

nivel de visibilidad

opciones.
```


---

# 81. CAPTURA UD11-06 — Generate Javadoc

Debe mostrar:

```text
scope

output directory

visibility.
```

---

# 82. Resultado

Se genera:

```text
documentación HTML
```

navegable con:

```text
clases

métodos

parámetros

descripciones.
```

---

# 83. CAPTURA UD11-07 — Javadoc HTML

Debe mostrar:

```text
una clase

un método

su documentación
generada.
```

---

# 84. RA4.g

Para superar RA4.g no basta:

```text
escribir comentarios //.
```

Debe existir evidencia de:

```text
herramienta del IDE/JDK

documentación de clases

generación o validación
de documentación.
```

---

# 85. Actividad A11.4 — Documenta una API

Documenta:

```text
TarifaReserva

ReservaService
```

incluyendo al menos:

```text
responsabilidad de clase

métodos públicos relevantes

parámetros

retornos

excepciones.
```

Genera:

```text
Javadoc HTML.
```

---

# 86. Calidad local vs calidad continua

Hasta ahora podemos ejecutar:

```bash
mvn test
```

manualmente.

También podemos ejecutar:

```text
Inspect Code
```

manualmente.

Pero un equipo puede olvidar:

```text
hacerlo
antes de publicar cambios.
```

---

# 87. Integración continua

CI significa:

```text
Continuous Integration
```

o:

```text
Integración Continua.
```

Una idea básica:

```text
cada cambio frecuente
se integra
y se verifica
automáticamente.
```

---

# 88. Objetivo

Detectar problemas:

```text
pronto
```

en lugar de:

```text
al final del proyecto.
```

---

# 89. Automatización local vs CI

## Automatización local

```bash
mvn test
```

ejecutada:

```text
por el desarrollador
en su ordenador.
```

## CI

Un sistema externo ejecuta automáticamente el proceso al producirse eventos como:

```text
push

Pull Request.
```

---

# 90. GitHub Actions

Utilizaremos:

```text
GitHub Actions
```

como herramienta de integración continua.

GitHub documenta específicamente workflows de CI para proyectos Java con Maven, destinados a compilar y probar automáticamente cambios y Pull Requests.

---

# 91. Workflow

Un workflow se define normalmente mediante:

```text
YAML
```

dentro de:

```text
.github/workflows/
```

Ejemplo:

```text
.github/
└── workflows/
    └── ci.yml
```

---

# 92. Estructura básica

```yaml
name: CI

on:
  push:
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      ...
```

---

# 93. `name`

```yaml
name: CI
```

define:

```text
el nombre visible
del workflow.
```

---

# 94. `on`

```yaml
on:
  push:
  pull_request:
```

define:

```text
cuándo
se ejecuta.
```

---

# 95. `jobs`

Un workflow contiene:

```text
uno o más trabajos.
```

Nuestro caso:

```yaml
jobs:
  build:
```

---

# 96. Runner

```yaml
runs-on: ubuntu-latest
```

indica el entorno de ejecución del job.

---

# 97. Checkout

El runner necesita:

```text
el código del repositorio.
```

Utilizaremos:

```yaml
- uses: actions/checkout@v7
```

---

# 98. Java

Después configuramos:

```yaml
- uses: actions/setup-java@v6
  with:
    distribution: temurin
    java-version: '25'
```

El proyecto oficial `setup-java` utiliza actualmente exactamente este patrón —`checkout@v7`, `setup-java@v6` y `java-version: '25'`— en sus ejemplos vigentes.

---

# 99. Caché Maven

Podemos añadir:

```yaml
cache: maven
```

para reutilizar dependencias entre ejecuciones y reducir descargas.

El propio `setup-java` soporta caché de dependencias Maven.

---

# 100. Verificación

Finalmente:

```yaml
- name: Verify with Maven
  run: mvn --batch-mode verify
```

---

# 101. ¿Por qué `verify`?

En Maven:

```text
test
```

ejecuta la fase de pruebas.

```text
verify
```

avanza en el ciclo y permite:

```text
construir

ejecutar pruebas

realizar comprobaciones
configuradas
```

hasta esa fase.

GitHub y `setup-java` muestran `mvn verify` como flujo válido para proyectos Maven en Actions.

---

# 102. Workflow definitivo

```yaml
name: CartagoQuality CI

on:
  push:
    branches:
      - main

  pull_request:
    branches:
      - main

jobs:
  build:

    runs-on: ubuntu-latest

    steps:

      - name: Checkout repository
        uses: actions/checkout@v7

      - name: Set up Temurin 25
        uses: actions/setup-java@v6
        with:
          distribution: temurin
          java-version: '25'
          cache: maven

      - name: Verify project
        run: mvn --batch-mode verify
```

---

# 103. Qué ocurre tras push

```text
PUSH
↓
GitHub detecta evento
↓
crea runner
↓
checkout
↓
instala/configura Java 25
↓
ejecuta Maven
↓
compila
↓
ejecuta pruebas
↓
resultado
```

---

# 104. Resultado verde

Si:

```text
build correcto

tests correctos
```

workflow:

```text
SUCCESS.
```

---

# 105. Resultado rojo

Si:

```text
compilación falla

o

una prueba falla
```

workflow:

```text
FAILURE.
```

---

# 106. CAPTURA UD11-08 — GitHub Actions

Debe mostrar:

```text
workflow ejecutado

job

estado.
```

---

# 107. CAPTURA UD11-09 — Job details

Debe mostrar:

```text
Checkout

Set up Temurin

Verify project

salida Maven.
```

---

# 108. CI no arregla errores

GitHub Actions:

```text
detecta

informa

bloquea según configuración
```

pero:

```text
no arregla automáticamente
la lógica
del programa.
```

---

# 109. Pull Request + CI

Podemos obtener:

```text
PR
↓
CI
↓
tests
↓
resultado
```

antes de integrar cambios.

Esto permite conocer:

```text
si el cambio rompe
la construcción
o las pruebas.
```

---

# 110. CONOCIMIENTO AUXILIAR NO EVALUADO

Crear ramas, push y Pull Requests pertenece a:

```text
RA4.f/h
UD05.
```

En UD11 los utilizamos:

```text
solo como infraestructura
para ejecutar CI.
```

No se vuelven a calificar.

---

# 111. CI ≠ CD

## CI

```text
integrar

construir

probar

verificar.
```

## CD

Puede referirse a procesos posteriores de:

```text
entrega

despliegue.
```

En UD11 trabajaremos:

# CI.

No desplegaremos la aplicación.

---

# 112. Error frecuente — CI que no ejecuta pruebas

Workflow:

```yaml
- run: echo "Todo bien"
```

no demuestra adecuadamente:

```text
integración continua
del código.
```

Debe existir:

```text
verificación real
del proyecto.
```

---

# 113. Error frecuente — workflow solo manual

Si el alumno pulsa:

```text
Run workflow
```

manualmente como única evidencia:

```text
no demuestra
integración automática
ante cambios.
```

Nuestro workflow reaccionará a:

```text
push

pull_request.
```

---

# 114. Error frecuente — usar Java distinto

Local:

```text
Temurin 25
```

CI:

```text
Java 17
```

puede generar:

```text
inconsistencias.
```

Nuestro estándar:

```text
Temurin 25
```

también en CI.

---

# 115. Error frecuente — ignorar workflow rojo

Un check rojo:

```text
no es decoración.
```

Debemos:

```text
abrir job

buscar step que falla

leer log

identificar causa.
```

---

# 116. Error frecuente — cambiar tests para que pasen

Ante:

```text
test rojo
```

no debemos simplemente:

```text
cambiar el esperado
hasta que sea verde.
```

Primero:

```text
comprobar requisito.
```

---

# 117. Calidad integrada

Podemos pensar:

```text
CÓDIGO
↓
INSPECCIÓN
↓
TESTS
↓
REFACTOR
↓
DOCUMENTACIÓN
↓
CI
```

La calidad no depende de una sola herramienta.

---

# 118. Caso profesional — CartagoQuality

Recibimos un proyecto Java que:

```text
funciona

tiene pruebas
```

pero contiene:

```text
nombres pobres

duplicación

métodos largos

números mágicos

documentación insuficiente

warnings

ningún workflow CI.
```

Nuestra misión:

# CONVERTIRLO EN UN PROYECTO MÁS MANTENIBLE Y VERIFICABLE.

---

# 119. Código inicial de ejemplo

```java
public class R {

    public double c(
            int h,
            boolean p) {

        if (h <= 0) {
            throw new
                IllegalArgumentException();
        }

        double x = h * 50;

        if (p) {
            x = x * 0.9;
        }

        System.out.println(
            "IMPORTE=" + x
        );

        return x;
    }

    public double c2(
            int h) {

        return h * 50;
    }
}
```

---

# 120. Problemas candidatos

Podemos encontrar:

```text
R
→ nombre poco expresivo

c / c2
→ nombres pobres

h / p / x
→ variables poco expresivas

50
→ número mágico

0.9
→ número mágico

duplicación
→ h * 50

impresión
→ responsabilidad mezclada.
```

---

# 121. Actividad A11.5 — Plan de refactorización

Antes de tocar código completa:

| Problema | Evidencia | Refactor propuesto | Riesgo | Prueba que protege |
|---|---|---|---|---|
| | | | | |

No se permite empezar:

```text
refactorizando al azar.
```

---

# 122. PRÁCTICA EVALUABLE P11.1

# AUDITORÍA Y MEJORA DE CARTAGOQUALITY

**Modalidad:** individual  
**RA:** RA4  
**CE:** RA4.a, b, c, d, e, g  
**Instrumento:** I-RA4-02  

---

# 123. Objetivo

Demostrar que puedes:

```text
analizar código

identificar refactorizaciones

crear/proteger pruebas

configurar el analizador

aplicar refactorizaciones
con el IDE

documentar la API.
```

---

# 124. Estado inicial

El profesor entrega:

```text
CartagoQuality
```

con:

```text
código funcional

suite de pruebas parcial

proyecto Maven

varios problemas
introducidos deliberadamente.
```

---

# 125. Tarea A — Auditoría manual

Sin modificar todavía el proyecto identifica:

```text
mínimo 6 problemas
```

entre:

```text
nombres

duplicación

long method

magic values

responsabilidades

parámetros

condicionales

documentación.
```

Para cada uno propón:

```text
refactorización
```

razonada.

**CE:** RA4.a

---

# 126. Evidencias RA4.a

```text
E-RA4.a-01
Listado de smells.

E-RA4.a-02
Refactor adecuado
por problema.

E-RA4.a-03
Justificación técnica.
```

---

# 127. Tarea B — Estado verde inicial

Ejecuta:

```bash
mvn test
```

y conserva evidencia de:

```text
suite inicial verde.
```

Si no está verde:

```text
informa al profesor
antes de refactorizar.
```

---

# 128. Tarea C — Pruebas de protección

Revisa si existen pruebas para los comportamientos que vas a modificar estructuralmente.

Cuando falte evidencia:

```text
añade prueba
```

antes de refactorizar.

Ejemplos:

```text
tarifa normal

premium

dato inválido.
```

**CE:** RA4.b

---

# 129. Importante

No se evalúa aquí:

```text
“sabe usar @Test”
```

como competencia de RA3.

Se evalúa:

# ¿HA CREADO/SELECCIONADO PRUEBAS QUE PROTEJAN LA REFACTORIZACIÓN?

---

# 130. Tarea D — Secuencia de seguridad

Por cada refactor relevante documenta:

```text
TESTS ANTES
→ verde

REFACTOR
→ herramienta IDE

TESTS DESPUÉS
→ verde
```

---

# 131. Evidencias RA4.b

```text
E-RA4.b-01
Suite verde previa.

E-RA4.b-02
Pruebas asociadas
al comportamiento refactorizado.

E-RA4.b-03
Ejecución tras cada cambio.

E-RA4.b-04
Resultado funcional conservado.
```

---

# 132. Tarea E — Análisis automático

Ejecuta:

```text
Inspect Code
```

sobre:

```text
Whole project
```

o ámbito indicado.

Conserva:

```text
informe inicial.
```

**CE:** RA4.c

---

# 133. Tarea F — Clasificar hallazgos

Selecciona al menos:

```text
5 hallazgos
```

y registra:

| Inspección | Archivo | Severidad | Problema | Decisión |
|---|---|---|---|---|
| | | | | |

Decisión:

```text
corregir

no corregir
con justificación

suprimir
con justificación.
```

---

# 134. Evidencias RA4.c

```text
E-RA4.c-01
Inspect Code ejecutado.

E-RA4.c-02
Informe de resultados.

E-RA4.c-03
Análisis de hallazgos.

E-RA4.c-04
Decisiones justificadas.
```

---

# 135. Tarea G — Perfil de inspección

Crea:

```text
Miralmonte-Quality
```

a partir de un perfil existente.

Modifica al menos:

```text
1 inspección habilitada/deshabilitada

1 severidad

1 opción configurable

1 scope
```

cuando técnicamente proceda.

**CE:** RA4.d

---

# 136. Tarea H — Reanalizar

Ejecuta nuevamente el análisis utilizando:

```text
Miralmonte-Quality.
```

Explica:

```text
qué cambió
en los resultados

y por qué.
```

---

# 137. Evidencias RA4.d

```text
E-RA4.d-01
Perfil creado.

E-RA4.d-02
Inspecciones configuradas.

E-RA4.d-03
Severidad modificada.

E-RA4.d-04
Scope configurado.

E-RA4.d-05
Comparación entre perfiles.
```

---

# 138. Tarea I — Refactorizaciones con IntelliJ

Aplica como mínimo:

```text
Rename

Extract Method

Extract Constant
```

más al menos:

```text
una cuarta operación
```

entre:

```text
Extract Variable

Move

Inline

Change Signature
```

si el proyecto lo permite razonablemente.

**CE:** RA4.e

---

# 139. Regla de evidencia

Debe aparecer:

```text
la herramienta del IDE.
```

No basta entregar únicamente:

```text
código final.
```

---

# 140. Evidencias RA4.e

```text
E-RA4.e-01
Rename mediante IDE.

E-RA4.e-02
Extract Method mediante IDE.

E-RA4.e-03
Extract Constant mediante IDE.

E-RA4.e-04
Refactor adicional.

E-RA4.e-05
Preview/usos afectados.

E-RA4.e-06
Tests verdes posteriores.
```

---

# 141. Tarea J — Reinspección final

Ejecuta:

```text
Inspect Code
```

después de refactorizar.

Compara:

```text
antes

después.
```

No es obligatorio:

```text
cero warnings.
```

Sí es obligatorio:

```text
comprender
qué queda
y por qué.
```

---

# 142. Tarea K — Documentación

Documenta al menos:

```text
2 clases

4 métodos públicos
```

mediante Javadoc.

Incluye cuando proceda:

```text
@param

@return

@throws.
```

**CE:** RA4.g

---

# 143. Tarea L — Generación

Utiliza:

```text
Tools
→ Generate Javadoc
```

y genera:

```text
documentación HTML.
```

Comprueba que:

```text
las clases

métodos

parámetros
```

aparecen correctamente.

---

# 144. Evidencias RA4.g

```text
E-RA4.g-01
Comentarios Javadoc.

E-RA4.g-02
Documentación de clases.

E-RA4.g-03
Documentación de métodos.

E-RA4.g-04
Generate Javadoc.

E-RA4.g-05
HTML generado.
```

---

# 145. Entregable P11.1

```text
P11.1_Apellidos_Nombre.pdf
```

más:

```text
proyecto CartagoQuality
```

cuando la plataforma permita entregarlo.

El PDF debe contener:

1. auditoría manual;
2. smells;
3. propuestas de refactor;
4. pruebas previas;
5. análisis inicial;
6. perfil Miralmonte-Quality;
7. refactorizaciones;
8. pruebas posteriores;
9. análisis final;
10. comparación antes/después;
11. Javadoc;
12. documentación generada;
13. conclusión.

---

# 146. Instrumento I-RA4-02

**RA:** RA4  
**CE:** RA4.a, b, c, d, e, g  
**Actividad:** P11.1  
**Tipo:** auditoría y mejora técnica individual  

Cada CE recibe:

```text
NOTA 0,00–10,00
```

independientemente.

---

# 147. Rúbrica definitiva I-RA4-02

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA4.a** | Identifica refactorizaciones adecuadas ante problemas habituales del código | Confunde refactorización con nueva funcionalidad o propone cambios sin relación con el problema | Reconoce algunos smells y alguna operación de refactorización | Identifica problemas habituales y selecciona correctamente Rename, Extract, Move, Inline u otras operaciones adecuadas | Además compara alternativas y justifica cuándo no conviene aplicar una refactorización | **100 % del CE** |
| **RA4.b** | Elabora y utiliza pruebas asociadas a la refactorización | Refactoriza sin pruebas o las pruebas no protegen el comportamiento afectado | Ejecuta algunas pruebas antes/después con cobertura limitada | Selecciona o crea pruebas relevantes antes de refactorizar y demuestra que continúan pasando después | Además construye una red de seguridad especialmente precisa, relacionando cada refactor con los comportamientos protegidos | **100 % del CE** |
| **RA4.c** | Revisa el código fuente mediante un analizador | No ejecuta un análisis útil o interpreta incorrectamente los resultados | Ejecuta inspecciones y reconoce algunos problemas con ayuda | Ejecuta Inspect Code sobre un ámbito definido, interpreta los hallazgos y decide razonadamente su tratamiento | Además distingue problemas relevantes de ruido, analiza causas y compara de forma rigurosa el estado antes/después | **100 % del CE** |
| **RA4.d** | Identifica y utiliza posibilidades de configuración del analizador | Usa únicamente el perfil predeterminado sin comprender configuración | Modifica alguna inspección o severidad con ayuda | Crea/configura un perfil, habilita reglas, modifica severidad, ámbito y opciones pertinentes | Además justifica una configuración coherente para el proyecto y explica el impacto de cada decisión | **100 % del CE** |
| **RA4.e** | Aplica refactorizaciones mediante herramientas del IDE | Modifica manualmente el código sin utilizar las herramientas requeridas o altera comportamiento | Utiliza alguna refactorización asistida con ayuda | Aplica correctamente varias refactorizaciones del IDE manteniendo el comportamiento protegido por pruebas | Además utiliza preview/conflict detection, ejecuta cambios pequeños y justifica con precisión cada transformación | **100 % del CE** |
| **RA4.g** | Utiliza herramientas del entorno para documentar clases | Añade comentarios insuficientes o no genera documentación | Escribe Javadoc básico y genera parcialmente documentación | Documenta correctamente clases/métodos y genera la referencia HTML mediante la herramienta del entorno | Además produce una API clara, evita comentarios redundantes y documenta contratos, excepciones y restricciones con precisión | **100 % del CE** |

---

# 148. PRÁCTICA EVALUABLE P11.2

# INTEGRACIÓN CONTINUA DE CARTAGOQUALITY

**Modalidad:** individual  
**RA:** RA4  
**CE:** RA4.i  
**Instrumento:** I-RA4-03  

---

# 149. Objetivo

Convertir:

```text
mvn verify
```

de una acción:

```text
manual
```

en:

```text
una verificación automática
en GitHub
ante cambios
del repositorio.
```

---

# 150. Requisito previo

El proyecto debe:

```text
compilar localmente

tener tests

pasar:
mvn --batch-mode verify
```

antes de crear el workflow.

---

# 151. Tarea A — Ejecución local

Ejecuta:

```bash
mvn --batch-mode verify
```

Conserva:

```text
BUILD SUCCESS.
```

Si falla localmente:

```text
no pases todavía a CI.
```

---

# 152. Tarea B — Workflow

Crea:

```text
.github/workflows/ci.yml
```

con:

```yaml
name: CartagoQuality CI

on:
  push:
    branches:
      - main

  pull_request:
    branches:
      - main

jobs:
  build:

    runs-on: ubuntu-latest

    steps:

      - name: Checkout repository
        uses: actions/checkout@v7

      - name: Set up Temurin 25
        uses: actions/setup-java@v6
        with:
          distribution: temurin
          java-version: '25'
          cache: maven

      - name: Verify project
        run: mvn --batch-mode verify
```

---

# 153. Tarea C — Primera ejecución

Publica el workflow mediante el flujo Git ya conocido.

Debes demostrar:

```text
workflow detectado

ejecución automática

checkout

Java 25

Maven verify

resultado verde.
```

**CE:** RA4.i

---

# 154. Tarea D — Fallo deliberado

Introduce un cambio controlado que provoque:

```text
un test fallido
```

sin destruir el proyecto.

Publica el cambio.

Debes obtener:

```text
workflow rojo.
```

---

# 155. Tarea E — Diagnóstico

Abre:

```text
Actions
→ workflow
→ job
→ step
```

y localiza:

```text
test que falla

expected

actual

causa.
```

---

# 156. Tarea F — Corrección

Restaura/corrige el defecto.

Publica el nuevo cambio.

Resultado esperado:

```text
workflow verde.
```

---

# 157. Tarea G — Pull Request

Crea una pequeña modificación en una rama y una Pull Request.

Comprueba que:

```text
el workflow
se ejecuta automáticamente
también sobre la PR.
```

No se vuelve a evaluar:

```text
crear la rama

crear la PR.
```

Se evalúa:

```text
que CI
reacciona al evento.
```

---

# 158. Tarea H — Explicación técnica

Responde:

1. ¿Qué activa el workflow?
2. ¿Dónde se ejecuta?
3. ¿Para qué sirve checkout?
4. ¿Para qué sirve setup-java?
5. ¿Qué versión de Java utiliza?
6. ¿Qué hace `cache: maven`?
7. ¿Qué ejecuta `mvn verify`?
8. ¿Qué diferencia existe entre `mvn test` local y CI?
9. ¿Por qué un workflow rojo es útil?
10. ¿Qué evidencia demuestra realmente RA4.i?

---

# 159. Evidencias RA4.i

```text
E-RA4.i-01
Workflow YAML.

E-RA4.i-02
Trigger push.

E-RA4.i-03
Trigger pull_request.

E-RA4.i-04
Temurin 25 configurado.

E-RA4.i-05
Maven verify ejecutado.

E-RA4.i-06
Workflow verde.

E-RA4.i-07
Fallo deliberado detectado.

E-RA4.i-08
Diagnóstico del log.

E-RA4.i-09
Nueva ejecución verde.

E-RA4.i-10
CI en Pull Request.
```

---

# 160. Entregable P11.2

```text
P11.2_Apellidos_Nombre.pdf
```

más:

```text
ci.yml
```

y referencia al:

```text
repositorio utilizado
```

cuando proceda.

Debe incluir:

1. ejecución local;
2. workflow;
3. configuración Java;
4. ejecución verde;
5. fallo deliberado;
6. log del fallo;
7. corrección;
8. nueva ejecución verde;
9. ejecución sobre PR;
10. explicación técnica.

---

# 161. Instrumento I-RA4-03

**RA:** RA4  
**CE:** RA4.i  
**Actividad:** P11.2  
**Tipo:** laboratorio de integración continua individual

---

# 162. Rúbrica definitiva I-RA4-03

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA4.i** | Utiliza herramientas de integración continua para verificar automáticamente el código | El workflow no funciona, se ejecuta solo manualmente o no realiza una verificación real del proyecto | Crea un workflow básico que ejecuta parcialmente el proyecto con ayuda | Configura GitHub Actions para `push` y `pull_request`, prepara Temurin 25 y ejecuta `mvn verify`, interpretando correctamente éxito y fallo | Además demuestra fallo/corrección de forma reproducible, interpreta logs con autonomía y explica claramente la diferencia entre ejecución local, automatización de pruebas e integración continua | **100 % del CE** |

---

# 163. Temporalización definitiva

| Sesión | Contenido | Actividades |
|---:|---|---|
| 1 | Calidad, smells y concepto de refactorización | A11.1 |
| 2 | Rename, Extract y constantes | laboratorio |
| 3 | Move, Inline, Change Signature y estrategia | A11.2 |
| 4 | Pruebas como red de seguridad | refactor protegido |
| 5 | Analizadores de código e Inspect Code | A11.3 |
| 6 | Perfiles, severidad, scopes y configuración | perfil Miralmonte-Quality |
| 7 | P11.1 — auditoría inicial | I-RA4-02 |
| 8 | P11.1 — refactorizaciones | I-RA4-02 |
| 9 | Javadoc y documentación de API | A11.4 |
| 10 | P11.1 — documentación y análisis final | I-RA4-02 |
| 11 | Integración continua y GitHub Actions | workflow guiado |
| 12 | Temurin 25 + Maven verify en CI | laboratorio |
| 13 | P11.2 — workflow funcional | I-RA4-03 |
| 14 | P11.2 — fallo, diagnóstico y corrección | I-RA4-03 |
| 15 | PR + CI, evidencias y cierre de RA4 | I-RA4-03 |

**Total: 15 periodos.**

---

# 164. Ejercicios de consolidación

1. ¿Qué significa refactorizar?
2. ¿Cambia una refactorización el comportamiento esperado?
3. ¿Qué es un code smell?
4. Pon tres ejemplos de smells.
5. ¿Para qué sirve Rename?
6. ¿Para qué sirve Extract Method?
7. ¿Para qué sirve Extract Constant?
8. ¿Cuándo podría utilizarse Move?
9. ¿Qué hace Change Signature?
10. ¿Cuándo podría utilizarse Inline?
11. ¿Por qué necesitamos pruebas antes de refactorizar?
12. ¿Qué significa test verde → refactor → test verde?
13. ¿Qué es un analizador estático?
14. ¿Qué hace Inspect Code?
15. ¿Qué es un inspection profile?
16. Diferencia perfil global y de proyecto.
17. ¿Qué es severidad?
18. ¿Qué es un scope?
19. ¿Por qué no debemos aceptar todos los quick-fixes automáticamente?
20. ¿Qué significa suprimir una inspección?
21. ¿Qué es Javadoc?
22. ¿Para qué sirven `@param`, `@return` y `@throws`?
23. ¿Qué genera Tools → Generate Javadoc?
24. ¿Qué significa CI?
25. Diferencia automatización local y CI.
26. ¿Qué es un workflow?
27. ¿Qué representa `on:`?
28. ¿Qué hace `actions/checkout`?
29. ¿Qué hace `actions/setup-java`?
30. ¿Qué versión Java utiliza el workflow?
31. ¿Qué hace `mvn verify`?
32. ¿Qué significa workflow verde?
33. ¿Qué significa workflow rojo?
34. ¿Por qué ejecutamos CI en Pull Requests?
35. ¿Se evalúa de nuevo Git en esta unidad?

---

# 165. Autoevaluación

### 1

Refactorizar significa:

A. mejorar estructura preservando comportamiento  
B. añadir siempre nuevas funciones  
C. borrar tests  
D. crear UML

### 2

Extract Method sirve para:

A. extraer parte del código a un método  
B. eliminar Git  
C. crear Javadoc  
D. instalar Java

### 3

Antes de refactorizar conviene:

A. tener pruebas relevantes verdes  
B. borrar los tests  
C. ignorar errores previos  
D. cambiar todo de golpe

### 4

Inspect Code:

A. analiza el código  
B. crea repositorios  
C. ejecuta Git  
D. genera diagramas

### 5

Un perfil de inspección puede configurar:

A. reglas, severidad y ámbitos  
B. únicamente el tema visual  
C. la contraseña de GitHub  
D. el JDK del sistema operativo

### 6

Javadoc permite:

A. generar documentación de API  
B. crear tests unitarios  
C. hacer commits  
D. generar UML

### 7

CI significa:

A. Continuous Integration  
B. Code Installation  
C. Class Inspection  
D. Continuous Interface

### 8

`actions/setup-java`:

A. configura Java en el runner  
B. genera UML  
C. hace refactor  
D. crea Javadoc

### 9

`mvn verify` en el workflow:

A. verifica el proyecto mediante Maven  
B. abre IntelliJ  
C. crea una rama  
D. modifica el código

### 10

RA4.f y RA4.h:

A. ya fueron evaluados en UD05  
B. se vuelven a evaluar en UD11  
C. pertenecen a RA3  
D. pertenecen a RA6

---

# 166. Soluciones

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

# PARTE B — MATERIAL DEL PROFESOR

# 167. Finalidad docente

La unidad debe integrar:

```text
ANÁLISIS

PRUEBAS

REFACTOR

DOCUMENTACIÓN

AUTOMATIZACIÓN
```

en un único flujo de mantenimiento profesional.

El alumno debe abandonar la idea:

```text
“si funciona,
no lo toques”
```

y sustituirla por:

```text
“si funciona
pero es difícil de mantener,
puedo mejorarlo
de forma controlada”.
```

---

# 168. RA4.a vs RA4.e

Muy importante.

## RA4.a

Pregunta:

```text
¿identifica
qué refactorización
sería adecuada?
```

## RA4.e

Pregunta:

```text
¿la aplica
con herramientas
del entorno?
```

Un alumno puede:

```text
entender perfectamente
qué debería hacer
```

pero utilizar mal IntelliJ.

Son CE distintos.

---

# 169. RA4.b

No debe convertirse en:

```text
repetición de UD10.
```

La pregunta no es:

```text
¿sabe JUnit?
```

sino:

```text
¿protege el comportamiento
que va a refactorizar?
```

---

# 170. Evidencia fuerte de RA4.b

Tabla:

| Refactor | Comportamiento protegido | Test previo | Antes | Después |
|---|---|---|---|---|
| Rename | cálculo premium | `aplicaPremium()` | PASS | PASS |
| Extract Method | validación | `rechazaCero()` | PASS | PASS |

---

# 171. RA4.c vs RA4.d

## RA4.c

```text
USAR analizador
e interpretar resultados.
```

## RA4.d

```text
CONFIGURAR analizador.
```

No mezclar la nota.

---

# 172. IntelliJ 2026.2 — Inspections

La documentación actual confirma:

```text
analiza código en el editor

permite Inspect Code

permite scope

permite profile

genera informe de problemas.
```


---

# 173. Perfiles

Los perfiles actuales pueden almacenarse:

```text
en IDE

o

en proyecto.
```

Los perfiles de proyecto permiten compartir una configuración con el propio proyecto.

---

# 174. No exigir “cero problemas”

Proyecto con:

```text
0 warnings
```

no implica automáticamente:

```text
código perfecto.
```

Se valora:

```text
interpretación

priorización

decisión razonada.
```

---

# 175. RA4.e — mínimo técnico

Exigir al menos:

```text
Rename

Extract Method

Extract Constant

+ una cuarta refactorización.
```

Si el proyecto no justifica:

```text
Move
```

no debe forzarse artificialmente.

Puede utilizarse:

```text
Extract Variable

Inline

Change Signature.
```

---

# 176. IntelliJ y refactor

IntelliJ 2026.2 mantiene:

```text
Rename

Extract Method

Extract Constant

Extract Variable

Move

Inline

Change Signature

Safe Delete
```

entre sus refactorizaciones principales.

---

# 177. RA4.g

No evaluar:

```text
cantidad de comentarios.
```

Evaluar:

```text
documentación útil

uso de herramienta

generación correcta.
```

---

# 178. Javadoc actual

IntelliJ 2026.2 puede:

```text
crear stubs

detectar problemas

mostrar Javadoc

generar referencia HTML.
```


---

# 179. Markdown Javadoc

Desde Java 23 Javadoc admite también comentarios con sintaxis Markdown.

No será necesario exigir:

```text
este formato nuevo.
```

Utilizaremos sintaxis tradicional:

```java
/**
 * ...
 */
```

para mantener uniformidad didáctica.

---

# 180. RA4.i

Debe quedar claramente separado de:

```text
RA3.g.
```

## RA3.g

```text
automatización de pruebas.
```

## RA4.i

```text
integración continua
del código.
```

La prueba diferencial:

```text
evento remoto
→ runner
→ build/test
→ resultado automático.
```

---

# 181. Herramienta CI

Adoptamos:

# GitHub Actions.

GitHub documenta específicamente su uso como CI para construir y probar proyectos Java/Maven.

---

# 182. Versiones de actions

Para el material 2026/27 queda fijado:

```text
actions/checkout@v7

actions/setup-java@v6
```

El repositorio oficial actual de `setup-java` utiliza ambas versiones en sus ejemplos y marca v6 como versión estable actual.

---

# 183. Java CI

Configuración:

```yaml
with:
  distribution: temurin
  java-version: '25'
```

coincide con:

```text
el estándar Miralmonte.
```

---

# 184. Maven

Comando:

```bash
mvn --batch-mode verify
```

es apropiado porque:

```text
reproduce en CI
la verificación Maven
del proyecto.
```

---

# 185. Qué no exigir en CI

No exigir:

```text
Docker

deployment

Kubernetes

multi-platform matrix

secrets complejos

publicación Maven Central

coverage services

SonarCloud.
```

No son necesarios para RA4.i.

---

# 186. Fallo deliberado

Debe existir una ejecución:

```text
verde
```

y otra:

```text
roja.
```

Así el alumno demuestra que:

```text
CI no es solo
un icono verde,
```

sino una herramienta capaz de:

```text
detectar regresiones.
```

---

# 187. Seguridad

No incluir:

```text
tokens

passwords

credenciales
```

en el YAML.

Para este workflow:

```text
no necesitamos secretos.
```

---

# 188. Capturas definitivas previstas

```text
CAPTURA UD11-01
Inspect Code

CAPTURA UD11-02
Inspection Profile

CAPTURA UD11-03
Inspection Results

CAPTURA UD11-04
Refactor This

CAPTURA UD11-05
Refactoring Preview

CAPTURA UD11-06
Generate Javadoc

CAPTURA UD11-07
Javadoc HTML

CAPTURA UD11-08
GitHub Actions run

CAPTURA UD11-09
Job / Maven verify

CAPTURA UD11-10
PR con check CI
```

---

# 189. Medidas de apoyo

Puede proporcionarse:

```text
proyecto inicial

suite de pruebas base

lista de smells de entrenamiento

perfil de ejemplo distinto

plantilla de Javadoc

workflow de entrenamiento
de otro proyecto.
```

No proporcionar:

```text
lista exacta
de todos los smells
de CartagoQuality

ni

la solución final
de refactorización.
```

---

# 190. Plantilla de auditoría

| ID | Problema | Evidencia | Refactor | Prueba protectora | Resultado |
|---|---|---|---|---|---|
| | | | | | |

---

# 191. Plantilla de inspección

| ID | Inspection | Severidad | Archivo | Decisión | Justificación |
|---|---|---|---|---|---|
| | | | | | |

---

# 192. Plantilla de CI

| Evento | Ejecución | Resultado | Step que falla | Causa |
|---|---|---|---|---|
| push | | | | |
| PR | | | | |

---

# 193. Ampliación

Alumnado avanzado puede investigar:

```text
Safe Delete

Extract Interface

Extract Superclass

Code Cleanup

inspection CLI

matrices CI

artifacts

branch protection

required checks.
```

Sin añadir nuevos CE.

---

# 194. Recuperación

Instrumento:

# IR-RA4-01

Bloques de UD11:

```text
RA4.a

RA4.b

RA4.c

RA4.d

RA4.e

RA4.g

RA4.i.
```

---

# 195. Ejemplo

Resultados:

```text
a = 7
b = 6
c = 4
d = 3
e = 7
f = 8
g = 6
h = 8
i = 4
```

Si RA4 no queda superado y precisa nueva evidencia de:

```text
RA4.d

RA4.i
```

se asignan:

```text
solo esos bloques.
```

RA4.f/h ya superados:

```text
se conservan.
```

---

# 196. Trazabilidad UD11

| RA | CE | Contenido | Actividad | Instrumento | Evidencias |
|---|---|---|---|---|---|
| RA4 | a | identificación de refactorizaciones | A11.1 / P11.1 | I-RA4-02 | E-RA4.a-01/03 |
| RA4 | b | pruebas asociadas a refactor | A11.2 / P11.1 | I-RA4-02 | E-RA4.b-01/04 |
| RA4 | c | análisis estático | A11.3 / P11.1 | I-RA4-02 | E-RA4.c-01/04 |
| RA4 | d | configuración del analizador | A11.3 / P11.1 | I-RA4-02 | E-RA4.d-01/05 |
| RA4 | e | refactorización asistida | P11.1 | I-RA4-02 | E-RA4.e-01/06 |
| RA4 | g | Javadoc | A11.4 / P11.1 | I-RA4-02 | E-RA4.g-01/05 |
| RA4 | i | integración continua | P11.2 | I-RA4-03 | E-RA4.i-01/10 |

---

# 197. Situación completa de RA4

UD05:

```text
RA4.f ✔

RA4.h ✔
```

UD11:

```text
RA4.a ✔
RA4.b ✔
RA4.c ✔
RA4.d ✔
RA4.e ✔
RA4.g ✔
RA4.i ✔
```

Resultado:

# RA4 COMPLETAMENTE CUBIERTO.

---

# 198. Cálculo definitivo RA4

RA4 contiene:

```text
9 CE.
```

Todos tienen:

```text
peso 1/9.
```

Por tanto:

```text
RA4 =
(
 a+b+c+d+e+f+g+h+i
) / 9
```

---

# 199. Distribución de instrumentos

```text
I-RA4-01
→ RA4.f + RA4.h

I-RA4-02
→ RA4.a + b + c + d + e + g

I-RA4-03
→ RA4.i
```

Ningún instrumento:

```text
mezcla RA.
```

---

# 200. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA4

**CE evaluados:**

```text
RA4.a
RA4.b
RA4.c
RA4.d
RA4.e
RA4.g
RA4.i
```

### ¿Se utilizan pruebas?

Sí.

Como:

```text
red de seguridad
de refactorización.
```

# RA3 NO SE RECALIFICA.

### ¿Se utiliza Git?

Sí, para:

```text
publicar workflow

activar CI

trabajar sobre PR.
```

# RA4.f NO SE RECALIFICA.

### ¿Se utiliza repositorio remoto?

Sí.

Como:

```text
infraestructura
de GitHub Actions.
```

# RA4.h NO SE RECALIFICA.

### ¿Se evalúa despliegue?

# NO.

### ¿Se evalúa UML?

# NO.

### ¿Se evalúa arquitectura avanzada?

# NO.

### ¿Algún instrumento evalúa otro RA?

# NO.

```text
I-RA4-02
→ exclusivamente RA4

I-RA4-03
→ exclusivamente RA4.
```

---

# 201. Checklist final UD11

```text
☑ 15 periodos.

☑ RA4 único.

☑ RA4.a oficial.

☑ RA4.b oficial.

☑ RA4.c oficial.

☑ RA4.d oficial.

☑ RA4.e oficial.

☑ RA4.g oficial.

☑ RA4.i oficial.

☑ RA4.f/h no recalificados.

☑ Concepto de refactorización.

☑ Refactor ≠ funcionalidad.

☑ Code smells.

☑ Nombres pobres.

☑ Métodos largos.

☑ Duplicación.

☑ Magic values.

☑ Responsabilidades.

☑ Rename.

☑ Extract Method.

☑ Extract Variable.

☑ Extract Constant.

☑ Move.

☑ Inline.

☑ Change Signature.

☑ Refactorización asistida.

☑ Preview.

☑ Pruebas protectoras.

☑ Test verde → refactor → test verde.

☑ Inspect Code.

☑ Inspections.

☑ Inspection Profile.

☑ Severidad.

☑ Scope.

☑ Configuración del analizador.

☑ Quick-fix contextualizado.

☑ Reinspección final.

☑ Javadoc.

☑ @param.

☑ @return.

☑ @throws.

☑ Generate Javadoc.

☑ HTML generado.

☑ CI.

☑ Automatización local ≠ CI.

☑ GitHub Actions.

☑ workflow YAML.

☑ push trigger.

☑ pull_request trigger.

☑ actions/checkout@v7.

☑ actions/setup-java@v6.

☑ Temurin 25.

☑ Maven cache.

☑ mvn --batch-mode verify.

☑ Ejecución verde.

☑ Fallo deliberado.

☑ Diagnóstico.

☑ Recuperación verde.

☑ CI sobre PR.

☑ CartagoQuality.

☑ P11.1.

☑ P11.2.

☑ I-RA4-02.

☑ I-RA4-03.

☑ 7 CE con nota propia 0–10.

☑ Rúbricas armonizadas.

☑ Evidencias codificadas.

☑ 10 capturas previstas.

☑ Consolidación.

☑ Ampliación.

☑ Autoevaluación.

☑ Resumen.

☑ Glosario.

☑ Material profesor.

☑ Recuperación modular.

☑ Trazabilidad completa.

☑ Aislamiento superado.

☑ RA4 cerrado.
```

# UD11 — VERSIÓN MAESTRA DEFINITIVA