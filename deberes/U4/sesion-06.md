# Deberes · Sesión 06 · Viernes 16 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **miércoles 21/10**. 50 minutos.
> Carpeta: `src/exercises/s06-homework/NN-name/index.ts`. Prohibido `any`, `as` y `!`. `npx tsc --noEmit` sin errores.

1. **Notificaciones.** Modela con una unión discriminada (discriminante `type`):
   - `exito` con `message`;
   - `error` con `message` y `code: number`;
   - `aviso` con `message` y `expiresIn: number` (segundos).

   Escribe `notificationText(n): string` con `switch` exhaustivo (`never`).
2. **Semáforo de stock.** `type StockLevel = 'soldOut' | 'low' | 'normal'`. `stockLevel(p: Product): StockLevel` (0 → agotado; 1–3 → bajo; resto → normal) y `stockLabel(n: StockLevel): string` con `switch` exhaustivo («Agotado», «Pocas unidades», «Disponible»).
3. **Genérico `countBy`.** `countBy<T>(list: readonly T[], key: (x: T) => string): Record<string, number>`. Pruébalo con productos (por categoría) y con tareas (por `done ? 'sí' : 'no'`).
4. **Genérico `paginate`.** `paginate<T>(list: readonly T[], page: number, size: number): T[]` (página 1 = primeros `size`). Con página < 1 o tamaño < 1, devuelve `[]`.
5. **Type guard.** `isTask(raw: unknown): raw is Task` para `{ id: number; title: string; done: boolean }`. Úsalo en `readTasks(text: string): Result<Task[]>`.
6. **Piensa** (comentario): ¿qué pasaría en el ejercicio 2 si añades `'reserved'` a `StockLevel` y no tocas `stockLabel`?

---

