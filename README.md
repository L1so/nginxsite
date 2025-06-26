# nginxsite - a2ensite replacement written in Bash
Easy enabling/disabling site on NginX, using Bash Script. This is an attempt to replicate apache `a2ensite` & `a2dissite` feature.

Tested in official upstream package of nginx and Ubuntu derivative package.

![](https://i.ibb.co/NpmMth4/Peek-2022-07-23-21-04.gif)

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
Or if you prefer `git clone`.
```bash
git clone https://github.com/L1so/nginxsite.git
cd nginxsite && sudo ./install
```
By installing, following things will happen.
- Creating directory `/etc/nginx/sites-{available,enabled}` if not exist
- [Modify nginx config to include `/etc/nginx/sites-available` if not already](https://stackoverflow.com/questions/17413526/nginx-missing-sites-available-directory/17415606#17415606)
- Copying main script to `/usr/local/bin/`

## Removing
Just execute `uninstall` script located on this repository.
```bash
sudo ./uninstall
```
It will remove all trace of `nginxsite`.
## Usage
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
### Create server block
To create a site, replace `(YOUR DOMAIN)` with your actual domain.
```bash
sudo ngxcreate (YOUR DOMAIN)
```
Running `ngxcreate` without any argument will give you a prompt to enter desired site name, if you don't include tld, the script will give you `.com` domain.
```bash
$ sudo ngxcreate
Please Enter a Domain Name (default TLD is .com):
examplesite
```
Will save a new file named `/etc/nginx/sites-available/examplesite.com`

### Delete server block
To delete a site, replace `(YOUR DOMAIN)` with your actual site domain.
```bash
sudo ngxdelete (YOUR DOMAIN)
```
Example given below.
```bash
root@mutiny:~# ngxdelete bar.co 
Removing --> /etc/nginx/sites-available/bar.co
```
### List site
To list site, simply type `ngxlist` (or `ngxlist -e` to show enabled sites).

![s](https://i.ibb.co/7nWN2WT/Peek-2022-07-24-20-40.gif)