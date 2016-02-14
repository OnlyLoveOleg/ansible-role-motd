# motd

Role to manage motd on remote. By default the role won't make any changes on remote
if the required variables not defined.


##Role Variables

```
motd - full or relative path to the motd file will be copied to /etc/motd
```


Ubuntu spesific:

```
landscape_common_remove - this variable can be really anything if defined the package
                          landscape-common will be removed.


update_motd_d - full or relative path to the update-motd.d directory (make sure to
                preserve the directory name) will be synchronized to /etc/update-motd.d
                in rsync --delete fashion.
```



##Example Playbook

```
- hosts: us-east-1a
  roles:
   - motd
```

```
group_vars/us-east-1a.yml
...
# role:motd
motd: group_files/us-east-1a/motd/motd.j2
landscape_common_remove: yes
update_motd_d: group_files/us-east-1a/motd/update-motd.d
```

NOTE: in the example above we used `group_files/<group>/<role-name>` as a way to manage
      the actual raw files.


##License

MIT


##Author Information

Tal Lannder

tal@pjili.org
