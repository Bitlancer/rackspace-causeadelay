rackspace-causeadelay
=====================

Causes a boot delay in Strings base images until the hostname is set by the Nova agent.

Why?
====

This is primarily useful for those using tools like Puppet.  As of the time of writing this document, a custom snapshot of a Rackspace CentoS 6.x image launches a nova-agent process that fetches and sets the local hostname (replacing the default hostname, which is the name of the snapshot).  Unfortunately, this isn't a blocking request, and sometimes software like Puppet will start and generate SSL certificates prior to the proper hostname being set.
