Kembali
=======

**kembali.rollback** are ansible roles to easily manage the rollback process for scripting applications such as Nodejs, Golang, PHP, Python and Ruby etc.

Installation
------------

kembali.rollback is an ansible role distributed globally using [Ansible Galaxy](https://galaxy.ansible.com/). In order to install kembali role you can use the following command.

```
$ ansible-galaxy install fajarhide.kembali
```

Update
------

```
$ ansible-galaxy install --force fajarhide.kembali
```

Rolling back
-----------

In order to rollback with kembali, you need to set up the deployment and run the rollback playbook.

```ansible-playbook -i hosts rollback-project.yml```

If you try to rollback with zero or one releases deployed, an error will be raised and no actions performed.

Variables you can tune in rollback role are less than in deploy one:

```yaml
vars:
  kembali_deploy_to: "/var/www/my-app" # Base path to deploy to.
  kembali_version_dir: "releases" # Releases folder name
  kembali_current_dir: "current" # Softlink name. You should rarely changed it.

  # Hooks: custom tasks if you need them
  kembali_before_symlink_tasks_file: "{{ playbook_dir }}/<your-deployment-config>/my-before-symlink-tasks.yml"
  kembali_after_symlink_tasks_file: "{{ playbook_dir }}/<your-deployment-config>/my-after-symlink-tasks.yml"
  kembali_before_cleanup_tasks_file: "{{ playbook_dir }}/<your-deployment-config>/my-before-cleanup-tasks.yml"
  kembali_after_cleanup_tasks_file: "{{ playbook_dir }}/<your-deployment-config>/my-after-cleanup-tasks.yml"
```

License
-------

MIT
