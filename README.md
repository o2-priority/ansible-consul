CONSUL
======

Ansible role to install and configure Consul


## Example

- To install and configure consul agent

```
  roles:
    - wunzeco.consul
```


- To configure server as consul master:

```
  vars:
    consul_home:    	"/opt/consul"
    consul_extra_opts:  "-server -bootstrap-expect 1"

  roles:
    - wunzeco.consul
```


## Testing

To run this role's integration tests

```
PLATFORM=ubuntu-1604        # ubuntu-1404 or centos
kitchen verify $PLATFORM && kitchen destroy $PLATFORM
```


## Dependencies

none
