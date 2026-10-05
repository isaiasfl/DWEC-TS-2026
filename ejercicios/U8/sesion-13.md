# Ejercicios · Sesión 13 · Martes 3 de noviembre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **viernes 6/11**. 45 minutos.
> Carpeta `src/exercises/s13-homework/`. Se puede ejecutar con `npx tsx` (sin navegador).

## Enunciados

### Ejercicio 1 · Store de tareas

Con `createStore` de clase, crea un store para `{ tasks: readonly Task[] }` con las acciones `create` (título), `toggle` (id) y `remove` (id). (`Task` de la sesión 03.)

### Ejercicio 2 · Tres suscriptores

Uno imprime la lista, otro imprime `"Pendientes: N"` y otro **se da de baja** después del segundo cambio (usa la función que devuelve `subscribe`).

### Ejercicio 3 · Historial (deshacer)

`createStoreWithHistory(reducer, initial)` que añada un método `undo(): void` que vuelva al estado anterior y avise a los suscriptores. Pista: guarda los estados anteriores en un array dentro del closure.

### Ejercicio 4 · Error propio

`class ValidationError extends Error` con un campo `readonly field: string`. Lánzalo desde `createValidatedTask(title: string): Task` si el título tiene menos de 3 letras. Captúralo con `instanceof` y muestra `"Error en titulo: ..."`.

### Ejercicio 5 · Piensa

**Piensa** (comentario): en el ejercicio 3, ¿por qué es fácil implementar «deshacer» precisamente porque el estado es **inmutable**?

---

