---
download_date: "2026-02-27T12:00:00.000Z"
source_url: "https://fromanengineersight.substack.com/p/specs-should-be-equations-not-essays"
added_by: "Christophe"
source_type: "general"
title: "Specs Should Be Equations, Not Essays"
---
[

![](https://substackcdn.com/image/fetch/$s_!zM6I!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F28d1ee13-96d5-43ff-b780-340cbcc4fdef_757x964.png)

](https://substackcdn.com/image/fetch/$s_!zM6I!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F28d1ee13-96d5-43ff-b780-340cbcc4fdef_757x964.png)

_“Thomas, who was the father of both Eleanor and Richard, had a grandson through Eleanor named William, who in turn had two daughters, Charlotte and Margaret, while Richard had a son named James, who was the father of both Beatrice and Arthur, the latter of whom married William’s daughter Charlotte.”_

Most of us have a hard time to get such a sentence.  
What about the diagram below?

[

![](https://substackcdn.com/image/fetch/$s_!UKrt!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F29e469e5-282d-416a-ac08-987088c260c6_2391x1298.png)

](https://substackcdn.com/image/fetch/$s_!UKrt!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F29e469e5-282d-416a-ac08-987088c260c6_2391x1298.png)

Easier right? By switching the representation, we ends up with something easier to understand. Here relationship is easier to grasp with a graph rather than a sequence of words.

Following the same idea, which formulation do you prefer?

*   “For any given value of x, the corresponding value of y is found by adding 2 to x.”
    
*   “The value of y is always 2 more than the value of x.”
    
*   y = x + 2
    

Kids often ask why they have to learn mathematics. [What’s the point of learning times tables if the calculator can do it faster and better?](https://medium.com/@benoit.pimpaud/why-do-we-study-mathematics-52d75d7fd049)  
As we grow, we understand two things about mathematics:

*   It brings mental models and patterns that help resolve anything
    
*   Its semantics and syntax are top-notch. One of the best set of representation humans have ever created.
    

The mathematical expression isn’t just shorter - it’s transformative. It allows manipulation, extension, and application impossible with prose descriptions.

> The powers of cognition come from abstraction and representation: the ability to represent perceptions, experiences, and thoughts in some medium other than that in which they have occured, abstracted away from irrelevant details. This is the essence of intelligence, for if the representation and the processes are just right, the new experiences, insights, and creations can emerge.  
> The important point is that we can make marks or symbols that represent something else and the do our reasoning by using those marks

Natural language doesn’t seem so ambiguous in our daily life:

> _\[...\] the ambiguity almost always results from the analysis of single, isolated sentences: in real situations, where several interacting people deal with real events, the sentences usually have only one meaningful interpretation. Actually, even when communications are ambigous, they are usually not perceived as such by either speaker or listener, even though both may have different interpretations of the meaning._

> _**It is the lack of perception of ambiguity that is important, and it derives from the communicative, social nature of language, something that is entirely missed when the language is studied as isolated, “simplified” printed sentences or utterances, completely abstracted from the real, social settings.[1](https://fromanengineersight.substack.com/p/specs-should-be-equations-not-essays#footnote-1-189185011)**_

Replace “printed sentences” with “tokens” and you have modern LLM training.

Also, when an LLM generates a response to an ambiguous prompt, it confidently selects one interpretation and proceeds - with no awareness that alternatives exist. It doesn’t “perceive” ambiguity because it has no mechanism for recognizing that its statistical resolution of a sentence is just one of several possible interpretations.

Humans don’t notice ambiguity because context resolves it most of the time.

And so while natural language still remains our main interface, the way we think and build creative solution is usually embedded into something deeper.

I’ve been exploring lately how instead of creating [a spec the size of a technical O’Reilly book](https://github.com/Dicklesworthstone/frankensqlite/blob/main/COMPREHENSIVE_SPEC_FOR_FRANKENSQLITE_V1.md) and creating a [Spec Observer skill](https://github.com/Ben8t/SpecObserver), we could use a mathematical representation for defining our spec.

The intuition here is that the shift happening from _writing code_ to _writing specs_ will expose how bad natural language is at precision.

That to extract a consistent, lean, and so maintenable and evolutive software specification, math can play a better role than natural language.

And so I’ve created this [math spec-driven skill](https://github.com/Ben8t/math-spec-driven-skill). It treats mathematics as a specification method, using sets, functions, relations, invariants, and explicit edge cases to define what a system is and what it must do.  
It enforces three principles:

*   Explicitness: every assumption is stated
    
*   Composability: parts can be specified independently, then combined safely
    
*   Falsifiability: claims are written so they can be proven or disproven
    

For example building a TicTacToe game using this spec methodology looks like this:

**Board** := P = {1..9} → {X, O, ∅}; initially ∀p ∈ P: P(p) = ∅  
**Players** := T = {X, O}; turn(n) = X if n is odd, O if n is even  
**Move** := move(p, t) requires P(p) = ∅ ∧ turn(n) = t; sets P(p) ← t  
**Lines** := L = {{1,2,3},{4,5,6},{7,8,9},{1,4,7},{2,5,8},{3,6,9},{1,5,9},{3,5,7}} **Win** := win(t) ⟺ ∃ℓ ∈ L : ∀p ∈ ℓ, P(p) = t  
**Draw** := draw ⟺ (∀p ∈ P: P(p) ≠ ∅) ∧ ¬win(X) ∧ ¬win(O)  
**Terminal** := game ends when win(X) ∨ win(O) ∨ draw  
**Invariant** := |{p : P(p)=X}| − |{p : P(p)=O}| ∈ {0, 1}

It can be frightening for most of us I do agree. But the LLM can easily return a translation for this:

> The **board** is a 3×3 grid of 9 cells, each either X, O, or empty. All cells start empty.
> 
> Two players — X and O — alternate turns, with X always going first. On your turn, you place your mark in any empty cell.
> 
> A player **wins** if they fill an entire row, column, or diagonal (there are 8 such lines). The game is a **draw** if every cell is filled and nobody has won. The game **ends** the moment someone wins or the board is full.
> 
> **Invariant:** at any point, the number of X’s on the board is either equal to or exactly one more than the number of O’s — this guarantees proper alternation.

I did try that skills on several projects, and [even if it might be useless for agents](https://arxiv.org/pdf/2602.11988)[2](https://fromanengineersight.substack.com/p/specs-should-be-equations-not-essays#footnote-2-189185011), it's valuable for me to iterate on the spec. I feel it easier to iterate on next steps when I have such rigorous foundation.

At the end of the day, the context we give to agents should be multi modal:

*   text for intents, examples, problem-context
    
*   diagram for relationship between entities
    
*   and math for explicitness, composability, and falsifiability[3](https://fromanengineersight.substack.com/p/specs-should-be-equations-not-essays#footnote-3-189185011)
    

This way we can use the full value of different representation and make things easier to maintain for both agents and humans.

If we push the idea further here we could imagine finding the ultimate substrat of mathematical representation to describe any SaaS, any software.  
That’s sounds like an utopia by the time I write this - but what we have achieved with frameworks and libraries in code really seem similar to a common set of equation expressed into a single formalism.

To build complex, maintenable and [malleable software](https://www.inkandswitch.com/essay/malleable-software/) \- ultimately to build at a higher level of abstraction - we somehow need the power that come from that level of representation.

In that scheme, we can see math as the _source of truth_ and code or natural language as a _projections_.

Math spec. come also with a crazy idea here: what if you apply the math themselves to create software and test it after the fact. We can imagine a similar build as SMT-solver or constraint optimization methodology, basically:

*   **math spec = the score function** - the gradient field that defines what “valid” looks like
    
*   **code = a sample** from the distribution of valid programs
    
*   **generation process = iterative refinement** where an agent proposes code and the spec’s invariants pull it toward correctness, like a potential field where the math model spec. allow to create the whole object in one-shot - swarm of agent iterating toward the optimal solution.
    

I’m not an expert in LLM architecture and optimization process, but that also resonate with diffusion models where you start from noise and iteratively denoise toward a sample that satisfies the learned distribution.

If Yann LeCun is right - and language really is just “lossy compression” of reality - then every spec we write in prose is already degraded before an agent touches it. I think he’s right - and the implication for software is direct. Every time we write a spec in natural language, we lose information. Every time an agent reads that spec, it loses more. The losses compound. Math doesn’t fix everything, but it preserves structure in a way prose simply cannot.

[“You want to write the least code as possible”](https://fromanengineersight.substack.com/p/issue-43-the-best-code-you-never) has been the mantra for years. Now we’re getting there. But the bottleneck doesn’t disappear, it moves. It moves from code to spec. From spec to intent. From intent to understanding the actual problem.

Which means, paradoxically, the more formal and mathematical our specifications get, the more human the hard part becomes. Creating good software means having good specs. Having good specs means having context and taste. And context and taste come from one place only: talking to people, understanding what they need, sitting with their problems long enough to see the shape of them. [Communication is the job](https://boz.com/articles/communication-is-the-job).

Natural language has been grown by humans to share cognition and sentiments. These are ultimately the two things why people work with you. The math gives us precision. The conversation gives us direction. We need both - and knowing when to switch between them might be the real skill now[4](https://fromanengineersight.substack.com/p/specs-should-be-equations-not-essays#footnote-4-189185011).

[2](https://fromanengineersight.substack.com/p/specs-should-be-equations-not-essays#footnote-anchor-2-189185011)

I actually did notice shorter iterations in my process for writing test cases and agent QA method.

[3](https://fromanengineersight.substack.com/p/specs-should-be-equations-not-essays#footnote-anchor-3-189185011)

TDD and DDD methodologies seems also to fit that realm. If you put these into your AGENTS.md, there is a chance the code generated will be easier to understand for humans.

No posts
