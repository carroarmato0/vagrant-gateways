# Change log

This file contains al notable changes to the dhcp Ansible role.

This file adheres to the guidelines of [http://keepachangelog.com/](http://keepachangelog.com/). Versioning follows [Semantic Versioning](http://semver.org/).

## 2.2.0 - 2018-10-13

### Added

- (GH-13,14) support fixed address hosts in subnets (credit: [Ahmed Sghaier](https://github.com/asghaier))
- (GH-15) Add variable `dhcp_service_state`, to define the desired state of the service (default: started). (credit: [Alessandro Ogier](https://github.com/aogier))
- (GH-17) New configuration items for failover peer: `address`, `failover_peer`, `hba`, `load_balance_max_seconds`, `max-balance`, `max-lease-misbalance`, `max-lease-ownership`, `max_response_delay`, `max_unacked_updates`, `mclt`, `min-balance`, `peer_address`, `peer_port`, `port`, `role`, `split` (credit: [cacheira](https://github.com/cacheira))

### Changed

- (GH-11,12) The `domain_search` key of `dhcp_subnets` can now also be a list (credit: [Ahmed Sghaier](https://github.com/asghaier))
- (GH-16) Allow host declaration without specifying `fixed-address`. (credit: [Alessandro Ogier](https://github.com/aogier))

## 2.1.2 - 2017-11-21

### Changed

- Fixed Ansible 2.4 deprecation warnings (include: -> include_tasks)

## 2.1.1 - 2017-07-03

### Changed

- (GH-10) Fixed bug where playbook run fails because `dhcp_global_includes` is undefined

## 2.1.0 - 2017-06-26

### Added

- New configuration items:
    - (GH-7) `dhcp_global_log_facility`, `dhcp_global_server_name`, `dhcp_global_authoritative` (credit: [@jpiron](https://github.com/jpiron))
    - `dhcp_global_ntp_servers`, `dhcp_global_includes` (credit: Felix Egli)

- (GH-9) Support OMAPI keys and catch-all options (credit: [@joshbenner](https://github.com/joshbenner))

### Changed

- (GH-7) Several improvements: package state as variable instead of hard-coded, made host declarations global (credit: [@jpiron](https://github.com/jpiron)
- (GH-8) Fixed typo in README (credit: [@donvipre](https://github.com/donvipre)
- Quoted values in `dhcp_global_domain_search` (credit: Felix Egli)

## 2.0.0 - 2016-04-29

### Added

- Support for Ubuntu LTS 14.04 (Trusty Tahr) and 16.04 (Xenial Xerus)
- Tested on Fedora 23 and CentOS 6, and added to supported platforms

### Changed

- This version now uses the general package management module introduced in Ansible 2.0. This is considered a breaking change, since it wil no longer work with Ansible 1.6-1.7.

## 1.1.0 - 2016-04-28

### Added

- Support for PXE boot parameters bootp, booting, next-server, filename. Credits to [Rian Bogle](https://github.com/rbogle)
- Address pools within subnet declaration. Credits to [Birgit Croux](https://github.com/birgitcroux)
- Definition of classes with match statements

## 1.0.1 - 2015-08-28

### Changed

- Fixed a tag name
- Fixed GH-1: domain name no longer needs to be "double quoted"

## 1.0.0 - 2015-08-24

First release!

### Added

- Allow setting some global variables
- Subnet declarations in YAML
