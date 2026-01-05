# Contributing to CDES Reference Data

Thank you for contributing to the Cannabis Data Exchange Standard reference data!

## Overview

This repository contains canonical reference data for the cannabis industry:

- **Terpene Library** - Scientific data on cannabis terpenes
- **Cannabinoid Registry** - Cannabinoid compound data
- **Strain Registry** - Cannabis strain definitions
- **Lab Directory** - Certified testing laboratories

## Scientific Accuracy Required

All data contributions **must be scientifically verifiable**:

### Required Sources

1. [PubChem](https://pubchem.ncbi.nlm.nih.gov/) - Primary source for chemical data
2. [CAS Registry](https://www.cas.org/) - For CAS number verification
3. Peer-reviewed scientific literature

### Required Fields (Terpenes)

| Field | Description | Source |
|-------|-------------|--------|
| `id` | CDES ID (terp-XXX) | Assigned |
| `name` | Common name | Scientific literature |
| `casNumber` | CAS Registry Number | CAS |
| `pubchemId` | PubChem Compound ID | PubChem |
| `molecularFormula` | Chemical formula | PubChem |
| `molecularWeight` | Molecular weight (g/mol) | PubChem |

## How to Contribute

### Adding a New Entry

1. **Research** - Gather data from at least 2 authoritative sources
2. **Validate CAS** - Verify the CAS number checksum
3. **Cross-reference** - Ensure PubChem data matches
4. **Open PR** - Include source URLs

### CAS Number Validation

The CAS number checksum must validate:

```
CAS: 123-45-6
Checksum: (3×1 + 2×2 + 1×3 + 6×4 + 5×5) % 10 = 6 ✓
```

### Example Entry

```json
{
  "id": "terp-001",
  "name": "Myrcene",
  "casNumber": "123-35-3",
  "pubchemId": 31253,
  "molecularFormula": "C10H16",
  "molecularWeight": 136.23,
  "category": "monoterpene",
  "sources": [
    {
      "type": "database",
      "name": "PubChem",
      "url": "https://pubchem.ncbi.nlm.nih.gov/compound/31253"
    }
  ]
}
```

## Correction Process

Found an error? Please:

1. Open an issue with the correct data
2. Include authoritative source
3. Reference the original entry ID

## Code of Conduct

- Accuracy over speed
- Cite your sources
- Be respectful in discussions

---

**License**: CC0 1.0 (Public Domain)
