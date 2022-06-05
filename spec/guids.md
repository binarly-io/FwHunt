# GUIDs

Similar with [protocols](./protocols.md)

```yaml
...
  guids:
    not-any:
      - name: EFI_PLATFORM_INFO_GUID
        value: 1E2ACC41-E26A-483D-AFC7A056C34E087B
      - name: EFI_STATUS_CODE_SPECIFIC_DATA_GUID
        value: 335984BD-E805-409A-B8F8D27ECE5FF7A6
```

JSON scheme:

```json
{
  "guids": {
    "not-any": [
      {
        "name": "EFI_PLATFORM_INFO_GUID",
        "value": "1E2ACC41-E26A-483D-AFC7A056C34E087B"
      },
      {
        "name": "EFI_STATUS_CODE_SPECIFIC_DATA_GUID",
        "value": "335984BD-E805-409A-B8F8D27ECE5FF7A6"
      }
    ]
  }
}
```
