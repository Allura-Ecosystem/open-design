# Allura Design — Deploy Guide

> Open Design customized for the Allura ecosystem: Allura + Faith Meats brand systems, Team Durham brand production, Allura Brain memory, Hermes Agent adapter, Docker, and Cloudflare Tunnel for `design.faithmeats.com`.

## What this is

This is a customized deployment of [Open Design](https://github.com/nexu-io/open-design) — a local-first design product that detects your installed code-agent CLI, runs design skills + design systems, and streams artifacts into a sandboxed preview.

The Allura customization adds:

| Layer | What | Where |
|-------|------|-------|
| **Brand design systems** | Allura (warm cream/charcoal/blue) + Faith Meats (Snow/Night/Gold + 5 flavors) | `design-systems/allura/`, `design-systems/faithmeats/` |
| **Skills** | allura-brand, allura-memory, faith-meats-brand, team-durham-brand-loop | `skills/` |
| **MCP** | Allura Brain governed memory server | `apps/daemon/src/mcp-config.ts` (template `allura-brain`) |
| **Hermes** | Hermes Agent adapter (pre-existing) + hermes-allura-brain plugin | `apps/daemon/src/runtimes/defs/hermes.ts`, `~/.hermes/plugins/memory/allura-brain/` |
| **Docker** | Allura-specific compose overlay + env template | `deploy/docker-compose.allura.yml`, `deploy/.env.allura.example` |
| **Cloudflare** | Tunnel config + Access policy for design.faithmeats.com | `deploy/cloudflared.yml`, `deploy/cloudflare-access-policy.yml` |

## Architecture

```
                    ┌─────────────────────────────────────┐
                    │   design.faithmeats.com              │
                    │   (Cloudflare Access: sasheed@       │
                    │    faithmeats.com only)              │
                    └─────────────────┬───────────────────┘
                                      │
                    ┌─────────────────▼───────────────────┐
                    │   Cloudflare Tunnel (cloudflared)   │
                    └─────────────────┬───────────────────┘
                                      │
                    ┌─────────────────▼───────────────────┐
                    │   Allura Design daemon (Docker)     │
                    │   - Open Design daemon (port 7456)   │
                    │   - Allura + Faith Meats design     │
                    │     systems bundled                 │
                    │   - Allura + Durham + Faith Meats   │
                    │     skills bundled                  │
                    │   - Allura Brain MCP template       │
                    │   - Hermes adapter enabled          │
                    └─────────────────┬───────────────────┘
                                      │
                    ┌─────────────────▼───────────────────┐
                    │   Allura Brain MCP (host)           │
                    │   localhost:5888/mcp                │
                    │   - PostgreSQL episodic traces      │
                    │   - RuVector/Neo4j semantic memory  │
                    │   - HITL curator                    │
                    └─────────────────────────────────────┘
```

## Quick start

### Prerequisites

- Docker + Docker Compose
- Allura Brain MCP server running on the host (default: `localhost:5888/mcp`)
- Cloudflare account with `faithmeats.com` zone
- Hermes Agent installed (optional, for Hermes adapter)

### 1. Configure environment

```bash
cd open-design/deploy
cp .env.allura.example .env
```

Edit `.env` and fill in:
- `OD_API_TOKEN` — generate with `openssl rand -hex 32`
- `CLOUDFLARE_TUNNEL_TOKEN` — from Cloudflare dashboard

### 2. Set up Cloudflare

**Option A — Dashboard (recommended)**

1. Go to https://one.dash.cloudflare.com/ → Networks → Tunnels
2. Create a tunnel named `allura-design`
3. Copy the token to `.env` as `CLOUDFLARE_TUNNEL_TOKEN`
4. Add public hostname: `design.faithmeats.com` → `http://open-design:7456`
5. Go to Access → Applications → Add application → Self-hosted
6. Public hostname: `design.faithmeats.com`
7. Identity provider: One-time PIN
8. Policy: Allow emails `sasheed@faithmeats.com`

**Option B — CLI**

```bash
cloudflared tunnel login
cloudflared tunnel create allura-design
cloudflared tunnel route dns allura-design design.faithmeats.com
# Copy the token from ~/.cloudflared/<tunnel-id>.json to .env
```

### 3. Start the stack

```bash
docker compose -f deploy/docker-compose.allura.yml --env-file deploy/.env up -d
```

### 4. Verify

```bash
# Health check (from host)
curl http://localhost:7456/api/health

# Visit the app
open https://design.faithmeats.com
```

You'll be prompted to enter your email. Enter `sasheed@faithmeats.com` and check your inbox for a one-time PIN.

## Design systems

Two brand design systems are bundled and auto-discovered by the daemon:

### Allura (`design-systems/allura/`)

Warm, governed, connected, evidence-first. The AI memory layer for real life.

- **Canvas:** Allura cream `#f6f3ec`
- **Text:** Allura charcoal `#1b1d21`
- **Accent:** Allura blue `#2961b8`
- **Typography:** IBM Plex Sans + IBM Plex Mono
- **Use for:** Allura Memory, Team RAM, RuVix, Allura ecosystem work

### Faith Meats (`design-systems/faithmeats/`)

Premium halal beef jerky. Globally inspired, ethically sourced, community-rooted.

- **Canvas:** Snow `#FBF5F3`
- **Text:** Night `#0B0808`
- **Accent:** Gold `#C8AD55`
- **Flavor colors:** 5 documented colors (Shawarma, Harissa, Korean, Balinese, Sriracha)
- **Typography:** Crimson Pro (headings) + DM Sans (body)
- **Use for:** Faith Meats newsletters, company overviews, invoices, marketing

Select either design system from the Open Design UI when creating a project. The daemon auto-discovers them from `design-systems/`.

## Skills

Four skills are bundled and auto-discovered:

| Skill | Trigger | Purpose |
|-------|---------|---------|
| `allura-brand` | "allura brand", "allura visuals" | Apply Allura brand identity to artifacts |
| `allura-memory` | "allura memory", "remember this" | Governed memory operations through Allura Brain MCP |
| `faith-meats-brand` | "faith meats", "halal jerky" | Apply Faith Meats brand identity to content |
| `team-durham-brand-loop` | "team durham", "brand loop" | Team Durham brand production pipeline |

## Allura Brain MCP

The Allura Brain MCP server provides governed memory:
- `memory_search` — search episodic + semantic memory
- `memory_add` — add a memory event (append-only)
- `audit_*` — audit trail queries
- `governance_*` — governance/policy queries

The daemon includes an `allura-brain` MCP template (in `apps/daemon/src/mcp-config.ts`) pointing to `http://localhost:5888/mcp` by default. Inside Docker, the daemon reaches a host-running Brain via `host.docker.internal:5888/mcp` (override with `ALLURA_BRAIN_URL`).

To enable Allura Brain in a project:
1. Open the project in Open Design
2. Go to Settings → MCP servers
3. Add the `allura-brain` template
4. The agent now has `memory_search` and `memory_add` tools

### Non-negotiable invariants

- `group_id` on every read/write (pattern `^allura-[a-z0-9-]+$`)
- PostgreSQL traces are append-only (no UPDATE/DELETE)
- Semantic graph uses SUPERSEDES (never edit nodes)
- HITL required for promotion (agents cannot promote their own knowledge)
- DB operations via MCP only (never `docker exec`)

## Hermes Agent

The Hermes adapter is pre-existing in Open Design (`apps/daemon/src/runtimes/defs/hermes.ts`). It detects the `hermes` CLI on PATH and launches it with ACP (Agent Communication Protocol).

### Hermes + Allura Brain

The `hermes-allura-brain` plugin is installed at `~/.hermes/plugins/memory/allura-brain/`. To activate it:

1. Edit `~/.hermes/config.yaml`
2. Set `memory.provider: allura-brain`
3. Restart Hermes

The Docker compose mounts `~/.hermes` read-only into the container so the daemon can detect Hermes and its plugins.

## Docker

### Build the image

```bash
docker compose -f deploy/docker-compose.allura.yml build
```

The Dockerfile (unchanged from upstream) copies `skills/` and `design-systems/` into the image, so the Allura + Faith Meats design systems and all four skills are bundled automatically.

### Services

| Service | Purpose | Port |
|---------|---------|------|
| `open-design` | Allura Design daemon | 7456 (localhost only) |
| `cloudflared` | Cloudflare Tunnel to design.faithmeats.com | — |

### Volumes

| Volume | Purpose |
|--------|---------|
| `allura_design_data` | Daemon data (projects, artifacts, MCP config) |

### Security

- The daemon binds to `127.0.0.1` only — not exposed to the LAN
- Cloudflare Access protects `design.faithmeats.com` (email allow-list)
- `read_only: true` filesystem with `tmpfs` for `/tmp`
- `no-new-privileges:true` security opt
- Memory + PID limits enforced

## Cloudflare Access

Only `sasheed@faithmeats.com` can access `design.faithmeats.com`. All other emails are denied.

The Access policy is configured in the Cloudflare dashboard (see `deploy/cloudflare-access-policy.yml` for the spec). Identity provider is email One-time PIN — no password to manage, no SSO to configure.

## Customization

### Add a new design system

1. Create `design-systems/<brand>/` with `DESIGN.md`, `tokens.css`, `manifest.json`, `USAGE.md`, `design-tokens.json`, `tailwind-v4.css`, `components.html`, `components.manifest.json`, and `preview/` pages
2. Rebuild the Docker image — the daemon auto-discovers it

### Add a new skill

1. Create `skills/<skill-name>/SKILL.md` with frontmatter (`name`, `description`, `triggers`, `od.mode`)
2. Rebuild the Docker image — the daemon auto-discovers it

### Change the default Allura Brain URL

Edit `.env`:
```bash
ALLURA_BRAIN_URL=http://your-brain-host:5888/mcp
```

## Troubleshooting

### Daemon can't reach Allura Brain

Inside Docker, the daemon uses `host.docker.internal` to reach the host. On Linux, ensure Docker has `host.docker.internal` resolution:
```bash
# Add to docker-compose.allura.yml under open-design service:
extra_hosts:
  - "host.docker.internal:host-gateway"
```

### Hermes not detected

The daemon detects Hermes via PATH. Inside Docker, either:
- Install Hermes in the image (add to Dockerfile), or
- Mount the Hermes binary + config (already done via `~/.hermes` mount)

### Cloudflare Tunnel not connecting

1. Verify `CLOUDFLARE_TUNNEL_TOKEN` is set in `.env`
2. Check the tunnel is running: `docker compose -f deploy/docker-compose.allura.yml logs cloudflared`
3. Verify the DNS route: `cloudflared tunnel info allura-design`

### Access denied for sasheed@faithmeats.com

1. Verify the Access policy includes `sasheed@faithmeats.com` in the allow list
2. Check the email is spelled correctly (no typos)
3. Verify the One-time PIN identity provider is enabled

## Upstream sync

This is a fork of `nexu-io/open-design`. To sync with upstream:

```bash
git remote add upstream https://github.com/nexu-io/open-design.git
git fetch upstream
git merge upstream/main
# Resolve conflicts — our additions are all drop-in (design-systems/, skills/, deploy/)
git push origin main
```

Our customizations are isolated to:
- `design-systems/allura/` (new, no conflicts)
- `design-systems/faithmeats/` (new, no conflicts)
- `skills/allura-brand/` (new, no conflicts)
- `skills/allura-memory/` (new, no conflicts)
- `skills/faith-meats-brand/` (new, no conflicts)
- `skills/team-durham-brand-loop/` (new, no conflicts)
- `apps/daemon/src/mcp-config.ts` (one addition — `allura-brain` template)
- `deploy/docker-compose.allura.yml` (new, no conflicts)
- `deploy/.env.allura.example` (new, no conflicts)
- `deploy/cloudflared.yml` (new, no conflicts)
- `deploy/cloudflare-access-policy.yml` (new, no conflicts)
- `deploy/README-allura.md` (this file, new, no conflicts)

The only file that may conflict on upstream sync is `apps/daemon/src/mcp-config.ts` — the `allura-brain` template is appended to the `MCP_TEMPLATES` array.

## License

Open Design is Apache-2.0. Allura customizations are MIT.