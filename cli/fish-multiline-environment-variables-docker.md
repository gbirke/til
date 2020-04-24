# How to set multiline environment variables for Docker

Say you want to pass an SSH private key to a Docker container. In Bash, you'd do

	docker run -it --rm -e SSH_KEY="$(< ~/.ssh/id_rsa)" my_container

Up until version 3.1 this was not possible in the Fish shell. There was a [long-running
issue](https://github.com/fish-shell/fish-shell/issues/159) that discussed the "right" way
to do this, mainly because they did not like the bash syntax with the dollar sign. Finally
the developers settled for the `string collect` command. The above equivalent for the Fish
shell is:

	docker run -it --rm -e SSH_KEY=(cat ~/.ssh/id_rsa | string collect) my_container
