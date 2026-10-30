# Caspar Manufaktur Agent Kit

Official agent rules, MCP configuration and plugin manifest for **[Caspar Manufaktur](https://www.caspar-manufaktur.de/)** – custom digital-print wallpaper made to measure in Germany since 1886.

Use this repository to connect AI coding and assistant tools to the public Caspar Manufaktur API and MCP server.

## Contents

| File | For |
|---|---|
| [`AGENTS.md`](AGENTS.md) | All agents (Codex, Jules, Amp, …) – interfaces and rules |
| [`CLAUDE.md`](CLAUDE.md), [`.mcp.json`](.mcp.json), [`.claude-plugin/plugin.json`](.claude-plugin/plugin.json) | Claude Code |
| [`.cursorrules`](.cursorrules), [`.cursor/mcp.json`](.cursor/mcp.json) | Cursor |
| [`.windsurfrules`](.windsurfrules) | Windsurf |
| [`.github/copilot-instructions.md`](.github/copilot-instructions.md), [`.vscode/mcp.json`](.vscode/mcp.json) | GitHub Copilot / VS Code |
| [`plugin.json`](plugin.json), [`mcp.json`](mcp.json), [`skills/`](skills/) | [Agent Plugins](https://agent-plugins.org/) 1.0.0 |

## Quick start

MCP server (Streamable HTTP, no API key):

```
https://www.caspar-manufaktur.de/mcp/
```

Claude Code:

```
claude mcp add --transport http caspar-manufaktur https://www.caspar-manufaktur.de/mcp/
```

REST:

```
curl https://www.caspar-manufaktur.de/api/v1/materials
curl "https://www.caspar-manufaktur.de/api/v1/materials/recommendation?priority=brandschutz"
```

## Links

- Developer portal: https://www.caspar-manufaktur.de/developers/
- OpenAPI 3.1: https://www.caspar-manufaktur.de/.well-known/openapi.json
- llms.txt: https://www.caspar-manufaktur.de/llms.txt
- API policy: https://www.caspar-manufaktur.de/api-policy/
- Contact: info@caspar-manufaktur.de

## Deutsch

Offizielle Regeln, MCP-Konfiguration und Plugin-Manifest für KI-Werkzeuge, die mit den öffentlichen Schnittstellen von Caspar Manufaktur arbeiten: Materialdaten, Materialempfehlung, Auflösungsprüfung (Wallcheck) und Übergabe an das Caspar-Team. Keine Preise, keine automatischen Bestellungen.

## License

MIT © Caspar GmbH
