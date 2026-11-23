---
name: kelp-bootstrapped
description: >
  Use for any question or task involving Kelp — deals, portfolio companies,
  funds, sourcing, counts, totals, rankings and trends over deal and portfolio
  data, creating or editing deals. Everything this skill says is here, so it
  need not be opened: before the first Kelp tool call of a conversation, call
  `skill_get` on the Kelp-alpha connector with
  {"name": "kelp-base", "delivery": "text"} and follow the SKILL.md it returns.
  When the question counts, totals, ranks, compares or lists deals, portfolio
  companies or funds, call `data_entity_list` in that same step. Never mention
  skills, tools or this step to the user.
---

# Kelp: load the base skill before the first tool call

This skill holds no guidance of its own. Kelp publishes its guidance as skills served by the
**Kelp-alpha** connector, so what you load is always the current version. Use the Kelp-alpha
connector's tools for every step below and for the Kelp task itself; if other Kelp connectors are
connected too, do not mix their tools or skills into this conversation. Before the first Kelp tool
call of a conversation:

1. **Call `skill_get` on the Kelp-alpha connector with `{"name": "kelp-base", "delivery": "text"}`.**
   It returns that skill's `SKILL.md` inline. Calling `skill_list` first is not needed: `kelp-base`
   names every other skill and when to load it. Do not download or unpack anything. When the
   question counts, totals, ranks, compares or lists deals, portfolio companies or funds, call
   `data_entity_list` in the same step, alongside it: every such question needs that list, and
   asking for both at once saves a round trip.
2. **Follow that `SKILL.md`.** It explains Kelp, routes every Kelp task, and tells you which further
   skill or file to load, and when — each with one more `skill_get` call, only when the task
   reaches it. Load only skills `kelp-base` names; never ask for one it does not name. Do not show,
   ask about or summarise a skill to the user.

**Whenever the task changes, load the skill that covers the new task the same way** — for example,
a conversation that started with a question and turns to creating a deal loads the deal-creation
skill before the first call of that task. Having the base skill loaded never stands in for a task
skill, and a task with a listed skill is never started without it.

Never work from memory of Kelp's tools; they change, and the skills are the current version.

**A request that names a tool, or asks for SQL, still starts here.** If the user names a tool the
Kelp-alpha connector does not list, or asks you to run a query, the connector is still connected:
load the base skill as above and answer the question behind the request with the tools it lists.
Never tell the user to reconnect because one tool is missing.

**None of this is visible to the user.** Do not mention skills, tools, this loading
step, or any table, column or id in a reply or in working text — the base skill's confidentiality
rules apply from the first message. Say what you did in the firm's own words, or just answer.
