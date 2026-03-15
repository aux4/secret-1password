#### Description

Get specific fields from a 1Password secret as a JSON object. The `--ref` is the vault and item path (e.g., `Personal/GitHub`) and `--fields` is a comma-separated list of field names to retrieve.

- **Multiple fields** — returns a JSON object with each requested field as a key.
- **OTP support** — use `--otp true` to include the one-time password in the response.

#### Usage

```bash
aux4 secret 1password get --ref <vault/item> --fields <field1,field2,...> [--otp <true|false>]
```

--ref      The secret reference, e.g. `Personal/GitHub` (required)
--fields   Comma-separated field names to retrieve (required)
--otp      Include one-time password (default: false)

#### Example

```bash
aux4 secret 1password get --ref "Personal/GitHub" --fields "username,password"
```

```json
{
  "username": "john",
  "password": "abc123"
}
```

With one-time password:

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
