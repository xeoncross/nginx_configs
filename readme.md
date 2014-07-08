# Nginx Sample Configs

These are sample configs that can be included from within nginx configs or used as a reference for common tasks.

These files are organised by block level

	http {
		server {
			location {
				# ...
			}
		}
	}

# Usage

Simply checkout the latest copy using git

	sudo git clone https://github.com/Xeoncross/nginx_configs /etc/nginx/nginx_configs

Then include the files you need from inside your `/etc/nginx/sites-available/[file]` configs

	include /etc/nginx/nginx_configs/gzip.conf

	server {
		listen 8000;
		server_name example.com *.example.com;
		root /var/www/example.com/public;

		include /etc/nginx/nginx_configs/server/base.conf
		include /etc/nginx/nginx_configs/server/cache.conf
		include /etc/nginx/nginx_configs/server/log.conf
		include /etc/nginx/nginx_configs/server/php.conf

		...
	}

## Quick links:

- http://wiki.nginx.org/HttpCoreModule
- http://wiki.nginx.org/HttpCoreModule#Variables
- https://github.com/Xeoncross/simpleserversetup
- [Varying-Vagrant-Vagrants](https://github.com/Varying-Vagrant-Vagrants/VVV/tree/master/config/nginx-config)