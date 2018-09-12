Kembali
=======

**kembali ((rollback))** adalah role yang dapat digunakan untuk mengelola proses rollback dengan mudah untuk aplikasi scripting seperti Nodejs, Golang, PHP, Python dan Ruby dll.

Installation
------------

Untuk menginstal role **kembali**, Anda dapat menggunakan perintah berikut dengan **ansible-galaxy**

```
$ ansible-galaxy install fajarhide.kembali
```

Update
------

```
$ ansible-galaxy install --force fajarhide.kembali
```

Rolling back
------------

Agar dapat rollback dengan role **kembali**, Anda perlu mengatur deploy dan menjalankan rollback playbook.

```
ansible-playbook -i hosts rollback-project.yml
```


Variables
---------

Variabel yang dapat Anda atur dalam peran rollback seperti yang diterapkan berikut:


```file.yaml
vars:
  kembali_deploy_to: "/var/www/my-app" # Path tujuan yang akan dirollback

  # Custom task jika dibutuhkan
  kembali_before_symlink_tasks_file: "{{ playbook_dir }}/<your-deployment-config>/my-before-symlink-tasks.yml"
  kembali_after_symlink_tasks_file: "{{ playbook_dir }}/<your-deployment-config>/my-after-symlink-tasks.yml"
  kembali_before_cleanup_tasks_file: "{{ playbook_dir }}/<your-deployment-config>/my-before-cleanup-tasks.yml"
  kembali_after_cleanup_tasks_file: "{{ playbook_dir }}/<your-deployment-config>/my-after-cleanup-tasks.yml"
```

License
-------

MIT
