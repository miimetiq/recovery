miimetiq.recovery
=================

Helps on backup and restore process of the MIIMETIQ artifacts.

Requirements
------------

- For backing up process, source machine has to have MIIMETIQ docker data volumes present.
- For restoring process, target machine has to have MIIMETIQ docker data volumes present, the process is going to update the content of the volume.
- MIIMETIQ docker data volumes name start with the literal: "docker-compose".
- Folder /tmp has enough capacity for copying all volumes.
- 

Role Variables
--------------

```
---
miimetiq_stack: "miimetiq-composer"
local_backup_path: "/tmp/docker-volume-backup"
images_filepath: "/tmp/miimetiq-images.tar"
images_filelist: "/tmp/miimetiq-images.list"

rancher_backup_user: "YOUR-ROOT-USER"
rancher_backup_user_pass: "YOUR-ROOT-PASSWORD"
rancher_db_name: "cattle"
rancher_db: "/tmp/rancher.sqldump"
racher_sql_container_name: "rancher-mysql"
rancher_path: "/docker-data/rancher-server"


storage: "local" # s3, local and sync
content: "all" # all, images, volumes, sql

aws_access_key: "AWS-ACCESS-KEY"
aws_secret_key: "AWS-SECRET-KEY"
aws_region: "REGION"
aws_bucket: "BUCKET"
```

Example Playbook
----------------

Take a look on **test/**  directory for having a reference about how to setup your playbook.

License
-------

MIT

Author Information
------------------

Author: Oriol Rius <oriol.rius@nexiona.com>
Company: Nexiona Connectocrats,S.L.
Website: https://nexiona.com
