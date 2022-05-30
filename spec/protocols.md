# Protocols

```yaml
  protocols:
    or:
      - name: EFI_HII_DATABASE_PROTOCOL_GUID
        value: EF9FC172-A1B2-4693-B3276D32FC416042
        service:
          name: LocateProtocol
      - name: EFI_HII_DATABASE_PROTOCOL_GUID
        value: EF9FC172-A1B2-4693-B3276D32FC416042
        service:
          name: HandleProtocol
    and:
      - name: EFI_SMM_END_OF_DXE_PROTOCOL_GUID
        value: 24E70042-D5C5-4260-8C39-0AD3AA32E93D
        service:
          name: LocateProtocol

```

JSON scheme:

```json
{
  "protocols": {
    "or": [
      {
        "name": "EFI_HII_DATABASE_PROTOCOL_GUID",
        "value": "EF9FC172-A1B2-4693-B3276D32FC416042",
        "service": {
          "name": "LocateProtocol"
        }
      },
      {
        "name": "EFI_HII_DATABASE_PROTOCOL_GUID",
        "value": "EF9FC172-A1B2-4693-B3276D32FC416042",
        "service": {
          "name": "HandleProtocol"
        }
      }
    ],
    "and": [
      {
        "name": "EFI_SMM_END_OF_DXE_PROTOCOL_GUID",
        "value": "24E70042-D5C5-4260-8C39-0AD3AA32E93D",
        "service": {
          "name": "LocateProtocol"
        }
      }
    ]
  }
}
```

# Possible kinds of matches

- `and` (or none) => and
- `or` => or (logical or of list of strings)
- `not-any` => not any of these strings
- `not-all` => not all of these strings
