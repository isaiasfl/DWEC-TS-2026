# Ejercicios · Sesión 12 · Viernes 30 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

## Parte A · `async`/`await` y `fetch`

> **Para el alumnado:** ejercicios para **practicar en casa** antes de la siguiente clase (unos 50 minutos). No se entregan, pero algún día te puede tocar **explicar tu solución** en clase.
> Carpeta `src/exercises/s12-homework/`. Prohibido `as`, `!` y `any`. Todo lo que venga de `fetch` se guarda como `unknown` y se valida.

API: `https://dummyjson.com` (usuarios: `/users/{id}` y `/users?limit=5&select=id,firstName,lastName,email`).

## Enunciados

### Ejercicio 1 · Rehaz con `await`

**Rehaz con `await`** la cuenta atrás de la sesión 11: `countdown(from: number): Promise<void>` con un `for` y `await wait(1000)`. Compara la longitud con tu versión con `then`.

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

---

## Parte B · Directorio de usuarios con estados de carga

> **Para el alumnado:** ejercicios para **practicar en casa** antes de la siguiente clase (unos 60 minutos). No se entregan, pero algún día te puede tocar **explicar tu solución** en clase.
> Proyecto Vite `users-isaias` con capas `utils/`, `services/`, `components/`. Prohibido `as`, `!` y `any`.

**Directorio de usuarios** con `https://dummyjson.com/users`.

### Ejercicio 1 · Dominio

`interface Person { id: number; name: string; email: string; age: number }` (en español). `LoadState<T>` como en clase.

### Ejercicio 2 · Adaptador

**Adaptador** `services/users.ts`:
- el DTO `ApiUser` (`firstName`, `lastName`, `email`, `age`) **sin exportar** y su type guard;
- `adaptUser(dto): Person` (`name` = nombre + apellido);
- `loadPeople(signal?: AbortSignal): Promise<Person[]>` con `/users?limit=20&select=firstName,lastName,email,age`.

### Ejercicio 3 · Búsqueda

**Búsqueda** `searchPeople(text, signal?)` con `/users/search?q=...` y `encodeURIComponent`.

### Ejercicio 4 · Pantalla

**Pantalla** con los 4 estados (cargando, error con «Reintentar», vacío, lista) en un `switch` exhaustivo.

### Ejercicio 5 · Buscador

**Buscador** con `debounce` (400 ms) y `AbortController`.

### Ejercicio 6 · Prueba sin red

En DevTools → Red → *Offline*, recarga y comprueba que aparece el error y que «Reintentar» funciona al volver a *Online*.

---

