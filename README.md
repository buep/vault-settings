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


## Or: use curl to have

Useful if you only wanna read the settings and have zero foot print on your local disk.

```
curl -Os https://raw.githubusercontent.com/Praqma/vault-settings/master/praqma-vault.json
vault --import praqma-vault.json && rm praqma-vault.json
```
