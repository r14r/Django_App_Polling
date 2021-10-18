PREFIX_PKG := django_tutorial_polls

VERSION_BOOTSTRAP := 5.1.3

default:
	grep -E ':\s+#' Makefile

clearcache:	# Clear Cache
	python manage.py clearcache

run:		# Run Server
	python manage.py runserver 8000

migrate:		# Run Server
	python manage.py migrate

deploy:		# Deploy
	rm -rf dist $(PREFIX_PKG)*
	rm -rf polls.dist
	cd polls && python3 setup.py sdist
	mkdir polls.dist && mv polls/dist/* polls/$(PREFIX_PKG)* polls.dist


jquery_install:		# Install jQuery Library
	cd .. && yarn add jquery
	rm -rf polls/static/jquery
	mkdir  polls/static/jquery
	cp ../node_modules/jquery/dist/* polls/static/jquery

bootstrap_install:	# Install Bootstrap Library
	cd .. && yarn add bootstrap
	rm -rf  polls/static/bootstrap
	mkdir   polls/static/bootstrap
	cp -R ../node_modules/bootstrap/dist/* polls/static/bootstrap

bootstrap_download:	# Install Bootstrap from Source
	Remove-Item	-Force -Recurse		  install	
	New-Item    -ItemType  directory  install 
	Remove-Item	-Force -Recurse		  polls\static\vendor\bootstrap\bootstrap-$(VERSION_BOOTSTRAP)-dist
	Invoke-WebRequest -q https://github.com/twbs/bootstrap/releases/download/v$(VERSION_BOOTSTRAP)/bootstrap-$(VERSION_BOOTSTRAP)-dist.zip -Outfiler install\bootstrap.zip
	Expand-Archive install\bootstrap.zip -DestinationPath polls\static\vendor\bootstrap

	

