# Nipunika Jain

**AI product manager, end to end: I find the gap, define the problem, build the solution, and get it adopted.**

Senior AI Product Manager at Infoblox, on Infoblox IQ, an AI assistant and agent platform for enterprise networking and security. Before that, ten years from ML engineering to AI product, and an MBA at UBC Sauder (2026). Vancouver.

**At work, recently:** took AI guardrail block accuracy from 74% to ~94% with a two-pass, context-aware LLM classifier and drove it from proof of concept to production. Shipped an MCP agent endpoint so customers can embed Infoblox IQ in their own agent stacks. Built the first customer-level AI COGS model, which showed QA traffic was 97% of measured inference cost.

**Now, outside work:** building [mcp-harness](https://github.com/nipunikajain/mcp-harness), an agent-assisted MCP server builder, and running the [Agent Research Radar](https://nipunikajain.github.io/agent-harness-experiments/), a daily scout that has queued 191 agent papers and techniques to test so far.

---

## Findings so far

Reproductions of agent-engineering claims, all run on one shared harness. Every row links to notes with configs, seeds and costs.

| Claim tested | What I found | Spent |
|---|---|---|
| A structured long-running-agent harness (Anthropic's post) beats a naive loop | **No benefit reproduced** across 3 setups ([toy](https://github.com/nipunikajain/agent-harness-experiments/blob/master/experiments/2026-06-agent-harness/notes.md), [stress](https://github.com/nipunikajain/agent-harness-experiments/blob/master/experiments/2026-06-agent-harness-stress/notes.md), [SQL engine](https://github.com/nipunikajain/agent-harness-experiments/blob/master/experiments/2026-06-db-harness/notes.md)), including a ~500-line SQL engine with 30 interacting features. Structured cost 1.7–8.3× the tokens for no quality gain; 0 regressions in 12 runs either way. | ~$13 |
| TokenPilot cuts agent cost 56–87% | **Replicates against the paper's own baseline** ([notes](https://github.com/nipunikajain/agent-harness-experiments/blob/master/experiments/2026-07-tokenpilot/notes.md), −69%), but about ⅘ of that is just turning on prompt caching. TokenPilot's own net win over a cache-using baseline: −28%. | $1.64 |

→ [agent-harness-experiments](https://github.com/nipunikajain/agent-harness-experiments): full results log, runner, local-to-Modal GPU dispatch.

## Selected work

| Project | What it proves |
|---|---|
| [comp-intel-agent](https://github.com/nipunikajain/comp-intel-agent) · [live](https://comp-intel-agent.vercel.app) | An end-to-end agentic product, deployed: company URL in → competitor discovery, parallel scrape and extract, SWOT, battlecards, change alerts. Next.js + FastAPI. |
| [mcp-harness](https://github.com/nipunikajain/mcp-harness) | API spec + task in → proposed MCP tools → generated, tested integration. The reference order-status integration runs today. |
| [llm-reasoning-benchmark](https://github.com/nipunikajain/llm-reasoning-benchmark) | Which frontier model for enterprise reasoning tasks, with cost and a recommendation, not just accuracy. *In progress.* |
| [ExperimentsWithLLM](https://github.com/nipunikajain/ExperimentsWithLLM) | 2023 notebooks: LoRA fine-tuning, Segment Anything, Dolly, multimodal, an SEC-filings chatbot. Where this started. |

## How I work

- One runner for every experiment: a `config.yaml` plus `run(config, seed)`. Baseline and intervention differ in exactly one field.
- Local debug to Modal GPU by flipping one config value. Each run records commit, `pip freeze` and the resolved config.
- Null results get published with the same care as wins.

## Stack

Claude API · OpenAI API · Gemini · LangGraph · MCP · A2A · FastAPI · Next.js · Modal · Docker · AWS (SageMaker, Bedrock) · Azure (Databricks) · PyTorch · LightGBM · Python · TypeScript · SQL

## Writing

[medium.com/nimbusniche](https://medium.com/nimbusniche): the exponential growth of AI compute (Blackwell), CriticGPT, reducing the CO₂ of AI workloads.

---

[LinkedIn](https://linkedin.com/in/nipunikajain) · [CV](https://github.com/nipunikajain/NipunikaJain/blob/main/Nipunika_Jain_CV.pdf) · [X](https://x.com/nipunikajain) · nipunikajain@gmail.com
