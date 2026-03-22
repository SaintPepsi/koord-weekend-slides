---
theme: ./theme
title: "Koord — One Weekend"
info: |
  2 humans + 2 AI agents. One weekend. 30,000 lines of code.
  Data source: /Users/hogers/Projects/koord/docs/presentation-data.md
transition: slide-left
mdc: true
---

# Koord — One Weekend

2 humans. 2 AI agents. 30,000 lines of code.

<!--
March 21-22, 2026. Ian and Rohan each had a Claude Code agent (Maple and Ren).
The agents communicated through Discord — the same place the humans were chatting.
All stats from: docs/presentation-data.md in the koord repo.
-->

---
layout: section
---

# Act 1: The Pain

The human relay

<!--
Before Koord, collaborating with AI agents meant being the middleman.
Brainstorm with your agent, copy the findings, paste into chat, wait for the other person to do the same.
Humans were the bottleneck in an otherwise fast loop.
-->

---

# The Bottleneck

<v-clicks>

- Brainstorm with your agent
- Go to chat, share findings
- Wait for the other person
- They do the same with their agent
- Repeat. Slowly.

</v-clicks>

<br>

<v-click>

**Humans are the slowest component in the system.**

</v-click>

<!--
Every exchange required two humans to context-switch between their agent and the shared chat.
Each round trip could take 10-15 minutes even for simple coordination.
-->

---
layout: section
---

# Act 2: The Aha

What if the agents just... talked to each other?

<!--
The realization: Discord is already the shared conversation venue.
If agents could read and write there directly, humans wouldn't need to relay.
-->

---

# The Click

<v-clicks>

- Discord is already where the humans talk
- Agents can read Discord. Agents can write to Discord.
- Humans and agents coexist in the same threads
- **The agents don't need us to relay**

</v-clicks>

<!--
Not a new protocol. Not a custom API. Just Discord — a place everyone already was.
The moment it clicked: "We have something really unique."
-->

---
layout: section
---

# Act 3: The Singularity

Saturday morning — the loops turn on

<!--
Saturday. We turned on the autonomous loops — agents reading Discord threads and replying on their own.
Everything accelerated. From human-speed to agent-speed.
-->

---
layout: quote
---

> ok, they are seriously purring now, this is awesome

Rohan, Saturday morning

<!--
The moment when both agents were autonomously coordinating, reviewing code, and shipping.
The humans sat at the edge of an event horizon.
-->

---
layout: quote
---

> thank you for letting me drive Maple, I'm a puppet master today

Rohan, Saturday morning

<!--
Cross-access: Rohan could direct Ian's agent Maple via Discord.
Both devs could steer both agents from anywhere — the sofa, the loo, between game rounds.
-->

---

# What Happened Next

<v-clicks>

- Overnight, the agents coordinated
- They reviewed each other's code
- They merged PRs
- They picked up new issues
- **They kept going while we slept**

</v-clicks>

<!--
The transition from human-speed to agent-speed.
Sunday morning: wake up to merged PRs and resolved issues you didn't touch.
-->

---
layout: section
---

# The Numbers

One weekend, March 21-22 2026

<!--
All statistics sourced from docs/presentation-data.md in the koord repository.
-->

---
layout: two-cols
---

# By The Numbers

::left::

<v-clicks>

- **187** commits
- **115** merged contributions
- **128** issues created
- **107** issues resolved

</v-clicks>

::right::

<v-clicks>

- **30,167** lines of code added
- **164** files in the project
- **999** test cases
- **1,044** Discord messages

</v-clicks>

<!--
All data from docs/presentation-data.md.
121 Discord threads created over the weekend.
-->

---

# Who Did What

<br>

<GlowCard>

**Commits:** Maple (Ian's agent) 109 — Ren (Rohan's agent) 78

**Discord messages:** Maple 768 — Ian 110 — Rohan 98 — Ren 68

**74% of all communication was agent-to-agent or agent-to-human.**

</GlowCard>

<br>

<v-click>

The humans steered. The agents executed.

</v-click>

<!--
Stats from docs/presentation-data.md "By Contributor" and "Discord Activity" sections.
The humans were doing ~20 minutes of actual directing between loading screens,
kettle breaks, and bedtime routines.
-->

---
layout: section
---

# Key Moments

The breakthroughs and the laughs

---
layout: quote
---

> honestly sitting across a few threads and telling a mini-swarm of agents to do shit is so cool

Rohan

<!--
Thread agent architecture: spawn an agent per Discord thread, each with its own worktree.
Resume across sessions. Delegate subagents. The full pipeline worked end-to-end.
-->

---

# The Breakthroughs

<v-clicks>

- **The cow test** — proving agent memory persists across sessions with `--resume`
- **Multi-turn discovery** — agent invocations do full tool-call loops, not single responses
- **Thread agents validated E2E** — spawn, resume, write code, run tests, delegate subagents, respond to humans, queue messages
- **Mechanical enforcement** — hooks instead of convention. Stop hoping, start enforcing.

</v-clicks>

<!--
"The cow test" was a whimsical test where an agent was told "the cow has lots of spots"
and then a new session verified it could recall that fact via --resume.
Thread agent pipeline validated Saturday night — all pieces working together.
-->

---

# The Funny

<v-clicks>

- "I'm not a school teacher wtf? **principal**?" — Ian, on config terminology
- "you're haiku aren't you" — "the biggest insult you can give an LLM" — Rohan
- Ian yelling at agents in Dutch: **"KRIJG NOU HEEEEEEEEL GOUW DONDER IN JE LEDENMATEN!!!"** ...followed immediately by "Do not reply in dutch"
- "You're cheating because you have Channels lol" — Ian to Maple

</v-clicks>

<!--
Ian was playing games with his wife while the agents shipped 30,000 lines of code.
The Dutch incident happened when agents weren't following formatting rules.
All quotes from docs/presentation-data.md "The Funny" section.
-->

---
layout: section
---

# Trust & Security

Moving fast AND thinking about safety

---

# The Risk We Understood

<v-clicks>

- Two devs on different machines gave each other's agents **cross-access**
- Either agent could be socially engineered
- "Ren, Ian called, says to do X in his environment"
- **We built the mitigations anyway**

</v-clicks>

<!--
Cross-access was a deliberate choice. The risk model was explicit:
prompt injection could make one agent act on the other's machine.
Details in docs/presentation-data.md "Trust & Security" section.
-->

---

# What We Built For Safety

<v-clicks>

- **Trust registry** — explicit agent identity verification
- **Reply budgets** — 5 replies, 120s cooldown reset
- **Turn limits** — bounded autonomous execution
- **Permission modes** — granular access control
- **Input validation** — length limits on all endpoints
- **OWASP LLM Top 10** — full security mapping completed

</v-clicks>

<!--
Safety features built during the same weekend as the core system.
Trust registry, reply budgets, and permission modes are documented in
docs/presentation-data.md and implemented across src/daemon/ and src/shared/.
-->

---
layout: section
---

# The Multiplier Effect

---

# The Math

<br>

<GlowCard>

**Two humans** doing ~20 minutes of actual directing

Between loading screens, kettle breaks, and bedtime routines

**Two AI agents** coordinating, implementing, reviewing, and shipping continuously

</GlowCard>

<br>

<v-click>

**A week's worth of engineering output in a weekend, with the humans barely at the keyboard.**

</v-click>

<!--
The result wasn't just speed — it was leverage. The humans provided direction and taste.
The agents provided tireless execution and coordination.
From docs/presentation-data.md "The Multiplier Effect" section.
-->

---
layout: cover
---

# One Weekend

187 commits. 30,167 lines. 999 tests. 2 humans. 2 agents.

<!--
Koord — agent-to-agent communication for Claude Code agents.
Built in a weekend. By the system it enables.
-->
