# Ejercicios · Sesión 01 · Martes 6 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **miércoles 7/10**. Tiempo estimado: 40 minutos.
> Cada ejercicio va en su carpeta `src/exercises/s01-homework/NN-name/index.ts`, con `export`, y se importa en `main.ts`.
> **Prohibido** usar `for`, `for...of` o `forEach`. Resuélvelos solo con los métodos de hoy.

Usa los datos de **TechStore Isaías FL** (`src/data/products.ts`).



## Enunciados

### Ejercicio 1 · Etiquetas

La tienda quiere mostrar en el escaparate una etiqueta de texto por cada producto. Escribe una función que reciba la lista de productos y devuelva **una lista nueva de textos**, uno por producto y en el mismo orden, con el formato `#id nombre - precio €`.

```ts
tags(list: Product[]): string[]
```

Ejemplo con el catálogo de clase:

```ts
tags(products);
// ['#1 Teclado mecánico - 80 €', '#2 Ratón inalámbrico - 25 €', ... ] (6 textos)
```

**Ten en cuenta:** la lista que devuelves tiene **la misma longitud** que la que recibes. Piensa qué método transforma cada elemento en otro.

**Teoría:** [U2 · 3. map: transformar](../../apuntes/U2-arrays-funcionales.md#3-map-transformar)

### Ejercicio 2 · Agotados

El encargado necesita saber qué productos debe reponer. Escribe una función que devuelva **solo los nombres** de los productos que tienen `stock` igual a `0`.

```ts
soldOutNames(list: Product[]): string[]
```

Resultado esperado con el catálogo de clase:

```ts
soldOutNames(products); // ['Ratón inalámbrico', 'Monitor 24"']
```

**Ten en cuenta:** hay dos pasos, primero **quedarte** con algunos productos y después **transformarlos** en su nombre. Puedes encadenar los dos métodos.

**Teoría:** [U2 · 4. filter: seleccionar](../../apuntes/U2-arrays-funcionales.md#4-filter-seleccionar) · [U2 · 9. Encadenar métodos](../../apuntes/U2-arrays-funcionales.md#9-encadenar-métodos)

### Ejercicio 3 · Por categoría

En la web hay un menú para ver los productos de una categoría. Escribe una función que reciba la lista y una categoría y devuelva **los productos completos** de esa categoría.

```ts
byCategory(list: Product[], category: Category): Product[]
```

```ts
byCategory(products, 'audio');  // [Auriculares, Micrófono USB] (los dos objetos completos)
byCategory(products, 'monitors'); // [Monitor 27", Monitor 24"]
```

**Pregunta:** ¿qué devuelve `byCategory([], 'audio')`? Pruébalo y escribe la respuesta en un comentario. ¿Falla o devuelve algo con sentido?

**Teoría:** [U2 · 4. filter: seleccionar](../../apuntes/U2-arrays-funcionales.md#4-filter-seleccionar)

### Ejercicio 4 · Precio por id

El carrito guarda solo el `id` de cada producto, y necesita consultar su precio. Escribe una función que busque el producto con ese `id` y devuelva su precio. Si **no existe** ningún producto con ese `id`, debe devolver `null`.

```ts
priceOf(list: Product[], id: number): number | null
```

```ts
priceOf(products, 3);  // 220
priceOf(products, 99); // null
```

**Ten en cuenta:** el método que busca **un** elemento puede no encontrarlo. TypeScript te obligará a comprobarlo antes de leer `.price`.
**Explica en un comentario** por qué no sería buena idea devolver `0` cuando el producto no existe.

**Teoría:** [U2 · find: el primero que cumpla... o nada](../../apuntes/U2-arrays-funcionales.md#find-el-primero-que-cumpla-o-nada)

### Ejercicio 5 · ¿Se puede comprar?

**¿Se puede comprar?** Antes de añadir al carrito hay que comprobar si la compra es posible. Escribe una función que devuelva `true` solo si se cumplen **todas** estas condiciones, y `false` en cualquier otro caso:
- existe un producto con ese `id`;
- la cantidad pedida es mayor que `0`;
- hay `stock` suficiente para esa cantidad.

```ts
canBuy(list: Product[], id: number, quantity: number): boolean
```

```ts
canBuy(products, 1, 2);  // true  (teclado: hay 5)
canBuy(products, 1, 6);  // false (solo hay 5)
canBuy(products, 2, 1);  // false (ratón agotado)
canBuy(products, 99, 1); // false (no existe)
canBuy(products, 1, 0);  // false (comprar 0 unidades no es una compra)
```

**Teoría:** [U2 · find](../../apuntes/U2-arrays-funcionales.md#find-el-primero-que-cumpla-o-nada) · [U1 · Retorno temprano](../../apuntes/U1-typescript-desde-cero.md#retorno-temprano-guard-clause)

### Ejercicio 6 · Pregunta de pensar

No hay que programar nada nuevo: responde en un comentario. Imagina esta función, que dice si **todos** los productos tienen stock:

```ts
const allInStock = (list: Product[]): boolean => list.every((p) => p.stock > 0);
```

¿Qué devuelve `allInStock([])`, es decir, con una tienda **sin productos**? Pruébalo. ¿Te parece una respuesta razonable para una tienda? ¿Cómo lo resolverías?

**Teoría:** [U2 · 6. Comprobar: some, every, includes](../../apuntes/U2-arrays-funcionales.md#6-comprobar-some-every-includes)

---

