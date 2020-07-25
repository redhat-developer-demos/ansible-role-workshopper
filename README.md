Ansible role for RedHat Developers Workshop
===========================================

Ansible to configure [OpenShift](https://try.openshift.com) cluster for Red Hat Developer Workshops and Demos.

The role can also be used to install and configure:

- [ ] [OpenShift Serverless](https://knative.dev), both Serving and Eventing

- [ ] [OpenShift Pipelines](https://knative.dev)

- [ ] [OpenShift Servicemesh](https://knative.dev)

- [ ] [AMQ Streams](https://knative.dev)

- [ ] [AMQ Interconnect](https://knative.dev)

- [ ] [AMQ Integration Camel-K](https://knative.dev)

Requirements
------------

- [Docker Desktop](https://www.docker.com/products/docker-desktop) or Docker for Linux

- [Ansible](https://ansible.com) >= v2.9.10 

- OpenShift 4.5+ Cluster

```shell
pip3 install \
  -r https://raw.githubusercontent.com/kameshsampath/ansible-role-kind/master/requirements.txt
ansible-galaxy role install kameshsampath.kind
ansible-galaxy collection install community.kubernetes
```
__NOTE__: For Windows its recommended to use Windows Subsystem for Linux (WSL)

Role Variables
--------------

| Variable Name| Description | Default |
|--|--|--|
| deploy_serverless | Deploy OpenShift Serverless | True |
| deploy_pipelines | Deploy OpenShift Pipelines | True |
| deploy_servicemesh | Deploy OpenShift Pipelines | False |
| deploy_amq_streams | Deploy AMQ Streams  | False |
| deploy_amq_integration | Deploy AMQ Integration  | False |


Example Playbooks
----------------
The [examples](https://github.com/redhat-developer-demos/ansible-role-workshopper/tree/master/examples) directory has various playbook examples to get started using this role

License
-------

[Apache v2](https://github.com/redhat-developer-demos/ansible-role-workshopper/tree/master/LICENSE)

Author Information
------------------

[Kamesh Sampath](mailto:kamesh.sampath@hotmail.com)

Issues
=======

[Issues](https://github.com/redhat-developer-demos/ansible-role-workshopper/issues)

Testing
=======

Requirements
------------
- [Vagrant](https://www.vagrantup.com)
- Extra Python modules
```shell
pip3 install \
  -r https://raw.githubusercontent.com/kameshsampath/ansible-role-kind/master/molecule/requirements.txt
```

All tests are built using [molecule](https://molecule.readthedocs.io/en/latest/index.html) with following scenarios:

* Knative
```shell
molecule test  -s deploy_knative
```
* Clean machine Test

This test run on clean vm (Centos8) using vagrant. It will run all the tests end to end and verify the same.

```shell
molecule test  -s vm
```

