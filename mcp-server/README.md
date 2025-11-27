# @stpb/mcp-server

Model Context Protocol (MCP) server for the **Story Telling Portal for the Brave** - enabling AI assistants to access healing journey APIs.

## Installation

```bash
npm install @stpb/mcp-server
# or
pnpm add @stpb/mcp-server
```

## Quick Start

### With Claude Desktop

Add to `~/.config/claude/config.json`:

```json
{
  "mcpServers": {
    "stpb": {
      "command": "npx",
      "args": ["@stpb/mcp-server"],
      "env": {
        "STPB_API_URL": "https://your-stpb-app.vercel.app",
        "STPB_AUTH_TOKEN": "your-auth-token"
      }
    }
  }
}
```

### With Claude CLI

```bash
claude --mcp-config '{
  "mcpServers": {
    "stpb": {
      "command": "npx",
      "args": ["@stpb/mcp-server"],
      "env": {
        "STPB_API_URL": "https://your-stpb-app.vercel.app",
        "STPB_AUTH_TOKEN": "your-auth-token"
      }
    }
  }
}'
```

## Available Tools (23)

### Story Beat Tools
| Tool | Description |
|------|-------------|
| `create_story_beat` | Create a reflection in yellow/violet/white-gold/emerald phase |
| `get_story_beats` | Retrieve user's reflections with optional filters |
| `share_story_beat` | Share a story beat with the community |
| `delete_story_beat` | Delete a story beat |

### Community Tools
| Tool | Description |
|------|-------------|
| `get_lighthouse_beams` | Get shared stories from the Community Lighthouse |
| `create_story_circle` | Create a ceremonial story circle |
| `get_story_circles` | List available story circles |
| `join_story_circle` | Join an existing circle |
| `witness_story` | Witness a shared story (non-advice response) |

### NCP (Narrative Context Protocol) Tools
| Tool | Description |
|------|-------------|
| `analyze_beat` | Analyze a story beat for narrative throughlines |
| `get_narrative_arc` | Get the user's narrative arc visualization |
| `validate_coherence` | Validate narrative coherence |
| `get_storyform` | Get complete NCP storyform |

### Wound Healing Tools
| Tool | Description |
|------|-------------|
| `get_wounds` | Get tracked developmental wounds |
| `update_wound_stage` | Progress a wound through healing stages |
| `get_wound_categories` | Get Eight Feelings reference framework |

### Ceremony Tools
| Tool | Description |
|------|-------------|
| `initiate_ceremony` | Start a ceremony session |
| `get_wisdom` | Retrieve wisdom from ceremonies |
| `get_ceremony_stages` | Get Four Movements reference |

### Eva (AI Companion) Tools
| Tool | Description |
|------|-------------|
| `eva_analyze` | Analyze text for emotions and patterns |
| `eva_suggest_phase` | Get suggested narrative phase |
| `eva_detect_insight` | Detect insights in story beats |
| `get_companionship_guidelines` | Get witnessing vs. advice guidelines |

## Narrative Phases

| Phase | Color | Purpose |
|-------|-------|---------|
| **Yellow** | Inquiry | Questions, seeking understanding |
| **Violet** | Reflection | Processing, exploring emotions |
| **White-Gold** | Insight | Wisdom emerging, clarity |
| **Emerald** | Commitment | Action, moving forward |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `STPB_API_URL` | Yes | URL of the STPB Next.js application |
| `STPB_AUTH_TOKEN` | Yes | Bearer token for API authentication |

## Example Usage

```
User: Create a yellow phase reflection about my confusion

Claude: [calls create_story_beat with phase="yellow", text="..."]

Result: Story beat created with ID abc123
```

```
User: Analyze my latest story beat for narrative throughlines

Claude: [calls analyze_beat]

Result: Main Character throughline detected (85% confidence)
```

## Development

```bash
# Clone and install
git clone https://github.com/jgwill/STPB.git
cd STPB/mcp-server
pnpm install

# Build
pnpm build

# Run in development
pnpm dev
```

## License

MIT
