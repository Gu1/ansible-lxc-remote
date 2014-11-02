ansible-lxc-remote
==================

Connection backend to manage remote LXC containers by ssh'ing into the host machine and using lxc-attach to get a shell on the container.

It allows ansible to manage LXC containers without having to run a publicly accessible ssh daemon on every single one of them, with all the hassle it causes (having to assign a public ipv4 on each container or having to do port forwarding for each containers's ssh daemon on the host, or having ipv6 assigned to each container but requiring ipv6 to access them...).


How to Install
----------
In your ansible.cfg, add the following line:

    connection_plugins = path/to/the/ansible-lxc-remote/directory/

How to use
----------
In your inventory, just put:

    container_name ansible_ssh_user=user ansible_ssh_host=127.0.0.1 ansible_ssh_port=22 ansible_connection=lxc_remote

Then you can run commands on your containers as you would with any other machine. It should even support su/sudo (on the LXC host).
