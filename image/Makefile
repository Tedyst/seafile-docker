server_version=7.1.5

base_image=ghcr.io/tedyst/seafile-docker/base-mc:18.04
base_image_squashed=ghcr.io/tedyst/seafile-docker/base-mc:18.04-squashed
pro_base_image=ghcr.io/tedyst/seafile-docker/pro-base-mc:18.04
pro_base_image_squashed=ghcr.io/tedyst/seafile-docker/pro-base-mc:18.04-squashed
server_image=ghcr.io/tedyst/seafile-docker/seafile-mc:$(server_version)
server_image_squashed=ghcr.io/tedyst/seafile-docker/seafile-mc:$(server_version)-squashed
pro_server_image=ghcr.io/tedyst/seafile-docker/seafile-pro-mc:$(server_version)
pro_server_image_squashed=ghcr.io/tedyst/seafile-docker/seafile-pro-mc:$(server_version)-squashed
latest_pro_server_image=ghcr.io/tedyst/seafile-docker/seafile-pro-mc:latest
latest_server_image=ghcr.io/tedyst/seafile-docker/seafile-mc:latest

docker_build_command = docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 --push -t

all:
	@echo
	@echo Pleaes use '"make base"' or '"make server"' or '"make push"'.
	@echo

base:
	cd base && $(docker_build_command) $(base_image) .

server:
	cd seafile && cp -rf ../../scripts ./ && $(docker_build_command) $(server_image) .

pro-base:
	cd pro_base && $(docker_build_command) $(pro_base_image) .

pro-server:
	cd pro_seafile && cp -rf ../../scripts ./ && $(docker_build_command) $(pro_server_image) .

.PHONY: base server pro-base pro-server
