# Learning Path & Implementation Formula

To successfully implement the 5 systems and pass the Claude Architect certification, we will follow this structured approach:

## Step 1: Your First Agent Loop
- **Concept:** The basic ReAct (Reason + Act) loop.
- **Action:** Build a simple agent that can search the web and write a summary.
- **Location:** `5_Symbols/1_agent_loop/`

## Step 2: Multi-Agent Orchestration
- **Concept:** Coordinator and Sub-agent patterns.
- **Action:** Build a supervisor agent that delegates tasks (e.g., a researcher agent and a writer agent).
- **Location:** `5_Symbols/2_multi_agent/`

## Step 3: Agent SDK Deep Dive
- **Concept:** Using the official SDKs effectively.
- **Action:** Refactor the previous systems using the official Anthropic Agent SDK for robustness.
- **Location:** `5_Symbols/3_agent_sdk/`

## Step 4: Claude Code & MCP Integration
- **Concept:** Giving Claude context about local or remote systems via the Model Context Protocol.
- **Action:** Build an MCP server that exposes local file data or a database to Claude.
- **Location:** `5_Symbols/4_mcp_integration/`

## Step 5: Structured Extraction & Reliability Patterns
- **Concept:** Extracting JSON reliably and handling failure modes.
- **Action:** Build a pipeline that takes messy unstructured data and outputs strict JSON using tool use / function calling.
- **Location:** `5_Symbols/5_structured_extraction/`

## Official Certification Path (Anthropic Academy)
Based on the official [Anthropic Partner Program announcement](https://youtu.be/O9yc_Qaj5Ns?si=mqflBgmgRXmwltvx) by Carl Kaden and Haley Waker:
- The **CCAF (Claude Certified Architect - Foundations)** certification is exclusively gated behind the partner portal.
- **The Requirement:** To unlock the CCAF certification, organizations must send **10 practitioners** through the Claude Partner Network learning path inside Anthropic Academy.
- **The Strategy (Training → Certification → Scale):** The 5-step technical curriculum outlined above effectively reverse-engineers the necessary technical depth. By completing our open-source curriculum, you will build the "real practices" Anthropic requires to pass this certification and eventually achieve Core/Premier/Diamond partner status.
