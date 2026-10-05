# Deberes · Sesión 02 · Miércoles 7 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **martes 13/10** (el viernes se entregan los de [puesta al día](../U1/sesion-00.md)). 30 minutos.
> Carpeta: `src/exercises/s02-homework/NN-name/index.ts`. Sin `for` ni `forEach`. Usa `toSorted`, nunca `sort`. `npx tsc --noEmit` sin errores.

Datos: **TechStore Isaías FL**.

1. **Unidades totales.** `totalUnits(list: Product[]): number` con `reduce`.
2. **Más barato con stock.** `cheapestAvailable(list: Product[]): Product | undefined` (pista: `filter` + `toSorted` + `[0]`, o `reduce`).
3. **Catálogo ordenado.** `catalog(list: Product[]): string[]` ordenado por categoría y, dentro de cada categoría, por precio ascendente: `"audio · Micrófono USB · 45 €"`.
4. **Resumen numérico.** `summary(list: Product[]): { products: number; units: number; value: number }` en **un único** `reduce`.
5. **Piensa** (comentario): ¿qué devolvería tu función 2 con `[]`? ¿Y si usaras `sort` en la 3, qué le pasaría a `products`?

---

