# AGENTS.md

## Build/Lint/Test Commands

- **Format**: `stylua --check .` (check formatting) or `stylua .` (format)
- **Lint**: No dedicated linter - relies on stylua for formatting
- **Test**: No test framework configured - this is a Neovim config, not a software project
- **Health check**: Run `:checkhealth` in Neovim to verify configuration

## Code Style Guidelines

### Formatting
- Use **stylua** for all Lua code formatting
- Configuration in `.stylua.toml`: 2-space indentation, 160 char line width, single quotes preferred
- No trailing whitespace

### Lua Conventions
- Use `vim.keymap.set()` for key mappings
- Use `vim.opt` for setting options
- Use `vim.api.nvim_create_autocmd()` for autocommands
- Prefer `local` variables over global
- Use `---@type` annotations for type hints where helpful

### Plugin Configuration
- Use `lazy.nvim` for plugin management
- Plugin specs should be tables with `opts` for configuration
- Use `dependencies` key for plugin dependencies
- Lazy load plugins with `event`, `cmd`, or `ft` keys when possible

### File Organization
- Main config in `init.lua`
- Custom plugins in `lua/custom/plugins/`
- Keep plugin configurations self-contained
- Use descriptive keymap descriptions with `[L]` notation for leader keys

### Error Handling
- Use `pcall()` for optional operations that might fail
- Check plugin availability before use
- Gracefully handle missing external tools