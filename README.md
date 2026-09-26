# Automated Issue Closing

A repository to test GitHub automation for closing labeled issues.

## Automation

This repo includes a GitHub Actions workflow at
[`.github/workflows/auto-close-issues.yml`](.github/workflows/auto-close-issues.yml) that
automatically closes any issue labeled `completed` or `wontfix`.

- **Instant trigger**: fires as soon as one of those labels is added to an issue.
- **Hourly sweep**: also runs on a schedule (`cron: "0 * * * *"`) to catch any issue that
  already had the label before the workflow existed, or that was missed for any reason.
- **Manual trigger**: can be run on demand from the Actions tab (`workflow_dispatch`).

When it closes an issue, it first leaves a comment explaining why, then sets the issue state
to closed.
