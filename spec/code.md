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

JSON representation:

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
