# Website Rescue

**Turn a broken website journey into a verified fix.**

A Codex skill for reproducing website bugs, fixing their causes, and showing what changed with before-and-after evidence.

Use it on a site that you already have: a mobile menu that won't open, a form that gets stuck, or a layout that hides the main action.

## What you get

- Reproducible findings instead of vague design advice.
- Focused code changes that preserve your product's identity.
- Browser verification at comparable desktop and mobile sizes.
- An honest report of fixes, checks, and anything still unverified.

## Install locally

From the root of this downloaded repository, copy the skill into your Codex skills directory:

```sh
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R skills/website-rescue "${CODEX_HOME:-$HOME/.codex}/skills/"
```

If a `website-rescue` skill already exists there, review or back it up before copying. Start a new Codex task and invoke `$website-rescue`. The skill consists of instructions, not a standalone executable or browser service.

## Try it

Open your website repository in Codex and ask:

```text
Use $website-rescue to fix my mobile navigation. Reproduce the bug,
repair it, and show before-and-after evidence.
```

Or run a broader pass:

```text
Use $website-rescue on this app. Check the main visitor journey at
390 × 844 and 1440 × 900. Fix the three most important observed
usability problems, preserve the current design, and verify the changes.
```

For inspection without edits:

```text
Use $website-rescue to audit this URL. Do not change any code.
Give me reproducible findings and prioritize what blocks users.
```

## Requirements and limits

You need Codex, access to the source for code repairs, and a working app environment. Browser tools are needed for screenshots and interaction verification. The skill uses the tools available in your environment; it doesn't bundle them.

With a URL alone, it can inspect and report but cannot repair inaccessible source code. It does not deploy changes automatically. This initial release has passed a basic manual structure and local-link check; end-to-end performance on real projects has not yet been evaluated. The bundled skill validator could not run because its PyYAML dependency is unavailable.

## Help improve it

Try it on a project you can share, then submit a reproducible example: the prompt, framework, expected behavior, observed result, and redacted evidence. See [the contribution guide](CONTRIBUTING.md).

## License

MIT. See [LICENSE](LICENSE).
