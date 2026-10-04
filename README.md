# gritz examples

Example configuration and workspace images for [gritz](https://github.com/gritzapp/gritz).

## Workspaces

Workspace configuration examples, for a runner's `workspaces.yaml`:

- [claude.yml](workspaces/claude.yml) - Claude Code
- [codex.yml](workspaces/codex.yml) - OpenAI Codex
- [cursor.yml](workspaces/cursor.yml) - Cursor Agent
- [copilot.yml](workspaces/copilot.yml) - GitHub Copilot
- [mcp-server.yml](workspaces/mcp-server.yml) - MCP server configuration
- [private-repo.yml](workspaces/private-repo.yml) - Cloning private repositories
- [dummy.yml](workspaces/dummy.yml) - Dummy agent for testing

## Docker Compose runner

[runner/](runner/) runs a gritz runner as a Docker Compose service with a
pull-through registry cache.

## Workspace images

[images/](images/) builds the general-purpose workspace images the examples use:

- `ghcr.io/gritzapp/gritz-workspace-debian`: Debian with common build tools and
  the Claude Code, Codex, Copilot and Cursor CLIs.
- `ghcr.io/gritzapp/gritz-workspace-mise`: the Debian image plus
  [mise](https://mise.jdx.dev/).

The images do not contain gritz: the runner copies its own driver binary into
each container when it creates it. They are rebuilt weekly and whenever
`images/` changes, and tagged `latest`, `YYYYMMDD` and `sha-<commit>`.
