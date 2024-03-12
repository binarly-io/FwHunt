# PPI

Similar with [protocols](./protocols.md)

```yaml
...
  ppi:
    and:
      - name: EFI_PEI_READ_ONLY_VARIABLE2_PPI_GUID
        value: 2AB86EF5-ECB5-4134-B5563854CA1FE1B4
        service:
          name: LocatePpi
```

JSON representation:

```json
{
  "ppi": {
    "and": [
      {
        "name": "EFI_PEI_READ_ONLY_VARIABLE2_PPI_GUID",
        "value": "2AB86EF5-ECB5-4134-B5563854CA1FE1B4",
        "service": {
          "name": "LocatePpi"
        }
      }
    ]
  }
}
```
