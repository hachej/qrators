---
download_date: "2026-03-07T06:36:50.095Z"
source_url: "https://simonwillison.net/2026/Mar/4/qwen/"
added_by: "Christophe"
source_type: "general"
title: "[Simon Willison’s Weblog](/)"
---
# [Simon Willison’s Weblog](/)

[Subscribe](https://simonwillison.net/2026/Mar/4/qwen/about/#subscribe) 

**Sponsored by:** Postman — Every API your agents depend on, mapped and monitored. [See what's new](https://fandf.co/40IFB7j) 

## Something is afoot in the land of Qwen

4th March 2026

I’m behind on writing about Qwen 3.5, a truly remarkable family of open weight models released by Alibaba’s Qwen team over the past few weeks. I’m hoping that the 3.5 family doesn’t turn out to be Qwen’s swan song, seeing as that team has had some very high profile departures in the past 24 hours.

It all started with [this tweet](https://twitter.com/JustinLin610/status/2028865835373359513) from Junyang Lin ([@JustinLin610](https://twitter.com/JustinLin610)):

> me stepping down. bye my beloved qwen.

Junyang Lin was the lead researcher building Qwen, and was key to releasing their open weight models from 2024 onwards.

As far as I can tell a trigger for this resignation was a re-org within Alibaba where a new researcher hired from Google’s Gemini team was put in charge of Qwen, but I’ve not confirmed that detail.

More information is available in [this article from 36kr.com](https://www.36kr.com/p/3708425301749891). Here’s [Wikipedia on 36Kr](https://en.wikipedia.org/wiki/36Kr) confirming that it’s a credible media source established in 2010 with a good track record reporting on the Chinese technology industry.

The article is in Chinese—here are some quotes translated via Google Translate:

> At approximately 1:00 PM Beijing time on March 4th, Tongyi Lab held an emergency All Hands meeting, where Alibaba Group CEO Wu Yongming frankly told Qianwen employees.
> 
> Twelve hours ago (at 0:11 AM Beijing time on March 4th), Lin Junyang, the technical lead for Alibaba’s Qwen Big Data Model, suddenly announced his resignation on X. Lin Junyang was a key figure in promoting Alibaba’s open-source AI models and one of Alibaba’s youngest P10 employees. Amidst the industry uproar, many members of Qwen were also unable to accept the sudden departure of their team’s key figure.
> 
> “Given far fewer resources than competitors, Junyang’s leadership is one of the core factors in achieving today’s results,” multiple Qianwen members told 36Kr. \[...\]
> 
> Regarding Lin Junyang’s whereabouts, no new conclusions were reached at the meeting. However, around 2 PM, Lin Junyang posted again on his WeChat Moments, stating, “Brothers of Qwen, continue as originally planned, no problem,” without explicitly confirming whether he would return. \[...\]

That piece also lists several other key members who have apparently resigned:

> With Lin Junyang’s departure, several other Qwen members also announced their departure, including core leaders responsible for various sub-areas of Qwen models, such as:
> 
> Binyuan Hui: Lead Qwen code development, principal of the Qwen-Coder series models, responsible for the entire agent training process from pre-training to post-training, and recently involved in robotics research.
> 
> Bowen Yu: Lead Qwen post-training research, graduated from the University of Chinese Academy of Sciences, leading the development of the Qwen-Instruct series models.
> 
> Kaixin Li: Core contributor to Qwen 3.5/VL/Coder, PhD from the National University of Singapore.
> 
> Besides the aforementioned individuals, many young researchers also resigned on the same day.

Based on the above it looks to me like everything is still very much up in the air. The presence of Alibaba’s CEO at the “emergency All Hands meeting” suggests that the company understands the significance of these resignations and may yet retain some of the departing talent.

#### Qwen 3.5 is exceptional [#](https://simonwillison.net/2026/Mar/4/qwen/2026/Mar/4/qwen/#qwen-3-5-is-exceptional)

This story hits particularly hard right now because the Qwen 3.5 models appear to be _exceptionally_ good.

I’ve not spent enough time with them yet but the scale of the new model family is impressive. They started with [Qwen3.5-397B-A17B on February 17th](https://simonwillison.net/2026/Feb/17/qwen35/)—an 807GB model—and then followed with [a flurry of smaller siblings](https://huggingface.co/collections/Qwen/qwen35) in 122B, 35B, 27B, 9B, 4B, 2B, 0.8B sizes.

I’m hearing positive noises about the 27B and 35B models for coding tasks that still fit on a 32GB/64GB Mac, and I’ve tried the 9B, 4B and 2B models and found them to be notably effective considering their tiny sizes. That 2B model is just 4.57GB—or as small as 1.27GB quantized—and is a full reasoning and multi-modal (vision) model.

It would be a real tragedy if the Qwen team were to disband now, given their proven track record in continuing to find new ways to get high quality results out of smaller and smaller models.

If those core Qwen team members either start something new or join another research lab I’m excited to see what they do next.

Posted [4th March 2026](https://simonwillison.net/2026/Mar/4/qwen/2026/Mar/4/) at 3:50 pm · Follow me on [Mastodon](https://fedi.simonwillison.net/@simon), [Bluesky](https://bsky.app/profile/simonwillison.net), [Twitter](https://twitter.com/simonw) or [subscribe to my newsletter](https://simonwillison.net/about/#subscribe)

## More recent articles

* [Can coding agents relicense open source through a “clean room” implementation of code?](https://simonwillison.net/2026/Mar/4/qwen/2026/Mar/5/chardet/) \- 5th March 2026
* [I vibe coded my dream macOS presentation app](https://simonwillison.net/2026/Mar/4/qwen/2026/Feb/25/present/) \- 25th February 2026

This is **Something is afoot in the land of Qwen** by Simon Willison, posted on [4th March 2026](https://simonwillison.net/2026/Mar/4/qwen/2026/Mar/4/).

[ ai1894 ](https://simonwillison.net/2026/Mar/4/qwen/tags/ai/) [ generative-ai1679 ](https://simonwillison.net/2026/Mar/4/qwen/tags/generative-ai/) [ llms1645 ](https://simonwillison.net/2026/Mar/4/qwen/tags/llms/) [ qwen50 ](https://simonwillison.net/2026/Mar/4/qwen/tags/qwen/) [ ai-in-china90 ](https://simonwillison.net/2026/Mar/4/qwen/tags/ai-in-china/) 

**Next:** [Can coding agents relicense open source through a “clean room” implementation of code?](https://simonwillison.net/2026/Mar/4/qwen/2026/Mar/5/chardet/)

**Previous:** [I vibe coded my dream macOS presentation app](https://simonwillison.net/2026/Mar/4/qwen/2026/Feb/25/present/)

###  Monthly briefing

 Sponsor me for **$10/month** and get a curated email digest of the month's most important LLM developments.

 Pay me to send you less!

[ Sponsor & subscribe](https://github.com/sponsors/simonw/) 

* [Disclosures](https://simonwillison.net/2026/Mar/4/qwen/about/#disclosures)
* [Colophon](https://simonwillison.net/2026/Mar/4/qwen/about/#about-site)
* ©
* [2002](https://simonwillison.net/2026/Mar/4/qwen/2002/)
* [2003](https://simonwillison.net/2026/Mar/4/qwen/2003/)
* [2004](https://simonwillison.net/2026/Mar/4/qwen/2004/)
* [2005](https://simonwillison.net/2026/Mar/4/qwen/2005/)
* [2006](https://simonwillison.net/2026/Mar/4/qwen/2006/)
* [2007](https://simonwillison.net/2026/Mar/4/qwen/2007/)
* [2008](https://simonwillison.net/2026/Mar/4/qwen/2008/)
* [2009](https://simonwillison.net/2026/Mar/4/qwen/2009/)
* [2010](https://simonwillison.net/2026/Mar/4/qwen/2010/)
* [2011](https://simonwillison.net/2026/Mar/4/qwen/2011/)
* [2012](https://simonwillison.net/2026/Mar/4/qwen/2012/)
* [2013](https://simonwillison.net/2026/Mar/4/qwen/2013/)
* [2014](https://simonwillison.net/2026/Mar/4/qwen/2014/)
* [2015](https://simonwillison.net/2026/Mar/4/qwen/2015/)
* [2016](https://simonwillison.net/2026/Mar/4/qwen/2016/)
* [2017](https://simonwillison.net/2026/Mar/4/qwen/2017/)
* [2018](https://simonwillison.net/2026/Mar/4/qwen/2018/)
* [2019](https://simonwillison.net/2026/Mar/4/qwen/2019/)
* [2020](https://simonwillison.net/2026/Mar/4/qwen/2020/)
* [2021](https://simonwillison.net/2026/Mar/4/qwen/2021/)
* [2022](https://simonwillison.net/2026/Mar/4/qwen/2022/)
* [2023](https://simonwillison.net/2026/Mar/4/qwen/2023/)
* [2024](https://simonwillison.net/2026/Mar/4/qwen/2024/)
* [2025](https://simonwillison.net/2026/Mar/4/qwen/2025/)
* [2026](https://simonwillison.net/2026/Mar/4/qwen/2026/)
