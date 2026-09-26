# UD01 — MATERIAL DEL PROFESOR

## 1. Finalidad didáctica

La primera unidad debe construir un modelo mental correcto de qué sucede entre:

```text
código escrito
```

y:

```text
programa en ejecución.
```

No se pretende enseñar arquitectura de computadores en profundidad.

El alumno debe comprender suficientemente:

```text
software
↔
sistema operativo
↔
memoria
↔
procesador
```

para poder interpretar posteriormente los procesos de:

```text
compilación

ejecución

depuración

build

testing

CI.
```

---

# 2. Idea didáctica central

Debe evitarse enseñar un único esquema universal:

```text
fuente
→ ejecutable.
```

Conviene contrastar desde el principio:

## Flujo nativo conceptual

```text
fuente
↓
compilador
↓
código objeto
↓
linker
↓
ejecutable
```

## Flujo Java

```text
.java
↓
javac
↓
.class / bytecode
↓
JVM
↓
ejecución
```

La comparación cubre de forma mucho más precisa:

```text
RA1.c
+
RA1.d.
```

---

# 3. Precisión terminológica importante

No presentar:

```text
Pedido.class
```

como equivalente directo de:

```text
Pedido.obj.
```

El primero contiene:

```text
bytecode
para la JVM.
```

El segundo representa conceptualmente:

```text
código objeto
de un proceso
de compilación nativa.
```

Tampoco llamar al `.class`:

```text
“el ejecutable Java”
```

sin matización.

---

# 4. JDK utilizado

Estándar del curso:

```text
Eclipse Temurin JDK 25 LTS.
```

Herramientas prácticas de UD01:

```text
javac

java

javap.
```

No es necesario introducir Maven todavía.

---

# 5. Orientación de las ocho sesiones

| Sesión | Contenido | Evidencia formativa |
|---:|---|---|
| 1 | Programa, hardware, SO, memoria y CPU | A01.1 |
| 2 | Lenguajes y clasificaciones | A01.2 |
| 3 | Fuente, objeto, enlace y ejecutable | ejercicios |
| 4 | Bytecode, JVM y flujo Java | esquema comparativo |
| 5 | Laboratorio `javac`, `java`, `javap` | compilación guiada |
| 6 | Herramientas de desarrollo y caso Pedido | A01.3 |
| 7 | P01.1 — tareas A–C | I-RA1-01 |
| 8 | P01.1 — tareas D–E y cierre | I-RA1-01 |

**Total: 8 periodos.**

---

# 6. Solución A01.1

| Situación | Respuesta orientativa |
|---|---|
| Programa guardado tras apagar | almacenamiento |
| Aplicación actualmente ejecutándose | RAM/proceso gestionado por SO |
| Ejecución final de instrucciones | CPU |
| Resultado visible | pantalla/periférico de salida |
| Gestión de procesos y archivos | sistema operativo |

No exigir una correspondencia artificialmente exclusiva.

Ejemplo:

```text
un programa en ejecución
implica simultáneamente
RAM + CPU + SO.
```

Lo importante es justificar correctamente.

---

# 7. Solución A01.2

## Java

```text
Nivel:
alto nivel

Ejecución:
compila a bytecode JVM;
la JVM ejecuta y puede utilizar JIT

Paradigmas:
orientado a objetos,
imperativo,
características funcionales.
```

## C

```text
Nivel:
alto nivel

Ejecución habitual:
compilación nativa

Paradigmas:
procedimental / imperativo.
```

## Python

Respuesta aceptable:

```text
alto nivel

multiparadigma

habitualmente asociado
a ejecución interpretada.
```

Respuesta avanzada:

```text
implementaciones como CPython
compilan internamente
a bytecode
que después ejecuta
una máquina virtual/intérprete.
```

No penalizar a un alumno de nivel básico por no entrar en detalles internos de CPython si la clasificación introductoria está bien razonada.

---

## JavaScript

```text
alto nivel

multiparadigma

motores modernos
pueden combinar interpretación
y compilación JIT.
```

---

## Kotlin/JVM

```text
alto nivel

compila a bytecode JVM

orientado a objetos
+
funcional.
```

---

# 8. Solución de fuente/objeto/ejecutable

| Elemento | Clasificación |
|---|---|
| `Pedido.java` | código fuente |
| `modulo.obj` | código objeto |
| `aplicacion.exe` | ejecutable nativo |
| `Pedido.class` | class file con bytecode JVM |

Respuesta avanzada:

> `Pedido.class` es un artefacto generado por compilación, pero en el modelo didáctico no debe confundirse con el código objeto nativo de un flujo C/C++ ni con un ejecutable nativo.

---

# 9. Solución laboratorio Pedido

Código:

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

Secuencia:

```bash
javac Pedido.java
javap -c Pedido
java Pedido
```

El profesor deberá comprobar:

```text
Pedido.class
```

antes de continuar.

---

# 10. Experimento de modificación sin recompilación

Éste es pedagógicamente muy importante.

Secuencia:

```text
1. compilar con unidades = 3

2. ejecutar

3. cambiar fuente a unidades = 4

4. NO compilar

5. ejecutar de nuevo
```

El alumno descubre:

```text
modificar el fuente
no modifica automáticamente
el class file existente.
```

Después:

```bash
javac Pedido.java
java Pedido
```

demuestra la relación entre:

```text
fuente

artefacto generado

ejecución.
```

---

# 11. `javap -c`

No evaluar:

```text
conocimiento de opcodes.
```

La finalidad es demostrar:

```text
el .class contiene
una representación diferente
del código Java.
```

Es suficiente identificar:

```text
instrucciones

invocaciones

retorno.
```

---

# 12. Solución A01.3

1. Java → bytecode:

```text
compilador
javac.
```

2. Ejecutar `.class`:

```text
runtime / JVM
mediante java.
```

3. Seguir ejecución línea a línea:

```text
debugger.
```

4. Registrar versiones:

```text
control de versiones.
```

5. Objetos → ejecutable nativo:

```text
linker.
```

6. Automatizar build:

```text
build tool.
```

7. Trabajar con proyecto completo:

```text
IDE.
```

Aceptar alternativas correctamente justificadas.

---

# 13. Soluciones de autoevaluación

```text
1 → A
2 → B
3 → B
4 → B
5 → B
6 → A
7 → A
8 → A
9 → A
10 → B
```

---

# 14. P01.1 — Solución orientativa

## Tarea A — RA1.a

Esquema aceptable:

```text
SSD / almacenamiento
       ↓
Pedido.class
       ↓
Sistema operativo
       ↓
Proceso JVM
       ↓
RAM
       ↓
CPU
       ↓
SO
       ↓
Pantalla
```

Debe explicar que:

- el fichero persiste en almacenamiento;
- la JVM se ejecuta como proceso;
- durante la ejecución se utilizan memoria y CPU;
- el SO gestiona recursos y dispositivos;
- la pantalla muestra la salida.

No exigir ese orden gráfico exacto.

---

# 15. Tarea B — RA1.c

Mínimos:

```text
fuente
→ texto escrito por desarrollador

objeto
→ resultado intermedio
  de compilación nativa

ejecutable
→ artefacto final
  preparado para ejecución
  en ese entorno nativo

.class
→ bytecode JVM.
```

Error conceptual relevante:

```text
“.class = .exe”
```

debe corregirse.

---

# 16. Tarea C — RA1.d

Evidencia mínima:

```text
Pedido.java

javac Pedido.java

Pedido.class

javap -c Pedido

java Pedido.
```

Explicación esperada:

```text
javac
genera bytecode

.class
contiene código intermedio

JVM
lo carga y ejecuta

la JVM permite desacoplar
el bytecode
de una CPU/SO concretos
mediante una implementación
de JVM para esa plataforma.
```

---

# 17. Tarea D — RA1.e

No corregir mediante una tabla rígida de:

```text
lenguaje = una categoría.
```

Valorar especialmente:

```text
capacidad
de justificar matices.
```

Ejemplo de respuesta avanzada:

> Java es un lenguaje de alto nivel y multiparadigma con fuerte orientación a objetos. Su implementación estándar compila a bytecode para JVM, que puede combinar interpretación y JIT.

---

# 18. Tarea E — RA1.f

Debe demostrar:

```text
herramienta
→ función.
```

No evaluar todavía:

```text
configuración avanzada de IDE
→ RA2

depuración práctica
→ RA3

operaciones Git
→ RA4.
```

---

# 19. Instrumento I-RA1-01

**RA:** RA1  
**CE:** a, c, d, e, f  
**Actividad:** P01.1  
**Tipo:** práctica técnica individual

Cada CE obtiene:

```text
nota propia
0,00–10,00.
```

---

# 20. Rúbrica definitiva

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA1.a** | Relaciona programas y componentes del sistema | No reconoce correctamente la función de los componentes | Reconoce almacenamiento, memoria y CPU de forma básica | Reconstruye correctamente la intervención de almacenamiento, RAM, CPU, SO, JVM y periféricos | Además explica con precisión persistencia, proceso, ejecución e interacción entre capas | **100 %** |
| **RA1.c** | Diferencia fuente, objeto y ejecutable | Confunde conceptos fundamentales | Diferencia parcialmente los tres artefactos | Los diferencia correctamente y clasifica ejemplos | Además distingue con precisión el `.class` Java del objeto y ejecutable nativos | **100 %** |
| **RA1.d** | Reconoce código intermedio y máquina virtual | No comprende bytecode/JVM | Identifica `.class` y JVM con alguna imprecisión | Explica y demuestra `.java → javac → .class → JVM` | Además relaciona correctamente bytecode, portabilidad y JIT a nivel conceptual | **100 %** |
| **RA1.e** | Clasifica lenguajes por características | Clasificaciones incorrectas o arbitrarias | Aplica clasificaciones básicas | Clasifica por nivel, ejecución y paradigma con justificación | Además reconoce modelos híbridos y evita simplificaciones inapropiadas | **100 %** |
| **RA1.f** | Evalúa la funcionalidad de herramientas | Confunde sus funciones | Identifica herramientas principales | Relaciona correctamente herramienta, función y necesidad | Además selecciona justificadamente diferentes herramientas según el problema | **100 %** |

---

# 21. Evidencias definitivas

```text
E-RA1.a-01
Mapa programa-sistema

E-RA1.c-01
Tabla fuente/objeto/ejecutable

E-RA1.d-01
Compilación y javap

E-RA1.d-02
Explicación JVM

E-RA1.e-01
Clasificación de lenguajes

E-RA1.f-01
Mapa de herramientas

E-RA1.f-02
Selección razonada.
```

---

# 22. Registro de calificación

No calcular primero:

```text
nota P01.1
```

para repartirla.

Registrar directamente:

```text
RA1.a = x

RA1.c = x

RA1.d = x

RA1.e = x

RA1.f = x.
```

RA1 todavía:

# NO QUEDA CERRADO.

Faltan:

```text
RA1.b
RA1.g
```

que se evaluarán en UD02.

---

# 23. Recuperación

Instrumento general:

# IR-RA1-01

Contiene siete bloques correspondientes a:

```text
RA1.a
RA1.b
RA1.c
RA1.d
RA1.e
RA1.f
RA1.g.
```

Los asociados a UD01 son:

```text
RA1.a
RA1.c
RA1.d
RA1.e
RA1.f.
```

Si tras finalizar RA1 se requiere nueva evidencia únicamente de:

```text
RA1.d
```

se activa solo:

```text
bloque RA1.d
```

del instrumento de recuperación.

---

# 24. Propuesta de recuperación RA1.d

Entregar al alumno un programa Java diferente:

```text
Saludo.java
```

y solicitar:

```text
fuente

compilación

.class

javap

ejecución

explicación del flujo.
```

Debe generar:

```text
ER-RA1.d-01.
```

---

# 25. Medidas de apoyo

Puede facilitarse:

- esquema incompleto de hardware/software;
- tabla con las categorías de lenguajes;
- plantilla fuente/objeto/ejecutable;
- comandos `java`, `javac`, `javap`;
- archivo Java de entrenamiento diferente de Pedido;
- tabla herramienta → posible función.

No facilitar:

```text
las respuestas completas
de P01.1.
```

---

# 26. Errores previsibles

Especialmente frecuentes:

```text
JDK = JVM

.class = ejecutable

.class = .obj

java compila

javac ejecuta

fuente modificado
= programa recompilado

lenguaje
= una única clasificación.
```

Conviene utilizarlos como:

```text
preguntas de contraste
durante la clase.
```

---

# 27. Trazabilidad definitiva

| RA | CE | Contenido principal | Actividad | Instrumento | Evidencia |
|---|---|---|---|---|---|
| RA1 | a | software y sistema informático | A01.1 / P01.1 | I-RA1-01 | E-RA1.a-01 |
| RA1 | c | fuente, objeto, ejecutable | P01.1 | I-RA1-01 | E-RA1.c-01 |
| RA1 | d | bytecode y JVM | laboratorio / P01.1 | I-RA1-01 | E-RA1.d-01/02 |
| RA1 | e | clasificación de lenguajes | A01.2 / P01.1 | I-RA1-01 | E-RA1.e-01 |
| RA1 | f | herramientas de desarrollo | A01.3 / P01.1 | I-RA1-01 | E-RA1.f-01/02 |

---

# 28. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA1

**CE evaluados:**

```text
RA1.a
RA1.c
RA1.d
RA1.e
RA1.f
```

### ¿Se introduce contenido perteneciente evaluativamente a otro RA?

**Sí, únicamente como conocimiento contextual no evaluado.**

Se mencionan:

```text
IDE
depurador
control de versiones
build tools
```

para identificar su función general dentro de RA1.f.

No se evalúan:

```text
configuración IDE → RA2

depuración → RA3

Git → RA4.
```

### ¿Algún instrumento evalúa otro RA?

# NO.

```text
I-RA1-01
→ exclusivamente RA1.
```

---

# 29. Checklist editorial de publicación

```text
☑ Portada normalizada.

☑ Ficha curricular.

☑ RA oficial.

☑ CE oficiales.

☑ RA1.b/g excluidos.

☑ 8 periodos.

☑ Punto de partida profesional.

☑ Hardware/software.

☑ Fuente/objeto/ejecutable.

☑ Flujo nativo.

☑ Bytecode.

☑ JVM.

☑ JIT contextualizado.

☑ Lenguajes clasificados.

☑ Herramientas.

☑ Laboratorio JDK.

☑ javac.

☑ java.

☑ javap.

☑ Pedido como caso integrador.

☑ Actividades A01.1–3.

☑ P01.1.

☑ I-RA1-01.

☑ Evidencias codificadas.

☑ Rúbrica por CE.

☑ Consolidación.

☑ Ampliación no evaluable.

☑ Glosario.

☑ Autoevaluación.

☑ Soluciones profesor.

☑ Recuperación.

☑ Trazabilidad.

☑ Control de aislamiento.

☑ Numeración editorial limpia.

☑ Sin numeración heredada de borrador.
```

# UD01 — ESTADO EDITORIAL

**Currículo:** cerrado  
**Contenido:** cerrado  
**Evaluación:** cerrada  
**Material alumno:** publicable  
**Material profesor:** publicable  
**Estado:** **UNIDAD PILOTO VALIDADA**