# Solr Jetty (`solr-jetty`)

**Part of the BAS Ansible Role Collection (BARC)**

Installs Solr with Jetty using the solr-jetty meta package

## Overview

* Installs Solr Jetty meta-package which installs Solr into a Jetty container
* Configures Jetty

## Availability

This role is designed for internal use but if useful can be shared publicly.

## Usage

### Requirements

#### BAS Ansible Role Collection (BARC)

* `openjdk-7`

## Variables

* `solr_jetty_no_start`
    * Controls whether Jetty is not allowed to start
    * This variable **MUST** be either "0" (allowed to start) or "1" (not allowed to start).
    * You **SHOULD NOT** need to change this value.
    * Default: "0"
* `solr_jetty_host`
    * The interface Jetty will bind to
    * For security purposes this variable **SHOULD** be a local only interface.
    * By default this variable will be the IPv4 address of the local interface.
    * You **SHOULD NOT** need to change this value
    * Default: "{{ ansible_lo.ipv4.address }}"
* `solr_jetty_port`
    * The port Jetty will bind to
    * Default: "8080"
* `solr_jetty_java_options`
    * Additional options used to configure the Java environment in which Jetty/Solr operate within
    * By default this variable configures Java to use IPv4 (rather than IPv6) networking, this is not required and can be disabled if needed.
    * Default: "-Djava.net.preferIPv4Stack=true"

## Contributing

This project welcomes contributions, see `CONTRIBUTING` for our general policy.

## Developing

### Committing changes

The [Git flow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow/) workflow is used to manage development of this package.

Discrete changes should be made within *feature* branches, created from and merged back into *develop* (where small one-line changes may be made directly).

When ready to release a set of features/changes create a *release* branch from *develop*, update documentation as required and merge into *master* with a tagged, [semantic version](http://semver.org/) (e.g. `v1.2.3`).

After releases the *master* branch should be merged with *develop* to restart the process. High impact bugs can be addressed in *hotfix* branches, created from and merged into *master* directly (and then into *develop*).

### Issue tracking

Issues, bugs, improvements, questions, suggestions and other tasks related to this package are managed through the BAS Web & Applications Team Jira project ([BASWEB](https://jira.ceh.ac.uk/browse/BASWEB)).

## License

Copyright 2015 NERC BAS. Licensed under the MIT license, see `LICENSE` for details.