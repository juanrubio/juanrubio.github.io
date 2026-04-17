---
layout: post
title: Open-sourcing mercadona-cli
subtitle: A low-key CLI for carts, orders, and checkout flows on Mercadona's unofficial private API
date: 2026-04-17
published: true
tags: [cli, open-source, automation, jekyll]
---

I have not written here in a while, so this feels like a good small post to get
things moving again.

Today I open-sourced [mercadona-cli](https://github.com/juanrubio/mercadona-cli),
a command-line tool for working with Mercadona's private web API. It supports
multiple profiles, product search, cart management, order inspection, draft
editing for existing orders, delivery slots, checkout helpers, and `--json`
output for automation.

This is an unofficial tool built on top of a private API, so the caveats matter
just as much as the features.

## Why build it

This started from a very practical place. I wanted my OpenClaw instances to be
able to help with shopping tasks, and Mercadona happens to be the supermarket I
use most. Repeating the same grocery workflows through the website gets old
quickly, especially when the interesting part is not clicking buttons but
reasoning about what to buy, when to schedule it, and how to automate the
boring bits safely.

That pushed the CLI toward machine-readable output, repeatable commands,
multi-profile support, and workflows that could be automated without treating
the browser UI as the primary interface.

A CLI made those workflows composable.

Instead of treating grocery ordering as a one-off browser task, it became
possible to:

- inspect carts and orders quickly
- script repeatable flows
- work with multiple profiles
- integrate the tool into other automations
- expose machine-readable output for agents and cron jobs

In other words, it turned a fiddly bit of life admin into something closer to a
real tool.

## What it can do

At the moment, `mercadona-cli` supports:

- multiple account profiles
- browser-token based authentication
- product search
- cart add, remove, clear, and repeat-style workflows
- order history and order inspection
- draft editing for confirmed orders
- delivery address and slot inspection
- checkout creation, slot assignment, confirmation, and status checks
- `--json` output for automation and scripting

It is built as a TypeScript CLI and published as an npm package.

## The unavoidable caveat

This tool depends on Mercadona's private web API.

That means a few things are true by definition:

- it is unofficial
- it is not endorsed by Mercadona
- it may break at any time
- browser-derived tokens are sensitive and need to be treated carefully
- no one should mistake convenience for stability

I think tools like this are still worth building and sharing, as long as the
trade-offs are stated plainly.

## What I like about it

I like small tools that are honest about what they are.

`mercadona-cli` is a small, practical tool built around a real recurring need.
It makes a repetitive workflow easier to inspect, automate, and reason about.

There is something satisfying about turning an awkward UI-bound task into a
clear interface with predictable commands and scriptable output.

## If you want to try it

The repository is here:

- <https://github.com/juanrubio/mercadona-cli>

Install from npm:

```bash
npm install -g mercadona-cli
```

Then:

```bash
mercadona --help
```

If you use it, keep the unofficial/private API caveat in mind.

Low-key tools are still tools. Sometimes that is enough.
