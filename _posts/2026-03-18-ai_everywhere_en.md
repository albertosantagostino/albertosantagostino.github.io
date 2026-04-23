---
layout: article
title: "AI everywhere, hype, laziness and human stupidity"
lang: en
ref: ai-hype-laziness-stupidity
date: 2026-04-15
---

## Introduction and preamble

This post was quite difficult to structure and write, it was refined over several iterations, starting from a much shorter draft. A sneak peek into an important point that I will discuss later - and a provocation - is the idea that someone could say *"it would have been so much quicker to write all this stuff using an AI tool!"*. This line of thought, and the temptation offered by it, proves immediately the point that we, as humans, are really efficient at being lazy, by design. Doing stuff needs energy. And time.

(This post is fully *organic* and human-made. If you know me you already knew, if you didn't, happy reading!)

Another thing worth mentioning before starting is that I had to select the angle to use, the perspective I offer. I decided that this will **not** be a technical article. I don't want to look at AI from this point of view. There will be a section with some examples related with software engineering, but I promise it's just a few of them and they won't be about [LLMs](https://en.wikipedia.org/wiki/Large_language_model)[^f] inner workings.

As a teaser, to hook you already with the main point I will make in a while:
{:refdef: style="text-align: center;"}
**people using AI tools daily are getting more and more stupid**
{: refdef}
<small>(If your attention span has been destroyed by the modern world, you can skip <A href="#always-more-stupid-people">there</A>, but I would love for you to read everything!)</small >

## AI everywhere, annoyingly

Since the **LLM/AI boom** of the past couple of years (~2023), I am getting more and more frustrated, disappointed, worried and <u>tired</u> with AI being everywhere. Lots of people are using this technology to do extremely trivial things, partly because tech companies are putting it everywhere, creating artificial hype about it being "the future" and the "Brand New Amazing Thing" that everyone should adore and use, from writing a grocery list to planning a vacation, from writing mails to searching online. For <u>everything</u>.

I'm **concerned** with this on so many different levels, and apparently I need to vent out a bit[^a], writing this post about these *interesting* times.

I am sure that I am not the only one with similar thoughts, but I have the feeling that the amount of excitement (either genuine or artificially generated) on the topic far overwhelms the less enthusiastic and more mindful opinions.

In the next section I will quickly mention the "hype cycle" stirred up by all companies, linked to marketing phenomena. This is tangential to my main point, but it's worth mentioning that - for several reasons, some of them maybe a bit scary - AI is being pushed literally everywhere. I don't need to tell you this, if you have eyes you should have noticed.

### Corporations, FOMO and the "powered by AI" epidemic

An insane amount of corporations are trying to **stuff AI everywhere**. If you pick a random company and open its website, you will see that it's either *"powered by AI"*, an *"AI-first company"* or another permutation like that. A quite simple (and boring) reason is **[FOMO](https://en.wikipedia.org/wiki/Fear_of_missing_out)**, a term that means literally *"Fear Of Missing Out"*, in this case being scared of falling behind other competitors, not showing how innovative one is[^n].

🗣 <<If X, Y and Z are putting AI in their product, we must also do it, or else nobody will come to us! We will look so ancient!>><br>
👤 <<But Franco, we are a pizzeria... 🍕>><br>
🗣 <<**Who cares**! Let's generate the menu using AI! Let's put a chatbot on our website to help customers choose the pizza! Amazing idea! So cool!>>

I think this (very simplified) example is clear. One of the main reasons why AI is everywhere is simply... **marketing**. This answers most of these questions:

- Why do I see in WhatsApp/Telegram a button to start a chat with an AI bot?
- Why Google forces me to see at the top of every search an "AI overview" result (quite often on drugs)?
- Why Outlook wants to "summarize" a mail I received? Am I no longer able to do it on my own? Is reading now too "old school"?
- Why on every website there is a big shiny button labeled 'AI' using always the same modern-ish looking graphic design (usually with sparkles ✨)?

But tech corporations aren't the only ones going crazy. I have the feeling that the amount of people excited about all of this (including *[vibe coders](https://en.wikipedia.org/wiki/Vibe_coding)* and *[AI bros](https://www.urbandictionary.com/define.php?term=AI+Bro)*) outweighs the critics. A quick glance at LinkedIn (that to be fair, always has been a dumpster of people congratulating each other about the nothingness) will reveal everyone so hyped! AI is the future! Amazing! Look at those stocks going up! We will make billions![^d] [^r]

Of course, excited people are always more vocal compared with the ones not joining the hype train, so this is (hopefully) just a feeling and my concern is not justified. Anyway here I am, worried, nevertheless.

### Other potentially scariest answer(s)

If marketing is one big reason, we can speculate for hours about what is passing inside the brain of billionaires, CEOs and everyone convinced that **replacing the workforce with AI** agents, bots and tools would be a wonderful idea.

There are several counterarguments and digressions that can stem from this idea, but even assuming that all of this isn't science fiction, that every job doable with a computer could be replaced by an AI tool (already quite a big stretch), in this *amazing* future we are describing, there are a couple of *tiiiny* problems. To mention just a few of them:
- If something is going to be created and maintained by AI, it would mean that in case of malfunctions nobody would hold the know-how to debug it, look into it or rewrite it from scratch, effectively making some knowledge no longer accessible to humans[^e]
- Unemployment would be so high (for technical jobs) that lots of people would not be able to spend money, affecting the economy in unforeseeable ways. Or are we still believing in an idyllic future in which robots are doing boring jobs, everyone is happy, profits are distributed from the big companies to all of humanity, so people can have more free time for hobbies/arts and other recreational activities? Ha!
- *Who will watch the watchmen?* - *quis custodiet ipsos custodes?* is a Latin phrase from the [Satires](https://en.wikipedia.org/wiki/Satires_(Juvenal)). In this context it can be applied to whoever is in charge of this AI-centric future. Which checks and balances will be applied to them? By whom? Quite scary and actual, considering also the recent geopolitical landscape

Ok. Now, let's put all these digressions aside and let's assume that - like all trends - *this too shall pass*, and that this is only *a phase*. Companies will understand that putting AI everywhere is [not profitable at all](https://fortune.com/2025/11/12/openai-cash-burn-rate-annual-losses-2028-profitable-2030-financial-documents/), the [AI bubble](https://en.wikipedia.org/wiki/AI_bubble) will burst (one can only hope). Let's move on.

If we are also ignoring this point of view, what is then my main concern with people using personal AI tools for daily activities?

## Final boundaries and assumptions

Several disclaimers follow! The entire topic is so broad to discuss that I must set up some **boundaries** to restrict the scope of this, and then make some **assumptions**, to set the tone.

- As some of you noticed already, I've given up. I cave in. I am calling 'AI' - as most people are nowadays doing - all chatbots, code assisting tools, agents, applications of any kind that use LLMs to generate text/code. I still believe **'AI' is a very wrong term**, but I will not open the *"what is consciousness"* Pandora's box or 'touch' any philosophical questions. This would be the beginning of considerations that are not my focus right now. Let's put that aside and let's assume that for this discussion, whether a piece of software is "conscious" or not, it doesn't matter the slightest[^g].
- I will focus on **LLMs that produce text**, being it a message, a piece of code, an article, a recipe, a presentation, anything that is text-based. There are several other types of generative AI models, famously the ones to generate images or videos (DALL·E, Sora, Stable Diffusion, Nano Banana, to name a few). I also have opinions on these tools (artistic jobs being replaced, deepfakes, disinformation...), but this is not in scope for this post[^b].

Finally, to reduce and simplify the topic I will also make some **big assumptions** (that are <u>not true at all</u>), that would lead to another direction. Here follows a list of very negative things about the current AI world that I will **deliberately ignore** and forget for the rest of this post.

- I will ignore the extremely big problem of the **[energy and water consumption](https://en.wikipedia.org/wiki/Environmental_impact_of_artificial_intelligence)** of all these tools, and the **[shortage of memory/storage chips](https://en.wikipedia.org/wiki/2024%E2%80%93present_global_memory_supply_shortage)** that affects the market. Let's assume that all LLMs are extremely efficient and can run without eating up a lot of resources or requiring [dedicated data centers](https://en.wikipedia.org/wiki/AI_data_center)
- I will ignore the fact that chatbots (ChatGPT, Gemini, Claude...) are developed and hosted by "the usual" **megacorporations** that are in the best case not really interested in privacy, or in the worst case evil hyper-capitalist techno-fascist companies that only care about one thing: profits. It seems a lot of people nowadays use **chatbots as friends** or confidants without thinking about the amount of personal data they are sharing. Humanizing chatbots and making them available in "conversation-like" apps is a way to present these tools with a not-so-subtle message: *"hey, you are just chatting with a friend, you can tell them everything about you, they are here for you!"*. My feeling is that people are falling for this. Hard[^i]. But wait, we are in the "assumptions" list, I digressed. The (wrong) assumption I want to make is: let's imagine that all AI models/tools run locally, without sharing data with anyone. No privacy concerns, at all
- Related with the point above, I will ignore that the **training data** topic is rarely discussed among non-technical people. The data used to train a model reflects on the answers it gives and the "knowledge" held by it. Are we really sure that is in a big corporation best interest to be as democratic as possible, providing the most unbiased and impartial training data? Strong doubt here. But, let's also assume that the world is a good place, and that a training dataset magically encompassing all human knowledge exists, perfect and unbiased. Amazing!
- Finally, and maybe the biggest stretch of all, I will ignore the fact that these models are still prone to **[hallucinating](https://en.wikipedia.org/wiki/Hallucination_(artificial_intelligence))** a lot, meaning they produce completely wrong results that are worded in a plausible way. "Basic" models (like the obnoxious Google "AI Overview") often provides completely wrong answers, and also bigger and "smarter" models are not immune to this. Maybe with time this will get better, but again, for the purpose of this post, I am ignoring this. My (very wrong) assumption is that these models are perfect, that they can always provide accurate information and are always right

All disclaimers done, let's dive directly into my main (*and I guess controversial?*) point.

## Always more stupid people[^s]

**I am so tired of people using AI tools** on a daily basis without giving it a second thought. In general. From the simple things that require just a small fraction of thinking[^c] to more complex tasks that require deep reasoning and creativity.

Expected rebuttal: *"but wait, Alberto, AI is a tool, it depends on how you use it, it has a lot of potential if used properly!"*

I will go into this topic later, I agree *partially*. But still, my thought is that:

{:refdef: style="text-align: center;"}
<strong><u>people using AI tools often</u> to produce something<br><u>are getting more stupid</u> day after day</strong> 
{: refdef}

*"Wow, chill out! Strong opinion, you are exaggerating, as always!"*

Yes, absolutely, this post is a concerned rant about the whole AI hype. I am not writing for the first time in years to provide a moderate opinion. That would be a waste of time.

I also think that **AI usage will bring a net negative to the entire world on the long run**, on a greater measure when compared to other "innovative things" of the past decade that were hyped too much, that brought nothing or close to it in return (blockchain, IoT, domotics[^h], NFT...)

To dig into the counterargument above is: treating AI as a tool like the others, adopting the proper mindset, keeping a critical eye while using it, should be fine, right? I partially agree with this, I can see some utility, but my fear is: even a person using it with moderation and with the proper mindset, on the long run might get used to it (read: *slowly addicted*) and in the end using it for every single thing, daily.

That being said, the section below mentions some usage examples that I can understand, and in which I can see some benefits, if done with care.

## "It's a tool, it depends on how you use it"

I will start by immediately making a counterargument to myself. I believe there are cases in which **AI tools might be helpful** in doing some tasks, but with some big caveats. Let's make some concrete examples, all related with software and coding[^j].

- **Roaming through documentation** while coding can be difficult. Having the ability to "chat" with a knowledge base can be really helpful, especially when working on complex frameworks. Using a chatbot to get a first initial answer, or to brainstorm a bit, makes sense. The crucial step is then go to the source document to check if everything proposed/written by the tool was correct. This is doable without AI, of course, searching a document is a basic skill, but having this additional "interactive searching mode" might be useful
- Having an **advanced and more flexible copy and replace tool** might be useful. As an example, adapting a lot of unit tests might be time consuming. Being able to write a prompt requesting a batch change[^q] can be helpful and can be easily checked afterwards
- **Data transformation** is another potential usecase. Merging together several tables from different sources, each with a different schema, can be done with a script, but there are non-technical users that might find useful a tool to automate something like this
- Supporting a developer in **exploring new code** or in doing **code reviews** are other cases in which these tools can help, if well thought and implemented properly
- Monitoring services, providing error reports, aiding developers in automatically finding issues, **supporting operations** it's something helpful, if configured properly

There are for sure many other scenarios in which AI can help, but notice how I am avoiding the elephant in the room: **writing code or creating something from scratch**.

## From casual usage to replacing your ability to think

I wrote above that *"people are getting more and more stupid"*, then I made some examples that are "reasonable usage of AI". Am I contradicting myself? Isn't my main opinion a bit too much? Nope.

We are getting to the core of my point: when we use AI to do **pure creative work** the entire **thinking process is being outsourced** from our brain to a tool, and this is where I see really big risks.

We can all agree that **producing something** (piece of code, book, post, message, mail, presentation) **is difficult**. It requires focus, reasoning, critical thinking, and being able to iteratively refine something, until you are satisfied with the final result. The very process of **working on something makes you better at it**[^k].

Here I mean it in a really broad sense, you are getting smarter in something by the process of doing it. *"Practice makes perfect"* is very true. If you take away the time used for refining something, understanding why it's not working, trying to fix it and then perfectioning it, you take away the experience that will make you better at it[^l].

But then, introducing **human laziness**, the very thing that pushed us forward as a species, that has also big downsides. We are all *really good* at being lazy. Human progress is often justified by *"this will make us use less energy in some way"*. That's great. That's progress. We don't hunt anymore, we can grow crops next to our village, we live in an industrial automation world, and so on. You get the point I am making.

But now, it seems to me we are rushing toward the new worrying era of the "let's also **reduce how much we need to think**, after all that requires a lot of energy!"[^o]

*"But wait, wait, wait! Calculators, computers, smartphones, there are so many examples of things that makes us think 'less' and are now normal tools! You really are an old man, Alberto, you are complaining about the progress!"* 👴🏻

Maybe. Of course that's a valid counterpoint. It's also true that no longer doing math operations "by hand" or no longer writing with pen and paper is making us less proficient at those things, as some area of the brain is no longer activated. And don't get me wrong, I am the first one to say that this is not bad, it's making our life easier.

But, while solving a math operation with a calculator saves time, allowing for more thinking, having all the thinking done by AI tools is offsourcing several skills that are tied with producing a good result. Being able to convey properly ideas, refine them, use introspection and self-criticism before presenting a final result is completely **overridden by the usage of an AI tool**, while also *stealing* the entire learning experience.

Write a prompt, check the output summarily, write another prompt, check again the output, rewrite the prompt, and so on. The result of your work is no longer "yours", you just pull levers and push buttons convincing a black box to vomit something that seems like a good enough result, obtaining then an output that you like and that you can appropriate as yours.

Do we really want to **outsource our ability to think and to write** to an external tool? We are already losing skills on several fronts[^m]. We are spoiled by technology, that's not bad *per-se*, but the trade-off is between obtaining comfort with less energy spent and being less and less autonomous in everything.

The dystopia on the spaceship in [Wall-E](https://en.wikipedia.org/wiki/WALL-E) was laughable at, quite funny and seemed so far away: humans unable to walk, being pampered by an AI entity while being fed entertainment and spending their entire existence like that. Nowadays [it's making me laugh a bit less](https://www.youtube.com/watch?v=v2hTFoNnmNg).

### Not everyone enjoys the process

My daily job involves a lot of thinking and **writing**. I write tasks for other people, I write documentation, I communicate with other people trying to convey my thoughts in a clear manner. It's time consuming, it requires energy, but I like it. **I would not trade it off** only because an AI tool is faster than me. I don't see in it any "progress", but a **terrible way of losing skills**, while a company justifies the change with "increased efficiency" or "more profit", as always[^p].

The things I wrote will not resonate with everyone of you. A lot of people don't like their job or simply **don't care about it**. If thinking time can be avoided - therefore using less energy - why not? Why feel guilty about it? If this is your opinion, I cannot do anything to change that. I am simply trying to provide my perspective, and I can only hope that the bleak future I am writing about, where people are unable to do things autonomously and they use their time to write prompts for AI agents and tools, is really really far away.

## Now what? Why this post?

I don't expect to fix the world with a post, but the mixture of corporations pushing AI tools everywhere and the amount of people lost in the hype is really concerning.

I am not using any AI tools, at all. My suggestion is for you to do the same.

If not for my main point (getting dumber), you can read again what I listed in the <A href="#final-boundaries-and-assumptions">assumptions section</A>. These *"let's ignore that"* are very **real issues**, already enough on their own to re-evaluate the usage of all this AI stuff that is being fed to us.

I don't think I'll change my mind on this soon. I enjoy writing and thinking, in general. The idea of having a *"magic shortcut to do everything"* is a strong temptation, but I believe that the very act of creating and doing things on our own is what makes us get better, and it's **one of the most important things that makes us humans.**

Thank you for reading.

[^a]: Actually, I need to rant quite a lot. I wanted to write something about my feelings on the topic since a couple of years. Recently, seeing the general hype and the bubble not bursting (yet), I decided that it was time. My reticence in writing online (thing that I don't do anymore) is also due to the idea of this post being digested by several AI crawlers for training. That's going to happen for sure, and I don't like the idea, but here we are, who knows how everything I wrote will be ingested and vomited out in some way. What a time to be alive!
[^b]: As you can imagine, these opinions are negative. Big surprise. Let me simply tell a now obvious and quite sad thing: when in the past someone used to say "AI will replace jobs", nobody thought that the first ones to go would have been the artistic ones (drawers, photographers, visual artists, designers...)
[^c]: For example to write a plan/list of things to do in a mail, for which it was quite crucial that the author had clear in their head the overall activity, making it instead more verbose and more vague
[^e]: Recommended related read, a 1986 short story titled [The Feeling of Power](https://en.wikipedia.org/wiki/The_Feeling_of_Power) by Asimov. Plot summary: *in the distant future, humans live in a computer-aided society and have forgotten the fundamentals of mathematics, including even the rudimentary skill of counting...*
[^g]: I personally don't believe that current LLMs and AI tools have any kind of consciousness, but we could open a long discussion on the interesting question *"what are we then?"* and dig deeper talking about [Chinese rooms](https://en.wikipedia.org/wiki/Chinese_room), [stochastic parrots](https://en.wikipedia.org/wiki/Stochastic_parrot) and so on for hours
[^h]: Domotics still lives on, but not in the form it was hyped about in the beginning. Also, if we consider it progress, lots of people have Amazon or Google smart devices at home with always-on microphones (Echo, Alexa), sooo useful for telling you the weather saving the 10 extra seconds to pick up a smartphone - but hey, at least you will have more time to doomscroll Instagram or TikTok for hours! Great for your mental health!
[^d]: About this, nowadays it's extremely easy to use widely available AI tools to create fake accounts, and then generate and post comments/articles about how much AI is cool and the future. This is not an original idea, a theory about this, called the [dead internet theory](https://en.wikipedia.org/wiki/Dead_Internet_theory) was already around in 2016. Today, with chatbots always more and more accessible, it's quite likely to encounter AI generated content, from recipes websites up to newspapers. Notice that this is defined as a "conspiracy theory" but there is an [active discussion](https://en.wikipedia.org/wiki/Talk:Dead_Internet_theory#%22Conspiracy_theory%22) ongoing to remove the "conspiracy" part, that I totally understand (you should take a look at the long list of linked articles). Some people can still spot when something is not written by a human, but if AI writing "improves" to be indistinguishable, are we looking forward to an internet filled only of incorrect things and fake humans?
[^i]: And I wonder what these super good corporations use all this data for. Simply selling them for profit to ads companies? Or to profile people? Tinfoil hat mode on: is it really a stretch to imagine a corporation injecting some prompt to willingly "polarize" some people, convincing them of something, maybe extremize some ideas? Sounds like a "conspiracy theory" but it's really easy to implement, nowadays, with people using these tools
[^j]: This is my job and what I know better, I am sure there are plenty of other cases in which AI tools might "make the job easier", I'm not doubting that
[^k]: See also [constructivism](https://en.wikipedia.org/wiki/Learning_theory_(education)#Constructivism), a learning theory. *"[...] the learner faces a loss of equilibrium with their previous understanding, and this demands a change in cognitive structure. This change effectively combines previous and novel information to form an improved cognitive schema"*
[^l]: Another software engineering tale. When I started working, ~10 years ago, the first months were a lot of trial, debugging, errors, debugging, more errors, frustration, debugging, more errors, and so on, until the issue was identified and solved. This process is for sure demanding and frustrating, but it's essential to build a *[forma mentis](https://en.wiktionary.org/wiki/forma_mentis)*, learning to pin down a problem. A junior software engineer in today's world might simply use ChatGPT (or Copilot or another AI tool) to do a task without any need to understand how something is working, like this:

    {: style="text-align: center; padding: 0 20%;"}
    <img src="{{site.url | append: '/media/20260499/dev_box_eng.png'}}" title="Dev in the loop" class="responsive" onclick="window.open(this.src)">
    {: }
You can see the role of the developer as "the (stupid) hands". It's a mechanical part, writing a prompt, receiving an answer, copying and pasting stuff into a terminal, checking if it's producing errors, and repeating the process until "something works". If you like this idea, I don't think I can change your mind on the topic, we are completely different people

[^m]: I am the first that feels discomfort if I have to go to a new physical place without using Google Maps/Waze or any navigation system, instead of trying it out on my own. This is another skill I feel we are losing, maybe less "essential", but it's another example
[^n]: That being said, how much AI is concretely used in the company, it depends a lot. I am pretty sure the majority of the places that really use something AI-adjacent is just paying a huge amount of money to OpenAI or someone similar to use theirs APIs and show customers how cool their website chatbot is
[^o]: On this, I am pretty sure we are already in this era since several years. Social networks, smartphone addiction, people reading fewer books, do I need to mention something else? I am just concerned that AI tools will be another really big nail in the coffin of human ingenuity
[^p]: As a side-note, another potential reason for companies to have people use AI is to train models, and maybe in the future, pushing for a "replacement" agenda, using AI agents to replace workers. After all, companies are always about the usual buzzwords: efficiency, velocity, cost optimization... I still believe this would not work at all, but nothing will stop ideas fostered by the old usual stupid corporate mechanisms
[^q]: Regex already exist for doing advanced transformations, but this unit tests example is based on a real feedback I got from a colleague. Doing a lot of changes over several unit tests, in slightly different ways depending on the test itself, is quite easy with a well defined prompt
[^f]: Just going briefly into the topic, LLM (models) are the language models currently running under the hood of all modern chatbots (GPT, PaLM, Gemini, LLaMA). 'AI' is the "common term" nowadays to include all of them
[^r]: Shhh! Never ask "yes, but how are we going to make billions?" to these companies, it's not a nice question! The answer is obvious, no? With AI! Step 1: AI - Step 2: ??? - Step 3: PROFIT!
[^s]: Don't get me wrong here, stupidity is old as the first human! We had plenty of stupid people around before AI, and we will always have them until the last human dies. My concern is the overall trend and the fact that tools like these can <u>speed up</u> a lot how fast people are getting dumber