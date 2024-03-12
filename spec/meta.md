# Metadata

```yaml
BRLY-2022-016:
  meta:
    author: Binarly (https://github.com/binarly-io/FwHunt)
    license: CC0-1.0
    name: BRLY-2022-016
    version: "1.0"
    namespace: vulnerabilities
    CVE number: CVE-2022-33209
    vendor id: INTEL-SA-00712
    architecture: X86:LE:64
    advisory: https://binarly.io/advisories/BRLY-2022-016/index.html
    url: https://www.intel.com/content/www/us/en/security-center/advisory/intel-sa-00712.html
    description: Stack overflow vulnerability in SMI handler
    volume guids:
      - 8e61fd6b-7a8b-404f-b83f-aa90a47cabdf
```

JSON representation:

```json
{
  "BRLY-2022-016": {
    "meta": {
      "author": "Binarly (https://github.com/binarly-io/FwHunt)",
      "license": "CC0-1.0",
      "name": "BRLY-2022-016",
      "version": "1.0",
      "namespace": "vulnerabilities",
      "CVE number": "CVE-2022-33209",
      "vendor id": "INTEL-SA-00712",
      "architecture": "X86:LE:64",
      "advisory": "https://binarly.io/advisories/BRLY-2022-016/index.html",
      "url": "https://www.intel.com/content/www/us/en/security-center/advisory/intel-sa-00712.html",
      "description": "Stack overflow vulnerability in SMI handler",
      "volume guids": [
        "8e61fd6b-7a8b-404f-b83f-aa90a47cabdf"
      ]
    }
  }
}
```

## Targets

There are scenarios where FwHunt can be used to scan targets other than UEFI modules.
For these scenarios, the `target` field of the metadata should be defined, which is a hint to the tool that will load the rules.

### module

To scan the UEFI module of any kind (PEI, DXE, SMM, ...), use the following specifier in the metadata:

```yaml
meta:
  target: module
```

`module` is the default target and may be unspecified.

### firmware

To scan the firmware, use the following specifier in the metadata:

```yaml
meta:
  target: firmware
```

Example: [MsiLeakBootGuardKeys](https://github.com/binarly-io/FwHunt/blob/main/rules/SupplyChain/MsiLeakBootGuardKeys.yml)

### bootloader

To scan the bootloader, use the following specifier in the metadata:

```yaml
meta:
  target: bootloader
```

Example: [BlackLotusBootkit](https://github.com/binarly-io/FwHunt/blob/main/rules/Threats/BlackLotusBootkit.yml)

## Volume GUIDs

To scan only selected firmware modules, it is necessary to list them in the `volume guids` field of the metadata.
If the list of `volume guids` is empty and `target` is `module`, it is assumed that all modules extracted from the firmware will be scanned.
