To use this repo you go

# Install vault

```
npm install -g vault
```

## Either: Clone the settings file using git

Useful if you plan to write back to the settings file.

```
git clone git@github.com:Praqma/vault-settings.git
vault --import vault-settings/praqma-vault.json
```


## Or: Use curl

Useful if you only wanna read the settings and have zero foot print on your local disk.

```
curl -Os https://raw.githubusercontent.com/Praqma/vault-settings/master/praqma-vault.json
vault --import praqma-vault.json && rm praqma-vault.json
```

# All you need now is s shared secret or key

Agree with your team what the passphrase is - maybe even for different for different security levels or contexts. Or consider using a `.ssh` key-pair that you destribute.

Install the passphrase locally like this:

```
vault -cp
passphrase: *************
```

(It will be stored, securely encrypted, in `~/.vault`).

Now get the password of the service (using `google` as an example) by typing:

```
vault google
```

Or install the distributed .ssh key and use it like this:

```
vault -k google
```

# Update the settings file

Use `vault --export <file-location>` to update the praqma-vault.json settings file locally, and then commit and push back to the repo.

**NOTE**:
That if you have installed the passphrase using `vault -cp` It's written in clear-text in your settings file whne you run `vault --export`. You probably wanna edit your file and remove that, before you commit and push! 
