# Deberes · Sesión 08 · Miércoles 21 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **martes 27/10**. 50 minutos.
> Convierte la **agenda** de los deberes 07 al patrón **estado → render** con reductor. Prohibido modificar el DOM fuera de `render` y mutar el estado.

1. **Estado.** `interface AgendaState { readonly contacts: readonly Contact[]; readonly text: string; readonly onlyFavorites: boolean }`.
2. **Acciones.** `type AgendaAction` con: `search` (texto), `toggleOnlyFavorites`, `toggleFavorite` (id) y `remove` (id).
3. **Reductor.** `agendaReducer(state, action): AgendaState` en `domain/`, con `switch` exhaustivo.
4. **Vista.** Cada fila tiene dos botones con `data-action` y `data-id`: «★» (alternar favorito) y «Borrar» (borrar). **Un solo** listener en el `<ul>`.
5. **`dispatch` y `render`** en `main.ts`, como en clase.
6. **Prueba sin navegador:** en un fichero aparte, encadena 4 acciones con `agendaReducer` y muestra el estado final con `console.log`. (El reductor es puro: se puede probar sin DOM.)

---

