# Simplified Technical English ✈️

A Claude Code skill that kills AI slop using the writing standard built for
flight manuals.

Aircraft maintenance manuals cannot afford ambiguity, so the aerospace
industry built **ASD-STE100 Simplified Technical English**: every word has one
meaning, instructions are 20 words or fewer, every instruction is a command.
A mechanic in any country can read one and do the right thing.

AI-generated text fails in the exact opposite way. Long sentences. Hedged
claims. "Leverage" and "seamless" and "it's important to note". This skill
applies the STE principles to any text and the slop dies mechanically:

- **One word, one meaning** - no word a reader can take two ways
- **Hard sentence limits** - 20 words per instruction, 25 per description, counted
- **One instruction per sentence** - sequences become numbered steps
- **Active voice, imperative commands** - "Remove the bolt", never "the bolt should be removed"
- **A substitution table** - utilize→use, commence→start, facilitate→help
- **An AI-slop blocklist** - delve, crucial, seamless, robust, and friends, deleted on sight

## Install

```bash
git clone https://github.com/jsath/simplified-technical-english.git
cp -r simplified-technical-english/skills/technical-english ~/.claude/skills/
```

## Use

In Claude Code:

```
/technical-english rewrite the README in this repo
```

```
/technical-english audit: <paste any text>
```

Or just ask naturally: "de-slop this", "make this readable", "apply STE to
this doc". The skill triggers on its own.

Three modes:
- **Rewrite** (default) - full rules, outputs the rewrite plus a violation report
- **Audit** - violation report only, nothing rewritten
- **Light** - for marketing copy with a voice worth keeping, applies only the
  sentence limits, active voice, substitutions, and the slop blocklist

## Example

**Before** (one 44-word sentence):

> In order to facilitate the seamless integration of the authentication
> module, it is important to note that developers should ensure that the
> configuration file has been comprehensively updated prior to commencing the
> deployment process, which can be accomplished via the CLI.

**After** (longest sentence: 11 words):

> Update the configuration file before you start the deployment. Use the CLI
> to deploy. This connects the authentication module.

Same facts. A third of the words. No ambiguity.

## What it will not do

It does not delete facts to look concise. It does not touch code, commands,
or quoted strings. It does not invent a value to complete a sentence, it
marks the gap.

## Attribution

Inspired by ASD-STE100 Simplified Technical English, maintained by the
AeroSpace and Defence Industries Association of Europe. This is an
independent skill applying its principles, not the official specification or
its dictionary. The official spec is available free from
[asd-ste100.org](https://www.asd-ste100.org).

## License

MIT © Johann Sathianathen

---

Built by [Johann Sathianathen](https://johann.fyi). I build AI systems like
this every week and break them down inside
[AI Operators](https://www.skool.com/ai-operators-5011/about). You do not
need it to use this skill.
