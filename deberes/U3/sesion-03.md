# Deberes · Sesión 03 · Viernes 9 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **miércoles 14/10**. 45 minutos.
> Carpeta: `src/exercises/s03-homework/NN-name/index.ts`. **Prohibido** `push`, `splice`, `sort` y asignar propiedades (`x.algo = ...`). `npx tsc --noEmit` sin errores.

Vamos a gestionar las **tareas** del equipo de Isaías FL:

```ts
export type Priority = 'low' | 'medium' | 'high';

export interface Task {
  readonly id: number;
  title: string;
  priority: Priority;
  done: boolean;
}
```

1. **Crear.** `createTask(list: Task[], title: string, priority: Priority): Task[]` (nueva tarea sin hacer, id siguiente).
2. **Alternar.** `toggleDone(list: Task[], id: number): Task[]` → cambia `done` de `true` a `false` y viceversa.
3. **Renombrar.** `rename(list: Task[], id: number, title: string): Task[]`. Si el título está vacío (tras `trim`), devuelve la lista **sin cambios**.
4. **Limpiar.** `removeDone(list: Task[]): Task[]`.
5. **Editar.** `editTask(list: Task[], id: number, changes: Partial<Omit<Task, 'id'>>): Task[]`.
6. **Pendientes.** `pendingByPriority(list: Task[]): string[]` → títulos no hechos, primero `alta`, luego `media`, luego `unsubscribe`.
7. **Comprueba** en `main.ts` que, tras todas las operaciones, el array original sigue igual.

---

