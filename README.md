# Quest OS

> Turn your goals into daily quests. Powered by Obsidian, Claude, and MCP.

***

## The Problem with Goals

I've always wished my goals felt more like quests in a video game. Telling yourself to "learn Japanese" sounds like a chore. But framing it as "The N3 Fluency Quest" makes it an adventure. 

But even with the right framing, I kept hitting a wall: the daily planning overhead. Every time I sat down to work, I wasted precious energy figuring out *what* to do. What should I study today? What needs reviewing? The mental cost of managing the project was eating into the time I had to actually execute it.

I needed a system where the planning happened once, and the execution happened daily, without friction.

## Enter Quest OS

**Quest OS** is an Obsidian vault that acts as a local operating system for your ambitions. 

You define your goal exactly once. Claude (the AI) then generates a complete, structured journey system for you. It builds the strategy, the timeline, the tracker, and the map of your project.

From that point on, you don't plan. Every day, you simply open your computer and tell Claude: **"daily quest"**. Claude reads your vault via MCP, analyzes your progress, and tells you exactly what to do. You complete the work, then say **"submit quest"**. Claude evaluates your session, updates your local trackers, and queues up future reviews.

It is a closed-loop system that feels like a game and saves you from the burden of managing it yourself.

***

## What's Inside the Box?

The repository has a simple, modular structure:

```text
quest-os/
├── Goal Journey Template/       ← The core engine. Start here.
│   ├── 00 MOC.md                
│   ├── 01 Goal Input Format.md  
│   └── 02 Master Prompt.md      
│
└── Japanese Fluency Journey/    ← A generated example journey
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
    └── Vocab/                   ← The local tracker and daily context
```

***

## The Setup Guide

To automate this loop, you need three pieces of software working in harmony:

1. **Obsidian**: The local database where your notes and trackers live.
2. **Claude Desktop**: The AI orchestrator that generates and evaluates your daily quests.
3. **Docker Desktop**: The invisible bridge running the MCP server, allowing Claude to read and write directly to your Obsidian vault.

### 1. Install Claude Desktop

Download the macOS or Windows app from [claude.ai/download](https://claude.ai/download) and sign in. The **free plan** works perfectly and includes the MCP support we need. There is a daily message limit, but it is generally enough to run your daily quest loop. Upgrading to Pro ($20/month) simply removes that cap.

> **Why the desktop app?** The web version of Claude cannot read your local files. The desktop app supports the Model Context Protocol (MCP), which is the key to automating Obsidian.

### 2. Install Docker Desktop

Docker runs the MCP server, acting as the middleman. Download it from [docker.com](https://www.docker.com/products/docker-desktop/) and install it. Once set up, just leave it running in the background.

### 3. Configure Obsidian

Download Obsidian from [obsidian.md](https://obsidian.md/). Open this repository as your vault by choosing `Open folder as vault` and selecting the `quest-os` folder.

To expose Obsidian to Claude, install the necessary API plugin:
1. Go to **Settings** > **Community plugins**.
2. Turn off **Restricted mode**.
3. Click **Browse** and install **"Local REST API"**.
4. Enable the plugin, go to its settings, and **copy the API Key**. Leave the port as `27124`.

> **Note:** Keep Obsidian open while using Quest OS. The API only functions while the application is running.

### 4. Wire Everything Together

First, set up the server in Docker. Open Docker Desktop, navigate to the **MCP Toolkit** (or **MCP Catalog**), and add the **Obsidian MCP server**. In the settings, paste your **Obsidian API Key** into the secrets field, then start the server.

Next, connect Claude. In Docker Desktop's **Clients** section, find **Claude Desktop** and click **Connect**. Completely restart Claude Desktop (quit and reopen).

Finally, verify the connection. In Claude Desktop, click the tools icon (the plug symbol) in the chat input area. You should see `MCP_Docker` listed alongside tools like `obsidian_search` and `obsidian_update_note`. 

***

## Your First Quest

With the machinery in place, starting is simple:

1. Open `Goal Journey Template/01 Goal Input Format.md` and detail what you want to achieve.
2. Copy the prompt from `Goal Journey Template/02 Master Prompt.md`.
3. Open Claude Desktop, paste the prompt, and insert your goal.
4. Claude will generate all the necessary files. Save each one into a new folder in your vault.
5. Say **"daily quest"** to Claude to begin your very first day.

***

## The Daily Loop

Once your system is established, your daily commitment is simple:

Ensure Obsidian and Docker are running. Tell Claude, **"daily quest."** Step away and do the work it assigns. When finished, return and say, **"submit quest,"** providing any notes from your session. Claude updates your tracker, and your day is done.

***

## Troubleshooting

- **Missing MCP tools:** Restart Claude Desktop. Ensure Docker is running the Obsidian MCP server.
- **Connection refused:** Verify Obsidian is open and the Local REST API plugin is enabled.
- **Tools fail silently:** This is usually a mismatch with your API key in the Docker settings.

***

## A Final Word

I built this system to turn my ambitions into structured, manageable adventures without the daily friction of project management. You are welcome to fork it, adapt it, or break it to suit your own needs. 
