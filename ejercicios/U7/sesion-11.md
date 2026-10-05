# Ejercicios · Sesión 11 · Miércoles 28 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **martes 3/11**. 50 minutos.
> Carpeta `src/exercises/s11-homework/`. Prohibido `as`, `!` y `any`. Todo lo que venga de `fetch` se guarda como `unknown` y se valida.

API: `https://dummyjson.com` (usuarios: `/users/{id}` y `/users?limit=5&select=id,firstName,lastName,email`).

## Enunciados

### Ejercicio 1 · Rehaz con `await`

**Rehaz con `await`** la cuenta atrás de la sesión 10: `countdown(from: number): Promise<void>` con un `for` y `await wait(1000)`. Compara la longitud con tu versión con `then`.

### Ejercicio 2 · DTO de usuario

`interface ApiUser { id: number; firstName: string; lastName: string; email: string }` y su type guard `isApiUser`.

### Ejercicio 3 · Un usuario

`getUser(id: number): Promise<ApiUser>` usando `fetchJson`. Prueba con `1` y con `99999` (debe lanzar un error con el 404).

### Ejercicio 4 · Lista

`getUsers(): Promise<ApiUser[]>` (la respuesta tiene la forma `{ users: [...] }`).

### Ejercicio 5 · Sin excepciones

`fullName(id: number): Promise<Result<string>>` que nunca lance: `{ ok: true, value: 'Emily Johnson' }` o `{ ok: false, error: '...' }`.

### Ejercicio 6 · Paralelo

`namesOf(ids: number[]): Promise<string[]>` con `Promise.allSettled`: los que fallen se muestran como `'(desconocido)'`.

---

