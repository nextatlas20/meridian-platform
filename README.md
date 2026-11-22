# meridian-platform

Monorepo for the Meridian customer-facing API stack: billing, checkout, identity,
metering and reporting services. Every deployable unit lives in its own directory and
carries a manifest that the release tooling reads.

```
meridian-platform/
├── catalog/                 # machine-readable indexes consumed by the status page
├── docs/                    # operator documentation
├── org/teams.yaml           # team ownership registry
└── services/<name>/service.yaml
```

Release branches are cut from `main` (`release/YYYY.MM`) and only receive the services
that are shipping in that release.
