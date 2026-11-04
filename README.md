### CLI Harness

- Copilot CLI
- Kiro CLI
- Claude
- Codex
- Antigravity
- Amp

#### OSS Harnesses

- OpenCode
- Pi

#### OSS Orchestrators

Orchestrate one or more agent harness together.

- T3 Codes https://t3.codes
- Orca https://www.onorca.dev

### SDKs

AgentSDK to build Agent applications and own harnesses

1. Claude Agent SDK - https://code.claude.com/docs/en/agent-sdk/overview
2. Strands SDK - https://strandsagents.com/docs/user-guide/sdk/
3. AgentCore for AWS Agents - https://aws.amazon.com/bedrock/agentcore/

#### Codemode

https://developers.cloudflare.com/agents/tools/codemode/

https://platform.claude.com/docs/en/agents-and-tools/tool-use/programmatic-tool-calling

### Spec Driven Development for Projects

Always follow this pattern to start with well defined Project Requirement Design (PRD) and ADR's with `/plan` mode.

- Plan
- Design
- Develop
- Test
- Feedback loop

### Skills

Always use Official Skills from software vendors.

https://www.skills.sh/official

```
npx skills add aws/agent-toolkit-for-aws/skills
npx skills add redis/agent-skills
npx skills add https://github.com/cloudflare/security-audit-skill \
 --skill security-audit
npx skills add https://github.com/cloudflare/skills
npx skills add docker/skills --list
npx skills add aws/agent-toolkit-for-aws/skills
npx skills add docker/skills
npx skills add Arize-ai/arize-skills
npx skills add grafana/skills
npx skills add clickhouse/agent-skills
npx skills add https://github.com/openai/skills --skill playwright
npx skills add hashicorp/agent-skills
npx skills add https://github.com/hashicorp/agent-skills --skill aws-ami-builder
npx skills add https://github.com/hashicorp/agent-skills --skill terraform-style-guide
npx skills add https://github.com/hashicorp/tfctl-cli --skill tfctl
npx skills add https://github.com/microsoft/playwright-cli --skill playwright-cli
npx skills add langfuse/skills
npx skills add anthropics/skills
```

#### symlink

Symlink for `.claude/skills` folder from `.agents/skills`

```
mkdir -p .claude
ln -s ../.agents/skills .claude/skills
```

### LSP Servers

This is a must-have settings to enable LSP servers in harnesses, token efficient.

https://code.claude.com/docs/en/plugins/code-intelligence

### Hooks

- Primarily used for automation with `PreToolUse` and `PostToolUse` hooks.

https://code.claude.com/docs/en/hooks

### MCP

All of the MCPs are to be distributed via Cloudflare MCP Portal with OAuth permissions.

https://developers.cloudflare.com/cloudflare-one/access-controls/ai-controls/mcp-portals/

### Plugins

- Plugin is a combination of scripts, mcp servers, agents, hooks, skills from a vendor distributed via a marketplace.

https://code.claude.com/docs/en/plugins/overview

https://agent-plugins.org

### Harness Memory

https://kiro.dev/blog/memory-in-ide-cli/

https://docs.github.com/en/copilot/how-tos/use-copilot-agents/copilot-memory/create-memories#importing-memories-with-copilot-cli

#### Long Term Memory

- For now, sqllite for storing memory and astro docs for projects. Use hooks for memory.

### Gateway

Caching, firewall rules, and costs view via AI Gateway.

https://www.cloudflare.com/products/ai-gateway/

### WebMCP

https://github.com/webmachinelearning/webmcp

### Update Harness versions

```
copilot update && kiro-cli update && claude update && amp update
```

### Documentation

kiro-cli https://kiro.dev/docs/cli/

claude https://code.claude.com/docs/en/platforms

copilot https://docs.github.com/en/copilot/get-started/cli-quickstart

### Best Practices

- Well structured `User Prompt` to the Harness
- PRD's in Plan Mode and grill for questions back to me to understand the system and architecture
- Constantly update `AGENTS.md` in the repository
- Frequently look at `/context` to look at the usage of prompts, tools, skills
- Read the skills from official vendors and understand how it is structured, usage, best practices
- Enable OTel observability to send spans and traces to Arize
- Read through the docs of StrandsSDK and Agent loop is absolutely necessary
- Document the learnings across sessions in memory with hooks for workflows
- ALWAYS write Evals/test cases and edge scenarios written for end to end testing
