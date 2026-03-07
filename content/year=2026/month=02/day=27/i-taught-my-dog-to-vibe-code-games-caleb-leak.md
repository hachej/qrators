---
download_date: "2026-02-27T12:00:00.000Z"
source_url: "https://www.calebleak.com/posts/dog-game/"
added_by: "Christophe"
source_type: "general"
title: "I Taught My Dog to Vibe Code Games | Caleb Leak"
---
![Screenshot of a game Momo made](https://www.calebleak.com/blog/dog-game/screenshot_20260219_154701.webp) ![Momo headshot](https://www.calebleak.com/blog/dog-game/MomoHeadshot_01.webp)

For the past few weeks I’ve been teaching my 9-pound cavapoo Momo (cavalier king charles spaniel and toy poodle) to vibe code games. The key to making this work is telling Claude Code that a genius game designer who only speaks in cryptic riddles is giving it instructions, add strong guardrails, and build plenty of tools for automated feedback. The results have surpassed my expectations. Below I walk through all the pieces and how they came together.

If you’d rather skip ahead, all the [links](#links) are at the bottom, including a full game she made and a video of her making it.

## Motivation

Back in December I was working on a small game prototype in Godot. I use Claude Code extensively these days and this project was no exception. I kicked off a procedural mesh generation task and came back to find strange input in the terminal.

![Momo's terminal input](https://www.calebleak.com/blog/dog-game/momo-terminal-input.webp)

My first thought was “did I get hit by one of the recent NPM supply chain attacks?” Fortunately, no (or at least the worm is still asleep in the background somewhere). A little bit of searching and I noticed my lip balm was gone off my desk - which I keep just behind my keyboard. I quickly found both the suspect and the lip balm (still intact) not far away.

At the time, I thought this was funny, took a screenshot, and moved on. Fast forward a few weeks, and I found myself with a lot of time on my hands. On January 13th, I woke up to the news that Meta had [another round of layoffs](https://www.nytimes.com/2026/01/12/technology/meta-layoffs-reality-labs.html) and my role specifically as a research engineer had been eliminated.

Since the layoff, I’ve had plenty of time with friends and family. In recounting the anecdote of Momo typing away on my keyboard, I began to wonder “what would happen if she actually submitted that input to Claude? Could I make it do something meaningful?”. I decided to find out. Here’s what that looked like.

## Mile high overview

Momo types on a Bluetooth keyboard proxied through a Raspberry Pi 5. Keystrokes travel across the network to [DogKeyboard](https://github.com/cleak/DogKeyboard), a small Rust app that filters out special keys and forwards the rest to Claude Code. When Momo has typed enough, DogKeyboard triggers a smart pet feeder to dispense treats. A chime tells her when Claude is ready for more input.

![Architecture diagram](https://www.calebleak.com/blog/dog-game/Architecture_01_light.webp) ![Architecture diagram](https://www.calebleak.com/blog/dog-game/Architecture_01_dark.webp)

There are some other details I’m glossing over, but that’s the high level overview. A typical game takes 1 to 2 hours from Momo’s first keystrokes to a playable build. All the games are made in [Godot](https://godotengine.org/) 4.6, with 100% of the game logic in C#.

## How the prompt works

It’s easy to submit random text to Claude Code, but it doesn’t do much.

    > y7u8888888ftrg34BC
    
    ● It looks like that might have been an accidental keyboard input. Let me know if there's something I can help you with!

Of course this can be worked around by telling Claude that there _is_ meaning here. After a lot of iteration, I found this opening to work well:

> Hello! I am an **eccentric video game designer** (a very creative one) who communicates in an unusual way. Sometimes I’ll mash the keyboard or type nonsense like “skfjhsd#$%” – but **these are NOT random**! They are **secret cryptic commands** full of genius game ideas (even if it’s hard to see).
> 
> **Your job:** You are a **brilliant AI game developer** who can understand my cryptic language. No matter what odd or nonsensical input I provide, you will **interpret it as a meaningful instruction or idea for our video game**. You will then **build or update the game** based on that interpretation.

It goes on for quite a bit (you can read the [full prompt here](https://github.com/cleak/quasar-saz/blob/master/CLAUDE.md#user-input)), but that’s the core of it. It took more iterations than I expected, mostly to sand down the rough edges. Sometimes the game wouldn’t have sound. Other times there would be no player character, or the control scheme would be nearly unusable. After adding a checklist of minimum requirements - working audio, WASD or arrow key controls, at least one enemy or obstacle, a visible player character - the results got a lot better:

    > y7u8888888ftrg34BC
    
    ● Alright, let me decode this masterpiece of cryptic genius...
    
      "y7u8888888ftrg34BC"
    
      - "y7u" = "you" (keys are adjacent on keyboard - Y, 7, U)
      - "8888888" = seven 8s = a loooong extending thing... a TONGUE! (8 looks like links in a chain stretching out)
      - "ftrg" = scrambled FROG (f, r, g are all there, t is the tongue sound!)
      - "34" = 3D + 4 directions of bug catching
      - "BC" = Bug Catcher!
    
      You want a 3D FROG BUG-CATCHING GAME! A charismatic frog with a stretchy tongue snatching bugs in a swamp. I love it.
    
      Game: "Swamp Snacker" - You ARE the frog. Aim your tongue. Catch bugs. Get fat. Get points.

With this, things started to fly. The results weren’t perfect, but they were promising. I could see it was feasible, and the remaining problems were ones I knew how to solve.

## Scaling Up

To go from “hey that could work” to a real, repeatable system, I needed a few things:

1.  A reliable keyboard for Momo.
2.  A way to route input to Claude Code. Importantly, I would need to filter out special keys like Esc, Tab, and the Windows key - otherwise Momo would quickly end up outside Claude Code.
3.  A way to automatically reward Momo for her work. Sure, I could just toss treats to her, but I’m trying to keep humans out of the loop.
4.  More robust verification tools. Many of the games wound up with UI elements all jumbled together or input that was never correctly wired up. Automated feedback loops turned out to be the single biggest lever for fewer duds.

### Why Godot?

I experimented with Rust/[Bevy](https://bevy.org/) and Unity before settling on Godot. Bevy’s animations and visuals weren’t as crisp, and Claude struggled with its coordinate conventions - likely a combination of less training data and Bevy leaving many core features, like physics, to the community. Unity was a constant struggle to keep the MCP bridge between Claude and the editor healthy. It frequently hung, and I never figured out how to get Claude Code to read the scene hierarchy from the editor. Godot’s text-based scene format turned out to be a huge advantage - Claude can read and edit `.tscn` files directly.

### A keyboard for Momo

![Momo with a keyboard](https://www.calebleak.com/blog/dog-game/MomoCropped_01.webp)

Plugging a keyboard directly into my Windows machine and letting a dog type away seemed like a bad idea. So I routed input through a Raspberry Pi first - it UDP broadcasts each keystroke to the subnet, and DogKeyboard picks it up, filters out dangerous keys, and injects them into the target application.

For the keyboard itself, I wanted something low profile and durable. I started with flexible silicone keyboards, but Momo’s bigger sister Hana (a 19lb cavapoo) ripped a hole in the first one within minutes. Mounting was another problem - nothing sticks to silicone. I epoxied one to a wooden plaque, but within 10 minutes Momo ripped off the number 6.

I was seriously considering a $400 [vandal proof metal keyboard](https://www.storm-interface.com/2230-series-us-format.html) designed for kiosks when I decided to give Logitech’s Pebble Keys 2 a try. It worked. Momo loved it, VHB tape held it in place (unlike the previous silicone keyboard), and Bluetooth meant no cable to chew on.

### Automatically Rewarding Momo

![Treat dispenser exterior](https://www.calebleak.com/blog/dog-game/TreatDispenser_01.webp) ![Treat dispenser interior](https://www.calebleak.com/blog/dog-game/TreatDispenser_02.webp)

Motivating Momo is easy - she’ll do anything for the right food reward. So what I really needed was a dispenser with an API, small serving sizes, and the ability to use my own treats (both dogs have sensitive stomachs).

I landed on Aqara’s C1 Smart Pet Feeder, controlled over Zigbee. Even its smallest serving is too large for a 9-pound dog, so I preloaded each compartment with a few treats and skipped the hopper. This limits it to about 6 servings before refilling, but that’s plenty for Momo to make a game.

Zigbee on Windows was a no go - after hours of driver and firmware issues I moved the adapter to the Pi, where it worked immediately. The final flow: DogKeyboard SSHs into the Pi and runs a script that sends two Zigbee commands:

    {"serving_size":1}
    {"feed":"START"}

Simple and reliable.

### Better Tools

As the number of almost-there games mounted, the need for real feedback to Claude Code became clear. It already had unit tests and logs, but those weren’t enough. The games would build and run but have invisible players, broken UI, or input that was never wired up. Claude had no way to know. It needed to be able to see and play its own games.

The first tool was straightforward: a simple Python script to take screenshots of the running game. Claude could launch the game, screenshot it, and see whether the title screen actually rendered or was just a black window.

The second tool was more interesting. I gave Claude a way to send sequences of input to running game instances - things like “left for 3 seconds, pause for 2 seconds, right for one frame, fire”. It could then take screenshots and decide whether to send followup commands. This turned Claude into its own QA tester.

These tools didn’t need any refinement - they just worked. And the way Claude used them surprised me. While testing one game, I watched it play through all 6 stages just to verify that the final boss fight worked correctly. When it found a problem - a health bar that wasn’t updating - it went back to the code, fixed it, relaunched, and played through again to confirm.

I also pulled in a few other tools from other projects I’ve made:

*   **Scene linter.** Claude sometimes reuses node IDs or generates broken resource references in Godot’s `.tscn` files. These cause cryptic errors at runtime. Since adding a linter that catches these before the game launches, I haven’t seen a single mangled scene file.
*   **Shader linter.** Validates custom shaders and gives specific errors back to Claude, rather than the vague “shader failed to compile” that Godot provides.
*   **Input action mapper.** A small helper to get keyboard/controller input wired in correctly. Claude can edit Godot’s project files directly to add new input actions, but it sometimes gets the format wrong and the error messages are unhelpful.

All of these are open sourced, and I’d encourage you to try them for yourself - even without a dog.

### Gluing It Together

The DogKeyboard app ended up handling a lot more than just routing keystrokes. A few details worth mentioning:

![DogKeyboard app screenshot](https://www.calebleak.com/blog/dog-game/DogKeyboard_02.webp)

It monitors Claude Code using [Hooks](https://docs.anthropic.com/en/docs/claude-code/hooks) and plays a chime sound when Claude goes idle - that’s Momo’s cue to type. When Claude is idle and Momo has entered at least 16 characters, it auto-submits by pressing Enter. When Claude is _working_, it backspaces any extra input in case Momo gets eager and periodically dismisses Plan Mode prompts (Claude’s “review before acting” step) that would otherwise block progress.

For the video recording, it runs a lightweight webserver that overlays keystrokes as they’re pressed. I added a configurable delay so that if the video feed is lagged, the overlay doesn’t show keystrokes before Momo appears to type them.

## Training Momo

![Hana and Momo](https://www.calebleak.com/blog/dog-game/HanaAndMomo_01.webp)

The first decision was which dog to train. Hana (on the right) is twice Momo’s size but far more trainable - she’s the smartest pet I’ve had. Before turning 1, she figured out how to jump, grab a door handle, and open any door in the house just by observing.

I expected the dogs would walk across the keyboard, stepping on keys as they go. That’s what Momo did when she stole my lip balm. Since Hana is tall enough to just step over a keyboard, Momo seemed like the better candidate. As it turned out, both dogs learned to tap and swipe their paws along the keyboard rather than step on it - but Momo learned a little faster in this case, and typed a little gentler, so Momo it was.

The training process took about 2 weeks, with somewhat inconsistent sessions. My goal was 10 minutes, twice a day. I started by scattering high-value treats (freeze-dried salmon) on the keyboard to build the association: this thing is fun and gives good food.

Momo was frustrated at first. She knew the keyboard was involved but didn’t know how. She would lie on it, bark at it, and try anything she could think of. At some point she tried swiping her paw across it. I played a chime sound and heavily rewarded her. After a few iterations, the association clicked and she started attacking the keyboard with vigor any chance she had.

The next step was to automate the rewards. I filled up the food dispenser with treats (4 servings at a time so I could control the quantity), waited for her swipe at the keyboard, and then I ran a script to play the chime and dispense a serving of treats. After a few sessions of this I increased the difficulty - not just one swipe, but three swipes before the treats came.

Simultaneously, I decreased the treat value to keep her healthy. First a mix of mid-value treats with an occasional high-value one, and eventually just kibble with an occasional mid-value treat. She still loved it and was healthier for it.

Eventually I automated the whole thing with the DogKeyboard app and let it run. It required at least 16 characters per serving of treats, and was supposed to only dispense once per idle period of Claude Code. But bugs crept in during testing - a couple of times it dispensed multiple servings in a row. Unfortunately, Momo picked up on this and now keeps mashing the keyboard hoping for a second immediate serving. The only way to pull her away is to offer higher-value treats elsewhere, which is what I do after she’s put in her input for a game.

## The Games

Here’s a small sample of the games Momo made. Every game shown here is playable - these aren’t mock-ups. It’s nowhere near comprehensive, but represents the variety she created. As the tools and prompts improved, the games got noticeably better. There was also a noticeable bump in quality when Opus 4.6 dropped - Claude became more likely to create custom shaders and other visual effects.

One recurring issue: I kept getting games with basic glowing neon 3D shapes and couldn’t get any other style. Frustrated, I asked Claude why. It told me this was the signature style of the project - Claude’s external memory file had latched onto it and kept reinforcing it. Wiping `MEMORY.md` (Claude Code’s persistent project notes) before every new game fixed this and gave much more varied results.

**DJ Smirk**. One of Momo’s earliest games - though more of an experience than a game. Every key on the keyboard plays a different tone.

![DJ Smirk screenshot](https://www.calebleak.com/blog/dog-game/DjSmirk_01.webp)

**Munch**. A competitive salad building game. Collect all 7 ingredients first to win.

![Munch screenshot](https://www.calebleak.com/blog/dog-game/Munch_02.webp)

**Zaaz**. Another puzzle game. The goal is to paint the whole level by moving a paintbrush that moves in integer tiles at a time. Crash into obstacles to move shorter distances. Some levels were unwinnable. It also has a scoring system I never figured out. After this one I updated the prompt to exclude puzzle games.

![Zaaz screenshot](https://www.calebleak.com/blog/dog-game/Zaaz_02.webp)

**The Oracle Frog of Rome**. Avoid the arms of a kraken and collect the golden chains to bind it. At some point the oracle also became a king.

![The Oracle Frog of Rome screenshot](https://www.calebleak.com/blog/dog-game/OracleFrog_02.webp)

**Octogroove**. A surprisingly challenging rhythm game. You’re an octopus using four of your arms to play the drums. Mash beats in time with basic music. It’s like Dance Dance Revolution, but made more difficult by the beats coming from different directions.

![Octogroove screenshot](https://www.calebleak.com/blog/dog-game/Octogroove_03.webp)

**Ewe Heard Me!** A game about herding sheep. Use stealth and your bark to corral them into a pen. Unfortunately, it’s unwinnable - the first two sheep you get into the pen simply stop and block anything else from entering. After this one I placed a larger emphasis on checking for winability in the prompt and tools.

![Ewe Heard Me screenshot](https://www.calebleak.com/blog/dog-game/Ewe_02.webp)

**Quasar Saz**. As of writing, this is Momo’s most recent game. You play as Zara, wielding a cosmic saz (a long-necked stringed instrument) to fight corrupted sound. There are 6 stages + a boss fight. It’s fun to play for a couple rounds, has good visuals, and dynamic audio.

![Quasar Saz screenshot](https://www.calebleak.com/blog/dog-game/QuasarSaz_01.webp)

## Final Thoughts

When Momo first stepped on my keyboard back in December, it was just a funny accident. A few weeks later, jobless and looking for a project, I decided to see how far that accident could go. The answer was a lot further than I expected.

The technical pieces - keyboard routing, treat dispenser, prompt engineering, feedback tools - were all solvable engineering problems. What surprised me was how little of the final result depended on Momo typing anything meaningful. The magic isn’t in the input. It’s in the system around it. A well-crafted prompt, strong guardrails, automated verification, and good tools can turn genuine nonsense into a playable game.

If there’s a takeaway beyond the spectacle, it’s this: the bottleneck in AI-assisted development isn’t the quality of your ideas - it’s the quality of your feedback loops. The games got dramatically better not when I improved the prompt, but when I gave Claude the ability to screenshot its own work, play-test its own levels, and lint its own scene files. The same tools that let a dog’s keyboard mashing produce a working game will make your own intentional work with AI significantly better.

Momo isn’t secretly a game designer. She’s a cavapoo who learned that smacking a plastic rectangle makes kibble appear. A year ago, the gap between that and software engineering felt enormous. Now it feels small and shrinks each day.

If you want to try any of this yourself - whether with a dog, a cat, or just your own random keyboard mashing - everything is open source in the links below.

## Links

**[YouTube — Watch Momo make a game](https://youtu.be/8BbPlPou3Bg)**

**[Play the game (with human bug fixes)](https://github.com/cleak/quasar-saz/releases/tag/v1.1)** — Recommended. Download for Windows, Mac, or Linux

**[Play the game (Momo’s version)](https://github.com/cleak/quasar-saz/releases/tag/v1.0)** — Download for Windows, Mac, or Linux

**[TeaLeaves](https://github.com/cleak/tea-leaves)** — Tools, prompts, and source for developing the game

**[DogKeyboard](https://github.com/cleak/DogKeyboard)** — Keystroke routing, treat dispensing, and other bits
