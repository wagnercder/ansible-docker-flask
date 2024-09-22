# ansible-docker-flask

This project is designed to reinforce various concepts of Ansible and Vagrant. To achieve this objective, we've developed a simple application using Flask + Redis. These services are orchestrated and deployed using Docker, managed directly by Ansible.

That are a lot of different concepts from Ansible being used, such as:
- roles
- tasks
- handlers
- templates
- dependencies
- inventory

To get started, ensure you have Vagrant (version 2.2.19 or higher) installed. Then, execute the following command:

```
vagrant up # vagrant may require sudo permission
```

This command will instantiate a VirtualBox running Ubuntu 20.04, which serves as the target machine for configuring and running our application.

To check if the vagrant machine was created properly, you can run:

```
vagrant ssh my_host
```

After running `vagrant up` it will create a directory where the files from the virtual machine are persisted. One of the generated files is related
to its private ssh key, that key is needed to access the machine through ansible.

Take a look at the inventory file, there you can set the path to the private_key created by ansible, by replacing `path_to_vagrant` with your own.

On the controller side, Python 3.9 is required as Ansible (version 2.15.12) is a tool written in Python.

```
export ANSIBLE_CONFIG=/your_path/ansible-docker-flask/ansible-project/ansible.cfg
```

Make sure to give read permissions to the vagrant's private_key, so ansible can run our playboook through ssh.

```
ansible-playbook main.yml
```

You can access the running application at `192.168.61.0:5000`.

To change the current IP address, update the `Vagrantfile`. To modify the port, update the `docker-compose.yml` file.
