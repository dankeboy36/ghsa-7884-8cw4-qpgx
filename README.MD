### ghsa-7884-8cw4-qpgx

Bare minimum setup to reproduce [GHSA-7884-8cw4-qpgx](https://github.com/advisories/GHSA-7884-8cw4-qpgx). See [github/advisory-database#3487](https://github.com/github/advisory-database/issues/3487) for more details.

This example uses `npm` [workspaces](https://docs.npmjs.com/cli/v7/using-npm/workspaces). There are two [`private`](https://docs.npmjs.com/cli/v7/configuring-npm/package-json#private) packages: `arduino-ide-extension`, and the `other` (naming is irrelevant for the latter).

### Steps

1. Install the dependencies. The project does not have any dependencies.
    ```sh
    npm i
    ```

1. Verify the `workspaces` is correctly configured. Expect the project name to be echoed to the standard out.

    ```sh
    npm run echo
    ```

1. Run `npm audit`

    ```sh
    npm audit
    ```

#### Actual output:

```sh
% npm audit
# npm audit report

arduino-ide-extension  *
Severity: critical
Malware in arduino-ide-extension - https://github.com/advisories/GHSA-7884-8cw4-qpgx
No fix available
node_modules/arduino-ide-extension
packages/arduino-ide-extension

1 critical severity vulnerability

Some issues need review, and may require choosing
a different dependency.
```
