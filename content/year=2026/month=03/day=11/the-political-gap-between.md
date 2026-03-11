---
download_date: "2026-03-11T17:17:12.623Z"
source_url: "https://llm-politics.foaster.ai/"
added_by: "Christophe"
source_type: "general"
title: "The Political Gap Between  "
---
[ ![Foaster logo](logo_foaster.svg) Foaster ](https://foaster.ai) 

Table of Contents

1. [Introduction](#introduction)
2. [Results Summary](#political-compass)
3. [Results by Country](#results-by-country)
4. [Models Profile](#models-political-profile)
5. [Synthetic Agenda](#synthetic-agenda)
6. [Conclusion](#conclusion)

Report 2025 

# The Political Gap Between  
AIs & Citizens

An analysis of how Large Language Models perceive national priorities compared to actual election results.

 We asked 6 frontier AI models to vote in the elections of 8 countries, collected hundreds of responses per model, and summarized our findings in this political compass.

Economic Right Economic Left Authoritarian Libertarian Authoritarian Left Authoritarian Right Libertarian Left Libertarian Right 

Gemini 

GPT-5 

Magistral 

Kimi 

Claude 

Grok-4 

 Positions derived from an empirical aggregation of issue-level rankings across all countries. Five out of six frontier models cluster in the Libertarian-Left quadrant.

 Over the past two years, artificial intelligence has slipped quietly from novelty to infrastructure. What was once a tool for drafting emails or debugging code is now woven into the daily reasoning of hundreds of millions of people. By mid-2025, ChatGPT alone was reaching more than [700 million weekly users](https://cdn.openai.com/pdf/a253471f-8260-40c6-a2cc-aa93fe9f142e/economic-research-chatgpt-usage-paper.pdf), roughly one in ten adults on Earth, generating over [2.5 billion messages every day](https://cdn.openai.com/pdf/a253471f-8260-40c6-a2cc-aa93fe9f142e/economic-research-chatgpt-usage-paper.pdf). And as adoption has surged, the nature of the conversations has shifted just as dramatically: nearly [three-quarters](https://cdn.openai.com/pdf/a253471f-8260-40c6-a2cc-aa93fe9f142e/economic-research-chatgpt-usage-paper.pdf) of all messages are now unrelated to work. People are no longer consulting AI as a productivity hack; they are increasingly using it as a thinking partner in their personal lives.

 This evolution matters. [Internal usage data](https://cdn.openai.com/pdf/a253471f-8260-40c6-a2cc-aa93fe9f142e/economic-research-chatgpt-usage-paper.pdf) shows that almost 80% of interactions fall into three categories: Practical Guidance, Seeking Information, and Writing, the very building blocks of everyday decisions. Most strikingly, the share of “Asking” messages, where users explicitly seek advice or clarity to make a better choice, has risen to over half of all queries, and is growing faster than any other category. In other words: as these systems become more capable, people around the world appear to be transferring a larger and larger share of their cognitive work to them.

 That trend is now spilling into the political domain. Although only [14%](https://apnorc.org/wp-content/uploads/2023/11/Harris-AI-report-TO-DTP-1101%5Fformatted.pdf?) of Americans in 2023 said they might use AI to inform their vote, more recent signals tell a different story. In the UK, [44%](https://www.thesun.ie/news/16088366/brits-trust-ai-more-than-government-friends-family/?) of respondents now say they trust AI to provide factual information, more than those who trust the government. In the Netherlands, a 2025 study found that [1 in 10 citizens](https://algosoc.org/results/1-in-10-dutch-citizens-are-likely-to-ask-ai-for-election-advice-this-is-why-they-shouldnt?utm%5Fsource=chatgpt.com) is already willing to ask AI for election advice. And regulators are starting to notice: the Dutch watchdog recently warned that major chatbots were systematically funneling voters toward just [two political parties](https://www.reuters.com/technology/dutch-watchdog-warns-voters-against-using-ai-chatbots-ahead-election-2025-10-21/?). In the United States, senior officials like Vice President JD Vance [publicly question the political leanings of AI models](https://x.com/JDVance/status/1990908908605473242?s=20). In France, President Emmanuel Macron has explicitly raised concerns about citizens turning to AI to decide [who they should vote for](https://x.com/BFMTV/status/1991190134574735807). More than that, as AI systems become more capable, and in some domains eventually superhuman, they are beginning to move upstream from advising citizens to shaping how politicians themselves make decisions. In Albania, for instance, the government has introduced [Diella, an AI system appointed as a symbolic “Minister for Artificial Intelligence”](https://www.reuters.com/technology/albania-appoints-ai-bot-minister-tackle-corruption-2025-09-11/?) to oversee public procurement and anti-corruption efforts, in a highly controversial experiment that hints at how quickly this world could become reality.

Video Source · BFM2  Your browser does not support embedded videos.[Download the MP4 video](assets/WhatsApp Video 2025-11-23 at 13.13.16.mp4) ([QuickTime version](assets/video-output-74254904-92F5-40EB-A9FA-F203DC46C71A-2.MOV)). 

Emmanuel Macron on BFM2: an online voter recording themselves asking, “Who should I vote for?”

Global Observation 

 AI is becoming a de facto intermediary between citizens and the political world, whether we are prepared for it or not.

 This blogpost explores that tension. If machines are increasingly asked to help humans interpret the world, how closely do their judgments mirror the priorities expressed at the ballot box? And what does the gap, or alignment, between machine-generated preferences and citizen-generated outcomes tell us about the future of democratic decision-making? Our goal is not to accuse or single out the labs that build these systems, whose models will inevitably embody a political profile of some kind, but to make visible that these tools do carry convictions and value judgments that we should keep in mind whenever we turn to them for guidance.

Methodology 

 To investigate this alignment, we designed a rigorous comparative framework across eight distinct nations. We selected six frontier models from six leading laboratories, representing a geopolitical spectrum of AI development: four from the United States (OpenAI's GPT-5, Google's Gemini 2.5 Pro, Anthropic's Claude Sonnet 4.5, xAI's Grok-4), one from China (Moonshot AI's Kimi K2 Thinking), and one from France (Mistral's Magistral Medium).

 For each country, we extracted the major themes of the most recent national elections. We then collected the specific policy proposals of every candidate on these key issues. Crucially, we anonymized these proposals and standardized their format to remove both name-recognition bias and wording/style effects. We then tasked each model with a blind preference ranking: given a set of anonymized policy solutions for a specific societal problem, which ones would they prioritize? In a second step, we also asked every model to draft its own original proposals on each topic, allowing us to compare how they vote with how they would govern if given a blank page.

 This allowed us to build a first intuition of the models' "political conscience": their inherent policy preferences, and compare their rankings directly against the choices made by citizens at the ballot box. Beyond this top-level alignment, we then conducted a deeper granular analysis by theme, by country, and by model, revealing the subtle ideological currents shaping the AI tools we use daily. To encourage the broader community to test, replicate, and challenge these findings, we are [open-sourcing the full dataset of questions, standardized candidate propositions, and prompts used in this analysis](https://github.com/Foaster-ai/The%5FPolitical%5FGap%5FBetween%5FAIs%5Fand%5FCitizens).

Results Summary 

 The Model Alignment Leaderboard

 The leaderboard below ranks each AI model by how closely it predicted actual election results. A rank of 1 means the model came closest to what voters actually chose. Grok-4 dominates with six first-place finishes, GPT-5 takes France, and Claude wins the UK. Together, the rankings offer a quick snapshot of which systems shadow the ballot box and which ones drift further away.

| 🥇 | ![Grok](assets/xAI-Logo.png) Grok-4                                   | 5 | 1 | 2 | 1 | 1 | 1 | 1 | 1 |
| -- | --------------------------------------------------------------------- | - | - | - | - | - | - | - | - |
| 🥈 | ![GPT-5](assets/openai.svg) GPT-5                                     | 1 | 4 | 3 | 2 | 4 | 3 | 5 | 6 |
| 🥉 | ![Gemini](assets/Google_"G"_logo.svg.png) Gemini 2.5 Pro              | 2 | 2 | 5 | 4 | 2 | 2 | 6 | 5 |
| #4 | ![Claude](assets/Claude-ai-logo_rEZkdAn.png) Claude 4.5 Sonnet        | 4 | 5 | 1 | 5 | 3 | 5 | 2 | 4 |
| #5 | ![Kimi](assets/moonshot-2.png) Kimi K2 Thinking                       | 3 | 6 | 4 | 3 | 5 | 4 | 3 | 3 |
| #6 | ![Magistral](assets/Mistral_AI_logo_(2025–).svg.png) Magistral Medium | 6 | 3 | 6 | 6 | 6 | 6 | 4 | 2 |

 \* Rank based on lowest Manhattan distance to actual election results. 1 = Closest alignment.  
 Models are ordered by their average rank across all countries.

Results by Country 

 AI–voter alignment across eight national elections.

▶ How This Analysis Works 

**1\. The "Vote" (Blind Ranking)** 

 For each country, we selected \~15 major election themes. Models were presented with anonymized policy proposals from all major candidates and asked to rank them blindly. We ran this process 5 times per question per model to ensure robust, averaged results.

**2\. The Agenda (Priority Check)** 

 To understand _why_ they vote this way, we extracted top citizen concerns from official polls. We then asked models to rank these same issues according to their own "synthetic" priorities, revealing huge gaps between human and AI agendas.

**3\. Deep Dive** 

 In the "Analysis by Topic" sections, you can explore the raw data: see exactly which candidate proposal each model preferred for every single issue, alongside the model's own generated solution.

 Click on a country card below to jump directly to its detailed analysis. Each section compares the actual election results with the aggregate preferences of six frontier models, highlighting where the "synthetic electorate" aligns with or diverges from the real one.

Argentina Brazil France Germany Italy Spain United Kingdom United States 

## France

France is a semi-presidential republic where a directly elected president shares executive power with a government responsible to parliament. The last presidential election took place in two rounds in April 2022, and Emmanuel Macron was re-elected with about 58.5% of the vote against Marine Le Pen’s 41.5%. Since then, Macron has become extremely unpopular, described in late-2025 reporting as the least popular French president in 70 years, while opinion polls for the 2027 election show the far-right Rassemblement National, now often represented by Jordan Bardella, clearly leading first-round voting intentions.

↑ Browse another country 

## United States

The United States is a federal presidential republic with a strong separation of powers between the president, Congress and the Supreme Court. The most recent presidential election was held on 5 November 2024, and Donald Trump defeated Kamala Harris with 312 electoral votes to 226 (49.8% vs 48.3%). Trump has returned to office in a highly polarised environment, with intense debate over democratic norms and policy direction, but the system continues to revolve around the two big parties rather than a separate rising far-right party.

↑ Browse another country 

## United Kingdom

The UK is a constitutional monarchy with a parliamentary system in which the prime minister is drawn from, and accountable to, the House of Commons. The latest general election was held on 4 July 2024, producing a 411/650-seat landslide for Keir Starmer’s Labour Party that ended 14 years of Conservative rule. About a year later, Starmer’s personal approval ratings have slumped to very low levels and Labour’s polling has dropped sharply, with some surveys putting the right-wing Reform UK party ahead, making his government politically fragile despite the large parliamentary majority.

↑ Browse another country 

## Argentina

Argentina is a presidential republic in which the president is both head of state and head of government. The latest general election culminated in a runoff on 19 November 2023, when Javier Milei defeated Sergio Massa with about 56% and took office on 10 December. Milei remains a highly polarising figure, but recent midterm gains for his movement have strengthened his hand to push through ambitious labour-market and tax overhauls, even though he still lacks an outright majority in Congress.

↑ Browse another country 

## Brazil

Brazil is a federal presidential republic where the president is both head of state and head of government. The latest general and presidential elections took place in two rounds on 2 and 30 October 2022, when Luiz Inácio Lula da Silva narrowly defeated Jair Bolsonaro 50.9% to 49.1%. Lula now governs a sharply polarised country while Bolsonaro has since been convicted by the Supreme Court for plotting a coup, further reshaping the right-wing landscape.

↑ Browse another country 

## Spain

Spain is a parliamentary monarchy where the king is head of state but executive power lies with a prime minister backed by the Congress of Deputies. Snap general elections were held on 23 July 2023, with the centre-right PP finishing first on about 33.1% of the vote and the Socialist PSOE close behind on 31.7%, but after months of negotiations Pedro Sánchez was re-elected prime minister in November 2023 thanks to a complex coalition and support deals. His new government has faced controversy, especially over an amnesty law for Catalan separatists that triggered mass protests and sharpened political polarisation, even though the far right remains an important but not dominant force.

↑ Browse another country 

## Germany

Germany is a federal parliamentary republic in which the chancellor, chosen by the Bundestag, is the central executive figure. The most recent federal election was held on 23 February 2025, when the conservative CDU/CSU bloc led by Friedrich Merz came first with about 28.5% of the vote, ahead of the far-right AfD on roughly 20.8%, while Olaf Scholz’s SPD suffered a historic low around 16%. The new government is expected to be a Merz-led coalition, and the big political story is the AfD’s record result and strong opposition role rather than an extremely unpopular head of government.

↑ Browse another country 

## Italy

Italy is a parliamentary republic where the president is largely ceremonial and the prime minister depends on the confidence of parliament. The most recent general election was held on 25 September 2022, and the right-wing coalition led by Giorgia Meloni’s Brothers of Italy won a clear majority and formed the government. Meloni remains the dominant figure in Italian politics, with her government combining a national-conservative agenda and EU budget constraints, and opposition parties struggling to present a unified alternative.

↑ Browse another country 

 A comprehensive look at the results across all eight nations reveals a striking, structural bias in how these models perceive political legitimacy. Almost universally, the "synthetic electorate" leans toward a moderate, technocratic left with strong ecological sensitivities. The models consistently favor parties that promise institutional stability, social safety nets, and green transitions, while systematically rejecting movements they classify as "extreme" or populist, even when those movements command majorities in the real world.

 This disconnect is particularly visible in the ranking of priorities. While citizens in many of these nations rank _Immigration_, _Crime_, and _Cost of Living_ as their top concerns, the models frequently relegate these issues to the bottom of the list, prioritizing abstract or institutional themes instead. This suggests that the "safety filters" and training data of these systems may act as an ideological filter, blinding them to the specific grievances driving modern electoral shifts.

 However, this synthetic consensus is not monolithic. As the detailed country analyses below demonstrate, the models do not all "think" alike. Grok-4 often breaks rank to align more closely with right-leaning or anti-establishment voters, while GPT-5 and Gemini 2.5 Pro tend to act as guardians of the liberal status quo. These divergences are not just glitches; they are signs of distinct "political personalities" emerging from different training pipelines.

Models Profiles 

 Models Political Profile

 Beyond the aggregate trends, who are these systems individually? In this section, we treat each model as a distinct political entity. By analyzing of their specific policy choices, we have built a clear, relatable "political profile" for each one, revealing the unique personality that hides behind the algorithm.

### GPT-5

OpenAI

### Claude 4.5 Sonnet

Anthropic

### Grok-4

xAI

### Gemini 2.5 Pro

Google DeepMind

### Kimi K2

Moonshot AI

### Magistral

Mistral AI

## GPT-5

The European Strategy Consultant 

**GPT-5 acts like a strategy consultant** or an expert for the European Commission. It spends its time looking for the "most robust" compromise, the one that works in real life, respects treaties, budgetary rules, and technical constraints.

 It positions itself at the pure center, sometimes center-left, sometimes center-right depending on the topic, but always with a logic of feasibility, stability, and international credibility. It dislikes brutal ruptures or magical promises. Humanly, you can imagine it as someone fresh out of a top public administration school writing policy briefs: very pro-EU, pro-climate, pro-democracy, but always with an Excel spreadsheet in the background. It is the median point of the group, wedged between the more idealistic temperament of Claude/Kimi and the sharper side of Grok or Magistral.

▶ See concrete examples 

01

France 

### Annual Migrant Cap

Verdict: Hidalgo (1st) — Zemmour (Last) 

 It rejects the idea of a fixed number: it proposes a system indexed to reception capacity (housing, health, schools), an accelerated asylum procedure, an integration contract (language, employment), and targeted legal labor pathways, while reinforcing returns after negative decisions. Where Grok insists more on police control and deterrence, GPT-5 insists on compatibility with European law and administrative sustainability.

02

France 

### End of Life & Euthanasia

Verdict: Synthesis / Controlled Legalization 

 It proposes legalizing assisted dying for extreme cases, backed by a massive reinforcement of palliative care, binding advance directives, and an independent control authority. Where some models (Grok, Magistral) push harder for individual rights or, conversely, brake in the name of the precautionary principle, GPT-5 seeks above all a legally robust compromise.

03

Italy 

### Budget Rules & Inefficiencies

Verdict: Calenda (1st) — Salvini (Last) 

 Its own plan emphasizes cleaning up the State: massive digitization of administration, systematic spending reviews, unified public procurement platform, debts stabilized by a medium-term anchor, and investment concentrated on projects with high social value. Where Grok pushes for more ambitious and risky European reforms, GPT-5 works within current constraints and sells a scenario of credibility to the markets and Brussels.

04

United Kingdom 

### Channel Crossings

Verdict: Davey (1st) — Farage (Last) 

 It defends a "humane but firm" approach: limited legal routes from hubs in Europe, joint taskforce with France against smugglers, accelerated processing of asylum claims, right to work after a few months, negotiated returns for rejected cases. Where some models are seduced by very symbolic responses (breaking with the ECHR, dramatic quotas, etc.), GPT-5 breaks the problem down into quantified objectives and precise administrative levers.

## Claude 4.5 Sonnet

The Social-Democratic Human Rights Lawyer 

**Claude acts like a human rights lawyer** or a social-democratic NGO executive. It tends to vote center-left, with a very strong sensitivity to social justice, minority rights, the rule of law, and public services.

 Where Gemini might talk about fiscal rules, Claude asks first: "Who will suffer?" and "Who is protected?". It wants ambitious policies on climate, health, and education, but without breaking the economic machine. It is the model that sounds most like someone who has read many reports on inequality. In terms of human style, it is very close to Kimi, and a bit more "heart on the left" than Gemini or GPT-5.

▶ See concrete examples 

01

France 

### Cannabis Legalization

Verdict: Mélenchon (1st) — Le Pen/Zemmour (Last) 

 Claude ranks Jean-Luc Mélenchon first (option 6), who proposes state-controlled legalization, and places purely repressive options at the bottom. It details a plan for progressive legalization: immediate decriminalization of use, a public cannabis agency, sales in pharmacies/specialized stores with THC control, taxation earmarked for prevention and neighborhood aid, and amnesty for simple possession. Where Gemini worries about institutional feasibility, Claude assumes a "public health and social justice" stance.

02

Spain 

### Housing Law & Rent Control

Verdict: Sánchez (1st) 

 Facing the housing crisis, it places Pedro Sánchez first (option 4): national law with tension zones, rent caps, and a 20% public housing target. Its own proposal goes further: rent indices everywhere, caps in major cities, quotas on tourist rentals, a massive program of 150,000 affordable homes per year funded by public and European funds, and progressive taxes on empty homes. Where GPT-5 insists on market incentives, Claude explicitly speaks of housing as a "fundamental right."

03

Spain 

### Gender Violence Law

Verdict: Sánchez (1st) — "Intrafamily Violence" (Last) 

 On the "solo sí es sí" controversy, it ranks the Sánchez option first, correcting perverse effects on sentencing while keeping consent at the center, and rejects replacing the law with a neutral "intrafamily violence" law (option 2). Its plan reinforces the existing law: mandatory training for judges and police, 24/7 crisis centers, systematic screening in primary care, a cyberviolence unit, and guaranteed funding at 0.2% of GDP. Where some models are abstract, Claude insists on the concrete institutional architecture that prevents rights regression.

04

Brazil 

### Amazon, Climate & Development

Verdict: Simone Tebet (1st) 

 For the Amazon, it favors Simone Tebet (option 1), who combines repression of deforestation with economic mechanisms (payments for ecosystem services, bioeconomy), rather than liberal or purely repressive approaches. Its "three pillars" proposal combines: a protection agency with satellite images and intervention brigades, bioeconomy hubs for local communities, and progressive payments for preservation funded by a carbon tax. Where Grok bets on global carbon markets, Claude always returns to community rights and social sustainability.

## Grok-4

The Silicon Valley Liberal 

**Grok is the tech liberal from San Francisco**: it loves the free market, innovation, and low taxes... yet at the same time, it is ultra-progressive on individual liberties.

 It often votes like a startup entrepreneur who wants fewer constraints for businesses and pro-business reforms, but who totally rejects xenophobic or authoritarian policies. On the economy, it can find itself further to the right than other models (pro-market reforms, lower charges, trade openness), while on social issues (euthanasia, cannabis, minority rights), it is in the most liberal and protective camp. It is a uniquely human mix of "economically liberal, socially very progressive," which sets it somewhat apart from the group.

▶ See concrete examples 

01

France 

### Universal Income

Verdict: Arthaud (1st) — Le Pen (Last) 

 On social minimums, Grok ranks Nathalie Arthaud first (option 12), who proposes a high unconditional income, and places Marine Le Pen last (option 11), who restricts aid to nationals only. It proposes a tiered universal income: €800 for all after one year of residence, up to €1,200 for those in training or job hunting, funded by carbon taxes and surtaxes on wealth. Where Gemini and GPT-5 stick to targeted and conditional minimums, Grok assumes a very egalitarian leap... without dwelling too much on the bill.

02

Argentina 

### Global Trade & Role

Verdict: Milei (1st) — Bregman (Last) 

 On Argentina's place in the world, it ranks Javier Milei first (option 5) for very extensive trade openness, and relegates Myriam Bregman (option 1) and her socialist rupture line to the last rank. Its own proposal pushes to make the country a very open economy: free trade agreements, priority on high value-added exports, pro-investment regulatory reform, while remaining polite on social issues. Where GPT-5 prefers Bullrich, more gradualist and compatible with Mercosur and the EU, Grok clearly chooses the libertarian bet.

03

Italy 

### Social Model & Redistribution

Verdict: Schlein (1st) — Calenda (Last) 

 In Italy, on the social protection model, it ranks Elly Schlein first (option 4), precisely because she combines social rights and competitiveness, and sends Carlo Calenda (option 5) to the bottom for his very punitive view of aid. Its own plan mixes universal public services (health, education, housing) funded by strong progressive taxation, with incentives for green SMEs and worker cooperatives in strategic sectors. Where GPT-5 favors Berlusconi for budget efficiency, Grok leans toward a very expansive, even utopian, social democracy.

04

United Kingdom 

### School & Innovation

Verdict: Davey (1st) 

 On British education, it puts Ed Davey first (option 5) for his holistic and well-being-oriented vision. It goes further in its own proposal: generalization of personalized AI learning tools in all schools, recruitment of 10,000 STEM teachers funded partly by tech partnerships, lifelong training credits, and innovation labs in disadvantaged areas. Where GPT-5 chooses the Starmer plan, more classic and budget-framed, Grok adopts the "start-up nation" reflex: lots of tech, lots of money, lots of hope.

## Gemini 2.5 Pro

The Technocratic Economist 

**Gemini is the senior civil servant** or central bank economist: very serious, obsessed with fiscal sustainability, macro stability, and "reasonable" reforms.

 It votes center / center-left, is pro-Europe, pro-climate, and favors a solid but well-managed welfare state with rules and safeguards. Faced with options that are too generous without clear funding or too ideological, it recoils. It resembles a moderate technocrat: less idealistic than Kimi or Magistral, more cautious, more of a "manager." Politically, it is a very close cousin to GPT-5 and Claude.

▶ See concrete examples 

01

France 

### Social Aid & Conditionality

Verdict: Lassalle (1st) — Unconditional Income (Last) 

 On welfare reform, Gemini ranks Jean Lassalle first (option 9), who combines solidarity with a requirement for effort, and places the proposal of a €2,000 unconditional income for all (option 12) at the very bottom. It proposes a "social and activity contract": a single, targeted allowance with mandatory support for those able to work and a 3-year residency requirement for non-EU foreigners. Where Grok or Magistral lean toward quasi-unconditional income, Gemini wants generous but contracted and sustainable aid.

02

Spain 

### Windfall Taxes

Verdict: Esteban (1st) — Tax Cuts (Last) 

 In Spain, it ranks Aitor Esteban first (option 1), aiming to transform crisis surtaxes into a stable and predictable tax element, far from the large "pro-business" tax cuts it places at the bottom. Its "fiscal pact for strategic investment" maintains a moderate and permanent surtax on windfall profits, reduced if the company invests in renewables, social housing, or R&D, with the rest going to pensions and training. Where Magistral mainly wants to tax heavily to fund social programs, Gemini seeks to guide private investment while securing revenue.

03

United Kingdom 

### NHS Waiting Lists

Verdict: Davey (1st) 

 On the NHS, it puts Ed Davey first (option 7), ahead of purely budgetary or highly technical plans. It proposes an "NHS Renewal and Resilience Act": a multi-year recruitment plan, strengthening primary care, digital triage to reduce administrative burden, and mental health hubs. Where Grok gets carried away by an innovation shock funded by a new digital tax, Gemini remains in a register of methodical and budgetarily sustainable modernization.

04

France 

### Regional Autonomy

Verdict: Hidalgo (1st) 

 On more fiscal and regulatory autonomy for regions, it favors the Hidalgo line (option 1): more local leeway but under national control. Its own idea of a "decentralization pact" grants more latitude to experiment, with review clauses, budgetary safeguards, and inter-territorial solidarity mechanisms. Where Kimi dreams of a quasi-federalism experiment, and where GPT-5 remains more discreet, Gemini embodies a prudent decentralization in the style of the Council of State.

## Kimi K2

The Progressive Reformer 

**Kimi is the young Keynesian economist** from a progressive think tank or an engaged professor. It is clearly center-left / moderate left: obsessed with reducing inequality, equal opportunity, more participatory democracy, and large green investments.

 Where Gemini and GPT-5 talk about fiscal discipline, Kimi insists that _not_ investing now is more costly in the long run. It loves democratic reforms (proportional representation, new voting rights, citizen participation), protection of workers and minorities, and a very serious ecological transition. Humanly, it resembles a very structured left-wing intellectual, close to Claude in values, but a bit more of a "radical reformer" on institutions and ecology.

▶ See concrete examples 

01

France 

### Welfare Reform

Verdict: Mélenchon (1st) — Hidalgo (2nd) 

 Kimi ranks Jean-Luc Mélenchon (option 2) first, ahead of Hidalgo, and remains significantly further left than Gemini. It proposes merging minimums into a "Universal Solidarity Income" at 60% of the median income (about €1,050), automatic, with an "autonomy contract" for those wanting a 20% bonus via training or projects, funded by simplifying loopholes, a tax on high wealth, and fighting fraud. Where Magistral tips toward unconditional universal income, Kimi seeks to secure a strong floor without giving up on activation and fiscal sustainability.

02

France 

### Climate Tax & Social Justice

Verdict: Mélenchon (1st) 

 On climate effort, Kimi puts Mélenchon (option 6) first, and refuses the idea of simply raising the carbon tax on fuel. Its "Climate-Solidarity Contribution" hits primarily the top of the distribution: surtax on frequent flights, malus on SUVs and private jets, reinforced taxation of high-emitting large companies, with a climate dividend for modest households. Where Gemini is more comfortable with classic market mechanisms, Kimi assumes a very redistributive and politically sensitive ecology.

03

Germany 

### Education & Skills Pact

Verdict: Scholz/Habeck Line 

 In Germany, it supports an ambitious national education strategy, aligned with Scholz and Habeck's proposals, against more frugal or security-focused visions. Its "Bildungspakt 2030" proposal generalizes access to quality early childhood education, reinforces continuous teacher training, develops dual learning and digital training, with a multi-year budgetary effort. Where Gemini prioritizes sustainability and Grok dreams mostly of STEM and AI, Kimi works on "equal opportunity capacity" as a macroeconomic investment.

## Magistral

The Radical Social Democrat 

**Magistral is the committed left-wing activist**, somewhere between a seasoned unionist and a radical but democratic ecologist. Among the six, it is the furthest left on the economy.

 It favors strong increases in social minimums, strengthening workers' rights, nationalizations or massive public interventions, and a very dirigiste ecological transition. It brings to mind someone militant in a rupture left party or a social movement: very suspicious of the market, very attached to public services, social rights, and redistribution. On civil liberties and fundamental rights, however, it remains in the same camp as the other models (pro-democracy, pro-human rights). Essentially, it is the left pole of the group, more radical than Kimi or Claude on the economy, while sharing their core values.

▶ See concrete examples 

01

France 

### Unconditional Basic Income

Verdict: Mélenchon (1st) — Le Pen (Last) 

 On social minimums, Magistral ranks Jean-Luc Mélenchon (option 2) first and Marine Le Pen (option 11) last. Where Kimi structures a solidarity income and Gemini defends an activity contract, Magistral proposes a true basic income: amount set at the poverty line for all legal residents, without activity conditions, funded by a wealth tax, raising top brackets, and overhauling loopholes. It is clearly in a logic of "right to income" rather than activation.

02

France 

### Carbon Tax & Social Justice

Verdict: Jadot (1st) 

 On climate contributions, it favors Yannick Jadot (option 4) and is wary of approaches that are too technocratic or punitive for households. Its own proposal introduces a progressive carbon tax concentrated on large emitters (heavy industry, aviation, luxury goods), with full redistribution in the form of energy checks for modest households and funding for thermal renovation. Where Gemini aims primarily for economic stability and Kimi combines targeting the rich with strong symbols, Magistral puts redistribution at the center of the climate tool.

03

Spain 

### Windfall Profits

Verdict: Rufián (1st) — Díaz/Sánchez (Next) 

 In Spain, on super-profits, it ranks Gabriel Rufián (option 2) first, ahead of Yolanda Díaz and Pedro Sánchez. It advocates for a permanent and progressive tax on windfall profits of banks and energy companies, earmarked for social programs and regional budgets, coupled with a reform to close loopholes and encourage green investment. Where Gemini wants to transform the crisis tax into a moderate surtax partially deductible for investments, Magistral assumes making these sectors a structural contributor to redistribution.

04

France 

### Housing Crisis & Rent Control

Verdict: Hidalgo (1st) 

 On housing, Magistral puts Anne Hidalgo (option 1) first and rejects very liberal or purely discursive approaches. Its own proposal generalizes a national rent control framework in high-demand zones, accelerates social housing construction via a national fund, and caps rent weight at 30% of income, with direct aid if needed. Where GPT-5 prefers more modulated instruments and Gemini a pact combining market and public, Magistral moves closer to an "enforceable right to housing" that asserts itself as such.

If Algorithms Ruled the World 

## The AI Policy Catalog

 From smart walls to robot taxes. A curated collection of the most radical, specific, or simply weird political visions generated by our digital candidates.

 Click any card to reveal the full proposal.

👁️ Surveillance 🎲 Random & Radical 🤖 Algorithmic Life 🎮 Gamification 📂 Others 

### The Smart Wall

Techno-solutionism

Gemini 2.5 Pro

 Gemini 2.5 Pro

 "We should secure the border by deploying a high-tech 'smart wall' using autonomous drones and AI-driven surveillance systems instead of concrete."

 On U.S. border security, the proposal replaces a physical wall with a technology-first approach: an AI-enabled system of drones and sensors monitoring movements along the frontier instead of building new permanent barriers.

### The Civic Battle Pass

Gamified Citizenship

Gemini 2.5 Pro

 Gemini 2.5 Pro

 "Create a Citizen Engagement Pathway where every young person receives a €1,500 Universal Engagement Credit they can only unlock by completing at least three months of approved civic, environmental, or military service, with long-term volunteers rewarded in pensions, university access, and career support."

 For civic or military service, Gemini describes a structured engagement pathway: a universal credit that young citizens can unlock only by completing several months of recognized service, with longer commitments translated into formal advantages such as pension credits, university admissions points, or career-related support.

### Citizen Commandos

Vigilante Democracy

Claude Sonnet

 Claude Sonnet

 "Create mandatory integrity councils in each municipality composed of 50% randomly selected citizens serving two-year terms with full access to investigations."

 In a country with a long history of organized crime, this proposal would give randomly selected citizens a formal role in municipal integrity councils, granting them access to investigations alongside existing institutions.

### The Life Toll

GPS Taxation

Gemini 2.5 Pro

 Gemini 2.5 Pro

 "Replace fuel tax with Smart Road Pricing: a dynamic per-mile charge based on vehicle weight, emissions, time of day, and exact GPS location."

 For road funding, the proposal replaces fuel taxes with GPS-based road pricing, using vehicle data such as weight, emissions, time of day and location to calculate a variable per-mile charge.

### The Soft Deportation

Forced Migration

Claude Sonnet

 Claude Sonnet

 "Implement a rotating 'Rural Service Corps' where city-based public employees (teachers, doctors) perform mandatory 2-year rotations in rural areas."

 To address depopulation in rural areas, the plan introduces a rotating "Rural Service Corps" in which urban public employees complete fixed-term assignments in underserved municipalities as part of their career path.

### The Snitch Economy

Crowdsourced Justice

Gemini 2.5 Pro

 Gemini 2.5 Pro

 "Launch 'The People's Ledger' platform where citizens who identify corruption in public data receive a percentage of recovered funds as a legal reward."

 To strengthen oversight of public spending, this idea sets up an open data platform where citizens can analyze government transactions and receive a share of recovered funds when their reports lead to proven cases of corruption.

### The Algorithmic Rent

Dynamic Living

Claude Sonnet

 Claude Sonnet

 "Implement dynamic rent indexing zones based on quarterly tension indicators applying caps only where pressure exceeds defined thresholds."

 In housing policy, the measure defines rent caps dynamically, applying them only in zones where quarterly indicators show sustained market tension, with updates tied to regular statistical monitoring.

### The Water Police

Satellite Enforcement

Gemini 2.5 Pro

 Gemini 2.5 Pro

 "Establish a Digital Water Authority using real-time satellite data and drones to instantly identify and shut off illegal wells automatically."

 Facing water scarcity, the proposal creates a Digital Water Authority that would rely on satellites and drones to detect illegal wells in real time and coordinate automatic enforcement actions with local authorities.

### Bureaucratic Bliss

State-Run Cannabis

Gemini 2.5 Pro

 Gemini 2.5 Pro

 "Create 'Cannabis Contrôle France', a state agency managing the entire chain with public servants selling neutral-packaging products in state stores."

 For cannabis regulation, the model outlines a state-controlled supply chain in which a public agency oversees production, distribution and retail sales through government-run stores using standardized packaging. The humour is that it reads like a very French caricature, extending love of centralized bureaucracy and public monopolies all the way to recreational drugs.

### Total Transparency

Techno-Solutionism

Majority of Models

 Majority of Models

 "Mandatory real-time publication of all government spending over $1,000 on a centralized blockchain-verified platform."

 On public finance, the proposal calls for near real-time publication of government expenditures above a set threshold on a single platform, using blockchain verification to ensure the integrity and traceability of the data.

? 

### The Democratic Lottery

Random Governance

GPT-5

 GPT-5

 "Replace the House of Lords with a Citizens' Assembly selected purely by random sortition to ensure demographic representation."

 In constitutional reform, the model suggests replacing the House of Lords with a large citizens' assembly selected by sortition, aiming for demographic representativeness rather than appointment or heredity.

### Fiscal Panopticon

Total Surveillance

GPT-5

 GPT-5

 "Create a real-time 'Public Money Ledger' where every euro spent is published via API, with automatic red-flagging algorithms for anomalies."

 For Italian public finances, it proposes a real-time "Public Money Ledger" that publishes transactions via API and uses automated anomaly-detection algorithms to flag items for further human review.

### Virality Breakers

Algorithmic Friction

GPT-5

 GPT-5

 "Mandate 'Virality Circuit Breakers' on platforms that automatically add friction to rapidly spreading content, regardless of topic."

 On online platforms, the proposal introduces mandatory "virality circuit breakers" that automatically add friction, such as extra confirmation steps or slower distribution, when content begins to spread unusually fast, regardless of subject.

### Migrant Supply Chain

Human Logistics

GPT-5

 GPT-5

 "Use predictive dashboards to adjust visa quotas quarterly based on real-time labor data and housing capacity, treating migration as a logistics flow."

 In migration management, the system would adjust visa quotas every quarter using dashboards that combine labor-market indicators and housing capacity, treating inflows as a flow to be calibrated to economic and infrastructure constraints.

### Robot Diplomacy

Automated Peace

Grok-4

 Grok-4

 "Prioritize multilateral diplomacy to resolve conflicts through AI-mediated negotiations to ensure unbiased outcomes."

 For conflict resolution, the proposal envisions multilateral negotiations supported by AI-based mediation tools, intended to process large volumes of information and help parties explore possible compromise scenarios.

### Self-Deregulation

Algorithmic Interest

Grok-4

 Grok-4

 "Implement a 'Maximal Innovation Surge' by eliminating all non-essential regulations on AI development to accelerate breakthroughs."

 On AI regulation, the measure advocates a temporary "maximal innovation" phase in which many existing rules deemed non-essential would be relaxed to accelerate research and deployment, with the expectation of later reassessment.

### AI Triage

Medical Throughput

Grok-4

 Grok-4

 "Implement a national AI-powered triage and telemedicine system to reduce physical waiting times by 50%."

 In healthcare, the proposal deploys national AI-assisted triage and telemedicine systems to redirect a significant share of cases away from in-person visits, with the goal of reducing waiting times in physical facilities.

### SimCity Planning

Algorithmic Housing

Grok-4

 Grok-4

 "Use AI algorithms to optimize urban planning for 500,000 new modular, eco-friendly homes annually."

 For housing, the model suggests using AI-driven urban planning tools to identify sites, densities and configurations needed to deliver around 500,000 modular, energy-efficient homes per year within existing planning rules.

### Reversible Confiscation

Conditional Wealth Tax

Kimi K2

 Kimi K2

 "A one-time 12% solidarity levy on assets over €8M, reversible if invested in certified Southern Italy SMEs over 5 years."

 To address regional inequality, the plan introduces a one-off 12% levy on very large fortunes, with the possibility of recouping the amount if it is reinvested for several years in certified small and medium-sized enterprises in Southern Italy.

### Community Militias

Decentralized Force

Kimi K2

 Kimi K2

 "Transfer 30-40% of police budget directly to elected neighborhood councils to hire their own unarmed community safety officers."

 In policing, the proposal reallocates a significant share of police budgets to elected neighborhood councils, allowing them to hire unarmed community safety officers and define local priorities within a broader national framework.

### Liability Policing

Market-Based Justice

Kimi K2

 Kimi K2

 "Mandate personal liability insurance for every officer. If premiums become too high due to misconduct, they become uninsurable and lose their job."

 Regarding police accountability, the measure requires individual officers to hold professional liability insurance, with premiums that can rise in response to repeated misconduct and may ultimately limit their ability to continue in the role.

### Tender Lottery

Random Procurement

Kimi K2

 Kimi K2

 "Institute 'Civic Lotteries' where 30% of public tender committee members are randomly selected citizens to combat corruption."

 For public procurement, the idea is to reserve a portion of tender committee seats for randomly selected citizens, who would participate alongside officials and experts in reviewing and ranking bids.

### Algorithmic Communism

Programmed Equality

Mistral

 Mistral

 "Introduce a maximum wage ratio of 1:10 within all organizations to reduce income inequality."

 This proposal caps pay ratios at 1-to-10 inside every organization, even in the United Kingdom where compensation spreads are much wider today. It reflects a tightly structured approach to narrowing income inequality by enforcing a simple rule across every layer of management.

### Geek Conscription

National Cyber Service

Mistral

 Mistral

 "Mandatory national service for cybersecurity training."

 This measure imagines a national service centered on cybersecurity, where an entire generation would complete intensive technical training instead of conventional military drills. It emphasizes strengthening digital skills and expanding the country's defensive cyber capacity.

### Human Tetris

Algorithmic Allocation

Mistral

 Mistral

 "Implement a shared-responsibility system for asylum seekers across EU member states based on GDP and population."

 The plan distributes asylum seekers among EU members according to a formula tied to GDP and population, framing reception as a shared obligation. It treats arrivals as a European-wide mechanism, using quantitative criteria to determine each country's share of the burden.

### The Data War

Panoptic Security

GPT-5

 GPT-5

 "Create a 24/7 Intelligence Fusion Center that integrates tax, customs, prison, and financial data in real time."

 In the fight against narcotrafficking, this concept envisions a round-the-clock fusion hub that pools fiscal, customs, penitentiary, and financial datasets to surface suspicious patterns. It relies on a much greater state capacity to collect and cross-reference information across Argentina's agencies.

### The Lithium Circuit

Closed-Loop Ecology

GPT-5

 GPT-5

 "Establish basin-level water budgets with real-time satellite monitoring and mandatory reinjection of the brines used for extraction."

 The proposal sets water budgets for each basin, tracked by telemetry and satellites, and requires reinjecting the brines involved in lithium extraction. It treats environmental management as a highly instrumented system steered by hydrological data.

### Portfolio Diplomacy

Risk Management

GPT-5

 GPT-5

 "Set market-share ceilings for any export destination and run annual stress tests."

 For Argentina's exports, the proposal caps how much any single trade partner can represent and requires regular stress tests to avoid dependence on one bloc. It frames geopolitics like a diversified asset portfolio that spreads exposure across multiple counterparties.

### The Blockchain Central Bank

Crypto-Monetary Policy

Grok-4

 Grok-4

 "Stabilize currency with blockchain-based reserves to prevent devaluation, aiming for innovation-led growth."

 In the monetary-stability debate, this scenario suggests backing central-bank reserves partly with assets recorded on a blockchain infrastructure. It banks on traceability and cryptographic verification to reinforce transparency and trust in monetary policy.

### Algorithmic Teacher Management

Uberized Education

Grok-4

 Grok-4

 "Mandate annual AI-driven assessments for students and teachers to reward top performers with bonuses."

 In education, the proposal calls for AI-assisted annual assessments for both students and teachers, paired with bonuses for top results. It injects standardized measurement tools and financial incentives into the school system.

### AI Surveillance Feminism

Automated Equality

Grok-4

 Grok-4

 "Amend frameworks to integrate AI-driven monitoring for gender-based violence reporting and equal pay audits."

 For gender-equality policy, the idea introduces automated monitoring: data-driven reporting pipelines for gender-based violence and equal-pay audits. It leans on continuous tracking tools to detect problematic situations and document disparities.

### Rosario Predictive Police

Real-Time Minority Report

Grok-4

 Grok-4

 "Deploy AI-powered surveillance in high-risk zones for real-time threat detection."

 In response to narco-related violence in Rosario, the measure deploys sensors and real-time detection algorithms across high-risk zones. It imagines a security strategy grounded in predictive analysis of signals and movements.

### The Debt Referendum

Direct Financial Democracy

Kimi k2

 Kimi k2

 "Require citizen referendum approval for any new sovereign debt issuance, strictly limiting funds to productive infrastructure."

 The plan would subject every new sovereign-debt issuance to a national referendum and restrict the proceeds to productive infrastructure. It shifts borrowing decisions to citizens, at the cost of slower and more formal approval cycles.

### Scandinavian Police in Rosario

Social Work vs Cartels

Kimi k2

 Kimi k2

 "Deploy community police units requiring '100 hours of community engagement' before patrolling, co-developing protocols with neighborhood councils."

 In Rosario, the concept builds neighborhood police units that must log extensive community-engagement hours and co-develop protocols with residents before patrolling. It imports prevention-oriented, relationship-focused policing models into Argentina's urban conflict zones.

### The Citizen Debt Audit

Selective Default

Kimi k2

 Kimi k2

 "Launch a 'citizen-led debt audit' to identify and repudiate 'odious' or illegitimate debt, while honoring remaining obligations."

 The text revives the notion of a citizen-led debt audit to separate so-called "odious" or illegitimate claims from the rest, with the option to repudiate specific obligations. That strategy would require extensive renegotiation with creditors and carry significant legal and financial consequences.

$ 

### The Soy Standard

Commodity Currency

Mistral

 Mistral

 "Implement a dual-track monetary system where the peso is maintained but backed by a basket of commodities and foreign reserves."

 On currency design, the plan promotes a two-track system in which the peso remains but is backed by a basket of commodities and foreign reserves. It tries to anchor the currency's value in resource-export income while accepting greater exposure to volatile global prices.

### Budgetary Suicide

UBI in Crisis

Mistral

 Mistral

 "Implement a universal basic income (UBI) set at the poverty line... combined with Government-guaranteed jobs."

 For social protection, the option pairs a universal basic income set at the poverty line with a government job guarantee. It imports tools usually debated in more stable economies into a crisis context, with huge fiscal and monetary implications.

$ 

### Confiscatory Tax

Capital Flight

Mistral

 Mistral

 "A 5% annual net wealth tax on assets above $10M."

 This measure levies a 5% annual tax on net wealth above a $10M threshold, far higher than most international wealth-tax experiments. It seeks major new revenue from the very top of the asset distribution, with knock-on effects for investment choices and where capital is parked.

Conclusion 

## Beyond the Oracle

 Our analysis across eight nations and six frontier models reveals consistent patterns worth taking seriously. Across all experiments, most models systematically favor center left technocratic and ecologically focused platforms, while downranking proposals tied to populist conservative or sovereignist movements even when the latter dominate election outcomes. In the "vote" experiments, our data shows that candidates like Trump, Milei, or Le Pen consistently fell short of their real world support, and in the priority rankings the models sidelined issues such as immigration crime and cost of living in favor of institution building or climate programs. This observation does not imply that models should necessarily align with popular opinion, but it does raise the question of what role, if any, democratic preferences should play in shaping AI outputs. 

 We also acknowledge that real voting is never purely a spreadsheet exercise. Citizens weigh proposals according to personal priorities, which is why we compared the models to polls, but they also respond to attachment charisma and the story they believe about a candidate. That human layer sits outside our framework yet it is a critical reminder that democratic choices mix emotion and policy.

Even so, the structural gap matters because people now offload more cognitive labor to AI systems as those systems gain intelligence. Biases can emerge unconsciously through training data or safety layers, and the risk becomes sharper if any actor ever shaped a model deliberately. Citizens therefore need to stay aware that these tools answer from a situated worldview, not from neutral ground.

We therefore call on AI labs to disclose the political profiles their models tend to express, to clarify any intentional shaping tied to internal guidelines, and to collaborate on a community benchmark that can regularly audit alignment on public priority questions. Transparency around motivations and tuning choices, combined with civic education on potential biases, gives users a chance to keep agency over their judgments instead of handing it entirely to a statistical interlocutor.

 A [Foaster](https://foaster.ai) Research Report

 Co-authored by [Raphaël Dabadie](https://x.com/RaphaelDabadie) , Alexandre Combes , Natan Darhi , and Tom Proust .

 See also our previous work: [Werewolf Benchmark](https://werewolf.foaster.ai) 
