# Ejercicios · Puesta al día de TypeScript

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **viernes 9/10**. Tiempo estimado: 45–60 minutos.
> Lee primero el apartado **Antes de empezar** entero: ahí está dónde va cada fichero y cómo se comprueba.

## Antes de empezar

### Qué vas a construir

Una pequeña librería para la **clínica veterinaria**: un tipo para las mascotas, una lista de datos y cuatro funciones que trabajan con esa lista. Cada ejercicio usa lo que hiciste en el anterior, así que hazlos **en orden**.

**Hito final:** al terminar, tu `src/main.ts` muestra en la consola del navegador el **informe de la clínica** completo, con `npx tsc --noEmit` sin errores:

```text
ej02 5
ej03 Toby (dog, 3 años) · chip: sin chip
ej03 Luna (cat, 5 años) · chip: ES-123
ej04 3.8
ej04 null
ej05 ['Toby', 'Rex']
ej05 ['Coco']
ej05 []
ej06 Luna
ej06 no hay ninguna mascota con ese chip
```

Llegarás a él en siete subhitos. Cada ejercicio añade una pieza y unas líneas nuevas a ese informe:

| Subhito | Ejercicio | Qué tienes al terminarlo |
|---|---|---|
| 1 | Tipo de mascota | TypeScript ya sabe cómo es una mascota y rechaza las mal escritas |
| 2 | Datos | La lista de las 5 mascotas; el informe muestra `ej02 5` |
| 3 | Descripción | Cada mascota se puede mostrar como frase |
| 4 | Edad media | El informe muestra la edad media y qué pasa con una lista vacía |
| 5 | Por especie | Puedes listar los nombres de una especie |
| 6 | Buscar por chip | Buscas por microchip sin que el programa falle si no existe |
| 7 | Piensa | Sabes leer y explicar los errores del compilador; el informe está completo |

No pases al siguiente subhito hasta que el actual cumpla su **Comprueba**.

### Paso 1 · El proyecto

Trabaja en el proyecto Vite que creaste en clase (`tienda`). Si no lo tienes, créalo ahora:

```bash
npm create vite@latest tienda -- --template vanilla-ts
cd tienda
npm install
```

### Paso 2 · Crea esta estructura de carpetas y ficheros

Créala **exactamente así** antes de escribir código. Los ficheros pueden estar vacíos al principio.

```text
src/
├── main.ts                                   ← ya existe: aquí pruebas cada ejercicio
├── types/
│   └── pet.ts                                ← ejercicio 1
├── data/
│   └── pets.ts                               ← ejercicio 2
└── exercises/
    └── s00-homework/
        ├── ex03-describe/index.ts            ← ejercicio 3
        ├── ex04-average-age/index.ts         ← ejercicio 4
        ├── ex05-of-species/index.ts          ← ejercicio 5
        ├── ex06-find-by-chip/index.ts        ← ejercicio 6
        └── ex07-think/index.ts               ← ejercicio 7
```

Cómo se leen los nombres de carpeta:

| Parte | Significa | Ejemplo |
|---|---|---|
| `s00` | sesión 00 del curso | `s01` será la sesión 01 |
| `-homework` | ejercicios para casa (los de clase van en `s00/`) | |
| `ex03` | ejercicio número 3, **siempre con dos cifras** para que se ordenen bien | `ex10`, no `ex1` |
| `-describe` | nombre en inglés de lo que hace, en minúsculas y con guiones | `average-age` |

> [!IMPORTANT]
> **Regla:** los tipos van en `src/types/`, los datos en `src/data/` y cada función en la carpeta de su ejercicio. Así cualquier ejercicio importa los tipos y los datos desde el mismo sitio.

### Paso 3 · Reglas de esta hoja

- Todo lo que otro fichero necesite usar se marca con `export`.
- En `main.ts`, las líneas `import` van **arriba del todo**, juntas; los `console.log` van debajo. Cuando un enunciado diga «añade en `src/main.ts`», pon su `import` con los demás y sus `console.log` al final.
- Los tipos se importan con `import type`; los valores y funciones con `import`.
- Para recorrer listas usa `for...of` o `forEach`. **Todavía no** se permiten `map`, `filter`, `reduce` ni `find`.
- Prohibido `any`, `as` y `!`.
- Nombres de código en inglés; textos y comentarios en español.

### Paso 4 · Cómo compruebas que está bien

Después de **cada** ejercicio:

1. Ejecuta `npx tsc --noEmit`. Debe terminar **sin ninguna línea de error**. Si sale un error, el ejercicio no está terminado.
2. Ejecuta `npm run dev`, abre la página en el navegador y mira la **consola** (F12 → pestaña Consola). Debe aparecer exactamente el resultado que indica el enunciado.

> [!WARNING]
> **Trampa:** `npm run dev` no comprueba tipos. La página puede funcionar con errores de TypeScript: el que manda es `npx tsc --noEmit`.

### Paso 5 · Qué entregas

Tu proyecto con la estructura del paso 2, subido a tu repositorio de GitHub, y el enlace en la tarea de Moodle. Antes de entregar, `npx tsc --noEmit` sin errores.

---

## Enunciados

### Ejercicio 1 · Tipo de mascota

Vas a definir **cómo es una mascota** para que TypeScript pueda avisarte si escribes una mal.

**Fichero:** `src/types/pet.ts`

**Qué tienes que hacer:**

1. Crea y exporta un tipo llamado `Species` que solo admita **tres valores exactos**: `'dog'`, `'cat'` o `'rabbit'`. Es una **unión de literales**: cualquier otro texto debe dar error.
2. Crea y exporta una `interface` llamada `Pet` con **exactamente** estas cinco propiedades, ni una más:

| Propiedad | Tipo | Obligatoria | Detalle |
|---|---|---|---|
| `id` | `number` | sí | de **solo lectura** (`readonly`): una vez creada la mascota no se puede cambiar |
| `name` | `string` | sí | nombre de la mascota |
| `species` | `Species` | sí | usa el tipo del punto 1, no `string` |
| `age` | `number` | sí | edad en años |
| `chip` | `string` | **no** | código del microchip; es **opcional** porque no todas las mascotas lo tienen |

**Comprueba (subhito 1 de 7):** este fichero solo contiene tipos, así que en consola no sale nada. Basta con que `npx tsc --noEmit` no dé errores.

**Teoría:** [U1 · 5. Uniones y literales](../../apuntes/U1-typescript-desde-cero.md#5-uniones-y-literales) · [U1 · 8. Objetos: interface y type](../../apuntes/U1-typescript-desde-cero.md#8-objetos-interface-y-type)

### Ejercicio 2 · Datos

Vas a crear la lista de mascotas con la que probarás el resto de ejercicios.

**Fichero:** `src/data/pets.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Pet` desde el ejercicio 1. La primera línea del fichero es exactamente esta:

   ```ts
   import type { Pet } from '../types/pet';
   ```

2. Crea y exporta una constante llamada `pets` con el tipo `Pet[]`.
3. Mete en ella **estas cinco mascotas, con estos mismos valores y en este orden**. Los resultados de los ejercicios siguientes están calculados con ellas:

| `id` | `name` | `species` | `age` | `chip` |
|---|---|---|---|---|
| 1 | Toby | `'dog'` | 3 | *(sin chip)* |
| 2 | Luna | `'cat'` | 5 | `'ES-123'` |
| 3 | Coco | `'rabbit'` | 1 | `'ES-456'` |
| 4 | Rex | `'dog'` | 8 | `'ES-789'` |
| 5 | Mishi | `'cat'` | 2 | *(sin chip)* |

«Sin chip» significa que **no escribes la propiedad `chip`** en ese objeto (no pongas `chip: ''` ni `chip: undefined`). Así empieza el array:

```ts
export const pets: Pet[] = [
  { id: 1, name: 'Toby', species: 'dog', age: 3 },
  { id: 2, name: 'Luna', species: 'cat', age: 5, chip: 'ES-123' },
  // ... las otras tres
];
```

**Comprueba (subhito 2 de 7):** en `src/main.ts`, borra lo que trae Vite y escribe:

```ts
import { pets } from './data/pets';

console.log('ej02', pets.length);
```

En consola debe salir: `ej02 5`

**Teoría:** [U1 · 7. Arrays y tuplas](../../apuntes/U1-typescript-desde-cero.md#7-arrays-y-tuplas)

### Ejercicio 3 · Descripción

Vas a escribir una función que convierte una mascota en una frase para mostrarla en pantalla.

**Fichero:** `src/exercises/s00-homework/ex03-describe/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo: `import type { Pet } from '../../../types/pet';`
2. Crea y exporta una función con **esta firma exacta** (mismo nombre, mismo parámetro, mismo tipo de retorno):

   ```ts
   export function describe(m: Pet): string
   ```

3. La función devuelve un texto con este formato, respetando espacios, paréntesis y el punto medio `·`:

   ```text
   <name> (<species>, <age> años) · chip: <chip>
   ```

4. Si la mascota **no tiene chip**, en lugar del código aparece el texto `sin chip`. Hazlo con el operador `??` dentro de la plantilla de texto (no con `if` ni con `||`).

**Comprueba (subhito 3 de 7):** añade en `src/main.ts`:

```ts
import { describe } from './exercises/s00-homework/ex03-describe';

console.log('ej03', describe(pets[0]));
console.log('ej03', describe(pets[1]));
```

En consola debe salir exactamente:

```text
ej03 Toby (dog, 3 años) · chip: sin chip
ej03 Luna (cat, 5 años) · chip: ES-123
```

**Teoría:** [U1 · 6. null, undefined y valores por defecto](../../apuntes/U1-typescript-desde-cero.md#6-null-undefined-y-valores-por-defecto)

### Ejercicio 4 · Edad media

Vas a calcular la edad media de una lista de mascotas, teniendo en cuenta que la lista puede venir vacía.

**Fichero:** `src/exercises/s00-homework/ex04-average-age/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Pet` igual que en el ejercicio 3.
2. Crea y exporta una función con esta firma exacta:

   ```ts
   export function averageAge(list: Pet[]): number | null
   ```

3. **Lo primero** que hace la función: si `list` está vacía (`list.length === 0`), devuelve `null` y termina. Una lista vacía no tiene media, y dividir entre `0` daría `NaN`.
4. Si no está vacía: crea una variable `sum` que empiece en `0`, recorre la lista con `for...of` sumando el `age` de cada mascota y devuelve `sum / list.length`.
5. No redondees el resultado.

**Comprueba (subhito 4 de 7):** añade en `src/main.ts`:

```ts
import { averageAge } from './exercises/s00-homework/ex04-average-age';

console.log('ej04', averageAge(pets));
console.log('ej04', averageAge([]));
```

En consola debe salir:

```text
ej04 3.8
ej04 null
```

(3 + 5 + 1 + 8 + 2 = 19, y 19 / 5 = 3.8)

**Teoría:** [U1 · Devolver «puede que no haya resultado»](../../apuntes/U1-typescript-desde-cero.md#devolver-puede-que-no-haya-resultado-number--null) · [U1 · 10. Recorrer arrays](../../apuntes/U1-typescript-desde-cero.md#10-recorrer-arrays)

### Ejercicio 5 · Por especie

Vas a obtener los nombres de todas las mascotas de una especie concreta.

**Fichero:** `src/exercises/s00-homework/ex05-of-species/index.ts`

**Qué tienes que hacer:**

1. Importa **los dos** tipos: `import type { Pet, Species } from '../../../types/pet';`
2. Crea y exporta una función con esta firma exacta:

   ```ts
   export function ofSpecies(list: Pet[], species: Species): string[]
   ```

3. Dentro, crea un array vacío **con su tipo anotado**: `const names: string[] = [];` (sin la anotación, TypeScript no sabe qué irá dentro).
4. Recorre `list` con `forEach`. Para cada mascota cuya `species` sea igual a la recibida, añade **su nombre** (no la mascota entera) con `names.push(...)`.
5. Devuelve `names`. Si ninguna mascota coincide, devuelve el array vacío, **no** `null`.

**Comprueba (subhito 5 de 7):** añade en `src/main.ts`:

```ts
import { ofSpecies } from './exercises/s00-homework/ex05-of-species';

console.log('ej05', ofSpecies(pets, 'dog'));
console.log('ej05', ofSpecies(pets, 'rabbit'));
console.log('ej05', ofSpecies([], 'cat'));
```

En consola debe salir (el navegador puede mostrar los arrays con otro formato, pero con estos valores):

```text
ej05 ['Toby', 'Rex']
ej05 ['Coco']
ej05 []
```

**Teoría:** [U1 · 10. Recorrer arrays](../../apuntes/U1-typescript-desde-cero.md#10-recorrer-arrays)

### Ejercicio 6 · Buscar por chip

Vas a buscar una mascota por su microchip y, en `main.ts`, usar el resultado de forma segura aunque no se encuentre.

**Fichero:** `src/exercises/s00-homework/ex06-find-by-chip/index.ts`

**Qué tienes que hacer:**

1. Importa el tipo `Pet`.
2. Crea y exporta una función con esta firma exacta:

   ```ts
   export function findByChip(list: Pet[], chip: string): Pet | undefined
   ```

3. Recorre la lista con `for...of`. En cuanto encuentres una mascota cuyo `chip` sea igual al recibido, **devuélvela con `return` dentro del bucle**: no hace falta seguir mirando.
4. Después del bucle (si se ha llegado ahí, no había ninguna), escribe `return undefined;`.

**Comprueba (subhito 6 de 7):** añade en `src/main.ts`:

```ts
import { findByChip } from './exercises/s00-homework/ex06-find-by-chip';

const found = findByChip(pets, 'ES-123');
if (found !== undefined) {
  console.log('ej06', found.name);
}

const missing = findByChip(pets, 'XX-000');
if (missing === undefined) {
  console.log('ej06', 'no hay ninguna mascota con ese chip');
}
```

En consola debe salir:

```text
ej06 Luna
ej06 no hay ninguna mascota con ese chip
```

**Ten en cuenta:** el `if (found !== undefined)` es obligatorio. Sin él, TypeScript no te deja escribir `found.name` porque `found` podría ser `undefined`. Lo vas a comprobar en el ejercicio 7.

**Teoría:** [U1 · Retorno temprano](../../apuntes/U1-typescript-desde-cero.md#retorno-temprano-guard-clause)

### Ejercicio 7 · Piensa

No hay que programar nada nuevo. Vas a provocar dos errores a propósito, leer lo que dice TypeScript y explicarlo con tus palabras.

**Fichero:** `src/exercises/s00-homework/ex07-think/index.ts` (solo contendrá comentarios)

**Qué tienes que hacer:**

1. **Primer error.** En `src/data/pets.ts`, cambia temporalmente la especie de Toby a `species: 'fish'`. Ejecuta `npx tsc --noEmit` y copia el mensaje de error.
2. Deshaz el cambio y comprueba que `tsc` vuelve a estar sin errores.
3. **Segundo error.** En `src/main.ts`, escribe temporalmente esta línea **sin** ningún `if` delante:

   ```ts
   console.log(findByChip(pets, 'ES-123').name);
   ```

   Ejecuta `npx tsc --noEmit` y copia el mensaje de error.
4. Borra esa línea y comprueba que `tsc` vuelve a estar sin errores.
5. En `ex07-think/index.ts`, escribe tus respuestas con **exactamente** esta plantilla, rellenando cada línea:

   ```ts
   // Error 1 · species: 'fish'
   // Mensaje de tsc: ...
   // Por qué ocurre: ...
   //
   // Error 2 · findByChip(...).name sin comprobar
   // Mensaje de tsc: ...
   // Por qué ocurre: ...
   // Cómo se arregla: ...
   ```

**Comprueba (subhito 7 de 7):** al terminar, `npx tsc --noEmit` debe salir **sin errores**: los dos cambios tienen que estar deshechos.

**Teoría:** [U1 · 12. Leer los errores del compilador](../../apuntes/U1-typescript-desde-cero.md#12-leer-los-errores-del-compilador)

---

