# Metadata

```yaml
UsbRt-INTEL-SA-00057:
  meta:
    author:       Binarly
    license:      https://creativecommons.org/publicdomain/zero/1.0/
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

JSON scheme:

```json
{
  "UsbRt-INTEL-SA-00057": {
    "meta": {
      "author": "Binarly",
      "license": "https://creativecommons.org/publicdomain/zero/1.0/",
      "name": "UsbRt-INTEL-SA-00057",
      "version": 1.0,
      "namespace": "vulnerabilities",
      "vendor id": "INTEL-SA-00057",
      "advisory": "https://www.intel.com/content/www/us/en/security-center/advisory/intel-sa-00057.html",
      "url": "https://...",
      "description": "Detection for arbitrary code execution in SMM",
      "volume guids": [
        "dcd13040-23d8-41c6-b8f5-22281a0d64e8"
      ]
    }
  }
}
```

## Targets

We support scenarios where FwHunt can be used to scan targets other than UEFI modules.

### firmware

To scan the firmware, use the following specifier in the metadata:

```yaml
meta:
  target: firmware
```

Example: [MsiLeakBootGuardKeys](https://github.com/binarly-io/FwHunt/blob/main/rules/SupplyChain/MsiLeakBootGuardKeys.yml)

### boot-loader

To scan the boot loader, use the following specifier in the metadata:

```yaml
meta:
  target: boot-loader
```

Example: [BlackLotusBootkit](https://github.com/binarly-io/FwHunt/blob/main/rules/Threats/BlackLotusBootkit.yml)
