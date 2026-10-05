# Deberes · Sesión 14 · Miércoles 4 de noviembre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **martes 10/11** (primer día de React). 45 minutos.
> Sobre el proyecto de clase. Cada componente: `interface XProps` + `function X(props: XProps): HTMLElement`. Prohibido que un componente use el `store` directamente (solo `App`).

1. **`Badge`.** `Badge({ stock }: { stock: number }): HTMLElement` → un `<span>` con «Agotado», «Últimas unidades» (1–3) o nada (devuelve un `<span>` vacío). Úsalo dentro de `Card`.
2. **`QuantityButton`.** `QuantityButton({ text, onClick, disabled }: QuantityButtonProps)`, que sea reutilizable. Úsalo para «Añadir» en `Card` y para «−» en `Cart`.
3. **`Summary`.** Componente con el número de productos visibles y el precio medio de los visibles (si no hay, «—»). El cálculo va en un **selector** del dominio (`averageVisiblePrice(state): number | null`).
4. **Vaciar.** Botón «Vaciar carrito» en `Cart` con la prop `onClear: () => void`. Añade la acción `clear` al reductor (sesión 08).
5. **Traduce a JSX** (en un comentario, sin ejecutarlo): escribe cómo quedaría tu `Card` en JSX. Pista: mira la tabla del bloque 4 de la clase.

---

