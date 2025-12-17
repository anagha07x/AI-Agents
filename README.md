🪙 Crypto Analysis Agent (LangGraph)
An interactive LLM-powered crypto market analysis agent built using LangGraph and LangChain, capable of calling external tools, retaining conversational memory across turns, and producing structured, data-backed insights.

🚀 Features
🔧 Tool-augmented reasoning
Lists cryptocurrencies
Fetches real-time market data
Retrieves recent crypto-related news
🧠 Memory-enabled conversations
Retains context across multi-turn interactions using thread_id
🔄 Graph-based execution
Deterministic agent flow using LangGraph nodes
💬 Interactive CLI chat
Supports follow-up questions like “What about ETH?”
🛑 Safe memory handling
Prevents context overflow by controlling memory growth

🧩 Architecture Overview
The agent is implemented as a LangGraph ReAct-style graph with the following nodes:
Assistant Node
Uses an LLM bound with tools via llm.bind_tools()
Decides when to call tools based on user intent
ToolNode
Executes the requested crypto tools
Conditional Routing
Routes control between assistant and tools based on detected tool calls
Memory is managed using a checkpoint-based system (MemorySaver) to enable multi-turn conversations.

🧠 Memory & Context Management
The agent supports context-aware conversations using a persistent thread_id.
To prevent token overflow during long sessions or repeated tests:
Each interactive session uses a fresh thread ID
Memory can be reset or pruned safely between runs
This avoids exceeding model context limits while preserving usability
