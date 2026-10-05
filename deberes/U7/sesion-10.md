# Deberes · Sesión 10 · Martes 27 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **viernes 30/10**. 40 minutos.
> Carpeta `src/exercises/s10-homework/`. Solo `then`/`catch`/`finally` (todavía **sin** `async`/`await`). `error: unknown` en todos los `catch`.

1. **Predice y explica.** Copia este código en un comentario, escribe el orden que esperas y después ejecútalo. Explica cualquier diferencia.
   ```ts
   console.log('A');
   setTimeout(() => console.log('B'), 10);
   setTimeout(() => console.log('C'), 0);
   Promise.resolve().then(() => console.log('D'));
   console.log('E');
   ```
2. **Cuenta atrás.** `countdown(from: number): Promise<void>` que imprima `3`, `2`, `1`, `¡Ya!` con un segundo entre cada uno (usa `wait` y encadena).
3. **Stock remoto.** `checkStock(id: number): Promise<number>` que, con `simulateRequest`, devuelva el stock de un producto de TechStore Isaías FL tras 300 ms, o **rechace** con `new Error('Producto no encontrado')` si el id no existe.
4. **Varios a la vez.** `stockOfMany(ids: number[]): Promise<number[]>` con `Promise.all` y `checkStock`. ¿Qué pasa si un id no existe?
5. **Tolerante.** `availableStockOfMany(ids: number[]): Promise<number>` → suma el stock de los que existan, ignorando los que fallen (`allSettled`).

---

