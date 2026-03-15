# aux4 secret 1password set

## set a secret field

### should update the field and confirm

```execute
aux4 secret 1password set --ref "secret://1password/Personal/Test" --field password --value newpass123
```

```expect
secret://1password/Personal/Test updated
```
