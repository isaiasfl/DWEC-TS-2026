# Ejercicios · Sesión 05 · Miércoles 14 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **martes 20/10**. 45 minutos.
> Repositorio con commit propio (`lazygit`): mensaje `s05: proyecto por capas`.

## Enunciados

### Ejercicio 1 · Termina el refactor

**Termina el refactor** de clase: `domain/`, `data/`, `ui/` y `main.ts` que solo compone.

### Ejercicio 2 · Barril

Crea `domain/index.ts` que reexporte los tipos (`export type`) y las funciones públicas. `main.ts` y `ui/` deben importar **solo** de `'./domain'` o `'../domain'`.

### Ejercicio 3 · Nueva regla de negocio

En `domain/catalog.ts`, `applyDiscount(list: readonly Product[], category: Category, percentage: number): Product[]`. Si el porcentaje no está entre 0 y 100, devuelve la lista sin cambios.

### Ejercicio 4 · Nueva vista

En `ui/console.ts`, `showSummary(list: readonly Product[]): void` que imprima el número de productos, unidades totales y valor del inventario. Los cálculos deben estar en el **dominio** (crea `inventorySummary` allí) y la vista solo los muestra.

### Ejercicio 5 · Comprueba

**Comprueba** que `grep -rn "ui/" src/domain` no devuelve nada y que `npx tsc --noEmit` pasa.

### Ejercicio 6 · Piensa

**Piensa** (en un `NOTAS.md`): si mañana la tienda se muestra en una web, ¿qué carpetas cambiarías y cuáles no?

---

