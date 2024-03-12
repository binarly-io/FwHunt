# Strings

## strings

```yaml
  strings:
    or:
      - string2
      - string3
    and:
      - string0
      - string1
```

JSON representation:

```json
{
  "strings": {
    "or": [
      "string2",
      "string3"
    ],
    "and": [
      "string0",
      "string1"
    ]
  }
}
```

## wide_strings

```yaml
  wide_strings:
    or:
      - widestring2
      - widestring3
    and:
      - widestring0
      - widestring1
```

To specify the endianness of wide strings:

```yaml
  wide_strings:
    and:
      - utf16le: widestring0
      - utf16be: widestring1
```

If the strings are specified as a list of strings, we default to little endian encoding.

JSON representation:

```json
{
  "wide_strings": {
    "or": [
      "widestring2",
      "widestring3"
    ],
    "and": [
      "widestring0",
      "widestring1"
    ]
  }
}
```

```json
{
  "wide_strings": {
    "and": [
      {
        "utf16le": "widestring0"
      },
      {
        "utf16be": "widestring1"
      }
    ]
  }
}
```

## hex_strings

```yaml
  hex_strings:
    or:
      - hexstring2
      - hexstring3
    and:
      - hexstring0
      - hexstring1
```

JSON representation:

```json
{
  "hex_strings": {
    "or": [
      "hexstring2",
      "hexstring3"
    ],
    "and": [
      "hexstring0",
      "hexstring1"
    ]
  }
}
```


# Possible kinds of string matches

- `and` (or none) => and
- `or` => or (logical or of list of strings)
- `not-any` => not any of these strings
- `not-all` => not all of these strings
