# NVRAM

Similar with [protocols](./protocols.md)

```yaml
...
  nvram:
    or:
      - name: NetworkStackVar
        guid: D1405D16-7AFC-4695-BB12-41459D3695A2
        service:
          name: GetVariable
      - name: NetworkStackVar
        guid: D1405D16-7AFC-4695-BB12-41459D3695A2
        service:
          name: SetVariable
```

JSON representation:

```json
{
  "nvram": {
    "or": [
      {
        "name": "NetworkStackVar",
        "guid": "D1405D16-7AFC-4695-BB12-41459D3695A2",
        "service": {
          "name": "GetVariable"
        }
      },
      {
        "name": "NetworkStackVar",
        "guid": "D1405D16-7AFC-4695-BB12-41459D3695A2",
        "service": {
          "name": "SetVariable"
        }
      }
    ]
  }
}
```
