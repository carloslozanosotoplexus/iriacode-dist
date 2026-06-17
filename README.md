# iriacode

**El generador open-source (Apache-2.0) del ecosistema coherente de IA.** Instala una vez
y deja **todos tus CLIs de IA** —Claude Code, GitHub Copilot, Codex, Gemini y Cursor—
trabajando con las mismas reglas, skills, hooks y memoria, de forma reproducible y sin
configuración manual. Autoalojado, **sin telemetría**, solo necesita **Python 3.9+** (sin Node).

> 🌐 Página de descarga: **https://carloslozanosotoplexus.github.io/iriacode-dist/**
> Este repo es el **canal público de distribución**; el código y su histórico viven en un repositorio privado de Plexus.

## Instalar (copia y pega)

**macOS / Linux:**
```sh
curl -fsSLO https://github.com/carloslozanosotoplexus/iriacode-dist/releases/latest/download/iriacode-latest-installer.sh
chmod +x iriacode-latest-installer.sh
./iriacode-latest-installer.sh
export PATH="$HOME/.local/bin:$PATH"
iriacode setup --global
iriacode welcome
```

**Windows (PowerShell):**
```powershell
Invoke-WebRequest -Uri https://github.com/carloslozanosotoplexus/iriacode-dist/releases/latest/download/iriacode-latest-installer.ps1 -OutFile iriacode-latest-installer.ps1
.\iriacode-latest-installer.ps1
iriacode setup --global
```

El instalador es **autocontenido** (lleva el wheel embebido), **refresca siempre** (idempotente)
y **no necesita clonar este repo ni cuenta**.

## Desinstalar (deja el equipo como antes)
```sh
./iriacode-latest-installer.sh --uninstall
```
Revierte toda la configuración de iriacode (bloques en tus CLIs, hooks, `~/.iriacode`) **preservando
tu propio contenido**, y elimina el paquete y el launcher.

## Qué es iriacode

iriacode no es un chatbot ni un wrapper: es un **generador de ecosistema**. A partir de un
**registro único** (`iriacode.registry.json`) materializa, idéntico en cada equipo:

- **Conducta (4 reglas):** alcance mínimo, evidencia antes que acción, cero especulación, consulta humana ante incertidumbre.
- **Taxonomía de agentes:** multiagentes, subagentes y microagentes por tecnología (routing determinista + fuentes oficiales).
- **Skills de primera clase** (estándar abierto **agentskills.io**): portables a Claude, Codex, Gemini CLI, Copilot, Cursor, OpenCode, Goose, Kiro… Incluye skills núcleo: `research-first`, `verification-loop`, `self-evaluation`, `tdd-workflow`, `code-review`, `security-review`, `deep-research`, `codebase-onboarding`, `spec-driven-development`.
- **Hooks de enforcement:** en Claude Code se ejecutan de verdad (evidence-gate, secret-guard, verification-on-stop); en los demás se inyecta el protocolo equivalente.
- **Memoria operativa:** contextos tipificados + aprendizajes (`iriacode memory`).
- **Aprendizaje continuo cross-CLI:** `iriacode observe` aprende de los chats locales de tus CLIs y `iriacode suggest` propone skills por patrones comunes (privacy-first: solo términos, redacta secretos).
- **Spec-Driven Development** (GitHub Spec Kit): `iriacode spec init`.

## Qué hace por el ecosistema donde se instala

1. **Coherencia:** todos los CLIs del equipo comparten conducta, skills y criterios → mismos resultados, menos deriva.
2. **Cero fricción:** `setup --global` escribe los bloques gestionados de cada CLI (no pisa tu config: usa marcadores y la preserva).
3. **Enforcement real** donde la plataforma lo permite (hooks de Claude) y por protocolo en el resto.
4. **Mejora sola:** aprende de los chats y sugiere/curar skills; reutilizable en todo el equipo.
5. **Portabilidad y soberanía:** Python stdlib, sin Node, sin telemetría, todo en `~/.iriacode`. Reversible al 100% (`--uninstall`).
6. **Multi-CLI auditable:** `iriacode harness audit` muestra qué cubre cada compromiso (Claude, Copilot, Codex, Gemini, Cursor).

## Comprobar
```sh
iriacode version        # versión instalada
iriacode harness audit  # matriz multi-CLI
iriacode skills         # catálogo (agentskills.io)
```

## Verificar integridad
Cada Release incluye el SHA-256 del instalador en su descripción:
```sh
shasum -a 256 iriacode-latest-installer.sh
```

---

Releases: pestaña *Releases*. Licencia: **Apache-2.0**.
