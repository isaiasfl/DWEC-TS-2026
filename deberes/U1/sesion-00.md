# Deberes · Puesta al día de TypeScript

*Apuntes de **Isaías FL** · DWEC 2.º DAW*

> **Para el alumnado:** entrega para el **viernes 9/10**. Tiempo estimado: 45 minutos.
> Cada ejercicio va en `src/exercises/s00-homework/NN-name/index.ts` con `export`. Antes de entregar: `npx tsc --noEmit` **sin errores**.
> Usa bucles (`for...of` o `forEach`), **todavía sin** `map`/`filter`.

1. **Tipo de mascota.** Crea `type Species = 'dog' | 'cat' | 'rabbit'` y una `interface Pet` con `id` (solo lectura), `name`, `species`, `age` y `chip` opcional (texto).
2. **Datos.** Exporta un array `pets: Pet[]` con 5 mascotas; al menos una sin `chip`.
3. **Descripción.** `describe(m: Pet): string` → `"Toby (perro, 3 años) · chip: sin chip"`. Usa `??`.
4. **Edad media.** `averageAge(list: Pet[]): number | null`. Pruébala con `[]`.
5. **Por especie.** `ofSpecies(list: Pet[], species: Species): string[]` con los nombres.
6. **Buscar.** `findByChip(list: Pet[], chip: string): Pet | undefined` con `for...of`. En `main.ts`, muestra el nombre **solo si existe**.
7. **Piensa** (comentario): ¿qué pasa si escribes `species: 'pez'`? ¿Y si en el paso 6 haces `findByChip(...).name` sin comprobar?

---

