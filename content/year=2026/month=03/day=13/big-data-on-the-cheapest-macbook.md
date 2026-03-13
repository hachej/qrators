---
download_date: "2026-03-13T16:06:47.671Z"
source_url: "https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook"
added_by: "Christophe"
source_type: "general"
title: "Big Data on the Cheapest MacBook"
---
[![DuckDB Logo for Download](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/images/logo-dl/DuckDB_Logo-horizontal.svg)](https://duckdb.org/) 

[Documentation](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/)

* [Getting Started](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs)
* [Installation](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/installation/)
* [Guides](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/stable/guides/overview)
* [Data Import](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/stable/data/overview)
* [Client APIs](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/stable/clients/overview)
* [SQL Introduction](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/stable/sql/introduction)
* [Why DuckDB](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/why%5Fduckdb)

[Resources](#)

* [Blog](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/news/)
* [Library](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/library/)
* [Events](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/events/)
* [Everywhere](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/everywhere/)
* [Webshop](https://shop.duckdb.org/)
* [FAQ](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/faq)

[GitHub 36.6k](https://github.com/duckdb/duckdb)

[Support](https://duckdblabs.com/#support)

[Support](https://duckdblabs.com/#support) 

# Big Data on the Cheapest MacBook

![Author Avatar](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/images/blog/authors/gabor_szarnyas.png) 

Gábor Szárnyas 

2026-03-11 · 7 min 

_TL;DR: How does the latest entry-level MacBook perform on database workloads? We benchmarked it using ClickBench and TPC-DS SF300\. We found that it could complete both workloads, sometimes with surprisingly good results._

Apple released the [MacBook Neo](https://en.wikipedia.org/wiki/MacBook%5FNeo) today and there is no shortage of tech reviews explaining whether it's the right device for you if you are a student, a photographer or a writer. What they _don't_ tell you is whether it fits into our [Big Data on Your Laptop](https://blobs.duckdb.org/merch/duckdb-2024-big-data-on-your-laptop-poster.pdf) ethos. We wanted to answer this _using a data-driven approach,_ so we went to the nearest Apple Store, picked one up and took it for a spin.

## [What's in the Box?](#whats-in-the-box) 

Well, not much! If you buy this machine in the EU, there isn't even a charging brick included. All you get is the laptop and a braided USB-C cable. But you likely already have a few USB-C bricks lying around – let's move on to the laptop itself!

![](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/images/blog/macbook-neo/box.jpg)

The only part of the hardware specification that you can select is the disk: you can pick either 256 or 512 GB. As our mission is to deal with alleged “Big Data”, we picked the larger option, which brings the price to $700 in the US or €800 in the EU. The amount of memory is fixed to 8 GB. And while there is only a single CPU option, it is quite an interesting one: this laptop is powered by the 6-core [Apple A18 Pro](https://en.wikipedia.org/wiki/Apple%5FA18#CPU), originally built for the iPhone 16 Pro.

It turns out that we have already [tested this phone](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/2024/12/06/duckdb-tpch-sf100-on-mobile.html#a-song-of-dry-ice-and-fire) under some unusual circumstances. Back in 2024, with DuckDB v1.2-dev, we found that the iPhone 16 Pro could complete all [TPC-H](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/current/core%5Fextensions/tpch.html) queries at scale factor 100 in about 10 minutes when air-cooled and in less than 8 minutes while lying in a box of dry ice. The MacBook Neo should definitely be able to handle this workload – but maybe it can even handle a bit more. Cue the inevitable benchmarks!

## [ClickBench](#clickbench) 

For our first experiment, we used [ClickBench](https://benchmark.clickhouse.com/), an analytical database benchmark. ClickBench has 43 queries that focus on aggregation and filtering operations. The operations run on a single wide table with 100M rows, which uses about 14 GB when serialized to Parquet and 75 GB when stored in CSV format.

### [Benchmark Environment](#benchmark-environment) 

We ported [ClickBench's DuckDB implementation to macOS](https://github.com/szarnyasg/ClickBench/tree/duckdb-macos-compatible) and ran it on the MacBook Neo using the freshly minted [v1.5.0 release](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/2026/03/09/announcing-duckdb-150.html). We only applied a small tweak: as suggested in [our performance guide](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/current/guides/performance/my%5Fworkload%5Fis%5Fslow.html), we slightly lowered the memory limit to 5 GB, to reduce relying on the OS' swapping and to let DuckDB handle memory management for [larger-than-memory workloads](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/current/guides/performance/how%5Fto%5Ftune%5Fworkloads.html#larger-than-memory-workloads-out-of-core-processing). This is a common trick in memory-constrained environments where other processes are likely using more than 20% of the total system memory.

![](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/images/blog/macbook-neo/laptop.jpg)

We also re-ran ClickBench with DuckDB v1.5.0 on two cloud instances, yielding the following lineup:

* The star of our show, the MacBook Neo with 2 performance cores, 4 efficiency cores and 8 GB RAM
* [c6a.4xlarge](https://instances.vantage.sh/aws/ec2/c6a.4xlarge) with 16 AMD EPYC vCPU cores and 32 GB RAM. This instance is [popular in ClickBench](https://benchmark.clickhouse.com/#system=-&type=-&machine=+ca4e&cluster%5Fsize=-&opensource=-&hardware=+c&tuned=+n&metric=combined&queries=-) with about 80 individual results reported.
* [c8g.metal-48xl](https://instances.vantage.sh/aws/ec2/c8g.metal-48xl) with a whopping 192 Graviton4 vCPU cores and 384 GB RAM. This instance is often at the top of the [overall ClickBench leaderboard](c8g.metal-48xl).

The benchmark script first loaded the Parquet file into the database. Then, as per [ClickBench's rules](https://github.com/ClickHouse/ClickBench/blob/main/README.md#rules-and-contribution), it ran each query three times to capture both cold runs (the first run when caches are cold) and hot runs (when the system has a chance to exploit e.g. file system caching).

### [Results and Analysis](#results-and-analysis) 

Our experiments produced the following aggregate runtimes, in seconds:

| Machine        | Cold run (median) | Cold run (total) | Hot run (median) | Hot run (total) |
| -------------- | ----------------- | ---------------- | ---------------- | --------------- |
| MacBook Neo    | 0.57              | 59.73            | 0.41             | 54.27           |
| c6a.4xlarge    | 1.34              | 145.08           | 0.50             | 47.86           |
| c8g.metal-48xl | 1.54              | 169.67           | 0.05             | 4.35            |

**Cold run.** The results start with a big surprise: in the cold run, the MacBook Neo is the clear winner with a sub-second median runtime, _completing all queries in under a minute!_ Of course, if we dig deeper into the setups, there is an explanation for this. The cloud instances have network-attached disks, and accessing the database on these dominates the overall query runtimes. The MacBook Neo has a local NVMe SSD, which is far from best-in-class, but still provides relatively quick access on the first read.

**Hot run.** In the hot runs, the MacBook's _total runtime_ only improves by approximately 10%, while the cloud machines come into their own, with the c8g.metal-48xl winning by an order of magnitude. However, it's worth noting that on _median query runtimes_ the MacBook Neo can still beat the c6a.4xlarge, a mid-sized cloud instance. And the laptop's _total runtime_ is only about 13% slower despite the cloud box having 10 more CPU threads and 4 times as much RAM.

## [TPC-DS](#tpc-ds) 

For our second experiment, we picked the queries of the TPC-DS benchmark. Compared to the ubiquitous TPC-H benchmark, which has 8 tables and 22 queries, TPC-DS has 24 tables and 99 queries, many of which are more complex and include features such as [window functions](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/current/sql/functions/window%5Ffunctions.html). And while TPC-H has been [optimized to death](https://homepages.cwi.nl/~boncz/snb-challenge/chokepoints-tpctc.pdf), there is still some semblance of value in TPC-DS results. Let's see whether the cheapest MacBook can handle these queries!

For this round, we used DuckDB's [LTS version](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/install/?version=lts), v1.4.4\. We generated the datasets using DuckDB's [tpcds extension](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/current/core%5Fextensions/tpcds.html) and set the memory limit to 6 GB.

At SF100, the laptop breezed through most queries with a median query runtime of 1.63 seconds and a total runtime of 15.5 minutes.

At SF300, the memory constraint started to show. While the median query runtime was still quite good at 6.90 seconds, DuckDB occasionally used up to 80 GB of space for [spilling to disk](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/current/guides/performance/how%5Fto%5Ftune%5Fworkloads.html) and it was clear that some queries were going to take a long time. Most notably, [query 67](https://github.com/duckdb/duckdb/blob/main/extension/tpcds/dsdgen/queries/67.sql) took 51 minutes to complete. But hardware and software continued to work together tirelessly, and they ultimately passed the test, completing all queries in 79 minutes.

## [Should You Buy One?](#should-you-buy-one) 

Here's the thing: if you are running Big Data workloads on your laptop every day, you probably shouldn't get the MacBook Neo. Yes, DuckDB runs on it, and can handle a lot of data by leveraging [out-of-core processing](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/current/guides/performance/how%5Fto%5Ftune%5Fworkloads.html#larger-than-memory-workloads-out-of-core-processing). But the MacBook Neo's disk I/O is lackluster compared to the Air and Pro models (about 1.5 GB/s compared to 3–6 GB/s), and the 8 GB memory will be limiting in the long run. If you need to process [Big Data on the move](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/2025/09/08/duckdb-on-the-framework-laptop-13.html) and can pay up a bit, the other MacBook models will serve your needs better and there are also good options for Linux and Windows.

All that said, if you run [DuckDB in the cloud](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/library/duckdb-in-the-cloud/) and primarily use your laptop as a client, this is a great device. And you can rest assured that if you _occasionally_ need to crunch some data locally, DuckDB on the MacBook Neo will be up to the challenge.

##### In this article

* [What's in the Box?](#whats-in-the-box)
* [ClickBench](#clickbench)  
   * [Benchmark Environment](#benchmark-environment)  
   * [Results and Analysis](#results-and-analysis)
* [TPC-DS](#tpc-ds)
* [Should You Buy One?](#should-you-buy-one)

##  Recent Posts

[](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/2026/03/09/announcing-duckdb-150.html) 

![Announcing DuckDB 1.5.0](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/images/blog/thumbs/duckdb-release-1-5-0.svg) 

release 

### [Announcing DuckDB 1.5.0](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/2026/03/09/announcing-duckdb-150.html)

2026-03-09

The DuckDB team

[](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/2026/01/26/announcing-duckdb-144.html) 

![Announcing DuckDB 1.4.4 LTS](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/images/blog/thumbs/duckdb-release-1-4-4-lts.svg) 

release 

### [Announcing DuckDB 1.4.4 LTS](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/2026/01/26/announcing-duckdb-144.html)

2026-01-26

The DuckDB team

[ All blog posts ](https://duckdb.org/news/) 

###### Documentation

[Getting Started](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/stable/)  
[Installation](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/install/)  
[Guides](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/stable/guides/overview.html)  
[Data Import](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/stable/data/overview.html)  
[Client APIs](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/stable/clients/overview.html)  
[SQL Introduction](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/stable/sql/introduction.html)  
[Why DuckDB](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/why%5Fduckdb.html)  

###### Resources

[Engineering Blog](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/news/)  
[Library](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/library/)  
[Events](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/events/)  
[Webshop](https://shop.duckdb.org/)  
[RSS Feed](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/feed.xml)  
[Status Page](https://status.duckdb.org/)  
[FAQ](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/faq.html)  

###### Development

[Release Calendar](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/release%5Fcalendar.html)  
[Roadmap](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/roadmap.html)  
[Building DuckDB](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/docs/stable/dev/building/overview.html)  
[GitHub Issues](https://github.com/duckdb/duckdb/issues)  

###### Related Sites

[DuckLake](https://ducklake.select/)  
[DuckDB Foundation](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/foundation/)  
[DuckDB Labs](https://duckdblabs.com/)  
[Commercial Support](https://duckdblabs.com/#support) 

###### Community

[Community Extensions](https://duckdb.org/community%5Fextensions/)  
[LinkedIn](https://www.linkedin.com/company/duckdb/posts)  
[Bluesky](https://bsky.app/profile/duckdb.org)  
[X (Twitter)](https://twitter.com/duckdb)  
[Discord](https://discord.duckdb.org)  

© 2026 DuckDB Foundation, Amsterdam NL

[Code of Conduct](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/code%5Fof%5Fconduct.html) [Trademark Use](https://duckdb.org/2026/03/11/big-data-on-the-cheapest-macbook/trademark%5Fguidelines.html) 
