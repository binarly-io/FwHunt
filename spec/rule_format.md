# FwHunt rule format

## Blocks

* meta
* code
* strings
* wide_strings
* hex_strings
* nvram
* protocols
* ppi
* guids

## meta

```
UsbRt-INTEL-SA-00057:
  meta:
    author:       Binarly
    licence:      https://creativecommons.org/publicdomain/zero/1.0/
    name:         UsbRt-INTEL-SA-00057
    version:      1.0
    namespace:    vulnerabilities
    vendor id:    INTEL-SA-00057
    advisory:     https://www.intel.com/content/www/us/en/security-center/advisory/intel-sa-00057.html
    url:          https://...
    description:  Detection for arbitrary code execution in SMM
    volume guids:
      - dcd13040-23d8-41c6-b8f5-22281a0d64e8
```

Note: each key is optional

## code

```
...
  code:
    0:
      pattern: 0fb704250e040000c1e00405040100008b08
        # 0fb704250e040000                    movzx   eax, word ptr ds:40Eh
        # c1e004                              shl     eax, 4
        # 0504010000                          add     eax, 104h
        # 8b08                                mov     ecx, [rax]; data
      place:
        - sw_smi_handlers
...
```

Place - where the recursive search for code patterns occurs:

* sw_smi_handlers - inside SW SMI handlers
* child_sw_smi_handlers - inside child SW SMI handlers

## strings, wide_strings, hex_strings

```
...
  strings:
    0: string1
    1: string2
    2: string3
  wide_strings:
    0: wide_string1
    1: wide_string2
    2: wide_string3
  hex_strings:
    0: c0c0c0......c1c1c1
    1: 55aa55aa55aa
    ...
...
```

## guids

```
...
  guids:
    - 0:
      - name: EFI_PLATFORM_INFO_GUID
      - value: 1E2ACC41-E26A-483D-AFC7A056C34E087B
    - 1:
      - name: EFI_STATUS_CODE_SPECIFIC_DATA_GUID
      - value: 335984BD-E805-409A-B8F8D27ECE5FF7A6
...
```

## ppi

```
...
  ppi:
    - 0:
      - name: EFI_PEI_READ_ONLY_VARIABLE2_PPI_GUID
      - value: 2AB86EF5-ECB5-4134-B5563854CA1FE1B4
      - service:
        - name: LocatePpi
    - 1:
      ...
...
```

## protocols

```
...
  protocols:
    - 0:
      - name: EFI_HII_DATABASE_PROTOCOL_GUID
      - value: EF9FC172-A1B2-4693-B3276D32FC416042
      - service:
        - name: LocateProtocol
    - 1:
      - name: EFI_LOADED_IMAGE_PROTOCOL_GUID
      - value: 5B1B31A1-9562-11D2-8E3F00A0C969723B
      - service:
        - name: HandleProtocol
    - 2:
      ...
...
```

## nvram

```
...
  nvram:
    - 0:
      - name: NetworkStackVar
      - guid: D1405D16-7AFC-4695-BB12-41459D3695A2
      - service:
        - name: GetVariable
    - 1:
      ...
...
```
