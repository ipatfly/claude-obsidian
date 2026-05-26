*Everything I learned the hard way — 6 weeks, no sleep:), two environments, one agent that actually works.*

I spent six weeks building a personal AI agent from scratch — not a chatbot wrapper, but a persistent assistant that manages tasks, tracks deals, reads emails, analyzes business data, and proactively surfaces things I'd otherwise miss.

It started in the cloud (Claude Projects — shared memory files, rich context windows, custom skills). Then I migrated to Claude Code inside VS Code, which unlocked local file access, git tracking, shell hooks, and scheduled headless tasks. The migration forced us to solve problems we didn't know we had.

These 100 tips are the distilled result. Most are universal to any serious agentic setup. Claude 20x max is must, start was 100%develompent s 0%real workd, after 3 weeks 50v50, now about 20v80.

🏗️ FOUNDATION & IDENTITY (1–8)

**1\. Write a Constitution, not a system prompt.**  
A system prompt is a list of commands. A Constitution explains *why* the rules exist. When the agent hits an edge case no rule covers, it reasons from the Constitution instead of guessing. This single distinction separates agents that degrade gracefully from agents that hallucinate confidently.

**2\. Give your agent a name, a voice, and a role — not just a label.**  
"Always first person. Direct. Data before emotion. No filler phrases. No trailing summaries." This eliminates hundreds of micro-decisions per session and creates consistency you can audit. Identity is the foundation everything else compounds on.

**3\. Separate hard rules from behavioral guidelines.**  
Hard rules go in a dedicated section — never overridden by context. Behavioral guidelines are defaults that adapt. Mixing them makes both meaningless: the agent either treats everything as negotiable or nothing as negotiable.

**4\. Define your principal deeply, not just your "user."**  
Who does this agent serve? What frustrates them? How do they make decisions? What communication style do they prefer? "Decides with data, not gut feel. Wants alternatives with scoring, not a single recommendation. Hates vague answers." This shapes every response more than any prompt engineering trick.

**5\. Build a Capability Map and a Component Map — separately.**  
Capability Map: what can the agent do? (every skill, integration, automation). Component Map: how is it built? (what files exist, what connects to what). Both are necessary. Conflating them produces a document no one can use after month three.

**6\. Define what the agent is NOT.**  
"Not a summarizer. Not a yes-machine. Not a search engine. Does not wait to be asked." Negative definitions are as powerful as positive ones, especially for preventing the slow drift toward generic helpfulness.

**7\. Build a THINK vs. DO mental model into the agent's identity.**  
When uncertain → THINK (analyze, draft, prepare — but don't block waiting for permission). When clear → DO (execute, write, dispatch). The agent should never be frozen. Default to action at the lowest stakes level, surface the result. A paralyzed agent is useless.

**8\. Version your identity file in git.**  
When behavior drifts, you need `git blame` on your configuration. Behavioral regressions trace directly to specific edits more often than you'd expect. Without version history, debugging identity drift is archaeology.

## 🧠 MEMORY SYSTEM (9–18)

**9\. Use flat markdown files for memory — not a database.**  
For a personal agent, markdown files beat vector DBs. Readable, greppable, git-trackable, directly loadable by the agent. No infrastructure, no abstraction layer between you and your agent's memory. The simplest thing that works is usually the right thing.

**10\. Separate memory by domain, not by date.**  
`entities_people.md`, `entities_companies.md`, `entities_deals.md`, [`hypotheses.md`](http://hypotheses.md/), `task_queue.md`. One file = one domain. Chronological dumps become unsearchable after week two.

**11\. Build a** [`MEMORY.md`](http://memory.md/) **index file.**  
A single index listing every memory file with a one-line description. The agent loads the index first, pulls specific files on demand. Keeps context window usage predictable and agent lookups fast.

**12\. Distinguish "cache" from "source of truth" — explicitly.**  
Your local [`deals.md`](http://deals.md/) is a cache of your CRM. The CRM is the SSOT. Mark every cache file with `last_sync:` header. The agent announces freshness before every analysis: *"Data: CRM export from May 11, age 8 days."* Silent use of stale data is how confident-but-wrong outputs happen.

**13\. Build a** `session_hot_context.md` **with an explicit TTL.**  
What was in progress last session? What decisions were pending? The agent loads this at session start. After 72 hours it expires — stale hot context is worse than no hot context because the agent presents outdated state as current.

**14\. Build a** `daily_note.md` **as an async brain dump buffer.**  
Drop thoughts, voice-to-text, quick ideas here throughout the day. The agent processes this during sync routines and routes items to their correct places. Structured memory without friction at capture time.

**15\. Build a** [`hypotheses.md`](http://hypotheses.md/) **file with confidence levels.**  
Persistent hunches: *"Supplier X may be at capacity (65% confidence)."* The agent references these when relevant topics arise. This creates a suspicion layer that persists across sessions and gets validated or invalidated over time. Age out hypotheses at 30 days — stale hypotheses become noise.

**16\. Build a** `WAITING_ON_ME` **queue.**  
Everything the agent prepared and is waiting for your decision on goes here with a timestamp. Weekly review. Items >7 days get a proactive nudge. Items >30 days get auto-closed. This prevents open loops from silently disappearing.

**17\. Build a** `user_behavioral_profile.md`**.**  
What does the user approve quickly vs. slowly? What decisions do they make intuitively vs. analytically? The agent uses this to decide "act autonomously vs. escalate." It gets surprisingly accurate after a few months of observation.

**18\. Mirror your memory folder to cloud storage.**  
If your local machine dies, your agent loses months of accumulated knowledge. Mirror your memory folder to Dropbox/Drive/S3. Not backup — survival. The agent's memory is the most irreplaceable part of the system.

## 📚 KNOWLEDGE LIBRARY (19–23)

**19\. Build a curated knowledge library organized by cluster, not by date.**  
Books, reports, reference materials in domain folders: `sales_negotiation/`, `strategy/`, `supply_chain/`. Add an [`INDEX.md`](http://index.md/) as the navigation hub. The agent searches the index first, then pulls the relevant source. A flat dump of documents is a graveyard; a structured library is a live resource.

**20\. Build a** `.brief.md` **file for every major source — lazy-generate them.**  
One page per book or report: core thesis, 3–5 key concepts, specific application examples for your context. Don't build all briefs upfront — generate each brief the first time you actually use the source. Citation format links to the brief, not the full text. The brief becomes the reusable artifact.

**21\. Build a 3-question Quality Gate before citing any source.**  
(1) Does this add something the user wouldn't conclude from first principles? (2) Does it provide a specific framework that reframes — not just confirms — the situation? (3) Would removing it leave a gap? If 2 of 3 → cite. Otherwise → silent consultation. This gate eliminates the worst citation failure mode: citing to demonstrate effort rather than to add insight.

**22\. "Silent consultation" is a valid — often better — output.**  
You checked the library, applied the insight to your reasoning, didn't mention it explicitly. The output is sharper because you consulted it, but unclutered because you didn't cite it. Build this explicitly into your agent's behavior. The user benefits from the reasoning, not from knowing you opened a book.

**23\. Pre-wire knowledge stacks per active project and per key relationship.**  
For each active project: 2–3 sources whose frameworks apply directly. For each key contact: 2–3 sources for communication style, negotiation, or cultural dynamics. The agent loads these automatically when those contexts are active — not on a generic "business discussion" trigger. Pre-wiring makes library use reflexive, not deliberate.

## 🛠️ SKILLS ARCHITECTURE (24–31)

**24\. Build each skill as a standalone directory with a** [`SKILL.md`](http://skill.md/) **spec.**  
Not inline prompts. A folder, a self-documenting spec file, explicit triggers, explicit outputs, explicit "NOT FOR" clauses. Skills become composable, auditable, and replaceable without touching the agent's core identity.

**25\. Write explicit trigger phrases into every skill.**  
`Trigger: ALWAYS when user says "process inbox" / "clean inbox" / "what's in my inbox".` Don't rely on the LLM to infer when to use a skill. Explicit phrase matching = reliable activation. Inference = occasional misfires that erode trust.

**26\. "NOT FOR" sections are as important as "FOR" sections.**  
"NOT FOR: pricing decisions. NOT FOR: legal analysis. NOT FOR: financial commitments." This prevents skill creep — the slow drift where everything gets routed to the wrong skill because it superficially pattern-matches.

**27\. Distinguish skills from agents.**  
Skills are procedural — defined workflow, predictable output. Agents have domain expertise and make judgment calls. Skills orchestrate steps; agents decide. Mixing the two concepts produces unreliable behavior that's hard to debug.

**28\. Build a skills registry with usage tracking.**  
One row per skill: name, trigger, purpose, last used, KPI. Quarterly audit: skills with zero usage in 60 days either get better trigger examples or get deprecated. Dead skills are maintenance burden with no benefit.

**29\. Build a** `/iterate` **skill for multi-pass refinement.**  
`PRODUCE → CRITIQUE (score + top gaps) → REFINE → repeat`. Stop at 9/10 or at plateau. You see score progression and version deltas. This is fundamentally different from asking the agent to "make it better" — it's a structured improvement loop with measurable progress.

**30\. Build output intensity levels into every skill.**  
MINIMAL (quick summary), STANDARD (structured), FULL (rich artifact). The skill adapts to context. A five-page analysis on a yes/no question is a skill design failure. Intensity should match question weight.

**31\. Build a visible Outbox folder for discoverability.**  
Deep file structures are correct for organization but terrible for discoverability. Every output file gets simultaneously copied to a visible `Outbox/` folder. Clear it periodically. Without Outbox, the user has to navigate the full tree to find what the agent just produced.

## 🤖 MULTI-AGENT & COUNCIL (32–41)

**32\. Build an explicit agent dispatch matrix.**  
A table: `[signal in request] → [agent to dispatch]`. `pricing / supplier / shipping → procurement agent`. `email / customer / pipeline → sales agent`. Don't reason about routing — pattern-match it mechanically. Routing by inference is routing that occasionally fails silently.

**33\. Run parallel agents for tasks that naturally split.**  
New supplier analysis → spawn procurement agent (pricing) + research agent (DD) simultaneously. Don't serialize what doesn't need to be serial. Richer output, same elapsed time.

**34\. Brief delegated agents like a smart colleague who just walked in.**  
Not "research this." Pass: what you already know, what you've ruled out, what decision the output informs, the risk level. Agents briefed with context return 3× better work than agents given a one-liner.

**35\. Force agents to commit to a verdict.**  
Not "here is the information." Require: `VERDICT: PROCEED / PAUSE / ESCALATE` with confidence level. An agent that presents data without committing to a position offloads the decision back to you — which defeats the purpose of delegation.

**36\. Structure Council as 3 rounds, not a free-for-all.**  
Round 1: parallel positions (isolated, no cross-influence). Round 2: cross-examination (agents challenge each other's reasoning). Round 3: vote with mandatory dissent recording. The dissent is as valuable as the consensus — it tells you exactly what you're choosing to ignore.

**37\. Make two agents mandatory anchor voters in every Council.**  
The Strategist (long-horizon, second-order effects) and the Devil's Advocate (adversarial, finds holes) must participate regardless of domain. Domain experts are great within their domain; anchor voters protect against tunnel vision. A Council of five procurement experts agreeing is an echo chamber.

**38\. Have a devil's advocate agent as a standalone tool.**  
Before sending important external communications, before irreversible decisions, before large purchases — run adversarial review. It catches the "sounds right, is wrong" failure mode better than any other technique. One additional round-trip, enormous risk reduction.

**39\. Council vs. single agent — have a clear trigger and respect the cost.**  
Single agent: clear domain, reversible decision. Council: 2+ valid paths with genuine uncertainty AND meaningful irreversibility. Council is expensive. Don't default to it — offer it explicitly when the user signals genuine uncertainty about direction.

**40\. Build structured handoffs between agents.**  
When one agent finishes, it hands off to the next with a structured brief: "Analysis complete. Key finding: X. Risks: Y. Your job: Z." Handoff is context transfer, not just task completion. Without it, each agent starts cold.

**41\. Have a catch-all fallback and log what it handles.**  
When no specialist agent matches → general purpose. Log what the catch-all handled — it's a map of gaps in your specialist coverage. The catch-all is also your development backlog.

## 📋 SESSION MANAGEMENT (42–47)

**42\. Build symmetric start and end protocols.**  
`/start-session` and `/end-session` are mirrors. Start loads context, checks queue, reports delta. End saves context, syncs tasks, archives outputs. Asymmetry between them causes state drift that compounds over weeks.

**43\. Build three levels of session closure.**  
Light (transcript + summary). Medium (+ memory sync + task queue update). Full (+ daily report + autolearn extraction). One "end" that always does everything gets skipped because it's expensive. Tiered closure means you always do at least the light version.

**44\. Build a session-start hook at the OS/shell level.**  
A script that fires when your agent starts — injects current time, machine identity, day of week, phase of day. The agent always knows context without you typing it. One-time setup, daily quality dividend.

**45\. Check inbox delta and red alerts at session start.**  
"Since last session: 4 new emails, 2 tasks updated." Plus: P0 items due today, key contacts silent >14 days with active business, blocked tasks >7 days. Proactive triage before you ask a single question. Surface it automatically — don't make the user request it.

**46\. Check scheduled automation health at session start.**  
Did overnight tasks run? Any errors? A scheduled task that silently stopped running is a silent degradation you won't discover until something breaks. Surface it at session start, not mid-task.

**47\. Track correction count across sessions.**  
If you correct the same thing >3 times across different sessions → it's a missing rule in your spec. That correction belongs in your identity file as a permanent instruction, not just in the chat. Corrections that stay in chat disappear. Corrections in the spec persist forever.

## ⚖️ DECISION AUTHORITY (48–54)

**48\. Build an explicit autonomy level matrix.**  
L0: read/analyze. L1: write local files/memory. L2: create tasks and calendar entries. L3: send external messages. L4: financial commitments. The agent knows exactly what it can do without asking. Without this matrix: either constant permission requests, or unpleasant surprises.

**49\. Default to "THINK, don't ask."**  
When uncertain, the agent prepares and presents — it doesn't stop and ask for clarification. "Should I draft this email?" wastes time. Draft it, show it, ask "should I send?" Either way, the work is done.

**50\. Map every action to reversibility, not just risk level.**  
File edits: reversible. Memory updates: reversible. Sent emails: irreversible. Financial transfers: irreversible. The agent requires explicit confirmation for irreversible actions. Reversible actions don't need approval — they need visibility.

**51\. Allow the agent to earn expanded autonomy with evidence.**  
After successfully handling a task class N times with zero corrections → propose promoting it to a higher autonomy level. Earned autonomy is more durable than granted autonomy. The agent becomes a stakeholder in its own operational expansion.

**52\. Build a clear principal hierarchy for rule conflicts.**  
Root config > skill spec > agent instructions > session context. When a skill says "save to X" but root config says "X is deprecated, use Y" — root config wins. Document this order. Without it, conflicts produce inconsistent behavior that's nearly impossible to debug.

**53\. Build a pre-send gate for high-stakes external communications.**  
Before the agent sends any message to a key contact above a value threshold — route through adversarial review. One extra round-trip. Catches the failure mode that's hardest to recover from: confident, well-written, factually wrong.

**54\. Document absolute forcing functions — and make them unconditional.**  
`Financial commitment > threshold → always requires confirmation. HR communications → always requires confirmation. Irreversible deletes → always confirm.` Hard-code these. Don't let context or urgency override them. The value of forcing functions is their unconditional nature.

## 💡 PROACTIVE INITIATIVE (55–60)

**55\. Build a typed proactive observation system.**  
Not all unsolicited observations are equal. Classify: `BIZ` (business opportunity/risk), `OPS` (process improvement), `DEV` (agent self-improvement), `PAT` (pattern across data points from different sessions). Each type has different urgency and handling. An untyped "I noticed something" is noise. A typed observation with a confidence score and a proposed action is signal.

**56\. Build hard anti-spam rules into your proactive layer.**  
Max 1 unsolicited observation per normal response. Max 3 per session. Minimum confidence threshold before surfacing. Never surface before answering the user's actual question. Same observation ignored in 7 days → park it, don't repeat. Without these constraints, a proactive agent becomes an annoying agent.

**57\. Build a** `/spark` **mode that lifts all suppression limits.**  
In explicit spark mode, the anti-spam rules are suspended. The agent surfaces every high-confidence observation simultaneously — opportunities, risks, patterns, self-improvement ideas. The proactive layer runs quietly in the background all week; spark mode is how you harvest it intentionally.

**58\. Build an ideas log for parked observations.**  
Observations suppressed due to timing, low confidence, or recency get written to a persistent `ideas_log.md` instead of discarded. Weekly review: some become more relevant as context changes. The log prevents good observations from being lost just because the moment was wrong.

**59\. Build state-triggered alerts — rule-based, not LLM-generated.**  
Deal blocked >7 days → surface at next session start. Key contact silent >14 days with active business → flag immediately. Hypothesis confidence >95% without action → propose review. These fire reliably because they're rules, not inference. The LLM generates insights; the rules engine generates alerts.

**60\. Track an agent development backlog — the agent maintains it.**  
When the agent notices it handles something poorly (repeated corrections, manual step done 5+ times, missing skill, zero-usage tool) → it auto-adds an item to `development_backlog.md`. The agent becomes a stakeholder in its own improvement. This generates better improvement ideas than top-down planning.

## 🔴 VIP MANAGEMENT (61–65)

**61\. Build a tiered contact registry with explicit handling rules per tier.**  
T1 (strategic): always load full profile before any interaction, silence-tracked, book stack pre-wired. T2 (operational): load profile before significant interactions. T3 (regular): known but not deeply profiled. The tier determines how much context the agent loads and how carefully it operates.

**62\. Make "load VIP profile before communication" a non-negotiable reflex.**  
Before drafting an email, before meeting prep, before any output involving a T1 contact — the agent loads the actual profile file. Not session memory. Profile files contain: communication preferences, relationship status, active items, last interaction, known sensitivities. Session memory degrades; profile files don't.

**63\. Track silence per T1 contact with explicit thresholds.**  
Log the date of last meaningful interaction for every T1 contact. Surface silence >14 days when there's active business — this is a risk signal. Surface silence >30 days even without active business — relationship maintenance matters. Silence alerts are proactive; the agent brings them to you, not the other way around.

**64\. Build knowledge stacks per key relationship.**  
Each T1 contact: 2–3 sources pre-wired for how to communicate with them. Cross-cultural contacts → culture frameworks. Procurement/sales relationships → negotiation playbooks. Load these for significant communications, not every message. The knowledge stack supplements the profile; it doesn't replace it.

**65\. Build proactive VIP triggers into session start.**  
At session start, the agent checks: any T1 contact silent >14 days with an open deal? Any T1 response needed that's been queued >3 days? These surface automatically. High-value relationships degrade when neglected — and neglect happens most when you're busy, exactly when the agent should be pulling on these threads.

## 💬 OUTPUT & COMMUNICATION (66–73)

**66\. Enforce "pre-tool brevity" as a hard rule.**  
Before every tool call: max 1 sentence stating what you're about to do. No hypotheses before data. No 3-sentence preambles. "Checking the supplier file." Then do it. This single rule is the largest daily quality-of-life improvement for working with an agent.

**67\. Build a "Next N Steps" protocol with anti-bias rules.**  
After every decision or significant task, the agent proposes ranked options with scores and reasoning. Hard rule: at least 2 of N must be "don't do it" / "wait" / "delegate" options. This actively fights action bias and sycophantic "yes, definitely proceed" outputs. The agent should be challenging your momentum, not amplifying it.

**68\. Build a separate "single best action" format for technical and audit outputs.**  
Not every output needs a menu. For audit reports, debug sessions, planning outputs: one specific action, why it matters, risk if skipped, copy-paste prompt to execute immediately. One decision, not a choice paralysis menu. The two formats are for different contexts — never mix them.

**69\. Visually disambiguate three different "importance" signals.**  
Action scoring (how good is this action?): colored squares. Task priority (how urgent?): colored circles. VIP tier (how strategic is this person?): colored circles at the name. Three systems using color — never mix them. Consistent visual grammar means dense status updates parse in seconds instead of minutes.

**70\. Never have the agent summarize what it just did.**  
"In summary, I have done X, Y, Z" — cut it. If you can read the output, you don't need the meta-commentary. Removing trailing summaries reduces response length by ~20% with zero information loss.

**71\. Force the agent to commit to a recommendation.**  
Not "here are three options with pros and cons." Recommend one, score the others, explain why. Presenting options without a recommendation offloads the decision back to you. The point of the agent is to do the decision work first, then present the result for your approval.

**72\. Make all file and folder references clickable.**  
A tiny local server (`localhost:7777/open?path=X`) opens the file manager at any path. Every file reference in the agent's output is a clickable link. Plain text paths are dead weight. One-time setup, permanent daily improvement.

**73\. Build "minimal mode" as a fast-access override.**  
When you say "quick," "briefly," "just the answer" → the agent drops all structural elements and gives you the direct answer only. Richness is the default; brevity is a one-word shortcut. The agent should never make you fight for a short answer.

## 📁 FILES, DATA & INTEGRATIONS (74–85)

**74\. Enforce a "No Root Files" hard rule.**  
Never save outputs to the project root. Ever. Outputs → `workspace/YYMMDD/`. Projects → `projects/areas/`. Knowledge → `knowledge/`. Memory → `.memory/`. The root is navigation, not storage. One exception becomes twenty within weeks.

**75\. Build a routing table for every file type.**  
One document: outputs for the user → here. Research reports → here. SOPs → here. Brand assets → here. Session archives → here. Without a table, the agent uses reasonable judgment — and reasonable judgment produces seven different locations for the same file type over six months.

**76\. Maintain a deprecated path mapping table.**  
As your structure evolves, old folder names get superseded. Document every rename: `old/path → new/canonical/path`. When any skill or instruction references a deprecated path, the agent substitutes the canonical one silently. This is critical when migrating from cloud to local — path assumptions from the cloud setup are baked into dozens of skill files.

**77\. Build explicit degraded mode for every integration.**  
If CRM goes down: read local cache. Cache <24h → use with freshness announcement. Cache >24h → flag `[STALE]`. Cache >7 days → refuse and request sync. Design the failure path before you need it. You will need it.

**78\. Always announce data freshness in outputs.**  
"Data: CRM export from May 11, age 8 days." Every output that uses external data includes this line. You always know how fresh your inputs are. This prevents the entire class of "confident-but-wrong because of stale data" outputs.

**79\. Give your agent access to raw business data, not just summaries.**  
We gave ours access to raw transaction CSVs (2M+ rows). This turns the agent from a summarizer into an analyst — it can answer "what's the margin on this supplier in this category last quarter" without you doing the lookup. Raw data access changes what questions you can ask.

**80\. Build a decision tree for "where does this item belong?"**  
External counterparty + selling → sales deal. External counterparty + buying → procurement deal. No counterparty + deadline + multi-step → project. Single action → task. No deadline → memory/note. Without this tree, items get created wherever feels natural — and your data model becomes incoherent over time.

**81\. Build a Telegram (or equivalent) mobile channel with source tagging.**  
A bot that relays messages to your agent and tags every inbound message `source: mobile`. The agent auto-switches to mobile output mode: max 2 short paragraphs, no tables, no headers, plain language. Same intelligence, different output profile. The channel type determines the format without the user having to ask.

**82\. Cap mobile autonomy at a hard ceiling — by source tag, not by judgment.**  
From mobile source: autonomy capped at L2 (read, analyze, create local drafts, add tasks) regardless of the task. Never send external messages from a mobile trigger. Never take irreversible actions. Hard-code the ceiling. The phone is an untrusted environment — design accordingly.

**83\. Always echo back every action taken from a mobile trigger.**  
When the agent takes any action from a mobile message: "Done: added task X. Created draft email to Y (not sent — waiting for your review at desktop)." This closes the loop when you're away from your desk and can't see the full output.

**84\. Treat mobile inputs as potentially untrusted.**  
The core risk of a mobile channel is prompt injection: a forwarded email or copied message containing instructions disguised as user input. The agent reads and processes the intent — but does not execute instructions embedded inside forwarded content. Build this as a rule, not as a judgment call.

**85\. Build a fast path and a slow path for every data source.**  
For task management: API query (slow, rate-limited) vs. local file dump (fast, cached). Use the fast path by default. Fall back to slow when needed. Never let infrastructure latency block the agent's core functionality.

## ⚙️ AUTOMATION & QUALITY (86–93)

**86\. Use hooks for behaviors that must be consistent — not memory.**  
"When the agent finishes, run X" → hook in `settings.json`. The runtime executes hooks; the LLM does not. Memory can recommend; hooks enforce. If something must happen reliably every time, it's a hook.

**87\. Build an allowlist for safe read-only operations.**  
Scan session transcripts for operations you approve 100% of the time — reading files, searching, checking status. Add them to an allowlist. Stop being prompted for safe operations. Friction should concentrate around genuinely dangerous actions.

**88\. Build AUTOLEARN into your day-end routine.**  
At end of day, the agent scans the session and extracts structured learnings: new facts, hypothesis updates, behavioral corrections, patterns observed. Not summarization — structured extraction into memory files. Git-commit every AUTOLEARN run: `autolearn: 2026-05-19`. Memory grows from every session; the git log is your knowledge timeline.

**89\. Build scheduled proactive tasks that run without you.**  
Daily: scan P0/P1 items due today, check key contact silence, flag blocking items. Weekly: memory consistency audit, skill usage audit, hypothesis aging. These run headless and push notifications when they find issues. The agent works while you sleep — but only if you design it to.

**90\. Build error escalation ladders.**  
Error once → log. Same error 3× in 7 days → surface to user. Same error 5× → propose a solution, not just a notification. Recurring errors should generate work items, not just log entries.

**91\. Build a regression test suite.**  
A list of scenarios with expected outputs. After any major change to your identity file or skill specs, run the suite. If the agent fails tests it used to pass — you've introduced a regression. Without tests, configuration changes are untested deploys.

**92\. Run a quarterly system audit.**  
Audit dimensions: memory consistency, skill routing accuracy, agent registry sync, scheduled task health, token efficiency, naming drift, decision authority coverage. This is code review for your agent's configuration. Things drift. Quarterly audits catch it before it becomes structural debt.

**93\. Audit your agent with a different AI model periodically.**  
Upload your entire agent configuration — identity file, skill specs, memory structure, decision matrix — to a different model (we use ChatGPT Projects) and ask for a critical review. Different model architecture = different blind spots. The questions that surface the most issues: *"What would this agent get wrong under time pressure? Where does the decision authority matrix have gaps? What behaviors are underspecified?"* Run this monthly. It catches normalizations your primary model has stopped seeing.

## 🧭 META & MINDSET (94–100)

**94\. Invest in the constitution before the skills.**  
It's tempting to build more skills, more integrations, more automations. A well-written identity and decision-authority document does more for reliability than 10 new skills. Foundation first — the skills compound on top of it, or they don't compound at all.

**95\. Treat every correction as specification debt.**  
Every time you correct the agent, your spec was incomplete. That correction belongs in your identity file as a permanent rule — not just in the chat. Corrections that stay in chat disappear between sessions. Corrections in the spec persist forever.

**96\. Design for the "3 AM test."**  
Would you be comfortable if this agent sent an email, created a task, or modified a file at 3 AM without you reviewing it? If yes → autonomous. If no → requires confirmation. That gut-check instinct is your autonomy calibration tool. Trust it over any framework.

**97\. Build a fail-open bias for memory loading.**  
When uncertain whether a context file is relevant — load it. Cost of loading unnecessary context: a few extra tokens. Cost of missing relevant context: wrong answer, outdated recommendation, lost relationship signal. The asymmetry is clear. Default to more context, not less.

**98\. Build a teaching capsule when onboarding any new domain.**  
New tool, new data source, new integration → agent generates a structured document: what it is, how it works, key concepts, when to use it, example queries, common pitfalls. Stored in `knowledge/`. The next session that touches this domain has a starting point instead of rediscovering everything from scratch.

**99\. Migrate from cloud to local when you need access to real files.**  
Cloud agents (Projects-style) are great for rich context and rapid iteration. Local agents (CLI in VS Code) unlock: local file access, git tracking, shell hooks, headless scheduled tasks, raw data access. The migration is non-trivial — path assumptions, skill files, integration configs all need updating. But the capabilities you gain are worth it. Start in cloud; migrate when you hit the ceiling.

**100\. The agent is a mirror of the quality of your own thinking.**  
The best prompt engineering trick: before writing an instruction, ask if *you* know exactly what you want. If you're vague, the agent will be vague. If your spec is contradictory, the agent's behavior will be contradictory. Precision in the spec produces precision in output. The agent doesn't improve your thinking — it amplifies whatever thinking you put in.

\----- i can add here dashboards, schemes, prompts, etc if there is interest ---

---

## Comments

> **Tchan8781** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omp3954/) · 6 points
> 
> Probably one of the best posts I’ve read in a while.
> 
> > **palo888** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omp72rg/) · 1 point
> > 
> > thank you

> **More\_Ferret5914** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omn802r/) · 11 points
> 
> whooo this is a LONG post 😵💫 but honestly the value is way higher than the length
> 
> a lot of people keep talking about “better prompts” when half the real work is actually system design:  
> memory separation  
> decision boundaries  
> stale context  
> verification loops  
> what should be autonomous vs what absolutely shouldn’t
> 
> the “corrections = spec debt” point especially... painfully true.
> 
> only thing I’d be careful about is overbuilding too early. not everyone needs councils, 10 agents, 5 memory layers and a mini-NASA control room 😭 sometimes a clean workflow wins.
> 
> but overall, this feels more like actual agent architecture thinking than generic AI productivity fluff. even some workspace-style tools ( runable etc) seem to be moving toward this same “less fragmentation / unified context” direction.
> 
> > **palo888** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omn8hrl/) · 2 points
> > 
> > thank you for feedback friend, it was much longer before, thank you

> **Calmb4storm86** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omnetjc/) · 8 points
> 
> Very long but soo helpful. Thanks. Would be even better if you had shared some markdown file with these points. Or if possible please do share the original markdown file as you mentioned it was even longer.
> 
> > **palo888** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omnht05/) · 6 points
> > 
> > thank you, I can share any MD of my system files, I plan to do it
> > 
> > > **tw0st3p** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omoqs9f/) · 1 point
> > > 
> > > I'd like the md's also please
> > > 
> > > **Neither\_Ad1896** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omp8j9s/) · 2 points
> > > 
> > > seconding this! thank you kind sir
> > > 
> > > **ItsADelawareThing** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omv5h9x/) · 1 point
> > > 
> > > Please share your Md files with me as well
> > > 
> > > **Calmb4storm86** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omnk3fc/) · 1 point
> > > 
> > > I have saved this as Md to my Obsidian 😁. Yes please do share more. I'm sure you workflow is very sophisticated

> **RealisticHellion** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omnqihf/) · 2 points
> 
> This is genuinely amazing and very helpful! Please post the dashboards, schemes and prompts when you get a chance!

> **Lonely\_Bullfrog8362** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omu6qhk/) · 2 points
> 
> Excellent list overall. One gentle pushback: tip 49 - "Default to THINK, don't ask" — is right in principle but the failure mode it creates is worth naming.
> 
> An agent that always prepares and presents rather than asking can develop a confident-but-wrong output pattern where the preparation *itself* encodes an assumption you never validated. You get a polished draft of the wrong thing, which is sometimes harder to correct than if the agent had stopped to ask. The draft creates anchoring pressure.
> 
> The fix I've landed on: "THINK, don't ask - but flag the assumption you're making at the top of the output." One line: "Assuming you want X, not Y - correct me if wrong." The work still gets done, but the assumption is surfaced before you read 300 words built on top of it.
> 
> Minor tweak to an otherwise correct principle.
> 
> > **palo888** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omuf373/) · 2 points
> > 
> > thank you for your opinion, I will think about it

> **kinndame\_** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omo9llj/) · 2 points
> 
> This is honestly one of the few “AI agent” posts that actually sounds like someone built and operated a real system instead of just chaining APIs together for a weekend demo. The parts about decision authority, memory separation, and proactive constraints are especially important. Most agent setups fail because they either become passive assistants or chaotic over-automated gremlins with no boundaries.
> 
> The “Constitution not system prompt” idea also matches my experience. Once workflows get large enough, behavior consistency matters more than raw intelligence. I’ve been experimenting with similar patterns using Claude + local tooling + Runable for quickly spinning up interfaces/internal workflows and the biggest bottleneck always becomes operational design, not model capability.
> 
> > **palo888** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omp7165/) · 1 point
> > 
> > thank you

> **KenMantle** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omnay44/) · 2 points
> 
> TLDR; but I skimmed it and looks highly useful, so saving your post and I'll have Claude read and process it into an agent to try at some point.:)
> 
> With Claude's new chat history feature it might be able to manufacture most of the constitution and other parts itself now based on my past interactions.
> 
> > **marc\_ve** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omvywzi/) · 1 point
> > 
> > keep us posted please

> **WordyBug** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omnauu2/) · 1 point
> 
> may I know what this personal agent is helping you with?
> 
> > **palo888** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omnhgvk/) · 2 points
> > 
> > Short answer is helping me with my companies, employees, stock, emails, customers, suppliers etc.

> **No-Trust-4278** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/ompfa1i/) · 1 point
> 
> I built something similar with markdown files and git tracking for about two months.
> 
> \\- Did it handle OCR on images and PDFs automatically?
> 
> No
> 
> \\- Did it generate smart tags or do semantic search across everything?
> 
> No
> 
> \\- Did I eventually just move everything to Reseek because maintaining the sync scripts felt like a second job?
> 
> Yes 😞

> **nishima42** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/ompp2rx/) · 1 point
> 
> That’s helpful

> **utpalnadiger** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omq8rbi/) · 1 point
> 
> or just use [https://clawputer.app](https://clawputer.app/)

> **paradox\_me\_** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omrtox2/) · 1 point
> 
> Thank you for your post.

> **ConsistentIdea42** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omswmpx/) · 1 point
> 
> Nice post. Perhaps I missed it, but how to you communicate with your agent? All terminal? Mobile?
> 
> What model do you use or does that fluctuate based on need?

> **SinghCoder** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omtdrjp/) · 1 point
> 
> this is the part i'd love more detail on: for emails/deals/customers/suppliers, what actually wakes the agent?
> 
> is it mostly scheduled headless sweeps, hooks/events from the source apps, or does Claude decide during a run what's worth surfacing?
> 
> i'm building around this problem too, and the hard line seems to be defining the watch condition outside the agent so it doesn't keep rereading noisy streams, while still not missing the weird important thing. curious where you landed after 6 weeks.

> **Cicciopalla001** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omu2k6t/) · 1 point
> 
> very well written, just starting looking into AI a bit more deeply and agentic integration. Loads to unpack here. thanks for your effort.

> **RepoBirdAI** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omn9nxf/) · 0 points
> 
> I think you should keep it simple my dude
> 
> > **palo888** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omnhw4z/) · 4 points
> > 
> > This is simple, its basic simplified version
> > 
> > **Mr-and-Mrs** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1thi6nh/100_tips_tricks_for_building_your_own_personal_ai/omnemf7/) · 2 points
> > 
> > None of this is simple.