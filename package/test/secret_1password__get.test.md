# aux4 secret 1password get

## get secret fields

### should return field values as JSON

```execute
aux4 secret 1password get --ref "secret://1password/Personal/Test" --fields "username,password"
```

```expect
"username":
```

```expect
"password":
```

## get secret fields with otp

### should return field values with otp

```execute
aux4 secret 1password get --ref "secret://1password/Personal/Test" --fields "username,password" --otp true
```

```expect
"otp":
```
