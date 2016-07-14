Management scripts for the crashplan storage cluster

The initial function provides an ansible playist for gathering logs
from the specified servers.

{{{
ansible-playbook -i cp_hosts gatherlogs.yaml --extra-vars "hosts=master,store ticketnum=<cpticket>"
}}}

The host inventory is appropriate for running from a client that has access to
the master. It treats the master as the head node in the cluster and uses it to 
access the storage server.
