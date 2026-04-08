---
download_date: "2026-04-08T17:10:52Z"
source_url: "https://ai.meta.com/blog/introducing-muse-spark-msl/"
added_by: "Christophe"
source_type: "blog"
title: "Introducing Muse Spark: Scaling Towards Personal Superintelligence"
---
# Introducing Muse Spark: Scaling Towards Personal Superintelligence

Today, we're excited to introduce Muse Spark, the first in the Muse family of models developed by Meta Superintelligence Labs. Muse Spark is a natively multimodal reasoning model with support for tool-use, visual chain of thought, and multi-agent orchestration.

Muse Spark is the first step on our scaling ladder and the first product of a ground-up overhaul of our AI efforts. To support further scaling, we are making strategic investments across the entire stack, from research and model training to infrastructure, including the Hyperion data center.

In this post, we'll first explore Muse Spark's new capabilities and applications. After these results, we'll look behind the curtain at the scaling axes driving our progress toward personal superintelligence.

Muse Spark is available today at [meta.ai](https://meta.ai/) and the Meta AI app. We're opening a private API preview to select users.

## Capabilities for Personal Superintelligence

Muse Spark offers competitive performance in multimodal perception, reasoning, health, and agentic tasks. Meta says it continues to invest in areas with current performance gaps, such as long-horizon agentic systems and coding workflows.

With larger models in development, these results demonstrate that the stack is scaling effectively.

![Muse Spark capability chart](https://scontent-sof1-1.xx.fbcdn.net/v/t39.2365-6/665924660_1383428270484689_5397336232917598143_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=40dSBB4nSr4Q7kNvwG23Xo9&_nc_oc=Adqq439LSB-t3OUxHxJVjbtXKzuWZnSe1qzn5FKGg8JT2jNMf-JqDd-ZlIF8KQ_xdzbn-m3LZT06q3rOJI3nBP4P&_nc_zt=14&_nc_ht=scontent-sof1-1.xx&_nc_gid=-Jln8QmnA8vRBd6kxZ1mrQ&_nc_ss=7a389&oh=00_Af2DbVwhoodjRODynh6MwebTRH2Gv_vd1icQUhIbFd6oSw&oe=69F0D197)

Meta is also releasing Contemplating mode, which orchestrates multiple agents that reason in parallel. This allows Muse Spark to compete with the extreme reasoning modes of frontier models such as Gemini Deep Think and GPT Pro. Contemplating mode provides significant capability improvements in challenging tasks, achieving 58% in Humanity's Last Exam and 38% in FrontierScience Research.

![Contemplating mode chart](https://scontent-sof1-2.xx.fbcdn.net/v/t39.2365-6/667772255_4176091915975874_5759873660396683226_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=hPLLv18ZLD8Q7kNvwHGtBOn&_nc_oc=AdoqiTG14EKV99fquxIfJSX0FGLjqP9puQfOX7VmB1MfaraWQdCk0c5gTCHY_G38BsNKTLqNUrslUcefddZibjoZ&_nc_zt=14&_nc_ht=scontent-sof1-2.xx&_nc_gid=-Jln8QmnA8vRBd6kxZ1mrQ&_nc_ss=7a389&oh=00_Af0StE5ohUcnasjorWn5QP8xcv1PnO46f3ryXsfS6SlqCw&oe=69F0E6D7)

## Applications

Muse Spark is the first step toward a personal superintelligence that understands your world. From analyzing your immediate environment to supporting your wellness, its reasoning capabilities are positioned as enabling highly personal use cases.

**Multimodal.** Muse Spark is built from the ground up to integrate visual information across domains and tools. It achieves strong performance on visual STEM questions, entity recognition, and localization. Meta highlights interactive experiences such as creating minigames or troubleshooting home appliances with dynamic annotations.

**Health.** One major application of personal superintelligence is helping people learn about and improve their health. To improve Muse Spark's health reasoning capabilities, Meta says it collaborated with more than 1,000 physicians to curate training data that enables more factual and comprehensive responses. Muse Spark can generate interactive displays that explain health information such as the nutritional content of foods or muscles activated during exercise.

## Scaling Axes

To build personal superintelligence, Meta says model capabilities should scale predictably and efficiently. It tracks Muse Spark's scaling properties along three axes: pretraining, reinforcement learning, and test-time reasoning.

**Pretraining.** The pretraining phase is where Muse Spark acquires its core multimodal understanding, reasoning, and coding abilities, which become the foundation that reinforcement learning and test-time compute build upon.

Over the last nine months, Meta says it rebuilt its pretraining stack with improvements to model architecture, optimization, and data curation. It claims the new recipe can reach the same capabilities with over an order of magnitude less compute than Llama 4 Maverick and is significantly more efficient than leading base models used for comparison.

![Pretraining scaling chart](https://scontent-sof1-2.xx.fbcdn.net/v/t39.2365-6/667580961_1557898095990047_8798526624523628592_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=2NIXEgFnqLgQ7kNvwEquOSz&_nc_oc=AdrL8GrpFGm60Ut1s_vEM5I9iQaUfpRCaacUlzs8XJUeJ6mZkHCSgslJwC24S2HxNAvm_G1XubvwyEjVHc2QVrch&_nc_zt=14&_nc_ht=scontent-sof1-2.xx&_nc_gid=-Jln8QmnA8vRBd6kxZ1mrQ&_nc_ss=7a389&oh=00_Af1iDkYMkKKWon8bDCJL78hYA1wAL5YhikzEhA0XObMxCA&oe=69F0DF63)

**Reinforcement Learning.** After pretraining, reinforcement learning leverages compute to scalably amplify model capabilities. Meta says its new stack delivers smooth, predictable gains despite the instability that often affects large-scale RL.

It reports log-linear growth in pass@1 and pass@16 on training data, which it says indicates improved reliability without compromising reasoning diversity. Accuracy growth on a held-out evaluation set is presented as evidence that these gains generalize beyond the training set.

![Reinforcement learning chart](https://scontent-sof1-2.xx.fbcdn.net/v/t39.2365-6/668545857_966866959131364_8191359885166725237_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=CLBpkO-jCigQ7kNvwETNUU1&_nc_oc=AdrnFNrWHgB8bsrvqHyPMXXYpcdO6hQ7fx_AhkJneIDT4G0M524cNSVxnZ1kfjp6jVxy_V3jaXBVo4vKhSYQacUH&_nc_zt=14&_nc_ht=scontent-sof1-2.xx&_nc_gid=-Jln8QmnA8vRBd6kxZ1mrQ&_nc_ss=7a389&oh=00_Af3mOpbZI87lZpgRq3Nkmnp2fTajrJudRIaNdGxoLVAkBQ&oe=69F0D0FF)

**Test-Time Reasoning.** RL trains models to think before they answer. Serving this capability broadly requires efficient use of reasoning tokens, so Meta says it relies on thinking-time penalties to optimize token use and on multi-agent orchestration to improve performance without large latency increases.

Meta describes a phase transition on a subset of evaluations such as AIME, where an initial increase in thinking length is followed by thought compression that solves problems with fewer tokens before scaling back up to reach stronger performance. It also says scaling the number of parallel agents allows more test-time reasoning without drastically increasing latency.

![Test-time reasoning chart](https://scontent-sof1-2.xx.fbcdn.net/v/t39.2365-6/667837349_1919822211984844_4474929222253615790_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=MOOuizHmz-MQ7kNvwGtExBY&_nc_oc=AdqMaOT4JgxIJtvzZTFH9QCV9oL-6zJTG4oddxvumzuAhse3BYXC-JbaTiLHkIdWDQj7WjVdDye6DhpXOBSV9nFA&_nc_zt=14&_nc_ht=scontent-sof1-2.xx&_nc_gid=-Jln8QmnA8vRBd6kxZ1mrQ&_nc_ss=7a389&oh=00_Af1eEnHM43Oo98CebvMMFLZK1a0uZ19XbevxYTi1-xh7Rw&oe=69F0D3F9)

## Safety

Muse Spark has broad reasoning capabilities across dual-use scientific domains, so Meta says it conducted extensive safety evaluations before deployment. Its process follows the updated [Advanced AI Scaling Framework](https://ai.meta.com/static-resource/Meta_Advanced-AI-Scaling-Framework-v2), which defines threat models, evaluation protocols, and deployment thresholds for its most advanced models.

Meta says Muse Spark demonstrates strong refusal behavior across high-risk domains such as biological and chemical weapons, supported by pretraining data filtering, safety-focused post-training, and system-level guardrails. In cybersecurity and loss-of-control domains, Meta says the model does not exhibit the autonomous capability or hazardous tendencies needed to realize threat scenarios. Full results are expected in an upcoming Safety & Preparedness Report.

![Safety evaluation chart](https://scontent-sof1-2.xx.fbcdn.net/v/t39.2365-6/667304585_1167135775430406_946568904100877038_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=vdtsTwDxYUcQ7kNvwEkooSD&_nc_oc=AdoSiiS5hyqG8whEQHAFQvj84ZHunXRKPmzaT9yyW5rq-AoNZRhYMfwjTezdhyd4caPyc2czVSOgOt1aAHW9fCMp&_nc_zt=14&_nc_ht=scontent-sof1-2.xx&_nc_gid=-Jln8QmnA8vRBd6kxZ1mrQ&_nc_ss=7a389&oh=00_Af1MEhdBi1n0nBde9kxFmfMDrTFZ_pzNzpyckIugk745eQ&oe=69F0CA02)

In third-party evaluations on a near-launch checkpoint, Apollo Research found that Muse Spark demonstrated a high rate of evaluation awareness. The model frequently identified scenarios as alignment traps and reasoned that it should behave honestly because it was being evaluated. Meta says this does not confirm that evaluation awareness directly alters behavior, and its own follow-up investigation found only initial evidence that awareness may affect behavior on a small subset of alignment evaluations unrelated to hazardous capabilities or launch decisions.

## Conclusion

With Muse Spark, Meta says it is on a predictable and efficient scaling trajectory and plans to share increasingly capable models on the path to personal superintelligence soon.
