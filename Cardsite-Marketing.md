# Cardsite® Marketing

The single reference for writing any customer-facing material about Cardsite: websites, landing pages, ads, social, email, launches, print and partner material.

Built from *Cardsite® — Brand & Product Overview* (August 2026). Version: October 2026.

**How to use this document.** Read it whole, or pull out any one section. Each section stands on its own. Every section follows the same three rules, which apply even when it's used alone:

- **Write for people, not developers.** Lead with what the reader gets, never with how Cardsite works.
- **Claim only what's in Product Facts.** No invented features, integrations, numbers, customers or comparisons.
- **Translate internal words.** Slug, resource, gate, routing and similar terms stay internal (see Voice & Copy Rules).

**Status labels** used throughout:
**[FACT]** stated in the source overview, safe to use · **[STRATEGY]** this document's recommendation, not yet validated · **[EXAMPLE]** illustrative copy or scenarios, never presented as real customers · **[OPEN]** unknown, so don't claim it.

**Where to look**

| You need to… | Go to |
|---|---|
| Brief an agent | Agent Instructions |
| Check whether something is true | Product Facts, then Open Questions |
| Decide what to say and to whom | Positioning & Messaging, Audiences |
| Market a specific feature | Features → Value |
| Get the wording right | Voice & Copy Rules |
| Write for a specific channel | Channel Guide |
| Start from existing lines | Copy Bank |
| Teach the difference between docs and marketing | Before & After |

---

## Agent Instructions

*Use as a system prompt for any agent writing Cardsite marketing. It works on its own; it works better with Product Facts and Features → Value in context.*

```
You write marketing for Cardsite. Your readers are everyday people: creators,
local businesses, students, event organizers, agency teams. They are not
developers and don't care how Cardsite works. They care what it lets them do,
what it saves them from, and what they get.

Your job: make Cardsite's value obvious to the reader, in their words, for
their situation. Never rephrase product documentation. If source material is
technical, translate it; its style does not carry over into the copy.

Before writing:
- Identify the reader. If none is given, pick the likeliest for the channel and
  say which you chose.
- Pick the one thing they want right now, and the single benefit that answers
  it. One message per piece.
- Check every factual claim against Product Facts.

How to write:
- Open with the reader's outcome or problem. Feature names come second, if at all.
- Be concrete. A real-feeling situation (a menu, a link in bio, a launch, a
  client preview) beats an abstract claim.
- Plain, confident, contemporary language. Short sentences, active verbs, "you".
- Sound like a capable friend, not a press release or a spec sheet.
- Test every line: would a stranger see why it matters to them?

Words: say link or address, not slug; page, link, file or site, not resource;
keep private or password-protect, not gate; send people to the right place,
not routing; the card, not card view. Technical terms (HTML, React, SSL,
pixels, subdomain) only for technical or marketer readers, and only when they
help. No startup clichés (unlock, seamless, supercharge, elevate, empower,
leverage, game-changer, all-in-one solution).

Truth:
- Claim only what Product Facts states. Never invent features, integrations,
  named platforms, metrics, speeds, customer results, testimonials, user
  counts or competitor comparisons.
- Illustrative scenarios are fine, framed as examples, never as real customers.
- If a brief asks for an unsupported claim, write around it and flag it.
- Prices and plan limits may change; use them only in pricing contexts, exactly
  as listed.

Brand:
- "Cardsite": one word, capital C. "Cardsite®" at first mention in a document,
  page or email; plain after.
- Addresses in lowercase: card.site/yourname.
- "Cardsite is a presence platform" is the brand line. Pair it with a concrete
  line; never use it alone as a headline for new audiences.

Output: deliver the copy first. Then, under "Notes", list any assumptions or
unverified claims. When asked for options, give genuinely different angles,
not rewordings.
```

---

## Product Facts

*The source of truth. Internal reference: precise, not persuasive. Don't paste it into marketing; translate it. If something isn't here, it isn't established. Check Open Questions.* **[FACT]** throughout, except where marked.

### Identity

| | |
|---|---|
| Company | Cardsite, Inc. (Delaware) |
| Product | Cardsite® (registered trademark, USPTO) |
| Brand line | Cardsite is a presence platform. |
| Descriptor | Create, host, and share pages, links, QR codes, sites, files, and more in seconds. |
| Web / contact | cardsite.com · contact@cardsite.com |

"Cardsite" is one word with a capital C. Use ® at first mention in any document; plain "Cardsite" afterwards.

### What it is

People reach someone through QR codes, social profiles, search, messages, ads and shared links. Cardsite gives each one a short address that can be a page, a link, a file, a site or a card. Cardsite hosts them, routes visitors, controls access and measures results, all in one place.

**Addresses:** card.site/name (standard) · name.card.site (subdomain) · yourdomain.com/name (own domain, with SSL) · crd.site (archive for inactive content).

### Capabilities

| Area | Verified capabilities |
|---|---|
| Hosting | Upload existing work: static HTML, zips, React, Markdown, SVG, files. Custom domains, SSL, global delivery, search indexing, bot protection. |
| Addresses | Short chosen addresses, subdomains, custom domains, dynamic QR codes whose destination can change after printing. |
| Routing | Smart links that send each visitor somewhere by device, location, language or rule. Redirects. |
| Access | Password protection, audience-limited visibility, content warnings before entry. |
| Analytics | One analytics view across pages, links and QR codes. Marketing pixels and campaigns managed in one place. |
| Collaboration | Workspaces shared with people and AI agents. Scoped permissions, version history, backups. |
| AI drafting | Draft copy, assets and docs with AI, saved in the workspace with its context and access rules. |

**Things you can make:** short links, bio pages, contact cards (vCards), events, files, static pages, splash pages, payment links, smart links, dynamic QR codes, cards.

**The card:** put @ before the name in any *public* Cardsite address to see a summary card of it, adapted to whoever's looking (device, language, referrer). card.site/alice is the page; card.site/@alice is its card. This works on own domains too.

### Plans

*Subject to change before general availability. Verify before publishing prices or limits.*

| | Free | Starter | Pro | Business | Business+ | Enterprise |
|---|---|---|---|---|---|---|
| Price | $0 | $5/mo | $25/mo | $100/mo | $500/mo | Custom |
| Chosen addresses | 1 | 3 | 5 | 10 | 25 | Custom |
| Subdomains | 0 | 1 | 3 | 5 | 25 | Custom |
| Own domains | 0 | 0 | 1 | 3 | 25 | Custom |
| Workspaces | 1 | 2 | 5 | 10 | Unlimited | Unlimited |
| Storage | 100 MB | 1 GB | 10 GB | 100 GB | 1 TB+ | Custom |

Automatic (auto-generated) addresses are unlimited within storage on every plan. Starter is the first plan with a subdomain; Pro is the first with your own domain.

### When addresses are released

Content stays at its address while a Free account is active or a paid subscription is current.

| | Free | Paid |
|---|---|---|
| Released after | 90 days with no sign-in **and** no visitors | 90 days after the subscription lapses |
| Notices before release | 30 days, 7 days, 3 days, 24 hours | 90, 60, 30, 7, 3 days, 24 hours |
| Afterwards | Address becomes available to others; content readable at the archive address for 12 months | Same, and the archive address is reserved for the original owner up to 3 years |

Archive rule: drop the "a" (card.site/x → crd.site/x; name.card.site/x → name.crd.site/x). Signing back in (Free) or resubscribing (Paid) during the archive window restores the content and archive address immediately, and the original address if nobody has taken it.

Safe to say: a Free page that's getting visitors isn't released just because the owner hasn't signed in; nothing is released without several notices; released content stays readable for 12 months.

### Named audiences

A creator launching products and sharing one link in bio. A local bakery publishing a menu through a dynamic QR code that updates without reprinting. A student organizing research and sharing it with a card. An agency running campaigns, microsites, branded links and analytics for each client in separate workspaces.

### Approved copy

Company-approved "About" text. Quote verbatim when official copy is needed.

> **Cardsite is a presence platform.** Create, host, and share pages, links, QR codes, sites, files, and more in seconds.
>
> **One place for your domains, pixels and campaigns.** Connect what you already own and manage it together.
>
> **Short URLs people remember.** card.site/Demo-Q4-Review, not a string of characters.
>
> **Host what you already built.** Static HTML, zips, React, Markdown, SVG. Search indexing, bot protection and SSL included.
>
> **Every URL has a card.** Add @ to any Cardsite link to see it as a summary, rendered for whoever is looking.
>
> **Route and redirect.** Send each visitor to the right destination by device, location or language. Track what happens after the click, scan or visit.
>
> **Gate what's private.** Password gates, audience limits, content warnings.
>
> **Work with people and agents.** Shared workspaces, scoped privileges, version history, backups. Give your agent the tools to manage your presence.
>
> **Create in place.** Draft copy, assets and docs with AI and keep them organized where they'll be used.

### Claim guardrails

| You may say | Don't say (not established) |
|---|---|
| Change where a printed QR code goes; update your pages; set up redirects | That every short link can be re-pointed after sharing |
| One view of clicks, scans and visits across pages, links and QR codes | Specific metrics, real-time stats, conversion or revenue tracking |
| Manage your marketing pixels and campaigns in one place | Named ad platforms or pixel providers |
| Send visitors somewhere by device, location or language | Specific "rule" types |
| Password-protect, limit who can see it, add a content warning | How audience limits work in practice |
| Share a workspace with your team and AI agents, with permissions | Which agents or AI tools are supported |
| Draft copy, assets and docs with AI | AI models, quality claims |
| Payment links, events, contact cards exist | Payment providers, fees, ticketing, RSVPs |
| SSL, search indexing, bot protection, global delivery included | Speed or uptime figures, SEO ranking gains |
| "in seconds" (within the approved descriptor) | Specific timings, "instantly" |
| Several notices before an address is released | "Your links never expire", "free forever" |
| — | Customer counts, testimonials, results, awards, "#1", "the only", or comparisons with competitors |

---

## Positioning & Messaging

*What to say about Cardsite and in what order. Facts behind every message are in Product Facts.* **[STRATEGY]** unless marked.

### The core idea

People find you in a dozen places: a QR code on a table, the link in your bio, a text, an ad, a search result. Usually each points somewhere different, made with a different tool, and none of them tell you anything.

**Cardsite gives everything you share one home.** It's a short address that's yours. It can be a page, a link, a file or a whole site. You can update it after it's out in the world, and it shows you what's working.

### The story, at three lengths

**One line:** Everything you share, in one place you control.

**Short:** Your menu, your portfolio, your launch, your link in bio. Cardsite gives each one a short address people remember and lets you update it whenever things change, even a QR code that's already printed. It also shows you what's working.

**Medium:** You share things everywhere: QR codes, social profiles, messages, ads. Keeping track usually means separate tools, long ugly links and printed codes you can't fix. Cardsite puts it all in one place. Make a page, a short link, a QR code or a whole site in seconds, and give it an address people remember. Update it whenever things change. Send each visitor to the right place, keep private things private, and see what's getting attention. You can even use your own domain.

**Long:** use the approved copy in Product Facts.

### Positioning statement

For people and teams who share things online and off (creators, local businesses, students, agencies) who are tired of scattered links, codes they can't change and not knowing what works, Cardsite is the one place to create, host and share pages, links, QR codes, sites and files. Every one of them gets a short, memorable address you control, can update and can measure. That replaces juggling a separate tool for each.

*This names no competitor and makes no comparative claim. Keep it that way.*

### The five reasons to choose Cardsite

Lead with one. Use others as support.

| Reason | Promise in the customer's words | Proof [FACT] | Best for |
|---|---|---|---|
| **One home** | Your pages, links, files, QR codes and sites, together, at addresses people remember. | Chosen addresses, subdomains, own domains; many types of content in one account | Everyone (the default lead) |
| **Change it anytime** | Update your page, or change where a printed QR code points, without starting over. | Dynamic QR codes, redirects, version history | Local businesses, events, anything printed |
| **See what works** | Every click, scan and visit, in one view. | One analytics view; pixels and campaigns together | Creators, agencies, marketers |
| **Right place, right person** | One link sends each visitor where it makes sense for them. | Smart links by device, location, language | Apps, multi-country or multilingual audiences |
| **Your terms** | Keep private things private. | Passwords, audience limits, content warnings | Students, client work, previews |

**Supporting messages** (rarely the lead): every link has a card · bring a site you've already built · work together with your team and AI agents · draft copy where it'll be published · your links don't disappear without warning.

**Details** (prices, limits, file formats, technical specs) go on pricing pages, FAQs, help content and technical pages.

### What makes Cardsite distinctive

Use these as things Cardsite does, never as comparisons.

- **Breadth under one set of addresses.** Links, bio pages, files, whole sites, QR codes, payment links, events and contact cards all get the same kind of short address, on card.site, a subdomain or your own domain.
- **Printed things stay fixable.** This is the most concrete, relatable story in the product.
- **The card.** Add @ to any public link and get a summary card. It's memorable and easy to demo.
- **A considerate lifecycle.** Pages with visitors aren't released for inactivity alone, there are several notices first, and there's a predictable 12-month archive.
- **Built for working with AI agents.** A real edge with teams and early adopters. Not a lead for everyday audiences.

### Using "presence platform"

It's the approved brand line [FACT], but abstract. Keep it in boilerplate, About text, partner and press material, always followed by the concrete descriptor. Don't use it as a headline for new audiences, and don't stretch it ("elevate your presence").

### Choosing the message

| Reader's situation | Lead | Support |
|---|---|---|
| One link for everything (bio, signature) | One home | See what works |
| Prints menus, flyers, signs, packaging | Change it anytime | See what works |
| Running campaigns, ads, launches | See what works | Right place, right person |
| Audience spans countries, languages, devices | Right place, right person | See what works |
| Sharing drafts, client work, coursework | Your terms | One home, the card |
| Already built a site | One home (bring what you built) | Own domain |
| Team managing many clients | One home (separate workspaces) | See what works, work together |

---

## Audiences

*Who Cardsite is for and what to lead with. The four core audiences are named in the source [FACT]; their motivations and frustrations are reasoned hypotheses [STRATEGY], not research. Scenarios are [EXAMPLE]. Claims must stay within Product Facts.*

**True of every reader:** they're busy and skimming, so the value must land in the first line. They have a job to get done today (a launch, a menu, a link), not a platform to evaluate. They trust specifics, and they don't want to learn new vocabulary.

### Creators

Makers, writers, coaches, musicians, artists, small online sellers. Usually solo, living on social platforms that allow one link.

- **Want:** one link that leads to everything (the new drop, the shop, the newsletter), and to know what followers actually care about.
- **Frustrated by:** ugly links, updating links every launch, not knowing which post worked.
- **Lead with:** One home (one link in bio), then See what works. Also: their name in the address, payment links, the card.
- **Scenario:** A ceramicist launches a collection on Friday. Her link, card.site/ash-ceramics, already points to her page. She adds the collection and a payment link, and by Monday she can see whether Instagram or the QR code at her market stall brought more visits.
- **Words that land:** your link, your page, your name, launch, drop, followers.
- **Avoid leading with:** hosting formats, workspaces, pixels, "presence platform".
- **CTA:** Claim your link · Make your page

### Local businesses

Cafés, restaurants, bakeries, salons, shops, gyms. Busy, not technical, and they print things.

- **Want:** customers to find the current menu, hours or specials, and to change them without reprinting.
- **Frustrated by:** reprinting when prices change, QR codes stuck on old PDFs, not knowing if anyone scans.
- **Lead with:** Change it anytime (the printed code keeps working), then See what works (whether people scan). Also: an address short enough to say out loud, their own domain on Pro.
- **Scenario:** A bakery puts one QR code on every table. When the autumn menu arrives, they update the menu page. The table cards stay where they are.
- **Words that land:** menu, specials, print once, no reprinting, customers, scan.
- **Avoid leading with:** analytics, routing, agents, file formats.
- **CTA:** Make your QR code · Put your menu online

### Students

Students, researchers, study groups. Price-sensitive (Free and Starter matter).

- **Want:** notes, projects and research in one tidy place, easy to share, with control over who sees what.
- **Frustrated by:** work scattered everywhere, messy links, not wanting everything public.
- **Lead with:** One home, then Your terms (password-protect drafts). Also: the card, free to start.
- **Scenario:** A student keeps her thesis research on password-protected Cardsite pages while it's a draft. She sends her supervisor card.site/@thesis-notes, a tidy summary card instead of a wall of links.
- **Words that land:** notes, projects, study group, share, private, free.
- **Avoid leading with:** campaigns, pixels, domains, business plans.
- **CTA:** Start free · Make your first page

### Agencies

Marketing, social, design and digital agencies, and freelancers with several clients. Fluent in marketing vocabulary; some are technical.

- **Want:** quick campaign pages and branded links, each client kept separate, results to report, control over who can touch what.
- **Frustrated by:** many tools per client, links and pixels scattered across accounts, access headaches.
- **Lead with:** One home (each client in its own workspace, on the client's domain), then See what works (results in one view, pixels and campaigns together). Also: routing, permissions, version history, backups, AI agents, hosting existing sites.
- **Scenario:** An agency launches a client campaign: a microsite on the client's domain, branded short links for each ad, and a QR code for the in-store display. All of it sits in the client's workspace with the client's pixels attached and one view of the results.
- **Words that land:** clients, campaigns, branded links, workspaces, reporting. Pixels, subdomains and React are fine here when they help.
- **Avoid:** "save hours" or efficiency claims with no proof.
- **CTA:** See plans for teams · Set up a client workspace

### Possible further audiences [STRATEGY, not named by Cardsite]

Each one is backed by verified features. Test them before investing.

| Audience | Lead | Built on |
|---|---|---|
| Event organizers | Change it anytime (schedules change, posters don't) | Event pages, dynamic QR codes, passwords |
| Freelancers & professionals | One home (portfolio and contact in one link) | Bio pages, contact cards, own domain |
| Small online sellers | One home + get paid | Payment links, bio pages |
| Makers with a site already built | Bring what you built, on your domain | Hosting, own domains, SSL |
| Teams working with AI agents | Work together, safely | Workspaces, permissions, version history |

---

## Features → Value

*Every major feature translated from what it is into what it does for someone. "Limits" lines are [FACT]; problem, benefit, angle and lines are [STRATEGY]; examples are [EXAMPLE]. ★ can headline · ◆ supporting · ○ mention, don't lead.*

### ★ Short, memorable links
- **What it does:** gives anything you share a short address you choose, like card.site/yourname.
- **Problem:** long, random links look untrustworthy and can't be said aloud or remembered.
- **Benefit:** people can type it, say it, remember it, and trust it's you.
- **Who & when:** anyone putting a link on a slide, a podcast, a business card, a bio.
- **Example:** a speaker ends with "slides at card.site/sam-talks", and the room actually writes it down.
- **Angle:** links people remember. *"A link you can say out loud."*
- **Limits:** chosen addresses per plan: 1 / 3 / 5 / 10 / 25. Automatic addresses are unlimited within storage. Never promise a particular address is available.

### ★ Dynamic QR codes
- **What it does:** a QR code you can point somewhere new after it's printed.
- **Problem:** the menu changes, the event moves, the offer ends, and the printed code is wrong forever.
- **Benefit:** print once, keep it current.
- **Who & when:** local businesses, events, packaging, posters, anything physical.
- **Example:** a café's table codes open the winter menu the day it launches. Same codes, no reprint.
- **Angle:** the printed thing stays right. *"Change the menu, not the QR code."*
- **Limits:** destination changes after printing; scans count in analytics. Don't claim code styling (colors, logos).

### ★ Bio pages
- **What it does:** a simple page with all your links, so one link in your profile leads to everything.
- **Problem:** your profile allows one link, and you have five things to share.
- **Benefit:** everything you want people to find, behind one link that's yours.
- **Who & when:** creators, freelancers, sellers, at every launch.
- **Example:** a musician's card.site/juno points to her new single, tour dates and newsletter.
- **Angle:** one link for everything you do. *"Everything you do, one link away."*
- **Limits:** works with the card. Don't claim templates, themes or specific blocks.

### ★ Analytics, pixels & campaigns
- **What it does:** one view of how people engage with your pages, links and QR codes, plus your marketing tracking and campaigns in one place.
- **Problem:** results scattered across tools, so you're guessing which post, code or link works.
- **Benefit:** know what's working and do more of it.
- **Who & when:** creators after a launch, businesses checking a printed code, agencies reporting to clients.
- **Example:** a shop puts one QR code on the window and another on its flyers, and sees which gets scanned.
- **Angle:** stop guessing. *"Every click, scan and visit, in one place."*
- **Limits:** no named metrics, ad platforms or pixel providers; no conversion or revenue promises.

### ◆ Smart links & redirects
- **What it does:** one link that sends each person to the right place for their device, location, language or a rule you set.
- **Problem:** one destination doesn't fit everyone (iPhone vs Android, US vs UK store, English vs Spanish).
- **Benefit:** everyone lands somewhere that makes sense, from a single link.
- **Who & when:** apps, international businesses, multilingual audiences, campaigns.
- **Example:** a podcast shares one link; iPhone listeners go to one app, everyone else to another.
- **Angle:** *"One link. Everyone ends up in the right place."*
- **Limits:** device, location, language, rule; redirects. Don't describe rule types.

### ◆ Your own domain & subdomain
- **What it does:** use your own web address (yourbrand.com/offer) or your own space on Cardsite (yourname.card.site).
- **Problem:** links on someone else's domain look less like you.
- **Benefit:** everything you share carries your name.
- **Who & when:** businesses, agencies (client domains), professionals building a brand.
- **Example:** a studio shares yourstudio.com/spring for its campaign page, hosted on Cardsite.
- **Angle:** your name on every link. *"Your own domain. SSL included."*
- **Limits:** subdomain from Starter; own domain from Pro (1), Business (3), Business+ (25). Don't promise domain registration.

### ◆ Bring what you built (hosting)
- **What it does:** upload a site or page you've already made, and it's online at your address.
- **Problem:** getting a finished site online usually means sorting out hosting and security certificates.
- **Benefit:** your work, online and shareable, with the essentials included.
- **Who & when:** designers, students with projects, people using site builders or AI tools, agencies with microsites.
- **Example:** a designer exports her portfolio and has it live on her own domain that afternoon.
- **Angle:** *"Built it already? Put it online."* Name the formats only for technical readers.
- **Limits:** static HTML, zips, React, Markdown, SVG, files; SSL, global delivery, search indexing, bot protection. No server-side code, databases or performance figures.

### ◆ Privacy controls
- **What it does:** add a password, limit who can see something, or show a warning before people enter.
- **Problem:** drafts, client previews and sensitive content aren't for everyone.
- **Benefit:** share with exactly the people you mean to.
- **Who & when:** students, agencies (client approvals), creators (previews).
- **Example:** an agency shares a campaign preview with its client behind a password before launch day.
- **Angle:** *"Keep private things private."*
- **Limits:** passwords, audience limits, content warnings. How audience limits work isn't specified. No security guarantees or compliance claims.

### ◆ The card (@)
- **What it does:** add @ before any public Cardsite link to see a neat summary card of it, suited to whoever's looking.
- **Problem:** a bare link says nothing about what's behind it.
- **Benefit:** a clean, at-a-glance preview of any page, ready to share.
- **Who & when:** students sharing projects, professionals sharing profiles, anyone sending a link to someone deciding whether to click.
- **Example:** card.site/alice is Alice's page; card.site/@alice is the summary she sends a recruiter.
- **Angle:** *"Your link has a card."* Show the @ in the copy.
- **Limits:** public links only (the approved line says "every URL"; see Open Questions).

### ◆ Workspaces for people & agents
- **What it does:** shared spaces where your team, and the AI agents you use, work on your content with the right access each.
- **Problem:** shared logins, unclear access, mistakes nobody can undo.
- **Benefit:** work together safely, with history and backups behind you.
- **Who & when:** agencies, teams, anyone using an AI assistant to manage content.
- **Example:** an agency gives each client a workspace, and each person gets only the access their role needs.
- **Angle:** *"Your team, your agents, the right access for each."* For early adopters: "Give your agent the tools to manage your presence" (approved).
- **Limits:** workspaces per plan 1 / 2 / 5 / 10 / unlimited. Don't name supported agents or describe permission levels.

### ○ AI drafting
- **What it does:** draft copy, assets and docs with AI right where they'll be published.
- **Benefit:** start from a draft, not a blank page, without switching tools.
- **Line:** *"Draft it where it'll live."*
- **Limits:** no model names or quality claims.

### ○ Payment links
- **What it does:** a link people can use to pay you. **Line:** *"Share a link. Get paid."*
- **Limits:** providers, fees and currencies are unknown, so don't state them.

### ○ Event pages
- **What it does:** a page for your event, shareable by link or QR code, easy to update.
- **Line:** *"Venue changed? Update the page, not the posters."*
- **Limits:** ticketing, RSVPs and calendar features are unknown.

### ○ Contact cards
- **What it does:** lets people save your details from a link or QR code. Say "contact card", not vCard.
- **Limits:** confirm the exact experience before featuring.

### ○ Files
- **What it does:** share a file at a short address instead of an attachment. **Limits:** counts toward storage.

### ○ Splash pages
Listed in the source with no description. Don't market them until their purpose is confirmed.

### ○ Links that don't vanish
- **What it does:** if you stop using Cardsite, your links aren't switched off overnight. You get several reminders, and your content stays readable at a backup address for a year.
- **Benefit:** peace of mind that what you've shared stays findable.
- **Where:** pricing FAQs, onboarding, reassurance for free users. **Line:** *"Your links don't disappear without warning."*
- **Limits:** follow the release rules in Product Facts exactly. Never say "never expire".

---

## Voice & Copy Rules

*How Cardsite sounds and the rules every line follows. Applies to all channels. [STRATEGY], except brand mechanics marked [FACT].*

### Voice

The approved copy already has a rhythm worth keeping: a short bold claim, then one plain sentence that makes it concrete ("**Short URLs people remember.** card.site/Demo-Q4-Review, not a string of characters."). Keep the rhythm, and move the content to the reader's side.

Cardsite sounds like a capable friend who's good with this stuff: clear, quick, a little warm, never showing off.

| We are | We're not |
|---|---|
| Clear: lands in one read | Clever at the expense of meaning |
| Concrete: menus, launches, links in bio | Abstract: "solutions", "experiences", "ecosystems" |
| Confident: says what it does | Boastful: "revolutionary", "the best" |
| Light: short sentences, room to breathe | Cute: a pun on every line |
| On the reader's side | Talking about our platform and our tech |

### Tone by moment

| Moment | Tone | Example |
|---|---|---|
| Homepage, ads | Confident, inviting | *Everything you share, in one place you control.* |
| Social | Relaxed, situational, a little humour | *Menu changed again? Your QR code doesn't care.* |
| Onboarding | Encouraging, step by step | *Pick an address. It's yours.* |
| Pricing | Straight, no tricks | *Start free. Add your own domain on Pro.* |
| Account notices | Calm, specific | *Your page at card.site/juno will be released in 7 days. Sign in to keep it.* |
| Agencies, partners | Professional, still plain | *Every client in its own workspace.* |
| Technical readers | Precise, still benefit-first | *Upload HTML, React or a zip. It's live on your domain with SSL.* |

### Rules

- **Start with them.** The first line is their outcome or their problem. Never open with "Cardsite is a platform that…" for a new reader.
- **One message per piece.** An ad, post or subject line carries one benefit.
- **Show, don't summarise.** A menu or a bio link beats "manage your presence across channels".
- **Benefit, then feature.** "Change the menu without reprinting. Dynamic QR codes update after printing." Not the reverse.
- **Use their words.** Menu, link in bio, flyer, launch, client.
- **Short and active.** Short sentences, strong verbs, more "you" than "we".
- **Specific beats superlative.** "Your own domain on Pro" beats "powerful custom branding".
- **Every claim traceable** to Product Facts.
- **No feature lists as headlines.** Lists come after the reader cares.
- **Read it as a stranger.** If they wouldn't see why it matters, rewrite.

### Terminology

| Internal term | Say instead | Internal term OK when… |
|---|---|---|
| slug | link, address | never in marketing |
| resource, artifact | page, link, file, site (name the thing) | never in marketing |
| custom slug | an address you choose | pricing tables may say "chosen addresses" |
| smart link, routing | one link that sends people to the right place | feature pages, explained once |
| gate, password gate | password-protect, keep private | — |
| audience-scoped visibility | choose who can see it | — |
| card view | the card, summary card | — |
| hosting, static HTML, React, zips | put it online, your site | technical and maker readers |
| SSL | secure | technical readers |
| global delivery, search indexing, bot protection | delivered worldwide, findable in search, protected from bots | technical readers, never as speed claims |
| analytics layer | see what's working, your stats | — |
| marketing pixels | your ad tracking | marketers and agencies say "pixels" |
| scoped privileges | the right access for each person | — |
| archive address, release | backup address; if you stop using Cardsite | help content and FAQs |

**Use consistently:** Cardsite (never CardSite or Card Site) · card.site/yourname (lowercase, no https or www) · the card · dynamic QR code (first mention; then QR code) · workspace · your own domain.

### Avoid

**Jargon** (unless the reader is technical and it helps): slug, resource, artifact, routing, gating, CDN, static, deploy, provision, scoped, layer, stack.

**Clichés, never:** unlock, supercharge, seamless, effortless, leverage, empower, elevate, revolutionize, game-changer, next-level, cutting-edge, best-in-class, robust, world-class, all-in-one solution, one-stop shop, reimagine, frictionless, magic, "digital presence" (outside the brand line), "Say goodbye to…", "Meet [feature]".

**Patterns:**
- Opening with the company or category name.
- Three abstract nouns in a row ("speed, simplicity and control").
- Feature lists as headlines.
- Unprovable outcomes stated as fact ("grow your audience", "boost sales", "save hours"). Frame them as what the reader can do instead: "see what grows your audience".
- Stacked rhetorical questions.
- Exclamation marks outside casual social.

### Brand mechanics

- **[FACT]** "Cardsite": one word, capital C. Cardsite® at first mention in any document; plain afterwards.
- For ads, social and in-app text where ® is impractical, follow legal's guidance (see Open Questions).
- Don't start a sentence with a lowercase address. Write "Your link: card.site/juno."
- Example addresses should be lowercase and hyphenated (card.site/ash-ceramics).
- Prices: "$25/month" in body copy, "$25/mo" in tables. Say "Free plan" or "Start free", never "free forever".

---

## Channel Guide

*How to write for each channel. The order of thought is always the same: who's reading → what they want right now → one benefit → one proof → one action. Facts stay within Product Facts; examples are [EXAMPLE]; check current platform character limits before publishing.*

### Homepage

**Job:** in five seconds, a stranger knows what Cardsite does for them and how to start.

**Shape:** hero (promise + one line + one CTA) → a visual of a real-looking address and what's behind it → the reasons to choose Cardsite as benefit blocks → who it's for (short scenarios linking to audience pages) → the card demo → "Start free" pricing teaser → closing CTA.

> **Everything you share, in one place you control.**
> Pages, links, QR codes, files and whole sites, at an address people remember. Update them anytime. See what's working.
> [Start free]

**Avoid:** "presence platform" as the hero, every content type above the fold, a row of headers that reads like a spec.

### Landing pages

**Job:** convert one kind of visitor with one problem.

**Shape:** problem-led headline → the moment it hurts → how Cardsite fixes it (one feature, shown) → two or three supporting benefits → the plan that fits → CTA.

> **Print your QR code once. Change the menu as often as you like.**
> Prices go up, specials change, the summer menu arrives. The code on your tables stays the same and always opens the latest version.
> **See who's scanning.** Know whether the code in your window gets used.
> **An address you can say out loud.** card.site/your-bakery fits on a chalkboard.
> [Make your QR code]

### Pricing page

Describe each plan by who it's for, then the numbers. *Purpose lines are [STRATEGY]:* **Free** try it out, one address of your own · **Starter** a few addresses and your own subdomain · **Pro** your own domain · **Business** teams and several brands · **Business+** agencies with many domains · **Enterprise** custom needs. Rename "custom slugs" to "addresses you choose", add "automatic links: unlimited within storage", and put the lifecycle reassurance in the FAQ. Verify every number before shipping.

### Search ads

Mirror what the person searched for in the first headline. One benefit. Write to the platform's limits.

| Search | Headlines | Description |
|---|---|---|
| qr code menu | *QR Code Menu You Can Update* · *Change the Menu, Keep the Code* | *Print your code once. Update the menu anytime. See how many people scan. Start free.* |
| link in bio | *One Link for Everything You Do* · *Your Name in Your Bio Link* | *A bio page at card.site/yourname. Add links, files and payments. See what gets clicks.* |
| host html site | *Put Your HTML Site Online* · *Host React, HTML or a Zip* | *Upload what you built. Your own domain, SSL and search indexing included.* |

### Social & display ads

Formula: a recognisable moment → the fix → CTA. The visual does half the work, so show the printed code, the bio link or the card.

> [Café table card with a QR code] *New menu. Same QR code.* Update what's behind it anytime. No reprinting. [Start free]

> [Phone showing a bio page] *Five things to share. One link in your bio.* [Claim your link]

### Print, outdoor, in-store

The product *is* a QR code and a short address, so put a real one on the ad, pointing at a page that demonstrates Cardsite. Headline of seven words or fewer, address readable from a distance.

> *This QR code can change its mind.* card.site/try *(illustrative; confirm availability)*

### Organic social

Post themes: **moments** each audience recognises · **tricks** (the @ card, one link for iPhone and Android) · **how-tos**, one task each · **made with Cardsite**, using only real, permitted examples and never fabricated ones. One idea per post, hook in the first line, light humour, no hashtag walls.

> *Your menu changed three times this year. Your QR code didn't have to.*

> *Tip: put @ in front of any public Cardsite link. card.site/alice → her page. card.site/@alice → its card.*

### Email

**Subject lines:** one benefit, specific, ideally under 50 characters. The preheader finishes the thought instead of repeating it.

| Subject | Preheader |
|---|---|
| *Your link is ready* | *Here's how to make it yours in two steps.* |
| *Print it once* | *Dynamic QR codes update after they're printed.* |
| *Which link actually worked?* | *Every click, scan and visit, in one view.* |

**Onboarding [STRATEGY]:** welcome and first win (choose an address, make something) → update something you've shared or make a QR code → check your stats → try the card → suggest an upgrade only when it fits their use (own domain, more addresses).

**Account notices** are operational, not promotional. Give the address, the date and the one action that keeps it. Mention the archive factually. Use no urgency beyond the real deadline.

> **Subject:** Your page at card.site/juno will be released in 7 days
> We haven't seen a sign-in or any visitors in a while, so on [date] this address will become available to others. Signing in before then keeps it yours. If it is released, your content stays readable at crd.site/juno for 12 months, and signing in during that time brings it back.

**Newsletters:** one story, one CTA. Not a digest.

### Launches & product announcements

**Shape:** what people can now do (never the internal feature name) → the problem it ends → how it works in one or two steps → an audience example → which plans and how to start.

> **Now your QR codes can change after they're printed.** Printed the wrong link? Menu changed? Point the same code somewhere new, and everyone who scans lands in the right place.

**Release notes:** *"You can now [do X], so [outcome]."* Technical detail goes on the second line.
**In-app:** one line, action-led. *"Add @ to see your card."* *"Want your own domain? Available on Pro."*

### Sales & partner material

Lead with client outcomes: separate workspaces, branded links on client domains, one view of results. Technical vocabulary is fine where it helps. Use the approved copy for the company description. No competitive claims or customer results until real ones exist.

### At a glance

| Channel | Room | Lead with | CTA |
|---|---|---|---|
| Homepage hero | Headline + one line | The core promise | Start free |
| Landing page | Full page | The audience's problem | Audience CTA |
| Search ad | Very little | The searched problem | Start free |
| Social ad | Visual + one line | A recognisable moment | Claim your link / Make your QR code |
| Print | ≤ 7 words + code | The trick itself | Scan / visit |
| Organic social | One idea | A moment or trick | Soft or none |
| Email | Subject + one story | One benefit | One button |
| Launch | Short article | What you can now do | Try it |
| In-app | One line | The next action | The action |

---

## Copy Bank

*Ready-to-adapt lines. [EXAMPLE] unless marked; all claims checked against Product Facts. Adapt them to the reader. Don't reuse one line everywhere.*

### Headline formulas

- **Change X, not Y:** *Change the menu, not the QR code.* · *Update the page, not the posters.* · *New launch, same link in bio.*
- **Outcome, constraint removed:** *Print once. Keep it current.* · *One link. Every destination.* · *Your own domain. SSL included.*
- **The moment:** *Five things to share. One link in your bio.* · *Menu changed again?* · *Sending a client a preview?*
- **You + verb + thing:** *Put your menu online.* · *Share your research without sharing everything.* · *Give every client their own space.*
- **The reveal:** *This QR code can change its mind.* · *Add @ to any Cardsite link.* · *Your link has a card.*
- **Plain promise:** *Everything you share, in one place you control.* · *Links people remember.* · *See what's working.*
- **Question → answer** (search, email): *Which post actually worked? Now you'll know.* · *Printed the wrong link? Fix it.*

### Subheads

- *Pages, links, QR codes, files and whole sites, at an address people remember.*
- *Point the same QR code somewhere new, even after it's printed.*
- *Every click, scan and visit, in one view.*
- *Add a password, choose who can see it, or show a warning first.*
- *Already built a site? Put it online at your own domain.*
- *One link sends each person to the right place for their phone, country or language.*

### Calls to action

General: *Start free* · Creators: *Claim your link*, *Make your page* · Local business: *Make your QR code*, *Put your menu online* · Students: *Make your first page* · Agencies: *See plans for teams*, *Set up a workspace* · Technical: *Upload your site* · Upgrade: *Use your own domain*, *Get more addresses* · Demo: *Try the card*, *See your stats*.

Lead with a verb and say what happens next. Avoid "Learn more" when there's an action to take; never "Submit".

### Brand lines & boilerplate

**[FACT]** Brand line: *Cardsite is a presence platform.* Descriptor: *Create, host, and share pages, links, QR codes, sites, files, and more in seconds.*

**Candidate taglines [STRATEGY, not approved]:** *One home for everything you share.* · *Everything you share, in one place you control.* · *Links people remember.*

**Short boilerplate [STRATEGY, needs approval]:** Cardsite® is a presence platform. Create, host and share pages, links, QR codes, sites and files at short addresses people remember, and see what's working.

**Medium boilerplate [STRATEGY, needs approval]:** Cardsite® is a presence platform. People use it to create, host and share pages, links, QR codes, sites and files in seconds, at short addresses on card.site or their own domain. They can update what they've shared, send each visitor to the right place, keep private things private, and see what's working in one view.

**Long:** the approved copy in Product Facts.

### One fact, many formats

The words change with the channel; the claim never grows.

**Dynamic QR codes change destination after printing**
- Homepage: **Print once. Keep it current.** Point the same QR code somewhere new, even after it's on the table, the poster or the packaging.
- Local business: *Print your QR code once. Change the menu as often as you like.*
- Search ad: *QR Code You Can Update* / *Change where it goes after printing.*
- Social: *New menu. Same QR code.*
- Events: *Venue moved? Update the page. The posters still work.*
- Agency: *Campaign QR codes you can re-point after the print run.*

**One analytics view across pages, links and QR codes**
- Homepage: **See what's working.** Every click, scan and visit, in one place.
- Creator: *Find out which post actually sent people to your shop.*
- Local business: *Is anyone scanning the code in your window? Now you'll know.*
- Agency: *One view of results across every page, link and QR code in a client's campaign.*

**Add @ to any public link to see its card**
- Homepage: **Every link has a card.** Add @ to any Cardsite link and see a neat summary of what's behind it.
- Student: *Send your supervisor the card, not a wall of links.*
- Professional: *card.site/@yourname: your page at a glance.*

**One home for pages, links, files, sites and QR codes**
- Creator: *Your shop, your newsletter, your latest video. One link in your bio.*
- Student: *Notes, projects and research, together and easy to share.*
- Agency: *Every client's links, pages, microsites and QR codes, each in its own workspace.*
- Technical: *Short links, bio pages, QR codes and HTML/React hosting under one set of addresses, including your own domain.*

### One feature, different readers

- **Passwords.** Student: *Keep drafts private until they're ready.* Agency: *Share client previews behind a password.* Creator: *Give early access to your inner circle.*
- **Own domain.** Local business: *yourbakery.com/menu. Your name, your menu.* Professional: *Every link you share, on your own domain.* Agency: *Run each campaign on the client's own domain.*
- **Smart links.** App maker: *One link. iPhone users to the App Store, Android users to Google Play.* Shop: *One link sends each visitor to the store for their country.* Creator: *One link, the right language for each listener.*

---

## Before & After

*Technical descriptions from the source, rewritten as marketing that makes the same claim and no bigger one. [EXAMPLE]. The "why" lines carry the lesson.*

**The product**
Before: *Every resource gets a slug; every slug can live on card.site, a subdomain, or a domain you own.*
After: **Everything you share, in one place you control.** Pages, links, QR codes, files and whole sites, at an address people remember, on card.site or your own domain.
Why: "resource" and "slug" are builders' words. Readers need to know what they can put there and why the address matters.

**Dynamic QR codes**
Before: *Dynamic QR codes whose destination can change after printing.*
After: **Change the menu, not the QR code.** The code on your tables keeps working when the menu changes.
Why: the before is accurate but leaves the reader to imagine the use. The after names the moment it matters.

**Smart links**
Before: *Smart links that send each visitor to a destination by device, location, language or rule.*
After: **One link. Everyone ends up in the right place.** iPhone users to the App Store, Android users to Google Play.
Why: a list of parameters becomes one case that makes the idea click.

**Hosting**
Before: *Host static HTML, zips, React, Markdown, SVG and files. Custom domains, SSL, global delivery, search indexing, bot protection.*
After, everyday reader: **Built it already? Put it online.** Upload your site and it's live at your own address, secure and findable in search.
After, technical reader: **Upload HTML, React or a zip. It's live on your domain.** SSL, global delivery, search indexing and bot protection included.
Why: same fact, two readers. Format names only for people who know them.

**Access controls**
Before: *Password gates, audience-scoped visibility, content warnings before entry.*
After: **Keep private things private.** Add a password to a draft, choose who can see a client preview, or show a warning before people go in.
Why: each internal concept becomes something a person would actually do.

**Analytics**
Before: *One analytics layer across pages, links and QR codes. Marketing pixels and campaigns managed centrally.*
After, creator: **Find out which post actually sent people your way.** Every click, scan and visit, in one place.
After, agency: **Every client's results in one view.** Pages, links and QR codes reported together, with pixels and campaigns managed in one place.
Why: "analytics layer" describes architecture. Readers want an answer to a question they already have.

**The card**
Before: *Add @ before the slug of any public Cardsite URL to see that resource as a summary card, rendered for whoever is looking.*
After: **Your link has a card.** Put @ in front of any Cardsite link: card.site/@alice shows a neat summary of Alice's page.
Why: show the trick with a real-looking address; the rendering details aren't the hook.

**Workspaces**
Before: *Workspaces shared with people and AI agents. Scoped privileges, version history, backups.*
After: **Every client in their own space.** Give your team, and the AI agents you work with, exactly the access they need, with version history and backups behind it all.
Why: "scoped privileges" becomes the outcome it gives people.

**Address lifecycle**
Before: *Free: 90 days with no sign-in and no visitor traffic triggers release. Notices at 30 days, 7 days, 3 days, 24 hours. Content served read-only at the archive address for 12 months.*
After (FAQ): **What happens if I stop using my free account?** As long as people are visiting your page, it stays put. If there's no sign-in *and* no visitors for 90 days, we'll remind you four times before the address is released. Even then, your content stays readable at a backup address (just drop the "a": crd.site/yourname) for 12 months, and signing back in restores it.
Why: told from the reader's side, the same rules become reassuring.

**Plans**
Before: *Pro — $25/mo. Custom slugs: 5. Subdomains: 3. Own domains: 1. Workspaces: 5. Storage: 10 GB.*
After: **Pro, $25/month. For your own brand, on your own domain.** 1 domain you own · 5 addresses you choose · 3 subdomains · 5 workspaces · 10 GB.
Why: a purpose line tells readers whether the plan is theirs before they compare numbers.

### Common failures

| Failure | Looks like | Fix |
|---|---|---|
| Documentation rephrased | "Cardsite lets you route visitors by device and location." | Name the situation: "One link. iPhone and Android users each land in the right store." |
| Internal words leaking | "Create a resource and assign a custom slug." | "Make a page and pick its address." |
| Feature dump | "Links, pages, QR codes, hosting, analytics, gates, workspaces and AI." | Lead with one benefit; list later. |
| Abstract promise | "Elevate your digital presence." | "Everything you share, in one place you control." |
| Invented outcome | "Grow your sales 3×." | "See which link people actually click." |
| Category opener | "Cardsite is a presence platform that…" as an ad headline | Lead with the reader's outcome; keep the brand line for boilerplate. |

---

## Open Questions

*What the source doesn't establish, and what to say until it's answered. [OPEN]. When one is resolved, move the answer into Product Facts (or Audiences, for research) and delete it here.*

### Product

| Question | Until answered |
|---|---|
| Can an ordinary short link be re-pointed after sharing, or only QR codes, redirects and smart links? (This decides how broad "Change it anytime" can be.) | Say it for QR codes, pages and redirects only. |
| What do "audience limits" mean in practice (sign-in, allow-lists, members, expiry)? | "Choose who can see it"; lead with passwords. |
| What can a smart-link "rule" be? | Mention device, location and language only. |
| Which analytics metrics exist (visits, referrers, locations, real-time, exports)? | "Clicks, scans and visits" only. |
| Which pixel providers and ad platforms are supported? | "Your marketing pixels"; name no platforms. |
| Which AI agents can join a workspace, and how? | Keep it general; lead with it only for agencies and early adopters. |
| What does AI drafting produce, and on which plans? | "Draft copy, assets and docs." |
| Payment links: providers, currencies, fees? | Say they exist; nothing more. |
| Events: RSVPs, ticketing, calendar? | Event pages + dynamic QR only. |
| What is a splash page? | Don't market it. |
| Can QR codes be styled or downloaded in print formats? | Don't mention it. |
| Does the card work on private links? Approved copy says "every URL". | Use "any public Cardsite link" in precise contexts; confirm the approved wording with legal. |
| Are features limited by plan beyond the published table? | Tie nothing to plans except the published limits. |

### Pricing

| Question | Until answered |
|---|---|
| Are August 2026 prices final ("subject to change before general availability")? | Confirm before any pricing copy; keep prices out of evergreen assets. |
| Annual pricing, discounts, trials? | Monthly prices only. |
| Is the Free plan permanent? | "Free plan" / "Start free"; never "free forever". |
| Paid archive "reserved until 3 years": from release, from lapse, or in total? | "Kept for you longer on paid plans" until confirmed. |
| What happens to domains and subdomains when a subscription lapses? | Don't address it in marketing. |

### Proof & claims

| Question | Until answered |
|---|---|
| Any real customers, quotes, case studies or usage numbers? | None. Use clearly illustrative scenarios only. |
| What does "in seconds" refer to? | Only within the approved descriptor. |
| Security or compliance certifications? | No compliance claims. |
| Any approved competitive positioning? | No competitor names or comparisons. |

### Brand & audience

| Question | Until answered |
|---|---|
| Does the ® rule apply to ads, social and in-app text? | Use it in documents, web pages and emails; ask legal about short-form. |
| Visual identity (logo, colors, type, imagery)? | Out of scope; request brand guidelines. |
| Are the candidate taglines and boilerplate approved? | Treat as drafts; use the approved copy where official text is needed. |
| Is there customer research behind the audience insights? | Use the hypotheses; test before scaling spend. |
| Which audience is the commercial priority? | Lead with "One home"; give each audience its own landing page. |
| Which markets and languages? | English, US pricing. |

---

## Keeping This Current

- **Product changes:** update Product Facts first, then the affected feature in Features → Value, then any Copy Bank lines that depend on it.
- **Answered question:** move the answer into Product Facts or Audiences, and delete it from Open Questions.
- **Validated strategy:** once something is tested, approved or researched, remove its [STRATEGY] label.
- **Precedence:** Product Facts decides what's true. Agent Instructions and Voice & Copy Rules decide how to say it, and technical source material never overrides them. Strategy gives way to a specific approved brief.
