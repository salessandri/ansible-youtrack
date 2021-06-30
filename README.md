# YouTrack

This role sets up a YouTrack service using [JetBrain's official docker image](https://hub.docker.com/r/jetbrains/youtrack).

This only takes care of setting up the service, its configuration is done through the web interface once the service is running.

## Requirements

This role relies on `docker` being available on the host and the [`docker_container` ansible module](https://docs.ansible.com/ansible/latest/modules/docker_container_module.html) in ansible.

[`geerlingguy.docker` role](https://galaxy.ansible.com/geerlingguy/docker) can be used to setup docker.
For the `docker_container` python module, [`geerlingguy.pip` role](https://galaxy.ansible.com/geerlingguy/pip) can be used to install Python's [`docker` package](https://pypi.org/project/docker/).

## Role Variables

 - **`youtrack__version`** (optional, default: _2021.2.19690_): Image version tag to use.
 - **`youtrack__container_name`** (optional, default: _youtrack-server_): Name to use for the container created by the role.
 - **`youtrack__data_dir`** (optional, default _/var/youtrack/_): Folder to use for persistent files.
 - **`youtrack__listen_host`** (optional, default: _127.0.0.1_): Address where the container will publish the service's socket.
 - **`youtrack__listen_port`** (optional, default: _8080_): Port where the container will publish the service's port.

## Example Playbook

The following would be a fairly common role usage example:

```yaml
- host: youtrack.my-domain.com
  roles:
    - role: salessandri.youtrack
```

## License

MIT

## Author Information

This role was created in 2021 by [Santiago Alessandri](https://rambling-ideas.salessandri.name).
