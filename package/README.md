# aux4 secret 1password

1Password secret manager for aux4. Wraps the [1Password CLI](https://developer.1password.com/docs/cli/) (`op`) to manage secrets using `secret://` references.

## Prerequisites

- [1Password CLI](https://developer.1password.com/docs/cli/) (`op`) installed and authenticated
- `jq` installed

## Reference Format

```
secret://1password/<vault>/<item>
secret://1password/<vault>/<item>/<field>
```

## Usage

### List secrets

List all secrets across all vaults:

```bash
> aux4 secret 1password list
```
```
secret://1password/Personal/GitHub
secret://1password/Personal/Gmail
secret://1password/Work/AWS
```

List secrets from a specific vault:

```bash
> aux4 secret 1password list --vault Personal
```
```
secret://1password/Personal/GitHub
secret://1password/Personal/Gmail
```

List secrets with field names:

```bash
> aux4 secret 1password list --vault Personal --withFields true
```
```
secret://1password/Personal/GitHub
  fields: username, password

secret://1password/Personal/Gmail
  fields: username, password
```

### Search secrets

Search for secrets by name:

```bash
> aux4 secret 1password search --query github
```
```
secret://1password/Personal/GitHub
```

Search with field names:

```bash
> aux4 secret 1password search --query github --withFields true
```
```
secret://1password/Personal/GitHub
  fields: username, password
```

### Get secret fields

Get specific fields from a secret:

```bash
> aux4 secret 1password get --ref "secret://1password/Personal/GitHub" --fields "username,password"
```
```json
{"username": "john", "password": "abc123"}
```

Get fields with one-time password:

```bash
> aux4 secret 1password get --ref "secret://1password/Personal/GitHub" --fields "username,password" --otp true
```
```json
{"username": "john", "password": "abc123", "otp": "123456"}
```

### Create a secret

```bash
> aux4 secret 1password create --vault Personal --item GitHub --fields "username=john,password=abc123"
```
```
secret://1password/Personal/GitHub
```

Create with a specific category:

```bash
> aux4 secret 1password create --vault Personal --item "API Key" --fields "credential=sk-abc123" --category "API Credential"
```
```
secret://1password/Personal/API Key
```

### Update a secret field

```bash
> aux4 secret 1password set --ref "secret://1password/Personal/GitHub" --field password --value newpass123
```
```
secret://1password/Personal/GitHub updated
```
