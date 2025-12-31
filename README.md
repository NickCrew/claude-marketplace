# Claude Private Marketplace

This repository hosts a Claude Code marketplace that exposes the private `claude-cortex` plugin. Point Claude Code at this git repository to make the plugin available organization-wide.

## Repository layout

- `.claude-plugin/marketplace.json` – marketplace manifest referencing the private plugin repo
- (optional) `docs/` – add internal onboarding or change logs here

## Usage

1. Ensure the `claude-cortex` plugin repository is available at `https://github.com/NickCrew/claude-cortex`.
2. Grant your team access to this public repository (or adjust the URLs if you fork it).
3. In Claude Code, add the marketplace:

   ```
   /plugin marketplace add NickCrew/claude-marketplace
   ```

4. Install the plugin:

   ```
   /plugin install claude-cortex@claude-private
   ```

## Local development

To test locally without pushing to GitHub, clone both repositories and update the plugin entry in `marketplace.json` to use a local `url` source instead of `github`. For example:

```json
{
  "source": {
    "source": "url",
    "url": "file:///Users/you/path/to/claude-cortex"
  }
}
```

After editing, run `claude plugin validate .` inside each repository to verify JSON structure before publishing.
