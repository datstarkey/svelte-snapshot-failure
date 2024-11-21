# Replication

To replicate, install the project in the root with `pnpm i`

Enable TS server Logging

Navigate to `shared/src/lib/index.ts` in your IDE

Everything looks okay

Navigate to `web/src/lib/index.ts` in your IDE

Everything looks okay

Leave `web/src/lib/index.ts` open and close vscode
Reopen vscode

Everything looks okay

Navigate to `shared/src/lib/index.ts`

Error: `Cannot find module './MyComponent.svelte' or its corresponding type declarations.ts(2307)`

TS Server Log Error:

`info 55   [14:57:24.357] -Svelte Plugin- Svelte snapshot was not found after trying to load script snapshot for /Users/jake/Repos/svelte-snapshot-failure/shared/src/lib/MyComponent.svelte`

Only way to fix is to restart VScode

## Differences

I've tried this with and without project references, path alias's and installing the project as pnpm workspace package, and it always gives the same error

## Workaround

Package and build shared

- this ruins the developer experience as you lose go to source between packages
- increased build time as you have to build the shared project for each change

More Log:

```
Info 47   [14:57:24.303] -Svelte Plugin- Starting Svelte plugin
Info 48   [14:57:24.304] -Svelte Plugin- svelteOptions: {"namespace":"svelteHTML"}
Info 49   [14:57:24.304] -Svelte Plugin- Svelte snapshot was not found after trying to load script snapshot for /Users/jake/Repos/svelte-snapshot-failure/shared/src/lib/MyComponent.svelte
Info 50   [14:57:24.305] -Svelte Plugin- Successfully read Svelte file contents of /Users/jake/Repos/svelte-snapshot-failure/shared/src/routes/+page.svelte
Info 51   [14:57:24.305] -Svelte Plugin- SvelteSnapshot: /Users/jake/Repos/svelte-snapshot-failure/shared/src/routes/+page.svelte - patched scriptInfo
Info 52   [14:57:24.305] Plugin validation succeeded
Info 53   [14:57:24.306] Starting updateGraphWorker: Project: /Users/jake/Repos/svelte-snapshot-failure/shared/tsconfig.json
Info 54   [14:57:24.357] -Svelte Plugin- Resolved ./MyComponent.svelte to Svelte file /Users/jake/Repos/svelte-snapshot-failure/shared/src/lib/MyComponent.svelte
Info 55   [14:57:24.357] -Svelte Plugin- Svelte snapshot was not found after trying to load script snapshot for /Users/jake/Repos/svelte-snapshot-failure/shared/src/lib/MyComponent.svelte
Info 56   [14:57:24.454] Finishing updateGraphWorker: Project: /Users/jake/Repos/svelte-snapshot-failure/shared/tsconfig.json projectStateVersion: 1 projectProgramVersion: 0 structureChanged: true structureIsReused:: Not Elapsed: 148.47679199999993ms
Info 57   [14:57:24.454] Project '/Users/jake/Repos/svelte-snapshot-failure/shared/tsconfig.json' (Configured)
Info 58   [14:57:24.454] 	Files (127)

Info 59   [14:57:24.454] -----------------------------------------------
Info 60   [14:57:24.456] getConfigFileNameForFile:: File: /Users/jake/Repos/svelte-snapshot-failure/shared/tsconfig.json ProjectRootPath: /Users/jake/Repos/svelte-snapshot-failure:: Result: undefined
Info 61   [14:57:25.886] Host configuration update for file /Users/jake/Repos/svelte-snapshot-failure/shared/src/lib/index.ts
Info 62   [14:57:30.277] Starting updateGraphWorker: Project: /dev/null/auxiliaryProject1*
Info 63   [14:57:30.279] Finishing updateGraphWorker: Project: /dev/null/auxiliaryProject1* projectStateVersion: 1 projectProgramVersion: 0 structureChanged: true structureIsReused:: Not Elapsed: 2.1462919999994483ms
Info 64   [14:57:30.279] Project '/dev/null/auxiliaryProject1*' (Auxiliary)
Info 65   [14:57:30.279] 	Files (1)
```
