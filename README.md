LIVEPROJECT-ANSIBLE-ROLE-EC2
=========

For launching and terminating `X` amount of AWS EC2 machines running Red Hat Enterprise Linux v8.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the `boto` package is required:

- `boto3`

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in `defaults/main.yml`, `vars/main.yml`, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. `hostvars`, `group_vars`, etc.) should be mentioned here as well:

- Role Defaults:

```yml
# Default region in which the resources will be deployed:
region: "ap-southeast-2"
# The amount of EC2 machines to be launched:
quantity: 3
# Whether the role will be creating or terminating instances (the values are `create` or `terminate`):
mode: "create"
```

- Role Vars:

```yml
key_name: The name of the SSH key pair that you must use to later log in to the instance(s).
rhel8_version: Specific version of the RHEL8 to be deployed.
instance_type: The size of the AWS EC2 instance.
aws_tags: Key/value pairs of the AWS tags to identify the resources.
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles:

- No dependencies

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too. An example of `create_ec2.yml`:

```yml
- hosts: localhost
  roles:
      - liveproject-ansible-role-ec2
```

By default, running the above `ansible-playbook -i inventory create_ec2.yml` will launch 3x EC2 machines of t2.micro size in Asia Pacific (Sydney) region.

License
-------

©2020 by Manning Publications Co. All rights reserved.

Author Information
------------------

Lucian Maly
