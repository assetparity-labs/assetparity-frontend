# AssetParity transfer-assurance console

A campaign-oriented interface for comparing classic payment and SAC transfer behavior. It is designed around a transfer matrix and an evidence inspector, rather than a generic JSON editor.

## Workflow

- Pick cases from the transfer suite.
- Name and save a campaign to the local evidence store.
- Select a matrix row to inspect each route's before/after asset balances and separate native fees.
- Open saved campaigns after restarting the service.
- Import observation files or export a complete campaign bundle.
- Use the coverage map to distinguish supported, excluded and future suites.

Run `node server.mjs` alongside the sibling backend service, then open http://127.0.0.1:4380. The frontend proxies its local API to 127.0.0.1:4381. CSP limits scripts, styles and network access to the same origin. Imported text is rendered through text nodes, not interpreted as HTML. No wallet connection or transaction submission is exposed.

The console labels synthetic and imported observations explicitly. A green conformance result is limited to the declared comparison scope; it is not a consensus-verification or production-safety certificate.

`node --test test.mjs` checks the served console shell and CSP. Campaign creation, matrix inspection and coverage navigation are also manually exercised in the browser. [Workspace setup](https://github.com/assetparity-labs/assetparity-backend).
