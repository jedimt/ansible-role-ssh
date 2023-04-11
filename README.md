Ansible Role: Update Known Hosts
=========

Updates the known_hosts file on the Ansible controller with the

Requirements
------------

Requires ssh-keyscan on the Ansible controller.

Role Variables
--------------

There are three variables included in the role:

    ssh_known_hosts_command: "ssh-keyscan -T 10"
    ssh_known_hosts_file: "{{ lookup('env','HOME') + '/.ssh/known_hosts' }}"
    ssh_known_hosts: "{{ groups['servers'] }}"

Dependencies
------------

None

Example Playbook
----------------

    # ===========================================================================
    # Update Ansible controller SSH keys
    # ===========================================================================
    - name: Update SSH keys for Ansible controller known_hosts
      hosts: localhost
      connection: local
      gather_facts: false
      become: false

      roles:
        - jedimt.ssh

License
-------

MIT

Author Information
------------------

Aaron Patten
aaronpatten@gmail.com
