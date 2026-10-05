# Ejercicios · Sesión 01 · Martes 6 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **miércoles 7/10**. Tiempo estimado: 50–60 minutos.
> Lee primero el apartado **Antes de empezar** entero: ahí está dónde va cada fichero, los datos y cómo se comprueba.

## Antes de empezar

### Qué vas a construir

Las funciones que necesita la web de **TechStore Isaías FL** para trabajar con su catálogo: etiquetas para el escaparate, lista de productos para reponer, filtro por categoría, consulta de precios y la comprobación de si una compra es posible. Cada ejercicio usa los mismos datos y las mismas ideas que el anterior, así que hazlos **en orden**.

**Hito final:** al terminar, tu `src/main.ts` muestra en la consola del navegador el **panel de la tienda** completo, con `npx tsc --noEmit` sin errores:

```text
ej01 ['#1 Teclado mecánico - 80 €', '#2 Ratón inalámbrico - 25 €', '#3 Monitor 27" - 220 €', '#4 Auriculares - 60 €', '#5 Monitor 24" - 140 €', '#6 Micrófono USB - 45 €']
ej02 ['Ratón inalámbrico', 'Monitor 24"']
ej03 ['Auriculares', 'Micrófono USB']
ej03 ['Monitor 27"', 'Monitor 24"']
ej03 []
ej04 220
ej04 null
ej05 true false false false false
ej06 true
```

Llegarás a él en seis subhitos. Cada ejercicio añade una pieza y unas líneas nuevas a ese panel:

| Subhito | Ejercicio | Qué tienes al terminarlo |
|---|---|---|
| 1 | Etiquetas | Cada producto se convierte en un texto para el escaparate (`map`) |
| 2 | Agotados | Sabes qué productos hay que reponer (`filter` + `map`) |
| 3 | Por categoría | La web puede mostrar el menú de una categoría (`filter`) |
| 4 | Precio por id | El carrito consulta precios sin fallar si el producto no existe (`find`) |
| 5 | ¿Se puede comprar? | El carrito decide si una compra es válida |
| 6 | Piensa | Entiendes un caso límite de `every`; el panel está completo |

No pases al siguiente subhito hasta que el actual cumpla su **Comprueba**.

### Paso 1 · El proyecto

Sigue trabajando en el mismo proyecto Vite (`tienda`) de la sesión 00. Las carpetas de la sesión 00 se quedan como están.

Abre `src/main.ts` y **borra todo su contenido**: en esta hoja lo vas a rellenar con las pruebas de la sesión 01. Tus ejercicios de la sesión 00 no se pierden, siguen en sus carpetas.

### Paso 2 · Los datos de TechStore

Si ya los creaste en clase, comprueba que son **exactamente** estos. Si no, créalos ahora copiándolos tal cual. Todos los resultados de esta hoja están calculados con ellos.

`src/types/product.ts`:

```ts
export type Category = 'peripherals' | 'monitors' | 'audio';

export interface Product {
  id: number;
  name: string;
  price: number; // euros, sin IVA
  category: Category;
  stock: number;
}
```

`src/data/products.ts`:

```ts
import type { Product } from '../types/product';

export const products: Product[] = [
  { id: 1, name: 'Teclado mecánico', price: 80, category: 'peripherals', stock: 5 },
  { id: 2, name: 'Ratón inalámbrico', price: 25, category: 'peripherals', stock: 0 },
  { id: 3, name: 'Monitor 27"', price: 220, category: 'monitors', stock: 3 },
  { id: 4, name: 'Auriculares', price: 60, category: 'audio', stock: 10 },
  { id: 5, name: 'Monitor 24"', price: 140, category: 'monitors', stock: 0 },
  { id: 6, name: 'Micrófono USB', price: 45, category: 'audio', stock: 2 },
];
```

### Paso 3 · Crea esta estructura de carpetas y ficheros

Créala **exactamente así** antes de escribir código. Los ficheros pueden estar vacíos al principio.

```text
src/
├── main.ts                                   ← vacío: aquí pruebas cada ejercicio
├── types/
│   └── product.ts                            ← paso 2
├── data/
│   └── products.ts                           ← paso 2
└── exercises/
    └── s01-homework/
        ├── ex01-tags/index.ts                ← ejercicio 1
        ├── ex02-sold-out-names/index.ts      ← ejercicio 2
        ├── ex03-by-category/index.ts         ← ejercicio 3
        ├── ex04-price-of/index.ts            ← ejercicio 4
        ├── ex05-can-buy/index.ts             ← ejercicio 5
        └── ex06-think/index.ts               ← ejercicio 6
```

Cómo se leen los nombres de carpeta:

| Parte | Significa | Ejemplo |
|---|---|---|
| `s01` | sesión 01 del curso | la anterior era `s00` |
| `-homework` | ejercicios para casa (los de clase van en `s01/`) | |
| `ex04` | ejercicio número 4, **siempre con dos cifras** para que se ordenen bien | `ex10`, no `ex1` |
| `-price-of` | nombre en inglés de lo que hace, en minúsculas y con guiones | `sold-out-names` |

Desde cualquier `index.ts` de esta hoja, los tipos y los datos se importan así (se suben **tres** carpetas: la del ejercicio, `s01-homework` y `exercises`):

```ts
import type { Category, Product } from '../../../types/product';
```

Importa solo los tipos que uses en ese fichero: si no usas `Category`, no lo pongas, o `tsc` dará error.

### Paso 4 · Reglas de esta hoja

- **Prohibido** usar `for`, `for...of` y `forEach`. Se resuelve todo con los métodos de hoy: `map`, `filter`, `find` y `every`.
- Ninguna función modifica el array que recibe: siempre devuelve un valor nuevo.
- Todo lo que otro fichero necesite usar se marca con `export`.
- Los tipos se importan con `import type`; los valores y funciones con `import`.
- En `main.ts`, las líneas `import` van **arriba del todo**, juntas; los `console.log` van debajo. Cuando un enunciado diga «añade en `src/main.ts`», pon su `import` con los demás y sus `console.log` al final.
- Prohibido `any`, `as` y `!`.
- Nombres de código en inglés; textos y comentarios en español.

### Paso 5 · Cómo compruebas que está bien

Después de **cada** ejercicio:

1. Ejecuta `npx tsc --noEmit`. Debe terminar **sin ninguna línea de error**. Si sale un error, el ejercicio no está terminado.
2. Ejecuta `npm run dev`, abre la página en el navegador y mira la **consola** (F12 → pestaña Consola). Deben aparecer los valores que indica el enunciado. El navegador puede dibujar los arrays con otro formato (por ejemplo, `(2) ['Auriculares', 'Micrófono USB']`): lo que tiene que coincidir son los valores y su orden.

> [!WARNING]
> **Trampa:** `npm run dev` no comprueba tipos. La página puede funcionar con errores de TypeScript: el que manda es `npx tsc --noEmit`.

### Paso 6 · Qué entregas

Tu proyecto con la estructura del paso 3, subido a tu repositorio de GitHub, y el enlace en la tarea de Moodle. Antes de entregar, `npx tsc --noEmit` sin errores.

---

## Enunciados

### Ejercicio 1 · Etiquetas

La tienda quiere mostrar en el escaparate una etiqueta de texto por cada producto.

**Fichero:** `src/exercises/s01-homework/ex01-tags/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Product` (solo ese).
2. Crea y exporta una función con **esta firma exacta** (mismo nombre, mismo parámetro, mismo tipo de retorno):

   ```ts
   export function tags(list: Product[]): string[]
   ```

3. La función devuelve **un array nuevo de textos**: uno por producto, en el mismo orden. Por tanto, el array devuelto tiene **la misma longitud** que `list`.
4. Cada texto tiene este formato, respetando la almohadilla, los espacios y el guion:

   ```text
   #<id> <name> - <price> €
   ```

5. Resuélvelo con **un solo** `map` y una plantilla de texto (comillas invertidas `` ` ``).

**Comprueba (subhito 1 de 6):** añade en `src/main.ts`:

```ts
import { products } from './data/products';
import { tags } from './exercises/s01-homework/ex01-tags';

console.log('ej01', tags(products));
```

En consola debe salir un array con estos **6 textos**, en este orden:

```text
ej01 ['#1 Teclado mecánico - 80 €', '#2 Ratón inalámbrico - 25 €', '#3 Monitor 27" - 220 €', '#4 Auriculares - 60 €', '#5 Monitor 24" - 140 €', '#6 Micrófono USB - 45 €']
```

**Teoría:** [U2 · 3. map: transformar](../../apuntes/U2-arrays-funcionales.md#3-map-transformar)

### Ejercicio 2 · Agotados

El encargado necesita saber qué productos debe reponer.

**Fichero:** `src/exercises/s01-homework/ex02-sold-out-names/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Product`.
2. Crea y exporta una función con esta firma exacta:

   ```ts
   export function soldOutNames(list: Product[]): string[]
   ```

3. Devuelve **solo los nombres** (textos, no productos) de los productos cuyo `stock` es exactamente `0`.
4. Hazlo en dos pasos **encadenados** en una sola expresión:
   - primero `filter`, para **quedarte** con los productos que tienen `stock === 0`;
   - después `map`, para **transformar** cada uno de esos productos en su `name`.

**Comprueba (subhito 2 de 6):** añade en `src/main.ts`:

```ts
import { soldOutNames } from './exercises/s01-homework/ex02-sold-out-names';

console.log('ej02', soldOutNames(products));
```

En consola debe salir:

```text
ej02 ['Ratón inalámbrico', 'Monitor 24"']
```

**Teoría:** [U2 · 4. filter: seleccionar](../../apuntes/U2-arrays-funcionales.md#4-filter-seleccionar) · [U2 · 9. Encadenar métodos](../../apuntes/U2-arrays-funcionales.md#9-encadenar-métodos)

### Ejercicio 3 · Por categoría

La web tiene un menú para ver los productos de una sola categoría.

**Fichero:** `src/exercises/s01-homework/ex03-by-category/index.ts`

**Qué tienes que hacer:**

1. Importa **los dos** tipos: `Category` y `Product`.
2. Crea y exporta una función con esta firma exacta:

   ```ts
   export function byCategory(list: Product[], category: Category): Product[]
   ```

3. Devuelve **los productos completos** (los objetos, no sus nombres) cuya `category` es igual a la recibida, en el mismo orden en que están en `list`. Usa `filter`.
4. Debajo de la función, en el mismo fichero, responde a esta pregunta con **exactamente** esta plantilla. Para contestarla, mira la tercera línea del **Comprueba**:

   ```ts
   // Pregunta · ¿Qué devuelve byCategory([], 'audio')?
   // Resultado: ...
   // ¿Da error o devuelve algo con sentido? ¿Por qué?: ...
   ```

**Comprueba (subhito 3 de 6):** añade en `src/main.ts`. Como la función devuelve objetos completos, para que se lean bien en consola mostramos solo sus nombres con un `map`:

```ts
import { byCategory } from './exercises/s01-homework/ex03-by-category';

console.log('ej03', byCategory(products, 'audio').map((p) => p.name));
console.log('ej03', byCategory(products, 'monitors').map((p) => p.name));
console.log('ej03', byCategory([], 'audio'));
```

En consola debe salir:

```text
ej03 ['Auriculares', 'Micrófono USB']
ej03 ['Monitor 27"', 'Monitor 24"']
ej03 []
```

**Teoría:** [U2 · 4. filter: seleccionar](../../apuntes/U2-arrays-funcionales.md#4-filter-seleccionar)

### Ejercicio 4 · Precio por id

El carrito guarda solo el `id` de cada producto y necesita consultar su precio.

**Fichero:** `src/exercises/s01-homework/ex04-price-of/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Product`.
2. Crea y exporta una función con esta firma exacta:

   ```ts
   export function priceOf(list: Product[], id: number): number | null
   ```

3. Busca con `find` el producto cuyo `id` es igual al recibido y guárdalo en una constante `product`.
4. `find` devuelve `undefined` si no encuentra nada. Por eso, **antes** de leer `product.price`, comprueba con un `if` si `product` es `undefined`: en ese caso devuelve `null` y termina.
5. Si existe, devuelve su `price`.
6. Debajo de la función, responde con esta plantilla:

   ```ts
   // Pregunta · ¿Por qué no es buena idea devolver 0 cuando el producto no existe?
   // Respuesta: ...
   ```

**Comprueba (subhito 4 de 6):** añade en `src/main.ts`:

```ts
import { priceOf } from './exercises/s01-homework/ex04-price-of';

console.log('ej04', priceOf(products, 3));
console.log('ej04', priceOf(products, 99));
```

En consola debe salir:

```text
ej04 220
ej04 null
```

**Ten en cuenta:** si intentas leer `product.price` sin el `if`, TypeScript se queja de que `product` puede ser `undefined`. No lo silencies con `!`: compruébalo.

**Teoría:** [U2 · find: el primero que cumpla... o nada](../../apuntes/U2-arrays-funcionales.md#find-el-primero-que-cumpla-o-nada)

### Ejercicio 5 · ¿Se puede comprar?

**¿Se puede comprar?** Antes de añadir algo al carrito hay que comprobar si esa compra es posible.

**Fichero:** `src/exercises/s01-homework/ex05-can-buy/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Product`.
2. Crea y exporta una función con esta firma exacta:

   ```ts
   export function canBuy(list: Product[], id: number, quantity: number): boolean
   ```

3. La función devuelve `true` **solo** si se cumplen **las tres** condiciones siguientes, y `false` en cualquier otro caso:
   - existe un producto con ese `id`;
   - `quantity` es mayor que `0` (comprar 0 unidades no es una compra);
   - el `stock` del producto es **mayor o igual** que `quantity`.
4. Sigue este orden dentro de la función:
   - busca el producto con `find`, igual que en el ejercicio 4;
   - si es `undefined`, devuelve `false` y termina;
   - si existe, devuelve el resultado de comprobar las otras dos condiciones unidas con `&&`.

**Comprueba (subhito 5 de 6):** añade en `src/main.ts` (las cinco llamadas en un solo `console.log`):

```ts
import { canBuy } from './exercises/s01-homework/ex05-can-buy';

console.log(
  'ej05',
  canBuy(products, 1, 2),  // teclado, hay 5 → true
  canBuy(products, 1, 6),  // teclado, pide 6 y solo hay 5 → false
  canBuy(products, 2, 1),  // ratón agotado → false
  canBuy(products, 99, 1), // no existe → false
  canBuy(products, 1, 0),  // 0 unidades → false
);
```

En consola debe salir:

```text
ej05 true false false false false
```

**Teoría:** [U2 · find](../../apuntes/U2-arrays-funcionales.md#find-el-primero-que-cumpla-o-nada) · [U1 · Retorno temprano](../../apuntes/U1-typescript-desde-cero.md#retorno-temprano-guard-clause)

### Ejercicio 6 · Piensa

Vas a descubrir un caso límite de `every` que sorprende a casi todo el mundo, y a explicarlo.

**Fichero:** `src/exercises/s01-homework/ex06-think/index.ts`

**Qué tienes que hacer:**

1. Copia en el fichero, tal cual, esta función que dice si **todos** los productos tienen stock:

   ```ts
   import type { Product } from '../../../types/product';

   export const allInStock = (list: Product[]): boolean => list.every((p) => p.stock > 0);
   ```

2. Pruébala con una tienda **sin productos** (mira el **Comprueba**).
3. Debajo de la función, responde con exactamente esta plantilla:

   ```ts
   // Pregunta 1 · ¿Qué devuelve allInStock([])?
   // Resultado: ...
   // Pregunta 2 · ¿Es una respuesta razonable para una tienda sin productos? ¿Por qué?
   // Respuesta: ...
   // Pregunta 3 · ¿Cómo cambiarías la función para que una tienda vacía devuelva false?
   // Respuesta (escribe el código en una línea): ...
   ```

**Comprueba (subhito 6 de 6):** añade en `src/main.ts`:

```ts
import { allInStock } from './exercises/s01-homework/ex06-think';

console.log('ej06', allInStock([]));
```

Anota en la pregunta 1 lo que sale en consola. Al terminar, `npx tsc --noEmit` sin errores y la consola debe mostrar el **hito final** completo del principio de la hoja.

**Teoría:** [U2 · 6. Comprobar: some, every, includes](../../apuntes/U2-arrays-funcionales.md#6-comprobar-some-every-includes)

---

