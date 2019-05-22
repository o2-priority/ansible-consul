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
    - o2-priority.consul
```

## Testing

To run integration tests of this role

PLATFORM = ubuntu or centos
```
kitchen test $PLATFORM --destroy=never && docker kill client server01 server02 server03 && docker rm client server01 server02 server03
```

> **Note:**
> `--destroy=never` must be supplied because multiple nodes are required to be running for all the tests to pass. As a consequence of this `$PLATFORM` must also be specified for the `kitchen test` command otherwise it will not work because of the `instance_name` property. The `docker` commands remove the left over containers for the next platform run


## Dependencies

none
