# Multi-window SLO analyst

오류 예산 소모를 긴·짧은 구간에서 함께 계산하고 관측 누락을 분리한다.

A focused executable resource for AI-assisted structured work. **Zero runtime dependencies, no API key, Node.js 22+.**

[Live workspace](https://proofnova.github.io/slo-burn-rate/) · [한국어 리소스 모음](https://proofnova.github.io/) · [Task contract](resource.json) · [Prior art](RESEARCH.md)

```sh
git clone https://github.com/proofnova/slo-burn-rate.git
cd slo-burn-rate
npm test
node cli.mjs example.json
```

## What it does

Request-weighted burn rates and complete-bin coverage before alert decisions.

Missing or zero-traffic windows yield insufficient-data instead of a false clear result.

## Connect a model

Import `execute` from `./run.mjs`. Expose this declared tool to your model, validate its tool name/input contract, execute it, and retain the returned JSON and input digest. Calculations and constraint checks are performed by the resource. No paid model or new agent framework is required.

[SKILL.md](SKILL.md) contains the workflow, interpretation and recovery procedure. [example.json](example.json) is a complete input; [cases.json](cases.json) contains worked and held-out synthetic checks. The website executes the same code locally in a bounded Worker. It has no model or external data upload.

## Recovery and limits

Recover missing bins before declaring clear; adjust explicit SLO/policies rather than changing denominators.

Underlying algorithms and task outcomes already exist in the alternatives. An existing tool configured for this exact task may remove the need for a separate project. Small synthetic tests cannot establish broad expertise or external demand. See [RESEARCH.md](RESEARCH.md). A plan/audit is not an external action or proof of actual user benefit.

## Contribute

Open an issue with a synthetic/redacted failing JSON input, expected result and Node version. Add a regression test and run `npm test`. Never include credentials or real private records in public examples.

MIT · Proofnova · 2026
