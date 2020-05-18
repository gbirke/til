## Ansible variable resolution

If your inventory defines child groups and you have a host in a non-child
group and in a child group, Ansible will use the variables of the child group.
Example

		[books]
		books.example.com

		[movies]
		movies.example.com

		[entertainment]
		movies.example.com
		games.example.com

		[media:children]
		books
		movies

Ansible will overwrite the group vars for `entertainment` for the host `movies.example.com` with the group vars for `media`.

Source: https://docs.ansible.com/ansible/2.7/user_guide/intro_inventory.html#how-variables-are-merged


