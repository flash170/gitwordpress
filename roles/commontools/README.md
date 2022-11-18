Роль commontools
=========

Данная роль устанавливает основные, безовые программы на серверах.

Role Variables
--------------
Примеры приведены в defaults/main.yml

Dependencies
------------

None

Example Playbook
----------------
play-commontools.yml
---
- hosts: "{{ target }}"
  become: yes
  become_method: sudo
  roles:
    - {role: commontools}

Play
------------

ansible-playbook play-commontools.yml -u ubuntu --extra-vars "target=production"

License
-------

MIT
