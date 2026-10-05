# Ejercicios · Sesión 02 · Miércoles 7 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **martes 13/10** (el viernes se entregan los de [puesta al día](../U1/sesion-00.md)). Tiempo estimado: 45–60 minutos.
> Lee primero el apartado **Antes de empezar** entero: ahí está dónde va cada fichero, los datos y cómo se comprueba.

## Antes de empezar

### Qué vas a construir

El **panel de administración** de TechStore Isaías FL: unidades en almacén, la oferta más barata que se puede comprar, el catálogo ordenado para imprimir y un resumen con las cifras del negocio. Hoy resumes listas en un solo valor (`reduce`) y las ordenas sin estropear el original (`toSorted`). Hazlos **en orden**: el ejercicio 4 junta todo lo anterior.

**Hito final:** al terminar, tu `src/main.ts` muestra en la consola del navegador el **panel de administración** completo, con `npx tsc --noEmit` sin errores:

```text
ej01 20 0
ej02 Micrófono USB
ej02 undefined
ej03 ['audio · Micrófono USB · 45 €', 'audio · Auriculares · 60 €', 'monitors · Monitor 24" · 140 €', 'monitors · Monitor 27" · 220 €', 'peripherals · Ratón inalámbrico · 25 €', 'peripherals · Teclado mecánico · 80 €']
ej04 { products: 6, units: 20, value: 1750 }
ej04 { products: 0, units: 0, value: 0 }
```

Llegarás a él en cinco subhitos. Cada ejercicio añade una pieza y unas líneas nuevas a ese panel:

| Subhito | Ejercicio | Qué tienes al terminarlo |
|---|---|---|
| 1 | Unidades totales | Sabes cuántas unidades hay en el almacén (`reduce` con un número) |
| 2 | Más barato con stock | Encuentras la oferta más barata que se puede comprar (`filter` + `toSorted`) |
| 3 | Catálogo ordenado | El catálogo sale ordenado por dos criterios, listo para imprimir |
| 4 | Resumen numérico | Las tres cifras del negocio en una sola pasada (`reduce` con un objeto) |
| 5 | Piensa | Sabes por qué `sort` es peligroso; el panel está completo |

No pases al siguiente subhito hasta que el actual cumpla su **Comprueba**.

### Paso 1 · El proyecto y los datos

Sigue en el mismo proyecto Vite (`tienda`). Los datos son **los mismos de la sesión 01**: `src/types/product.ts` y `src/data/products.ts`, sin ningún cambio. Si los has tocado, vuelve a dejarlos exactamente como en la hoja de la sesión 01: los resultados de esta hoja están calculados con ellos.

Abre `src/main.ts` y **borra todo su contenido**: en esta hoja lo vas a rellenar con las pruebas de la sesión 02. Tus ejercicios anteriores no se pierden, siguen en sus carpetas.

### Paso 2 · Crea esta estructura de carpetas y ficheros

Créala **exactamente así** antes de escribir código. Los ficheros pueden estar vacíos al principio.

```text
src/
├── main.ts                                       ← vacío: aquí pruebas cada ejercicio
├── types/product.ts                              ← ya existe (sesión 01)
├── data/products.ts                              ← ya existe (sesión 01)
└── exercises/
    └── s02-homework/
        ├── ex01-total-units/index.ts             ← ejercicio 1
        ├── ex02-cheapest-available/index.ts      ← ejercicio 2
        ├── ex03-catalog/index.ts                 ← ejercicio 3
        ├── ex04-summary/index.ts                 ← ejercicio 4
        └── ex05-think/index.ts                   ← ejercicio 5
```

Los nombres siguen la convención de siempre: `s02` es la sesión 02, `-homework` indica que son ejercicios para casa, `ex03` es el ejercicio 3 (siempre con dos cifras) y después va el nombre en inglés de lo que hace, en minúsculas y con guiones.

Desde cualquier `index.ts` de esta hoja, el tipo se importa así:

```ts
import type { Product } from '../../../types/product';
```

### Paso 3 · Reglas de esta hoja

- **Prohibido** usar `for`, `for...of` y `forEach`.
- Para ordenar usa **siempre** `toSorted`, **nunca** `sort` (en el ejercicio 5 verás por qué).
- Ninguna función modifica el array que recibe: siempre devuelve un valor nuevo.
- Todo lo que otro fichero necesite usar se marca con `export`. Los tipos se importan con `import type`.
- En `main.ts`, las líneas `import` van **arriba del todo**, juntas; los `console.log` van debajo. Cuando un enunciado diga «añade en `src/main.ts`», pon su `import` con los demás y sus `console.log` al final.
- Prohibido `any`, `as` y `!`.
- Nombres de código en inglés; textos y comentarios en español.

### Paso 4 · Cómo compruebas que está bien

Después de **cada** ejercicio:

1. Ejecuta `npx tsc --noEmit`. Debe terminar **sin ninguna línea de error**. Si sale un error, el ejercicio no está terminado.
2. Ejecuta `npm run dev`, abre la página en el navegador y mira la **consola** (F12 → pestaña Consola). Deben aparecer los valores que indica el enunciado. El navegador puede dibujar arrays y objetos con otro formato: lo que tiene que coincidir son los valores y su orden.

> [!WARNING]
> **Trampa:** `npm run dev` no comprueba tipos. La página puede funcionar con errores de TypeScript: el que manda es `npx tsc --noEmit`.

### Paso 5 · Qué entregas

Tu proyecto con la estructura del paso 2, subido a tu repositorio de GitHub, y el enlace en la tarea de Moodle. Antes de entregar, `npx tsc --noEmit` sin errores.

---

## Enunciados

### Ejercicio 1 · Unidades totales

El almacén quiere saber cuántas unidades tiene en total, sumando el `stock` de todos los productos.

**Fichero:** `src/exercises/s02-homework/ex01-total-units/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Product`.
2. Crea y exporta una función con **esta firma exacta** (mismo nombre, mismo parámetro, mismo tipo de retorno):

   ```ts
   export function totalUnits(list: Product[]): number
   ```

3. Resuélvela con **un solo** `reduce`:
   - el acumulador es un número que empieza en `0` (el segundo argumento de `reduce`);
   - en cada vuelta devuelves el acumulador más el `stock` del producto.
4. Con una lista vacía, `reduce` devuelve directamente el valor inicial. Por eso `totalUnits([])` debe dar `0` sin que escribas ningún `if`.

**Comprueba (subhito 1 de 5):** añade en `src/main.ts`:

```ts
import { products } from './data/products';
import { totalUnits } from './exercises/s02-homework/ex01-total-units';

console.log('ej01', totalUnits(products), totalUnits([]));
```

En consola debe salir:

```text
ej01 20 0
```

(5 + 0 + 3 + 10 + 0 + 2 = 20)

**Teoría:** [U2 · 7. reduce: resumir en un valor](../../apuntes/U2-arrays-funcionales.md#7-reduce-resumir-en-un-valor)

### Ejercicio 2 · Más barato con stock

Un cliente busca la opción más económica que pueda comprar **ahora mismo**.

**Fichero:** `src/exercises/s02-homework/ex02-cheapest-available/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Product`.
2. Crea y exporta una función con esta firma exacta:

   ```ts
   export function cheapestAvailable(list: Product[]): Product | undefined
   ```

3. Devuelve el producto **más barato de los que tienen stock** (`stock > 0`). Encadena tres pasos en una sola expresión:
   - `filter`, para quedarte solo con los productos que tienen stock;
   - `toSorted`, para ordenarlos por `price` de menor a mayor (comparador `(a, b) => a.price - b.price`);
   - `[0]`, para coger el primero, que es el más barato.
4. Si la lista está vacía o ningún producto tiene stock, `[0]` sobre un array vacío da `undefined`, que es justo lo que pide la firma. No hace falta ningún `if`.

Ojo con los datos: el ratón cuesta 25 € y es el más barato de la tienda, pero está agotado, así que **no** es la respuesta.

**Comprueba (subhito 2 de 5):** añade en `src/main.ts`. Como la función puede devolver `undefined`, se comprueba antes de leer `.name`:

```ts
import { cheapestAvailable } from './exercises/s02-homework/ex02-cheapest-available';

const cheapest = cheapestAvailable(products);
if (cheapest !== undefined) {
  console.log('ej02', cheapest.name);
}
console.log('ej02', cheapestAvailable([]));
```

En consola debe salir:

```text
ej02 Micrófono USB
ej02 undefined
```

**Teoría:** [U2 · 8. Ordenar sin romper: toSorted](../../apuntes/U2-arrays-funcionales.md#8-ordenar-sin-romper-tosorted-y-compañía) · [U2 · 9. Encadenar métodos](../../apuntes/U2-arrays-funcionales.md#9-encadenar-métodos)

### Ejercicio 3 · Catálogo ordenado

Hay que imprimir el catálogo en papel, agrupado por categorías y con los precios de menor a mayor dentro de cada una.

**Fichero:** `src/exercises/s02-homework/ex03-catalog/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Product`.
2. Crea y exporta una función con esta firma exacta:

   ```ts
   export function catalog(list: Product[]): string[]
   ```

3. Primero ordena con `toSorted` usando **dos criterios**:
   - **primero por `category`**, en orden alfabético. Para comparar textos usa `a.category.localeCompare(b.category)`, que devuelve un número negativo, `0` o positivo;
   - **si la categoría es la misma** (`localeCompare` devuelve `0`), por `price` de menor a mayor (`a.price - b.price`).

   Une los dos criterios con `||`: si el primero da `0` (empate), se usa el segundo.
4. Después, con `map`, convierte cada producto en un texto con este formato, respetando los puntos medios `·` y los espacios:

   ```text
   <category> · <name> · <price> €
   ```

5. Todo en una sola expresión encadenada: `list.toSorted(...).map(...)`.

**Comprueba (subhito 3 de 5):** añade en `src/main.ts`:

```ts
import { catalog } from './exercises/s02-homework/ex03-catalog';

console.log('ej03', catalog(products));
```

En consola debe salir un array con estos **6 textos**, en este orden:

```text
ej03 ['audio · Micrófono USB · 45 €', 'audio · Auriculares · 60 €', 'monitors · Monitor 24" · 140 €', 'monitors · Monitor 27" · 220 €', 'peripherals · Ratón inalámbrico · 25 €', 'peripherals · Teclado mecánico · 80 €']
```

**Teoría:** [U2 · Ordenar por varios criterios](../../apuntes/U2-arrays-funcionales.md#ordenar-por-varios-criterios)

### Ejercicio 4 · Resumen numérico

El panel de administración muestra tres cifras: cuántos productos distintos hay, cuántas unidades en total y cuánto dinero vale todo el stock.

**Fichero:** `src/exercises/s02-homework/ex04-summary/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Product`.
2. Crea y exporta un tipo para el resultado, con exactamente estas tres propiedades numéricas:

   ```ts
   export interface Summary {
     products: number; // cuántos productos distintos hay
     units: number;    // suma del stock de todos
     value: number;    // suma de price × stock de cada producto
   }
   ```

3. Crea y exporta una función con esta firma exacta:

   ```ts
   export function summary(list: Product[]): Summary
   ```

4. Calcula las tres cifras en **un único** `reduce` (no llames a `totalUnits` ni recorras la lista tres veces):
   - el valor inicial es el objeto `{ products: 0, units: 0, value: 0 }`;
   - en cada vuelta devuelves **un objeto nuevo** con las tres cifras actualizadas: `products` suma 1, `units` suma el `stock` y `value` suma `price * stock`;
   - no modifiques el acumulador (nada de `acc.units += ...`): crea un objeto nuevo.

**Comprueba (subhito 4 de 5):** añade en `src/main.ts`:

```ts
import { summary } from './exercises/s02-homework/ex04-summary';

console.log('ej04', summary(products));
console.log('ej04', summary([]));
```

En consola debe salir:

```text
ej04 { products: 6, units: 20, value: 1750 }
ej04 { products: 0, units: 0, value: 0 }
```

(valor: 80×5 + 25×0 + 220×3 + 60×10 + 140×0 + 45×2 = 400 + 0 + 660 + 600 + 0 + 90 = 1750)

**Teoría:** [U2 · Acumular en un objeto](../../apuntes/U2-arrays-funcionales.md#acumular-en-un-objeto)

### Ejercicio 5 · Piensa

No hay que programar nada nuevo. Vas a comprobar con tus propios ojos qué pasa si usas `sort` en lugar de `toSorted`, y a explicarlo.

**Fichero:** `src/exercises/s02-homework/ex05-think/index.ts` (solo contendrá comentarios)

**Qué tienes que hacer:**

1. Mira la segunda línea `ej02` de tu consola: es lo que devuelve `cheapestAvailable([])`.
2. **Experimento.** Añade temporalmente estas tres líneas **al final** de `src/main.ts`:

   ```ts
   console.log('antes', products[0].name);
   products.sort((a, b) => a.price - b.price);
   console.log('después', products[0].name);
   ```

3. Recarga la página, anota lo que sale en las líneas `antes` y `después`, y **borra** las tres líneas.
4. En `ex05-think/index.ts`, escribe tus respuestas con **exactamente** esta plantilla:

   ```ts
   // Pregunta 1 · ¿Qué devuelve cheapestAvailable([])? ¿Por qué?
   // Respuesta: ...
   //
   // Pregunta 2 · ¿Qué salió en «antes» y en «después»?
   // antes: ...
   // después: ...
   //
   // Pregunta 3 · ¿Qué le ha hecho sort al array products original?
   // Respuesta: ...
   //
   // Pregunta 4 · En una aplicación donde varias partes usan products, ¿por qué es un problema?
   // Respuesta: ...
   ```

**Comprueba (subhito 5 de 5):** las tres líneas del experimento están borradas, `npx tsc --noEmit` sale sin errores y la consola muestra el **hito final** completo del principio de la hoja.

**Teoría:** [U2 · 8. Ordenar sin romper](../../apuntes/U2-arrays-funcionales.md#8-ordenar-sin-romper-tosorted-y-compañía)

---

