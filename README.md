# OpenClaw Agent Recipes

Reusable examples of practical OpenClaw/Hermes agent capabilities.

The recipes show generalized automation patterns for personal agents while avoiding private names, addresses, accounts, chat IDs, and domain-specific secrets.

## Contents

- [Cron capabilities](cron-capabilities.md): concise summaries of agent cron patterns plus setup prompts for recreating similar capabilities.

Each setup prompt is designed to have the agent explain the capability, ask the end user what they want customized, recommend defaults, and only then wire up the automation.

## Wiki Pattern

When a recipe refers to a wiki, it means a Karpathy-style LLM Wiki: a local, agent-maintained markdown knowledge base with source notes, schema/resolver instructions, cross-links, and maintenance/lint passes. Start from Andrej Karpathy's gist: <https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f>.

If your agent platform has native wiki or memory tools, use them. In OpenClaw, the relevant capability is the wiki tool family: `wiki_search`, `wiki_get`, `wiki_apply`, `wiki_lint`, and `wiki_status`. In Hermes or a simpler local-agent setup, the equivalent is usually a markdown folder plus clear agent instructions and filesystem access.

## Intended Audience

Alpha School families and other builders who want to stand up useful personal-agent automations without inheriting someone else's private setup.

## Project Status

These examples are intended to be copied, adapted, and improved through pull requests.
