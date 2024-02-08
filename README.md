# ansible-docker-flask

This project is designed to reinforce various concepts of Ansible and Vagrant. To achieve this objective, we've developed a simple application using Flask + Redis. These services are orchestrated and deployed using Docker, managed directly by Ansible.

That are a lot of different concepts from Ansible being used, such as:
- roles
- tasks
- handlers
- templates
- dependencies
- inventory

To get started, ensure you have Vagrant (version 2.2.6) installed. Then, execute the following command:

```
vagrant up
```

This command will instantiate a VirtualBox running Ubuntu 18.04, which serves as the target machine for configuring and running our application.

On the controller side, Python is required as Ansible (version 2.13.13) is a tool written in Python.

```
ansible-playbook main.yml -i inventory
```

You can access the running application at `192.168.61.0:5000`.

To change the current IP address, update the `Vagrantfile`. To modify the port, update the `docker-compose.yml` file.