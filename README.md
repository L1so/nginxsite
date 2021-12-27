# nginxsite
Easy enabling/disabling site on NginX, using Bash Script. This is an attempt to replicate apache `a2ensite` & `a2dissite` feature.

## Feature
- Autocomplete.
- Interactive menu.
- Easy [un]install script.
- Beginner friendly.

### Installation
Download your copies of repository, then execute `install` script located on main directory. Note that this required root user.
```bash
wget -O nginxsite.zip https://github.com/L1so/nginxsite/archive/refs/heads/main.zip
unzip -qq nginxsite.zip && rm nginxsite.zip
cd nginxsite-main && sudo ./install
```
Or if you prefer `clone`.
```bash
git clone https://github.com/L1so/nginxsite.git
cd nginxsite && sudo ./install
```
By installing, following things will happen.
- Creating directory `/etc/nginx/sites-{available,enabled}` if not exist
- Copying main script to `/usr/local/bin/`

## Removing
Just execute `uninstall` script located on this repository.
```bash
sudo ./uninstall
```
It will remove all trace of `nginxsite`.
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
### Create NginX server block
You can now create NginX server block (equivalent to apaches virtualhost) seamlessly.
```bash
sudo ngxcreate (YOUR SITE NAME)
```
Running `ngxcreate` without any argument will give you a prompt to enter desired site name, if you don't include TLD, the script will give you `.com` domain.
```bash
$ sudo ngxcreate
Please Enter a Domain Name (default TLD is .com):
examplesite
```
Will save a new file named `/etc/nginx/sites-available/examplesite.com`
