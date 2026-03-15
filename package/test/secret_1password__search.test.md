# aux4 secret 1password search

## search secrets

### should return matching secret references

```execute
aux4 secret 1password search --query test
```

```expect
secret://1password/
```

## search secrets in a vault

### should return matching secret references from the vault

```execute
aux4 secret 1password search --query test --vault Personal
```

```expect
secret://1password/Personal/
```

## search secrets with fields

### should return matching secret references with field names

```execute
aux4 secret 1password search --query test --withFields true
```

```expect
secret://1password/
```

```expect
fields:
```
