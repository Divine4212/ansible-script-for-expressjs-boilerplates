# ansible-script-for-expressjs-boilerplates
### Automated Deployment and Configuration with Ansible for Boilerplates
This guide will walk you through the process of deploying the boilerplate application using Ansible on a remote Ubuntu 22.04 server. The playbook will handle everything from cloning the repository to setting up the necessary services and configurations.

## Prerequisites
Before you begin, ensure you have the following:

1. A remote Ubuntu 22.04 server with SSH access.
2. Ansible installed on your local machine.
3. Python 3.12 installed on the remote server.

NB: This is an expressjs boilerplate application

## Steps

1. Clone the repository and cd into the directory
```sh
git clone https://github.com/Divine4212/ansible-script-for-expressjs-boilerplates.git

cd ansible-script-for-expressjs-boilerplates
```

2. Add an inventory.cfg file
```sh
touch inventory.cfg
```
the contents of the inventory.cfg file are, your target `ip address`, `ansible_user=ubuntu` and `ansible_ssh_private_key_file=/path/to/keypair
```sh
[hng]
ip-address ansible_user=ubuntu ansible_ssh_private_key_file=path/to/main-key.pem
```

4. Run the Ansible Playbook

Execute the Ansible playbook using the following command:
```sh
ansible-playbook main.yaml -b -i inventory.cfg
```

## Verification
1. Check Application Status

Verify that the application is running by checking the status of the systemd service:
```sh
sudo systemctl status app.service
```

2. Access the Application

Open your browser and navigate to the server's IP address to verify that the application is running correctly.

3. Check Logs

Ensure that logs are being written to the specified log files:

```sh
sudo tail -f /var/log/stage_5b/out.log
sudo tail -f /var/log/stage_5b/error.log
```

## Conclusion
This guide provides a comprehensive approach to deploying the boilerplate application using Ansible. By following these steps, you can automate the setup and configuration of your application, ensuring a consistent and reliable deployment process.
