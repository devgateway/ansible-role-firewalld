# devgateway.firewalld

Install and run Firewalld, and enable services.

## Required Variables

### `fwd_services`

List of services or ports (in the format of `port/protocol` or `port-port/protocol`) to enable.

Note that the services must already be known to Firewalld, i.e. their
packages must be installed.

## Playbook Example

    ---
    - hosts:
        - foobar
      tasks:
        - name: Configure firewall
          include_role:
            name: devgateway.firewalld
          vars:
            fwd_services:
              - vnc-server
      handlers:
        - name: Firewall settings changed
          debug:
            msg: Reconnect to the server


## License

GPLv3+

## Author Information

Copyright 2018, Development Gateway

