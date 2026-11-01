# VSlices Index

This repository owns the **public static publication surface** for VSlices, targeting `https://vslices.alive-lab.dev/`. It does not own the semantics, source code or CI of experiences it aggregates.

## First integration

```text
/
└── playground/
    └── enactment/
```

[Enactment Playground](https://github.com/vslices/enactment-playground) remains a standalone repository. Index checks out a **specific source revision**, builds and tests it, and copies its `site/` output into `public/playground/enactment/`. Updates to the upstream repository do not automatically replace the published version: revise the pin in a reviewed PR.

**Current source pin:** `1642e103b2f6db65c7c091dd410fb6d119556ab5`, merged from [Enactment PR #4](https://github.com/vslices/enactment-playground/pull/4). This revision keeps the Composition promotion simulator and v1 legacy compatibility, and introduces the sticky, scenario-oriented sidebar with the canonical protocol link.

## Publication

- Enable GitHub Pages **GitHub Actions** as the publishing source for this repository.
- Configure Pages custom domain `vslices.alive-lab.dev` and Cloudflare DNS for the `vslices` host, respecting existing records and GitHub's instructions.
- The only `CNAME` belongs at this site's published root. The child application uses relative asset paths.
- Confirm HTTPS and direct navigation to `/playground/enactment/` after activation.

The proposed domain, DNS and Pages settings are **not yet applied**. No runtime backend, Cloudflare Worker or additional paid service is required for this static integration.

## Ownership

The child repository owns its implementation and tests; this repository owns public assembly, the selected child revision and the result deployed under the host.
