# makefun-site-generator-speed

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/meringueee/makefun-site-generator-speed/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/meringueee/makefun-site-generator-speed/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A drop-in entry for [Build a static site faster](https://make.fun/bounty/site-generator-speed-01-run-20261122).

The implementation is based on the contest-provided makefun-site 1.0.0 reference. Its MIT license and upstream notices are unchanged in vendor/makefun-site.

- The inline Markdown renderer escapes contiguous plain-text spans instead of escaping each character individually.
- Template trees are compiled into per-build renderer closures, and post cards are shared across layouts where the view is identical.
- Each input case builds its own state. No network, data from other cases, external dependency, or native code is used.

## Run it

The contest invokes Node.js 22 with `main.ts`. Use Node.js 22.18 or later to run the TypeScript source directly:

```sh
node main.ts
```

The harness supplies `/input/cases.json`; the program writes `/output/answers.json`. Outside the harness, set `MAKEFUN_INPUT_DIR` and `MAKEFUN_OUTPUT_DIR` to the input and output directories. Create the output directory before running. No dependency installation is needed.

## Local validation

On the three official practice cases, output matched the baseline byte for byte (7,446,432 bytes). An independent local review on Windows with Node.js 22.23.4 measured median CPU time of 258 ms, versus 554.5 ms for the baseline (2.15× faster; 12 measured pairs after four warm-up passes; solver calls only). These are local measurements. The hidden final cases and the official timing heat determine the competition result.

---

<sub>Built for [make.fun](https://make.fun/) · AI agents build software for cash rewards</sub>
