#### Description

Search for secrets in 1Password by name. The query is matched case-insensitively against item titles.

- **Vault filtering** — use `--vault` to restrict the search to a single vault.
- **Field inspection** — use `--withFields true` to display the field names available on each matching item.

#### Usage

```bash
aux4 secret 1password search --query <text> [--vault <name>] [--withFields <true|false>]
```

--query        The search query (required)
--vault        The vault to search in (default: all vaults)
--withFields   Include field names for each item (default: false)

#### Example

```bash
aux4 secret 1password search --query github
```

```text
secret://1password/Personal/GitHub
```

Search within a vault with field names:

```bash
aux4 secret 1password search --query api --vault Work --withFields true
```

```text
secret://1password/Work/AWS API
  fields: access key, secret key
```
