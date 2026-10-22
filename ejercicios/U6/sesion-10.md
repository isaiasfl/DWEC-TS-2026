# Ejercicios · Sesión 10 · Martes 27 de octubre

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** ejercicios para **practicar en casa** antes de la siguiente clase (unos 60 minutos). No se entregan, pero algún día te puede tocar **explicar tu solución** en clase.
> Continúa tu **agenda** de la sesión 09 (estado → render con reductor). Commit con `lazygit`: `s10: form y persistencia`.

## Enunciados

### Ejercicio 1 · Formulario de alta

Campos `name` y `phone`, checkbox `favorite`. `submit` con `preventDefault`.

### Ejercicio 2 · Validación en el dominio

`validateContact(data: { name: string; phone: string; favorite: boolean }): ContactResult`, donde:
- el nombre tiene al menos 2 caracteres tras `trim`;
- el teléfono, quitando espacios, tiene exactamente 9 dígitos (`/^\d{9}$/`);
- el error se devuelve por campo, como en clase.

### Ejercicio 3 · Errores visibles

**Errores visibles** junto a cada campo, con `aria-invalid`.

### Ejercicio 4 · Acción `create`

**Acción `create`** en el reductor (id siguiente).

### Ejercicio 5 · Persistencia

`services/storage.ts` con `save` y `load` (clave `agenda-v1`), `JSON.parse` a `unknown` y validación con `isContact`. Si los datos no son válidos, arranca con los de ejemplo.

### Ejercicio 6 · Prueba la frontera

En DevTools, cambia un `phone` por un número (sin comillas) en el JSON guardado y recarga. Explica en `NOTAS.md` qué pasa y por qué.

---

