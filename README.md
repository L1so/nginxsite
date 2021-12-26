# nginxsite
Easy enabling/disabling site on NginX, using Bash Script.

## Feature
- Autocomplete.
- Interactive menu.
- Easy [un]install script.
- Easy to use.

### Installation
To install, execute `install` script located on main directory. Note that this required root user.
```bash
sudo ./install
```
By installing, following things will happen.
- Adding new entries on `~/.bashrc`
- Creating directory `/etc/nginx/sites-{available,enabled}` if not exist
- Copying main script to `/usr/local/bin/`

## Removing
Just execute `uninstall` script located on this repository.
```bash
sudo ./uninstall
```
It will remove all trace of `nginxsite`, this include entries on `~/.bash.rc` and `/usr/local/bin`.

## General usage
This section will show you general use of this snippet.
### Enabling
To activate a site, replace `(YOUR SITE)` with your actual site domain (located in `/etc/nginx/sites-available/`).
```bash
sudo ngxensite (YOUR SITE)
```
### Disabling
To deactivate a site, replace `(YOUR SITE)` with your actual site domain (located in `/etc/nginx/sites-available/`).
```bash
sudo ngxdissite (YOUR SITE)
```
