---
download_date: "2026-03-09T17:42:26.449Z"
source_url: "https://x.com/samhogan/status/2030476849911050687?s=20"
added_by: "Ju Hurault"
source_type: "x"
title: "Sam Hogan 🇺🇸 on X"
---
# Sam Hogan 🇺🇸 (@samhogan)


What if a codebase was actually stored in Postgres and agents directly modified files by reading/writing to the DB? 

Code velocity has increased 3-5x. This will undoubtedly continue. PR review has already become a bottleneck for high output teams. 

Codebase checked-out on filesystem seems like a terrible primitive when you have 10-100-1000 agents writing code. 

Code is now high velocity data and should be modeled at such. Bare minimum, we need write-level atomicity and better coordination across agents, better synchronization primitives for subscribing to codebase state changes and real-time time file-level code lint/fmt/review. 

The current ~20 year old paradigm of git checkout/branch/push/pr/review/rebase ended Jan 2026. We need an entirely new foundational system for writing code if we’re really going to keep pace with scale laws.
