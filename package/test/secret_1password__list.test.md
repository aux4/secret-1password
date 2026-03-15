# aux4 secret 1password list

## list all secrets

### should return secret references

```execute
aux4 secret 1password list
```

```expect
secret://1password/
```

## list secrets from a vault

### should return secret references from the vault

```execute
aux4 secret 1password list --vault Personal
```

```expect
secret://1password/Personal/
```

## list secrets with fields

### should return secret references with field names

```execute
aux4 secret 1password list --vault Personal --withFields true
```

```expect
secret://1password/Personal/
```

```expect
fields:
```
