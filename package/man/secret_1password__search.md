Search for secrets in 1Password by name. The *query* is matched case-insensitively against item titles.

```bash
> aux4 secret 1password search --query github
```
```
secret://1password/Personal/GitHub
```

Search within a specific vault:

```bash
> aux4 secret 1password search --query api --vault Work
```
```
secret://1password/Work/AWS API
secret://1password/Work/Stripe API
```

Include field names:

```bash
> aux4 secret 1password search --query github --withFields true
```
```
secret://1password/Personal/GitHub
  fields: username, password
```
