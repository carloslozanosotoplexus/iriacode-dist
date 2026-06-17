# iriacode — distribución

Canal **público de distribución** de **iriacode**, el generador open-source (Apache-2.0)
del ecosistema coherente de IA (reglas, agentes, skills, mcps y arneses) para Claude,
GitHub Copilot, Codex, Gemini y Cursor.

> El **código fuente y su histórico** se desarrollan en un repositorio privado de Plexus.
> Este repositorio existe **solo para distribuir las releases** (instalador + wheel), de
> forma que cualquiera pueda instalarlo sin acceso al repo de código.

## Instalar

Descarga el instalador de la última **Release** (pestaña *Releases*) y ejecútalo
(macOS/Linux):

```sh
chmod +x iriacode-*-installer.sh
./iriacode-*-installer.sh        # instala (pip --user) + setup --global (configura tus CLIs)
iriacode setup --global
iriacode welcome
```

Windows: usa `iriacode-*-installer.ps1`.

Requisito único: **Python 3.9+** (sin Node). El instalador es autocontenido (lleva el
wheel embebido) y no necesita este repo ni red.

## Verificar integridad

Cada Release incluye el SHA-256 del instalador en su descripción. Comprueba:

```sh
shasum -a 256 iriacode-<version>-installer.sh
```

## Qué hace iriacode

`iriacode setup --global` materializa la conducta (4 reglas), skills (estándar
agentskills.io), hooks de enforcement (nativos en Claude) y los bloques de instrucciones
para cada CLI. Es autoalojado y **sin telemetría**: todo el estado vive en `~/.iriacode`.

Licencia: **Apache-2.0**.
