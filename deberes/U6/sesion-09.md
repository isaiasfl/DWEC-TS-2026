# Deberes · Sesión 09 · Viernes 23 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **miércoles 28/10**. 60 minutos.
> Continúa tu **agenda** de los deberes 08 (estado → render con reductor). Commit con `lazygit`: `s09: form y persistencia`.

1. **Formulario de alta.** Campos `name` y `phone`, checkbox `favorite`. `submit` con `preventDefault`.
2. **Validación en el dominio.** `validateContact(data: { name: string; phone: string; favorite: boolean }): ContactResult`, donde:
   - el nombre tiene al menos 2 caracteres tras `trim`;
   - el teléfono, quitando espacios, tiene exactamente 9 dígitos (`/^\d{9}$/`);
   - el error se devuelve por campo, como en clase.
3. **Errores visibles** junto a cada campo, con `aria-invalid`.
4. **Acción `create`** en el reductor (id siguiente).
5. **Persistencia.** `services/storage.ts` con `save` y `load` (clave `agenda-v1`), `JSON.parse` a `unknown` y validación con `isContact`. Si los datos no son válidos, arranca con los de ejemplo.
6. **Prueba la frontera:** en DevTools, cambia un `phone` por un número (sin comillas) en el JSON guardado y recarga. Explica en `NOTAS.md` qué pasa y por qué.

---

