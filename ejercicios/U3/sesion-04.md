# Ejercicios · Sesión 04 · Martes 13 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **viernes 16/10**. 40 minutos.
> Carpeta: `src/exercises/s04-homework/NN-name/index.ts`. Sin `!` ni `as`. `npx tsc --noEmit` sin errores.

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

---

