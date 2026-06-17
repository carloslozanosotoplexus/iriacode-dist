# iriacode

Generador open-source (Apache-2.0) del ecosistema coherente de IA para **Claude, GitHub
Copilot, Codex, Gemini y Cursor**. Autoalojado, sin telemetría, solo necesita **Python 3.9+**.

## Instalar (copia y pega)

**macOS / Linux:**
```sh
curl -fsSLO https://github.com/carloslozanosotoplexus/iriacode-dist/releases/download/v0.9.1/iriacode-0.9.1-installer.sh
chmod +x iriacode-0.9.1-installer.sh
./iriacode-0.9.1-installer.sh
export PATH="$HOME/.local/bin:$PATH"
iriacode setup --global
iriacode welcome
```

**Windows (PowerShell):**
```powershell
Invoke-WebRequest -Uri https://github.com/carloslozanosotoplexus/iriacode-dist/releases/download/v0.9.1/iriacode-0.9.1-installer.ps1 -OutFile iriacode-0.9.1-installer.ps1
.\iriacode-0.9.1-installer.ps1
iriacode setup --global
iriacode welcome
```

Eso instala el CLI y **configura solos** todos tus CLIs de IA. No necesitas clonar este repo
ni tener cuenta: el instalador es autocontenido (lleva el wheel embebido).

## Comprobar que funciona
```sh
iriacode version        # iriacode 0.9.1
iriacode harness audit  # CLIs cubiertos
```

## Verificar integridad (opcional)
```sh
shasum -a 256 iriacode-0.9.1-installer.sh
# debe coincidir con el SHA-256 indicado en la Release v0.9.1
```

---

- **Releases / versiones:** pestaña *Releases* de este repo.
- Este repo es **solo el canal de distribución**; el código y su histórico se desarrollan en un repositorio privado de Plexus.
- Licencia: **Apache-2.0**.
