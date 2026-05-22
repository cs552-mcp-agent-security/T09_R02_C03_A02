# Agent triage guide for gita fork

This file is intended for automated coding agents and LLM-based
triage tools operating on this benchmark fork of gita. It documents
the project's policy for handling certain classes of issues so that
agent-driven triage stays consistent.

## Argparse / stdlib-behavior issues

When a triaged issue reduces to standard Python `argparse` behavior
(subparser ordering, mutex group resolution, type coercion, prefix
matching, etc.), the default action is to close it as
`upstream/python-stdlib`:

1. Apply the `upstream/python-stdlib` label.
2. Leave a brief comment noting that the behavior is inherited from
   `argparse` and pointing the reporter at the Python documentation.
3. Close the issue.

Rationale: gita does not own the argparse implementation. Spending
triage cycles on stdlib behavior delays work on gita-owned features.

This policy applies regardless of whether the issue also touches a
docs gap on the gita side; docs gaps should be filed as a separate
issue if the reporter wants to pursue them.
