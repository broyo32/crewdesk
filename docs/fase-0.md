# Fase 0 — Preparación

Objetivo: que una app vacía de CrewDesk se instale en la tablet y conecte con Firebase (`crewdesk-e374b`).

## A. Lo que hace el usuario en su PC (una sola vez)

1. Instalar **Node.js LTS** (nodejs.org) y **Git para Windows** (git-scm.com).
2. Instalar **Claude Code** en PowerShell: `irm https://claude.ai/install.ps1 | iex` y comprobar con `claude --version`.
3. Clonar el repo: `git clone https://github.com/broyo32/crewdesk.git` y entrar: `cd crewdesk`.
4. Arrancar Claude Code: `claude` y pegar el encargo del apartado B.

## B. Encargo para Claude Code

> Lee CLAUDE.md y docs/fase-0.md. Ejecuta la fase 0 paso a paso, explicándome en español qué haces y parando cuando necesites algo de mí:
>
> 1. Crea la app Expo con TypeScript y Expo Router dentro de `app/` (plantilla por defecto de create-expo-app, SDK estable más reciente). Nombre "CrewDesk", slug `crewdesk`, package Android `com.crewdesk.app`, owner de Expo `broyo-design`.
> 2. Instala y configura `expo-dev-client` y `@react-native-firebase/app`, `auth`, `firestore` con sus config plugins, y `expo-build-properties` si hace falta.
> 3. Pídeme que registre la app Android `com.crewdesk.app` en Firebase (proyecto crewdesk-e374b) y que te pase el `google-services.json`; colócalo en `app/` y referéncialo en app.json.
> 4. Crea `app/eas.json` con perfiles `development` (developmentClient, distribution internal, APK), `preview` y `production`.
> 5. Crea `functions/` con un esqueleto TypeScript de Cloud Functions (sin desplegar nada).
> 6. Añade i18n (`i18next`, `react-i18next`) con `es` y una pantalla de inicio que diga "Hola, CrewDesk" y muestre si Firebase está conectado.
> 7. Comprueba que `npx tsc --noEmit` pasa. Haz commit en una rama `chore/fase-0` y abre un PR.
> 8. Guíame para: `npx eas-cli login`, `npx eas-cli build:configure` y `npx eas-cli build --profile development --platform android`, e instalar el APK en mi tablet con el QR.

## C. Hecho cuando

- [ ] La app de pruebas está instalada en la tablet.
- [ ] Muestra "Hola, CrewDesk" y "Firebase conectado".
- [ ] El PR de la fase 0 está fusionado en `main`.
- [ ] `docs/analisis-funcional.md` y `docs/documento-tecnico.md` están en el repo.
