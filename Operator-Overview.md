# Operator — Brand & Product Overview

For partners and agencies · October 2026 · Draft v0.1

---

## Identity

| | |
|---|---|
| Company | FiftyTwo Software, Inc. (52 Software™), a subsidiary of 52! Holdings Corp. |
| Product | Operator (legal and technical name: Operator OS™) |
| One line | Intelligence that stays home. |
| Descriptor | Operator is your own AI assistant. It runs on a computer you own, remembers you, and asks before it acts. |
| Web | operatorharness.org |
| Contact | contact@operatorharness.org |
| Code | github.com/operatorharness/operator |
| Social | @operatorharness |
| Community | Discord, GitHub issues |
| Launch | Week of October 26, 2026 (version 0.3.0) |

Write "Operator" in everyday copy. Use "Operator OS™" on first mention in legal, technical, and partner documents, then "Operator". Never shorten Operator Workspace to "Operator": that is a separate, internal 52 Online system ([Holdings §6.2](52!-Holdings-Overview.md#62-52-holdings-and-52-online-accounts)).

## What Operator is

Most AI lives on someone else's servers. Operator lives on yours.

You install it on a computer you own, connect it to the AI model you prefer, and talk to it in the chat app you already use. It answers, searches the web, manages files, keeps reminders and schedules, and carries out multi-step tasks. Your conversations, memory, files, and passwords stay on your machine.

Operator is open source (MIT) and free. You pay only for the model, if you choose a hosted one. A model that runs on your own machine costs nothing.

## How it works

1. **Download** the launcher from operatorharness.org. One file, nothing else to install.
2. **Open it.** The dashboard opens in your browser. Create a password.
3. **Name your assistant** and connect a model.
4. **Say hello.** The chat opens and your assistant greets you by name.

Optional: connect a chat app (Telegram takes about a minute), so Operator is a contact on your phone like anyone else.

## Product pillars

| Pillar | What it covers |
|---|---|
| **Yours** | Runs on your own computer, from a laptop to a small single-board computer or an old Android phone. Memory, files, and credentials stay there. |
| **Asks first** | Sentinel, Operator's security layer, pauses anything risky until you approve it from chat, the dashboard, or the Apple app. Passwords sit in an encrypted vault the model never reads. |
| **Remembers** | Carries what it learns across conversations. You can see and change what it knows about you at any time. |
| **Everywhere you chat** | 18+ chat apps, plus a built-in chat. Searchable conversations, attachments, and native apps for iPhone, iPad, Mac, and Apple Watch. |
| **Your choice of model** | 30+ providers, or a free local model. Optional routing sends simple questions to a cheaper model. |
| **Grows with you** | Learns skills from tasks it finishes, installed only after you approve. Extends with skills and the Model Context Protocol. |
| **Small by design** | One file, no database or runtime to set up. The core build is under 15 MB. |

## Names and addresses

| Address | What it is |
|---|---|
| operatorharness.org | Home, download, and documentation. The only official site. |
| operatorharness.org/download | Android app |
| github.com/operatorharness/operator | Source code (public, MIT) |
| operatorharness.com · .io · .co · operatorworkspace.com | Redirect to operatorharness.org ([Reserved Domains](52-Reserved-Domains.md#operator)) |

Handles and namespaces: GitHub organization `@operatorharness`, social `@operatorharness`, npm scope `@operatorharness` (next to claim, [Software §6.4](52-Software-Overview.md#64-npm-and-images)), images `ghcr.io/operatorharness/…`. Any other domain using the Operator name is not ours.

## Where Operator sits

- **Product of 52 Software.** 52 Software makes Operator and provides no adoption or implementation services for it. Those are 52 Studio's ([Holdings §3](52!-Holdings-Overview.md#3-entities)).
- **Independent of Station.** Operator is one of the agent runtimes Station runs on. It keeps its own address, and nothing in Operator depends on Station. Station ships inside it as an optional skill ([Station overview](Station-Overview.md)).
- **Hosted by Cardsite.** Cardsite® is the reference Static Hosting Partner for Operator, and credited as Flagship Sponsor on every applicable 52 surface ([52 x Cardsite §3](52xCardsite-Overview.md#3-52--cardsite)).

## Status and safety

State these plainly, in this order, wherever Operator is described to partners.

- **Operator has no cryptocurrency or token.** Anything traded under its name is a scam.
- **Not yet externally reviewed.** Operator has had no external security review. Until 1.0, it is for personal projects and experiments, not for anything critical.
- **Built with AI, reviewed by people.** Most of the code was written by an AI agent, then reviewed, tested, and refined by people. We say so openly and hold it to the same bar as hand-written code.
- **Versions.** Current version 0.3.0. What is true now is kept in the repository's `.station/STATUS.md`.

## Proposed copy

> **Operator is your own AI assistant.** Intelligence that stays home.
>
> **Your machine. Your memory.** Operator runs on a computer you own, so what it learns about you stays with you.
>
> **It asks first.** Before it sends, deletes, buys, or runs anything that matters, Operator checks with you. Say yes from chat, your phone, or the dashboard.
>
> **It remembers you.** Tell it how you like things once. It carries that into every conversation.
>
> **Talk to it where you already talk.** Telegram, WhatsApp, Discord, Slack, and more, or the built-in chat. Apps for iPhone, iPad, Mac, and Apple Watch.
>
> **Pick your own model.** Use a major provider, or a free one that runs on your own machine.
>
> **Small enough to run anywhere.** Download one file and you're chatting in minutes. Free and open source.

## Claims guidance

| Say | Don't say | Why |
|---|---|---|
| Runs on your machine; your memory, files, and passwords stay there | "Fully private" or "nothing leaves your device" | With a hosted model, your messages go to that provider. Only a local model keeps them home. |
| Asks before anything that matters | "Asks before everything" | Reads, searches, and safe local work run without asking. |
| Free and open source | "Secure" or "audited" | No external security review before 1.0. |
| An AI assistant | "Superintelligence" | Overpromises, and invites skepticism. |
| Your own assistant | Any token, coin, or "powered by" crypto language | Operator has none. |

## Who it's for

- Someone who wants an assistant that knows them and doesn't send their life to a stranger's server.
- A family or small team that wants one assistant in the group chat they already use.
- A tinkerer who runs it on a spare Raspberry Pi or an old phone.
- A developer or agency that builds on Operator with skills and MCP tools. Implementation work is 52 Studio's.

---

Operator OS™ is a trademark of FiftyTwo Software, Inc. Details are subject to change before general availability.
