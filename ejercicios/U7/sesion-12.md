# Ejercicios · Sesión 12 · Viernes 30 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **miércoles 4/11**. 60 minutos.
> Proyecto Vite `users-isaias` con capas `domain/`, `services/`, `ui/`. Prohibido `as`, `!` y `any`.

**Directorio de usuarios** con `https://dummyjson.com/users`.

## Enunciados

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

