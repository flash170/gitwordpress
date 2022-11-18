
test hosts
sudo ansible all -i inventory -m ping -u yura --ask-pass

yura@app1:~/WordPress$ ansible-playbook play-commontools.yml -u yura --extra-vars "target=app" -kK
SSH password:
BECOME password[defaults to SSH password]:

PLAY [app] ****************************************************************************************

TASK [Gathering Facts] ****************************************************************************
ok: [app2]
ok: [app1]

TASK [commontools : Common tools install] *********************************************************
changed: [app1]
changed: [app2]

TASK [commontools : Set timezone] *****************************************************************
changed: [app2]
changed: [app1]

PLAY RECAP ****************************************************************************************
app1                       : ok=3    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
app2                       : ok=3    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0


ansible-playbook play-commontools.yml -u ubuntu --extra-vars "target=app" --ask-vault-pass 

fatal: [app1]: FAILED! => {
    "changed": false,
    "msg": "AnsibleUndefinedVariable: 'mysql_db' is undefined"
}
<192.168.1.202> (0, b'', b'')
fatal: [app2]: FAILED! => {
    "changed": false,
    "msg": "AnsibleUndefinedVariable: 'mysql_db' is undefined"
}
