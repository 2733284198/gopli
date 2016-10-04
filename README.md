Cylinder
========
Database backup between remote hosts (or local) written in Golang.

## Usage
Write down setting file in toml.
```
[database]
  [database.remotehost1]
  host = "xxx.xxx.xxx.xxx"
  port = 3306
  management_system = "mysql"
  name = "remotehost1_db"
  user = "root"
  password = "password"

  [database.remotehost2]
  host = "yyy.yyy.yyy.yyy"
  port = 3306
  management_system = "mysql"
  name = "remotehost2_db"
  user = "root2"
  password = "password2"

[ssh]
  [ssh.remotehost1]
  ssh_key = "~/.ssh/id_rsa"

  [ssh.remotehost2]
  ssh_key = "~/.ssh/id_rsa"
```

```
cylinder sync remotehost1 remotehost2 -c config/cylinder.toml
```
