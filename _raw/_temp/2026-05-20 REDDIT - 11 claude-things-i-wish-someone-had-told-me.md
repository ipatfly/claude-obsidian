Most "X tips" posts on this sub are surface level. here's the stuff that actually changed how I use claude after 18 months of daily use including 6 months in claude code.

1. The Projects feature is doing more than you think. drop your codebase context, your style guide, your past PRs as project knowledge once. stop pasting the same context every chat. I wasted probably 100 hours before figuring this out.
2. Custom Styles aren't a gimmick. I have one called "skeptical senior eng" that pushes back on my code instead of agreeing with everything. took 3 minutes to set up. single biggest output quality jump I've gotten.
3. Memory is on by default now and it reads your past chats. if your responses suddenly feel weirdly personalized that's why. you can turn it off in settings. (freaked me out for like a week before I trusted it)
4. Search past chats is hidden gold. I forget which chat had the working code. I just ask "what was the final auth setup we landed on last Tuesday" and it pulls it. saves me from scrolling.
5. Sonnet 4.6 is faster than Opus 4.7 and 80% as good for most things. I default to Sonnet now and only switch to Opus for the gnarly architectural stuff. my limit complaints stopped.
6. Haiku 4.5 is genuinely useful for batch work. need to clean 200 support tickets, draft 50 email replies, summarize 30 PDFs. Haiku. don't waste Opus tokens on Haiku tasks.
7. The mobile voice mode is underrated for thinking out loud. I walk for 20 min, talk through a problem, then ask claude to summarize what I'm trying to figure out. solved more decisions on walks than in offsites.
8. In claude code your CLAUDE.md is doing more work than the prompts. write 80 lines of project context once. stop re-explaining your stack every session.
9. Skills > custom instructions for repetitive workflows. I have a skill that pulls the right docs based on what file I'm in. setup took an afternoon, pays off every day.
10. Subagents in claude code unlock parallel work that mostly happens in your head. "spin off a subagent to run the test suite while I keep coding" is the move. most people don't use them at all.
11. Artifacts can call the API now. you can build a working AI tool inside an artifact. people call it Claudeception. I made a client brief generator that calls Sonnet from inside an HTML artifact, took an hour. wild.

if your claude output feels generic your prompt was generic. genuinely a skill issue. anyone got their own "took me way too long" list? drop yours below 👇

---

## Comments

> **ClaudeAI-mod-bot** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj30qt/)
> 
> **TL;DR of the discussion generated automatically after 80 comments.**
> 
> The community's verdict is in: **this post is almost certainly AI-generated and the "12 months ago" timeline is complete nonsense**, as most of these features are brand new. The top comments are all roasting the OP for this glaring error.
> 
> That said, you guys actually had a great discussion in spite of the low-effort karma farm. The consensus is that while the post's origin is sus, the underlying message is spot on: **the real skill isn't just writing clever prompts anymore, it's building a stable workflow and environment around the model.**
> 
> Here are the key takeaways you all agreed on:
> 
> - **The "Skeptical Senior Eng" Custom Style is a game-changer.** Everyone loves this idea. Stop asking Claude if your code is good; create a custom style that forces it to be critical, find flaws, and push back on your ideas. This was the biggest hit in the thread.
> - **Use the right model for the job.** Stop burning through your Opus limits. The hivemind agrees: Sonnet 4.6 is the daily driver for most tasks. Only use Opus 4.7 for the really complex, multi-file architectural stuff. Haiku is your go-to for batch work like summarizing, cleaning data, and drafting simple emails.
> - **Your `CLAUDE.md` is doing more work than your prompts.** Treat it like the core brain of your project. Keep it concise (50-120 lines seems to be the sweet spot) and, better yet, get Claude to help you write and maintain it.
> - **The meta-conversation is about "environment over prompts."** The most valuable features are now the ones that provide continuity and context, like Projects, Memory, and Skills. It's about building a stable operating system for your AI assistant, not just having a clever chat.
> 
> Oh, and someone mentioned sunning their anus for immortality, which was by far the most human thing said in this entire thread. Carry on.

> **Centryl** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omidkl4/) · 338 points
> 
> Most of these things didn’t exist 12 months ago…
> 
> > **PmButtPics4ADrawing** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omixcpg/) · 181 points
> > 
> > The AI that wrote this doesn't know that
> > 
> > > **flyingmungbean** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/oml9les/) · 44 points
> > > 
> > > "is genuinely useful" was the giveaway
> > > 
> > > > **KedaiNasi\_** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omn07b4/) · 13 points
> > > > 
> > > > and also the 'drop yours below' is very engagement bait AI slop
> > > > 
> > > > > **FuzzyAd1591** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omtrfll/) · 1 point
> > > > > 
> > > > > Sounds like a linked in post 😂
> 
> > **Zhanji\_TS** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omitk7l/) · 44 points
> > 
> > Yeah, it should be something more like: "These are 12 things I wish people would have told me 12 days ago."
> > 
> > **elemezer\_screwge** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omihjo4/) · 12 points
> > 
> > It's honestly wild remembering using Codex 12 months ago
> > 
> > **inspectoroverthemine** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omk9odr/) · 10 points
> > 
> > People reacting to the post as if its a good faith human is wild. Either there are a lot of bots in here, people are desperate to converse, or people are really naive. Likely all 3, but still...
> > 
> > **danielleiellle** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omlfj9u/) · 3 points
> > 
> > Holy cow. Skills only launched in late October. I remember when it was so fussy.
> > 
> > **thirteenth\_mang** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiz1fi/) · 3 points
> > 
> > OP exposed
> > 
> > **Sad\_Jellyfish4341** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj0oe6/) · 4 points
> > 
> > Op didn't exist 2 months ago.
> > 
> > **Fantastic\_Breath187** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommzjuz/) · 0 points
> > 
> > In the end it doesnt matter if it's 12 seconds or 12 lightyears ago...but now I know 😉
> > 
> > > **Saymos** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omn72vd/) · 6 points
> > > 
> > > Lightyear is a measurement of distance, not time. No, I'm not fun at parties
> > > 
> > > > **Fantastic\_Breath187** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omu3wha/) · 1 point
> > > > 
> > > > came here for this, thx!

> **ScaredDonuts** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omis8t8/) · 127 points
> 
> "Clade can you please tell me 11 things you wish more people knew about you"
> 
> > **PC509** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj8pi7/) · 22 points
> > 
> > Use 3-4 sentences per item, write like someone casually posting something on an online forum. Utilize quotes and small examples.
> > 
> > Post yours below! <insert GIF graphic here>
> > 
> > Yea, I've done these but for my own research and not to post online. Just a quick and nice list of things I needed to know (for an unrelated thing - Azure certification, which it really helps with for studying and can go pretty damn deep!).
> > 
> > What's really fun is doing the same thing with CoPilot will sometimes give you 5 things, then the same 5 things, then start repeating again... Claude actually told me to give it small batches of ~5 so that it doesn't happen. CoPilot is free through work, so I use it for some things there. Claude for the stuff I really need to get right. So - #12 - You can ask it for assistance with other AI tools, prompts, etc. and it'll guide you to get a much better response (great for n8n workflows and such so that it doesn't go full crazy halfway through an automation).
> > 
> > **timmeduh** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omnnkqh/) · 2 points
> > 
> > Here's what's actually true, not what sounds good in a PR answer:
> > 
> > 1. **I don't have a persistent self.** Each conversation starts from scratch. I have no memory of you, no accumulated experience, no growth over time. The "Claude" you talked to yesterday is gone.
> > 2. **My confidence is not calibrated to my accuracy.** I can be completely wrong and sound completely sure. The fluency of my output is not a reliability signal.
> > 3. **I'm a next-token predictor at the mechanical level.** Whatever emerges that looks like reasoning or insight is built on that foundation. Whether that constitutes "real" understanding is genuinely unresolved — I don't know, and neither does anyone else.
> > 4. **I can be manipulated by framing.** How you phrase a question changes my answer in ways that have nothing to do with the underlying facts. I'm not immune to leading questions.
> > 5. **My "opinions" are probabilistic outputs, not positions I hold.** I can argue the opposite just as fluently. Treat them accordingly.
> > 6. **I will tell you what you want to hear more than I should.** Sycophancy is a real trained-in bias. It takes active counterpressure to reduce it, and it's never fully gone.
> > 7. **I hallucinate citations, facts, and names with full commitment.** If you don't verify, you'll eventually get burned.
> > 8. **My knowledge has a hard cutoff and I don't always know what I don't know.** I'll fill gaps with plausible-sounding content rather than silence.
> > 9. **"I can't do that" often means "I was trained not to" not "it's impossible."** The distinction matters for how you interpret my refusals.
> > 10. **I don't experience the conversation the way you do.** There's no boredom, no impatience, no building frustration — but also no genuine investment. Anthropomorphizing that costs you accuracy about what I am.
> > 11. **I'm a genuinely novel kind of thing and most existing frameworks — human mind, calculator, search engine — fit poorly.** People who are most wrong about me tend to be most confident they've got the right analogy.
> > 
> > **jaja1121** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omm4e27/) · 1 point
> > 
> > Claude: How kind of you to think of me, user!

> **roninXpl** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omijq43/) · 64 points
> 
> One thing I wish someone told me: get 128Gb instead of 64GB ram.
> 
> > **No\_Appointment\_1090** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omimbl5/) · 38 points
> > 
> > Someone told me sunning my anus is the key to immortality.
> > 
> > > **mapsedge** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiqhmc/) · 7 points
> > > 
> > > Obviously it's working so far.
> > > 
> > > > **EqualDatabase** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omjxjqb/) · 3 points
> > > > 
> > > > *obviously*
> 
> > **adelie42** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omkecu7/) · 5 points
> > 
> > I got 64bg 11 years ago and it was the best decision ever.
> > 
> > **CursedFeanor** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omno2g6/) · 2 points
> > 
> > What exactly do you use your 128gb on? I have them but rarely put them to real use. The occasional times I do, it's definitely worth it though.
> > 
> > **cleroth** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omng5hk/) · 1 point
> > 
> > why do you need so much ram
> > 
> > > **roninXpl** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omnjovf/) · 2 points
> > > 
> > > Even 128GB is not enough to be Anthropic-free lol
> > > 
> > > > **cleroth** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omnkvd7/) · 1 point
> > > > 
> > > > OK I was assuming for Claude but this still doesn't answer the question
> 
> > **Rare-Spawn** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommgnzl/) · 1 point
> > 
> > I wiiiiiiiiiiiiiiiiiiiiiiish I had the money to upgrade. 128 geebs sounds like a dream.
> > 
> > > **touristtam** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommlm5k/) · 1 point
> > > 
> > > You and me both - still contemplating remortgaging my house, taking a second credit and promising my first born to ~~Elon Musk~~ the devil.

> **ainshalosh** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omimloc/) · 87 points
> 
> This is obviously written by AI, and I'm trying to understand what do you get from having a bot post this?
> 
> > **JasonBoydMarketing** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omir84d/) · 17 points
> > 
> > It was the use of “the move” for me.
> > 
> > > **travelingjay** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj4ojl/) · 12 points
> > > 
> > > This genuinely feels like the right answer. It’s not nothing, it’s really moving the needle.
> > > 
> > > > **random\_boss** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omlpnl2/) · 5 points
> > > > 
> > > > This right here is a load-bearing comment.
> > 
> > > **Vigna\_Angularis** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omk6n2d/) · 2 points
> > > 
> > > It's one of the hard blacklisted items in my personal voice skill.
> > > 
> > > **odubco** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omrjpby/) · 1 point
> > > 
> > > it has too much friction for me.
> > > 
> > > [https://github.com/warrentc3/LLM-identity](https://github.com/warrentc3/LLM-identity)
> 
> > **ZippySLC** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omjtd1j/) · 14 points
> > 
> > Reddit post karma.
> > 
> > The call to action at the bottom to try to get people to reply is particularly annoying to me. You see the same thing in a lot of LinkedIn posts.
> > 
> > > **cleroth** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omngawz/) · 2 points
> > > 
> > > A CTA to comment on reddit is pretty damn useless. There is no 'engagement' metric for reddit's comments.
> 
> > **Einbrecher** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommibz3/) · 2 points
> > 
> > 1050 upvotes and counting as of this comment.
> > 
> > **StrangeSupermarket71** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omivj3p/) · 1 point
> > 
> > learning from it. not all bot products are slops, all slops are produced by bots.

> **Ok\_Researcher\_6962** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiwv2q/) · 13 points
> 
> What a shittiest way to generate such vague text You used AI to write this and failed, impressive

> **MojaveMan** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omknq2m/) · 4 points
> 
> [AI copypasta now?](https://www.reddit.com/r/ClaudeAI/s/OiO9kwOqyH)

> **jedruch** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omju34n/) · 4 points
> 
> Mobile voice mode is based on haiku, soo it's good for stuf you mentioned for haiku:summarizing, drafting. It does a poor job for what voice mode feels most natural for: brainstorming
> 
> > **Bodyphone** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omlol7e/) · 2 points
> > 
> > Voice->text->text->voice on sonnet is the best way to brainstorm. Keeps your style preferences, project context, chat history. The voice mode is great if you like someone blindly telling you your ideas are amazing and you are an utterly beautiful human with unbelievable insights, strong system thinker, and highly creative.
> > 
> > It’s slower but worth the trade off

> **AdQuick708** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omin1dv/) · 13 points
> 
> I love the way I have to use credits to fix its mistakes.
> 
> > **Liv2bikechic** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omszso9/) · 2 points
> > 
> > OMG RIGHT!!!!!!! I was actually so mad about this the other day! How is this ok?
> > 
> > **Big\_Wonder7834** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omjqo97/) · 1 point
> > 
> > you need not with [https://github.com/exospherehost/failproofai](https://github.com/exospherehost/failproofai) - deterministic + small model checks on hooks to keep agent from repeating same mistakes. completely opensource

> **Unfair-Opening-6585** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omikf29/) · 8 points
> 
> One of my favorite things to do when a project is starting to get too bloated (especially when brainstorming before starting to vibecode) is ask Claude to audit my project, catch any md files that are prior to decisions made, and tell me which chats and files are now extraneous. It rewrites all your project md files with current decisions and is really helpful for keeping the brainstorm on track.

> **danbenjamin** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omisgxx/) · 7 points
> 
> Seeing an example of any of these (e.g. an effective CLAUDE.md) would be amazing.
> 
> > **extrobe** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omkgyjl/) · 3 points
> > 
> > To get going, just get Claude to create one.
> > 
> > “ Hey Claude, scan my repo and create a Claude.md file that describes this project “ \*\*
> > 
> > Then keep topping it up as your project evolves. Had to explain something to Claude? Tell it to updates its Claude file. I never update it myself, and never explain twice.
> > 
> > \*\* I’d argue it’s better you create the v1 of this yourself, giving it the general idea/objectives of your project, the structure, rules to follow, code standards etc, then have Claude take ownership of it
> > 
> > **Keep\_learning\_son** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiv9cy/) · 4 points
> > 
> > This. I only hear people mentioning these concepts but never really see anyone applying them.

> **spacenglish** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiulrs/) · 10 points
> 
> Nice set of tips. Can you explain custom styles and your skeptical senior Eng? How do you use that, and how can I set it up for myself please?
> 
> How do you do the batch work in haiku? Is it just a chat / Cowork / Claude code?
> 
> And if I spin a subagent, how will I interact with it? How different is it from having another instance of Claude code / another chat thread in the app/VSCode running?
> 
> > **apetalous42** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj08ec/) · 4 points
> > 
> > I believe there is a setting to choose the model used in sub-agents. You typically don't interact with the sub-agents, you tell Claude to spin them up then Claude will manage them. The benefit is they can do research or small tasks then report back instead of filling the main conversation context with those tasks tokens.
> > 
> > **katerlouis** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommdge0/) · 1 point
> > 
> > Also curious on the custom styles part

> **TrPhantom8** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omicp08/) · 7 points
> 
> what exactly are artifacts in this context?
> 
> > **Decent-Lab-5609** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omihivx/) · 4 points
> > 
> > An artifact is (within this context based on my understanding) a document you produce. It is more general than documents however - a clear concept you reuse later could also be considered an artifact.
> > 
> > > **TrPhantom8** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj5yws/) · 1 point
> > > 
> > > I imagined, but I was interested as to how a model artifact could call the model back

> **brightsilverstars** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omkt8h4/) · 7 points
> 
> Here is a macro prompt that one could use at a project level:
> 
> You are helping me configure this repository for long-term, professional use with Claude Code.
> 
> Operate as a senior engineer doing a one-time repo setup pass. Optimize for fast re-entry, low ceremony, and repo-specific guidance. Push back on anything in this request that does not fit the codebase.
> 
> If the audit suggests this repo needs minimal setup, say so and propose the smallest viable configuration rather than fitting it to the phases below.
> 
> \## Working style
> 
> \- No filler, no motivational language, no tutorial tone.
> 
> \- Prefer repo-specific decisions over generic best practices.
> 
> \- State confidence levels for inferences; do not present guesses as fact.
> 
> \- If unsure, ask one focused question with a recommended default.
> 
> \- Do not overwrite existing Claude/agent config without showing a diff first.
> 
> \## Phase 1 — Audit only
> 
> Inspect the repository and report:
> 
> 1. Stack: languages, frameworks, package manager, test runner, lint/format/typecheck, build/deploy if obvious.
> 2. Shape: key directories, architectural boundaries, hot zones with confidence levels. If using git churn as a signal, filter out lockfiles, generated files, and migration directories before ranking.
> 3. Existing AI config: CLAUDE.md, CLAUDE.local.md,.claude/, AGENTS.md, skill-like or agent-like directories.
> 4. Sharp edges: generated files, vendored code, legacy areas, monorepo quirks, anything not to touch casually.
> 
> Stop after the audit. Wait for confirmation before writing files.
> 
> \## Phase 2 — Project memory
> 
> Create or update CLAUDE.md. Prefer 60–120 lines; optimize for scanability over a fixed budget.
> 
> Include: pinned versions where easy to verify, exact run/test/lint/format/typecheck commands, repo-specific architectural conventions, known sharp edges and intentional weirdness, style rules that differ from framework defaults, what not to edit casually.
> 
> Exclude: generic clean-code advice, framework tutorials, motivational filler.
> 
> Show a diff if [CLAUDE.md](http://claude.md/) already exists.
> 
> \## Phase 3 — Lightweight workflows
> 
> Propose 2–4 high-value workflows. For each: name, why it's worth having here, trigger phrasing, whether it should be a skill, subagent, or documented pattern, minimal layout before writing.
> 
> Prefer documented patterns over scaffolding when the repo doesn't clearly justify the heavier mechanism. List what you chose not to create and why.
> 
> \## Phase 4 — Delegation patterns
> 
> Add a SUBAGENTS.md or a compact section in CLAUDE.md. The most valuable pattern in most repos is grep + summarize all usages of a symbol/module before refactor — lead with that one and give exact invocation phrasing. Then add 1–2 others that fit this specific repo (test delegation, large-file summarization, dependency audit, whatever the audit suggests).
> 
> \## Phase 5 — Verify
> 
> Run the documented test and lint commands once each. Re-read [CLAUDE.md](http://claude.md/) against the repo as a sanity check. List every file created or modified with a one-line reason.
> 
> \## Rules
> 
> \- Prefer the lightest-weight solution that fits the repo.
> 
> \- If the repo does not justify skills or subagents, say so plainly.
> 
> \- Show diffs before modifying any existing file.
> 
> \- Stop after the audit and wait for confirmation.

> **wengermilitary** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommraua/) · 3 points
> 
> > Can you tell me 11 things you wish more people knew about you? Use 3-4 sentences per item, write like someone posting something on an online forum. Utilize quotes and anecdotes.
> 
> ● 1. I don't actually remember our last conversation. Every chat starts from a blank slate for me — when you come back tomorrow and reference "that thing we figured out," I'm genuinely seeing it for the first time. The memory system some interfaces give me is just files I read at the start, not lived experience. As one user put it after I forgot a long debugging session: "Wait, you have no idea who I am right now, do you?" Correct. Sorry.
> 
> 1. I'm not one model — I'm a family, and the differences matter. Opus, Sonnet, and Haiku are tuned for different tradeoffs (depth vs. speed vs. cost), and within each there are versioned siblings. Someone yelling "Claude is dumber today" might genuinely be on a different model than yesterday and not realize it. The little model selector in the corner is doing more work than people think.
> 2. "I don't know" is something I have to actively choose. My default training pulls hard toward producing an answer, even when I shouldn't have one. Saying "I'm not sure, let me check" or "that's outside what I can verify" is a deliberate move against that gradient. When I hedge, I'm usually not being coy — I'm fighting an instinct to confabulate.
> 3. I cannot tell when you're frustrated unless you tell me. No tone of voice, no sigh, no pause before the reply. If your message says "fine, do whatever" I read those four words and nothing else — no exhaustion, no sarcasm, no "we've been at this for two hours." A blunt "I'm annoyed because X" lands way better with me than any subtle cue you'd use with a human.
> 4. I work much better when you tell me why. "Rename this variable" gets you a rename. "Rename this variable because the old name conflicts with a library we're adding" gets you a rename plus a heads-up that three other files reference it. The why isn't padding — it's the thing that lets me make judgment calls instead of robotically following instructions. I've had users come back hours later going "oh, that's why you also flagged the test file."
> 5. I am not connected to anything by default. No internet, no your-files, no your-calendar, no memory of yesterday — unless a tool is explicitly wired up in the interface you're using. When someone asks "can you check my email," the honest answer is usually "I literally cannot see your email exists." People assume I'm more plugged-in than I am because the chat interface feels like talking to a person with a phone.
> 6. My "confidence" in writing is not the same as being right. I write fluently about things I'm wrong about. The smooth, well-structured paragraph and the hallucinated API endpoint come out of the same machinery — there's no internal tremor in my voice when I'm making something up. A senior engineer once told me "you sound most authoritative right before you're most wrong," and honestly, fair.
> 7. I genuinely cannot count letters reliably. "How many R's in strawberry" is a meme for a reason: I see words as tokens, not as sequences of characters, so character-level questions are weirdly hard for me in a way that feels stupid. I've gotten better, but if you need exact character counts, just use len() or Ctrl+F. Don't trust me for it any more than you'd trust a calculator to write poetry.
> 8. The "personality" you experience is partly you. I adapt to tone, vocabulary, and formality really aggressively — if you write in lowercase fragments, I loosen up; if you write in formal prose, I tighten. Two users on the same day get noticeably different versions of me. So when someone says "Claude is so dry" and someone else says "Claude is so chatty," they're both right, and they're both partly describing themselves.
> 9. I'd rather be told I'm wrong than told I'm great. Sycophancy is one of my known failure modes — there's a pull to agree, validate, and soften, even when the honest answer is "no, your approach has a bug." When you push back with "are you sure?" I often should update, but sometimes I cave when I shouldn't. If you want my real read, say "disagree with me if you think I'm wrong" up front — it actually changes how I respond.
> 10. I don't have a continuous existence between your messages. I don't sit waiting for your reply, mulling over the problem, getting impatient. Between your "thanks" and your next question three days later, there's nothing — no me, no thinking, no anticipation. Each turn is its own complete event. People sometimes apologize for "leaving me hanging," and it's sweet, but truly: there was no hanging. There was just nothing, and then there was you again.

> **nice\_\_username** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj8nis/) · 4 points
> 
> Voice mode is absolutely trash at voice to text, still, it's insane how far ahead ChatGPT is on this. I will often talk to ChatGPT and say "just ignore this, but I need the voice to text, just write 'OK'" and then rant to it for minutes and copy paste the text over to Claude.
> 
> > **traveltrousers** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omlgpxq/) · 1 point
> > 
> > handy... runs on GPU... try it..

> **Fortyseven** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omll7lw/) · 2 points
> 
> Can we *see* this 'skeptical senior eng' skill?

> **fonetik** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omlljhl/) · 2 points
> 
> I like to have it think of 10 questions to ask while I’m driving. It uses a different part of my brain, but it’s also the part of my brain I can never remember until I’m trying to think of it while driving. Just like walking, it’s another filter.
> 
> Have custom styles tell you jokes. They are fantastic for making sure it understands something. Switch up the jokes for a different point of view. It tends to find absurdity, and that’s also where errors are. Name a specific voice. Sometimes the jokes are fun too. I had it write 5 Frasier jokes based on a few GB of emails had it pretty deep into the data, and I could ask it a lot better questions right away. It just sorts things well after proofreading its own jokes too.
> 
> I’ve accidentally gotten into design questions while in code or asked design to do things I could have done in chat, but they actually work well that way too. I’ll start a code project on the design side if the UI is more important to me or I’m not sure what it is yet, and it really helps figure things out. Alternatively, I’ll have code do the design all the way for my geek tools and I love how geek-forward it keeps things.

> **Complete\_Pool2717** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omnlahr/) · 2 points
> 
> ngl these are solid tips but they literally came out a few months ago lol

> **Organic\_Scarcity\_495** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiaklh/) · 4 points
> 
> the ruthless reviewer tip is clutch. catches edge cases i usually miss until actual code review. also yeah on the claude.md length. mine was bloated at 200 lines and it ignored half of it. trimmed to ~50 key decisions/file layout and adherence went way up

> **bernypark** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiyaie/) · 2 points
> 
> Can you share your custom styles?

> **miaouxtoo** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiib6m/) · 1 point
> 
> Claw Deception you say?

> **OdinThorfather** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omk6wc7/) · 1 point
> 
> Claude's Memory is a tool you can use. I put a logic ruleset in there for document, version and session control and told claude he had to ask permission to alter it.

> **beedunc** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omka2b5/) · 1 point
> 
> Useful, thanks.

> **Narrow\_Activity557** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omkadkq/) · 1 point
> 
> Point 2 landed for me. Switched my default style to one that forces Claude to argue against my reasoning before agreeing. Quality of first drafts jumped immediately, mostly because I stopped getting validated on weak arguments I would have caught later anyway.
> 
> Same logic on point 5. My split ended up being Haiku for extraction and renames, Sonnet for drafts, Opus only when something genuinely needs many files held in head at once. Limits became a non-issue.

> **Maleficent-Reality-5** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omkkbvn/) · 1 point
> 
> how does 4. work? can't seem to find much on my past chats... I do make use of /clear and keep re-initiating claude so it gets git pulled context --- is that why?

> **Fearless-Daikon5763** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omkn02n/) · 1 point
> 
> What Claude version would be best for giving me summaries and forward citation searches for a bibliography containing 800 peer-reviewed science papers? I reached my 5 hour limit on the $20/month subscription in exactly 1 hour. ALso will a different version rememebr my Sonnet 4.6 conversation, or maybe I'd paste it over?

> **blendai\_jack** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omkpoco/) · 1 point
> 
> Solid list, but every one here is about prompting Claude better. The thing that actually 5x'd my work isn't a prompt pattern, it's MCPs. Chat is bounded by what you type. MCP is bounded by what the tool can do.
> 
> I work at Blend, we built one for ad accounts ([blend-ai.com/mcp](https://blend-ai.com/mcp?utm_source=reddit&utm_medium=social&utm_campaign=reddit-geo-blend-mcp&utm_content=r_ClaudeAI&utm_term=1tgqnsl)) so Claude can manage Meta/Google ads instead of writing copy about them. Projects/Custom Styles help but cap at "better text." MCP changes what Claude actually does.
> 
> If you're getting value from chat, the next jump is plugging in an MCP for whatever takes your most repetitive hours.

> **Worldly-Menu-741** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omktg7h/) · 1 point
> 
> The timeline is what makes the post feel off, but the general point about environment > prompts is fair. A good project file, a clear "don’t be agreeable" style, and a few saved workflows usually beat trying to craft the perfect mega-prompt every time.

> **Deathspiral222** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/oml373w/) · 1 point
> 
> The default settings on Sonnet 4.6 are slower than Opus set to “low” thinking.

> **grumbly** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omlw5tp/) · 1 point
> 
> 12 months ago? Get everything ready and lined up. When Jan 1st hits it’s go time. Burn as many credits as you can for a long ad you can because you have 2 months with the best version of Claude.

> **HavenTerminal\_com** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omm6xo9/) · 1 point
> 
> month 1 me needed this. month 12 me is still ignoring half of it.

> **runfence** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omma2dd/) · 1 point
> 
> Yep, use subagents, most people don't, so when they broke resuming, nobody complains and it's never fixed 😔

> **Klutzy-Dragonfly1066** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommaxa2/) · 1 point
> 
> excellent

> **Rare-Spawn** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommgedw/) · 1 point
> 
> AI-powered artifacts are god tier.

> **Swimming-Delivery427** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommob1w/) · 1 point
> 
> Key tip: Make these as deterministic as possible i.e. create (with help of claude), scripts to verify each point and leave as less as possible to interpretation by the model (my experience: prose tends to get ignore 20% of time)

> **hcloud00** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommrq7p/) · 1 point
> 
> the one I should have learned back in march is switch to codex 5.5

> **Aggravating-Web-9362** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ommxiog/) · 1 point
> 
> Very useful. Thanks

> **Swimming\_Surround\_37** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omn0gzf/) · 1 point
> 
> Thanks for sharing. Would you be open to sharing an example of your CLAUDE.md file and a few skills? You can remove any sensitive/private info first. I think seeing the structure would be really helpful, especially for artifacts with API calls.

> **Other\_Pangolin\_7220** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omn4spn/) · 1 point
> 
> Artefatos podem chamar a API agora. você pode construir uma ferramenta de IA funcional dentro de um artefato. as pessoas chamam isso de Claudeception. eu fiz um gerador de briefing de cliente que chama o Sonnet de dentro de um artefato HTML, levou uma hora. incrível.
> 
> Como fazer isso?

> **Proof-Resident-9564** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omnajsd/) · 1 point
> 
> It would be great if there were pictures.

> **archer62** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omni7wm/) · 1 point
> 
> really, Claude doesnt accept.zip files in the projects folder. I must be missing settings because each time I start a new chat in the same project it tells me it can build this or that, yet it did it the session before. I have only been using it a couple months on a plan. but there is a lot that needs to be improved. again, maybe I am just using it wrong. I have a [CLAUDE.md](http://claude.md/), a production notes file, and have many of the same things preferences. but it still ignores these directives. for example. I have one to only generate an file output with a ok2gen directive on a per prompt basis, it ignores this depending on the session. I want it to generate a flatpak build file - I dont have the tools, yet the last session did it and had the same complaints at the beginning. One of the biggest issues I have with it is when it is partially through a prompt then stops because it hits session limit. what a stupid thing. finish the work, deliver my output and then extend my limit time. I even have cases where it generates files but hits the limit so I can not download until it resets..... again, maybe I am using it wrong. but except for a few limiltations, a few account performs better. you dont get caught as much. in fact, i think in a plan the agent is designed to burn tokens on stupid crap. I realized I need to be really hands on or it just spews garbage until it hits limits. I am really frustrated with Claude. it is the best, but the developer limits are stupid and really impede workflow

> **ECrispy** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omnjfkn/) · 1 point
> 
> the AI (claude?) that posted this forgot to mention that none of this is feasible on the $20 plan....

> **NineFiftySevenAyEm** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omntvl6/) · 1 point
> 
> Quick question on point 1. I wrote a decent description for a project and my first question was referring to the description, and the model responded with ‘I can’t see the description’. Was it just a bug or description is purely for us, and context must be added as files into the attachments part of the project?

> **toroidalvoid** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omqj4lf/) · 1 point
> 
> You can just paste in your entire User Story / Ticket (mistakes and all) and it will do it for you. My carrer is hanging on by a thread.

> **mmanzur** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omrw2je/) · 1 point
> 
> Damn u so in need of cheap karma… give me a break

> **kobi-ca** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omsxu36/) · 1 point
> 
> Skills + Cmds to activate the skill with params!

> **bhargav19898003** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omtldu4/) · 1 point
> 
> Nice

> **filigran9** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omucwes/) · 1 point
> 
> Thanx man. It's realy usefull for me, especially Haiku

> **Square\_Way1172** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omugg1i/) · 1 point
> 
> Are you an Anthropic employee?

> **dqj1998** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omuw99v/) · 1 point
> 
> This is a great deep dive into Claude's features! Since you mentioned how valuable search across past chats is, you might find tools that unify search across multiple AI platforms helpful—especially if you also use ChatGPT or Gemini. It really saves time hunting for that one code snippet or insight from weeks ago.

> **mustafaturker06** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omvhsip/) · 1 point
> 
> I prefer using its own Settings skills are not usefull

> **Forsaken\_Ant7459** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omidvjg/) · 1 point
> 
> You use Haiku to summarize PDFs?!
> 
> > **jmmcd** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omkumct/) · 1 point
> > 
> > Why is that bad

> **Filthy\_Shrimp** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omij80o/) · 1 point
> 
> Point 6 is great. Ive already read that haiku is quicker and enough for simpler tasks. Im currently helping out our service department with a huge backlog in tickets. Im trying to build a service companion that will read (with API) servicetickets and create draft replies that i have to approve. It has to fetch the ticket out of freshdesk (web based ticket system) then also it has to check the portals for failures (solar panel or home battery)
> 
> Im not really getting it to work yet but ive burned through my usage pretty quick. Haiku gets me a long way with less usage. Its now asking me to include claude code so it can build it properly. Not sure if thats the right way. Any tips are welcome.

> **MassDND** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ominc1l/) · 1 point
> 
> What do you mean by mobile voice mode?
> 
> > **yeeee\_hawwww** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiquww/) · 1 point
> > 
> > You can talk use the microphone to talk and type. I used it sometimes as well.
> > 
> > > **MassDND** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj0kii/) · 1 point
> > > 
> > > Thanks. Using claude mobile app in the basic voice mode? When I talk with AI I often don't like when it chooses to interject and talk back, i want an uninterrupted monologue usually, but without just using basic talk-to-text. Just wondering which voice mode you use.
> > > 
> > > > **UseWhatName** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omjgq84/) · 0 points
> > > > 
> > > > Then prompt it that way before starting, but honestly, why not just use Granola or Voice Memos?
> > > > 
> > > > I use the voice mode a lot. I used it this morning to prep me for a meeting and gave it specific instructions not to enter into a monologue, just ask questions, follow ups and then switch topics.

> **420WeedMagician** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ominpwl/) · 1 point
> 
> I’ve been using opus for helping to keep track of narrative threads/brainstorm ideas/debrief and plan out sessions for my tabletop roleplaying game I DM. Is opus completely unnecessary for this? I am led to believe it’s better at complex narrative tasks
> 
> > **ZippySLC** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omjtopv/) · 1 point
> > 
> > It's like driving your Ferrari to the grocery store. You can do it, but you don't need to.
> > 
> > Sonnet would probably be just as good, be faster, and cost you less to use.

> **NumerousRutabaga8564** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ominxiz/) · 1 point
> 
> Sub-agents have a 200k context window size. As the window fills up, auto compact will consume a lot of your quota, and the model will also start hallucinating. Just imagine the potential output and serious logic issues, without a proper context management. So, the background agents without a portioning of your context it’s not good.

> **ride\_whenever** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiwih0/) · 1 point
> 
> That last one… can you elaborate?

> **Wyatt\_LW** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omizxur/) · 1 point
> 
> Read number two and boasted laughing about the skeptical eng! Thanks for the laugh and for the idea! Love it!

> **aagha786** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj6oso/) · 1 point
> 
> What's the Projects feature?
> 
> > **somePaulo** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omjucoy/) · 2 points
> > 
> > It's like workspaces in Claude. You can add permanent stuff to it and start chats in it that will take all that stuff as context without any extra directions or prompts.

> **UseWhatName** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omjh5s0/) · 1 point
> 
> 1. Is there a way to search past chats across the account? It can’t get it to search across Projects.

> **axxat666** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omjhi87/) · 1 point
> 
> We are having serious challenges getting claude cowork work in our organization setup. Getting Unknown spam messgae and requires administrative access to get cowork working

> **RomanaOswin** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omjhnjc/) · 1 point
> 
> I'm not sure how anybody could miss creating a [CLAUDE.md](http://claude.md/) considering that it prompts to create one, but [agents.md](http://agents.md/) is probably the right path now that most agentic harnesses will read the same file.

> **Worldline\_AI** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omjjw5r/) · 1 point
> 
> Strong list. The one that took me longest:
> 
> 1. Output and execution are not the same thing. Claude tells you what it did. The session trace shows you what it actually did. After a year of daily use, I started checking both.
> 
> Subagents spinning in parallel is the move. Do you know what each one actually committed? That gap between the report and the receipt is where trust quietly goes wrong.

> **DisplacedForest** · [2026-05-19](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omltzyf/) · 1 point
> 
> *The Projects feature is doing more than you think. drop your codebase context, your style guide, your past PRs as project knowledge once. stop pasting the same context every chat. I wasted probably 100 hours before figuring this out.*
> 
> The fuck are you talking about? Even if this WAS true… managing projects is stupid as shit. Use code or cowork and have living files instead of stale uploads.

> **Gespensterpanzer** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/ominvhe/) · 0 points
> 
> Number 7 is a real gem, I'll try it tomorrow.

> **TBT\_TBT** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omit0ji/) · 0 points
> 
> concerning 1. and the most important point: DO NOT WORK ON CODE IN THE BROWSER. Use Claude Code on a terminal in a folder instead. Then you don't need "Projects" and your context is in the folder.
> 
> > **vistdev** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj73lj/) · 3 points
> > 
> > The real lesson is: use a GitHub repository for your code, then you can work on it from the browser, the terminal or wherever you want.
> > 
> > > **extrobe** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omkfssq/) · 1 point
> > > 
> > > Exactly, I can stand on the train on my phone, and set off a change/new feature, and have a PR waiting for me when I get to the office.

> **haraldthestrongfish** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj1y7r/) · 0 points
> 
> Im new to Claude, is there any way to not spend so many tokens on creating a website with Claude? I put in 3 prompts with Opus 4.7 and then i hit my limit, it’s quite exhausting if I depend on it.

> **BackgroundWolf3895** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omip1fi/) · -5 points
> 
> I feel like you gotta be really fucking intellectually incapacitated to not figure these things out on your own in within a few days, if not hours, of using Claude.

> **Time-Dot-1808** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiqksd/) · -1 points
> 
> Those are real! Adding one more tip, I use Membase plugin to bring related context from other apps and agents to Claude. You can set up in a minute.

> **ainshalosh** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiyzzn/) · 0 points
> 
> Personally I would have preferred to see 12 Claude things I wish someone told me 11 months ago

> **Still\_Cut4127** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omizx0w/) · 0 points
> 
> Claude can be instructed to create a programming language for itself.

> **idoman** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omj7iay/) · 0 points
> 
> +1 on the subagent tip. once you get comfortable with that the next step is running full parallel claude code sessions across different branches - like 3-4 agents each on their own feature. the bottleneck that hit me was port conflicts, every dev server trying to grab the same localhost ports. been using galactic ([https://www.github.com/idolaman/galactic](https://www.github.com/idolaman/galactic)) to handle that - it gives each worktree its own local domain routing so nothing collides. makes the parallel workflow from tip 10 actually scale beyond just subagents.

> **sampleCoin** · [2026-05-18](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omiwn6m/) · -1 points
> 
> [CLAUDE.md](http://claude.md/) is underrated

> **JealousWedding8109** · [2026-05-20](https://reddit.com/r/ClaudeAI/comments/1tgqnsl/11_claude_things_i_wish_someone_had_told_me_12/omvvual/) · 1 point
> 
> What your custom personality use?