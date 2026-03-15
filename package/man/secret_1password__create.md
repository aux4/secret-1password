#### Description

Create a new secret in 1Password. Fields are provided as comma-separated `key=value` pairs. Returns the `secret://` reference for the newly created item.

- **Category** — defaults to `Login`. Use `--category` to specify a different 1Password item category.

#### Usage

```bash
aux4 secret 1password create --vault <name> --item <title> --fields <key=val,...> [--category <type>]
```

--vault      The vault to create the secret in (required)
--item       The item title (required)
--fields     Comma-separated field assignments, e.g. `username=john,password=abc123` (required)
--category   The item category (default: Login)

#### Example

```bash
aux4 secret 1password create --vault Personal --item GitHub --fields "username=john,password=abc123"
```

```text
secret://1password/Personal/GitHub
```

With a custom category:

```bash
aux4 secret 1password create --vault Personal --item "API Key" --fields "credential=sk-abc123" --category "API Credential"
```

```text
secret://1password/Personal/API Key
```
