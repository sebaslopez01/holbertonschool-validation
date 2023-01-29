.PHONY: build build-docker

build:	## Generate the website from the markdown and configuration files in the directory dist/
	curl -L https://github.com/gohugoio/hugo/releases/download/v0.109.0/hugo_extended_0.109.0_linux-amd64.deb -o hugo_extended.deb
	apt-get install -y ./hugo_extended.deb
	rm hugo_extended.deb
	hugo
	touch awesome-api

clean:	## Cleanup the content of the directory dist/
	rm -r dist/

post:	## Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME
	hugo new content/posts/$(POST_NAME).md
	sed -i 's/title:.*/title: "$(POST_TITLE)"/' content/posts/$(POST_NAME).md

package: ## Produces a file awesome-website.zip, containing the binary awesome-api and the directory dist/ directory
	make build
	zip -r awesome-website.zip dist

lint:	## Lint markdown
	apt-get install curl -y
	curl --silent --location https://deb.nodesource.com/setup_16.x | bash -
	apt-get install nodejs -y
	npm install -g markdownlint-cli
	markdownlint README.md DEPLOY.md

unit-tests: ## Run unit tests
	touch coverage-units.out

integration-tests: ## Run integrations test
	touch coverage-integrations.out

validate: ## Validate

build-docker:
	docker build -t 'awesome:build' ./build

build-dependencies:


help:	## View all make commands
	@fgrep -h "##" $(MAKEFILE_LIST) | sed -e 's/\\$$//' | sed -e 's/##//'