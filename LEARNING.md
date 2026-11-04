# Lesson 01 · Conversation evidence

AI-drafted summary of actual observations and help received, not a transcript
or grade. Learner reviewed the summary and approved publication in this chat.

**Lesson:** STUDIO-001. **Context:** This chat, November 3, 2026.

## Prediction

Pending. The learner said “i dont kno” when asked how the request reaches the
calculator. AI explained DNS and Traefik routing and offered a choice; no
learner prediction was supplied.

## Check interpretation

The learner said “its working” after AI presented the successful multiplication
check. What this check leaves untested remains Pending. AI supplied the test
input, expected result and actual response.

## Browser observation

The learner tried 6 × 7 on their deployed calculator and reported “42 and 42”
for Browser Result and API Result. Their screenshot showed the same results.
The regular Chrome session initially showed a certificate warning. AI checked
the current trusted certificate and guided browser diagnostics. After a full
Chrome restart, the learner reported “its secure”. This is their observed
result, not a claim that every possible application behavior was tested.

## Keep decision

Pending. AI asked whether to keep the deployment and why; the learner has not
yet supplied an explicit decision with a reason. Asking AI to finish remaining
work is not recorded as that explanation.

## Review

The learner reviewed the summary of their browser results, secure loading,
AI assistance and remaining gaps, and replied “Yes, publish the summary”.
This approval establishes record accuracy, not a completed explanation of the gaps.

## AI work and next step

AI cloned the learner's repository, ran local setup, saved ignored configuration,
added optional per-route TLS resolver support, and ran the read-only server
check. The learner approved the concrete launch plan with “yes launch it”. AI
launched the pinned calculator image and verified image identity, trusted HTTPS,
valid and invalid API cases, and selected preservation checks for all three
existing containers. AI also checked memory after launch (about 47 MiB used by
the calculator). These are AI checks, separate from the learner observations.

Local formatting passed. The optional resolver test passed within a studio run
with 55 passing and 11 failing tests; failures included Windows platform and
filesystem limitations. The full local suite also encountered a Linux signal
API unavailable on Windows. Full Linux CI, including browser E2E, passed on pull request #2 (run 41768514803).

See [SPEC.md](SPEC.md), [new-launch evidence](studio/evidence.json), and
[issue #1](https://github.com/ab2737/my-server-studio/issues/1). Review these
records and [PR #2](https://github.com/ab2737/my-server-studio/pull/2).
Publish the approved summary, inspect CI for the latest commit, and resolve
remaining learner contributions before reporting assignment completion.

