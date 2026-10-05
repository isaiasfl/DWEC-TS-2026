# Deberes · Sesión 01 · Martes 6 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **miércoles 7/10**. Tiempo estimado: 40 minutos.
> Cada ejercicio va en su carpeta `src/exercises/s01-homework/NN-name/index.ts`, con `export`, y se importa en `main.ts`.
> **Prohibido** usar `for`, `for...of` o `forEach`. Resuélvelos solo con los métodos de hoy.

Usa los datos de **TechStore Isaías FL** (`src/data/products.ts`).

1. **Etiquetas.** `tags(list: Product[]): string[]` devuelve textos del tipo `"#1 Teclado mecánico - 80 €"`.
2. **Agotados.** `soldOutNames(list: Product[]): string[]`. Resultado esperado: `['Ratón inalámbrico', 'Monitor 24"']`.
3. **Por categoría.** `byCategory(list: Product[], category: Category): Product[]`. ¿Qué devuelve con una lista vacía?
4. **Precio por id.** `priceOf(list: Product[], id: number): number | null` devuelve `null` si el producto no existe. Explica en un comentario **por qué** no vale devolver `0`.
5. **¿Se puede comprar?** `canBuy(list: Product[], id: number, quantity: number): boolean` devuelve `true` solo si el producto existe **y** hay stock suficiente.
6. **Pregunta de pensar** (en un comentario): ¿qué devuelve `allInStock([])` si usas `every`? ¿Es razonable para una tienda?

---

