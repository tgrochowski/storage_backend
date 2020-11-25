.PHONY: _list

release_version := $(shell git rev-parse HEAD)

_list:
	@echo "Type make then a space then hit tab to see available commands"

start:
	- docker-compose up -d --remove-orphans

stop:
	- docker-compose down

destroy:
	- docker-compose rm -f

shell:
	docker exec -ti -u root storage-backend bash

composer_update:
	docker exec storage-backend /usr/bin/composer update --with-all-dependencies -working-dir=/var/www/html
	$(MAKE) clear_cache

composer_install:
	docker exec storage-backend /usr/bin/composer install --no-progress -no --prefer-dist --working-dir=/var/www/html
	$(MAKE) clear_cache

doctrine_migrate:
	docker exec storage-backend php /var/www/html/bin/console doc:dat:cr --if-not-exists
	docker exec storage-backend php /var/www/html/bin/console doc:mig:mig -n

clear_cache:
	docker exec storage-backend bash -c 'rm -rf /var/www/html/var/cache/*'
	$(MAKE) fix_permissions
	docker exec storage-backend php /var/www/html/bin/console cache:clear
	docker exec storage-backend php /var/www/html/bin/console cache:clear --env=prod
	docker exec storage-backend php /var/www/html/bin/console cache:warmup --env=prod
	$(MAKE) fix_permissions

fix_permissions:
	docker exec storage-backend chmod -R 777 /var/www/html/var/cache
	docker exec storage-backend chmod -R 777 /var/www/html/var/logs
	docker exec storage-backend bash -O extglob -c 'chown -R $(shell id -u):$(shell id -g) /var/www/html/!(var)'
