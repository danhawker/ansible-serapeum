ansible-serapeum
================

This Ansible role hopes to make the creation and population of offline or static Docker registries trivial.

Originally conceived to help Red Hat consultants in the installation of OpenShift Container Platform in disconnected or complex network environments.

Named after the daughter library of the Ancient Library of Alexandria. After the main library was destroyed, scholars used a "daughter library" in a temple known as the Serapeum, located in another part of the city.


The Flow
--------

* Setup local Docker (if required)
* Download images to local Docker cache (/var/lib/docker)
* Save images to a tarball
* Copy tarball to host machine (using whatever process is allowed/required)
* Load tarball to local cache
* Tag images for upload
* Push images to repository


Requirements
------------

This role makes extensive use of newer `docker_image` and `docker_image_facts` CORE module features and as such requires:

Anbible core >= 2.2.0
docker-py >= 1.7.0
Docker API >= 1.20

This role has only been tested on RHEL7 systems.

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Available variables are listed below, along with default values:

    serapeum_hostname: localhost
    serapeum_openshift_enabled: true
    serapeum_openshift_version: 3.4
    use_skopeo: false

    serapeum_offline_images_dir: /tmp


Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      roles:
         - { role: username.rolename, x: 42 }

License
-------

Apache 2.0 - See LICENSE

Author Information
------------------

Dan Hawker
