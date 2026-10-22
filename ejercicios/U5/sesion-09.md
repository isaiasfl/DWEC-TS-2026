# Ejercicios · Sesión 09 · Viernes 23 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** ejercicios para **practicar en casa** antes de la siguiente clase (unos 50 minutos). No se entregan, pero algún día te puede tocar **explicar tu solución** en clase.
> Convierte la **agenda** de la sesión 07 al patrón **estado → render** con reductor. Prohibido modificar el DOM fuera de `render` y mutar el estado.

## Enunciados

### Ejercicio 1 · Estado

`interface AgendaState { readonly contacts: readonly Contact[]; readonly text: string; readonly onlyFavorites: boolean }`.

### Ejercicio 2 · Acciones

`type AgendaAction` con: `search` (texto), `toggleOnlyFavorites`, `toggleFavorite` (id) y `remove` (id).

### Ejercicio 3 · Reductor

`agendaReducer(state, action): AgendaState` en `utils/`, con `switch` exhaustivo.

### Ejercicio 4 · Vista

Cada fila tiene dos botones con `data-action` y `data-id`: «★» (`data-action="favorite"`) y «Borrar» (`data-action="remove"`). Para saber qué botón se pulsó, **copia este listener** tal cual; lo explicamos en clase (delegación de eventos, bloque 3):

```ts
list.addEventListener('click', (event) => {
  if (!(event.target instanceof Element)) return;
  const button = event.target.closest('button[data-action]');
  if (!(button instanceof HTMLButtonElement)) return;
  const id = Number(button.dataset.id);
  if (!Number.isInteger(id)) return;
  if (button.dataset.action === 'favorite') dispatch({ type: 'toggleFavorite', id });
  if (button.dataset.action === 'remove') dispatch({ type: 'remove', id });
});
```

### Ejercicio 5 · `dispatch` y `render`

**`dispatch` y `render`** en `main.ts`, como en clase.

### Ejercicio 6 · Prueba sin navegador

En un fichero aparte, encadena 4 acciones con `agendaReducer` y muestra el estado final con `console.log`. (El reductor es puro: se puede probar sin DOM.)

---

