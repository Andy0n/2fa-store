# 2fa-store
Tool to securely store and view 2fa tokens. Like [password-store](https://www.passwordstore.org/) but for 2fa.

## Usage
### Initialize 2fa store:

```bash
2fa init <key>
```

Key should be the id to identify the gpg, that should be used.

### List of all available services

```bash
2fa list
```

```
2fa Store:
└── Service1
└── Service2
```

If no command is given:

```bash
2fa
```

fzf will open with all available services and after choosing one, the 2fa code 
will be shown.


### Adding a service:

```bash
2fa store <service>
```

Then enter the secret and it gets automatically encrypted and saved. 
Secret is either the Base32 String, or the whole otpauth://totp/.... string

### Retrieving a 2fa token:

```bash
2fa get <service>
```

Results in a output like:

```
123456 (21)
```

The countdown ticks automatically down and if reaches 0 generates a new token.

### Remove service

```bash
2fa remove <service>
```

Deletes the encrypted file containing the key.

### Full git integration

Initialize a git repository using

```bash
2fa git init
```

After that 2fa-store creates a commit every time the 2fa store is manipulated.

If you want to push to a remote repository:

```bash
2fa git remote add origin example.com:repo
2fa git push
```

## TODO
* Option to not show the token, but paste it into the clipboard.
