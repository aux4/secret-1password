Get specific fields from a 1Password secret. The *ref* must be a valid `secret://1password/<vault>/<item>` reference. The *fields* parameter is a comma-separated list of field names to retrieve.

```bash
> aux4 secret 1password get --ref "secret://1password/Personal/GitHub" --fields "username,password"
```
```json
{"username": "john", "password": "abc123"}
```

Include the one-time password:

```bash
> aux4 secret 1password get --ref "secret://1password/Personal/GitHub" --fields "username,password" --otp true
```
```json
{"username": "john", "password": "abc123", "otp": "123456"}
```

Get a single field:

```bash
> aux4 secret 1password get --ref "secret://1password/Work/AWS" --fields "password"
```
```json
{"password": "sk-abc123"}
```
