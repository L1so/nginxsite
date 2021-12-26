# nginxsite
Easy to use shell script to enabling/disabling site in NginX

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
