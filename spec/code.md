# Code (pattern search)

```yaml
...
  code:
    or:
      - pattern: 4d85c974..49813900200000
        place: child_sw_smi_handlers
      - pattern: 0fb704250e040000c1e00405040100008b08
        place: sw_smi_handlers
```

JSON scheme:

```json
{
  "code": {
    "or": [
      {
        "pattern": "4d85c974..49813900200000",
        "place": "child_sw_smi_handlers"
      },
      {
        "pattern": "0fb704250e040000c1e00405040100008b08",
        "place": "sw_smi_handlers"
      }
    ]
  }
}
```

# Possible syntax for defining ECode-based search

```yaml
...
  ecode:
    - op: BINOP
      kind: ADD
      args:
       - ...
       - ...
    - skip: true
      min: 0
      max: 10
```

JSON scheme:

```json
{
  "ecode": [
    {
      "op": "BINOP",
      "kind": "ADD",
      "args": [
        "...",
        "..."
      ]
    },
    {
      "skip": true,
      "min": 0,
      "max": 10
    }
  ]
}
```
