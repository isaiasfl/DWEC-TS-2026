# Deberes · Sesión 12 · Viernes 30 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **miércoles 4/11**. 60 minutos.
> Proyecto Vite `users-isaias` con capas `domain/`, `services/`, `ui/`. Prohibido `as`, `!` y `any`.

**Directorio de usuarios** con `https://dummyjson.com/users`.

1. **Dominio.** `interface Person { id: number; name: string; email: string; age: number }` (en español). `LoadState<T>` como en clase.
2. **Adaptador** `services/users.ts`:
   - el DTO `ApiUser` (`firstName`, `lastName`, `email`, `age`) **sin exportar** y su type guard;
   - `adaptUser(dto): Person` (`name` = nombre + apellido);
   - `loadPeople(signal?: AbortSignal): Promise<Person[]>` con `/users?limit=20&select=firstName,lastName,email,age`.
3. **Búsqueda** `searchPeople(text, signal?)` con `/users/search?q=...` y `encodeURIComponent`.
4. **Pantalla** con los 4 estados (cargando, error con «Reintentar», vacío, lista) en un `switch` exhaustivo.
5. **Buscador** con `debounce` (400 ms) y `AbortController`.
6. **Prueba sin red:** en DevTools → Red → *Offline*, recarga y comprueba que aparece el error y que «Reintentar» funciona al volver a *Online*.

---

