# Station™ — Brand & Product Overview

For partners and agencies · October 2026 · Draft v0.1

---

## Identity

| | |
|---|---|
| Company | FiftyTwo Software, Inc. (52 Software™), a subsidiary of 52! Holdings Corp. |
| Product | Station™ |
| d/b/a | Station Center™ (legal name only; never a product name) |
| One line | *Proposed:* Everything describes itself. |
| Descriptor | Station is an open standard that gives every project, machine, and team one shape a person reads in a minute and an agent operates without asking. |
| Web | station.center |
| Contact | contact@station.center |
| Social | @stationprotocol · @stationmodules · @stationcenter |
| GitHub | `@stationprotocol` · `@stationmodules` · `@stationcenter` |

Always write "Station" as one word with a capital S. "Station" alone means the whole system. Its parts are always two words: Station Protocol, Station Modules, Station Cloud. Use the ™ on first mention in any document, then plain "Station". Every Station surface carries the footer `© FiftyTwo Software, Inc.`

## What Station is

Projects, machines, and teams each describe themselves differently, so people have to dig and agents have to guess. Station fixes that with one shared way to lay things out and say what they are.

A Station project says who owns it, what it is for, and what is true right now, in the same place and the same words as every other Station project. A person gets it in a minute. An agent can operate it without asking.

Station is **harness-agnostic**: it runs on the agent tools you already use (OpenClaw, Hermes Agent, Meta Muse, Operator OS, and others) and ships no agent of its own. It is open by default, with an optional hosted service.

## The three parts

| Part | Class | What it is | Address | Repositories |
|---|---|---|---|---|
| **Station Protocol** | Standard | The specification: how a project, machine, or team describes itself. Versioned and published. Shown as STATION 1.0. | station.center/protocol | Public |
| **Station Modules** | Open source | A collection of reusable modules built on the protocol, organized into Station Libraries. | station.center/modules | Public |
| **Station Cloud** | Commercial | The hosted service: hosting, storage, and inference. | cloud.station.center | Private |

## Station Libraries

Libraries are part of Station Modules, not separate products. Each lists what a repository ships, never the repository itself, and takes public, open-licensed work only. Entries point at a tagged release, not a branch.

| Library | Lists | Address |
|---|---|---|
| **Folio** | Reusable web things: templates, starters, components | station.center/modules/folio |
| **Windmill** | Creative assets | station.center/modules/windmill |
| **Prompter** | Prompts | station.center/modules/prompter |
| **Brandmark** | Brand marks | station.center/modules/brandmark |

The Neue design system sits beside the libraries. Studio Design is not part of Station: it is Cardsite, Inc.'s proprietary design system ([Cardsite §4](52xCardsite-Overview.md#4-studio-design)).

Library previews run on the untrusted sandbox (`folio.sndbx.at`), never under station.center.

## Addresses

One rule governs every Station address:

> **If you read it, it's a path. If it runs, it's a subdomain.**

| Address | What | Runs on |
|---|---|---|
| `station.center` | Home: what Station is and where to start | Cardsite |
| `station.center/protocol` | The specification, versioned (`/protocol/1.0`) | Cardsite |
| `station.center/modules` | Module directory | Cardsite |
| `station.center/modules/<library>` | Station Libraries | Cardsite |
| `station.center/directory` | The registry of every published standard, module, and repository | Cardsite |
| `station.center/llms.txt` | One index of all Station, for agents | Cardsite |
| `cloud.station.center` | Station Cloud, including sign-in | Coolify (52 Online) |
| `api.station.center` | Station API | Coolify (52 Online) |
| `<label>.station.center` | A hosted module's front-end; its services are `api.<label>.station.center` | Front-end on Cardsite, services on Coolify |

Published `/protocol/<version>/` URLs never change. A new version gets a new path.

Former Station domains (stationprotocol, stationmodules, stationcenter, and others) redirect here ([Reserved Domains](52-Reserved-Domains.md#station)).

## How a project becomes a Station project

- A repository follows the Station layout, with a `station.json` naming its organization and role, a `.station/STATUS.md` stating what is true now, and an `AGENTS.md` telling an agent what to read, run, and never do.
- `station check` confirms the layout. `station add` installs a published standard or module.
- Nothing is listed anywhere automatically, and nothing is listed twice. A role names one repository across the group.
- Station is optional for the tools that read it. Operator OS ships Station as a built-in skill, and runs the same with it removed ([Operator overview](Operator-Overview.md)).
- Adopting Station for a client (migration, implementation) is 52 Studio's work, never 52 Software's.

## Where Station sits

- **Product of 52 Software.** 52 Software makes Station and nothing else. It provides no client services ([Holdings §3](52!-Holdings-Overview.md#3-entities)).
- **Runs on Operator OS and others.** Operator OS is one harness Station runs on, not part of it.
- **Sponsored by Cardsite.** Cardsite® is credited as Flagship Sponsor on Station surfaces and is the reference Static Hosting Partner: every static Station surface runs on Cardsite ([52 x Cardsite §3](52xCardsite-Overview.md#3-52--cardsite)).
- **Cardsite is a Station adopter.** Moving Cardsite's repositories and systems onto Station Protocol is a 12-month 52 Studio engagement.

## Proposed copy

> **Station is an open standard for projects that describe themselves.** Everything describes itself.
>
> **One shape.** Every Station project is laid out the same way, so a person reads it in a minute.
>
> **Agents can pick it up.** What it is, what's true now, and what to never touch are written down where an agent looks first.
>
> **Works with the agents you already use.** Station runs on OpenClaw, Hermes Agent, Meta Muse, Operator OS, and more. It brings no agent of its own.
>
> **Start from something good.** Station Libraries offer templates, creative assets, prompts, and brand marks, all open and ready to use.
>
> **Open first, hosted when you want it.** Station Protocol and Station Modules are free and open source. Station Cloud adds hosting, storage, and inference.

## Who it's for

- A team that wants every repository to explain itself the same way, to new people and to agents.
- A company like Cardsite moving its projects and machines onto one shared description.
- A creator or studio that wants a starting point from Folio, Windmill, Prompter, or Brandmark.
- A person running an agent like Operator who wants their workspace to become a Station project, with a single `AGENTS.md`.
- An agency such as 52 Studio adopting Station for clients.

## Registry

| | |
|---|---|
| Domain | station.center (Public); former domains in [Reserved Domains](52-Reserved-Domains.md#station) |
| Email | contact@station.center · `noreply@station.center` sends only · security reports to contact@station.center |
| GitHub | `@stationprotocol` (Public) · `@stationmodules` (Public) · `@stationcenter` (private repositories) |
| npm and images | Scope follows the organization: `@stationprotocol/…`, `@stationmodules/…`, `@stationcenter/…`; `ghcr.io/<org>/<repository>` |
| Trademarks | Station™ · Station Center™ (FiftyTwo Software, Inc.) |
| Licence | Every LICENSE and SECURITY.md names FiftyTwo Software, Inc. |

---

Station™ and Station Center™ are trademarks of FiftyTwo Software, Inc. Details are subject to change before general availability.
