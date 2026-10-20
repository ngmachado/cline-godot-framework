# Create a game with Cline and Godot

This framework gives Cline three roles and a library of game-development skills. You talk to one **Game Director**, which coordinates programming, art, and validation. During the tutorial, you will connect Cline to Godot through MCP and ask the team to create a small demo.

The package contains instructions and templates. You create the game yourself with Cline.

## Tutorial path

1. [Configure Cline's roles and skills](#1-configure-clines-roles-and-skills).
2. [Set up MCP in Godot and Cline](#2-set-up-mcp-in-godot-and-cline).
3. Browse and invoke skills with `/`.
4. [Ask the Director to create and test the demo](#4-ask-the-director-to-create-and-test-the-demo).

We are developing this guide one step at a time. Steps 1, 2, and the final demo prompt are below. Step 3, browsing and invoking skills with `/`, is still to be developed.

## How the three roles work

| Role | Responsibility |
|---|---|
| **Game Director** | Understands your request, chooses skills, assigns work, integrates results, and checks completion. This is your main chat. |
| **Game Developer** | Implements gameplay code and performs technical checks. Reports to the Director. |
| **Creative Artist** | Defines the visual direction and prepares the requested assets or specifications. Reports to the Director. |

A **role** defines responsibility. A **skill** provides a procedure for a particular task, such as gameplay programming or art direction. **MCP** gives the Director tools to interact with the Godot editor.

Testing is handled through skills and the Director's review; there is no separate QA role.

## 1. Configure Cline's roles and skills

### Before you begin

Have Cline installed and a model/provider configured. This walkthrough uses **Cline Desktop**, which supports ordinary subagents. Cline's IDE extensions can perform the role phases sequentially, but do not provide this same subagent workflow.

You do not need a running game or an MCP connection for this step.

### Add the framework to your workspace

Create a folder for your demo and copy the framework into it, including the hidden `.cline` folder. Open that folder as your Cline workspace. If you already have a Godot project, use its root folder and merge any existing instructions rather than overwriting them.

```text
my-demo/
├── README.md
├── AGENTS.md
├── .cline/
│   └── skills/
│       ├── game-concept/SKILL.md
│       ├── gameplay-programming/SKILL.md
│       ├── godot-editor/SKILL.md
│       └── ...
├── roles/
│   ├── game-director.md
│   ├── game-developer.md
│   └── creative-artist.md
├── SKILLS_INDEX.md
├── protocols/
├── workflows/
├── templates/
├── project/
├── tasks/
└── integrations/
```

On macOS, press **Cmd+Shift+.** in Finder to show hidden folders.

### What the files do

| File or folder | What it contains | How it is used |
|---|---|---|
| [AGENTS.md](AGENTS.md) | Project-wide instructions for the team. | Cline reads these rules to establish the Director-led workflow. |
| [roles/](roles/) | The three role definitions. | The Director reads its own role and supplies the appropriate worker role when delegating. |
| [.cline/skills/](.cline/skills/) | 34 skills, each in its own folder with a `SKILL.md`. | Cline discovers their names and descriptions, then loads the procedures when needed. |
| [SKILLS_INDEX.md](SKILLS_INDEX.md) | Skills grouped by responsibility. | A quick reference for finding the right procedure. |
| [protocols/](protocols/) | Shared rules for delegation, context, MCP access, and acceptance. | Keep handoffs and checks consistent across tasks. |
| [workflows/](workflows/) | Sequences for larger requests, such as creating a game or fixing a bug. | The Director chooses a workflow that fits your request. |
| [templates/](templates/) | Reusable task, art-brief, and test-report formats. | Copy or use as formats for project/task records; keep templates blank. |
| [project/](project/) | Initially blank project context. | The team records the game's vision, design, art direction, architecture, engine setup, and progress here. |
| [tasks/](tasks/) | Individual task contracts and handoffs. | Required for every delegated task: record ownership, writable files, and handoff; `project/TASK_BOARD.md` is the overview. |
| [integrations/](integrations/) | Engine connection guidance. | Points to the Godot MCP setup step below. |

You do not need to read every skill or create every project record before starting. The Director uses the relevant files as work proceeds. `project/GAME_VISION.md` and `project/GAME_DESIGN.md` describe what to build; `project/ART_DIRECTION.md` and `project/ARCHITECTURE.md` guide how to build it; `project/PROJECT_STATUS.md` and `project/TASK_BOARD.md` track progress.

### Enable the roles and skills

1. Open Cline's rules controls and confirm the workspace's `AGENTS.md` is enabled.
2. Open the Skills list and look for `game-concept`, `gameplay-programming`, and `godot-editor`. Keep the skills you intend to use enabled.
3. In Cline Desktop, open **Customize → Tools** and enable `spawn_agent` for separate Developer and Artist workers. Start a new chat after changing this setting.

The role files do not start workers automatically. The Director must delegate through Cline's actual subagent capability. Ordinary Cline subagents handle file tasks but do not receive MCP tools; the Director performs the Godot editor operations.

Keep one copy of each project skill under `.cline/skills/`. If you are migrating an earlier framework copy from `.agents/skills/`, move the skills rather than maintaining duplicate versions.

### Start the Director conversation

Paste this into a new Cline chat:

> Read AGENTS.md and roles/game-director.md. Act as my Game Director and keep this as our only conversation. Confirm the responsibilities of the Game Developer and Creative Artist, and list the project skills available to you. Distinguish native Cline skill discovery from a filesystem listing, and say if discovery or invocation is unavailable. Do not create game files, spawn workers, or use MCP yet.

**Expected result:** Cline identifies the three roles, reports the available skills, and understands that the Director coordinates the work.

If the rules or skills are missing, check that the workspace is the folder containing `AGENTS.md` and `.cline/skills/`. Confirm each skill has a `SKILL.md`, then reopen the workspace or start a new session.

**Next:** connect your Godot project using step 2 below.

## 2. Set up MCP in Godot and Cline

This tutorial uses **NPGameDev Godot MCP Toolkit** in Godot and its companion **`@npgamedev/godot-mcp-server`** bridge in Cline. You install and configure these on your computer; this framework does not include the plugin or a preconfigured connection. [Provider documentation](https://github.com/NPGameDev/godot-mcp-toolkit)

### Prepare your computer and project

Use Godot **4.2 or newer** and Node.js **22 or newer**, with npm/npx available. Run these commands in a terminal to check Node and npm:

```sh
node --version
npm --version
npx --version
```

If a command is missing, install [Node.js](https://nodejs.org/en/download), then restart Cline so it can find the tools. The bridge requires Node.js 22+. [Bridge prerequisites](https://github.com/NPGameDev/godot-mcp-server)

Open your Godot project and the same folder in Cline. If starting fresh, create the Godot project in your demo workspace first. The project root is the folder containing `project.godot`. Keep Godot and Cline running locally on the same computer for this tutorial.

### Install and enable the plugin in Godot

1. In Godot, open **AssetLib**, search for **Godot MCP Toolkit**, and select the NPGameDev package.
2. Download and install it into your project. Alternatively, use the provider’s [releases](https://github.com/NPGameDev/godot-mcp-toolkit/releases) and place the addon at `addons/godot_mcp_toolkit/`.
3. Open **Project → Project Settings → Plugins** and enable **Godot MCP Toolkit**.
4. Check that the MCP dock appears and the Output panel reports a listening address. Keep the editor open.

The default editor port is 6550, but the plugin can select another port in 6550–6560. Check the dock for the actual port; automatic discovery normally handles it. [Plugin installation](https://github.com/NPGameDev/godot-mcp-toolkit#quick-start)

### Configure the bridge in Cline

In **Cline Desktop**, use **Customize → Installed** to find and manage MCP servers. The standard MCP settings file is `~/.cline/data/settings/cline_mcp_settings.json` (`~` means your user home folder). If you use a custom Cline configuration directory, use its settings file instead. [Desktop controls](https://docs.cline.bot/usage/cline-desktop), [configuration locations](https://docs.cline.bot/getting-started/config)

In the **Cline IDE extension**, open **MCP Servers → Configure → Configure MCP Servers** to open the active settings file. [Cline MCP configuration](https://docs.cline.bot/mcp/mcp-overview)

Add the following entry to that file. If it already contains servers, merge `godot-mcp-toolkit` into the existing `mcpServers` object instead of replacing the file.

**macOS / Linux:**

```json
{
  "mcpServers": {
    "godot-mcp-toolkit": {
      "command": "npx",
      "args": ["-y", "@npgamedev/godot-mcp-server"],
      "env": {
        "GODOT_MCP_PROJECT_PATH": "/absolute/path/to/my-demo"
      },
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

**Windows:**

```json
{
  "mcpServers": {
    "godot-mcp-toolkit": {
      "command": "cmd",
      "args": ["/c", "npx", "-y", "@npgamedev/godot-mcp-server"],
      "env": {
        "GODOT_MCP_PROJECT_PATH": "C:/Users/YourName/my-demo"
      },
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

Replace the project path with your actual absolute folder path, preserving the quotes. On Windows, forward slashes avoid JSON backslash escaping. The server name is **`godot-mcp-toolkit`**, without `@`. The `@` appears only in the scoped npm package name inside `args`; keep it there.

Cline starts the bridge through `npx`, which downloads the package on first use. A separate global npm installation is not required. `GODOT_MCP_PROJECT_PATH` selects the project explicitly; update it when switching projects. The Windows configuration wraps `npx` with `cmd /c`. [Provider’s client configuration guide](https://npgamedev.github.io/godot-mcp-server/mcp-clients/)

Save the settings, restart or reconnect the MCP server in Cline, and start a new Director chat if the tools do not appear. Check that `godot-mcp-toolkit` is enabled and its tools are listed. Keep `autoApprove` empty for this setup; approve the read-only inspection when requested. A toolkit-generated `.mcp.json` is not a substitute for configuring Cline’s active MCP settings.

### Test the connection with the Director

Paste this into your Director conversation:

> Read AGENTS.md and act as my Game Director. Use the engine-capability-probe skill to check whether Cline is connected to my open Godot project through MCP. Discover the available tools and perform a read-only query against the editor. Report the project’s absolute path, the active scene if available, and which tool returned the information. Distinguish a responding MCP server from a working editor connection. If anything fails, explain what is missing. Do not modify files or scenes, launch the game, or spawn workers. Return the findings in this chat.

**Expected result:** the Director reports actual editor data matching your intended project and identifies the successful MCP call. If no scene is open, it should report that limitation and use project metadata where available. A tool list alone does not prove that the editor is connected.

This checks the connection only. Editing scenes, launching a game, and testing gameplay remain untested at this stage.

### If the check fails

| Symptom | Check |
|---|---|
| Plugin or MCP dock is missing | Confirm the addon is installed in this project and enabled under Plugins. |
| Cline cannot start `npx` or `node` | Check the terminal commands above and restart Cline after installing Node. On Windows, use the `cmd` configuration. |
| Tools are listed, but editor queries fail | Keep Godot open; check the plugin’s listening status and the configured project path. |
| The wrong project is reported | Correct `GODOT_MCP_PROJECT_PATH`, reconnect, and repeat the read-only check. |

For connection diagnostics, see the [provider’s troubleshooting guide](https://github.com/NPGameDev/godot-mcp-toolkit/blob/main/docs/troubleshooting.md). Do not report a connection as working until an editor query succeeds against the intended project.

**Next:** step 3 will cover browsing and invoking skills with `/`. The final demo prompt is provided below.

## 4. Ask the Director to create and test the demo

After configuring the roles and skills and passing the MCP connection check, paste this into your Director conversation. This prompt authorizes the team to create and test the demo in your Godot project.

```text
Act as my Game Director. Read AGENTS.md and roles/game-director.md. Use our
configured roles and skills to create a small Godot game called “Catch the Coin.”

First, verify through MCP that you are connected to the correct Godot project.
Inspect existing files before making changes and preserve unrelated work.

Build this demo:
- One 2D scene with a dark background.
- A blue square player controlled by WASD or arrow keys.
- Keep the entire player inside the screen.
- A gold coin that increases the score by one when collected.
- After each collection below three, respawn the coin at a random position
  fully inside the screen, away from the player.
- Show “Coins: 0 / 3” at the top, updating as coins are collected.
- After three coins, hide the coin and display “You Win!”
- Press R to restart: reset the score, player and coin, and hide the win message.

Use basic Godot shapes and the default font. Do not add external assets,
audio, menus, levels, or other features.

Coordinate the work:
1. Define the scene structure and acceptance checks. Create a required record
   under tasks/ for every delegated task, using templates/task.md as the format.
   Keep project/TASK_BOARD.md as the overview and leave reusable templates blank.
2. Assign the Creative Artist a minimal visual specification.
3. Assign the Game Developer the gameplay scripts and integration instructions.
4. Give workers clear file boundaries and relevant role/skill instructions.
   Record their returned handoffs and your acceptance in the task records.
5. Perform Godot MCP operations yourself; ordinary Cline subagents do not have
   MCP tools. Developer may perform authorized source edits and command-line checks.
6. Integrate the results, save the scene, and test the game using the relevant
   validation skills. Record actual results and unrun checks in project/TEST_PLAN.md.

Keep this as our only conversation. If worker spawning or a required tool is
unavailable, explain the limitation instead of claiming it ran.

Finish by telling me which scene to run, what you verified, and what I should
check manually. Distinguish scene launch from verified gameplay behavior.
```

**Expected result:** the Director coordinates the Artist and Developer, integrates their work through MCP, and reports a saved scene with actual test results or explicit blockers. A generated script or successful launch alone does not establish that the game works.

When you run the reported scene, check:

- Both WASD and arrow keys move the blue square, which stays fully on screen.
- Each coin adds exactly one point; the first two collections produce a new coin inside the screen and away from the player.
- The third collection leaves the counter at `Coins: 3 / 3`, hides the coin, and displays `You Win!`.
- R resets the game both during play and after winning, returning the counter to `Coins: 0 / 3` and hiding the win message.

## Cline references

- [Rules and AGENTS.md](https://docs.cline.bot/customization/cline-rules)
- [Skills and slash commands](https://docs.cline.bot/customization/skills)
- [Subagents and tool access](https://docs.cline.bot/features/subagents)
