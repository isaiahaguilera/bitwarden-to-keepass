# bitwarden-to-keepass
Export (most of) your Bitwarden items into KeePass database.

## How it works?
It uses official [bitwarden-cli](https://help.bitwarden.com/article/cli/) client to export your items from Bitwarden vault and move them into your KeePass database - that includes logins (with TOTP seeds, URIs, custom fields, attachments, notes) and secure notes.

## Install
- Clone this repository
- Run
```
make build
```

## Run/usage
- First you will need to **create new (empty) KeePass database** (tested with [KeePassXC](https://github.com/keepassxreboot/keepassxc) but it will probably work with others)
- Go into the virtual environment
```
source .venv/bin/activate
```
- [Download](https://help.bitwarden.com/article/cli/#download--install) official bitwarden-cli and do `bw login` (you need `BW_SESSION` for export to work).
- Run
```
python3 bitwarden-to-keepass.py --bw-session BW_SESSION --database-path DATABASE_PATH --database-password DATABASE_PASSWORD [--database-keyfile DATABASE_KEYFILE] [--bw-path BW_PATH]

python3 bitwarden-to-keepass.py --bw-session s8xZ5FE22b5LN6OrkgH3QZj3CMv/bBQqQgrXi1lQE+8ZA5LWGCwP+gHP9g4oF+pyhHRlYB6+aYOwJoS69lksOQ== --database-path BitwardenBackup.kdbx --database-password '' --bw-path /Users/isaiah.aguilera/.nvm/versions/node/v12.18.4/bin/bw
```
