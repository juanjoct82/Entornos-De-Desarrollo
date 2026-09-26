# UD10 — PRUEBAS UNITARIAS, AUTOMATIZACIÓN Y DOBLES DE PRUEBA

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 11 periodos lectivos  
**Resultado de Aprendizaje:** RA3  
**Práctica evaluable:** P10.1  
**Instrumento:** I-RA3-02  

**Lenguaje:** Java  
**JDK:** Eclipse Temurin JDK 25 LTS  
**IDE:** IntelliJ IDEA 2026.2  
**Gestión del proyecto:** Maven  
**Framework de pruebas:** JUnit 6.1.3  
**Dobles de prueba:** Mockito 5.24.0  
**Ejecución automática:** Maven Surefire 3.6.0  

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

En UD09 aprendimos a:

```text
diseñar casos de prueba

definir resultados esperados

utilizar valores límite

depurar

localizar defectos
```

Pero ejecutar manualmente:

```text
CP01

CP02

CP03

CP04

...
```

cada vez que modificamos el programa resulta poco eficiente.

Nuestro siguiente objetivo será convertir las comprobaciones en código:

```text
CÓDIGO DE PRODUCCIÓN
        +
CÓDIGO DE PRUEBA
        ↓
COMPROBACIÓN AUTOMÁTICA
```

Además aprenderemos a probar clases que dependen de:

```text
bases de datos

servicios

repositorios

notificaciones

sistemas externos
```

sin necesitar que todos esos componentes funcionen realmente.

---

# 2. Resultado de Aprendizaje

## RA3

**Verifica el funcionamiento de programas diseñando y realizando pruebas.**

---

# 3. Criterios de evaluación

En UD10 se evalúan exclusivamente:

## RA3.f

**Se han efectuado pruebas unitarias de clases y funciones.**

## RA3.g

**Se han implementado pruebas automáticas.**

## RA3.h

**Se han documentado las incidencias detectadas.**

## RA3.i

**Se han utilizado dobles de prueba para aislar los componentes durante las pruebas.**

Estas son las formulaciones oficiales vigentes del RD 405/2023.

---

# 4. CE reforzado pero no recalificado

Para escribir buenas pruebas seguiremos necesitando:

```text
casos de prueba

entradas

resultados esperados

valores límite

clases de equivalencia
```

Esto pertenece a:

```text
RA3.b
```

que ya fue evaluado en UD09.

En UD10:

# RA3.b SE REUTILIZA, PERO NO SE VUELVE A CALIFICAR.

---

# 5. ¿Qué aprenderemos?

Al finalizar la unidad deberás poder:

- explicar qué es una prueba unitaria;
- distinguir código de producción y código de prueba;
- preparar un proyecto Maven para testing;
- utilizar JUnit;
- escribir métodos `@Test`;
- utilizar assertions;
- comprobar excepciones;
- preparar datos antes de cada prueba;
- aplicar el patrón Arrange–Act–Assert;
- crear pruebas parametrizadas;
- ejecutar una clase de pruebas;
- ejecutar toda la suite;
- interpretar resultados PASSED/FAILED;
- ejecutar pruebas desde IntelliJ;
- ejecutar automáticamente las pruebas mediante Maven;
- comprender el papel de Surefire;
- registrar una incidencia reproducible;
- relacionar una incidencia con una prueba que la detecta;
- distinguir dummy, stub, fake, spy y mock;
- utilizar Mockito para crear dobles;
- programar comportamiento mediante `when`;
- verificar interacciones mediante `verify`;
- aislar una unidad de sus dependencias;
- reconocer por qué una prueba unitaria no debe depender innecesariamente de sistemas externos.

---

# 6. Herramientas utilizadas

Utilizaremos:

```text
JUnit 6.1.3

Mockito 5.24.0

Maven

Surefire 3.6.0

IntelliJ IDEA 2026.2
```

JUnit 6.1.3 incluye JUnit Platform y JUnit Jupiter, y requiere Java 17 o superior, por lo que Temurin 25 es plenamente compatible.

---

# 7. Maven y estructura del proyecto

Un proyecto Maven habitual separa:

```text
src/
├── main/
│   └── java/
│
└── test/
    └── java/
```

Por tanto:

```text
src/main/java
```

contiene:

# CÓDIGO DE PRODUCCIÓN

y:

```text
src/test/java
```

contiene:

# CÓDIGO DE PRUEBA.

---

# 8. Dependencia de JUnit

Configuración base:

```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter</artifactId>
    <version>6.1.3</version>
    <scope>test</scope>
</dependency>
```

`scope=test` significa que JUnit:

```text
se utiliza durante las pruebas
```

pero no forma parte normalmente de:

```text
la aplicación final.
```

La documentación oficial de JUnit mantiene `org.junit.jupiter:junit-jupiter:6.1.3` como artefacto agregador recomendado para trabajar con Jupiter.

---

# 9. Maven Surefire

Añadiremos:

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-surefire-plugin</artifactId>
    <version>3.6.0</version>
</plugin>
```

Surefire ejecuta las pruebas unitarias durante la fase Maven:

```text
test
```

y su versión estable actual es 3.6.0.

---

# 10. Configuración base

Ejemplo simplificado:

```xml
<properties>
    <maven.compiler.release>25</maven.compiler.release>
    <project.build.sourceEncoding>
        UTF-8
    </project.build.sourceEncoding>
</properties>

<dependencies>

    <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter</artifactId>
        <version>6.1.3</version>
        <scope>test</scope>
    </dependency>

</dependencies>

<build>

    <plugins>

        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>
                maven-surefire-plugin
            </artifactId>
            <version>3.6.0</version>
        </plugin>

    </plugins>

</build>
```

---

# 11. IntelliJ y JUnit

IntelliJ IDEA permite:

```text
crear clases de test

ejecutar un test

ejecutar una clase

ejecutar todos los tests

ver resultados

volver directamente
al código que falla.
```

IntelliJ 2026.2 mantiene soporte directo para JUnit y proyectos Maven.

---

# 12. CAPTURA UD10-01 — Estructura Maven

Debe mostrar:

```text
src/main/java

src/test/java

pom.xml
```

con el proyecto abierto en IntelliJ.

---

# 13. ¿Qué es una prueba unitaria?

Una prueba unitaria verifica:

```text
una unidad pequeña
del software
```

como:

```text
método

función

clase
```

de manera:

```text
rápida

repetible

aislada
```

cuando sea posible.

---

# 14. Ejemplo

Código de producción:

```java
public class Calculadora {

    public int sumar(int a, int b) {
        return a + b;
    }
}
```

Prueba:

```java
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.*;

class CalculadoraTest {

    @Test
    void sumaDosNumeros() {

        Calculadora calculadora =
                new Calculadora();

        int resultado =
                calculadora.sumar(2, 3);

        assertEquals(
                5,
                resultado
        );
    }
}
```

---

# 15. `@Test`

La anotación:

```java
@Test
```

indica que el método representa:

```text
una prueba
ejecutable por JUnit.
```

---

# 16. Assertion

Una assertion comprueba una expectativa.

Ejemplo:

```java
assertEquals(
        esperado,
        obtenido
);
```

Si:

```text
esperado == obtenido
```

la comprobación pasa.

Si no:

# FALLA.

---

# 17. La prueba no imprime para comprobar

Mala prueba:

```java
System.out.println(resultado);
```

y después:

> Parece correcto.

Mejor:

```java
assertEquals(
        12.0,
        resultado
);
```

La decisión:

```text
PASA / FALLA
```

queda automatizada.

---

# 18. Assertions habituales

Trabajaremos principalmente con:

```java
assertEquals()

assertTrue()

assertFalse()

assertNull()

assertNotNull()

assertThrows()
```

No necesitamos memorizar toda la API.

---

# 19. Ejemplo booleano

```java
assertTrue(
        usuario.esMayorDeEdad()
);
```

---

# 20. Ejemplo nulo

```java
assertNotNull(
        reserva
);
```

---

# 21. Comprobar excepciones

Si esperamos:

```java
IllegalArgumentException
```

podemos escribir:

```java
assertThrows(
    IllegalArgumentException.class,
    () -> servicio.reservar(0)
);
```

Esto convierte:

```text
“el método debe rechazar 0”
```

en:

# UNA COMPROBACIÓN AUTOMÁTICA.

---

# 22. Arrange – Act – Assert

Organizaremos muchas pruebas mediante:

```text
ARRANGE

ACT

ASSERT
```

o:

```text
PREPARAR

EJECUTAR

COMPROBAR.
```

---

# 23. Ejemplo AAA

```java
@Test
void aplicaDescuentoPremium() {

    // Arrange
    TarifaReserva tarifa =
            new TarifaReserva();

    // Act
    double resultado =
            tarifa.calcular(
                    2,
                    true
            );

    // Assert
    assertEquals(
            90.0,
            resultado
    );
}
```

---

# 24. Una prueba debe tener intención clara

Nombre poco útil:

```java
test1()
```

Mejor:

```java
calculaPrecioSinDescuento()
```

o:

```java
rechazaNumeroDeNochesNoValido()
```

El nombre debe ayudar a comprender:

```text
qué comportamiento
estamos comprobando.
```

---

# 25. Un comportamiento por prueba

No es obligatorio que:

```text
una prueba
=
una única assertion
```

pero conviene que una prueba represente:

```text
un comportamiento
coherente.
```

---

# 26. Pruebas independientes

Debemos evitar que:

```text
Test B
```

solo funcione después de:

```text
Test A.
```

La suite debe poder ejecutar:

```text
en cualquier orden
```

sin depender de resultados anteriores.

---

# 27. `@BeforeEach`

Cuando varias pruebas necesitan la misma preparación:

```java
@BeforeEach
void preparar() {
    tarifa =
            new TarifaReserva();
}
```

JUnit ejecuta esa preparación:

```text
antes de cada prueba.
```

---

# 28. Ejemplo

```java
class TarifaReservaTest {

    private TarifaReserva tarifa;

    @BeforeEach
    void preparar() {

        tarifa =
                new TarifaReserva();
    }

    @Test
    void calculaUnaNoche() {

        assertEquals(
                50.0,
                tarifa.calcular(
                        1,
                        false
                )
        );
    }
}
```

---

# 29. Evitar estado compartido accidental

Si una prueba modifica:

```text
una lista

un objeto

un contador
```

y ese mismo estado llega a otra prueba:

```text
el resultado puede depender
del orden.
```

Una buena suite debe minimizar:

# ACOPLAMIENTO ENTRE PRUEBAS.

---

# 30. Pruebas parametrizadas

Supongamos que queremos comprobar:

```text
1 noche → 50 €

2 noches → 100 €

3 noches → 150 €

4 noches → 200 €
```

Podríamos crear cuatro métodos.

También podemos utilizar:

```java
@ParameterizedTest
```

---

# 31. `@CsvSource`

Ejemplo:

```java
@ParameterizedTest
@CsvSource({
    "1, 50.0",
    "2, 100.0",
    "3, 150.0",
    "4, 200.0"
})
void calculaTarifaNormal(
        int noches,
        double esperado) {

    assertEquals(
            esperado,
            tarifa.calcular(
                    noches,
                    false
            )
    );
}
```

---

# 32. Relación con RA3.b

Los valores:

```text
1

2

3

4
```

siguen siendo:

```text
casos de prueba.
```

El diseño conceptual fue evaluado en UD09.

Aquí aprendemos:

# A CODIFICARLOS Y EJECUTARLOS AUTOMÁTICAMENTE.

---

# 33. CAPTURA UD10-02 — JUnit

Debe mostrar:

```text
clase de pruebas

@Test

resultado verde/rojo
```

en IntelliJ.

---

# 34. CAPTURA UD10-03 — Parameterized Test

Debe mostrar:

```text
@ParameterizedTest

varias ejecuciones
del mismo método
```

con sus resultados.

---

# 35. ¿Qué significa prueba automática?

Una prueba automática puede ejecutarse:

```text
sin que una persona
tenga que comprobar
manualmente
cada resultado.
```

Ejemplo:

```bash
mvn test
```

puede ejecutar:

```text
10

50

500

pruebas
```

y devolver:

```text
BUILD SUCCESS
```

o:

```text
BUILD FAILURE.
```

---

# 36. RA3.f vs RA3.g

Es una diferencia muy importante.

## RA3.f

Pregunta:

```text
¿sabe construir
pruebas unitarias
de clases y funciones?
```

## RA3.g

Pregunta:

```text
¿ha implementado
un mecanismo que permita
ejecutarlas automáticamente?
```

Una misma suite contribuye a ambos CE, pero:

# LA EVIDENCIA ES DIFERENTE.

---

# 37. Maven como automatizador

Al ejecutar:

```bash
mvn test
```

Maven:

```text
localiza pruebas

prepara dependencias

ejecuta Surefire

ejecuta JUnit

recoge resultados

devuelve éxito o fallo.
```

Surefire se enlaza por defecto con la fase `test` del ciclo Maven.

---

# 38. Automatización local ≠ integración continua

En UD10 ejecutaremos automáticamente:

```text
mvn test
```

en nuestro equipo.

Eso es:

# AUTOMATIZACIÓN DE PRUEBAS.

No es todavía:

```text
integración continua.
```

---

# 39. CONOCIMIENTO AUXILIAR NO EVALUADO

La ejecución automática de pruebas en:

```text
GitHub Actions

servidor CI

pipeline
```

pertenece evaluativamente a:

```text
RA4.i
→ UD11.
```

En UD10:

# NO SE EVALÚA CI.

---

# 40. CAPTURA UD10-04 — Maven test

Debe mostrar:

```bash
mvn test
```

y:

```text
Tests run

Failures

Errors

Skipped

BUILD SUCCESS
```

o el fallo provocado deliberadamente.

---

# 41. Una automatización debe ser repetible

Idealmente otra persona puede ejecutar:

```bash
mvn test
```

sobre el proyecto y obtener:

```text
la misma suite

las mismas reglas

los mismos resultados
```

si parte del mismo código.

---

# 42. Pruebas rápidas

Las pruebas unitarias deberían poder ejecutarse:

```text
con frecuencia.
```

Si cada prueba necesita:

```text
5 minutos

Internet real

una base de datos remota

un pago real
```

dejan de ser pruebas unitarias cómodas.

---

# 43. Aislamiento

Queremos probar:

```text
ReservaService
```

sin necesitar necesariamente:

```text
servidor de correo real

base de datos real

API externa real.
```

Aquí aparecen los:

# DOBLES DE PRUEBA.

---

# 44. Incidencias

Una prueba automática puede descubrir:

```text
un fallo.
```

Pero el equipo necesita poder responder:

```text
¿Qué ocurrió?

¿Cómo reproducirlo?

¿Qué esperaba la prueba?

¿Qué obtuvo?

¿En qué entorno?

¿Dónde está la evidencia?
```

Por eso necesitamos:

# DOCUMENTAR LA INCIDENCIA.

---

# 45. Incidencia ≠ simplemente “test rojo”

Una prueba fallida puede convertirse en una incidencia documentada.

Ejemplo:

```text
INC-001
Tarifa premium incorrecta
```

---

# 46. Plantilla de incidencia

| Campo | Información |
|---|---|
| ID | INC-001 |
| Título | Descuento premium incorrecto |
| Entorno | Java 25 / Maven / JUnit |
| Precondiciones | Cliente premium |
| Datos | 2 noches |
| Pasos | Ejecutar test correspondiente |
| Esperado | 90 € |
| Obtenido | 100 € |
| Evidencia | test fallido/captura |
| Estado | Abierta |
| Observaciones | posible fallo en descuento |

---

# 47. Una incidencia debe ser reproducible

Insuficiente:

```text
No funciona.
```

Mejor:

```text
Con 2 noches
y cliente premium,
calcular(2,true)
devuelve 100.0
en vez de 90.0.
```

---

# 48. Severidad y prioridad

Podemos registrar:

```text
severidad
```

para describir el impacto técnico.

Ejemplo:

```text
baja

media

alta

crítica
```

Pero:

```text
severidad
```

y:

```text
prioridad de negocio
```

no son necesariamente lo mismo.

No serán el núcleo evaluativo de RA3.h.

---

# 49. La evidencia más fuerte

Una incidencia queda especialmente bien documentada si contiene:

```text
caso reproducible

test que falla

esperado

obtenido

entorno

estado.
```

---

# 50. CAPTURA UD10-05 — Test fallido

Debe mostrar:

```text
expected

actual

nombre del test
```

y relacionarse con:

```text
INC-xxx.
```

---

# 51. Dobles de prueba

Un doble sustituye durante la prueba a:

```text
una dependencia real.
```

Ejemplo:

```text
ServicioReserva
```

depende de:

```text
RepositorioDisponibilidad.
```

No queremos consultar una base de datos real.

Podemos sustituirla por:

```text
un doble.
```

---

# 52. Analogía

En una película:

```text
actor real
```

puede ser sustituido temporalmente por:

```text
doble.
```

En una prueba:

```text
dependencia real
```

puede ser sustituida por:

```text
test double.
```

---

# 53. ¿Para qué?

Para:

```text
aislar la unidad

controlar respuestas

simular errores

evitar sistemas externos

hacer pruebas rápidas

observar interacciones.
```

---

# 54. Tipos de dobles

Trabajaremos conceptualmente con:

```text
Dummy

Stub

Fake

Spy

Mock
```

No existe obligación de utilizar todos en cada prueba.

---

# 55. Dummy

Un dummy es un objeto:

```text
necesario para completar
una llamada
```

pero que:

```text
no interviene realmente
en lo que queremos comprobar.
```

---

# 56. Ejemplo dummy

Método:

```java
registrar(
    Reserva reserva,
    Auditoria auditoria
)
```

Si en una prueba concreta:

```text
Auditoria
```

es obligatoria como parámetro pero no se utiliza para el comportamiento analizado:

```text
puede actuar
como dummy.
```

---

# 57. Stub

Un stub devuelve:

```text
respuestas predefinidas
```

para controlar el escenario.

Ejemplo:

```text
cuando pregunte
“¿Aula A101 disponible?”

responde
true.
```

---

# 58. Fake

Un fake tiene:

```text
una implementación funcional
pero simplificada.
```

Ejemplo:

```text
RepositorioReservasEnMemoria
```

que utiliza:

```java
List<Reserva>
```

en vez de:

```text
una base de datos real.
```

---

# 59. Spy

Un spy ayuda a:

```text
observar
cómo se utilizó
una dependencia.
```

Puede permitir comprobar:

```text
cuántas veces fue llamada

con qué parámetros.
```

---

# 60. Mock

Un mock es un doble configurable utilizado para:

```text
controlar comportamiento

y/o

verificar interacciones.
```

Mockito facilita precisamente esta clase de pruebas. Su versión estable actual es 5.24.0.

---

# 61. Dependencias del ejemplo

```java
public interface DisponibilidadGateway {

    boolean estaDisponible(
            String recursoId
    );
}
```

```java
public interface Notificador {

    void enviarConfirmacion(
            String email
    );
}
```

---

# 62. Clase que queremos probar

```java
public class ReservaService {

    private final DisponibilidadGateway
            disponibilidad;

    private final Notificador
            notificador;

    public ReservaService(
            DisponibilidadGateway disponibilidad,
            Notificador notificador) {

        this.disponibilidad =
                disponibilidad;

        this.notificador =
                notificador;
    }

    public boolean reservar(
            String recurso,
            String email) {

        if (!disponibilidad
                .estaDisponible(recurso)) {

            return false;
        }

        notificador
                .enviarConfirmacion(email);

        return true;
    }
}
```

---

# 63. Problema sin dobles

Para probar `ReservaService` podríamos necesitar:

```text
base de datos

servidor SMTP

conexión

configuración

datos reales.
```

Eso complica una prueba que debería comprobar:

```text
la lógica de ReservaService.
```

---

# 64. Mockito

Dependencia:

```xml
<dependency>
    <groupId>org.mockito</groupId>
    <artifactId>mockito-core</artifactId>
    <version>5.24.0</version>
    <scope>test</scope>
</dependency>
```

---

# 65. Crear un mock

```java
DisponibilidadGateway disponibilidad =
        mock(
            DisponibilidadGateway.class
        );
```

---

# 66. Programar una respuesta

```java
when(
    disponibilidad
        .estaDisponible("A101")
).thenReturn(true);
```

Significa:

> Durante esta prueba, cuando se consulte A101, responde `true`.

---

# 67. Crear otro mock

```java
Notificador notificador =
        mock(
            Notificador.class
        );
```

---

# 68. Construir la unidad

```java
ReservaService servicio =
        new ReservaService(
                disponibilidad,
                notificador
        );
```

La clase real que probamos es:

```text
ReservaService.
```

Las dependencias:

```text
DisponibilidadGateway

Notificador
```

son dobles.

---

# 69. Ejecutar

```java
boolean resultado =
        servicio.reservar(
                "A101",
                "profesor@miralmonte.es"
        );
```

---

# 70. Comprobar resultado

```java
assertTrue(resultado);
```

---

# 71. Verificar interacción

```java
verify(notificador)
    .enviarConfirmacion(
        "profesor@miralmonte.es"
    );
```

Ahora comprobamos:

```text
resultado

+
interacción.
```

---

# 72. Prueba completa

```java
@Test
void confirmaCuandoHayDisponibilidad() {

    DisponibilidadGateway disponibilidad =
            mock(
                DisponibilidadGateway.class
            );

    Notificador notificador =
            mock(
                Notificador.class
            );

    when(
        disponibilidad
            .estaDisponible("A101")
    ).thenReturn(true);

    ReservaService servicio =
            new ReservaService(
                    disponibilidad,
                    notificador
            );

    boolean resultado =
            servicio.reservar(
                "A101",
                "profesor@miralmonte.es"
            );

    assertTrue(resultado);

    verify(notificador)
        .enviarConfirmacion(
            "profesor@miralmonte.es"
        );
}
```

---

# 73. Escenario no disponible

```java
@Test
void noConfirmaSiNoHayDisponibilidad() {

    DisponibilidadGateway disponibilidad =
            mock(
                DisponibilidadGateway.class
            );

    Notificador notificador =
            mock(
                Notificador.class
            );

    when(
        disponibilidad
            .estaDisponible("A101")
    ).thenReturn(false);

    ReservaService servicio =
            new ReservaService(
                    disponibilidad,
                    notificador
            );

    boolean resultado =
            servicio.reservar(
                "A101",
                "profesor@miralmonte.es"
            );

    assertFalse(resultado);

    verify(
        notificador,
        never()
    ).enviarConfirmacion(
        anyString()
    );
}
```

---

# 74. ¿Qué hemos aislado?

No necesitamos:

```text
una base de datos real

un aula real

un servidor de correo real.
```

Estamos comprobando:

```text
la decisión
de ReservaService.
```

Eso es exactamente el objetivo de:

# RA3.i.

---

# 75. No hacer mock de todo

Un error frecuente:

```text
mockear
cada objeto
```

aunque sea una clase simple que podría utilizarse realmente.

Los dobles son útiles especialmente cuando existe:

```text
dependencia externa

coste

lentitud

no determinismo

dificultad de configuración.
```

---

# 76. Fake vs mock

## Fake

Podemos construir:

```java
class RepositorioFake
        implements Repositorio {
    // implementación en memoria
}
```

y utilizarlo como una versión simplificada.

## Mock

Podemos programar:

```java
when(repo.buscar(...))
        .thenReturn(...);
```

sin implementar realmente un repositorio funcional.

---

# 77. Stub vs mock

La terminología puede variar entre autores, pero a nivel didáctico:

## Stub

Nos interesa especialmente:

```text
qué devuelve.
```

## Mock

Nos interesa además poder comprobar:

```text
cómo fue utilizado.
```

---

# 78. Spy

Un spy puede envolver:

```text
un objeto real
```

y registrar interacciones.

No será obligatorio utilizar spies para superar P10.1.

Debes:

```text
reconocer el concepto.
```

---

# 79. CAPTURA UD10-06 — Mockito

Debe mostrar:

```text
mock()

when(...).thenReturn(...)

verify(...)
```

dentro de una prueba funcional.

---

# 80. JDK 21+ y Mockito

Mockito advierte que, desde Java 21, las restricciones del JDK sobre agentes dinámicos pueden producir advertencias o requerir configuración explícita del agente para determinadas capacidades del *inline mock maker*.

Para las prácticas:

```text
el profesor comprobará
la configuración del proyecto
antes de distribuirla.
```

No convertiremos esta cuestión interna de instrumentación en contenido evaluable del alumnado.

---

# 81. Regla docente

La práctica se entregará:

```text
ya configurada
```

para que el alumno evalúe:

```text
dobles de prueba
```

y no:

```text
cómo funciona internamente
la instrumentación de Mockito.
```

---

# 82. Caso profesional — CartagoBooking

CartagoBooking gestiona reservas de salas.

Reglas:

```text
una reserva necesita
una sala disponible

la duración debe ser
de al menos una hora

el precio base es
50 € por hora

clientes premium
reciben un 10 % de descuento

una reserva aceptada
envía confirmación.
```

---

# 83. Clase TarifaReserva

```java
public class TarifaReserva {

    public double calcular(
            int horas,
            boolean premium) {

        if (horas < 1) {
            throw new
                IllegalArgumentException(
                    "Horas no válidas"
                );
        }

        double total =
                horas * 50.0;

        if (premium) {
            total *= 0.90;
        }

        return total;
    }
}
```

---

# 84. Pruebas unitarias básicas

```java
@Test
void calculaUnaHoraNormal() {

    assertEquals(
        50.0,
        tarifa.calcular(
            1,
            false
        )
    );
}
```

---

# 85. Premium

```java
@Test
void aplicaDescuentoPremium() {

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

# 86. Excepción

```java
@Test
void rechazaCeroHoras() {

    assertThrows(
        IllegalArgumentException.class,
        () -> tarifa.calcular(
            0,
            false
        )
    );
}
```

---

# 87. Parametrización

```java
@ParameterizedTest
@CsvSource({
    "1, false, 50.0",
    "2, false, 100.0",
    "1, true, 45.0",
    "2, true, 90.0"
})
void calculaTarifas(
        int horas,
        boolean premium,
        double esperado) {

    assertEquals(
        esperado,
        tarifa.calcular(
            horas,
            premium
        )
    );
}
```

---

# 88. Actividad A10.1 — Primer test

Para:

```java
public int cuadrado(int numero)
```

escribe:

```text
un caso normal

cero

negativo
```

utilizando JUnit.

---

# 89. Actividad A10.2 — Excepciones

Método:

```java
public double dividir(
        double a,
        double b)
```

debe rechazar:

```text
b = 0.
```

Escribe una prueba con:

```java
assertThrows(...)
```

---

# 90. Actividad A10.3 — Parametrizar

Convierte:

```text
cinco tests
de la misma regla
```

en:

```text
una prueba parametrizada.
```

Después responde:

> ¿Qué hemos reducido sin perder casos?

---

# 91. Actividad A10.4 — Automatizar

Ejecuta:

```bash
mvn test
```

desde:

```text
estado limpio del proyecto.
```

Registra:

```text
número de tests

fallos

errores

resultado de build.
```

---

# 92. Actividad A10.5 — Romper deliberadamente

Modifica temporalmente:

```java
total *= 0.90;
```

por:

```java
total *= 0.95;
```

Ejecuta:

```bash
mvn test
```

Identifica:

```text
qué prueba detecta
la regresión.
```

Después restaura el código.

---

# 93. Actividad A10.6 — Documenta la incidencia

Con el defecto anterior crea:

```text
INC-001
```

incluyendo:

```text
título

entorno

datos

esperado

obtenido

test afectado

pasos

evidencia.
```

---

# 94. Actividad A10.7 — Stub conceptual

Crea manualmente una implementación sencilla de:

```java
DisponibilidadGateway
```

que siempre responda:

```java
true
```

y utilízala para probar `ReservaService`.

Después compara esa solución con:

```text
Mockito.
```

---

# 95. Actividad A10.8 — Mockito

Crea mocks de:

```text
DisponibilidadGateway

Notificador
```

y prueba:

```text
sala disponible

sala no disponible.
```

Verifica:

```text
confirmación enviada
cuando procede

confirmación no enviada
cuando no procede.
```

---

# 96. Errores frecuentes — testing

## Error 1

Una prueba sin assertion.

```java
@Test
void prueba() {
    servicio.calcular();
}
```

Puede ejecutarse sin demostrar:

```text
qué resultado
esperábamos.
```

---

# 97. Error 2

Copiar la implementación en el test.

Si producción calcula:

```text
precio = horas * 50
```

y el test calcula:

```text
esperado = horas * 50
```

utilizando exactamente la misma lógica:

```text
podemos repetir
el mismo error.
```

Preferimos valores esperados derivados:

```text
del requisito.
```

---

# 98. Error 3

Pruebas interdependientes.

```text
test2
```

no debe necesitar:

```text
que test1
haya sido ejecutado antes.
```

---

# 99. Error 4

Pruebas no deterministas

Una prueba no debería depender innecesariamente de:

```text
hora actual

Internet

orden aleatorio

datos externos cambiantes.
```

---

# 100. Error 5

Todo con mocks.

No tiene sentido reemplazar:

```text
una clase de valor sencilla
```

solo porque sabemos utilizar Mockito.

---

# 101. Error 6

Verificar implementación irrelevante

No queremos que el test falle simplemente porque:

```text
se reorganizó internamente
el código
```

si:

```text
el comportamiento
sigue siendo correcto.
```

---

# 102. Error 7

Incidencia sin esperado

```text
La reserva da mal.
```

no es una incidencia reproducible.

---

# 103. Error 8

Confundir automatización con CI

```bash
mvn test
```

automatiza pruebas.

Pero:

```text
GitHub Actions
```

pertenecerá a:

```text
UD11 / RA4.i.
```

---

# 104. Buenas prácticas

- nombres expresivos;
- AAA;
- pruebas independientes;
- resultados deterministas;
- casos relevantes;
- automatización con un comando;
- incidencias reproducibles;
- dobles únicamente cuando aportan aislamiento;
- verificar resultados antes que detalles irrelevantes;
- mantener pruebas suficientemente rápidas.

---

# 105. PRÁCTICA EVALUABLE P10.1

# VERIFICACIÓN AUTOMÁTICA DE CARTAGOBOOKING

**Modalidad:** individual  
**RA:** RA3  
**CE evaluados:** RA3.f, RA3.g, RA3.h, RA3.i  
**Instrumento:** I-RA3-02  

---

# 106. Proyecto

Se entrega:

```text
CartagoBooking
```

como proyecto Maven con:

```text
TarifaReserva

ReservaService

DisponibilidadGateway

Notificador
```

y estructura:

```text
src/main/java

src/test/java.
```

---

# 107. Tarea A — Pruebas unitarias de TarifaReserva

Crea pruebas para:

```text
1 hora normal

2 horas normales

1 hora premium

2 horas premium

0 horas

valor negativo.
```

Debes utilizar:

```text
assertEquals

assertThrows.
```

**CE:** RA3.f

---

# 108. Tarea B — Preparación común

Utiliza:

```java
@BeforeEach
```

cuando permita reducir:

```text
duplicación
```

sin ocultar lo que hace cada prueba.

**CE:** RA3.f

---

# 109. Tarea C — Prueba parametrizada

Crea al menos una:

```java
@ParameterizedTest
```

para comprobar varias combinaciones:

```text
horas

premium

esperado.
```

Los datos deben provenir de los casos ya razonados en UD09/RA3.b.

**CE:** RA3.f

---

# 110. Evidencias RA3.f

```text
E-RA3.f-01
Clase de pruebas unitaria.

E-RA3.f-02
Assertions adecuadas.

E-RA3.f-03
Prueba de excepción.

E-RA3.f-04
Prueba parametrizada.

E-RA3.f-05
Ejecución correcta
de la unidad/suite.
```

---

# 111. Tarea D — Automatización Maven

Configura o verifica:

```text
JUnit 6.1.3

Surefire 3.6.0.
```

Desde terminal ejecuta:

```bash
mvn test
```

sin lanzar manualmente cada prueba.

---

# 112. Tarea E — Evidencia reproducible

Incluye:

```text
comando

salida

tests ejecutados

failures

errors

resultado final.
```

**CE:** RA3.g

---

# 113. Tarea F — Automatización tras cambio

Introduce el defecto indicado por el profesor.

Ejecuta únicamente:

```bash
mvn test
```

y demuestra que la suite:

```text
detecta automáticamente
el problema.
```

Después restaura el código.

---

# 114. Evidencias RA3.g

```text
E-RA3.g-01
Configuración Maven/Surefire.

E-RA3.g-02
mvn test ejecuta
la suite completa.

E-RA3.g-03
Suite detecta
un defecto introducido.

E-RA3.g-04
Suite vuelve a verde
tras corregir/restaurar.
```

---

# 115. Tarea G — Incidencia

A partir del test fallido crea:

```text
INC-BOOKING-001.
```

Debe contener:

```text
ID

título

entorno

versión Java

precondición

datos

pasos

resultado esperado

resultado obtenido

test que falla

evidencia

estado.
```

**CE:** RA3.h

---

# 116. Tarea H — Calidad de la incidencia

Otra persona debe ser capaz de:

```text
reproducir el fallo
```

utilizando únicamente:

```text
proyecto

incidencia

comando indicado.
```

---

# 117. Evidencias RA3.h

```text
E-RA3.h-01
Incidencia identificada.

E-RA3.h-02
Pasos reproducibles.

E-RA3.h-03
Esperado/obtenido.

E-RA3.h-04
Relación con test fallido.

E-RA3.h-05
Evidencia y entorno.
```

---

# 118. Tarea I — Dobles

Prueba:

```text
ReservaService
```

sin utilizar:

```text
base de datos real

servidor de correo real.
```

Utiliza Mockito.

---

# 119. Escenario 1

Configura:

```text
sala A101
→ disponible.
```

Debes demostrar:

```text
reservar()
→ true
```

y:

```text
se envía confirmación.
```

---

# 120. Escenario 2

Configura:

```text
sala A101
→ no disponible.
```

Debes demostrar:

```text
reservar()
→ false
```

y:

```text
NO se envía confirmación.
```

---

# 121. Tarea J — Explicación del aislamiento

Responde:

1. ¿Qué clase real estás probando?
2. ¿Qué componentes han sido sustituidos?
3. ¿Qué comportamiento has programado en el stub/mock?
4. ¿Qué interacción has verificado?
5. ¿Qué sistema externo has evitado utilizar?
6. ¿Por qué esto mejora el aislamiento?

**CE:** RA3.i

---

# 122. Evidencias RA3.i

```text
E-RA3.i-01
Dependencias identificadas.

E-RA3.i-02
Mocks creados.

E-RA3.i-03
Stubbing mediante when.

E-RA3.i-04
Resultado comprobado.

E-RA3.i-05
Interacción comprobada
con verify.

E-RA3.i-06
Escenario negativo
con never.

E-RA3.i-07
Explicación del aislamiento.
```

---

# 123. Entregables

Archivo:

```text
P10.1_Apellidos_Nombre.pdf
```

más proyecto:

```text
CartagoBooking/
```

sin:

```text
target/
```

si la plataforma admite entrega de proyecto comprimido.

El PDF debe contener:

1. estructura del proyecto;
2. pruebas unitarias;
3. prueba parametrizada;
4. ejecución IntelliJ;
5. ejecución `mvn test`;
6. fallo deliberado;
7. incidencia;
8. pruebas con Mockito;
9. explicación de los dobles;
10. conclusión.

---

# 124. Instrumento I-RA3-02

**Instrumento:** I-RA3-02  
**RA:** RA3  
**CE:** RA3.f, RA3.g, RA3.h, RA3.i  
**Actividad:** P10.1  
**Tipo:** laboratorio de pruebas automatizadas individual  

Cada CE obtiene:

```text
NOTA 0,00–10,00
```

independientemente.

---

# 125. Rúbrica definitiva I-RA3-02

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA3.f** | Efectúa pruebas unitarias de clases y funciones | Las pruebas no contienen comprobaciones válidas, no aíslan comportamientos o no se ejecutan correctamente | Escribe algunas pruebas unitarias funcionales con ayuda y assertions básicas | Construye pruebas unitarias claras con JUnit, comprueba resultados, errores y varios casos mediante pruebas ordinarias y parametrizadas | Además organiza las pruebas con gran claridad, evita dependencias entre ellas, selecciona adecuadamente assertions y mantiene una suite robusta y legible | **100 % del CE** |
| **RA3.g** | Implementa un mecanismo reproducible de ejecución automática de pruebas | Las pruebas necesitan ejecución/comprobación manual una a una o la automatización no funciona | Ejecuta varias pruebas mediante el IDE o Maven con ayuda | Configura y utiliza Maven/Surefire para ejecutar automáticamente toda la suite mediante `mvn test` y detectar fallos | Además demuestra reproducibilidad desde estado limpio, interpreta correctamente los resultados del build y mantiene la automatización independiente de acciones manuales | **100 % del CE** |
| **RA3.h** | Documenta de forma reproducible las incidencias detectadas | La incidencia es vaga, carece de esperado/obtenido o no puede reproducirse | Registra los datos básicos del defecto aunque falten detalles | Documenta ID, entorno, datos, pasos, esperado, obtenido, evidencia, test afectado y estado de forma reproducible | Además relaciona con precisión la incidencia con la evidencia automática y permite que otra persona reproduzca y valide el defecto sin información adicional | **100 % del CE** |
| **RA3.i** | Utiliza dobles de prueba para aislar componentes | No consigue aislar la unidad o utiliza dobles sin comprender su finalidad | Crea algún stub/mock básico con ayuda | Sustituye correctamente dependencias mediante Mockito, programa respuestas y verifica interacciones para escenarios positivos y negativos | Además distingue justificadamente tipos de dobles, evita mocks innecesarios y diseña pruebas especialmente aisladas, deterministas y expresivas | **100 % del CE** |

---

# 126. Nota informativa P10.1

Puede mostrarse:

```text
(
 RA3.f
+RA3.g
+RA3.h
+RA3.i
) / 4
```

pero la evaluación conserva:

```text
RA3.f

RA3.g

RA3.h

RA3.i
```

por separado.

---

# 127. Temporalización definitiva

| Sesión | Contenido | Actividad |
|---:|---|---|
| 1 | Maven, JUnit y estructura de pruebas | primer test |
| 2 | Assertions, excepciones y AAA | A10.1–2 |
| 3 | `BeforeEach` y parametrización | A10.3 |
| 4 | Maven/Surefire y automatización | A10.4–5 |
| 5 | Incidencias y trazabilidad de fallos | A10.6 |
| 6 | Dobles: dummy, stub, fake, spy, mock | ejemplos |
| 7 | Mockito: `mock`, `when`, `verify` | A10.7–8 |
| 8 | P10.1 — pruebas unitarias | I-RA3-02 |
| 9 | P10.1 — automatización/incidencia | I-RA3-02 |
| 10 | P10.1 — dobles de prueba | I-RA3-02 |
| 11 | revisión, evidencias y cierre | I-RA3-02 |

**Total: 11 periodos.**

---

# 128. Ejercicios de consolidación

1. ¿Qué es una prueba unitaria?
2. ¿Qué diferencia existe entre código de producción y de prueba?
3. ¿Para qué sirve `@Test`?
4. ¿Qué es una assertion?
5. ¿Qué hace `assertEquals`?
6. ¿Para qué sirve `assertThrows`?
7. Explica Arrange–Act–Assert.
8. ¿Para qué sirve `@BeforeEach`?
9. ¿Qué problema tiene compartir estado entre pruebas?
10. ¿Qué es una prueba parametrizada?
11. ¿Para qué sirve `@CsvSource`?
12. ¿Qué evalúa RA3.f?
13. ¿Qué evalúa RA3.g?
14. ¿Qué hace `mvn test`?
15. ¿Qué función realiza Surefire?
16. ¿Ejecutar `mvn test` constituye por sí solo CI?
17. ¿Qué debe contener una incidencia?
18. Diferencia esperado y obtenido.
19. ¿Qué es un doble de prueba?
20. ¿Para qué sirve aislar una dependencia?
21. ¿Qué es un dummy?
22. ¿Qué es un stub?
23. ¿Qué es un fake?
24. ¿Qué es un spy?
25. ¿Qué es un mock?
26. ¿Qué hace `when(...).thenReturn(...)`?
27. ¿Qué hace `verify(...)`?
28. ¿Qué comprueba `never()`?
29. ¿Por qué no debemos mockear todo?
30. ¿Qué CE evalúa dobles de prueba?

---

# 129. Autoevaluación

### 1

`@Test`:

A. identifica un método de prueba  
B. crea una clase Java  
C. inicia Maven  
D. genera UML

### 2

`assertEquals`:

A. compara esperado y obtenido  
B. crea un mock  
C. instala JUnit  
D. hace commit

### 3

`assertThrows`:

A. comprueba una excepción esperada  
B. ignora errores  
C. crea un JAR  
D. depura

### 4

AAA significa:

A. Arrange, Act, Assert  
B. Add, Apply, Automate  
C. Analyse, Add, Abort  
D. ninguna

### 5

Una prueba parametrizada:

A. ejecuta el mismo comportamiento con distintos datos  
B. solo puede ejecutarse una vez  
C. sustituye Maven  
D. sustituye Mockito

### 6

`mvn test`:

A. puede ejecutar automáticamente la suite  
B. crea un Pull Request  
C. genera UML  
D. inicia Git

### 7

Una incidencia reproducible debe contener:

A. esperado y obtenido  
B. únicamente una opinión  
C. únicamente una captura  
D. solo el nombre del alumno

### 8

Un stub se utiliza principalmente para:

A. proporcionar respuestas controladas  
B. compilar Java  
C. crear ramas  
D. generar documentación

### 9

`verify()`:

A. permite comprobar una interacción con un mock  
B. compila Maven  
C. crea una clase  
D. abre el debugger

### 10

GitHub Actions:

A. forma parte de RA3.g en UD10  
B. queda reservado para RA4.i en UD11  
C. sustituye JUnit  
D. es un test double

---

# 130. Soluciones

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
10 → B
```

---

# PARTE B — MATERIAL DEL PROFESOR

# 131. Finalidad docente

El objetivo es que el alumno evolucione desde:

```text
“ejecuto y miro”
```

hacia:

```text
“el comportamiento esperado
está codificado
como una prueba repetible”.
```

Y después:

```text
“puedo ejecutar
todas mis comprobaciones
automáticamente”.
```

---

# 132. Separación RA3.f / RA3.g

Debe quedar muy clara.

## RA3.f

Evidencia:

```text
código JUnit
que prueba
clases/funciones.
```

## RA3.g

Evidencia:

```text
mecanismo automático
que ejecuta
la suite.
```

No asignar:

```text
la misma evidencia
sin distinguir
qué demuestra.
```

---

# 133. RA3.h

La incidencia no debe convertirse en:

```text
un ensayo teórico
sobre gestión de bugs.
```

Debe partir de:

# UN FALLO REAL Y REPRODUCIBLE.

---

# 134. Defecto controlado recomendado

En `TarifaReserva`:

Correcto:

```java
if (premium) {
    total *= 0.90;
}
```

Defectuoso:

```java
if (premium) {
    total *= 0.95;
}
```

Para:

```text
2 horas premium
```

tenemos:

```text
esperado:
90.00

obtenido:
95.00
```

---

# 135. Ventaja

La incidencia puede quedar enlazada claramente con:

```text
test

datos

esperado

actual.
```

---

# 136. RA3.i

El alumno debe demostrar:

```text
AISLAMIENTO.
```

No basta con utilizar:

```java
mock(...)
```

sin explicar:

```text
qué dependencia sustituye

por qué

qué se controla

qué se verifica.
```

---

# 137. Nivel de dobles

Los contenidos oficiales incluyen:

```text
Dobles de prueba.

Tipos.

Características.
```

pero no es necesario exigir:

```text
dominio avanzado
de todos los patrones
de mocking.
```

El mínimo práctico será:

```text
stub/mock mediante Mockito
```

y reconocimiento conceptual de:

```text
dummy

fake

spy.
```

---

# 138. Mockito actual

La versión 5.24.0 fue publicada el 23 de septiembre de 2026 y es actualmente la versión marcada como Latest en el repositorio oficial.

---

# 139. Java 25 y Mockito

La documentación oficial de Mockito advierte que los JDK desde Java 21 restringen la auto-adjunción de agentes y documenta la configuración explícita de Mockito como `-javaagent` para Maven/Surefire cuando sea necesaria.

Por ello:

```text
EL PROYECTO EVALUABLE
SE PROBARÁ PREVIAMENTE
EN LOS EQUIPOS DEL AULA.
```

---

# 140. Recomendación técnica docente

Para evitar que la configuración interna de Mockito distraiga del CE:

```text
entregar pom.xml
ya probado.
```

Si el entorno requiere agente explícito:

```text
configurarlo
en el proyecto base
```

antes de comenzar P10.1.

No convertir:

```text
javaagent
```

en requisito del alumno.

---

# 141. Surefire 3.6.0

Apache define 3.6.0 como la versión estable actual y el plugin `surefire:test` se enlaza con la fase Maven `test`.

Esto hace apropiado:

```bash
mvn test
```

como evidencia simple de:

```text
RA3.g.
```

---

# 142. JUnit 6.1.3

JUnit 6.1.3 fue publicado el 7 de agosto de 2026 y requiere Java 17 o superior.

No enseñar:

```text
JUnit 4
```

salvo contexto histórico.

---

# 143. IntelliJ

IntelliJ IDEA 2026.2 puede crear y ejecutar tests JUnit y visualizar resultados directamente desde el IDE.

Pero para RA3.g exigiremos además:

```bash
mvn test
```

para desacoplar la automatización de:

```text
hacer clic
sobre cada test.
```

---

# 144. No introducir CI todavía

Evitar en esta unidad:

```text
.github/workflows

GitHub Actions

pipelines

triggers push/pull_request.
```

Eso pertenece a:

```text
RA4.i
UD11.
```

---

# 145. Relación con UD11

Las pruebas de UD10 tendrán posteriormente otra utilidad:

```text
proteger refactorizaciones
```

en:

```text
RA4.b.
```

Pero en UD10:

# NO SE EVALÚA REFACTORIZACIÓN.

---

# 146. Capturas previstas

```text
CAPTURA UD10-01
Estructura Maven

CAPTURA UD10-02
JUnit y resultados

CAPTURA UD10-03
Parameterized Test

CAPTURA UD10-04
mvn test / Surefire

CAPTURA UD10-05
Test fallido + expected/actual

CAPTURA UD10-06
Mockito mock/when/verify

CAPTURA UD10-07
Suite completa verde

CAPTURA UD10-08
Incidencia relacionada
con el test fallido
```

---

# 147. Medidas de apoyo

Puede proporcionarse:

```text
proyecto Maven preparado

pom.xml funcional

test JUnit de ejemplo

tabla AAA

plantilla de incidencia

interfaces ya creadas

diagrama simple de dependencias.
```

No proporcionar:

```text
tests finales
de CartagoBooking

ni

mocks finales
de P10.1.
```

---

# 148. Plantilla AAA

```text
ARRANGE
¿Qué necesito preparar?

ACT
¿Qué método ejecuto?

ASSERT
¿Qué debe cumplirse?
```

---

# 149. Plantilla incidencia

```text
ID:

Título:

Entorno:

Precondición:

Datos:

Pasos:

Esperado:

Obtenido:

Test relacionado:

Evidencia:

Estado:
```

---

# 150. Plantilla de dobles

| Dependencia | ¿Real o doble? | Tipo | Comportamiento preparado | Interacción a comprobar |
|---|---|---|---|---|
| | | | | |

---

# 151. Solución orientativa RA3.f

Debe contener como mínimo:

```text
tests de comportamiento normal

premium

excepciones

parametrización.
```

---

# 152. Solución orientativa RA3.g

Evidencia fuerte:

```bash
mvn test
```

Ejemplo de resultado:

```text
Tests run: 10
Failures: 0
Errors: 0
Skipped: 0

BUILD SUCCESS
```

Después del defecto:

```text
Failures: 1

BUILD FAILURE
```

---

# 153. Solución orientativa RA3.h

Ejemplo:

```text
ID:
INC-BOOKING-001

Título:
Descuento premium aplica 5 %
en lugar de 10 %

Entrada:
horas=2
premium=true

Esperado:
90.00

Obtenido:
95.00

Test:
aplicaDescuentoPremium

Estado:
Abierta
```

---

# 154. Solución orientativa RA3.i

Mock:

```java
when(
    disponibilidad
        .estaDisponible("A101")
).thenReturn(true);
```

Ejecución:

```java
boolean creada =
        servicio.reservar(
            "A101",
            "profesor@miralmonte.es"
        );
```

Resultado:

```java
assertTrue(creada);
```

Interacción:

```java
verify(notificador)
    .enviarConfirmacion(
        "profesor@miralmonte.es"
    );
```

---

# 155. Escenario negativo

```java
when(
    disponibilidad
        .estaDisponible("A101")
).thenReturn(false);
```

Resultado:

```java
assertFalse(resultado);
```

y:

```java
verify(
    notificador,
    never()
).enviarConfirmacion(
    anyString()
);
```

---

# 156. Qué no evaluar en Mockito

No exigir:

```text
mock estático

constructor mocking

singleton mocking

answers avanzados

argument captors

strictness avanzada.
```

Pueden quedar para ampliación.

---

# 157. Ampliación

Alumnado avanzado puede estudiar:

```text
ArgumentCaptor

@Mock

@InjectMocks

@ExtendWith

spies

fakes en memoria

test fixtures

nested tests.
```

Sin añadir nuevos CE.

---

# 158. Recuperación

Instrumento:

# IR-RA3-01

Bloques correspondientes a UD10:

```text
RA3.f

RA3.g

RA3.h

RA3.i
```

Ejemplo:

```text
f = 7

g = 8

h = 3

i = 6
```

Si RA3 queda no superado y únicamente necesita nueva evidencia de:

```text
RA3.h
```

el alumno realizará exclusivamente:

```text
bloque de documentación
de incidencia.
```

---

# 159. Trazabilidad UD10

| RA | CE | Contenido | Actividades | Instrumento | Evidencias |
|---|---|---|---|---|---|
| RA3 | f | pruebas unitarias JUnit | A10.1–3 | P10.1 / I-RA3-02 | E-RA3.f-01/05 |
| RA3 | g | automatización Maven/Surefire | A10.4–5 | P10.1 / I-RA3-02 | E-RA3.g-01/04 |
| RA3 | h | documentación de incidencias | A10.6 | P10.1 / I-RA3-02 | E-RA3.h-01/05 |
| RA3 | i | dobles y aislamiento | A10.7–8 | P10.1 / I-RA3-02 | E-RA3.i-01/07 |

---

# 160. Estado completo de RA3

Tras UD09:

```text
RA3.a ✔
RA3.b ✔
RA3.c ✔
RA3.d ✔
RA3.e ✔
```

Tras UD10:

```text
RA3.f ✔
RA3.g ✔
RA3.h ✔
RA3.i ✔
```

Resultado:

# RA3 COMPLETAMENTE CUBIERTO.

---

# 161. Cálculo definitivo RA3

RA3 contiene:

```text
9 CE.
```

Cada CE tiene el mismo peso:

```text
1 / 9.
```

Por tanto:

```text
RA3 =
(
 a+b+c+d+e+f+g+h+i
) / 9
```

I-RA3-02 no posee un porcentaje arbitrario independiente.

---

# 162. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA3

**CE evaluados:**

```text
RA3.f
RA3.g
RA3.h
RA3.i
```

### ¿Se reutiliza RA3.b?

Sí.

Para:

```text
seleccionar datos
y resultados esperados.
```

# NO SE RECALIFICA.

### ¿Se utiliza Maven?

Sí.

Como:

```text
herramienta
de automatización
de pruebas.
```

### ¿Se evalúa integración continua?

# NO.

```text
RA4.i
→ UD11.
```

### ¿Se utiliza Git?

Puede existir el proyecto en un repositorio, pero:

# NO SE EVALÚA.

### ¿Se evalúa refactorización?

# NO.

### ¿Se evalúa Programación?

Java es el soporte técnico de las pruebas.

No se califica:

```text
algoritmia

arquitectura

calidad general
del programa
```

como CE independientes.

### ¿Algún instrumento evalúa otro RA?

# NO.

```text
I-RA3-02
→ exclusivamente RA3.
```

---

# 163. Checklist final UD10

```text
☑ 11 periodos.

☑ RA3 único.

☑ RA3.f oficial.

☑ RA3.g oficial.

☑ RA3.h oficial.

☑ RA3.i oficial.

☑ RA3.b solo reforzado.

☑ JUnit 6.1.3.

☑ Java 25.

☑ IntelliJ 2026.2.

☑ Maven.

☑ Surefire 3.6.0.

☑ Mockito 5.24.0.

☑ src/main/java.

☑ src/test/java.

☑ @Test.

☑ Assertions.

☑ assertThrows.

☑ AAA.

☑ @BeforeEach.

☑ Pruebas independientes.

☑ ParameterizedTest.

☑ CsvSource.

☑ mvn test.

☑ Automatización ≠ CI.

☑ Tests verdes/rojos.

☑ Incidencia reproducible.

☑ Esperado/obtenido.

☑ Dummy.

☑ Stub.

☑ Fake.

☑ Spy.

☑ Mock.

☑ mock().

☑ when().

☑ verify().

☑ never().

☑ Aislamiento de dependencias.

☑ CartagoBooking.

☑ P10.1.

☑ I-RA3-02.

☑ Cuatro CE con nota propia 0–10.

☑ Rúbrica armonizada.

☑ Evidencias codificadas.

☑ 8 capturas previstas.

☑ Consolidación.

☑ Ampliación.

☑ Autoevaluación.

☑ Resumen.

☑ Glosario.

☑ Material profesor.

☑ Recuperación modular.

☑ Trazabilidad completa.

☑ Sin CI anticipada.

☑ Aislamiento superado.

☑ RA3 cerrado.
```

# UD10 — VERSIÓN MAESTRA DEFINITIVA