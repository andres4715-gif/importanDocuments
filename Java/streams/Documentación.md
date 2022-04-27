# _Java 8: Streams_

- Para mas información se puede consultar esta [pagina](https://dovixman.io/2019/04/03/java-8-streams/)

- Elementos de un Stream
  Como ya he comentado, los Streams son abstracciones que nos permiten definir operaciones agregadas sobre una fuente de datos utilizando funciones.

Los Streams se componen de tres partes:

La fuente de datos
Las operaciones intermedias
La operación terminal

## Fuentes de datos

- La fuente de datos consiste en una colección de datos que pueden ser tratados como una cadena de valores.

---

# Operaciones intermedias

- distinct()
- filter(Predicate)
- map(Function)
- mapToInt(Function)
- mapToDouble(Function)
- mapToLong(Function)

### Operaciones de restricción de tamaño

- skip(Long n)
- limit(Long n)

### Operaciones de ordenación y desordenación

- sorted()
- sorter(Comparator)
- Unordered()

---

# Operaciones terminales

- findFirst(Predicate)
- findAny(Predicate)
- anyMatch(Predicate)

### Operaciones que devuelve colecciones

- collect(Collector)
- toArray()

## Operaciones que devuelve resultados numéricos

- count()
- max(Comparator)
- min(Comparator)
- average()
- sum()

## Operaciones de iteración

- forEach(Consumer)

## Operaciones de reducción

- reduce(BinaryOperator accumulator)

---
