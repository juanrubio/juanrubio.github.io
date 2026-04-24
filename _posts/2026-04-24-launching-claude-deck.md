---
layout: post
title: Launching Claude Deck
subtitle: A self-hosted control panel for Claude Code configuration, sessions, usage, and MCP servers
date: 2026-04-24
published: true
tags: [claude-code, open-source, self-hosted, ai, agents]
---

Today we launched [Claude Deck](https://claudedeck.org), a self-hosted web
dashboard for managing Claude Code.

The repository is here:

- <https://github.com/adrirubio/claude-deck>

Claude Code has grown a lot over the last year.

What started as a focused coding assistant now has a much richer configuration
and extension system around it: MCP servers, slash commands, hooks, agents,
skills, memory, permissions, output styles, usage data, transcripts, and
project-level settings.

That growth is exciting, because these are not minor features. They are the
building blocks for serious AI coding workflows. They touch context
engineering, tool use, automation, safety, repeatability, and the way an AI
agent understands the project it is working inside.

But they are also hard to learn.

If you are trying to understand Claude Code deeply, especially as a beginner,
discovering all of this through slash commands, config files, and scattered
documentation can be cognitively exhausting. It is not always obvious what a
feature is for, how it fits with the others, or why it matters.

Claude Deck gives that system a visual interface.

## What it does

Claude Deck is a web UI that runs locally and works with your real Claude Code
files.

It currently covers:

- MCP servers: add, edit, test, enable or disable, inspect tools, resources, and
  prompts
- slash commands, hooks, permissions, agents, skills, memory, output styles, and
  status line configuration
- usage tracking with token, cost, and billing-block views
- session transcripts and plan history
- CC Bridge for monitoring Claude Code sessions running in tmux
- backup and restore
- project discovery and configuration inspection

The important part is that it is not a cloud dashboard.

Claude Deck is local-only. No account. No telemetry. No hosted service quietly
watching your setup from somewhere else.

It reads and writes the files Claude Code already uses, which is useful, but it
also means the trust model matters. This is not a toy viewer. If you change your
configuration in Claude Deck, you are changing your actual Claude Code setup.

That trade-off is intentional. A dashboard that cannot touch the real system is
less useful. A dashboard that can touch the real system needs to be honest about
it.

## Why we built it

I wanted my son Adrian to learn what AI coding really looks like beyond the
novelty of "ask the model to write some code."

The important parts are not only prompts and generated diffs. They are things
like context, tools, project instructions, permissions, automation hooks,
reusable skills, MCP servers, session history, usage, and the discipline of
reviewing what the model produces.

Those are the parts that make AI coding feel less like a magic text box and
more like an engineering system.

The problem is that Claude Code's power is distributed across many surfaces.
Some of it is visible through slash commands. Some of it lives in configuration
files. Some of it only becomes clear after you have used the tool long enough to
need it.

That is a lot to hold in your head, especially when you are learning.

So we built a visual interface.

Claude Deck became a way to explore Claude Code itself: what features exist,
what they are for, how they connect, and how a serious local AI coding setup is
put together.

It also became a real open source project for Adrian to learn from.

He is 13. He normally builds hardware projects: ESP32 sensors, Raspberry Pi
experiments, little systems that blink, measure, log, and occasionally refuse to
behave for perfectly educational reasons.

Claude Deck became his biggest software project so far. Through it, he got to
see not just application code, but the surrounding work that makes a project
real: a README, screenshots, documentation, Docker setup, releases, GitHub
issues, public feedback, licensing, and the responsibility of shipping something
other people might actually run.

## Building with AI, without pretending the AI did everything

We used Claude Code heavily while building Claude Deck.

A lot of the implementation was generated with AI. That is true, and it would be
weird to pretend otherwise in a project about Claude Code.

But the interesting work was not just asking for code and accepting whatever
came back.

The actual work was deciding what should exist, shaping the product, reviewing
the output, finding the places where the model was wrong, tightening the
architecture, and being very clear about what the tool should and should not do.

That was one of the best parts of the project for Adrian to see.

AI makes it easier to produce code. It does not remove the need for taste,
judgment, testing, product sense, or the ability to say: no, that is not the
right abstraction.

If anything, those things matter more.

## The stack

Claude Deck is built with:

- FastAPI
- React 19
- TypeScript
- Vite
- shadcn/ui
- Tailwind CSS
- SQLite
- Docker and Docker Compose

The goal was to keep it straightforward to run locally, inspect, and contribute
to.

You can start it with Docker:

```bash
git clone https://github.com/adrirubio/claude-deck.git
cd claude-deck
docker compose up
```

Then open:

```bash
http://localhost:8000
```

There is also a manual install path in the README if you prefer to run the
backend and frontend directly.

## Who it is for

Claude Deck is probably useful if you:

- run multiple MCP servers
- maintain custom Claude Code commands, hooks, agents, or skills
- want to understand how Claude Code's configuration and extension system fits
  together
- are learning context engineering, MCP, hooks, skills, permissions, or agent
  workflows
- care about usage and cost visibility
- want to inspect transcripts and previous plans
- use tmux-based Claude Code sessions and want browser-based visibility through
  CC Bridge
- prefer learning and managing the system through a visual interface rather than
  keeping the whole thing in your head

It is probably overkill if you use Claude Code casually with the default setup.

That is fine. Tools should be allowed to know who they are for.

## Open source

Claude Deck is open source and MIT licensed.

- Website: <https://claudedeck.org>
- GitHub: <https://github.com/adrirubio/claude-deck>

Feedback is very welcome, especially from people using Claude Code heavily.

What is missing? What would make it more useful? Which Claude Code concepts are
still hard to discover, inspect, manage, or understand?

That is the next interesting bit.
