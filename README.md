# Automated-Commit

A GitHub Actions workflow that automatically updates a `TIMESTAMP.txt` file with the current date and time every 12 hours, then commits and pushes the change.

## Overview

The `Automated-Commit` workflow demonstrates how GitHub Actions can automate routine repository tasks. Specifically, this workflow:

- Checks out the latest code from the `master` branch.
- Updates the `TIMESTAMP.txt` file with the current date and time.
- Commits the change if any modification is detected.
- Pushes the change back to the `master` branch.

## Workflow Structure

The workflow is defined in `.github/workflows/master.yml` and includes:

- **Triggers**: Runs on every push to `master`, on a schedule every 12 hours, and can be manually triggered via `workflow_dispatch`.
- **Job**: `update_commit` runs on the latest Ubuntu runner, configures git, updates `TIMESTAMP.txt`, and commits + pushes.
- **Permissions**: `contents: write` granted to the workflow.

## Usage

1. Fork or use this repository as a template.
2. In `.github/workflows/master.yml`, set `git config user.email` and `user.name` to your own identity.
3. Push to `master`. The workflow runs immediately (on push) and again every 12 hours.
4. View runs under the **Actions** tab. Manually trigger anytime via **Run workflow**.

## Timeline

- Triggered every 12 hours (`0 */12 * * *`).
- Manual runs supported via `workflow_dispatch`.