---
title: "I Tried Every Popular Claude Skills System, Here is the Best"
tags:
  - "clippings/youtube"
categories: "[[Videos]]"
created: 2026-05-19T22:47:19+02:00
channel: "Rob Shocks"
published: 2026-05-18
duration: "15:32"
status:
url: "https://www.youtube.com/watch?v=VoxL_YmHR-I"
---
## About

![I Tried Every Popular Claude Skills System, Here is the Best](https://www.youtube.com/watch?v=VoxL_YmHR-I)

## Description


Skills have become the building blocks of modern agentic systems but most people are using them the wrong way. In this video, I break down what “skills” actually are, how they fit into the new Agent Development Life Cycle (ADLC), and the simple, desert island skill stack you need to ship faster without overwhelming your model’s context window.

We’ll compare the common patterns behind today’s most popular skill systems and workflows, including why you should often 

SKILL FRAMEWORKS
https://github.com/addyosmani/agent-skills/blob/main/skills/interview-me/SKILL.md
https://github.com/affaan-m/everything-claude-code
https://github.com/mattpocock/skills
https://github.com/garrytan/gstack

SPEC DRIVEN FRAMEWORKS
https://github.com/obra/superpowers
https://github.com/bmad-code-org/BMAD-METHOD
https://github.com/gsd-build/get-shit-done



Join the Build With AI Newsletter and the Course & Community below for weekly tactics, tools, and end to end builds.

https://dub.sh/course-link-metaskills


CHAPTERS
00:00 Intro
00:35 What Are Skills Again
01:00 Skill Libraries 
01:50 Library 1
02:35 Library 2
03:08 Test Driven Development
02:53 Prototype Mode 
04:30 Library 3
05:06 Library 4 
05:37 Spec Libraries 
06:20 Code Review with Code Rabbit Atlas (Sponsor)
08:50 The Simple Alternative 
12:32 Why you should build your own system
14:40 How you win as a builder


## Transcript

### Intro

**0:00** · So I went through all the major skill libraries, Gary Tan, Superpowers, Matt PCO, BMAD, Everything Claw Code, GSD, OpenSpec, and more. Essentially, what I wanted to do was distill all the key ideas down into a couple of prompts, skills, and patterns that you can reuse on every project over and over. And these are the ones I've settled on after almost 2 years now of working with agents. We're also going to talk about how the most powerful skill system is built and why you're not going to find it in someone else's repo.
**0:28** · Also, this week, our sponsor, Code Rabbit, just released a wicked new tool for code review. More on that later. So, skills are just part of the entire agent harness that we use to build our software. Skills are just natural language prompts. What differs is you put them in a special file called a skill.md. You've got some front matter in there, which is some extra information like the name of the skill and the description. And this is always loaded by the model. So it has an idea of what skills it has capable of using.

### What Are Skills Again

**0:58** · You can have scripts uh reference material assets all bundled into your skills folder. So recently what we're starting to see trend is skill libraries. So we've seen some really popular ones from Gary Tan, Afan Mustafa, Matt PCO, Adasmani. All these guys have been working in the industry for many years and have been pooling their approaches and thought processes into collections of skills which they're sharing with the rest of the community.

### Skill Libraries

**1:22** · If you look at GitHub for any of these skill systems, you've seen they're seeing huge growth. If you look at something like Everything Clawed Code, that's up at 183,000 stars. For context, there have been some huge open- source projects that have been on the go for 20 years that don't have anywhere near that many stars. So, having studied, used, and reviewed all these different skill libraries, you can really see that there really is a lot of common denominators. Let's take a quick look at some of the major repositories and see what the commonalities are. So Addi Asmani is from Google. He's got a great blog that's worth following.

### Library 1

**1:52** · What he advocates for is a simple set of skills based around creating a spec or specification for what you want to build. So you have a chat with an agent and decide exactly what's going to be built. Then you create a plan. So the agent thinks about how it's going to build out the specification or idea that you have. It builds it and builds incrementally, one slice at a time. Once the build is finished, it gets tested to make sure it adheres to the plan and the spec. Optionally, then you can review the code before it gets merged.
**2:22** · You can run code simplification prompt to ship to production. So, this is basically just one iteration of development all encapsulated into six or seven prompts.
**2:34** · Matt PCO has been on the go for years, a fantastic TypeScript developer and AI engineer. He is advocating for real simplicity. In math skills, we see a lot of similarities to what Addi has developed. We have a diagnose which is very similar to a discuss or specify. I do like the grill with doc skill. Matt is a big believer have a grounding and understanding in the domain model that you're working in and not having to repeat that every single time because you remember our agent has a certain amount of context window and you want to load some of that context and understanding of the project.

### Library 2

**3:02** · So grill with docs is one that's worth checking out. Again we see some commonalities around test driven development. All of the frameworks advocate for some level of testdriven development. It's the idea that you've got tests in place so that if your agent goes off and writes new code or does something else that you can run a suite of tests to make sure that nothing that you had previously built ends up being broken. It can be hit and miss with a lot of AI models. They actually cheat their way through testing. But it is one extra step to make sure that we're not breaking existing code as we move forward.

### Test Driven Development

**3:31** · Same as Adi Asani, we have the two issues which is basically again just breaking down a bigger project into a smaller vertical slice that the agent can handle. You don't want the agent taking on too much in the one go without actually verifying it to make sure that they built exactly what needed to be built. And then another one that I see that Matt has added is prototype. So it's the idea that you actually flesh out a design before you build it out.
**3:57** · And I'm a big believer in this. Anyone who has taken my course knows that I'm a big fan of a design mode or a prototype step. The idea here is that you just tell the model that you're going to implement the front end of the application, not the back end. because once we get into the back end, it starts to slow the agent down. And then actually passing that prototype to the agent gives it a much better sense of what it needs to build in the back end.
**4:18** · So doing this as an upfront step really saves some time. And again, this isn't a new idea. We've been doing wireframing and prototyping for the last 30 plus years. This is just the agentic approach. So Gary Tan is the CEO of Y Combinator. So Gary has a much more opinionated skill stack and there is a lot to learn from this. Personally, it's a bit too overengineered for my liking.

### Library 3

**4:41** · But if you look at any one of the individual skills, there's a lot of interesting things to learn from.
**4:46** · Particularly his skill around office hours is really unique. It's like the idea that we sit down with the Y Cominator CEO and he asks us six forcing questions about our startup idea. I actually think a big differentiator now when anyone can build quickly is actually knowing what to build and what to focus on. And then we have everything clawed code by Afen. Now, don't be worried. This elatched skill system will work for any different kind of agent.

### Library 4

**5:10** · So, of all the libraries that I've shown, this one is probably the biggest.
**5:13** · It's at about 182,000 stars and 170 contributions. It is pretty huge in terms of what it offers. It looks after memory, continuous learning, how to run verification loops, sub agent orchestration. It has a heavy focus on security. If you want to deep dive into what an extensive harness might look like, it's worth taking a look at all the different skills that it's got in there. And just a quick note on all the various different spec libraries.

### Spec Libraries

**5:40** · There's a lot of overlap between the skill systems that I showed you and of course these spec based libraries and I've covered a lot of them on the channel previously. BMAD is very enterprise level. It follows the path of a business analyst, a product manager, a senior architect, all working in party mode essent to figure out what you need to build and make sure it follows a strong software development life cycle process. So if you're at an enterprise level, it's worth checking out BMAD.
**6:06** · Superpowers is a little bit more lightweight of all of them. I think I actually like Superpowers the best. I've had some good results with it, but I'll be honest, I don't rely heavily on specbased systems. I just go with something a little bit lightweight and bespoke myself. And we'll talk about that in a second. Working with enterprise development teams, one of the biggest complaints I've gotten in the last year is the amount of code review that needs to be done. Thousands of lines if you let it get out of hand. But I highly recommend you make your commits a lot smaller to be a lot nicer to your team.

### Code Review with Code Rabbit Atlas (Sponsor)

**6:34** · But we still have to review a lot of this code and that's become a bottleneck. So if you've been watching the channel for a while, you know I'm a big fan of Code Rabbit. So, what I'm most excited about is just in the last couple of days, they've released Atlas and this really solves a big pain point for me. I've got a project here that I'm working on and we have a pull request.
**6:51** · If you don't know what pull request is, I've got a great video on Git a couple of videos back you can check out and I'll link to that in the description.
**6:58** · But essentially, either an agent or somebody else in my team has gone and create a load of code and they've submitted it for me to review before I actually add it into the main codebase.
**7:07** · So, normally what I have to do is go through the commits and go through all the merged code. And generally, this is quite a painful step because you're just looking at these sidebyside diff views that we're all familiar with. Basically, a sidebyside diff. Here's the original and here's what changed. But when I'm dealing with so many pull requests across so many different repos, this really starts to fry my brain a little bit. So, Code Rabbit was really paying attention to this and came up with something that I think is really, really useful. So, essentially, when I click that little review button, here's what I get instead.
**7:36** · But instead of a big long alphabetical file list, it breaks it down into layers. So to me the layers are basically okay well what's the new data shape and we can see that here.
**7:45** · Then what kind of business logic is going to consume that data shape and then you know what's the testing around it. I want to look at this change in patterns. So on the left here I get that structured navigation and the layers of the diff. Then I get the traditional diff in the middle. And then on the right I get these little AI summaries of exactly what's going on. And as I move through the code, they actually change and update based on what I'm looking at.
**8:08** · So here it gives me an explanation of exactly what's happening at each stage.
**8:13** · And to be honest, even if you're a beginner developer, this is really useful for helping you learn the code and the patterns that AI might be generating so your skills don't atrify and that you actually improve as a developer. And then what's even cooler is I can go ahead and chat with any one of these different comments or the pull request in general. So it handles everything native GitHub review can do as well. So, I can add my comments here.
**8:34** · And when I'm finished, I can just go and submit my full review, comment, approve, or request changes. So, Atlas just came out in the last couple of days. I highly recommend you check it out. And it's free for a limited time. So, get stuck in. Check out the link in the description down below. Okay, so we've taken a look at all the various different popular skill systems and stacks. Let's compile them together to show you the best pattern and skill pattern you can use to build out your projects. And this is going to be super simple. I'm not introducing you to another repository you have to follow.

### The Simple Alternative

**9:05** · It's just a set of patterns and a way of thinking that if you can imprint, you're going to be getting away with 90% of what all of these systems offer. So, the first thing you're going to do is go into ask mode. You can get ask mode in cursor in clog code or you can set it up as a little skill yourself. So, this doesn't need to be a skill. All you need to do is basically ask your agent to interview you about the project that you're going to create. Next up is you want to create some kind of a prototype.
**9:30** · You can ask the agent to produce an aski diagram. They do it really quick and it'll give you a quick wireframe.
**9:35** · Fastest way to do it. Or you can just chat to the agent and say, "Hey, let's go into design mode. I only want you to work in the front end, not in the back end. I want to design the wireframe of my application." So, here's a quick example of design mode. So, you basically just want to let the agent know we're in prototyping mode. Develop front end only. We're mocking up the interface. Use dummy JSON to represent any back-end data. link all components for navigation. Make buttons responsive.
**10:01** · Don't connect to backend logic. So essentially, you're stopping the agent from creating a complicated backend that it has to support. We just want to figure out the front end. We're going to do the back end later. So sometimes if it's a basic feature or we're just doing any kind of backend logic, we can actually skip prototyping. We sometimes have a strong idea of what we need to build. So you don't need to do it in every single step. So both claude code, codeex and cursor have their own vanilla plan mode which is really quite powerful and I don't think you need any kind of skill system around this.
**10:30** · In the case of cursor here and it's the same if you're using claw code or codeex it's basically going to create a document as a markdown breaks it down into various different phases so it knows what it should work on first which is important. It's very similar to how those other frameworks would shard or split the project into multiple different parts and then it creates a list of to-dos to work through and it sets out all these different verification steps naturally without you having to build any kind of skill around this.
**11:00** · This is something we needed to do for ourselves via skills and processes before, but now a lot of the modern agents are doing this for us. Once the build phase is completed, we're going to want to test and verify exactly what we wanted to get built was built. And again, this is something that's baked into the plan mode of many agents. Now, it's going to run a lint and build test to make sure that everything compiles and works okay.
**11:23** · Then what you can do is get the agent to use playright or the browser mode, which is in cursor or in claw code to basically test the application to make sure that it's all working fine. Now, this is kind of hit and miss. The testing that agents do doesn't really catch what you want to do. Inevitably, the test phase is still what we call a human in the loop phase where via some kind of a smoke test where you're going to click through the process yourself to make sure that everything works okay. Now, one thing a lot of the other frameworks talked about was testdriven development.
**11:52** · If you want that to be part of your workflow, you just include that in the planning stage.
**11:58** · Just say, I want to include test-driven development and it will start to implement and build tests as it's writing the code. So, that's pretty much it. Research, prototype, plan, build, and test. That's your kind of iteration loop. Essentially, this is all you need to get your software built, but there's a few extra steps and that is the polish step. Adi Asani has a skill which is called simplify code. So essentially that means you're getting an extra agent to run through the code. In this case, you might have used Opus or a anthropic model to build the software.
**12:25** · You might use GPD 5.5 or something like that to basically work through the code and give its opinions.

### Why you should build your own system

**12:35** · I think the best system is going to be the one that you end up building yourself. That's for a couple of different reasons, and I'll explain why.
**12:42** · So, first, I'd start with just natural language prompting, the kind of framework that I just showed you. You're just using your own agent patterns to work with the agent. Use the built-in ask mode, the build mode, the plan mode as much as you can, and just rely on the native capability of your mind and also the harness. When you do create a skill, it's only because the agent has messed up in some way or you want to give it very bespoke information about your codebase or your process that you want to carry out. And when you want that to be a very repeatable process.
**13:12** · Also, you want to be rewriting your skills to be as simple as possible. Maybe even just a few short paragraphs. There's no need for tons of extra information, which is going to bloat your context window and confuse the model. Next up, you're just going to work with that very simple skill alongside the agent harness that you're using. Understand where it works well and where it doesn't. Then manage for those edge cases you feel like the skill is missing. In traditional software, we have something that's called the software development life cycle. And that encompasses multiple different disciplines.
**13:40** · Now, we're looking at something that's like agentic development life cycle. And a big part of that is managing your harness and also skill management, particularly when you work across multiple different developers and large organizations.
**13:54** · Let's say you develop a skill that you feel is useful. How do you share and organize that skill with other people in your organizations? Skills.sh from Verscell does a good job of allowing you to store your skills in private repositories, being able to update them, store them, and share them as you see fit. Skills in some ways are essentially just documentation. And we've all experienced the scenario where comments go out of date, documents go out of date. You're going to have to spend as much time updating these skills and keeping them current. So you need to be very careful about what ones you introduce.
**14:24** · Are they absolutely necessary or are they just going to cause confusion to the model at a later point.
**14:30** · This is a whole new skill set if you will. So inevitably the best skill system and the best harness is going to be the one you develop over time for you. I think this is going to be how you really differentiate as a software developer. Your agent harness your set of skills that has been built up over time working with a particular codebase.

### How you win as a builder

**14:49** · If there's one skill that you absolutely can't live without, please share it in the comments so I can learn and everybody else in the community can learn as well at the same time. So hopefully that was helpful. Instead of introducing you to yet another skills library that you have to test and try, I kind of wanted to bring things back down to earth, give you the feeling that you weren't losing your mind in keeping up with all of these systems and understanding that it's really just some simple development loops that we've been practicing and using for the last 30 or 40 years of software development that you can rely on. A lot of these libraries, a lot of these skills are replicating that same approach.
**15:20** · That really starts to compound for you and for the organization that you're working within. If you found this useful, hit the subscribe button. It means you'll get more videos like this in your feed.
**15:30** · And I look forward to seeing you next