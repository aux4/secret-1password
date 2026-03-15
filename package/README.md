# aux4 secret 1password

1Password secret manager for aux4. Wraps the 1Password CLI (`op`) to manage secrets using `secret://` references. Secrets are resolved at execution time so credentials never appear in configuration files.

## Installation

```bash
aux4 aux4 pkger install aux4/secret-1password
```

## Prerequisites

- [1Password CLI](https://developer.1password.com/docs/cli/) (`op`) installed and authenticated (auto-installed via `brew` on macOS)
- `jq` installed

## Quick Start

```bash
aux4 secret 1password list --vault Personal
aux4 secret 1password get --ref "Personal/GitHub" --fields "username,password"
```

## Reference Format

The `--ref` parameter uses a simple `<vault>/<item>` path:

```text
Personal/GitHub
Work/AWS
```

When used inline by consuming packages (e.g., `aux4/browser`), the full `secret://` URI includes the provider prefix:

```text
secret://1password/<vault>/<item>/<field>
```

## Commands

### List

List secrets as `secret://` references. Optionally filter by vault and include field names.

```bash
aux4 secret 1password list
```

```text
secret://1password/Personal/GitHub
secret://1password/Personal/Gmail
secret://1password/Work/AWS
```

Filter by vault:

```bash
aux4 secret 1password list --vault Personal
```

```text
secret://1password/Personal/GitHub
secret://1password/Personal/Gmail
```

Include field names:

```bash
aux4 secret 1password list --vault Personal --withFields true
```

```text
secret://1password/Personal/GitHub
  fields: username, password

secret://1password/Personal/Gmail
  fields: username, password
```

### Search

Search for secrets by name. The query is matched case-insensitively against item titles.

```bash
aux4 secret 1password search --query github
```

```text
secret://1password/Personal/GitHub
```

Search within a specific vault with field names:

```bash
aux4 secret 1password search --query github --vault Personal --withFields true
```

```text
secret://1password/Personal/GitHub
  fields: username, password
```

### Get

Get specific fields from a secret as a JSON object.

```bash
aux4 secret 1password get --ref "Personal/GitHub" --fields "username,password"
```

```json
{
  "username": "john",
  "password": "abc123"
}
```

Include the one-time password:

```bash
aux4 secret 1password get --ref "Personal/GitHub" --fields "username,password" --otp true
```

```json
{
  "username": "john",
  "password": "abc123",
  "otp": "123456"
}
```

### Create

Create a new secret in 1Password. Fields are provided as comma-separated `key=value` pairs.

```bash
aux4 secret 1password create --vault Personal --item GitHub --fields "username=john,password=abc123"
```

```text
secret://1password/Personal/GitHub
```

Specify a category (defaults to `Login`):

```bash
aux4 secret 1password create --vault Personal --item "API Key" --fields "credential=sk-abc123" --category "API Credential"
```

```text
secret://1password/Personal/API Key
```

### Set

Update a single field of an existing secret.

```bash
aux4 secret 1password set --ref "Personal/GitHub" --field password --value newpass123
```

```text
Personal/GitHub updated
```
