# Quest OS

> An operating system for your quests, powered by Obsidian, Claude, and a daily loop that actually sticks.

---

## What is this?

I got tired of setting goals that die after two weeks.

You know how it goes. You get motivated, write a big plan, maybe even make a Notion board. Then life happens, you skip a few days, and suddenly you haven't touched it in a month. The plan is still there, perfectly formatted, completely ignored.

**quest-os** is my answer to that. It's an Obsidian vault that turns any goal into a structured **journey** with daily quests, a tracker, and an AI coach (Claude) that keeps the whole thing alive.

You tell Claude what you want to achieve. It builds out the entire system for you: strategy, timeline, skill tracker, daily quest format, everything. Then every day, you just say **"daily quest"** and Claude gives you exactly what to do today based on where you actually are, not where you hoped to be.

When you're done, you say **"submit quest"** and Claude evaluates your session, updates the tracker, and queues up your next review. That's the full loop.

It's not a to-do list. It's not a habit tracker. It's closer to a personal RPG system, except the quests are real and they compound.

---

## Why "quest-os"?

Two parts:

- **Quest**: Because I wanted goals to feel like quests, not chores. Every day you get a small, clear mission. You do it. You level up. The framing matters more than people think.
- **OS**: As in *operating system*. Not because it's an actual OS, but because it's the layer that runs underneath everything. Whatever goal you're chasing (a job, a language, a business), quest-os is the system that manages it. You plug in a goal, and the OS handles the structure, tracking, scheduling, and review.

So: **quest-os** = an operating system for running quests on your life goals.

Also, it just sounds cool. I'm not gonna pretend that wasn't part of it.

---

## What's inside

```
quest-os/
├── Goal Journey Template/       ← The reusable system (start here)
│   ├── 00 MOC.md                ← Map of Content: how everything connects
│   ├── 01 Goal Input Format.md  ← How to write your goal so Claude gets it
│   └── 02 Master Prompt.md      ← The prompt that generates your entire journey
│
└── Japanese Fluency Journey/    ← A real example journey (JLPT N3 in 12 months)
    ├── 00 MOC.md
    ├── 01 Context & Why.md
    ├── 02 Strategy.md
    ├── 03 Skill Strategy.md
    ├── 04 Timeline & Phases.md
    ├── 05 Tracker.md
    ├── 06 Visibility & Branding.md
    ├── 07 Target List.md
    ├── 08 Budget & Resources.md
    ├── 09 Key Decisions.md
    └── Vocab/                   ← Skill-specific tracker + daily quest context
```

The **Goal Journey Template** folder is the engine. The **Japanese Fluency Journey** is a working example of what it produces.

---

## How it works (the short version)

1. Write your goal using the format in `01 Goal Input Format.md`
2. Paste the prompt from `02 Master Prompt.md` into Claude, with your goal filled in
3. Claude generates an entire journey folder (10+ files). Save them in Obsidian.
4. Every day: say **"daily quest"** → do the quests → say **"submit quest"**
5. Repeat. That's it.

---

## Setup Guide

You need three things installed and running: **Claude Desktop**, **Docker Desktop**, and **Obsidian**. They work together like this:

- **Obsidian**: where your notes and trackers live
- **Claude Desktop**: the AI that reads your vault and generates daily quests
- **Docker Desktop**: the bridge that connects Claude to Obsidian (via MCP)

Let's set them up.

---

### 1. Install Claude Desktop

Claude Desktop is the local app for Anthropic's Claude. The AI still runs on Anthropic's cloud. You're just using the desktop app as the interface.

1. Go to [claude.ai/download](https://claude.ai/download)
2. Download the macOS (or Windows) version
3. Install and sign in with your Anthropic account
4. The **free plan** works fine and includes MCP support. There's a daily message limit, but it's enough for the daily quest loop. If you find yourself hitting the limit often, the Pro plan ($20/month) removes that cap.

> **Why Claude Desktop and not the web?** Because the desktop app supports MCP (Model Context Protocol), which is what lets Claude actually read and write to your Obsidian vault. The web version can't do that.

---

### 2. Install Docker Desktop

Docker runs the MCP server that connects Claude to Obsidian. Think of it as the middleman. It takes requests from Claude ("read this note", "update this tracker") and forwards them to Obsidian's API.

1. Go to [docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop/)
2. Download and install for your OS
3. Open Docker Desktop and let it finish its initial setup
4. Make sure Docker is **running** (you'll see the whale icon in your menu bar / system tray)

You don't need to know Docker to use this. Just keep it running in the background.

---

### 3. Install Obsidian and Required Plugins

#### Install Obsidian

1. Go to [obsidian.md](https://obsidian.md/)
2. Download and install
3. Open Obsidian and create a new vault (or open this repo as a vault)
   - If opening this repo: `Open folder as vault` → select the `quest-os` folder

#### Enable Community Plugins

1. Go to **Settings** → **Community plugins**
2. Turn off **Restricted mode** (this allows third-party plugins)
3. Click **Browse** to open the plugin catalog

#### Install the Local REST API Plugin

This is the plugin that lets external apps (Claude, through Docker) talk to your Obsidian vault.

1. In the community plugin browser, search for **"Local REST API"**
2. Click **Install**, then **Enable**
3. Go to the plugin's settings (Settings → Community plugins → Local REST API → ⚙️)
4. You'll see an **API Key**. Copy this, as you'll need it in the next step.
5. Note the port number (default is `27124`). Leave it as-is unless you have a conflict.

> **Keep Obsidian open** whenever you're using quest-os. The REST API only works while Obsidian is running.

---

### 4. Connect Everything Together

Now wire Claude → Docker → Obsidian:

#### Set up the Obsidian MCP Server in Docker

1. Open **Docker Desktop**
2. Look for the **MCP Toolkit** or **MCP Catalog** in the sidebar (Docker has built-in MCP support)
3. Search for the **Obsidian MCP server** in the catalog
4. Click the **+** to add it
5. In the server settings, paste your **Obsidian API Key** (the one you copied from the Local REST API plugin) into the secrets/environment field
6. Save and start the server

#### Connect Claude Desktop to Docker

1. In Docker Desktop, go to the **Clients** section
2. Find **Claude Desktop** in the list
3. Click **Connect**
4. **Restart Claude Desktop** completely (quit and reopen)

#### Verify the Connection

1. Open Claude Desktop
2. Look for the 🔌 or tools icon in the chat input area
3. You should see **MCP_Docker** (or similar) listed with Obsidian tools like:
   - `obsidian_search`
   - `obsidian_create_note`
   - `obsidian_get_note`
   - `obsidian_update_note`
   - etc.

If you see those tools, you're good. Claude can now read and write to your vault.

---

### 5. Quick Start

Now that everything is connected:

1. Open the `Goal Journey Template/01 Goal Input Format.md` and fill in your goal
2. Copy the prompt from `Goal Journey Template/02 Master Prompt.md`
3. Open Claude Desktop, paste the prompt, and replace `[PASTE YOUR GOAL INPUT HERE]` with your filled-in goal
4. Claude will generate 10+ files. Save each one into a new journey folder in your vault.
5. Say **"daily quest"** to start your first day

---

## The Daily Loop

Once your journey is set up, this is all you do every day:

```
1. Open Claude Desktop (make sure Obsidian + Docker are running)
2. Say: "daily quest"
3. Claude reads your tracker, picks today's quests, outputs them
4. Do the quests
5. Say: "submit quest" with your session notes
6. Claude evaluates, updates your tracker, done
```

That's the whole system. Simple to run, hard to ignore.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| Claude doesn't show MCP tools | Restart Claude Desktop. Make sure Docker is running and the Obsidian MCP server is started. |
| "Connection refused" errors | Make sure Obsidian is open and the Local REST API plugin is enabled. Check the port (default: 27124). |
| Docker MCP catalog is empty | Update Docker Desktop to the latest version. MCP support was added in recent releases. |
| Claude can't find my notes | Make sure your vault path is correctly configured in the MCP server settings. The API key must match. |
| Tools show up but fail silently | Check Docker Desktop logs for the MCP server container. Usually it's an API key mismatch. |

---

## Creating a New Journey

Want to chase a different goal? Just run the process again:

1. Fill in a new goal using the input format
2. Paste the master prompt with your new goal into Claude
3. Save the generated files into a new folder (e.g., `FAANG SWE Journey/`)
4. Each journey is independent, so you can run as many as you want.

---

## License

This is a personal system I built for myself. You're welcome to fork it, adapt it, break it, whatever. If it helps you actually finish something you've been putting off, that's all I care about.
