# Rules

To handle multiple rule variants that would otherwise be difficult/impossible to express using `and/or/not-any/not-all` combinators of individual matchers, the `variant` key allows multiple distinct rule bodies to be specified in a single rule. This allows us to rewrite the following two rules:

```yaml
BRLY-2021-011:
  meta:
    author: Binarly (https://github.com/binarly-io/FwHunt)
    license: CC0-1.0
    name: BRLY-2021-011
    namespace: vulnerabilities
    CVE number: CVE-2021-33627
    advisory: https://binarly.io/advisories/BRLY-2021-011/index.html
    description: SMM memory corruption vulnerability in combined DXE/SMM driver (SMRAM write)
    volume guids:
      - 74D936FA-D8BD-4633-B64D-6424BDD23D24
  code:
    and:
      - pattern: 488b5310498d48204d8b4018e8....0000
        place: child_sw_smi_handlers
      - pattern: 4981392010000075
        place: child_sw_smi_handlers
```

```yaml
BRLY-2021-011-1:
  meta:
    author: Binarly (https://github.com/binarly-io/FwHunt)
    license: CC0-1.0
    name: BRLY-2021-011-1
    namespace: vulnerabilities
    CVE number: CVE-2021-33627
    advisory: https://binarly.io/advisories/BRLY-2021-011/index.html
    description: SMM memory corruption vulnerability in combined DXE/SMM driver (SMRAM write)
    volume guids:
      - 74D936FA-D8BD-4633-B64D-6424BDD23D24
  code:
    and:
      - pattern: 488b5310498d40204c8bc948894424..4533c033c9e8
        place: child_sw_smi_handlers
```

As a single rule:

```yaml
BRLY-2021-011:
  meta:
    author: Binarly (https://github.com/binarly-io/FwHunt)
    license: CC0-1.0
    name: BRLY-2021-011
    namespace: vulnerabilities
    CVE number: CVE-2021-33627
    advisory: https://binarly.io/advisories/BRLY-2021-011/index.html
    description: SMM memory corruption vulnerability in combined DXE/SMM driver (SMRAM write)
    volume guids:
      - 74D936FA-D8BD-4633-B64D-6424BDD23D24
  variants:
    variant1:
      code:
        and:
          - pattern: 488b5310498d48204d8b4018e8....0000
            place: child_sw_smi_handlers
          - pattern: 4981392010000075
            place: child_sw_smi_handlers
    variant2:
      code:
        - pattern: 488b5310498d40204c8bc948894424..4533c033c9e8
          place: child_sw_smi_handlers
```
