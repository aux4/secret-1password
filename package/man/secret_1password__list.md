List secrets from 1Password as `secret://` references.

If *vault* is not provided, secrets from all vaults are listed.

```bash
> aux4 secret 1password list
```
```
secret://1password/Personal/GitHub
secret://1password/Personal/Gmail
secret://1password/Work/AWS
```

Filter by vault:

```bash
> aux4 secret 1password list --vault Personal
```
```
secret://1password/Personal/GitHub
secret://1password/Personal/Gmail
```

Include field names for each item:

```bash
> aux4 secret 1password list --vault Personal --withFields true
```
```
secret://1password/Personal/GitHub
  fields: username, password

secret://1password/Personal/Gmail
  fields: username, password
```
