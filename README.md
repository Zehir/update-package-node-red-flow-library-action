# Update Node-Red flow-library

Update or add a Node-Red package on the Node-Red flow library (flows.nodered.org).

## Inputs

## `package-name`

**Required** The name of the package. Default `""`.

## Outputs

## `result`

The result of update

## Example usage

```
uses: actions/update-package-node-red-flow-library-action@v1.0.2
with:
  package-name: 'node-red-contrib-deconz'
```
