# Pass

A tiny password manager in shell using 4096-bit RSA

# Limits

Passwords must have a length between 8 and 384 characters (RSA limitation)

# Install

```sh
mkdir -pv ~/.local/bin
wget https://raw.githubusercontent.com/ocku/pass/main/pass -qO ~/.local/bin/pass
```

```
Usage:
  pass [ls|list]
    list all entries in the vault

  pass [s|set] {name}
    ask for a password and save it as {name}

  pass [g|get] {name}
    get the password for {name} and print it to stdout

  pass [n|gen] {name} {length?}
    generate a password with length {length, defaults to 16},
      save it as {name} and print it to stdout

  pass [rm|remove] {name}
    remove the entry for {name} in the vault

  pass [x|export] {outfile}
    export vault to {outfile, defaults to vault.tar.gz}
```
