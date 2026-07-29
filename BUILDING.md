# Building ToonFlow Web

## Toolchain

- Node.js `24.18.0`
- Yarn Classic `1.22.22`

Use a Node version manager with `.nvmrc`, or install the exact Node.js release.
Corepack included with Node 24 can run the pinned Yarn version:

```powershell
corepack yarn --version
corepack yarn install --frozen-lockfile
```

Do not regenerate `yarn.lock` during a baseline build.

## Checks and Build

Run from the repository root:

```powershell
corepack yarn type-check
corepack yarn i18n:check
corepack yarn build
```

The upstream repository does not currently define lint or automated test
scripts. `build` includes the Vue TypeScript check and creates the Vite
production output under `dist/`.

At baseline revision `9c4cb0ec7d4f6b4067c7768e2df8cdc7f8587214`,
`type-check` and the standard `build` are blocked by an upstream syntax error at
`src/views/production/components/workbench/generate copy.vue:1063`. This is
tracked as TASK-002A in the Platform repository. Until that focused fix is
reviewed, the reproducible Vite artifact command is:

```powershell
corepack yarn build-only
```

This command does not replace the failed type check; both results must be
reported together.

## Local Smoke Test

Run the development server on its configured port:

```powershell
corepack yarn dev
```

Open `http://localhost:50188/` and verify that the first meaningful screen
renders without a framework error overlay or relevant console errors.
