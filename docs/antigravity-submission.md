# Antigravity Marketplace submission

Prepared on 2026-11-25 for Graphify 1.0.0, following Google's
[Build plugins](https://antigravity.google/docs/build-plugins/) guide. This is
submission preparation, not a claim of an existing listing.

## Package

This is a standalone Antigravity plugin: the manifest is `plugin.json` at the
repository root and every component sits beside it.

| Item | Value |
| --- | --- |
| Plugin name / display name | `graphify` / Graphify |
| Publisher | Graphify Labs |
| Repository | https://github.com/Graphify-Labs/graphify-antigravity |
| Manifest | `plugin.json` |
| MCP config | `mcp_config.json` (remote Streamable HTTP, `https://api.graphify.com/mcp`) |
| Rule | `rules/graphify.md` (`trigger: model_decision`) |
| Guide | `README.md` |
| Logo | `assets/logo.png` (512x512, transparent padding) |
| Version | `1.0.0` |
| Source license | Apache 2.0 |
| Website / docs | https://graphify.com / https://docs.graphify.com |
| Support | founders@graphify.com |
| Privacy / terms | https://graphify.com/privacy / https://graphify.com/terms |
| CLI install | `agy plugin install https://github.com/Graphify-Labs/graphify-antigravity` |

## Sign-in

The plugin declares no client ID or credentials. Antigravity discovers the
protected resource metadata from the 401 that `https://api.graphify.com/mcp`
returns, and Graphify's authorization server advertises dynamic client
registration and PKCE S256. Graphify allows both Antigravity callbacks:
`https://antigravity.google/oauth-callback` (desktop app and CLI) and
`https://antigravity.google.com/oauth/callback` (Marketplace installs). A
registration with the Marketplace callback returned 201 on 2026-11-25.

## Checks

- `agy plugin validate --strict .` (Antigravity CLI 1.5.16) passes with one
  rule, one MCP server, and no errors or warnings.
- `agy plugin install` loads the plugin enabled with one rule and one MCP server.
- CI runs the strict validation and pins the MCP connection and manifest fields.

## Not yet tested

- A live agent session in Antigravity, the browser sign-in, and tool calls.
  These need an Antigravity Google sign-in and a Graphify account.
- Installing from the Marketplace, which needs the listing.
