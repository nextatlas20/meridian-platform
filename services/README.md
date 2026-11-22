# Service manifests

Each deployable service owns exactly one manifest at `services/<service-name>/service.yaml`.
The fields used by the release tooling are:

| Field | Meaning |
| --- | --- |
| `name` | Service identifier; must match the directory name. |
| `team` | Owning team key; resolved through `org/teams.yaml`. |
| `tier` | Criticality, `1` (highest) to `3`. |
| `runtime` | Runtime image tag used by the deploy pipeline. |
| `status` | Lifecycle state: `active`, `paused` or `deprecated`. |
| `port`, `healthcheck`, `description` | Deployment metadata, not part of the catalog. |

A service is only published in the catalog while its manifest reports `status: active`.
`paused` services are kept in the tree but pulled out of the rotation, and `deprecated`
services are on their way to the retired list.
