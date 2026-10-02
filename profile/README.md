<p>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./logo-dark.svg">
    <img src="./logo-light.svg" alt="Boxline" height="44">
  </picture>
</p>

### Give your AI agents the infrastructure they need: browsers, shells, storage and isolated machines.

An agent that does real work needs more than a model. It has to open websites, run code, keep files and sign in to
things, somewhere safe. Boxline gives each agent its own cloud machine for that, through one API.

- **Browsers**: real Chrome, driven by your agent, by Playwright or Puppeteer, or by computer-use models. Watch it
  live and take over when it needs a person.
- **Shells**: bash with Python and Node in the same machine, so the agent can download, install, run and check.
- **Storage**: a workspace disk shared by the browser and the shell, files in and out, and saved logins that carry
  over to the next session.
- **Isolated machines**: every session runs in its own sandboxed machine (gVisor). Pause it, resume it, or move it
  to a fresh machine with its tabs and files.

## Start

```bash
npm install @boxline/sdk        # Node and TypeScript
pip install boxline-sdk         # Python
npx -y @boxline/mcp             # MCP server for Claude, Cursor and other clients
```

```ts
import { Boxline } from "@boxline/sdk";

const bx = new Boxline(); // BOXLINE_API_KEY from the console
const run = await bx.agent.run({ task: "Open https://example.com and tell me what the page is about" });
console.log((await bx.agent.wait(run.id)).result);
```

## Repositories

| | |
|---|---|
| [sdk-node](https://github.com/Boxline-dev/sdk-node) | Node.js and TypeScript SDK (`@boxline/sdk`) |
| [sdk-python](https://github.com/Boxline-dev/sdk-python) | Python SDK, sync and async (`boxline-sdk`) |
| [mcp](https://github.com/Boxline-dev/mcp) | MCP server (`@boxline/mcp`) |
| [cli](https://github.com/Boxline-dev/cli) | The `boxline` command line (`@boxline/cli`) |
| [examples](https://github.com/Boxline-dev/examples) | 63 examples and 9 integrations in Node and Python, each with a result check, and Claude Code skills |

[Website](https://boxline.dev) · [Docs](https://docs.boxline.dev) · [Console](https://app.boxline.dev)
