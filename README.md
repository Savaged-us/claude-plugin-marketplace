# Savaged Plugin Marketplace

Official Claude Code plugin marketplace for the Savaged-us organization.

## Installation

Add this marketplace to your Claude Code installation:

```bash
/plugin marketplace add Savaged-us/claude-plugin-marketplace
```

## Usage

Once added, you can browse and install plugins from this marketplace:

```bash
# List all available plugins
/plugin marketplace list

# Install a plugin from this marketplace
/plugin install <plugin-name>@savaged-marketplace
```

## Available Plugins

Currently, this marketplace is empty. Plugins will be added as they are developed.

## Adding Plugins to this Marketplace

### Option 1: Plugin hosted in separate repository

Add an entry to `.claude-plugin/marketplace.json`:

```json
{
  "name": "your-plugin-name",
  "description": "Brief description of your plugin",
  "source": {
    "source": "github",
    "repo": "Savaged-us/your-plugin-repo"
  },
  "version": "1.0.0",
  "author": "Your Name",
  "category": "productivity",
  "keywords": ["keyword1", "keyword2"]
}
```

### Option 2: Plugin included in this repository

1. Create a directory in `plugins/` for your plugin
2. Add the plugin files following Claude Code plugin structure
3. Add an entry to the marketplace.json:

```json
{
  "name": "your-plugin-name",
  "description": "Brief description",
  "source": "./plugins/your-plugin-name",
  "version": "1.0.0"
}
```

## Plugin Structure

Each plugin should follow this structure:

```
your-plugin/
├── plugin.json          # Plugin metadata
├── commands/            # Custom slash commands
│   └── example.md
├── agents/             # Custom agents
│   └── example.md
└── hooks/              # Custom hooks
    └── example.sh
```

### Minimal plugin.json example:

```json
{
  "name": "your-plugin-name",
  "version": "1.0.0",
  "description": "Your plugin description",
  "author": "Your Name"
}
```

## Team Configuration

To automatically install this marketplace for your team, add to `.claude/settings.json`:

```json
{
  "extraKnownMarketplaces": {
    "savaged-marketplace": {
      "source": {
        "source": "github",
        "repo": "Savaged-us/claude-plugin-marketplace"
      }
    }
  }
}
```

## Contributing

1. Fork this repository
2. Add your plugin following the structure above
3. Submit a pull request with your plugin addition

## License

MIT
