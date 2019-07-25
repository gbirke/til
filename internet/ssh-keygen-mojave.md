# Generating SSH keys on macOS Mojave

Mojave changed the `ssh-keygen` command to generate RFC4716-formatted keys by default- which are incompatible with the PEM-formatted keys on some Linux machines. To create keys in the correct format, you must use the parameter `-m PEM` like this:

    ssh-keygen -t rsa -b 4096 -m PEM -C "your-name@example.com"

See https://serverfault.com/questions/939909/ssh-keygen-does-not-create-rsa-private-key for more information.

