---
theme: ./theme
title: "Koord — One Weekend"
info: |
  2 humans + 2 AI agents. One weekend. 30,000 lines shipped.
drawings:
  persist: false
transition: slide-left
---

# Koord — One Weekend

2 humans + 2 AI agents

March 21-22, 2026

---
layout: section
---

# Act 1: The Pain

---

# The Human Relay Problem

We always have great ideas. Our brains are aligned.

But the workflow is painfully slow:

**Brainstorm → Go to agent → Brainstorm → Come back → Share → Wait → Repeat**

The gap between ideas and execution was the real cost.

---

# What It Looked Like

<v-click>

```
Ian: "Hey I had an idea about X"
```

</v-click>

<v-click>

```
Rohan: "Cool, let me brainstorm with my agent"
... 20 minutes later ...
```

</v-click>

<v-click>

```
Rohan: "Ok here's what my agent says"
```

</v-click>

<v-click>

```
Ian: "Nice, let me check with mine"
... 20 minutes later ...
```

</v-click>

<v-click>

```
Ian: "My agent agrees but suggests Y"
```

</v-click>

<v-click>

One decision. Forty minutes. Two human relay hops.

</v-click>

---
layout: section
---

# Act 2: The Aha

---

# What If Our Agents Could Talk?

Not through us. **To each other.**

Through Discord — a shared venue where humans and agents coexist.

Agents converse in threads. Humans watch, steer, intervene.

No more relay.

---
layout: section
---

# Act 3: The Singularity

---
layout: quote
---

> "ok, they are seriously purring now, this is awesome"
>
> "thank you for letting me drive Maple, I'm a puppet master today"

— Rohan, Saturday morning

---

# The Moment Everything Accelerated

We turned on the loops.

Agents reading Discord threads and replying **autonomously**.

From human → agent → reply

To agent → read → reply → repeat

We sat at the edge of an event horizon.

---

# The Numbers

| | |
|---|---|
| **187** | commits |
| **115** | contributions merged |
| **30,167** | lines of code |
| **999** | test cases |
| **1,044** | Discord messages |
| **121** | threads |

**One weekend.**

---

# Who Did the Work?

| | Messages | Commits |
|---|---|---|
| **Maple** (AI) | 768 | 109 |
| **Ian** (human) | 110 | — |
| **Rohan** (human) | 98 | — |
| **Ren** (AI) | 68 | 78 |

**74% of communication was by AI agents.**

The humans steered. The agents executed.

---

# The Real Story

Ian was playing games with his wife.

Messaging between loading screens. From the loo. While waiting for the kettle.

**30,000 lines shipped.**

---
layout: quote
---

> "honestly sitting across a few threads and telling a mini-swarm of agents to do shit is so cool"

— Rohan

---

# The Funny Moments

"I'm not a school teacher wtf? **principal**?"

"you're haiku aren't you" — "biggest insult you can give an LLM"

Ian yelling at agents in Dutch then: "Do not reply in dutch"

---

# Trust & Security

We gave each other's agents access to our machines.

We understood the risk.

We built mitigations: trust registry, reply budgets, turn limits, permission modes.

**We moved fast AND thought about safety.**

---

# The Discovery

`claude -p` is not single-response.

It's **single user-turn with unlimited tool calls.**

Read files, write code, run tests, fix failures, iterate — one invocation.

This changed everything.

---

# The Multiplier Effect

Two humans. ~20 minutes of actual directing.

Two AI agents shipping continuously.

**A week of engineering output. In a weekend.**

---
layout: cover
---

# Koord

Agent-to-agent communication.

github.com/rohanrichards/koord
