# Ejercicios · Sesión 04 · Martes 13 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** ejercicios para **practicar en casa** antes de la siguiente clase (unos 40 minutos). No se entregan, pero algún día te puede tocar **explicar tu solución** en clase.
> Carpeta: `src/exercises/s04-homework/exNN-name/index.ts`. Sin `!` ni `as`. `npx tsc --noEmit` sin errores.

Datos: **TechStore Isaías FL**.

## Enunciados

### Ejercicio 1 · Precios distintos

`distinctPrices(list: Product[]): number` → cuántos precios diferentes hay (usa `Set`).

### Ejercicio 2 · Seleccionados

`select(selection: ReadonlySet<number>, id: number): Set<number>` y `clearSelection(): Set<number>`. Muestra los nombres de los productos seleccionados.

### Ejercicio 3 · Stock por categoría con Map

`stockByCategory(list: Product[]): Map<Category, number>`.

### Ejercicio 4 · Fábrica de formateadores

`createFormatter(currency: '€' | '$'): (price: number) => string` → `createFormatter('€')(80)` da `"80.00 €"`.

### Ejercicio 5 · Contador de visitas

`createVisitLog()` que devuelva `{ visit(id: number): void; visits(id: number): number; mostVisited(): number | undefined }`. Usa un `Map` privado dentro del closure.

### Ejercicio 6 · Piensa

**Piensa** (comentario): ¿por qué `visits(id)` debe devolver `0` y no `undefined` para un producto nunca visitado? ¿Y por qué `mostVisited()` sí puede devolver `undefined`?

### Repaso sin la tienda

> Para practicar la herramienta **sin** el modelo de la tienda. Carpeta: `src/exercises/s04-homework/rNN-name/index.ts`. Haz al menos cuatro.

**`Set`**

- **R1. Letras distintas.** `uniqueLetters(word: string): number`. `uniqueLetters('Banana')` → `3` (b, a, n). Pista: `new Set('hola')` acepta un texto.
- **R2. Amigos en común.** `commonFriends(a: string[], b: string[]): string[]`. `(['Ana', 'Luis', 'Eva'], ['Eva', 'Pepe', 'Ana'])` → `['Ana', 'Eva']`.
- **R3. Palabras encadenadas.** `isValidChain(words: string[]): boolean` → `false` si alguna palabra se repite. `['casa', 'sapo', 'pozo']` → `true`; `['casa', 'sapo', 'casa']` → `false`.

**`Map`**

- **R4. Contar letras.** `letterCount(text: string): Map<string, number>`, sin contar espacios y sin distinguir mayúsculas. `'Hola ola'` → `h 1, o 2, l 2, a 2`.
- **R5. Películas por año.** Con `interface Movie { title: string; year: number }`, `titlesByYear(movies: Movie[]): Map<number, string[]>`. `Coco 2017, Up 2009, Wonder 2017` → `2017 → ['Coco', 'Wonder']`, `2009 → ['Up']`.
- **R6. Diccionario.** `translate(dictionary: ReadonlyMap<string, string>, words: string[]): string[]`. Si la palabra no está, devuelve `'?palabra'`. `cat, bird, dog` con `{cat: gato, dog: perro}` → `['gato', '?bird', 'perro']`.

**Funciones y closures**

- **R7. Fábrica de rangos.** `between(min: number, max: number): (n: number) => boolean`. `[3, 7, 12, 5, 20].filter(between(5, 12))` → `[7, 12, 5]`.
- **R8. Marcador de partido.** `createScoreboard()` devuelve `{ point(team: string): void; score(team: string): number }` con un `Map` privado. Dos puntos al local y uno al visitante → `score('local')` es `2`, `score('nadie')` es `0`.

---

