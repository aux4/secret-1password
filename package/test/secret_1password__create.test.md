# aux4 secret 1password create

## create a secret

### should return the secret reference

```execute
aux4 secret 1password create --vault Personal --item "Test Item $(date +%s)" --fields "username=testuser,password=testpass"
```

```expect
secret://1password/Personal/Test Item
```
