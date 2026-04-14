# Amazon Ads MCP Workshop

Build AI agents that manage Amazon Ads campaigns using the Model Context Protocol (MCP). This repository contains two workshop tracks — choose the one that fits your setup.

## Workshop Tracks

### [AWS Workshop](merged-workshop/01-overview.md) (~4 hours)

Build and deploy MCP servers and LangGraph agents to Amazon Bedrock AgentCore. Includes a custom Knowledge Base MCP server, agent deployment, and integration with the Amazon Ads MCP Server.

**Requires:** AWS account, Amazon Bedrock access, Amazon Ads API credentials

| Module | Title |
|---|---|
| [01](merged-workshop/01-overview.md) | Workshop Overview and Prerequisites |
| [02](merged-workshop/02-concepts.md) | MCP and AgentCore Concepts |
| [03](merged-workshop/03-build-mcp-server.md) | Build an MCP Server |
| [04](merged-workshop/04-deploy-mcp-server.md) | Deploy MCP Server to AgentCore |
| [05](merged-workshop/05-build-langgraph-agent.md) | Build a LangGraph Agent |
| [06](merged-workshop/06-deploy-agent.md) | Deploy Agent to AgentCore |
| [07](merged-workshop/07-connect-ads-mcp-server.md) | Connect to Amazon Ads MCP Server |
| [08](merged-workshop/08-build-ads-agent.md) | Build an Ads Campaign Agent |
| [09](merged-workshop/09-testing-monitoring.md) | Testing and Monitoring |
| [10](merged-workshop/10-cleanup.md) | Cleanup and Next Steps |

### [Non-AWS Workshop](non-aws-workshop/01-overview-and-setup.md) (~1.5 hours)

Connect to the Amazon Ads MCP Server and build a local agent using Claude via the Anthropic API. No AWS account required.

**Requires:** Anthropic API key, Amazon Ads API credentials

| Module | Title |
|---|---|
| [01](non-aws-workshop/01-overview-and-setup.md) | Overview and Setup |
| [02](non-aws-workshop/02-connect-ads-mcp-server.md) | Connect to Amazon Ads MCP Server |
| [03](non-aws-workshop/03-build-ads-agent.md) | Build an Ads Agent |
| [04](non-aws-workshop/04-testing-and-cleanup.md) | Testing and Cleanup |

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                Amazon Bedrock AgentCore                  │
│                (AWS Workshop only)                        │
│  ┌──────────────────┐  ┌──────────────┐  ┌───────────┐  │
│  │  LangGraph Agent  │  │ Knowledge Base│  │Amazon Ads │  │
│  │  (A2A Protocol)   │  │  MCP Server   │  │MCP Server │  │
│  └────────┬─────────┘  └──────┬───────┘  └─────┬─────┘  │
│           │                   │                 │        │
└───────────┼───────────────────┼─────────────────┼────────┘
            │                   │                 │
            ▼                   ▼                 ▼
┌───────────────────────────────────────┐  ┌────────────┐
│            AWS Services               │  │  External   │
│  Amazon Bedrock (Claude)              │  │ Amazon Ads  │
│  Bedrock Knowledge Base               │  │    API      │
│  AWS Secrets Manager                  │  └────────────┘
│  CloudWatch Logs                      │
└───────────────────────────────────────┘
```

## Prerequisites

| | AWS Workshop | Non-AWS Workshop |
|---|---|---|
| Python 3.13+ | ✅ | ✅ |
| AWS Account | ✅ | ❌ |
| Anthropic API Key | ❌ | ✅ |
| Amazon Ads API Credentials | ✅ (Track B) | ✅ |

## Contributors

Created by [Chintan Sanghavi](https://www.linkedin.com/in/chintansanghavi/) and [Christelle Ngambula](https://www.linkedin.com/in/chrisngambula/), Senior Solutions Architects at Amazon Ads.

## Resources

- [Amazon Ads MCP Server Documentation](https://advertising.amazon.com/API/docs/en-us/mcp/get-started)
- [Amazon Ads API Documentation](https://advertising.amazon.com/API/docs/en-us)
- [Amazon Bedrock AgentCore](https://aws.amazon.com/bedrock/agentcore/)
- [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)
- [Model Context Protocol Specification](https://modelcontextprotocol.io/)
