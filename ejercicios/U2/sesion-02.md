# Ejercicios · Sesión 02 · Miércoles 7 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **martes 13/10** (el viernes se entregan los de [puesta al día](../U1/sesion-00.md)). 30 minutos.
> Carpeta: `src/exercises/s02-homework/NN-name/index.ts`. Sin `for` ni `forEach`. Usa `toSorted`, nunca `sort`. `npx tsc --noEmit` sin errores.

Datos: **TechStore Isaías FL**.



## Enunciados

### Ejercicio 1 · Unidades totales

El almacén quiere saber cuántas unidades tiene en total, sumando el `stock` de todos los productos. Resuélvelo con `reduce`.

```ts
totalUnits(list: Product[]): number
```

```ts
totalUnits(products); // 20
totalUnits([]);       // 0
```

**Ten en cuenta:** el valor inicial de `reduce` (el segundo argumento) es lo que se devuelve con una lista vacía.

**Teoría:** [U2 · 7. reduce: resumir en un valor](../../apuntes/U2-arrays-funcionales.md#7-reduce-resumir-en-un-valor)

### Ejercicio 2 · Más barato con stock

Un cliente busca la opción más económica que se pueda comprar **ahora mismo**. Escribe una función que devuelva el producto **más barato de los que tienen stock**. Si no hay ninguno, devuelve `undefined`.

```ts
cheapestAvailable(list: Product[]): Product | undefined
```

```ts
cheapestAvailable(products); // { id: 6, name: 'Micrófono USB', price: 45, ... }
```

El ratón cuesta 25 €, pero está agotado: no vale.

**Pista:** `filter` + `toSorted` + `[0]`, o bien un `reduce`.

**Teoría:** [U2 · 8. Ordenar sin romper: toSorted](../../apuntes/U2-arrays-funcionales.md#8-ordenar-sin-romper-tosorted-y-compañía) · [U2 · 9. Encadenar métodos](../../apuntes/U2-arrays-funcionales.md#9-encadenar-métodos)

### Ejercicio 3 · Catálogo ordenado

Hay que imprimir el catálogo en papel. Devuelve una lista de textos con el formato `categoría · nombre · precio €`, ordenada **primero por categoría** (orden alfabético) y, **dentro de la misma categoría, por precio** de menor a mayor.

```ts
catalog(list: Product[]): string[]
```

```ts
catalog(products);
// [
//   'audio · Micrófono USB · 45 €',
//   'audio · Auriculares · 60 €',
//   'monitors · Monitor 24" · 140 €',
//   'monitors · Monitor 27" · 220 €',
//   'peripherals · Ratón inalámbrico · 25 €',
//   'peripherals · Teclado mecánico · 80 €',
// ]
```

**Ten en cuenta:** usa `toSorted`, que devuelve una copia, nunca `sort`. Para comparar textos, `localeCompare`.

**Teoría:** [U2 · Ordenar por varios criterios](../../apuntes/U2-arrays-funcionales.md#ordenar-por-varios-criterios)

### Ejercicio 4 · Resumen numérico

El panel de administración muestra tres cifras: cuántos productos distintos hay, cuántas unidades en total y cuánto vale todo el stock (`price × stock` de cada producto). Calcula las tres en **un único** `reduce`.

```ts
summary(list: Product[]): { products: number; units: number; value: number }
```

```ts
summary(products); // { products: 6, units: 20, value: 1750 }
summary([]);       // { products: 0, units: 0, value: 0 }
```

**Ten en cuenta:** el acumulador es un **objeto**. En cada vuelta devuelve un objeto nuevo con las tres cifras actualizadas.

**Teoría:** [U2 · Acumular en un objeto](../../apuntes/U2-arrays-funcionales.md#acumular-en-un-objeto)

### Ejercicio 5 · Piensa

Responde en un comentario:
- ¿Qué devuelve tu función del ejercicio 2 con una lista vacía, `cheapestAvailable([])`?
- Si en el ejercicio 3 usaras `sort` en lugar de `toSorted`, ¿qué le pasaría al array `products` original? ¿Por qué es un problema en una aplicación?

**Teoría:** [U2 · 8. Ordenar sin romper](../../apuntes/U2-arrays-funcionales.md#8-ordenar-sin-romper-tosorted-y-compañía)

---

