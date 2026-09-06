# hermes-mcp-ad-manager
Autonomous ad campaign management with Hermes Agent, Discord, and MCP.

# Hermes MCP Ad Manager

A lightweight local gateway that connects Hermes Agent to a private Discord bot, utilizing the Model Context Protocol (MCP) to autonomously manage cross-platform ad campaigns. 

This architecture completely bypasses the need to write and maintain fragile custom API integrations for individual ad networks (Meta, Google, TikTok, LinkedIn, etc.). Instead, the local agent handles intent parsing and decision-making, while the MCP server executes the API calls.

## Features
* **Local Decision Engine:** Run Hermes locally to keep prompt execution and logic on your own hardware.
* **Discord Interface:** Securely trigger terminal commands and manage campaigns on the go using natural language via a private Discord channel.
* **Zero Custom APIs:** Standardizes complex, multi-platform ad network executions through a single MCP bridge.

## Repository Contents
* `index.js`: The Discord bot initialization and local gateway routing script.
* `mcp_config.json`: The MCP server configuration block for Hermes.
* `.env.example`: Template for required environment variables.

## Prerequisites
To run this architecture, you will need:
1. [Node.js](https://nodejs.org/) installed locally.
2. A local installation of [Hermes Agent](https://github.com/NousResearch/Hermes).
3. A Discord Bot Token (generated via the Discord Developer Portal).
4. **LazyAds API Key:** This build uses the LazyAds BYOA (Bring Your Own Agent) plan as the MCP bridge for the ad networks. You can start your environment and get your API key [here]
(https://lazyads.ai/r/e5VCmo-50AF520B).

## Full Setup & Installation Guide
For the complete step-by-step tutorial on configuring the terminal environment, setting up the Discord gateway intents, and passing your API credentials to the MCP server, please refer to the full documentation:

📖 **[Read the Full Tutorial: Hermes Agent & LazyAds Integration]
(https://docs.google.com/document/d/1SxZabOel9fpdGjN5utvr8Ti2TLAuU8UqIOs-tBYH4ZE/edit?usp=drivesdk)**

## Usage Example
Once configured and running, you can drop natural language commands directly into your private Discord channel:

> `/ads analyze recent TikTok campaigns and pause anything with a ROAS under 1.5`

Hermes will parse the request locally, utilize the MCP bridge to fetch the live network data, execute the necessary pauses, and report the status back in Discord.
