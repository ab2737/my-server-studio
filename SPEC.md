# Lesson 01 specification

## STUDIO-001 · Launch a tested calculator on an existing server

**Status:** Approved new launch and repeat runtime verification passed.
**Next step:** Review the learning summary; keep decision and check-limit explanation remain incomplete.
**Instructor implementation:** [issue #9](https://github.com/kaw393939/373_hosting/issues/9).
Create your own issue from the [lesson template](.github/ISSUE_TEMPLATE/studio-calculator.md).

## Agreed result

Launch the supplied published calculator image through your existing Traefik
network and a nonconflicting HTTPS hostname. Preserve unrelated services and
host access. Do not add another proxy/updater or build a substitute image.
The [release selection](studio/calculator-release.json) supplies the expected
commit and multi-platform digest independently of the running website.
An explicitly agreed adoption of a matching existing deployment is recorded
as adoption, not a fresh launch. This bounded lesson does not certify the whole
server baseline or a vulnerability-free image.

- **Public hostname:** `https://calc.angelobustamanteselfhost.com`.
- **New launch or adopted deployment, and reason:** Proposed new launch; the
  read-only studio doctor reported `ready` / `launch-new`, with three existing
  containers and no conflicting calculator route. The learner approved launch;
  the successful new-launch report is preserved in [studio/evidence.json](studio/evidence.json).
  A subsequent verification also passed; its `already-managed` provenance
  describes that later check, rather than an adoption of pre-existing work.
- **Own issue / feature branch:** [Issue #1](https://github.com/ab2737/my-server-studio/issues/1)
  (confirmed open in the learner's signed-in GitHub browser) /
  `studio-001-calculator`.
- **Agreed scope or actual access/configuration gap:** Add only the pinned course
  calculator image on the existing `angelo-cicd_default` network, using the
  existing `websecure` entrypoint and `letsencrypt` certificate resolver.
  Preserve production, QA and Traefik. The learner's DNS lookup returned the
  droplet address. Private SSH settings remain in ignored local configuration.
  The local CLI was extended with an optional certificate-resolver setting
  because this proxy enables TLS per router. The generated plan includes
  `tls=true` and `tls.certresolver=letsencrypt`; it does not modify the proxy.
  The image is selected by `studio/calculator-release.json`, digest
  `sha256:aec414c990a5de6ed74c9e8dcb105b78f6358c03a8cea70a9d40dcda51c3a8fa`.
  Available memory was 214 MiB without swap; the calculator's 256 MiB ceiling
  is a limit, not a measured requirement. After launch the calculator used
  approximately 47 MiB and the host had 152 MiB available.
  Local formatting passed and the added resolver test passed; broader checks
  encountered Windows-specific failures. All three jobs in
  [CI run 41768514803](https://github.com/ab2737/my-server-studio/actions/runs/41768514803)
  passed, including the full studio check and browser E2E.

Private SSH targets and configuration stay in ignored local state. Share only
reviewed, selected evidence; never commit credentials or raw server output.

## Evidence to keep

| Evidence | Actual result / link |
|---|---|
| Prepared Black/Pylint/pytest and real-image browser checks | Full studio CI passed in [run 41768514803](https://github.com/ab2737/my-server-studio/actions/runs/41768514803), including real-image browser E2E; local Windows limitations remain recorded. |
| Hosted image/commit, trusted HTTPS, valid and rejected API cases | Launch and repeat verification passed; [new-launch evidence](studio/evidence.json). Multiplication returned 42 (200), division by zero 400, numeric string 422. |
| Preservation of unrelated services | All three pre-existing containers retained identity, state and published ports during launch and verification; see evidence. This is not a complete application health check. |
| Own prediction, check interpretation, browser observation and keep/revise reason | [LEARNING.md](LEARNING.md): learner observed 42 in browser and API and reported secure loading after restarting Chrome. Prediction, check limits and keep reason remain incomplete; AI assistance disclosed. |
| Accuracy review before publishing learner excerpts | Learner approved the displayed summary with “Yes, publish the summary”. The earlier brief SPEC observation was published before review; this was disclosed in chat. |
| Actual PR, latest CI, merge and issue closure | [PR #2](https://github.com/ab2737/my-server-studio/pull/2), all three CI jobs passed on commit 9f0f23b; merge and issue closure pending. |

Link the exported `studio/evidence.json`, actual CI and issue/PR when available.
CI does not deploy this server. A fixture, green check, timestamp, closed issue
or AI assertion alone does not establish the full result. `status` reports
recorded evidence and readiness for instructor review; it does not grade,
certify authorship or establish understanding.

## Optional instructor history

The records below are background, not steps to repeat. Their original anchors
remain here so earlier links continue to work.

## HOST-001 · Keep the Traefik dashboard private

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-001--keep-the-traefik-dashboard-private).

## HOST-002 · Controlled host maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-002--controlled-host-maintenance).

## HOST-003 · Companion image security maintenance

[Historical requirement and evidence](book/changes/hosting-spec-history.md#host-003--companion-image-security-maintenance).
