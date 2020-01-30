Role Name
=========

Dell PowerMax Flash Storage Arrays require additional software available from https://github.com/dell/ansible-powermax to run. Despite the documentation provided by https://github.com/dell/ansible-powermax the easiest way to access the required Dell EMC PowerMax modules is by using their (not well advertised) role (which makes accessible an Ansible collection). I was the first download on the Dell EMC PowerMax role / collection, so I know it is not being widely used. However, it's very easy to use with the following instructions

- Install the role / collection with the instructions on https://galaxy.ansible.com/dellemc/powermax
- Now reference this collection at the top of your playbook, this reference allows ansible to use the Dell EMC PowerMax modules. If you never used a collection, check out some of the example playbooks packaged with this role. It's pretty easy.

After following the above steps, this role may be used to expand volume(s) by providing a list of dictionaries, documenting the wwn to expand, and the size (in GB) to expand that wwn to.

Dell EMC reached out to me to provide automation solutions for their Dell EMC PowerMax product. I'm an automation consultant / trainer, so, if you need help Automating your Dell EMC infrastructure, we should talk! I'd love to run a training solution for you and your team!

Written by Russell Zachary Feeser for Dell EMC. Contact z at rzfeeser.com or just visit rzfeeser.com if you're looking for Ansible training, or using Ansible with Dell EMC products.

Requirements
------------

- Install the role / collection with the instructions on https://galaxy.ansible.com/dellemc/powermax
- Reference the `dellemc.powermax` collection at the top of each playbook
- (Alternatively) Follow the instructions found within the documentation on https://github.com/dell/ansible-powermax to 'hard install' the prerequisite dependencies to avoid referencing the `dellemc.powermax` collection in every playbook solution

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

See "Requirements".

Example Playbook
----------------

An example of using this role is below. Notice that the collection is referenced, or the Dell EMC PowerMax modules and plugin must be installed, before Ansible can utilize this role. 

    - name: Expanding Dell EMC PowerMax volumes by WWN
      hosts: localhost
      
      collection:
        - dellemc.powermax
        
      roles:
        - dell_powermax_expand_vol_by_wwn

License
-------

BSD

Author Information
------------------

Dell EMC reached out to me to provide automation solutions for their Dell EMC PowerMax product. I'm an automation consultant / trainer, so, if you need help Automating your Dell EMC infrastructure, we should talk! I'd love to run a training solution for you and your team!

Written by Russell Zachary Feeser for Dell EMC. Contact z at rzfeeser.com or just visit rzfeeser.com if you're looking for Ansible training, or using Ansible with Dell EMC products.
