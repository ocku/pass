# Pass

A tiny password manager in shell using OpenSSL's RSA implementation.

## Limits

Passwords have a minimum length of 8 and a maximum of `key_size_bits / 8 - 11` bytes (501 with a 4096 bit key).

## Install

```sh
mkdir -pv ~/.local/bin
wget https://raw.githubusercontent.com/ocku/pass/main/pass -qO ~/.local/bin/pass
```

## Configuration

File structures, limits, and key size can all be modified by directly editing the globals at the top of the script. These are the defaults:

```sh
# directories
work_dir="$HOME/.local/share/pass"
keys_dir="$work_dir/keys"
data_dir="$work_dir/data"
# keys
rsa_keygen_bits=4096
pub_key="$keys_dir/pub.pem"
priv_key="$keys_dir/priv.pem"
# limits
max_pass_len=$((rsa_keygen_bits / 8 - 11))
min_pass_len=8
```

## Usage

```
  pass [ls|list]
    list all entries in the vault

  pass [s|set] {name}
    ask for a password and save it as {name}

  pass [g|get] {name}
    get the password for {name} and print it to stdout

  pass [n|gen] {name} {length?}
    generate a password with length {length, defaults to 24},
      save it as {name} and print it to stdout

  pass [rm|remove] {name}
    remove the entry for {name} in the vault

  pass [x|export] {outfile}
    export vault to {outfile, defaults to vault.tar.gz}
```
