# Prerequisites Reference

## Required Tools

| Tool           | Minimum Version | Check Command    | Install                |
| -------------- | --------------- | ---------------- | ---------------------- |
| Node.js        | **v22+**        | `node --version` | https://nodejs.org/    |
| Git (optional) | Any             | `git --version`  | https://git-scm.com/  |

The Power Apps CLI (`@microsoft/power-apps-cli`) is installed locally in the project — no global install is required. The template does not list it directly and recent `@microsoft/power-apps` releases no longer pull it in, so after `npm install` the scaffold flow checks for the `pa` shim and, if it is missing, runs `npm install --save-dev @microsoft/power-apps-cli` (see [cli-binary.md](../../../shared/cli-binary.md)).

## Required Account

- Power Platform account with code apps enabled
- At least one environment available
- Know your environment ID: find it in the URL at make.powerapps.com, e.g. `https://make.powerapps.com/environments/<env-id>/home`

## Required Permissions (allowedPrompts)

When using plan mode, include these in `allowedPrompts`:

```json
{
  "allowedPrompts": [
    { "tool": "Bash", "prompt": "check tool versions (node, git)" },
    { "tool": "Bash", "prompt": "scaffold power apps template (npx degit)" },
    { "tool": "Bash", "prompt": "install npm dependencies" },
    { "tool": "Bash", "prompt": "build for production (npm run build)" },
    { "tool": "Bash", "prompt": "initialize power apps project (pa app init)" },
    { "tool": "Bash", "prompt": "list connections (pa connection list)" },
    { "tool": "Bash", "prompt": "add data sources (pa app add data-source)" },
    { "tool": "Bash", "prompt": "deploy to power platform (pa app push)" }
  ]
}
```
