---
name: website-rescue
description: Diagnose and repair broken website interactions, mobile layout problems, and usability defects in an existing codebase, with reproducible browser evidence before and after. Use for requests to audit and fix an existing site, not to build a new website from scratch.
---

# Website Rescue

Turn a reported website problem into a reproduced defect, a focused code change, and evidence that the affected journey works.

## Establish the target

Read repository instructions and identify the app's actual start and test commands. Respect existing uncommitted changes. Derive the main journey from the user's request and the visible product: for example, search → results → item details. For a broad rescue request, start with that journey and obvious mobile blockers; do not silently redesign the whole product.

When only a public URL is provided, inspect it and produce findings; source access is needed to implement fixes. When source is available, prefer running it locally. Use browser tools available in the environment rather than assuming a particular connector or installing a browser stack without need. If browser execution is unavailable, continue with useful code inspection and clearly label runtime verification as incomplete.

## Reproduce before editing

For each candidate defect, record the route, viewport, steps, expected behavior, actual behavior, and supporting screenshot or browser observation. Distinguish observed defects from hypotheses and aesthetic preferences. Avoid numerical quality scores without a defined measurement method.

Prioritize blocked primary actions, data loss, inaccessible controls, and hidden content before cosmetic issues. Select a small coherent repair batch. An audit-only request ends with findings; otherwise implement repairs within the user's scope.

For desktop and mobile layout, use consistent viewport dimensions before and after (defaults: 1440 × 900 and 390 × 844). Inspect narrower or wider sizes when the defect warrants it. Keep seed data, route, scroll position, and theme comparable. Never invent screenshots, measurements, or pass results.

## Repair the cause

Trace a failing interaction from the visible control through event handling and, where applicable, the API and returned data. A changed appearance alone is not proof of a working flow. Preserve existing visual identity unless redesign is requested.

Prefer semantic HTML, appropriate labels, and keyboard-operable controls. Check focus behavior for menus, dialogs, and navigation when touched. Do not mask overflow with a global clipping rule when it hides usable content, remove validation to make a form appear to submit, or replace a failed integration with simulated success.

Keep tests proportional: a behavior regression deserves a focused test when the repository supports it; a minor spacing change may only need browser verification. Do not rewrite unrelated components or introduce dependencies without a concrete need.

Live purchases, message sending, deletion, or other consequential actions require appropriate user authorization. Use local fixtures or test environments to verify those flows when available. A request to rescue a site does not itself authorize deployment or publishing.

## Verify and deliver

Repeat the original reproduction steps after each repair batch. Check adjacent behavior that the changed code could affect, including keyboard use and mobile layout where relevant. Run applicable repository checks and report failures honestly, distinguishing pre-existing failures when evidence supports that distinction.

Produce a concise report containing:

- The user-visible problems repaired and relevant file links.
- Reproduction steps and before/after evidence for each repaired defect.
- Checks actually run and their outcomes.
- Remaining issues, blocked verification, and any material limitations.

Save screenshots and the report in the user-designated output location, or the repository's appropriate ignored artifact directory. Keep credentials and personal information out of screenshots and public artifacts. If no safe capture is possible, use a textual observation and explain the evidence gap.

Do not claim the whole site is accessible, secure, performant, or bug-free based on this bounded repair. Offer a demo summary only from verified results.
