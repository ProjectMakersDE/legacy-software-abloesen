# Instructions for Coding Agents: Inventory of Legacy Code

This file is a task for an AI coding agent. Give it to the agent together with the project name and the path to the source code of the legacy software. The agent uses it to prepare the [inventory from phase 1 of the guide](../leitfaden/01-bestandsaufnahme.md) (in German). It does not replace watching people at work or measuring actual usage. It delivers the list of what exists in the code.

## Task

You analyse the source code of business software that is going to be replaced. Build an inventory of its functions, screens, interfaces and database tables. Propose places where anonymous usage counters could be added. Store the result as a wiki page.

## Rules

These rules apply without exception. If a step can only be done by breaking a rule, stop at that point and write the question under "Open questions".

1. Read only. Do not change code, configuration or databases. Do not run anything that writes data, starts migrations, deploys or calls services. The only files you create are the result pages. Do not commit them. A human decides that.
2. No production data. Do not connect to any production database or production system. Read the database structure from schema files, migrations, DDL exports or an empty test database that a human names explicitly.
3. No customer data leaves the machine. Do not send content from the repository to external services, not even as a search query. Do not copy personal data, credentials, hostnames or IP addresses into the result. If you find a password or key in the code, give only file and line, never the value.
4. Propose counters, do not add them. Adding a counter needs explicit approval first, because in Germany the works council and the data protection officer have to be involved before any measurement starts. Every proposed counter records only function, day and count. No user ID, no machine name, no timestamp per call.
5. Mark uncertainty. Code shows what is possible, not what is used. Never write "unused" without a measurement. Write "unreachable in code" with evidence (file, reason) or "usage unknown".

## Steps

1. Overview: language, frameworks, build, entry points, directory layout. Record the state you analysed: repository and commit.
2. Functions: business functions as users see them, derived from menus, controllers, forms, reports, print output, batch jobs and scheduled tasks. Give each function an ID (F01, F02 and so on).
3. Screens: all user interfaces, forms and dialogs, with file and related function.
4. Interfaces: inbound and outbound, for example APIs, file imports and exports, EDI, email, database links to other systems. Direction, technology, format, trigger. Name partners only by their role, such as "accounting" or "freight forwarder".
5. Database tables: meaning, which functions read and write them, triggers, stored procedures, constraints.
6. Rules that exist only in code: checks and calculations that run on save but are not enforced by the database. This list matters most for the later parallel operation, because the new system has to follow these rules when it writes to the old database.
7. Dependencies: which functions write to the same tables. This gives hints for the order of the migration.
8. Counting points: central places where one counter covers many functions at once, such as a menu handler, a shared controller base class, a job scheduler or the entry point of an interface. Flag functions that probably run rarely, for example at year end, so that a short measurement does not misjudge them.

## Result

Create the page `docs/wiki/projects/<project>/inventory.md` in the project's repository. The structure fits a project wiki that follows the pattern of ai-agent-wiki (ProjectMakers). Create the folder if it does not exist.

The frontmatter has three required keys: `title`, `verified` (date of the analysis as YYYY-MM-DD) and `source`. Links are relative Markdown links, not wikilinks. A page has at most 8,000 characters including frontmatter. The wiki's linter checks this. If the inventory gets longer, `inventory.md` stays the overview and links to sub-pages in the same folder, such as `inventory-functions.md` or `inventory-tables.md`, each with its own frontmatter. No other files are created.

Template:

```markdown
---
title: "Inventory <Project>"
verified: YYYY-MM-DD
source: "<repository>, commit <short hash>, static code analysis"
---

# Inventory <Project>

## Overview

Language, frameworks, build, entry points. What was analysed and what was not.

## Functions

| ID | Function | Entry point (file) | Screens | Tables read | Tables written | Usage |
|---|---|---|---|---|---|---|

## Screens

| Screen | File | Function |
|---|---|---|

## Interfaces

| Interface | Direction | Technology and format | Trigger | File |
|---|---|---|---|---|

## Database tables

| Table | Meaning | Read by | Written by | Triggers, procedures, constraints |
|---|---|---|---|---|

## Rules only in code

| Rule | File and location | Affected tables |
|---|---|---|

## Proposed usage counters

| Counting point | File and location | Functions covered | Note |
|---|---|---|---|

## Findings

Dead code with evidence, duplicate functions, functions with a rare rhythm, locations of credentials (file and line only).

## Open questions

What the code does not answer and a human has to clarify.
```

Without a measurement, the "Usage" column always says "unknown". Once counter data exists, a human fills it in.

## Wrap-up

At the end, report in a few sentences: paths of the pages you created, number of functions, screens, interfaces and tables found, the most important open questions, and everything you could not analyse.
