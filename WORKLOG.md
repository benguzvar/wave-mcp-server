# Worklog

## Current guidance

- [README](README.md) covers installation, tool behavior, configuration and local builds.
- [Worker guide](worker/README.md) covers hosted setup, verification, connection defaults and the legacy transport retirement gates. The [hosted connector overview](docs/hosted-oauth-connector.md) explains the public routes and consent flow.
- [Contributing](CONTRIBUTING.md) covers development; [release reporting](.github/RELEASES.md) covers verified delivery and reporting recovery.
- [GitHub issues](https://github.com/oliverames/wave-mcp-server/issues) track the unfinished client transition and the remaining Worker dependency overrides.

The legacy MCP and SSE routes remain supported until the receiving-client and session-drain conditions in the Worker guide are met. The Worker keeps only the `miniflare` `sharp` and `undici` overrides in `worker/package.json`: every stable Miniflare 4 release still pins affected versions, and only Miniflare 5 alpha and beta builds resolve patched ones. The `@modelcontextprotocol/sdk` and `client` overrides were removed when Agents 0.28.1 began peering SDK 1.32.1 and client and server 2.3.1. Published artifacts and deployed Workers require their own evidence; an old source or worklog entry is not a fresh delivery receipt.

## October 23, 2026: security lockfile refresh and Worker redeploy

`2c03787` moved the server to `@modelcontextprotocol/sdk` 1.32.1, clearing the SDK session-binding, cross-origin redirect and request-size advisories, and both packages to `ip-address` 10.7.4. Root tests 74/74, Worker tests and the bundle dry run passed, and CI passed. Worker version `a93078ae-0ad0-448f-bc7b-f2f5836b48af` is deployed at 100% from `2c03787` and replaced `784d0870-03d9-4a24-98ec-51bc06c829e7`. Unauthenticated checks of `/health`, `/`, `/mcp`, `Origin` handling, `/authorize` and the OAuth metadata matched the pre-deploy baseline, and a tail showed every request `ok` with no exceptions. No signed-in tool call or Wave operation ran; if a reconnected client misbehaves, roll back to `784d0870`.

## October 13, 2026: documentation cleanup

Moved the full previous worklog into the dated archive below and replaced repeated setup, status and release discussion with links to the maintained guides. Application code, transport routes and dependency settings are unchanged. No package publication, Worker deployment or Wave operation ran for this cleanup.

## Historical record

The [complete worklog through October 13, 2026](WORKLOG-2026-10-13.md) is an exact copy of the previous file. It stays at the repository root to preserve each relative link's original context. The [preservation record](docs/archive/worklog-2026-10-13.json) records the source revision, byte count and SHA-256 digest.

<details>
<summary>Previous entry links</summary>

- [Worklog](WORKLOG-2026-10-13.md#worklog)
<a id="2026-10-07---github-issue-review-closeout"></a>
- [2026-10-07 - GitHub Issue Review Closeout](WORKLOG-2026-10-13.md#2026-10-07---github-issue-review-closeout)
<a id="2026-10-07---readme-refresh-closeout"></a>
- [2026-10-07 - README Refresh Closeout](WORKLOG-2026-10-13.md#2026-10-07---readme-refresh-closeout)
<a id="open-items"></a>
- [Open items](WORKLOG-2026-10-13.md#open-items)
<a id="2026-09-22---released-108-hosted-default-business-survives-restarts-bare-uuids-accepted"></a>
- [2026-09-22 - Released 1.0.8: hosted default business survives restarts; bare UUIDs accepted](WORKLOG-2026-10-13.md#2026-09-22---released-108-hosted-default-business-survives-restarts-bare-uuids-accepted)
<a id="2026-09-02---released-107-for-the-accountsubtypearchivable-null-schema-coverage-audit"></a>
- [2026-09-02 - Released 1.0.7 for the AccountSubtype.archivable null; schema coverage audit](WORKLOG-2026-10-13.md#2026-09-02---released-107-for-the-accountsubtypearchivable-null-schema-coverage-audit)
<a id="2026-08-27---released-105-and-106-fixed-the-version-hook-and-a-node-18-crash"></a>
- [2026-08-27 - Released 1.0.5 and 1.0.6; fixed the version hook and a Node 18 crash](WORKLOG-2026-10-13.md#2026-08-27---released-105-and-106-fixed-the-version-hook-and-a-node-18-crash)
<a id="2026-08-26---reviewed-and-repaired-the-103-observability-work-response-cache-removed"></a>
- [2026-08-26 - Reviewed and repaired the 1.0.3 observability work; response cache removed](WORKLOG-2026-10-13.md#2026-08-26---reviewed-and-repaired-the-103-observability-work-response-cache-removed)
<a id="2026-08-26---deferred-items-cleared-worker-stack-upgraded-structured-output-delete-hardening"></a>
- [2026-08-26 - Deferred items cleared: worker stack upgraded, structured output, delete hardening](WORKLOG-2026-10-13.md#2026-08-26---deferred-items-cleared-worker-stack-upgraded-structured-output-delete-hardening)
<a id="2026-08-25---improvement-pass-security-bumps-api-doc-accuracy-honest-pagination"></a>
- [2026-08-25 - Improvement pass: security bumps, API-doc accuracy, honest pagination](WORKLOG-2026-10-13.md#2026-08-25---improvement-pass-security-bumps-api-doc-accuracy-honest-pagination)
<a id="2026-08-25---comprehensive-bug-fixing-pass-five-defects-four-in-the-shared-server"></a>
- [2026-08-25 - Comprehensive bug-fixing pass: five defects, four in the shared server](WORKLOG-2026-10-13.md#2026-08-25---comprehensive-bug-fixing-pass-five-defects-four-in-the-shared-server)
<a id="earlier-history-before-2026-08-23"></a>
- [Earlier history (before 2026-08-23)](WORKLOG-2026-10-13.md#earlier-history-before-2026-08-23)
<a id="2026-09-24---mcp-sdk-v2-compatibility-migration-issue-3"></a>
- [2026-09-24 - MCP SDK v2 compatibility migration, issue #3](WORKLOG-2026-10-13.md#2026-09-24---mcp-sdk-v2-compatibility-migration-issue-3)

</details>
