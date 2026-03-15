#### Description

Update a single field of an existing 1Password secret. The `--ref` must be a valid `secret://1password/<vault>/<item>` reference.

#### Usage

```bash
aux4 secret 1password set --ref <secret-ref> --field <name> --value <new-value>
```

--ref      The secret reference, e.g. `secret://1password/Personal/GitHub` (required)
--field    The field name to update (required)
--value    The new value (required)

#### Example

```bash
aux4 secret 1password set --ref "secret://1password/Personal/GitHub" --field password --value newpass123
```

```text
secret://1password/Personal/GitHub updated
```
