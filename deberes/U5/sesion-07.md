# Deberes · Sesión 07 · Martes 20 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **viernes 23/10**. 45 minutos.
> Proyecto Vite nuevo `agenda-isaias` con capas `domain/`, `data/`, `ui/`. Prohibido `innerHTML` con datos, `as` y `!`. `npx tsc --noEmit` sin errores.

**Agenda de contactos del departamento de Isaías FL.**

```ts
export interface Contact {
  readonly id: number;
  name: string;
  phone: string;
  favorite: boolean;
}
```

1. **Datos.** 6 contactos en `data/contacts.ts` (2 favoritos).
2. **Dominio.** `filterContacts(list: readonly Contact[], text: string, onlyFavorites: boolean): Contact[]` (busca en nombre **y** teléfono, sin distinguir mayúsculas).
3. **Vista.** `createContactRow(c: Contact): HTMLLIElement` con `textContent`; si es favorito, añade la clase `favorite` y una estrella (`★`) delante del nombre.
4. **Pantalla.** Un `<input type="search">`, un checkbox «Solo favoritos», la lista y un párrafo `"3 de 6 contactos"`. Todo se actualiza en vivo con una única función `updateView`.
5. **Estado vacío.** Si no hay resultados, muestra «Sin coincidencias para "texto"».
6. **Tecla Escape** en el buscador: lo vacía y actualiza la vista.

---

