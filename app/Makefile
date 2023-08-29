help:
	@echo "\t* clean - remove all build, test, coverage and Python artifacts"
	@echo "\t* build - package"

all: default

default: clean build

clean:
	# Clear Deploy Directory
	rm -rf dist/

build: clean
	# Create Deploy Directory
	mkdir ./dist

	# Copy main.py & config.json
	cp ./src/main.py ./dist
	cp ./src/config.json ./dist

	# Zip custom pakages
	zip -r dist/jobs.zip ./src/jobs
	zip -r dist/shared.zip ./src/shared

	# Zip dependency library
	pip install -r ./src/requirements.txt -t ./dist/libs
	cd ./dist/libs && zip -r -D ../libs.zip .
