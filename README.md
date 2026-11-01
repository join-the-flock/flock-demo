# Hello, Flock!

A "Hello, World!" project that uses Flock via FVM.

## Channel branches

This repository has separate `master`, `beta`, and `stable` demo branches. Each
branch's `.fvmrc` selects the same channel in `join-the-flock/flock`. Keep API
migrations channel-specific: newer Flutter APIs can reach master and beta before
stable. Master and beta use the standalone `material_ui` package; stable keeps
the framework's Material import until its matching SDK requires migration.

The workflow in this repository runs on GitHub Actions against the published
Flock SDK, using FVM and the matching demo branch for each channel. Pull requests
use their merge revision for the channel they target.

Nest's daily workflow separately checks out this repository's matching branch
and runs analysis, widget tests, and a release web build with the unpublished
assembled Flock SDK before publishing it. Nest bypasses this app's FVM settings
so it tests the candidate SDK, rather than the already-published distribution.
