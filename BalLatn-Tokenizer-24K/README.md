---
language:
  - bal
license: mit
library_name: transformers
tags:
  - balochi
  - tokenizer
  - latin-script
  - bpe
  - low-resource-nlp
---

# BalLatn-Tokenizer-24K (Balóchi Látini Syáhag BPE Tokenizer)

`BalLatn-Tokenizer-24K` is a 24,000-token Byte-Level BPE tokenizer trained specifically for **Pure Balochi Latin Script** (*Balóchi Látini Syáhag*, `ISO 639-3: bal`, `Script: Latn`) on cleaned literary prose (`Dástán`), poetry (`Shaér`), and lexical definitions (`Námgál`, `Rangál`) from [Labzánk](https://labzank.com/) and [Náganj](https://labzank.com/naganj.php).

## Key Features
- **Unicode NFC Normalization Only:** Strictly preserves Balochi accented vowels (`á, é, ó, Á, É, Ó`) and digraphs (`ch, dh, gh, kh, sh, th, zh`).
- **100% Pure Balochi Latin:** Zero Arabic script characters (`[\u0600-\u06FF]`) and zero English gloss contamination.
- **High Fertility Efficiency:** ~1.15–1.30 tokens per Balochi word (nearly 3× more efficient than default multilingual tokenizers).

## Quick Usage
```python
from transformers import AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("shah-bakhsh/BalLatn-Tokenizer-24K")
ids = tokenizer.encode("Maná dér ent ke é nemdi nebeshtah kotag.")
print(tokenizer.convert_ids_to_tokens(ids))
```
