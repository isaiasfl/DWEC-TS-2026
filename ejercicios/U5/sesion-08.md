# Ejercicios · Sesión 08 · Miércoles 21 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **martes 27/10**. 50 minutos.
> Convierte la **agenda** de la sesión 07 al patrón **estado → render** con reductor. Prohibido modificar el DOM fuera de `render` y mutar el estado.

## Enunciados

### Ejercicio 1 · Estado

`interface AgendaState { readonly contacts: readonly Contact[]; readonly text: string; readonly onlyFavorites: boolean }`.

### Ejercicio 2 · Acciones

`type AgendaAction` con: `search` (texto), `toggleOnlyFavorites`, `toggleFavorite` (id) y `remove` (id).

### Ejercicio 3 · Reductor

`agendaReducer(state, action): AgendaState` en `domain/`, con `switch` exhaustivo.

### Ejercicio 4 · Vista

Cada fila tiene dos botones con `data-action` y `data-id`: «★» (alternar favorito) y «Borrar» (borrar). **Un solo** listener en el `<ul>`.

### Ejercicio 5 · `dispatch` y `render`

**`dispatch` y `render`** en `main.ts`, como en clase.

### Ejercicio 6 · Prueba sin navegador

En un fichero aparte, encadena 4 acciones con `agendaReducer` y muestra el estado final con `console.log`. (El reductor es puro: se puede probar sin DOM.)

---

