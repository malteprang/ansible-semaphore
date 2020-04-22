# Purpose
You can run Ansible Semaphore out of the box with docker-compose either with a selfsigned certificat or a letsencrypt certificate.

# How to use ansible-semaphore

## prerequisites
You need a running docker-compose environment

## change the config to your needs
You need to change the domain example.com in all /conf/nginx* and docker-compose* files.
You also have to set a stronger MYSQL_ROOT_PASSWORD in the docker-compose* files.

## run ansible-semaphore without letsencrypt
`docker-compose up -d`

## run ansible-semaphore with letsencrypt
`docker-compose -f docker-compose_letsencrypt.yml up -d`

## open web interface
open `https://localhost/` or `https://example.com` in your webbrowser.
the default credentials are
`User: admin`
`User: admin`

You can set new credentials in your instance, the default credentials are only set in a fresh data directory and won't get overwritten.

# where is my data stored?
The database and some other files for persistent storage are located in the 'data' directory which is created at the first run.


