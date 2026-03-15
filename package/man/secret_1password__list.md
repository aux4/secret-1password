#### Description

List secrets from 1Password as `secret://` references.

- **Vault filtering** — use `--vault` to restrict results to a single vault. If omitted, secrets from all vaults are listed.
- **Field inspection** — use `--withFields true` to display the field names available on each item.

#### Usage

```bash
aux4 secret 1password list [--vault <name>] [--withFields <true|false>]
```

--vault        The vault to list secrets from (default: all vaults)
--withFields   Include field names for each item (default: false)

#### Example

```bash
aux4 secret 1password list --vault Personal
```

```text
secret://1password/Personal/GitHub
secret://1password/Personal/Gmail
```

With field names:

```bash
aux4 secret 1password list --vault Personal --withFields true
```

```text
secret://1password/Personal/GitHub
  fields: username, password

secret://1password/Personal/Gmail
  fields: username, password
```
