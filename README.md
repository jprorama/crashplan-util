Management scripts for the crashplan storage cluster

The initial function provides an ansible playist for gathering logs
from the specified servers.

```sh
ansible-playbook -i cp_hosts gatherlogs.yaml --extra-vars "hosts=master,store ticketnum=<cpticket>"
```

The host inventory is appropriate for running from a client that has access to
the master. It treats the master as the head node in the cluster and uses it to 
access the storage server.

The cp_host.template can be used to map to the local infrastructure.  If you treat
your master as the cluster entry point you can use a [jump host configuration](https://wiki.gentoo.org/wiki/SSH_jump_host)
to allow Ansible to work though that host against your storage server(s).
