# aux4 secret 1password get

## get secret fields

### should return field values as JSON

```execute
aux4 secret 1password get --ref "Fake/Fake Credentials" --fields "username,password"
```

```expect
"username":
```

```expect
"password":
```

## get single field

### should return single field value as JSON

```execute
aux4 secret 1password get --ref "Fake/Fake Credentials" --fields "username"
```

```expect
"username":
```
