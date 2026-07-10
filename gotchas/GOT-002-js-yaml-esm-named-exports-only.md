---
id: GOT-002
type: gotcha
title: js-yaml v5 ESM has named exports only — default import crashes at runtime
status: verified
feature: FEA-002
files:
  - repo: jarvis
    path: src/core/exportBlock.ts
tags:
  - jarvis
  - esm
  - dependencies
created: 2026-07-07T00:00:00.000Z
commits:
  - 'jarvis:3fcd97b'
---

`import yaml from 'js-yaml'` type-checks but `yaml.load` is undefined at runtime under Node ESM with js-yaml v5. Must use `import { load } from 'js-yaml'`. Hit during slice-4 Task 2; tsc alone does not catch it — only a runtime test does.
