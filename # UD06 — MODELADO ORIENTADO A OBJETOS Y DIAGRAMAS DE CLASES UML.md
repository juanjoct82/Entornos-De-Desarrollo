# UD06 — MODELADO ORIENTADO A OBJETOS Y DIAGRAMAS DE CLASES UML

**Módulo profesional:** 0487 – Entornos de Desarrollo  
**Ciclos:** 1.º DAM / 1.º DAW  
**Centro:** Colegio Miralmonte – Cartagena  
**Curso:** 2026/2027  
**Temporalización:** 14 periodos lectivos  
**Resultado de Aprendizaje:** RA5  

**Prácticas evaluables:**  
P06.1 — Del requisito al modelo UML  
P06.2 — Del modelo al código y del código al modelo  

**Instrumentos:**  
I-RA5-01  
I-RA5-02  

**Herramienta CASE de referencia:** Umbrello UML Modeller 26.08.1  
**Lenguaje de apoyo:** Java  
**JDK:** Eclipse Temurin JDK 25 LTS  
**Estándar UML de referencia:** UML 2.5.1

---

# PARTE A — MATERIAL DEL ALUMNO

# 1. Punto de partida

Hasta ahora hemos trabajado con:

```text
código

IDE

Git

repositorios
```

Pero antes de escribir muchas clases conviene ser capaces de responder:

```text
¿Qué elementos existen en el problema?

¿Qué responsabilidades tiene cada uno?

¿Qué información almacena cada clase?

¿Qué operaciones ofrece?

¿Qué clases se relacionan?

¿Una clase contiene a otra?

¿Una clase hereda de otra?

¿Cuántos objetos pueden relacionarse?
```

Para representar estas respuestas utilizaremos:

# DIAGRAMAS DE CLASES UML.

---

# 2. Resultado de Aprendizaje

## RA5

**Genera diagramas de clases valorando su importancia en el desarrollo de aplicaciones y empleando herramientas específicas.**

---

# 3. Criterios de evaluación

En esta unidad se evalúan los seis criterios de RA5.

## RA5.a

**Se han identificado los conceptos básicos de la programación orientada a objetos.**

## RA5.b

**Se han utilizado herramientas para la elaboración de diagramas de clases.**

## RA5.c

**Se ha interpretado el significado de diagramas de clases.**

## RA5.d

**Se han trazado diagramas de clases a partir de las especificaciones de las mismas.**

## RA5.e

**Se ha generado código a partir de un diagrama de clases.**

## RA5.f

**Se ha generado un diagrama de clases mediante ingeniería inversa.**

---

# 4. Contenidos curriculares relacionados

El currículo establece expresamente contenidos como:

```text
clases

atributos

métodos

visibilidad

objetos

instanciación

asociaciones

navegabilidad

multiplicidad

herencia

composición

agregación

realización

dependencia

notación UML

herramientas

generación automática de código

ingeniería inversa
```

---

# 5. ¿Qué aprenderemos?

Al finalizar UD06 deberás poder:

- explicar clase y objeto;
- diferenciar clase e instancia;
- identificar atributos y operaciones;
- comprender encapsulación;
- interpretar visibilidad;
- comprender abstracción;
- reconocer herencia;
- comprender polimorfismo a nivel conceptual;
- reconocer interfaces;
- interpretar un diagrama de clases;
- utilizar multiplicidades;
- diferenciar asociación, dependencia, agregación y composición;
- representar generalización;
- representar realización de interfaces;
- transformar requisitos en clases;
- evitar crear clases innecesarias;
- asignar responsabilidades;
- elaborar diagramas mediante Umbrello;
- generar estructura Java desde UML;
- importar código Java a Umbrello;
- construir un diagrama desde las clases importadas;
- comprender los límites de la generación automática y la ingeniería inversa.

---

# 6. ¿Por qué modelar antes de programar?

Imaginemos un sistema de alquiler de vehículos.

Empezamos directamente:

```java
public class Coche {
}
```

Después creamos:

```java
public class Cliente {
}
```

Luego descubrimos:

```text
un cliente puede tener varios alquileres

un alquiler tiene un vehículo

hay coches y motos

el precio depende del vehículo

cada alquiler tiene fechas

un vehículo puede estar disponible o no
```

Si no pensamos en:

```text
estructura

responsabilidades

relaciones
```

podemos terminar con un diseño difícil de mantener.

---

# 7. UML

UML significa:

```text
Unified Modeling Language
```

Es un lenguaje estándar de modelado.

UML 2.5.1 continúa siendo la especificación formal publicada por OMG que utilizaremos como referencia conceptual.

UML permite representar diferentes perspectivas.

En esta unidad nos centraremos exclusivamente en:

# DIAGRAMAS DE CLASES.

---

# 8. Diagrama de clases

Un diagrama de clases representa:

```text
clases

atributos

operaciones

relaciones estructurales
```

de un sistema.

Es un diagrama:

```text
ESTÁTICO
```

porque representa estructura y no la secuencia temporal de llamadas entre objetos.

La documentación actual de Umbrello describe precisamente los diagramas de clases como representaciones de clases, atributos, operaciones y relaciones estáticas.

---

# 9. CONOCIMIENTO AUXILIAR NO EVALUADO

La secuencia temporal:

```text
objeto A
llama
objeto B
```

se modelará mediante diagramas de comportamiento en:

```text
RA6
UD08
```

No se evalúan aquí diagramas de secuencia.

---

# 10. Clase

Una clase describe un conjunto de objetos que comparten:

```text
estructura

comportamiento
```

Ejemplo:

```text
Cliente
```

puede definir:

```text
nombre
email
telefono
```

y operaciones como:

```text
reservar()
cancelarReserva()
```

---

# 11. Representación UML

Una clase suele representarse mediante tres compartimentos:

```text
┌─────────────────────────────┐
│ Cliente                     │
├─────────────────────────────┤
│ -nombre : String            │
│ -email : String             │
├─────────────────────────────┤
│ +reservar() : void          │
│ +cancelar() : void          │
└─────────────────────────────┘
```

---

# 12. Nombre de la clase

Utilizaremos habitualmente nombres:

```text
singulares

significativos

relacionados con el dominio
```

Buenos ejemplos:

```text
Cliente

Reserva

Vehiculo

Factura
```

Evita:

```text
Datos

Cosa

GestorGeneral

Clase1
```

cuando no expresan una responsabilidad concreta.

---

# 13. Objeto

Un objeto es una instancia concreta de una clase.

Clase:

```text
Cliente
```

Objetos:

```text
clienteJuanjo

clienteAna

clienteLaura
```

Conceptualmente:

```text
CLASE
Cliente
   │
   ├── objeto A
   ├── objeto B
   └── objeto C
```

---

# 14. Clase ≠ objeto

Incorrecto:

> La clase Juan es un Cliente.

Mejor:

```text
Cliente
→ clase

juan
→ objeto / instancia
```

---

# 15. Atributo

Un atributo representa información perteneciente al estado de una clase.

Ejemplo:

```text
Cliente
```

puede tener:

```text
nombre

email

telefono
```

Notación:

```text
visibilidad nombre : Tipo
```

Ejemplo:

```text
-nombre : String
```

---

# 16. Operación

Una operación representa comportamiento ofrecido por una clase.

Formato:

```text
visibilidad nombre(parámetros) : retorno
```

Ejemplo:

```text
+calcularPrecio(dias : int) : double
```

---

# 17. Visibilidad

Utilizaremos:

```text
+
public

-
private

#
protected

~
package
```

Ejemplo:

```text
-nombre : String

+getNombre() : String
```

---

# 18. Encapsulación

La encapsulación busca controlar cómo se accede y modifica el estado de un objeto.

En lugar de:

```java
cliente.saldo = -5000;
```

podemos ofrecer operaciones que controlen:

```text
qué cambios son válidos.
```

---

# 19. Error frecuente

No debemos interpretar:

```text
private
```

como:

> nadie puede usar el atributo.

Significa:

```text
el acceso directo
está restringido
según las reglas del lenguaje.
```

La clase puede ofrecer métodos para consultar o modificar ese estado.

---

# 20. Abstracción

Abstraer significa centrarse en:

```text
características relevantes
```

del problema e ignorar detalles innecesarios.

Para una aplicación de alquiler:

```text
Vehiculo
```

puede necesitar:

```text
matricula

marca

modelo

tarifaDiaria
```

y probablemente no necesitemos modelar:

```text
número exacto de tornillos

composición química de la pintura
```

---

# 21. Responsabilidad

Una buena pregunta al diseñar una clase es:

> ¿De qué debe responsabilizarse?

Ejemplo:

```text
Reserva
```

puede responsabilizarse de:

```text
fecha inicio

fecha fin

estado

duración
```

No necesariamente de:

```text
enviar correos

dibujar pantalla

conectar directamente
a cualquier base de datos
```

---

# 22. Herencia

La herencia permite definir una relación:

```text
"es un tipo de"
```

Ejemplo:

```text
Vehiculo
   ▲
   │
 ┌─┴──────────┐
 │            │
Coche        Moto
```

Podemos decir:

```text
Coche es un Vehiculo

Moto es un Vehiculo
```

---

# 23. Generalización UML

UML representa la herencia mediante:

```text
GENERALIZACIÓN
```

con un triángulo vacío apuntando hacia la clase más general.

La documentación de Umbrello utiliza esta misma representación.

---

# 24. Código equivalente

```java
public abstract class Vehiculo {
}
```

```java
public class Coche extends Vehiculo {
}
```

```java
public class Moto extends Vehiculo {
}
```

---

# 25. No usar herencia solo para reutilizar código

Pregunta correcta:

> ¿Existe realmente una relación conceptual “es un”?

No:

> ¿Puedo ahorrarme copiar tres métodos?

La herencia modela una relación de clasificación.

---

# 26. Polimorfismo

Podemos trabajar con objetos diferentes mediante un tipo común.

Ejemplo:

```java
Vehiculo vehiculo;
```

podría referirse en distintos momentos a:

```text
Coche

Moto
```

si la jerarquía lo permite.

En esta unidad solo necesitamos comprender el concepto.

La implementación avanzada pertenece al módulo de Programación.

---

# 27. Interface

Una interface define un contrato de operaciones.

Ejemplo conceptual:

```text
<<interface>>
Facturable
----------------
+calcularImporte() : double
```

Una clase puede:

```text
REALIZAR
```

esa interfaz.

---

# 28. Realización

Ejemplo:

```text
<<interface>>
Facturable
       △
       ┆
       ┆
    Reserva
```

La línea discontinua con triángulo vacío representa una:

```text
realización.
```

---

# 29. Asociación

Una asociación representa una relación estructural entre clases.

Ejemplo:

```text
Cliente ───────── Reserva
```

Podemos indicar:

```text
roles

navegabilidad

multiplicidad.
```

---

# 30. Multiplicidad

La multiplicidad indica cuántos objetos pueden participar en una relación.

Valores comunes:

```text
1
0..1
*
0..*
1..*
```

Ejemplo:

```text
Cliente 1 ───────── 0..* Reserva
```

Interpretación:

```text
un cliente
puede tener cero o muchas reservas

cada reserva
pertenece a un cliente
```

si así lo establece el modelo.

---

# 31. Cómo leer una multiplicidad

Pregunta:

> ¿Cuántos objetos de esta clase pueden relacionarse con un objeto del otro extremo?

No leas una relación únicamente:

```text
de izquierda a derecha.
```

Lee ambos extremos.

---

# 32. Actividad A06.1 — Multiplicidades

Interpreta:

```text
Departamento 1 ─────── 0..* Empleado
```

Responde:

1. ¿Cuántos departamentos tiene un empleado según el modelo?
2. ¿Cuántos empleados puede tener un departamento?
3. ¿Podría existir un departamento sin empleados?

---

# 33. Navegabilidad

La navegabilidad puede expresar que una clase conoce o mantiene acceso a otra.

Ejemplo conceptual:

```text
Pedido ────────> Cliente
```

No debemos convertir todas las asociaciones automáticamente en:

```text
bidireccionales.
```

Pregúntate:

> ¿Qué objeto necesita conocer a cuál?

---

# 34. Asociación no significa necesariamente atributo literal

Un diagrama representa diseño conceptual.

Una asociación puede terminar implementándose mediante:

```text
referencia

colección

identificador

servicio

estructura diferente
```

según la solución técnica.

---

# 35. Agregación

Una agregación representa una relación:

```text
todo-parte
```

relativamente débil.

Se dibuja mediante:

```text
rombo vacío
```

en el extremo del todo.

Ejemplo clásico:

```text
Equipo ◇──── Jugador
```

---

# 36. Composición

La composición representa una relación todo-parte más fuerte.

Se dibuja mediante:

```text
rombo relleno.
```

Conceptualmente, la vida de la parte está fuertemente ligada al todo.

Ejemplo:

```text
Pedido ◆──── LineaPedido
```

Si eliminamos conceptualmente:

```text
Pedido
```

sus:

```text
LineaPedido
```

no tienen sentido independiente en ese modelo.

La documentación de Umbrello distingue agregación y composición precisamente por la fuerza de la relación todo-parte.

---

# 37. No abusar de la agregación

Una asociación normal suele ser suficiente.

No uses:

```text
agregación
```

solo porque:

> una clase “tiene” otra.

Debemos justificar el significado:

```text
todo-parte.
```

---

# 38. Composición ≠ “atributo dentro de clase”

Que Java tenga:

```java
private Cliente cliente;
```

no demuestra automáticamente:

```text
composición UML.
```

Debemos analizar el ciclo de vida conceptual de ambos elementos.

---

# 39. Dependencia

Una dependencia representa una relación más débil:

```text
una clase utiliza otra
```

sin mantener necesariamente una relación estructural permanente.

Ejemplo:

```java
public void imprimir(GeneradorPdf generador) {
}
```

Podemos modelar una dependencia:

```text
ServicioReserva - - - -> GeneradorPdf
```

---

# 40. Asociación vs dependencia

## Asociación

```text
forma parte estable
de la estructura del modelo
```

## Dependencia

```text
uso puntual
o relación menos fuerte
```

---

# 41. Actividad A06.2 — Tipo de relación

Clasifica razonadamente:

```text
Coche → Vehiculo

Pedido → LineaPedido

Profesor → Departamento

ServicioInforme → GeneradorPdf

Reserva → Cliente

Factura → Facturable
```

entre:

```text
generalización

asociación

agregación

composición

dependencia

realización
```

Puede existir más de una solución defendible en algunos dominios.

Debes justificar.

---

# 42. Diagramas de clases como lenguaje de comunicación

Un diagrama permite que:

```text
analista

programador

profesor

compañero
```

puedan discutir la estructura sin leer primero cientos de líneas de código.

---

# 43. Diagrama no es decoración

No se evalúa:

```text
que quede bonito.
```

Se evalúa:

```text
que represente correctamente
el modelo.
```

---

# 44. Herramienta CASE

Utilizaremos:

# Umbrello UML Modeller 26.08.1

Umbrello permite crear diagramas de clases, casos de uso, secuencia, comunicación, estados, actividades y otros diagramas UML. La versión 26.08.1 fue publicada el 10 de septiembre de 2026.

---

# 45. CAPTURA UD06-01 — Umbrello

Debe mostrar:

```text
Umbrello 26.08.1

vista del modelo

árbol del proyecto

área de diagrama.
```

---

# 46. Crear un diagrama de clases

En Umbrello:

```text
New
→ Class Diagram
```

o acción equivalente en la interfaz.

El nombre debe ser significativo.

Ejemplo:

```text
ModeloReservas
```

---

# 47. CAPTURA UD06-02 — Class Diagram

Debe mostrar:

```text
nuevo diagrama de clases

barra de herramientas UML

árbol del modelo.
```

---

# 48. Crear una clase

Clase:

```text
Cliente
```

Añadimos:

```text
atributos

operaciones

visibilidad

tipos.
```

Resultado:

```text
Cliente
-------------------------
-id : long
-nombre : String
-email : String
-------------------------
+getNombre() : String
```

---

# 49. CAPTURA UD06-03 — Propiedades de clase

Debe mostrar las propiedades de una clase y la edición de:

```text
atributos

operaciones

visibilidad

tipos.
```

---

# 50. Interpretar un diagrama

Antes de crear modelos debemos saber leerlos.

Ejemplo:

```text
┌──────────────────┐
│ Cliente          │
├──────────────────┤
│ -id : long       │
│ -nombre : String │
└─────────┬────────┘
          │ 1
          │
          │ 0..*
┌─────────▼────────┐
│ Reserva          │
├──────────────────┤
│ -inicio : Date   │
│ -fin : Date      │
└──────────────────┘
```

Podemos interpretar:

```text
existen dos clases

Cliente almacena id/nombre

Reserva almacena fechas

un cliente puede tener
varias reservas

cada reserva se vincula
con un cliente
```

---

# 51. Procedimiento para interpretar

Al recibir un diagrama:

## Paso 1

Identifica:

```text
clases e interfaces.
```

## Paso 2

Lee:

```text
atributos

operaciones

visibilidad.
```

## Paso 3

Identifica:

```text
relaciones.
```

## Paso 4

Lee:

```text
multiplicidades.
```

## Paso 5

Comprueba:

```text
generalizaciones

realizaciones

todo-parte

dependencias.
```

## Paso 6

Reconstruye:

```text
el significado del dominio.
```

---

# 52. Actividad A06.3 — Lee el modelo

El profesor entrega un diagrama con:

```text
Biblioteca

Socio

Prestamo

Ejemplar

Libro
```

Debes responder:

- clases existentes;
- atributos principales;
- relaciones;
- multiplicidades;
- herencia si existe;
- composición/agregación si existe;
- interpretación completa del modelo.

---

# 53. De requisitos a clases

Ahora realizaremos el proceso inverso.

Partimos de texto:

> Un centro deportivo gestiona socios. Cada socio puede realizar varias reservas. Cada reserva corresponde a una actividad. Las actividades tienen un monitor responsable.

No empezamos dibujando líneas al azar.

---

# 54. Paso 1 — identificar conceptos del dominio

Posibles candidatos:

```text
Socio

Reserva

Actividad

Monitor
```

---

# 55. No todos los sustantivos se convierten en clases

Texto:

> El sistema muestra un mensaje al usuario.

No necesitamos necesariamente:

```text
Clase Mensaje
```

ni:

```text
Clase Sistema.
```

Una clase debe representar:

```text
concepto relevante

con estado/comportamiento

o responsabilidad real.
```

---

# 56. Paso 2 — asignar atributos

Socio:

```text
id

nombre

email
```

Actividad:

```text
nombre

aforo
```

Reserva:

```text
fecha

estado
```

---

# 57. Paso 3 — asignar responsabilidades

Ejemplo:

```text
Reserva
```

podría tener:

```text
cancelar()

confirmar()
```

Pero debemos evitar:

```text
setDato1()

setDato2()

hacerTodo()
```

sin significado del dominio.

---

# 58. Paso 4 — relaciones

Texto:

> Un socio puede realizar varias reservas.

Modelo:

```text
Socio 1 ───────── 0..* Reserva
```

---

# 59. Paso 5 — revisar multiplicidades

Pregúntate:

```text
¿una reserva puede existir
sin socio?

¿puede una actividad
no tener reservas?

¿puede un monitor
dirigir varias actividades?
```

Las multiplicidades deben salir de los requisitos, no de:

```text
lo que dibuja Umbrello por defecto.
```

---

# 60. Paso 6 — comprobar redundancias

Si tenemos:

```text
Cliente

UsuarioCliente

DatosCliente
```

puede existir duplicación conceptual.

Debemos revisar responsabilidades.

---

# 61. Paso 7 — validar contra requisitos

Cada elemento importante del requisito debe poder localizarse en:

```text
clase

atributo

operación

relación

restricción
```

del modelo.

---

# 62. Caso guiado — Miralmonte Reservas

Requisitos:

```text
El colegio dispone de espacios.

Un espacio puede ser aula
o laboratorio.

Un profesor puede realizar reservas.

Cada reserva corresponde
a un único espacio.

Un espacio puede tener
muchas reservas.

Cada reserva posee
fecha, hora de inicio
y hora de fin.

Los laboratorios tienen
número de puestos.
```

---

# 63. Clases candidatas

```text
Profesor

Espacio

Aula

Laboratorio

Reserva
```

---

# 64. Generalización

```text
Espacio
   ▲
 ┌─┴───────────┐
Aula      Laboratorio
```

Porque:

```text
Aula es un Espacio

Laboratorio es un Espacio.
```

---

# 65. Asociaciones

```text
Profesor 1 ─────── 0..* Reserva

Espacio 1 ──────── 0..* Reserva
```

---

# 66. Modelo conceptual

```text
             Espacio
           /         \
        Aula       Laboratorio

Profesor ───── Reserva ───── Espacio
```

con las multiplicidades correspondientes.

---

# 67. Actividad A06.4 — Modela Miralmonte Reservas

Construye en Umbrello:

```text
Profesor

Espacio

Aula

Laboratorio

Reserva
```

Añade:

```text
atributos

operaciones necesarias

generalización

asociaciones

multiplicidades.
```

Exporta el diagrama como imagen o PDF.

---

# 68. CAPTURA UD06-04 — Relaciones

Debe mostrar:

```text
asociación

generalización

multiplicidad
```

en un mismo diagrama.

---

# 69. Association end y multiplicidad

Cuando configures una asociación en Umbrello debes comprobar:

```text
multiplicidad extremo A

multiplicidad extremo B

rol

navegabilidad
```

y no aceptar automáticamente los valores iniciales.

---

# 70. Error frecuente — multiplicidades al revés

Supongamos:

```text
Cliente 1 ─── * Pedido
```

El:

```text
*
```

situado cerca de:

```text
Pedido
```

indica cuántos pedidos pueden asociarse a un cliente.

No significa:

> muchos clientes por pedido.

---

# 71. Error frecuente — clases como tablas

UML orientado a objetos no consiste simplemente en:

```text
crear una clase
por cada tabla imaginaria.
```

Estamos modelando:

```text
objetos

responsabilidades

relaciones.
```

---

# 72. Error frecuente — todas las clases con getters/setters

Un diagrama no mejora por contener:

```text
30 getters

30 setters
```

que ocultan las operaciones importantes.

Representa aquellas operaciones relevantes para:

```text
comprender el diseño.
```

---

# 73. Error frecuente — flechas decorativas

No añadas relaciones porque:

```text
"queda conectado".
```

Cada relación debe tener un significado.

---

# 74. Error frecuente — composición indiscriminada

Incorrecto:

```text
Cliente ◆──── Reserva
```

solo porque:

```text
el cliente tiene reservas.
```

Pregunta:

> ¿La reserva pertenece existencialmente al cliente de tal manera que no puede tener sentido fuera de él en nuestro dominio?

Puede que la respuesta sea:

```text
no.
```

Entonces una asociación es más adecuada.

---

# 75. P01 — interpretar antes de dibujar

Una competencia importante de RA5.c es recibir modelos creados por otra persona.

En un equipo real:

```text
no todos los diagramas
los dibujas tú.
```

También debes:

```text
leerlos

discutirlos

detectar incoherencias.
```

---

# 76. Actividad A06.5 — Detecta errores

El profesor proporciona un diagrama que contiene errores como:

```text
multiplicidad incompatible

herencia incorrecta

composición injustificada

operación en clase equivocada

atributo redundante.
```

Localiza al menos cinco problemas y propón correcciones.

---

# 77. Modelo ↔ código

Hasta ahora hemos trabajado:

```text
REQUISITOS
↓
UML
```

Ahora veremos:

```text
UML
↓
CÓDIGO
```

Esto corresponde a:

# RA5.e.

---

# 78. Generación de código con Umbrello

Umbrello puede generar código fuente a partir del modelo UML.

La documentación actual indica que puede generar clases, atributos y operaciones para múltiples lenguajes, incluido Java, mediante:

```text
Code
→ Code Generation Wizard
```


---

# 79. Qué genera realmente

La generación automática produce principalmente:

```text
estructura

declaraciones

atributos

métodos
```

para ayudarnos a comenzar la implementación.

No genera mágicamente:

```text
toda la lógica de negocio

una aplicación terminada

una interfaz completa

una base de datos completa.
```

---

# 80. Ejemplo UML

Modelo:

```text
Cliente
------------------------
-nombre : String
-email : String
------------------------
+getNombre() : String
```

Puede generar una estructura Java equivalente a:

```java
public class Cliente {

    private String nombre;
    private String email;

    public String getNombre() {
        // TODO
        return null;
    }
}
```

La salida exacta depende de las opciones del generador.

---

# 81. CAPTURA UD06-05 — Code Generation Wizard

Debe mostrar:

```text
Code
→ Code Generation Wizard

clases seleccionadas

lenguaje Java

carpeta de salida.
```

---

# 82. Configuración de generación

Umbrello permite configurar aspectos como:

```text
lenguaje

carpeta de salida

comentarios

política de sobrescritura.
```

No utilizaremos opciones avanzadas innecesarias.

---

# 83. Actividad A06.6 — UML a Java

Crea:

```text
Cliente

Reserva

Espacio
```

en Umbrello.

Añade:

```text
atributos

operaciones

relaciones.
```

Genera Java.

Después compara:

```text
modelo
vs.
código generado.
```

Identifica:

```text
qué se ha generado

qué falta implementar.
```

---

# 84. Generación ≠ sincronización permanente

Modificar posteriormente:

```text
código Java
```

no implica que:

```text
el diagrama
```

se actualice automáticamente.

Tampoco debemos asumir que:

```text
modificar diagrama
```

reescribirá de forma segura cualquier código existente.

---

# 85. Round-trip engineering

El concepto ideal de:

```text
modelo ↔ código
```

perfectamente sincronizado se conoce habitualmente como:

```text
round-trip engineering.
```

Pero las herramientas presentan límites.

En este curso aprenderemos a:

```text
generar

importar

comparar
```

sin asumir sincronización bidireccional perfecta.

---

# 86. Ingeniería inversa

La ingeniería inversa sigue el sentido:

```text
CÓDIGO EXISTENTE
↓
MODELO
```

Nos permite comprender software que:

```text
ya está implementado.
```

---

# 87. Uso profesional

Imagina incorporarte a una aplicación con:

```text
200 clases
```

pero documentación incompleta.

La ingeniería inversa puede ayudar a:

```text
identificar clases

atributos

operaciones

relaciones
```

y construir una visión estructural inicial.

---

# 88. Ingeniería inversa ≠ comprender automáticamente el sistema

Una herramienta puede descubrir:

```text
estructura del código.
```

Pero no puede conocer automáticamente:

```text
decisiones de negocio

razones históricas

intención completa del diseño.
```

El desarrollador debe interpretar el resultado.

---

# 89. Importar código Java en Umbrello

Umbrello puede importar código fuente Java existente mediante:

```text
Code
→ Code Importing Wizard
```

El asistente analiza las declaraciones y crea elementos en el modelo.

---

# 90. Matiz fundamental

La documentación actual de Umbrello indica expresamente:

# IMPORTAR CÓDIGO NO CREA AUTOMÁTICAMENTE EL DIAGRAMA GRÁFICO.

Las clases importadas aparecen en:

```text
Tree View / árbol del modelo
```

y posteriormente pueden utilizarse en un diagrama.

---

# 91. Cómo cumpliremos RA5.f

Nuestro flujo será:

```text
CÓDIGO JAVA
     ↓
Code Importing Wizard
     ↓
CLASES IMPORTADAS
EN MODELO UMBRELLO
     ↓
NUEVO CLASS DIAGRAM
     ↓
INCORPORAR CLASES IMPORTADAS
     ↓
REVISAR RELACIONES
     ↓
DIAGRAMA OBTENIDO
MEDIANTE INGENIERÍA INVERSA
```

Así la fuente del modelo es:

# EL CÓDIGO EXISTENTE.

---

# 92. CAPTURA UD06-06 — Code Importing Wizard

Debe mostrar:

```text
Code
→ Code Importing Wizard

archivos Java

inicio de importación.
```

---

# 93. CAPTURA UD06-07 — Clases importadas

Debe mostrar:

```text
Tree View
```

con las clases Java importadas.

---

# 94. CAPTURA UD06-08 — Diagrama de ingeniería inversa

Debe mostrar:

```text
nuevo Class Diagram

clases importadas incorporadas

relaciones visibles.
```

---

# 95. Código para ingeniería inversa

Ejemplo:

```java
public abstract class Vehiculo {

    private String matricula;
    private double tarifaDiaria;

    public abstract double calcularPrecio(
            int dias);
}
```

```java
public class Coche extends Vehiculo {

    private int plazas;

    @Override
    public double calcularPrecio(
            int dias) {

        return dias * 50.0;
    }
}
```

```java
public class Moto extends Vehiculo {

    private boolean incluyeCasco;

    @Override
    public double calcularPrecio(
            int dias) {

        return dias * 30.0;
    }
}
```

---

# 96. Qué debería descubrir la herramienta

Al importar debería reconocer al menos:

```text
Vehiculo

Coche

Moto

atributos

operaciones

generalización
```

según la información disponible y las capacidades del importador.

---

# 97. No exigir perfección automática

Si una relación semántica no puede inferirse con precisión desde el código:

```text
el alumno debe detectarlo
y explicarlo.
```

RA5.f no consiste en:

```text
pulsar Import
sin mirar el resultado.
```

---

# 98. Actividad A06.7 — Ingeniería inversa guiada

Se proporciona un pequeño proyecto Java con:

```text
Cliente

Reserva

Espacio

Aula

Laboratorio
```

El alumno:

1. importa el código;
2. identifica clases importadas;
3. crea un Class Diagram;
4. incorpora las clases;
5. organiza el diagrama;
6. identifica relaciones;
7. compara con el fuente;
8. documenta limitaciones.

---

# 99. Dos sentidos

## Forward engineering

```text
UML
↓
código
```

## Reverse engineering

```text
código
↓
modelo UML
```

---

# 100. ¿Cuál es mejor?

No son alternativas excluyentes.

Se utilizan en momentos diferentes.

Proyecto nuevo:

```text
requisitos
↓
diseño
↓
código
```

Proyecto existente:

```text
código
↓
modelo
↓
comprensión/documentación
```

---

# 101. Caso profesional de evaluación — CartagoRent

CartagoRent necesita un sistema para alquilar vehículos.

Requisitos:

```text
La empresa dispone de vehículos.

Los vehículos pueden ser coches
o motocicletas.

Todos tienen:
matrícula,
marca,
modelo
y tarifa diaria.

Los coches tienen número de plazas.

Las motos indican si incluyen casco.

Existen clientes.

Un cliente puede realizar
varios alquileres.

Cada alquiler pertenece
a un único cliente.

Cada alquiler corresponde
a un único vehículo.

Un vehículo puede participar
en múltiples alquileres
a lo largo del tiempo.

Cada alquiler tiene:
fecha de inicio,
fecha de fin
y estado.

El alquiler debe poder
calcular su duración.
```

---

# 102. Análisis inicial

Clases candidatas:

```text
Vehiculo

Coche

Moto

Cliente

Alquiler
```

---

# 103. Generalización

```text
              Vehiculo
              ▲      ▲
              │      │
           Coche    Moto
```

---

# 104. Asociaciones

```text
Cliente 1 ───── 0..* Alquiler

Vehiculo 1 ───── 0..* Alquiler
```

Cada:

```text
Alquiler
```

se relaciona con:

```text
1 Cliente

1 Vehiculo.
```

---

# 105. Actividad A06.8 — Prepara CartagoRent

Antes de la práctica:

```text
subraya sustantivos

descarta candidatos irrelevantes

asigna atributos

asigna operaciones

define relaciones

define multiplicidades.
```

No utilices todavía Umbrello.

---

# 106. PRÁCTICA EVALUABLE P06.1

# DEL REQUISITO AL MODELO — CARTAGORENT

**Modalidad:** individual  
**RA:** RA5  
**CE:** RA5.a, RA5.b, RA5.c, RA5.d  
**Instrumento:** I-RA5-01

---

# 107. Objetivo

Demostrar que puedes:

```text
identificar conceptos POO

interpretar UML

usar una herramienta CASE

transformar requisitos
en un diagrama de clases.
```

---

# 108. Tarea A — Conceptos POO

Para CartagoRent identifica y explica con ejemplos del caso:

```text
clase

objeto

atributo

operación

encapsulación

abstracción

herencia

polimorfismo

interface
```

Cuando un concepto no sea necesario en el modelo final:

```text
indícalo
```

en lugar de forzarlo.

**CE:** RA5.a

---

# 109. Tarea B — Interpretación

El profesor proporciona un diagrama diferente:

```text
CartagoLibrary
```

con al menos:

```text
5 clases

asociaciones

multiplicidades

generalización

composición o agregación

dependencia/realización
```

Debes elaborar un informe explicando:

```text
qué representa cada clase

qué significan los atributos

qué significan las operaciones

cómo se relacionan

qué indican las multiplicidades

qué restricciones se deducen.
```

**CE:** RA5.c

---

# 110. Tarea C — Identificación del modelo

Desde los requisitos de CartagoRent:

1. identifica clases;
2. descarta falsos candidatos;
3. define responsabilidades;
4. define atributos;
5. define operaciones;
6. define relaciones;
7. define multiplicidades;
8. justifica herencia.

**CE:** RA5.d

---

# 111. Tarea D — Umbrello

Construye:

```text
CartagoRent
```

en:

```text
Umbrello 26.08.1
```

El diagrama debe contener como mínimo:

```text
Vehiculo

Coche

Moto

Cliente

Alquiler
```

y las relaciones necesarias.

**CE:** RA5.b y RA5.d

---

# 112. Tarea E — Notación

Utiliza correctamente:

```text
visibilidad

tipos

atributos

operaciones

generalización

asociaciones

multiplicidades.
```

No añadas:

```text
agregación

composición

dependencia

interface
```

si no son necesarias.

La precisión es más importante que:

```text
usar todas las relaciones UML.
```

---

# 113. Tarea F — Validación

Para cada requisito original señala:

```text
qué elemento del modelo
lo representa.
```

Tabla:

| Requisito | Elemento UML |
|---|---|
| vehículos coche/moto | |
| matrícula | |
| plazas | |
| casco | |
| cliente varios alquileres | |
| alquiler un vehículo | |
| fechas | |

---

# 114. Entregable P06.1

```text
P06.1_Apellidos_Nombre.pdf
```

más:

```text
P06.1_Apellidos_Nombre.xmi
```

o fichero nativo de Umbrello según configuración.

Debe contener:

```text
análisis

interpretación

diagrama

justificación

trazabilidad requisitos-modelo.
```

---

# 115. Evidencias P06.1

## RA5.a

```text
E-RA5.a-01
Identificación razonada
de conceptos POO.

E-RA5.a-02
Aplicación al dominio.
```

## RA5.b

```text
E-RA5.b-01
Modelo creado en Umbrello.

E-RA5.b-02
Uso correcto de elementos
y propiedades de la herramienta.
```

## RA5.c

```text
E-RA5.c-01
Interpretación de CartagoLibrary.

E-RA5.c-02
Lectura de multiplicidades
y relaciones.
```

## RA5.d

```text
E-RA5.d-01
Análisis de especificaciones.

E-RA5.d-02
Diagrama CartagoRent.

E-RA5.d-03
Trazabilidad requisito-modelo.
```

---

# 116. Instrumento I-RA5-01

**RA:** RA5  
**CE:** RA5.a, b, c, d  
**Actividad:** P06.1  
**Tipo:** análisis y modelado UML individual

Cada CE obtiene:

```text
NOTA 0–10
```

de forma independiente.

---

# 117. Rúbrica definitiva I-RA5-01

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA5.a** | Identifica conceptos básicos de POO y los relaciona con el dominio | Confunde clase/objeto, atributos, operaciones o relaciones fundamentales | Reconoce los conceptos esenciales con ejemplos sencillos | Identifica correctamente abstracción, encapsulación, herencia, polimorfismo, clases, objetos e interfaces y los aplica al caso | Además justifica cuándo un concepto aporta valor y evita aplicar herencia/interfaces artificialmente | **100 % del CE** |
| **RA5.b** | Utiliza una herramienta específica para elaborar diagramas de clases | No consigue construir un modelo funcional o utiliza la herramienta de forma incorrecta | Crea clases y algunas relaciones con ayuda | Utiliza Umbrello correctamente para clases, atributos, operaciones, relaciones y multiplicidades | Además mantiene un modelo limpio, consistente, organizado y editable, utilizando propiedades de la herramienta con autonomía | **100 % del CE** |
| **RA5.c** | Interpreta el significado de diagramas de clases | No comprende elementos o relaciones esenciales | Reconoce clases, atributos y asociaciones básicas | Interpreta correctamente clases, visibilidades, operaciones, multiplicidades, herencia y relaciones | Además deduce restricciones, detecta incoherencias y reconstruye con precisión el dominio representado | **100 % del CE** |
| **RA5.d** | Traza un diagrama de clases a partir de especificaciones | El modelo contradice los requisitos o contiene clases/relaciones arbitrarias | Representa la mayor parte de los conceptos con algunas imprecisiones | Traduce correctamente requisitos a clases, atributos, operaciones, relaciones y multiplicidades | Además justifica alternativas de diseño, elimina redundancias y mantiene trazabilidad completa requisito-modelo | **100 % del CE** |

---

# 118. Nota informativa de P06.1

```text
(
 RA5.a
+RA5.b
+RA5.c
+RA5.d
) / 4
```

Solo como resumen informativo.

---

# 119. PRÁCTICA EVALUABLE P06.2

# DEL MODELO AL CÓDIGO Y DEL CÓDIGO AL MODELO

**Modalidad:** individual  
**RA:** RA5  
**CE:** RA5.e, RA5.f  
**Instrumento:** I-RA5-02

---

# 120. Parte A — UML → Java

Utiliza un modelo proporcionado por el profesor:

```text
MiralmonteMaterial
```

con:

```text
Material

Portatil

Tablet

Alumno

Prestamo
```

No se utilizará el mismo modelo de P06.1 para evitar limitar la práctica a repetir pasos memorizados.

---

# 121. Tarea RA5.e — revisar modelo

Antes de generar código comprueba:

```text
clases

atributos

operaciones

visibilidad

generalización

relaciones.
```

---

# 122. Configurar Java

En Umbrello selecciona:

```text
Java
```

como lenguaje de generación.

Configura:

```text
carpeta de salida
```

separada.

---

# 123. Generar código

Utiliza:

```text
Code
→ Code Generation Wizard
```

Selecciona las clases.

Genera.

---

# 124. Analizar el resultado

Para cada clase comprueba:

```text
archivo generado

nombre de clase

atributos

tipos

métodos

herencia/interfaces
```

cuando proceda.

---

# 125. No completar lógica antes de analizar

Primero debemos observar:

```text
qué produjo Umbrello.
```

Después podremos compilar o realizar pequeños ajustes.

No queremos confundir:

```text
código generado
```

con:

```text
código escrito manualmente.
```

---

# 126. Compilación de comprobación

Importa el código generado a un pequeño proyecto Java y comprueba:

```text
estructura

sintaxis

correspondencia
```

con Temurin 25.

No se evalúa programación avanzada.

---

# 127. Evidencias RA5.e

```text
E-RA5.e-01
Modelo UML origen.

E-RA5.e-02
Code Generation Wizard.

E-RA5.e-03
Archivos Java generados.

E-RA5.e-04
Comparación UML ↔ Java.

E-RA5.e-05
Análisis de límites.
```

---

# 128. Parte B — Java → UML

El profesor proporciona:

```text
CartagoHotelCode
```

con clases Java desconocidas previamente.

Ejemplo de estructura:

```text
Habitacion

HabitacionEstandar

Suite

Cliente

ReservaHotel
```

---

# 129. Regla

No se proporciona:

```text
diagrama UML previo.
```

El punto de partida debe ser:

# EL CÓDIGO.

---

# 130. Importar código

En Umbrello:

```text
Code
→ Code Importing Wizard
```

selecciona:

```text
.java
```

del proyecto.

Ejecuta la importación.

---

# 131. Verificar Tree View

Comprueba que aparecen:

```text
clases

atributos

operaciones

relaciones detectadas
```

en el modelo.

---

# 132. Crear el diagrama

Crea:

```text
Class Diagram
```

denominado:

```text
CartagoHotelReverse
```

Incorpora desde:

```text
Tree View
```

las clases importadas.

---

# 133. Organizar

Distribuye las clases para facilitar:

```text
lectura de herencia

asociaciones

multiplicidades detectables.
```

No ocultes relaciones importantes para:

```text
hacerlo bonito.
```

---

# 134. Contrastar con el fuente

Comprueba manualmente:

```text
extends

implements

atributos que referencian otras clases

colecciones

métodos
```

y compara con el modelo generado/importado.

---

# 135. Informe de limitaciones

Identifica al menos:

```text
2 aspectos
```

que la ingeniería inversa:

```text
representa bien

o

no permite deducir perfectamente.
```

Ejemplo:

```text
intención de negocio

composición conceptual

multiplicidad exacta
```

pueden requerir interpretación humana.

---

# 136. Evidencias RA5.f

```text
E-RA5.f-01
Proyecto Java origen.

E-RA5.f-02
Code Importing Wizard.

E-RA5.f-03
Clases importadas en Tree View.

E-RA5.f-04
Diagrama construido
con elementos importados.

E-RA5.f-05
Comparación código-modelo.

E-RA5.f-06
Limitaciones documentadas.
```

---

# 137. Entregables P06.2

```text
P06.2_Apellidos_Nombre.pdf
```

más:

```text
modelo UML origen

Java generado

modelo de ingeniería inversa
```

cuando la plataforma lo permita.

---

# 138. Instrumento I-RA5-02

**RA:** RA5  
**CE:** RA5.e, RA5.f  
**Actividad:** P06.2  
**Tipo:** laboratorio CASE individual

Cada CE se califica:

```text
0–10
```

por separado.

---

# 139. Rúbrica definitiva I-RA5-02

| CE | Indicador observable | Insuficiente | Básico | Adecuado | Avanzado | Peso |
|---|---|---|---|---|---|---:|
| **RA5.e** | Genera código a partir de un diagrama de clases | No consigue generar código coherente o no puede relacionarlo con el modelo | Obtiene archivos básicos con ayuda | Configura Umbrello, genera correctamente Java y relaciona clases, atributos, operaciones y herencia con el modelo | Además verifica críticamente el resultado, distingue estructura generada de lógica no implementada y explica límites del forward engineering | **100 % del CE** |
| **RA5.f** | Genera un diagrama de clases mediante ingeniería inversa | No consigue obtener un modelo útil desde el código o dibuja un modelo sin utilizar la importación | Importa parte del código y obtiene elementos básicos con ayuda | Importa correctamente Java, crea el diagrama desde los elementos del modelo importado y verifica su correspondencia con el fuente | Además detecta relaciones/limitaciones que requieren interpretación humana y explica con precisión qué información puede y no puede reconstruirse automáticamente | **100 % del CE** |

---

# 140. Nota informativa de P06.2

```text
(
 RA5.e
+RA5.f
) / 2
```

Solo para mostrar un resumen de la entrega.

---

# 141. Temporalización definitiva

| Sesión | Contenido | Actividad |
|---:|---|---|
| 1 | Clase, objeto, atributos, operaciones, encapsulación | A06.1 |
| 2 | Abstracción, herencia, polimorfismo, interfaces | ejemplos guiados |
| 3 | Asociaciones, navegabilidad y multiplicidad | A06.1 |
| 4 | Agregación, composición, dependencia y realización | A06.2 |
| 5 | Interpretación de diagramas | A06.3 |
| 6 | Umbrello: clases, propiedades y relaciones | A06.4 |
| 7 | Requisitos → clases y responsabilidades | Miralmonte Reservas |
| 8 | Detección de errores y refinamiento | A06.5 |
| 9 | P06.1 — análisis e interpretación | evaluación |
| 10 | P06.1 — elaboración de modelo | I-RA5-01 |
| 11 | Generación automática de código | A06.6 |
| 12 | Ingeniería inversa | A06.7 |
| 13 | P06.2 — UML → Java | I-RA5-02 |
| 14 | P06.2 — Java → UML y cierre | I-RA5-02 |

**Total: 14 periodos.**

---

# 142. Resumen

RA5 cubre el flujo:

```text
PROGRAMACIÓN ORIENTADA A OBJETOS
           ↓
      MODELO UML
           ↓
 INTERPRETACIÓN / DISEÑO
           ↓
          CÓDIGO
```

y también:

```text
CÓDIGO EXISTENTE
      ↓
INGENIERÍA INVERSA
      ↓
MODELO UML
```

---

# 143. Glosario

**Abstracción:** selección de características relevantes de un concepto.

**Agregación:** relación todo-parte débil representada mediante rombo vacío.

**Asociación:** relación estructural entre clases.

**Atributo:** información que forma parte del estado de una clase.

**Clase:** descripción común de un conjunto de objetos.

**Composición:** relación todo-parte fuerte representada con rombo relleno.

**Dependencia:** relación de uso relativamente débil entre elementos.

**Encapsulación:** control del acceso al estado y comportamiento de un objeto.

**Forward engineering:** generación o creación de implementación desde un modelo.

**Generalización:** relación UML utilizada para representar herencia.

**Ingeniería inversa:** obtención de un modelo a partir de software existente.

**Interface:** contrato de operaciones que puede ser realizado por clases.

**Multiplicidad:** cantidad de instancias que pueden participar en una asociación.

**Navegabilidad:** dirección conceptual de conocimiento/acceso en una relación.

**Objeto:** instancia concreta de una clase.

**Operación:** comportamiento definido por una clase.

**Polimorfismo:** capacidad de trabajar con distintas implementaciones mediante un tipo común.

**Realización:** relación entre una implementación y una especificación/interfaz.

**UML:** Unified Modeling Language.

---

# 144. Autoevaluación

### 1
Una clase es:

A. una instancia concreta  
B. una descripción de objetos con estructura/comportamiento común  
C. un commit  
D. una JVM

### 2
Un objeto es:

A. una instancia  
B. un paquete UML  
C. un IDE  
D. una rama Git

### 3
`-nombre:String` indica:

A. atributo privado  
B. método público  
C. herencia  
D. composición

### 4
`1..*` representa:

A. una multiplicidad  
B. visibilidad  
C. herencia  
D. interfaz

### 5
La generalización representa habitualmente:

A. herencia  
B. dependencia temporal  
C. commit  
D. ejecución

### 6
El rombo relleno representa:

A. composición  
B. generalización  
C. dependencia  
D. realización

### 7
La línea discontinua con triángulo hacia una interface representa:

A. realización  
B. composición  
C. asociación simple  
D. agregación

### 8
RA5.e exige:

A. código desde diagrama  
B. depuración  
C. Git  
D. testing

### 9
RA5.f exige:

A. diagrama mediante ingeniería inversa  
B. CI  
C. GitHub  
D. Scrum

### 10
Al importar código con Umbrello:

A. siempre aparece automáticamente un diagrama perfecto  
B. las clases se importan al modelo y después pueden utilizarse en un diagrama  
C. se elimina el código  
D. se crea un workflow

---

# 145. Soluciones de autoevaluación

```text
1 → B
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

# 146. Finalidad docente

El objetivo no es que el alumno memorice:

```text
triángulo

rombo

flecha
```

sin entenderlos.

Debe poder pasar:

```text
REQUISITO
↓
CONCEPTO
↓
CLASE
↓
RELACIÓN
↓
DIAGRAMA
```

y también:

```text
DIAGRAMA
↓
INTERPRETACIÓN
```

---

# 147. Orden pedagógico

Conviene introducir:

```text
clase/objeto
↓
atributos/operaciones
↓
visibilidad
↓
asociación
↓
multiplicidad
↓
herencia
↓
interfaces
↓
todo-parte
↓
dependencia
```

y no comenzar mostrando:

```text
20 tipos de flecha UML.
```

---

# 148. Polimorfismo

RA5.a pide conceptos básicos de POO.

No se necesita aquí:

```text
programar jerarquías complejas.
```

Es suficiente comprender por qué:

```text
Vehiculo
```

puede ser el tipo común de:

```text
Coche

Moto.
```

---

# 149. Composición/agregación

No penalizar automáticamente una asociación normal cuando el texto no exige realmente todo-parte.

Sí penalizar:

```text
utilizar composición
sin justificar ciclo de vida
```

cuando contradiga el dominio.

---

# 150. Herramienta

La herramienta elegida queda definitivamente:

# Umbrello 26.08.1

porque permite cubrir en una sola herramienta:

```text
RA5.b

RA5.d

RA5.e

RA5.f.
```

La aplicación oficial de KDE confirma tanto diagramas de clases como generación de código.

---

# 151. Corrección importante frente a versiones anteriores

No utilizar como requisito de RA5.f:

```text
IntelliJ Java Class Diagram
```

porque su disponibilidad puede depender de:

```text
edición

plugins

características del producto.
```

El flujo definitivo será exclusivamente:

```text
Java
↓
Umbrello Code Import
↓
modelo importado
↓
Class Diagram.
```

---

# 152. Ingeniería inversa: criterio de corrección

No basta con:

```text
crear manualmente un diagrama
mirando el código.
```

Debe existir evidencia de:

```text
Code Importing Wizard
```

porque el CE exige ingeniería inversa mediante herramienta.

---

# 153. Pero tampoco basta con importar

El alumno debe:

```text
crear el diagrama

incorporar las clases importadas

organizarlo

compararlo con el fuente

interpretarlo.
```

---

# 154. Límite técnico documentado

Umbrello no crea automáticamente un diagrama al importar código.

Este comportamiento está expresamente documentado por KDE.

Por tanto, este paso:

```text
crear diagrama
+
arrastrar/incorporar
elementos importados
```

es deliberado y debe explicarse en clase.

---

# 155. Generación de código

Umbrello genera principalmente:

```text
declaraciones

atributos

operaciones
```

como punto de partida.

No valorar RA5.e según:

```text
si la aplicación final funciona.
```

Valorar:

```text
correspondencia
modelo → código.
```

---

# 156. Código generado

Si Umbrello genera:

```java
public class Cliente {
}
```

pero los métodos contienen:

```text
TODO
```

eso no significa que:

```text
la generación haya fallado.
```

La herramienta no tiene por qué conocer la implementación de la lógica.

---

# 157. CartagoRent — solución orientativa

Modelo mínimo:

```text
                    Vehiculo
              -matricula:String
              -marca:String
              -modelo:String
              -tarifaDiaria:double
                    ▲
             ┌──────┴───────┐
             │              │
           Coche           Moto
       -plazas:int   -incluyeCasco:boolean


Cliente 1 ───────── 0..* Alquiler 0..* ───────── 1 Vehiculo
```

Alquiler:

```text
-inicio: LocalDate
-fin: LocalDate
-estado: EstadoAlquiler
+calcularDuracion(): long
```

---

# 158. No exigir `EstadoAlquiler` como enum

Puede considerarse:

```text
String
```

en una solución básica.

En una solución avanzada puede modelarse:

```text
<<enumeration>>
EstadoAlquiler
```

No debe convertirse en requisito oculto si no está indicado.

---

# 159. P06.1 RA5.a

Debe evaluarse independientemente del aspecto gráfico.

Un alumno podría tener:

```text
RA5.a alto

RA5.b bajo
```

si comprende POO pero maneja mal Umbrello.

Eso es correcto.

---

# 160. P06.1 RA5.b

No confundir con RA5.d.

## RA5.b

Pregunta:

> ¿Sabe usar la herramienta?

## RA5.d

Pregunta:

> ¿Sabe transformar las especificaciones en un modelo correcto?

Puede manejar perfectamente Umbrello y diseñar mal.

O al contrario.

---

# 161. P06.1 RA5.c

Debe existir un diagrama:

```text
NO diseñado previamente
por el alumno
```

para demostrar realmente:

```text
interpretación.
```

CartagoLibrary cumple esa función.

---

# 162. P06.1 RA5.d

La trazabilidad:

```text
requisito → UML
```

es una evidencia especialmente importante.

Evita valorar solamente:

```text
resultado visual final.
```

---

# 163. P06.2 RA5.e

Secuencia:

```text
modelo origen
↓
wizard
↓
código
↓
comparación.
```

No permitir:

```text
escribir manualmente el Java
y decir que lo generó Umbrello.
```

---

# 164. P06.2 RA5.f

Secuencia:

```text
Java desconocido
↓
importación
↓
Tree View
↓
Class Diagram
↓
contraste.
```

---

# 165. Capturas previstas

```text
CAPTURA UD06-01
Umbrello 26.08.1

CAPTURA UD06-02
Nuevo Class Diagram

CAPTURA UD06-03
Propiedades de clase

CAPTURA UD06-04
Relaciones/multiplicidades

CAPTURA UD06-05
Code Generation Wizard

CAPTURA UD06-06
Code Importing Wizard

CAPTURA UD06-07
Tree View tras importación

CAPTURA UD06-08
Diagrama mediante ingeniería inversa
```

---

# 166. Medidas de apoyo

Para alumnado con dificultades:

```text
ficha de símbolos

diagrama parcialmente construido

tabla de multiplicidades

lista de candidatos a clase

ejemplo guiado anterior
```

sin entregar:

```text
CartagoRent resuelto.
```

---

# 167. Ampliación

Puede investigarse:

```text
abstract classes

enums UML

packages

plantillas/genéricos

XMI

round-trip engineering
```

sin añadir CE.

---

# 168. Recuperación

Instrumento:

# IR-RA5-01

Bloques:

```text
RA5.a

RA5.b

RA5.c

RA5.d

RA5.e

RA5.f
```

Ejemplo:

```text
a 7
b 6
c 4
d 6
e 7
f 3
```

Si RA5 no queda superado y requieren nueva evidencia:

```text
RA5.c

RA5.f
```

solo se activan esos dos bloques.

---

# 169. Trazabilidad

| RA | CE | Contenido | Práctica | Instrumento | Evidencias |
|---|---|---|---|---|---|
| RA5 | a | conceptos POO | P06.1 | I-RA5-01 | E-RA5.a-01/02 |
| RA5 | b | herramienta UML | P06.1 | I-RA5-01 | E-RA5.b-01/02 |
| RA5 | c | interpretación | P06.1 | I-RA5-01 | E-RA5.c-01/02 |
| RA5 | d | requisitos → diagrama | P06.1 | I-RA5-01 | E-RA5.d-01/03 |
| RA5 | e | UML → Java | P06.2 | I-RA5-02 | E-RA5.e-01/05 |
| RA5 | f | Java → UML | P06.2 | I-RA5-02 | E-RA5.f-01/06 |

---

# 170. Estado final RA5

```text
RA5.a → EVALUADO

RA5.b → EVALUADO

RA5.c → EVALUADO

RA5.d → EVALUADO

RA5.e → EVALUADO

RA5.f → EVALUADO
```

# RA5 COMPLETAMENTE CUBIERTO

---

# 171. Cálculo definitivo RA5

Los seis CE tienen el mismo peso:

```text
1 / 6
```

Por tanto:

```text
RA5 =
(
 a+b+c+d+e+f
) / 6
```

Los instrumentos no tienen pesos arbitrarios independientes.

---

# 172. CONTROL DE AISLAMIENTO DEL RA

**RA principal:** RA5

**CE evaluados:**

```text
RA5.a
RA5.b
RA5.c
RA5.d
RA5.e
RA5.f
```

### ¿Se evalúa Programación?

# NO.

Java se utiliza únicamente como:

```text
representación técnica
para RA5.e y RA5.f.
```

No se califica:

```text
calidad algorítmica

sintaxis avanzada

colecciones

excepciones

lógica de negocio.
```

### ¿Se evalúan diagramas de comportamiento?

# NO.

Se reservan para:

```text
RA6
UD07–UD08.
```

### ¿Se evalúa testing?

# NO.

### ¿Se evalúa IDE?

# NO.

### ¿Algún instrumento mezcla RA?

# NO.

```text
I-RA5-01
→ exclusivamente RA5

I-RA5-02
→ exclusivamente RA5.
```

---

# 173. Checklist final UD06

```text
☑ 14 periodos.

☑ RA5 único.

☑ 6 CE oficiales.

☑ Clase.

☑ Objeto.

☑ Instanciación.

☑ Atributos.

☑ Operaciones.

☑ Visibilidad.

☑ Encapsulación.

☑ Abstracción.

☑ Herencia.

☑ Polimorfismo.

☑ Interfaces.

☑ Asociación.

☑ Navegabilidad.

☑ Multiplicidad.

☑ Generalización.

☑ Agregación.

☑ Composición.

☑ Dependencia.

☑ Realización.

☑ Interpretación de diagramas.

☑ Requisitos → clases.

☑ Responsabilidades.

☑ Umbrello 26.08.1.

☑ UML 2.5.1.

☑ Modelado gráfico.

☑ Generación Java.

☑ Code Generation Wizard.

☑ Ingeniería inversa Java.

☑ Code Importing Wizard.

☑ Matiz de importación sin diagrama automático.

☑ Diagrama creado desde modelo importado.

☑ Round-trip tratado con límites.

☑ Miralmonte Reservas.

☑ CartagoRent.

☑ P06.1.

☑ P06.2.

☑ I-RA5-01.

☑ I-RA5-02.

☑ 6 CE con nota 0–10 propia.

☑ Rúbricas armonizadas.

☑ Evidencias codificadas.

☑ 8 capturas previstas.

☑ Consolidación.

☑ Ampliación.

☑ Resumen.

☑ Glosario.

☑ Autoevaluación.

☑ Soluciones profesor.

☑ Recuperación modular.

☑ Trazabilidad completa.

☑ Sin ponderaciones provisionales.

☑ Aislamiento superado.

☑ RA5 cerrado.
```

# UD06 — VERSIÓN MAESTRA DEFINITIVA