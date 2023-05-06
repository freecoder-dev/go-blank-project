##------------------------------
##
## Project build configuration
##
##------------------------------
APP_NAME = project_name
APP_BINARY = ../bin/${APP_NAME}
MAIN_ENTRY = ../src/app

## release version of the application
VERSION = v1.0
VERSION_PKG = ${APP_NAME}/src/app

## build options
# FLAGS ?= -s -w -X ${VERSION_PKG}.Revision=${VERSION}
FLAGS ?= -s -w -X main.Revision=${VERSION}

## build binary
build:
	@go build -ldflags="${FLAGS}" -o ${APP_BINARY} ${MAIN_ENTRY}
	@echo "built..."

## build and run the application
run: build
	@chmod u+x ${APP_BINARY}
	@${APP_BINARY} &
	@echo "started..."

## clean and delete binaries
clean:
	@go clean
	@rm ${APP_NAME}
	@echo "cleaned..."

## start the application
start: run

## stop the running application
stop:
	@-pkill -SIGTERM -f "${APP_NAME}"
	@echo "stopped..."

## stop and start the application
restart: stop start

