# DecisionLedger MCP Server

An MCP (Model Context Protocol) server that connects Claude to the [DecisionLedger](https://decisionworksmodels.com) decision-modeling platform. Run quantitative models, track decisions through governed lifecycles, manage approvals, and record outcomes — all from natural language.

## Setup

Add to your Claude Desktop config (`claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "decisionledger": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://api.decisionworksmodels.com/mcp"
      ]
    }
  }
}
```

Or install locally:

```bash
npm install -g decisionledger-mcp
```

## Available Tools

| Tool | Description |
|------|-------------|
| `list_plugins` | Discover available decision models (100+ models across risk, financial, HR, and more) |
| `get_plugin_schema` | Get the input schema for a decision model |
| `run_plugin` | Execute a decision model with given inputs |
| `list_runs` | View past decision model executions |
| `get_run` | Get full results of a past execution |
| `create_decision` | Create a new decision to track through its lifecycle |
| `search_decisions` | Search and filter decisions by status, priority, category, or SLA |
| `get_decision` | Get full details of a decision including status history |
| `advance_decision` | Advance a decision through lifecycle stages or link entities |
| `manage_approval` | Submit, approve, reject, or escalate approval requests |
| `list_approval_workflows` | List available approval workflows |
| `record_outcome` | Record the actual outcome of a decision (closes the feedback loop) |
| `get_outcome_dashboard` | Executive dashboard: effectiveness scores, prediction accuracy, insights |
| `find_similar_decisions` | Find similar past decisions using embedding similarity |
| `get_decision_graph` | Explore the decision relationship graph |
| `get_graph_intelligence` | Detect contradictions and duplicate decisions |
| `add_decision_document` | Upload documents (PDF, DOCX, XLSX, etc.) to a decision |

## Decision Methods

DecisionLedger includes 100+ pre-built quantitative models spanning:

- **Multi-Criteria Decision Analysis** (Weighted Sum, TOPSIS, AHP)
- **Probabilistic** (Bayesian Expected Utility)
- **Financial** (Cost-Benefit NPV, ROI)
- **Risk** (Risk Matrix, Stress Testing)
- **Optimization** (Linear Programming, Portfolio)
- **Simulation** (Monte Carlo, Scenario Modeling)
- **Machine Learning** (Clustering, Anomaly Detection)
- And many more domain-specific models for HR, benefits, sales, data governance, and compliance

## Decision Lifecycle

Decisions flow through governed stages:

```
draft -> analysis -> deliberation -> approval -> execution -> monitoring -> closed
```

Each transition is audited. Approvals can be routed through configurable workflows with SLA enforcement.

## Authentication

The remote MCP server uses OAuth. On first connection, you'll be prompted to authorize through your browser.

## License

MIT
