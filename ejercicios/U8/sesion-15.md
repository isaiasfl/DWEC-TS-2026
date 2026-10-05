# Ejercicios · Sesión 15 · Viernes 6 de noviembre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **miércoles 11/11**. 60 minutos.
> Proyecto `agenda-react` creado con `npm create vite@latest agenda-react -- --template react-ts`. Commit con `lazygit`: `s15: agenda en React`.

**Pasa tu agenda de octubre (sesiones 07–09) a React.**

## Enunciados

### Ejercicio 1 · Mudanza

Copia tu `domain/` (tipos `Contact`, `agendaReducer`, `validateContact`, `filterContacts`) y tu `services/storage.ts`. `npm run build` debe pasar **sin tocar** esos ficheros. Si no pasa, anota en `NOTAS.md` qué tuviste que cambiar y por qué (pista: si algo del dominio usaba el DOM, estaba en la capa equivocada).

### Ejercicio 2 · `main.tsx` sin `!`

**`main.tsx` sin `!`**, como en clase.

### Ejercicio 3 · Componentes

**Componentes** en `src/components/`, cada uno con su `interface XProps`:
- `ContactRow` (botones «★» y «Borrar» con callbacks `onToggleFavorite` y `onRemove`);
- `ContactList` (con `key`);
- `SearchBox` (input **controlado** y checkbox «Solo favoritos»).

### Ejercicio 4 · `App`

**`App`** con `useReducer(agendaReducer, undefined, () => initialStateFromStorage())`.

### Ejercicio 5 · `useEffect`

**`useEffect`** que guarde los contactos cuando cambien (`[state.contacts]`).

### Ejercicio 6 · Formulario de alta

**Formulario de alta** (opcional, ampliación): `ContactForm` con `onSubmit`, `e.preventDefault()` y tu `validateContact` de octubre.

---

