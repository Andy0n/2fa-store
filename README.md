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

### Adding a service:

```bash
2fa store <service>
```

Then enter the secret and it gets automatically encrypted and saved.

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

## TODO
* Parse Base32 and oauth://.. strings.
* Include git interface.
* Option to not show the token, but paste it into the clipboard.
