# Triage Labels

The skills speak in terms of five canonical triage roles. This file maps those roles to the actual label strings used in this repo's issue tracker.

| Label in mattpocock/skills | Label in our tracker | Meaning                                  |
| -------------------------- | -------------------- | ---------------------------------------- |
| `needs-triage`             | `needs-triage`       | Maintainer needs to evaluate this issue  |
| `needs-info`               | `needs-info`         | Waiting on reporter for more information |
| `ready-for-agent`          | `ready-for-agent`    | Fully specified, ready for an AFK agent  |
| `ready-for-human`          | `ready-for-human`    | Requires human implementation            |
| `wontfix`                  | `wontfix`            | Will not be actioned                     |

When a skill mentions a role (e.g. "apply the AFK-ready triage label"), use the corresponding label string from this table.

Also in use, outside the triage vocabulary (created by `/wayfinder`, not by `/triage`):

| Label                | Meaning                                                    |
| -------------------- | ---------------------------------------------------------- |
| `wayfinder:map`      | A wayfinder map: destination, fog and decisions for one workstream |
| `wayfinder:research` | Wayfinder ticket: answer a question by reading/gathering   |
| `wayfinder:prototype`| Wayfinder ticket: build a throwaway probe                  |
| `wayfinder:grilling` | Wayfinder ticket: grill the human on a decision            |
| `wayfinder:task`     | Wayfinder ticket: plain implementation work                |

All of these labels exist in the repo (`zanmingwang57-tech/dsh111`). Re-check with `gh label list`.
