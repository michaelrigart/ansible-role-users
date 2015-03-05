Ansible users Role
==================

An ansible role for managing users and groups.

Role Variables
--------------

    users_available: list of dictionaries containing data for user creation
      - username: username
        uid: user id
        groups: list of groups the user is member of
        shell: shell for the user
        name: full name of user
        createhomedir: create a homedir ( yes / no ) . If yes, ssh keys will be uploaded
        password: user password
        update_password: update password ( on_create / always )
        upload_key: define is ssh key needs to be uploaded ( yes / no )
    users_deleted: list of users that may be deleted. Provide the username
    users_groups_available: list of dictionaries containing data for group creation
      - groupname: group name
        gid: group id
    users_groups_deleted: list of groups to be deleted

When you set upload_key to "yes", make sure the users key is present in the roles file directory. The filename
needs to be the same as the username with .pub extension.

Example Playbook
-------------------------

    - hosts: servers
      roles:
         - { role: MichaelRigart.users }

License
-------

GPLv3

Author Information
------------------

Michaël Rigart <michael@netronix.be>