# Mini-Agent-Core: Personal AI on an M4 Mac Mini
📖 The Origin Story
Honestly, this whole thing started as a failed attempt to self-host OpenClaw. I wanted a local version running on my Mac Mini — something I could poke at, extend, and actually own.

I went deep into the plumbing, got lost, and realized I didn't need to replicate someone else's product. I needed a foundation I could actually modify. What emerged is a lean, vibe-coded pipeline:
Feishu (Lark) → Local Node.js → DeepSeek AI → Streaming Back.

###🪄 The "Frieren" Philosophy
I think about this project in terms of the magic system in Frieren: Beyond Journey's End. In that world, magic isn't about following a manual — it's about having a clear enough image in your head of what you want to happen.

The spell works if you truly believe in the shape of it. AI feels similar right now. If you can picture the workflow precisely enough, "vibe coding" can manifest it. The imagination is the hard part; the implementation is just following through.

⚡ The "Marketer" Edge: Why this way?
As a Marketer, I don't want to manage servers or complex NAT traversal. I want results.

WSS Connectivity: No public IP or Ngrok needed. The agent "dials out" via WebSocket Secure. If your Mac can browse the web, your agent can talk to the world.

Low Friction: It bypasses all the usual home-server networking headaches.

M4 Power: Running locally on the latest M4 silicon ensures zero-latency routing and future-proofs it for local LLMs (MLX/Ollama).

###🛠 The Setup

** 1. Environment
```bash
brew install node
npm install @larksuiteoapi/node-sdk axios
2. Core Logic (bot.js)
Note: I use placeholders for keys. In a production environment, always use environment variables.
```
** 2. Core Logic
```
javascript
/* MINI-AGENT-CORE v1.0 */
const Lark = require('@larksuiteoapi/node-sdk');
const axios = require('axios'); ...

const CONFIG = {
    APP_ID: 'YOUR_ID',       // Get from Feishu Open Platform
    APP_SECRET: 'YOUR_SECRET', 
    DEEPSEEK_KEY: 'YOUR_KEY'
};

// ... (Your core logic here)
```
**3. Deployment
To keep the agent alive 24/7 on my Mac Mini:

```
Bash
npm install -g pm2
pm2 start bot.js --name "mini-agent"
pm2 save
```
###🔮 Roadmap
This is a foundation, not a finished product. Next on my list:

[ ] System health reporting (CPU, RAM, thermals) via chat

[ ] Remote trigger for local macOS scripts/automation

[ ] Tavily Integration for real-time web search

Built by a Marketer on an M4 Mac Mini. Driven by imagination, manifested by AI.
