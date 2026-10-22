# Ejercicios · Sesión 08 · Miércoles 21 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** ejercicios para **practicar en casa** antes de la siguiente clase (unos 40 minutos). No se entregan, pero algún día te puede tocar **explicar tu solución** en clase.
> Cada ejercicio en `src/exercises/s08-homework/exNN-name/index.ts`, con `export`, importado en `main.ts`. Antes de darlo por terminado: `npx tsc --noEmit` sin errores. Prohibido `any`, `as` y `!`.

## Enunciados

### Ejercicio 1 · Fábrica de saludos

**Fábrica de saludos** (`ex01-greeter`). Crea `makeGreeter(greeting: string)` que devuelva una función que reciba un nombre y devuelva el saludo completo.
`makeGreeter('Buenos días')('Ana')` → `'Buenos días, Ana'`. Fabrica dos saludadores distintos y úsalos con `map` sobre `['Ana', 'Luis']`.

### Ejercicio 2 · Fábrica de conversores

**Fábrica de conversores** (`ex02-converter`). Crea `makeConverter(factor: number)` que devuelva una función que multiplique por `factor`. Fabrica `kmToMiles` (0.621) y `eurosToDollars` (1.08) y muestra `10` convertido con cada uno, con dos decimales.

### Ejercicio 3 · Closure: el marcador de un partido

**Closure: el marcador de un partido** (`ex03-scoreboard`). Crea `makeScoreboard()` que devuelva un objeto con tres funciones que compartan la misma mochila:
- `scoreHome()` y `scoreAway()` suman un punto a cada equipo;
- `result()` devuelve un texto como `'2 - 1'`.
Comprueba que dos marcadores distintos **no se mezclan**.

### Ejercicio 4 · Capas: la biblioteca

**Capas: la biblioteca** (`ex04-library`). Organiza en capas, con los nombres de clase:
- `types/book.ts`: `interface Book { readonly title: string; readonly author: string; readonly available: boolean }`;
- `services/books.ts`: un array con 5 libros (alguno no disponible);
- `utils/library.ts`: `availableBooks(list)` y `booksBy(list, author)`, **sin `console.log`**;
- `index.ts`: muestra por consola cuántos libros hay disponibles y los títulos de un autor.

### Ejercicio 5 · Pregunta (escríbela como comentario en `ex04-library/index.ts`)

Si mañana los libros vinieran de una API, ¿qué archivo cambiarías y cuáles no? ¿Por qué?

---

