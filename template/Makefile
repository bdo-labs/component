
#
# Settings
#

REPORTER?=spec


#
# Sources
#

SRC:=$(shell find -E . -regex '/^.*(html|js|json|css)$$/')
TESTS:=$(shell find . -name '*.test.js')


#
# Path
#

PATH=node_modules/bin:$(PATH)


#
# Targets
#

build: node_modules $(SRC)
	atomify
	@echo ""
	@echo "    {{basename}} was built!"
	@echo ""

node_modules: package.json
	npm install

test: build
	mocha --reporter $(REPORTER) --require should $(TESTS)

clean:
	rm -fr build

.PHONY: clean test

