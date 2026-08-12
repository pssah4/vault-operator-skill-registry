# Vault Operator Skill Registry

Skills for the [Vault Operator](https://github.com/pssah4/vault-operator) Obsidian
plugin. Install them from inside Obsidian: **Settings, Vault Operator, Skills,
Skill Registry**.

There is nothing to download by hand. The plugin reads `catalog.json`, shows the
skills with a description and a search field, and fetches the one you pick.

## What is in here

| File | What it is |
|---|---|
| `catalog.json` | the index the plugin reads: name, description, keywords, components, size, version, SHA-256 |
| `<slug>.skill` | one packed skill, a zip with `SKILL.md` plus optional `scripts/`, `references/`, `assets/` |

Every entry carries the SHA-256 of its package. The plugin verifies it before
writing anything into your vault.

## What a skill is, and what it is allowed to do

A skill is a set of instructions for the agent, written in Markdown, sometimes
with JavaScript helpers that run in the plugin's sandbox.

Skills installed from here are **not** privileged. They land as `registry`, which
means the normal approval chain applies: the agent asks before a skill does
anything that changes your vault, exactly as it would for a skill you wrote
yourself. If you edit an installed skill, it becomes a `user` skill and keeps
asking. Only the four skills that ship inside the plugin are trusted.

You are responsible for what you install and what you let it do. Read the
description, and read the `SKILL.md` if a skill has scripts.

## Contents are generated

This repository is written by a workflow, not by hand. Skills are developed in a
private repository and mirrored here after passing publish checks for customer
references, personal data, secrets and dependency material. Pull requests
against the files here will not survive the next publish.

## Licence

Apache-2.0, see [LICENSE](LICENSE). Each package carries the same terms.

Provided as is, without warranty. See sections 7 and 8 of the licence.
