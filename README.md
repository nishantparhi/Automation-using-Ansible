# Automation of service manipulation

This script can be used in service manipulation.
This Ansible role is made to automate [this task!](https://fedoraproject.org/wiki/QA:Testcase_base_service_manipulation)

In the `roles/tasks/main.yml` there is a variable named `service` which can be replaced by any service of your choice. In the proof I have used to automate the service of *_jenkins_*.

Below are the instructions on how to run this script:

1. Boot your Virtual Machine(Or your system) and start the sshd service.

2. Create a passwordless connection between the systems

3. In your inventory file, mark1.yml file, roles/test/main.yml file, and roles/test/inventory file; change the host to you system (`nishant-fedora-vm@192.168.237.135` in my case)

4. Run this on your main system `ansible-playbook playbook.yml -e "service=jenkins" -K`

5. Your target system will be rebooted thrice while running the role.

**NOTE: Do not run the Ansible-role on the localhost, it will throw back errors in the rebooting process.**

Proof: https://asciinema.org/a/byW0pQLsfeuNcQBFgCB5erzhc
