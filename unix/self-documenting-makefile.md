# Self Documenting Makefile
Type `make` and return back a list of available commands with descriptions

1. Add comments right after the target name
```
install: ## Install npm dependencies for the api, admin, and frontend apps
	@echo "Installing Node dependencies"
	@npm install

install-dev: install ## Install dependencies and prepared development configuration
	@./node_modules/.bin/selenium-standalone install
	@cp -n ./config/development.js-dist ./config/development.js | true

run-frontend-dev: webpack.PID ## Run the frontend and admin apps in dev (using webpack-dev-server)
```

2. Add a `help` target in your Makefile
```
.PHONY: help

help:
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'
```

3. Make this `help` target the default target
```
.DEFAULT_GOAL := help
```

## Tips
* If you copy this code snippet to a makefile, make sure your text editor converts indentation to tabs and not spaces.
* Adjust the width of the first column by changing the 30 value in the printf pattern to something larger or smaller.
* Remove the | sort to have targets ordered the way they appear in the makefile instead of alphabetically.

[source](http://marmelab.com/blog/2016/02/29/auto-documented-makefile.html)
