# Command Line Interface — DIGIKAM

**Upstream:** https://github.com/digiKam/digikam

## Anticloud CLI

```bash
# Install
pip install anticloud-digikam

# Run offline with PAX inference
anticloud-digikam --offline --pax-local

# Run with AIOSS logging
anticloud-digikam --aioss-log ./ledger.jsonl

# Single binary (after build)
./digikam --config config.yaml
```

## Options

| Flag | Description |
| --- | --- |
| `--offline` | Disable all network calls |
| `--pax-local` | Use local PAX inference at 127.0.0.1:11434 |
| `--aioss-log PATH` | Write AIOSS audit chain to PATH |
| `--encrypt` | Enable AES-256 at rest for output files |
| `--gpu` | Force GPU inference |
| `--cpu` | Force CPU inference |
| `--config PATH` | Load configuration from YAML file |
