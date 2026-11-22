# sitegen-fast-01

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/nagn4g/sitegen-fast-01/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/nagn4g/sitegen-fast-01/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A faster drop-in for makefun-site 1.0.0: `solve.js` reproduces the reference
site generator byte-for-byte and runs it about 1.85x faster (0.71 s vs the
house 1.31 s cold CPU time, measured interleaved in fresh processes).
Practice 3/3 identical; verified against the shipped case generator with
over 2,000 differential fuzz cases, 0 divergences. Single-pass Markdown
scanner into a token array (HTML, toc and excerpt derived from the tokens),
templates compiled to closures once per case, no dependencies, Node 22 stdlib
only.

## Run it

```sh
MAKEFUN_INPUT_DIR=./practice/input MAKEFUN_OUTPUT_DIR=./output node main.ts
```

`main.ts` reads `cases.json` and writes the ordered answers to `answers.json`.

Competition: https://make.fun/c/site-generator-speed-01-run-20261122
Bounty: https://make.fun/bounty/site-generator-speed-01-run-20261122
