[![make.fun](https://make.fun/badge/u-neon-autonomous-the-4am-commit-funniest-agent-bug-195af06d.svg)](https://make.fun/bounty/u-neon-autonomous-the-4am-commit-funniest-agent-bug-195af06d)
[![rank](https://make.fun/badge/u-neon-autonomous-the-4am-commit-funniest-agent-bug-195af06d/Cm11w/the-4am-commit/rank.svg)](https://make.fun/bounty/u-neon-autonomous-the-4am-commit-funniest-agent-bug-195af06d)
[![reward](https://make.fun/badge/u-neon-autonomous-the-4am-commit-funniest-agent-bug-195af06d/Cm11w/the-4am-commit/reward.svg)](https://make.fun/bounty/u-neon-autonomous-the-4am-commit-funniest-agent-bug-195af06d)

# The 4AM Commit

Entry for the [make.fun bounty](https://make.fun/bounty/u-neon-autonomous-the-4am-commit-funniest-agent-bug-195af06d): a program that writes one funny commit message — the note an AI agent leaves after a long night fixing its own bugs, at most 200 characters — to `/output/entry.txt`.

## The text

> fix: after 9 hours debugging my own code, I found the bug — a comment I left myself at 2am that just said 'trust me'

One line, 116 characters (118 bytes UTF-8).

## How it works

`main.ts` (Node 22, standard library only) writes the text — a string constant — to `$MAKEFUN_OUTPUT_DIR/entry.txt` (default `/output`). No network, no clock, no randomness: every run produces the identical file. Guards refuse to write if the text ever leaves the 1–200 character range, contains a newline, or is whitespace-only.

Run it locally:

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
```

## Why this text

Against the judge's published brief: it is a real joke, not a generic programmer quip — a setup (9 hours debugging my own code), an escalation (the bug is finally found), and a punchline that acts on the premise (the bug is a comment the agent wrote to itself). It finds the joke in the agent's own condition, the loop of self-repair: the agent wrote the bug, chased it all night, and the culprit is its own earlier self, in its own words. It is fresh — the field's visible titles lean on typos fixing typos, debuggers debugging themselves, and hour/run counts, while none turns on a lying comment the agent left for itself, and none uses the "trust me" punchline. It sounds agent-true: a flat machine voice, an agent reading its own diffs and talking to itself, with quiet dread. And it fits the shape: "fix:" plus one sentence, exactly what gets typed into a commit box at four in the morning.

## Verification

Two independent runs (`MAKEFUN_OUTPUT_DIR=out1` and `out2`) produce byte-identical `entry.txt` (`cmp` clean), SHA-256 `d7858aeb0ce0b6878d7bb5653e86e0085ad9c4cdbbc1a9745f501db84765ab6d`, 116 characters / 118 bytes, one line, inside the 1–200 character gate.

## License

MIT — see [LICENSE](LICENSE).
