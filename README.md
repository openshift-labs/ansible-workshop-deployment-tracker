Ansible Role: Track Deployment of OpenShift Workshops
[![Build Status](https://travis-ci.org/openshift-labs/ansible-workshop-deployment-tracker.svg?branch=master)](https://travis-ci.org/openshift-labs/ansible-workshop-deployment-tracker)
=========

Ansible Role for tracking the deployment of OpenShift workshops. This role issues a CURL request to a Google Form with the workshop type and workshop name.


Role Variables
------------

| Variable                  | Default Value                             | Description                                     |
|---------------------------|-------------------------------------------|-------------------------------------------------|
|`apps_hostname_suffix`     | apps.not-available.openshiftworkshop.com  | Hostname suffix for the workshop                |
|`workshop_type`            | not-available                             | Type of workshop: starter, cloud-native, devops |
 

OpenShift Version Compatibility
------------
When listing this role in `requirements.yml`, make sure to pin the version of the role via one of the tags:

```
- src: openshift_labs.workshop_deployment_tracker
  version: 1.0.0
```  

The following tables shows the version combinations that are tested and verified:

| Role Version      | OpenShift Version |
|-------------------|-------------------|
| 1.0.x   | 3.10.x, 3.11.x   |


Note that if a version combination is not listed above, it does **NOT** mean that the latest role version 
won't work on that OpenShift version. The above table is merely the combinations that we have tested and verified.


Example Playbook
------------

```
name: Example Playbook
hosts: localhost
tasks:
- import_role:
    name: openshift_labs.workshop_deployment_tracker
  vars:
    apps_hostname_suffix: "apps.mystarter-a1b2.openshiftworkshop.com"
    workshop_type: "starter"
```
