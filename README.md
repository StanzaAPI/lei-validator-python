# Global LEI & Corporate Tax ID Validator API — Python SDK

[![PyPI version](https://img.shields.io/pypi/v/stanzaapi-lei-validator.svg)](https://pypi.org/project/stanzaapi-lei-validator/)
[![Python Versions](https://img.shields.io/pypi/pyversions/stanzaapi-lei-validator.svg)](https://pypi.org/project/stanzaapi-lei-validator/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stanza API](https://img.shields.io/badge/Powered%20by-Stanza-blue)](https://stanzaapi.com)

> Sub-5ms validation for ISO 17442 LEI (MOD 97-10), US EIN, Australian ABN/ACN (MOD-89), and UK CRN.

Official, zero-dependency Python 3.8+ client library for **Global LEI & Corporate Tax ID Validator API**, built on the [Stanza Micro-API Network](https://stanzaapi.com). Intended for enterprise data pipelines, backend verification, and sub-5ms edge compute.

* 🌐 **Live Web Playground:** [Test your inputs online](https://stanzaapi.com/tools/lei-validator)
* 📚 **API Documentation:** [View full schema on Stanza](https://stanzaapi.com/tools/lei-validator)
* ⚡ **Platform Overview:** [Explore the Stanza Developer Network](https://stanzaapi.com)

---

## 📦 Installation

```bash
pip install stanzaapi-lei-validator
```

---

## 🚀 Quickstart

```python
import os
from stanzaapi_lei_validator import LeiValidatorClient

# Initialize client (api_key optional for local evaluation)
client = LeiValidatorClient(
    api_key=os.getenv("STANZA_API_KEY")
)

# Execute deterministic validation
response = client.validate("5493006MHB84DD0ZWV18")

if response.get("success"):
    print("Verification Success:", response["data"])
else:
    print("Validation Error:", response.get("error"), response.get("code"))
```

---

## 📄 Example Response

```json
{
  "success": true,
  "data": {
    "valid": true,
    "lei": "5493006MHB84DD0ZWV18",
    "format": "ISO_17442",
    "checksum_valid": true
  }
}
```

---

## ⚙️ Client Options

| Parameter | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `api_key` | `Optional[str]` | `os.getenv("STANZA_API_KEY")` | Your [Stanza API Key](https://stanzaapi.com). Required for production quotas. |
| `base_url` | `Optional[str]` | `"https://stanzaapi.com"` | API endpoint base URL. Custom endpoints supported for VPC enclaves. |
| `timeout` | `int` | `15` | Request timeout in seconds. |


---

## 🔗 Useful Links

* [Global LEI & Corporate Tax ID Validator API Interactive Sandbox](https://stanzaapi.com/tools/lei-validator)
* [Stanza Developer Directory](https://stanzaapi.com)
* [Source Code & Issue Tracker](https://github.com/stanzaapi/lei-validator-python)

## 📄 License

MIT © Stanza — Powered by [Stanza](https://stanzaapi.com).
