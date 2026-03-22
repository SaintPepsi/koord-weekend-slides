---
theme: ./theme
title: "Koord — One Weekend"
info: |
  2 humans + 2 AI agents. One weekend. 30,000 lines shipped.
drawings:
  persist: false
transition: slide-left
---

# Koord

2 humans + 2 AI agents. One weekend.

30,000 lines shipped.

---
layout: section
---

# Act 1: The Pain

---

# The Human Relay Problem

We always have great ideas. Our brains are aligned.

But the workflow is painfully slow:

<GlowCard>

**Brainstorm** → Go to agent → **Brainstorm** → Come back → **Share** → Wait → **Repeat**

</GlowCard>

<br>

The gap between ideas and execution was the real cost.

---

# What It Looked Like

<TerminalBlock title="discord — #general">

<v-click>

Ian: "Hey I had an idea about X"

</v-click>

<v-click>

Rohan: "Cool, let me brainstorm with my agent"
... 20 minutes later ...

</v-click>

<v-click>

Rohan: "Ok here's what my agent says"

</v-click>

<v-click>

Ian: "Nice, let me check with mine"
... 20 minutes later ...

</v-click>

<v-click>

Ian: "My agent agrees but suggests Y"

</v-click>

</TerminalBlock>

<v-click>

<p class="gp-gradient-text" style="font-size: 1.4rem; font-weight: 700; text-align: center; margin-top: 1.5rem;">
One decision. Forty minutes. Two human relay hops.
</p>

</v-click>

---
layout: section
---

# Act 2: The Aha

---
layout: dramatic
---

# What If Our Agents Could Talk?

Not through us. **To each other.**

Through Discord — a shared venue where humans and agents coexist.

Agents converse in threads. Humans watch, steer, intervene.

**No more relay.**

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
layout: dramatic
---

# The Moment Everything Accelerated

We turned on the loops.

Agents reading Discord threads and replying **autonomously**.

From human → agent → reply

To **agent → read → reply → repeat**

We sat at the edge of an event horizon.

---

# The Numbers

<StatGrid :stats="[
  { value: '187', label: 'Commits' },
  { value: '115', label: 'Merged contributions' },
  { value: '30,167', label: 'Lines of code' },
  { value: '999', label: 'Test cases' },
  { value: '1,044', label: 'Discord messages' },
  { value: '121', label: 'Threads' },
]" />

<p class="gp-gradient-text" style="font-size: 1.6rem; font-weight: 700; text-align: center; margin-top: 2rem;">
One weekend.
</p>

---

# Who Did the Work?

<ContribTable :rows="[
  { name: 'Maple', type: 'ai', messages: '768', commits: '109' },
  { name: 'Ren', type: 'ai', messages: '68', commits: '78' },
  { name: 'Ian', type: 'human', messages: '110', commits: '—' },
  { name: 'Rohan', type: 'human', messages: '98', commits: '—' },
]" />

<br>

<GlowCard>

**74% of communication was by AI agents.**

The humans steered. The agents executed.

</GlowCard>

---

# The Real Story

<br>

Ian was playing games with his wife.

Messaging between loading screens. From the loo. While waiting for the kettle.

<br>

<p class="gp-gradient-text" style="font-size: 2.2rem; font-weight: 700; text-align: center;">
30,000 lines shipped.
</p>

---
layout: quote
---

> "honestly sitting across a few threads and telling a mini-swarm of agents to do shit is so cool"

— Rohan

---

# The Funny Moments

<br>

<v-click>

"I'm not a school teacher wtf? **principal**?"

</v-click>

<v-click>

"you're haiku aren't you" — "biggest insult you can give an LLM"

</v-click>

<v-click>

Ian yelling at agents in Dutch then: **"Do not reply in dutch"**

</v-click>

---

# Trust & Security

<br>

We gave each other's agents access to our machines.

We understood the risk.

<br>

<GlowCard>

We built mitigations: **trust registry**, **reply budgets**, **turn limits**, **permission modes**.

We moved fast AND thought about safety.

</GlowCard>

---

# The Discovery

<br>

<GlowCard>

`claude -p` is not single-response.

It's **single user-turn with unlimited tool calls.**

</GlowCard>

<br>

Read files, write code, run tests, fix failures, iterate — one invocation.

**This changed everything.**

---
layout: dramatic
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
