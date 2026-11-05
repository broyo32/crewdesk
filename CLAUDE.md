# CrewDesk — instrucciones para Claude

CrewDesk es una app móvil (Android primero, iOS después) para organizar la convivencia de quienes comparten piso, tienen pareja o cuidan juntos de niños. Cada grupo se llama **CrewDesk**.

Antes de cualquier tarea, lee `docs/analisis-funcional.md` (el qué) y `docs/documento-tecnico.md` (el cómo). Si algo no está definido ahí, **pregunta al usuario antes de inventar**: él toma las decisiones de producto.

## Stack

- App: Expo + Expo Router, TypeScript estricto, en `app/`.
- Backend: Firebase (Auth, Firestore, Storage, Cloud Functions, FCM) con `@react-native-firebase/*`. Requiere development build (no Expo Go).
- Funciones en `functions/` (TypeScript). Reglas en `firestore.rules` y `storage.rules`.
- Estado: `zustand`. Formularios: `react-hook-form` + `zod`. Fechas: `date-fns` (zona Europe/Madrid). Repetición: `rrule`. Textos: `i18next` (solo `es` por ahora).

## Proyectos Firebase

| Alias | Project ID | Uso |
| --- | --- | --- |
| `dev` | `crewdesk-e374b` | Desarrollo y pruebas |
| `prod` | `crewdesk-b2e9d` | Usuarios reales. No desplegar sin permiso explícito del usuario. |

## Normas

- Código, nombres de variables y commits en inglés. Textos visibles en español, siempre a través de i18n.
- Un CrewDesk se llama `group` en el código (`groups/{groupId}`).
- Importes siempre en céntimos (enteros). Nunca `float` para dinero.
- Puntos de tareas: 4 niveles fijos → `effort: 1|2|3|4` = 1, 2, 3, 5 puntos. Cubrir un turno: +1 punto.
- Tests obligatorios para la lógica de puntos, asignación de turnos, deudas y repetición de eventos.
- Las reglas de seguridad se prueban con el emulador antes de cada cambio que las toque.
- Trabajar en ramas por tarea (`feat/...`, `fix/...`) y abrir PR; no hacer push directo a `main`.
- Usuario: no es programador. Explícale en español y en lenguaje llano qué has hecho y cómo probarlo.

## Entorno del usuario

- PC con Windows. Pruebas en una tablet (development build instalada vía EAS).
- Cuenta de Expo: `broyo-design`. Repo: `broyo32/crewdesk`.
