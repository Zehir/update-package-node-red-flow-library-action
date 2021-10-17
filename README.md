# Update Node-Red flow-library

Update or add a Node-Red package on the Node-Red flow library (flows.nodered.org).

## Inputs

### `package-name`

**Required** The name of the package. Default `""`.

## Outputs

### `result`

The result of update

## Example usage

```yaml
name: NPM Publish

on:
  push:
    branches:
      - main

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v1
      - uses: actions/setup-node@v1
        with:
          node-version: 10
      - run: npm install
      - run: npm test
      - id: publish
        uses: JS-DevTools/npm-publish@v1
        with:
          token: ${{ secrets.NPM_TOKEN }}
      - if: steps.publish.outputs.type != 'none'
        name: Update Node-Red flow-library
        uses: Zehir/update-package-node-red-flow-library-action@v1.0.4
        continue-on-error: true
        with:
          package-name: 'node-red-contrib-deconz'

```
