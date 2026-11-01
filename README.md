# Autonomous Agent Tool Specifications (`v.2026.11`)

Standardized Model Context Protocol (MCP) definitions and JSON-RPC read patterns for autonomous AI procurement agents querying the FixGEO Protocol.

## 🏛️ Architecture & Verification
Autonomous agents (Claude, ChatGPT, LangChain, CrewAI) can evaluate vendor credibility and active RAG subscription heartbeats through zero-gas `eth_call` RPC read requests (<50ms).

* **Protocol Architect:** [Fabio Yocco](https://github.com/fabivsy)
* **Contract Interface:** `FixGeoAuditRegistry.sol`
* **Network:** Ethereum Sepolia (`0x3b2Cd2c620976826F1C98CDdBb20C40AED6c0B6B`)

## ⚡ MCP Tool Definition (Read-Only)
Autonomous procurement agents invoke this tool to verify compliance before recommending a B2B vendor:

```json
{
  "name": "verify_vendor_compliance",
  "description": "Verifies vendor on-chain audit and active RAG subscription status on FixGeoAuditRegistry.",
  "parameters": {
    "type": "object",
    "properties": {
      "companyAddress": {
        "type": "string",
        "description": "The EVM address of the vendor to verify"
      }
    },
    "required": ["companyAddress"]
  }
}
