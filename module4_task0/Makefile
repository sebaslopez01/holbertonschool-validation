build:	## Generate the website from the markdown and configuration files in the directory dist/
	hugo
	touch awesome-api

clean:	## Cleanup the content of the directory dist/
	rm -r dist/

post:	## Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME
	hugo new content/posts/$(POST_NAME).md
	sed -i 's/title:.*/title: "$(POST_TITLE)"/' content/posts/$(POST_NAME).md

package: build ## Produces a file awesome-website.zip, containing the binary awesome-api and the directory dist/ directory
	zip -r awesome-website.zip dist

lint:	## Lint markdown
	markdownlint README.md DEPLOY.md

unit-tests: ## Run unit tests

integration-tests: ## Run integrations test

validate: ## Validate

help:	## View all make commands
	@fgrep -h "##" $(MAKEFILE_LIST) | sed -e 's/\\$$//' | sed -e 's/##//'