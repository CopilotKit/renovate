# renovate

Shared Renovate config for CopilotKit + ag-ui-protocol orgs.

Each repo's `renovate.json` extends this preset:

```json
{
    "$schema": "https://docs.renovatebot.com/renovate-schema.json",
    "extends": ["local>CopilotKit/renovate"]
}
```

## What this preset does (Phase 1)

- **GitHub Actions ecosystem only.** npm/pip stay on Dependabot.
- One grouped PR per repo, daily before 5am PT, covering all GHA bumps (minor, patch, AND major together).
- Automerge on green CI for the GitHub Actions group.
- SHA-pinning for actions (`helpers:pinGitHubActionDigests`) with digest changelogs.
- One Dependency Dashboard issue per repo summarizing pending updates.

## Scope

The plan deliberately excludes:

- npm / pip / docker / gomod / etc. (Dependabot keeps these for now)
- `CopilotKit/CopilotCloud` (orphaned project, do not maintain)

See Notion plan `3613aa38-1852-81a3-8863-fcff2907021c` for full migration rationale.
