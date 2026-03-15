#### Description

Update a single field of an existing 1Password secret. The `--ref` is the vault and item path (e.g., `Personal/GitHub`).

#### Usage

```bash
aux4 secret 1password set --ref <vault/item> --field <name> --value <new-value>
```

--ref      The secret reference, e.g. `Personal/GitHub` (required)
--field    The field name to update (required)
--value    The new value (required)

#### Example

```bash
aux4 secret 1password set --ref "Personal/GitHub" --field password --value newpass123
```

```text
Personal/GitHub updated
```
