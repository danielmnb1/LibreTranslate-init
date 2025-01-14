# LibreTranslate-init

Shell scripts to install [LibreTranslate](https://libretranslate.com)

Uses WSGI with [Gunicorn and Nginx](https://www.digitalocean.com/community/tutorials/how-to-serve-flask-applications-with-gunicorn-and-nginx-on-ubuntu-18-04).

## Install

```
# Add libretranslate user
useradd Libretranslate
mkdir /home/Libretranslate
chown libretranslate:libretranslate /home/Libretranslate
usermod -aG sudo libretranslate
passwd -d libretranslate
su libretranslate

# Download LibreTranslate-init
git clone https://github.com/danielmnb1/LibreTranslate-init.git ~/LibreTranslate-init

# Download dependencies and run LibreTranslate on port 5000
~/LibreTranslate-init/setup.sh

# Set server_name to your domain name in ~/LibreTranslate-init/nginx

# Run LibreTranslate WSGI with nginx and systemd
~/LibreTranslate-init/run.sh

# Check LibreTranslate status
sudo systemctl status libretranslate

# Enable https
~/LibreTranslate-init/get-cert.sh

```

#### Tutorials
- [Video tutorial](https://www.youtube.com/watch?v=mwacU-yqJwc)
- [Video tutorial 2](https://www.youtube.com/watch?v=SJ8lNcn4cjE)

#### Configuration
1. Find the setting you would like to change in the [LibreTranslate settings](https://github.com/LibreTranslate/LibreTranslate#arguments)
2. Add the setting to the environment of your libretranslate.service SystemD file

#### [Demo](https://translate.argosopentech.com)
Hosted on [DigitalOcean](https://m.do.co/c/a1af57be6e3f)
