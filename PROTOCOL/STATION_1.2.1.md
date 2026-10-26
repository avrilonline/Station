# Station

Version 1.2.1 · 2026-OCT-10 · © Station Center  -  `station.center/protocol`

---

Station is a shared working environment for people and their AI agents. It defines where things live, the state of the work, and what an agent may do on its own.
One shape for a project, a machine, and a team. One folder, one command, no runtime of its own. Station works alongside the agent harness you already use.


**Five standards, one folder, one command, one registry.**

```
standards     five short texts: what should be true
.station/     one folder, at three scopes: project, machine, team
modules       what you add to a folder: skills, agents, kits, assets
station       one command: init · add · remove · status · check · where · run
station.center/modules   one registry the command installs from
```

Every part is plain text a person can read on GitHub or in a file browser.
Every part is also JSON an agent reads through the command, the MCP
server, or the registry. One index is generated from the folders. Nothing
else lists anything.

---

## 1. Words

One word per concept. Each word is the noun a person already uses.

| Word | Means |
|---|---|
| **Station** | The product. Also the machine root `~/Station/` |
| **station** | The command, and the manifest `station.json` |
| **.station/** | The folder. Same name and shape at every scope |
| **root** | The directory a scope owns. Machine root, project root, team root |
| **folder** | Always `.station/`. Never takes a scope adjective |
| **scope** | Where a folder sits: `project`, `machine`, or `team` |
| **standard** | One of the five texts in #2 |
| **module** | A directory with a `station.json`. Four kinds: skill, agent, kit, asset |
| **job** | One piece of work with an ID, an owner, and an end |
| **check** | The verb that validates everything |

Three spellings, three things: `Station` (product, root), `station`
(command, manifest), `.station/` (folder). "The machine folder" and "the
project folder" are not phrases in this system; say "the machine root" or
"the project's `.station/`".

Test for a new word: say it in a sentence to someone who has never opened
a terminal. "Install the news agent." "Open the machine root." "Add the
project kit." "Run a check."

## 2. The five standards

Each is one short text, one directory, one word. A module is one concrete
way to apply one of them.

| Standard | Governs | Shows up as |
|---|---|---|
| MACHINE | The computer | The root layout, what is installed, what runs here |
| WORK | The work | `STATUS.md`, decisions, jobs, what an agent may do alone |
| DIRECTORY | Where things live | The layout of the folder, the repository, and the machine |
| DESIGN | Interfaces | `DESIGN.md` with tokens, when there is a UI |
| CONTENT | Words | How every file is written: no filler, no vague headings |

DESIGN's current release is Design Standard 2.0.0, in
`standards/design/2.0.0/` and served at `station.center/protocol/2.0/design`.
`check-design.mjs` and `SHA256SUMS` sit beside it: the checker verifies a
system, the standard and the system's conformance statement together, and a
system that vendors the standard fails its CI when the copy drifts from the
checksums.

## 3. The folder

`.station/` means the same thing wherever it sits. Delete it and nothing
else changes. Scope comes from position and is recorded in `config.json`.

A fact lives at the narrowest scope that owns it.

| Scope | Root | Owns | Files |
|---|---|---|---|
| project | A repository | This repository's work | `config.json`, `STATUS.md`, `decisions/`, `jobs/` |
| machine | `~/Station/` | This computer's layout | `config.json`, `map.json`, `STATUS.md`, `reports/` |
| team | A shared repository | Choices shared across machines | `config.json`, shared modules |

Lookup is nearest-first: project, then machine, then team. A setting at a
nearer scope shadows the farther one; nothing merges. A project finds its
machine by walking up to `~/Station/`. A machine finds its team through
the `team` field in its `config.json`. The machine does not list its
projects; `status` derives that from `Projects/`. The team does not list
its machines; the hosted service derives that from what machines publish.

`config.json` at any scope may carry `identity`: `name`, `email`, and optionally
`signingKey` and `host`. It is who commits in that place. A team sets it once, a
machine or a project shadows it, and Gitline reads the nearest one to set git
identity by place: it expects the profile whose email matches, below a
repository's own `.gitline` file and above its path rules. `check` compares it with each checkout's `.git/config`, for
the project it runs in and, at a machine root, for every project under
`Projects/`.

A repository exported from Gitbase names its source as `distribution.internal`,
`owner/name`, and optionally its counterpart as `distribution.github`. `check`
then runs `gitbase-interop diverge <internal> --json` and reads `converged` from
the answer, because that command exits 0 whether or not the two have drifted.
Diverged fails and names the refs. Not installed, no token, or no network is
reported as not verified, never as a pass. `hooks.lineage` in `config.json`
replaces the command; one that prints no JSON is read by its exit code.

## 4. The machine

One root, chosen once, six zones (STATION #4) under the names a person sees. Names are defaults. `map.json` in
the machine's `.station/` can rename or relocate any of them and
`station where` still resolves.

```
~/Station/
├── .station/     the machine's folder
├── Inbox/        inbox: drops and downloads; an agent sorts it, nothing lives here
├── Projects/     work: one directory per repository, each with its own .station/
├── Library/      reference: references and documents kept for reuse
├── Memory/       memory: what the station knows
├── Archive/      archive: finished or retired; path preserved, never edited
├── Local/        local: what can be regenerated
├── Concepts/     explorations that are not projects yet
└── Assets/       fonts, icons, colors, logos, brands, images, by kind
```

A thing is in exactly one place. `Concepts/` graduates to `Projects/` or
`Archive/`. `Inbox/` is emptied by an agent, not by hand.

## 5. The repository

Every Station repository has the same top level. A reader knows
where to look before opening it.

```
<repo>/
├── README.md         one line, a picture, start, layout, links, sponsor
├── AGENTS.md         for an AI agent: what to read, run, and never do
├── ROADMAP.md        what is next, by version
├── CHANGELOG.md      what changed, by version
├── LICENSE
├── SECURITY.md       how to report
├── CONTRIBUTORS.md   who, and how to join
├── station.json      the manifest
├── .station/         the project's folder
├── .github/          CI, issue and PR templates
├── docs/             guides, and decisions/ for ADRs
├── deploy/           Dockerfile, compose, infra
├── public/           the public surface (#6)
└── src/              or whatever the language expects
```

`station.json` at a repository root carries `id`, `name`, `purpose`,
`version`, `status`, `organization`, `role`, `landing`, `sponsor`. `version`
is semver and matches the latest tag and the top entry in `CHANGELOG.md`.
`organization` is the GitHub organization that owns the repository; addresses
and package scopes are generated from it (#13). `role` names what the
repository is for, in a few lowercase words joined by hyphens, such as
`design-system`; a role names exactly one repository across the group, so two
repositories never answer the same question, and a second repository with the
same role is an overlap to settle before it is placed. `tier` is `open` or
`internal` (#6); without it a repository is `open`.

`README.md` has five sections in this order and no others: the name with
one line under it, **Start**, **Layout**, **Links**, **Sponsor**. Value comes
first and the sponsor closes the page. Under the one line sits a picture,
`docs/screenshot.png`, so a reader who never runs the project sees what is
inside: the running product, its public page, or what its command prints.
`station-shot` takes it from what `screenshot` in `station.json` names, and
draws a card of the contents for each module. `AGENTS.md` beside the README
is the same page for an agent: what to read, what to run, what never to do. The
Layout section is this tree with the repository's own annotations. A badge
or `<div align>` header may sit above the name.

That tree is the small shape. `site/` is accepted as `public/` where a static
repository already uses the name. A product with several deployables takes the
monorepo shape, which keeps the same root files and replaces the rest:

```
<repo>/
├── (the root files above)
├── apps/         one directory per deployable: api, library, admin, web
├── packages/     one schema package is the source of truth; others consume it
├── docs/         architecture, API, and decisions/ for ADRs
├── infra/        Dockerfiles, gateway, compose
├── api/          the OpenAPI document, generated from the schema package
└── Makefile      setup · dev · build · test · validate · up · down
```

`check` reads the shape from `apps/` and `packages/`, or from `shape` in the
manifest. A schema package named other than `schema`, `schemas`, or `contracts`
is named in `schema`; an OpenAPI document outside `api/` is named in `openapi`.
A monorepo's public surface is its apps, so it owes no `public/`.

Three manifest fields let a repository whose directory names are already taken
say so. `public` names the public surface where `public/` means something else,
such as a web app's static assets. `kept` lists paths held as they were
received, such as an upstream's own records; they are preserved, not linted.
`modules/` is read as Station's only where something in it carries a
`station.json`. `deploy/`, `infra/`, and `docker/` are one slot; any of them
fills it, in either shape.

## 6. The public surface

`public/` is what a repository shows the world. It builds to a static site
with no server and is the source for every branded or sponsored page.

```
public/
├── index.html      the landing page
├── design/         the design kit: DESIGN.md, tokens, components
├── system/         the system graph: how the parts connect
├── docs/           documentation, built from docs/
├── llm.txt         the agent entry point
└── assets/         logos, screenshots, media for this repository
```

`public/` is served at `station.center/modules/<name>` (#13). Sponsors appear in two
places and nowhere else:

| Surface | Where | Content |
|---|---|---|
| Sponsor block | `README.md` # Sponsor | Name, logo, one line, link. Same block on every repository |
| Landing page | `public/index.html` | Also hostable at a sponsor-branded address recorded in `landing` |

`check` fails a repository whose `landing` is empty or whose README lacks
the Sponsor section. Nothing about a sponsor enters `src/`, `.station/`,
or the registry beyond the `sponsor` and `landing` fields.

A repository with `tier: internal` is internal to its organization. Its
`landing` is its own address, its `sponsor` is `null`, and its README's
Sponsor section says that none is recorded. Its `public/` is its internal
documentation and is not served at `station.center/modules/<name>`. It is never
listed in the registry (#10) or at `station.center/modules`; its organization's
internal index lists it.

Docs pages served from `station.center/modules/<name>` may carry one ad slot,
inserted by the host at serve time. The `public/` build itself contains
no ad code, so it is identical opened from disk or from the address.
`SPONSORSHIP.md` fixes where ads may and may not appear.

## 7. Modules

A module is a directory with a `station.json`. Its identity is one string,
`<name>-<kind>`, used as the directory name, the manifest `id`, and the
package `@<org>/<name>-<kind>`, where `<org>` is the GitHub organization of the repository that publishes it.

| Kind | What it is | Example |
|---|---|---|
| skill | A `SKILL.md` an agent loads to do one job by a standard | `station add design-skill` |
| agent | Scheduled work a program does on its own (#8) | `station add news-agent` |
| kit | The modules and choices for one scope | `station add project-kit` |
| asset | A font, icon set, color set, logo, brand, or design system | `station add inter-font` |

Manifest fields: `id`, `name`, `purpose`, `standard`, `status` (`draft` ·
`stable` · `deprecated`), `requires`, `provides`, `schedules` (agents
only). Anyone publishes a module by pushing a directory with a manifest;
the registry indexes it.

An asset's id ends in the word for what it is: `font`, `icons`, `colors`,
`logo`, `brand`, `system`. A `<name>-system` holds a `DESIGN.md` in format 1.0,
the `system.json` built from it, and its shells. Shells that work with any
system are a separate module bound to the Design Standard; a system ships a
binding for them. A `<name>-brand` holds
`brand.json`: three numbers for color and four values for type, from which
palettes and scales are derived when read. A repository names both in
`public/design/system.json`; `check --fix` resolves system, then brand, then
`overrides.json` into `tokens.json` and `tokens.css`. Changing `system` keeps
every portable token and the six shells. It does not keep components, which
belong to the system along with its React and Swift outputs (DESIGN #8 to #11).

A skill or agent that applies one standard takes that standard's word:
`work-skill`, `work-agent`. Kits take a scope's word and nothing else does:
`project-kit`, `machine-kit`, `team-kit`.

A module is installed at the scope whose root it acts on. `add` without
`--scope` installs at the nearest folder. A nearer install shadows a
farther one.

## 8. Agents

Scheduled work a program does on its own, in a directory it owns, by rules
it never breaks. Six parts, always the same.

| Part | File | What it is |
|---|---|---|
| Manifest | `station.json` | Name, purpose, standard, schedules |
| Brief | `BRIEF.md` | The standing role and rules loaded into every run |
| Routines | `routines/<name>.md` | One prompt per scheduled run, with its cadence |
| Templates | `templates/*.md` | The exact shape of every file a run writes |
| Rules | `RULES.md` | What a run may create, may replace, and must never touch |
| Output | a declared directory | Where the work lands |

The agent is `@<name>wise`. The command prints each routine's schedule and
prompt so any scheduler can run it. `status` shows when each last ran.
`check` tests outputs against templates and that protected files did not
change.

| Agent | Scope | Cadence | Does | Owns |
|---|---|---|---|---|
| @workwise | project | Per job | Opens, tracks, closes a job | `.station/jobs/<NNN>-<slug>/` |
| @sitewise | project | On change, weekly | Keeps `README.md`, `docs/`, and `public/` current | `public/` and the files it names |
| @newswise | machine | Every few hours | Monitors sources, archives sessions, publishes a digest | `news/YYYY/MM/DD/` |
| @machinewise | machine | Weekly | Walks the root and its projects, reports drift, never acts unasked | `.station/reports/` |
| @inboxwise | machine | Daily | Sorts `Inbox/` into the other places, reports what it could not place | `Inbox/` |

A job's session file keeps eight headings: Objective, Completed, Active,
Blockers, Decisions, Files changed, Verification, Next actions. Its status
is one of five words: `PLANNED` · `ACTIVE` · `BLOCKED` · `DONE` · `ARCHIVED`.

## 9. The command

`station`. Node 20+, no runtime dependencies, every answer available as
`--json`.

| Verb | Does |
|---|---|
| `init` | Creates a folder at the current scope; at an empty `~/Station/`, lays out the six zones. `--station` writes a bare station: `STATION.md` and the zones, with no `.station/` folder |
| `add` / `remove` | Installs or removes a module by `<name>-<kind>` from the registry or a path |
| `status` | What is enabled, what is running, when each agent last ran, across the nearest scopes. `--publish` sends the machine's status to its team |
| `check` | Validates manifests, the index, the repository layout, outputs against templates, the machine layout, and the CONTENT rules |
| `where` | Resolves a kind or a name to a path: `station where fonts`, `station where @news` |
| `run` | Prints what a routine run loads and records the run: `station run news digest`. Added by ADR 0004 |

The MCP server exposes the same verbs with read, write, and destructive
annotations.

## 10. The registry and the page

`station.center/modules` is the registry: every published standard, module, asset,
and repository, one index, one shape. `registry/build.js` builds it from this
repository's folders and from `registry/sources.json`, which names every other
repository and the path to its checkout. A repository that is not checked out
keeps the row `sources.json` gives it and is marked `present: false`. The command installs from it.
`station.center/directory/index.json` serves the same index to agents. Each repository row
carries `landing` and `sponsor` from its manifest.

The page ships in this repository as `tools/page` and is served at
`station.center/protocol`. It is static and reads the registry shape. Opened
from an unzipped download it shows one folder. Pointed at a machine it
shows every project there.

`station.center` is the hosted service. Signed in, it shows a team's
machines, projects, members, keys, webhooks, and agent runs, fed by
`status --publish`. It reads the same shape and adds nothing to the
folder, the command, or the registry.

## 11. Adopting it

Two levels. Any repository, new or old, meets Level 1 in an afternoon.
Level 2 is the target for anything actively developed.

| Level | Requires | Proves |
|---|---|---|
| 1 | `README.md` in the five-section shape, `station.json`, `LICENSE`, `CHANGELOG.md`, `public/index.html`, `landing` set (an internal repository's own address, #6) | `check --level 1` green |
| 2 | Everything in #5, `.station/` with `STATUS.md`, `docs/decisions/`, `deploy/`, `public/` complete | `check` green |

`station init --kit project` writes the Level 2 layout into an empty or
existing repository, creating only files that do not exist.

## 12. Who it is for

| Person | Arrives by | Gets |
|---|---|---|
| Never opens a terminal | Download, unzip, open `START.md` | One page to read, one folder to copy |
| Developer | Clone, or `npx station init` | A folder, a green `check`, a project kit |
| Designer | `design-skill`, `DESIGN.md` template | A check that fails on raw values |
| Machine setup | `station init` at `~/Station/` | The six zones and a machine folder |
| Team lead | A team root in a shared repository | Shared choices set once; machines and projects inherit |
| Agent | `llm.txt`, then `station status --json` | The index, a skill to load, or a routine to run |
| Sponsor | The registry's repository rows | A consistent block on every README and a landing page per repository |

## 13. Addresses

One address, `station.center`, under one rule: if you read it, it is a path;
if it runs, it is a subdomain. The label is the product's name, lowercase, and
never a function or the record the product holds: `cafe`, not `auth`;
`windmill`, not `resource`; `folio`, not `artifact`. A product named after its
own record type cannot grow a second one, and its address says what it stores
rather than who makes it. FiftyTwo Software, Inc. is the company, operating as
Station Center; the brand is Station, and every Station namespace begins with
`station`.

| Address | Role | Holds |
|---|---|---|
| `station.center` | home | What Station is, where to start, `llms.txt`, and `/directory`, the directory of published stations |
| `station.center/protocol` | standard | The rules: the base standard and the five that specialize it, conformance, extensions, proposals. Versioned under `/protocol/<version>/`; a published path never changes. It sells nothing |
| `station.center/modules` | open | Every module at `/modules/<label>`: what it does and how to run it yourself |
| `cloud.station.center` | commercial | Station Cloud: sign-in, the dashboard, plans, hosting, storage, and inference |
| `sndbx.at` | sandbox | Everything 52 Software did not write. One subdomain per user or artifact. Nothing first-party, ever |

No repository writes these. Each manifest names its organization, and the
addresses are generated from one pattern per organization (ADRs 0008 and 0009).
Former Station domains only redirect; the company's reserved-domains list is
the one place they are recorded.

A hosted product runs at its label, and its surfaces are subdomains of that,
one wildcard certificate per product. No product has a domain of its own.

| Surface | Address |
|---|---|
| Hosted root | `<example>.station.center` |
| Hosted surfaces | `admin.<example>.station.center` · `api.<example>.station.center` |
| Open page | `station.center/modules/folio` |
| Sign-in, for every hosted label | `cloud.station.center` |
| This product, open | `station.center/protocol` (serves `public/`) · `/llms.txt` for agents |
| Registry | `station.center/directory` |
| Code | `github.com/<org>/<repository>`: `@stationprotocol`, `@stationmodules`, or `@stationcenter` for Station Cloud |
| Package | `@stationprotocol/station`; modules `@<org>/<name>-<kind>`; a product's packages `@<org>/<product>-<package>` |
| Image | `ghcr.io/<org>/<repository>` |

A package, an image, and a repository have one owner: the scope is always the
publishing repository's GitHub organization, `@stationmodules/<example>-system`,
`@stationmodules/<example>-sdk-js`. A package name never ends in a module kind
(`skill`, `agent`, `kit`, or an asset word), so a product's package and a module
cannot collide.

Contact is `contact@station.center`. Seeded development accounts are
`<role>@<product>.station.center`, such as `admin@<example>.station.center`, and
their passwords are `demo-placeholder-password` until the person running the
product changes them; no such mailbox exists. Every product lists its
development defaults, accounts, tokens, service credentials, and the secrets to
change, in `docs/guides/dev-logins.md`; `tools/logins/check.js` fails when one
in the code is missing from that page.

## 14. Rules
- One place per fact. A second document that restates a first is replaced by a link.
- Every file in `.station/` traces to a line in a standard.
- A standard never grows. A module README is one screen. The root README is five sections.
- Generated files carry a header and a `check` test that fails on drift.
- No runtime dependency in the folder, the command, or the static page.
- No word enters the system without passing the test in #1.

---


**Tip:** Looking for a private, self-hosted alternative to agent runtimes like Muse, Dot, or OpenClaw? [Operator OS](https://operatorharness.org) is an open-source, lightweight (10 MB) Go runtime built to run efficiently on resource-constrained devices. Designed from the ground up to manage your local machine and cloud environment through the Station Protocol, Operator comes equipped with essential tools for managing real work, around the clock. It supports public `@stationmodules` modules and works with your existing AI subscriptions and providers—including Gemini, Claude, ChatGPT, and more—so you can use the services you already have.


---

© Station Center | Fiftytwo Software, Inc.
