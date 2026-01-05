# CDES Reference Data

Official reference datasets for the [Cannabis Data Exchange Standard (CDES)](https://cdes.acidni.net).

## Overview

This repository contains canonical reference data used by CDES-compliant applications:

- **Terpene Library** - Standardized terpene identifiers with CAS numbers, PubChem IDs, effects, and aromas
- **Cannabinoid Library** - (Coming soon) Standard cannabinoid identifiers
- **Strain Database** - (Coming soon) Reference strain information

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

All reference data in this repository is released into the **public domain** under CC0 1.0 Universal.
You can copy, modify, distribute and use the data for any purpose without attribution.

## Terpene Library

**File:** `terpenes/terpene-library.json`

Contains 24+ cannabis terpenes with:

| Field | Description |
|-------|-------------|
| `id` | Standardized identifier (e.g., `terp-myrcene`) |
| `name` | Common name |
| `casNumber` | Chemical Abstracts Service registry number |
| `pubchemId` | PubChem compound ID |
| `molecularFormula` | Chemical formula |
| `category` | Classification (monoterpene, sesquiterpene) |
| `aroma` | Array of aroma descriptors |
| `effects` | Array of effects with evidence levels |
| `boilingPoint` | Celsius and Fahrenheit |

### Usage Example

```python
import json

with open('terpenes/terpene-library.json') as f:
    data = json.load(f)

for terpene in data['terpenes']:
    print(f"{terpene['name']}: CAS {terpene['casNumber']}")
```

### Featured Terpenes

| Name | ID | CAS Number | Category |
|------|-----|------------|----------|
| Myrcene | terp-myrcene | 123-35-3 | Monoterpene |
| Limonene | terp-limonene | 5989-27-5 | Monoterpene |
| Beta-Caryophyllene | terp-beta-caryophyllene | 87-44-5 | Sesquiterpene |
| Linalool | terp-linalool | 78-70-6 | Monoterpene |
| Alpha-Pinene | terp-alpha-pinene | 80-56-8 | Monoterpene |
| Terpinolene | terp-terpinolene | 586-62-9 | Monoterpene |
| Humulene | terp-humulene | 6753-98-6 | Sesquiterpene |
| Ocimene | terp-ocimene | 13877-91-3 | Monoterpene |

## Installation

The data can be consumed directly from GitHub:

```bash
# Download the terpene library
curl -O https://raw.githubusercontent.com/Acidni-LLC/cdes-reference-data/main/terpenes/terpene-library.json
```

Or install via the CDES Python SDK:

```bash
pip install cdes
```

```python
from cdes import get_terpene_library

terpenes = get_terpene_library()
```

## Contributing

We welcome contributions! Please see our [contribution guidelines](CONTRIBUTING.md).

### Adding New Terpenes

1. Fork this repository
2. Add the terpene to `terpenes/terpene-library.json`
3. Include all required fields (id, name, casNumber, pubchemId)
4. Submit a pull request with scientific references

## Related Repositories

- [cdes-spec](https://github.com/Acidni-LLC/cdes-spec) - JSON Schema specifications
- [cdes-sdk-python](https://github.com/Acidni-LLC/cdes-sdk-python) - Python validation library
- [cdes-website](https://github.com/Acidni-LLC/cdes-website) - Documentation website

## Maintained By

[Acidni LLC](https://acidni.com) - Cannabis Data Analytics & AI Solutions
