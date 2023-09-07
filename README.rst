****
Jeti
****

Inventory scripts for Jetporch - https://www.jetporch.com/

https://www.jetporch.com/inventory/dynamic-cloud-inventory

History
=======

Jet supports an inventory script format originally developed for Ansible in 2012, that was in turn inspired by a much earlier feature in Puppet
called 'external nodes'.

The jeti repo started was started with a friendly fork of the ansible inventory scripts. These scripts were removed from the ansible inventory tree after Ansible 2.9
as Ansible moved to a new system of inventory plugins. 

The reason for this fork is Jet can support the ansible inventory script format and still wanted to use them.

Status
======

These plugins may need and warrant changes to function.  Updates are very welcome and patches will be tended to quickly!

We want everything here to function at a high degree of quality, and if things are unsalveagable due to major
API changes, please let us know and these scripts can be retired.

Support and Development Guidelines
==================================

None of these plugins should be considered dead but they should be considered 'community maintained' as not all services therein
are ones we use regularly. Obviously we want inventories for systems such as EC2 to function at a particularly high degree of quality.

As such, some bug ticket resolution may be a bit 'self-service'. Please be respectful and do not contact listed authors of older code
for help with forked jeti inventory scripts, names are left around for attribution and copyright reasons, not for support.

If you would like to port features over from inventory scripts that were made since Ansible 2.9, that is welcome, but make sure
any ports are well tested and have ansible dependencies removed when you submit any pull requests.

Testing
=======

Follow the instructions on any inventory plugin.

Execute it manually with "./plugin.py"

Execute it with jetp: "jetp show --inventory ./plugin.py --groups all" to see how Jet loaded the plugin.

Authors
=======

Ansible was created by `Michael DeHaan <https://github.com/mpdehaan>`_
and has contributions from over thousands of users. We are thankful for every one
of their contributions here. `Ansible <https://www.ansible.com>`_ is currently a project of
 `Red Hat, Inc. <https://www.redhat.com>`_.

Future contributions to this repo (September 2023 and beyond) are made by
contributors of the Jetporch project.

License
=======

GNU General Public License v3.0 or later, see COPYING for details.

