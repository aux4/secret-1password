Create a new secret in 1Password. The *fields* parameter accepts comma-separated `key=value` pairs.

```bash
> aux4 secret 1password create --vault Personal --item GitHub --fields "username=john,password=abc123"
```
```
secret://1password/Personal/GitHub
```

Specify a category (defaults to `Login`):

```bash
> aux4 secret 1password create --vault Personal --item "API Key" --fields "credential=sk-abc123" --category "API Credential"
```
```
secret://1password/Personal/API Key
```
