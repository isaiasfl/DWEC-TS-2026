<p align="center">
  <img src="assets/banner.svg" alt="DWEC · De TypeScript a React — 2.º DAW, curso 2026-27" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/2.º_DAW-Curso_2026--27-0f1e3a?style=flat-square" alt="2.º DAW · Curso 2026-27">
  <img src="https://img.shields.io/badge/módulo-DWEC-3178C6?style=flat-square" alt="Módulo DWEC">
  <img src="https://img.shields.io/badge/unidades-8-61DAFB?style=flat-square" alt="8 unidades">
  <img src="https://img.shields.io/badge/meta-tu_primera_app_React-20232A?style=flat-square&logo=react&logoColor=61DAFB" alt="Meta: tu primera app React">
</p>

<p align="center">
  <b>Desarrollo Web en Entorno Cliente</b> · Prof. <a href="https://github.com/isaiasfl"><b>Isaías Fernández Lozano</b></a>
</p>

---

> **Aquí no se viene a copiar código: se viene a entenderlo.**
> En ocho unidades pasarás de escribir tu primer tipo en TypeScript a levantar una aplicación React
> que consume una API real. Cada línea que escribas tendrá un porqué, y el compilador será tu primer
> compañero de equipo: si `tsc` no protesta, vas por buen camino.

## <img src="assets/iconos/target.svg" width="24" height="24" alt=""> Qué vas a construir

Durante todo el curso desarrollarás **TechStore**, una tienda de tecnología que crece contigo, unidad a unidad:

| Etapa | Tu TechStore sabe... |
|---|---|
| **U1–U2** | modelar productos con tipos y filtrarlos, ordenarlos y resumirlos con arrays funcionales |
| **U3–U4** | organizarse en módulos con una arquitectura limpia: dominio, servicios e interfaz separados |
| **U5–U6** | pintarse en el navegador, reaccionar a eventos, validar formularios y recordar el carrito |
| **U7** | cargar el catálogo desde una API REST real ([DummyJSON](https://dummyjson.com)), con estados de carga y error |
| **U8** | dar el salto a **React**: componentes, props, estado y efectos |

## <img src="assets/iconos/layers.svg" width="24" height="24" alt=""> Stack tecnológico

<p align="center">
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript"> <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite"> <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"> <img src="https://img.shields.io/badge/CSS3-663399?style=for-the-badge&logo=css&logoColor=white" alt="CSS3"> <img src="https://img.shields.io/badge/Node.js-5FA04E?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js"> <img src="https://img.shields.io/badge/npm-CB3837?style=for-the-badge&logo=npm&logoColor=white" alt="npm"> <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React"> <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git"> <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</p>

| Capa | Lo que dominarás |
|---|---|
| **Lenguaje** | TypeScript estricto: tipos, interfaces, uniones, genéricos, *narrowing*, utility types |
| **Datos** | `map`, `filter`, `reduce`, `toSorted`, `Map`, `Set`, inmutabilidad |
| **Arquitectura** | módulos ES, capas, funciones puras, una sola fuente de verdad |
| **Navegador** | DOM, eventos y delegación, formularios, `FormData`, `localStorage` |
| **Red** | `async`/`await`, `fetch`, `AbortController`, validación de lo que llega de fuera |
| **Herramientas** | Vite, npm, `tsc --noEmit`, Git y GitHub |
| **Framework** | React con TypeScript: componentes, props, `useState`, `useEffect` |

## <img src="assets/iconos/calendar-days.svg" width="24" height="24" alt=""> Hoja de ruta

<p align="center">
  <img src="assets/ruta.svg" alt="Ruta de aprendizaje: 8 unidades en 4 etapas hasta tu primera app React" width="100%">
</p>

El mismo recorrido, unidad a unidad:

```mermaid
flowchart LR
    U1[U1 · TypeScript<br/>desde cero] --> U2[U2 · Arrays<br/>funcionales]
    U2 --> U3[U3 · Objetos y<br/>colecciones]
    U3 --> U4[U4 · Módulos y<br/>arquitectura]
    U4 --> U5[U5 · DOM, eventos<br/>y estado]
    U5 --> U6[U6 · Formularios y<br/>persistencia]
    U6 --> U7[U7 · Asincronía<br/>y APIs]
    U7 --> U8[U8 · Patrones y<br/>puente a React]
    U8 --> R((React))
    style R fill:#61DAFB,stroke:#20232A,color:#20232A
    style U1 fill:#3178C6,stroke:#20232A,color:#fff
```

## <img src="assets/iconos/book-open.svg" width="24" height="24" alt=""> Unidades

| | | Apuntes | Ejercicios |
|---|---|---|---|
| <img src="assets/iconos/code-xml.svg" width="22" height="22" alt=""> | **U1** | [TypeScript desde cero](apuntes/U1-typescript-desde-cero.md) | [S00](ejercicios/U1/sesion-00.md) |
| <img src="assets/iconos/list.svg" width="22" height="22" alt=""> | **U2** | [Arrays funcionales](apuntes/U2-arrays-funcionales.md) | [S01](ejercicios/U2/sesion-01.md) · [S02](ejercicios/U2/sesion-02.md) |
| <img src="assets/iconos/boxes.svg" width="22" height="22" alt=""> | **U3** | [Objetos, colecciones y funciones](apuntes/U3-objetos-colecciones-funciones.md) | [S03](ejercicios/U3/sesion-03.md) · [S04](ejercicios/U3/sesion-04.md) |
| <img src="assets/iconos/layers.svg" width="22" height="22" alt=""> | **U4** | [Módulos, arquitectura y tipos avanzados](apuntes/U4-modulos-arquitectura-tipos-avanzados.md) | [S05](ejercicios/U4/sesion-05.md) · [S06](ejercicios/U4/sesion-06.md) |
| <img src="assets/iconos/mouse-pointer-click.svg" width="22" height="22" alt=""> | **U5** | [DOM, eventos y estado](apuntes/U5-dom-eventos-estado.md) | [S07](ejercicios/U5/sesion-07.md) · [S08](ejercicios/U5/sesion-08.md) |
| <img src="assets/iconos/clipboard-list.svg" width="22" height="22" alt=""> | **U6** | [Formularios y persistencia](apuntes/U6-formularios-persistencia.md) | [S09](ejercicios/U6/sesion-09.md) |
| <img src="assets/iconos/cloud-download.svg" width="22" height="22" alt=""> | **U7** | [Asincronía y APIs](apuntes/U7-asincronia-apis.md) | [S10](ejercicios/U7/sesion-10.md) · [S11](ejercicios/U7/sesion-11.md) · [S12](ejercicios/U7/sesion-12.md) |
| <img src="assets/iconos/atom.svg" width="22" height="22" alt=""> | **U8** | [Patrones y puente a React](apuntes/U8-patrones-y-puente-a-react.md) | [S13](ejercicios/U8/sesion-13.md) · [S14](ejercicios/U8/sesion-14.md) · [S15](ejercicios/U8/sesion-15.md) |

## <img src="assets/iconos/terminal.svg" width="24" height="24" alt=""> Empieza en dos minutos

```bash
# 1. Crea tu proyecto con Vite y TypeScript
npm create vite@latest techstore -- --template vanilla-ts
cd techstore
npm install

# 2. Arranca el servidor de desarrollo
npm run dev

# 3. Antes de entregar, el compilador debe dar el visto bueno
npx tsc --noEmit
```

Cada ejercicio vive en su propia carpeta y se importa desde `main.ts`:

```text
src/
├── main.ts
└── exercises/
    └── s01/
        └── ex01-available-products/
            └── index.ts
```

## <img src="assets/iconos/clipboard-check.svg" width="24" height="24" alt=""> Cómo trabajas y entregas

1. **Lee los apuntes** de la unidad antes de la sesión: llegarás con preguntas, no con dudas.
2. **Resuelve los ejercicios** de cada sesión en tu proyecto, cada ejercicio en `src/exercises/sNN/exNN-name/index.ts`.
3. **Versiona tu trabajo con Git** y súbelo a tu propio repositorio de GitHub: es tu portfolio.
4. **Comprueba** que `npx tsc --noEmit` termina **sin errores**.
5. **Entrega en Moodle**: allí están las tareas, los plazos y la evaluación.

## <img src="assets/iconos/star.svg" width="24" height="24" alt=""> Reglas de oro

| Regla | Por qué |
|---|---|
| Sin `any`, sin `as` y sin `!` | Un tipo que miente es peor que no tener tipo |
| Lo que llega de fuera se **comprueba** | Formularios, `localStorage` y APIs pueden traer cualquier cosa |
| Código en **inglés**, textos y comentarios en **español** | Así se trabaja en la empresa |
| Funciones pequeñas y con nombre que se explique solo | El código se lee muchas más veces de las que se escribe |
| `tsc` en verde antes de entregar | Si el compilador no lo entiende, nadie lo entenderá |

## <img src="assets/iconos/sparkles.svg" width="24" height="24" alt=""> Ampliación

¿Te sabe a poco? Retos voluntarios en tres niveles (**básico**, **medio** y **avanzado**) para quien quiera ir más allá:

[Unidades 1 y 2](ampliacion/U1-U2.md) · [Unidades 3 y 4](ampliacion/U3-U4.md) · [Unidades 5 y 6](ampliacion/U5-U6.md) · [Unidades 7 y 8](ampliacion/U7-U8.md)

## <img src="assets/iconos/lightbulb.svg" width="24" height="24" alt=""> Recursos recomendados

- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html): la referencia oficial del lenguaje.
- [MDN Web Docs](https://developer.mozilla.org/es/): DOM, eventos, `fetch` y todo lo del navegador.
- [Documentación de Vite](https://vite.dev/guide/): el entorno con el que trabajamos.
- [react.dev](https://react.dev/learn): para cuando llegue el salto final.

## <img src="assets/iconos/graduation-cap.svg" width="24" height="24" alt=""> Profesor

<table>
  <tr>
    <td width="110" align="center">
      <a href="https://github.com/isaiasfl"><img src="https://github.com/isaiasfl.png?size=200" width="96" alt="Isaías Fernández Lozano"></a>
    </td>
    <td>
      <b>Isaías Fernández Lozano</b><br>
      Profesor de Desarrollo Web en Entorno Cliente · 2.º DAW<br><br>
      <a href="https://github.com/isaiasfl"><img src="https://img.shields.io/badge/GitHub-isaiasfl-181717?style=flat-square&logo=github" alt="GitHub: isaiasfl"></a>
    </td>
  </tr>
</table>

---

<p align="center">
  <sub>Material elaborado por Isaías Fernández Lozano para el módulo DWEC · 2.º DAW · Curso 2026-27.<br>
  Las dudas, entregas y la evaluación se gestionan en Moodle.</sub>
</p>
