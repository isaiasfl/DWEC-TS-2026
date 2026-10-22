# Ejercicios · Sesión 05 · Miércoles 14 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** ejercicios para **practicar en casa** antes de la siguiente clase (unos 45 minutos). No se entregan, pero algún día te puede tocar **explicar tu solución** en clase.
> Repositorio con commit propio (`lazygit`): mensaje `s05: proyecto por capas`.

## Enunciados

### Ejercicio 1 · Termina el refactor

**Termina el refactor** de clase: `utils/`, `services/`, `components/` y `main.ts` que solo compone.

### Ejercicio 2 · Barril

Crea `utils/index.ts` que reexporte los tipos (`export type`) y las funciones públicas. `main.ts` y `components/` deben importar **solo** de `'./utils'` o `'../utils'`.

### Ejercicio 3 · Nueva regla de negocio

En `utils/catalog.ts`, `applyDiscount(list: readonly Product[], category: Category, percentage: number): Product[]`. Si el porcentaje no está entre 0 y 100, devuelve la lista sin cambios.

### Ejercicio 4 · Nueva vista

En `components/console.ts`, `showSummary(list: readonly Product[]): void` que imprima el número de productos, unidades totales y valor del inventario. Los cálculos deben estar en el **dominio** (crea `inventorySummary` allí) y la vista solo los muestra.

### Ejercicio 5 · Comprueba

**Comprueba** que `grep -rn "components/" src/utils src/types` no devuelve nada y que `npx tsc --noEmit` pasa.

### Ejercicio 6 · Piensa

**Piensa** (en un `NOTAS.md`): si mañana la tienda se muestra en una web, ¿qué carpetas cambiarías y cuáles no?

---

