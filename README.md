Jeti
====

Inventory scripts for Jetporch - https://www.jetporch.com/

https://www.jetporch.com/inventory/dynamic-cloud-inventory

About This Repo
===============

Jet uses an inventory script format originally developed for Ansible in 2012, that was in turn inspired by an earlier feature from Puppet
called 'external nodes'.

This jeti repo started was started with a friendly fork of the ansible inventory scripts. These scripts were removed from the ansible inventory tree after Ansible 2.9
as Ansible moved to a new system of inventory plugins which were not easy to call from other tooling, thus warranting this fork.

With this fork, Jet can support the original inventory script format despite a difference in programming language.
We suspect other projects can also make use of this JSON data as is documented on the jetporch homepage, and would encourage this!

What Is Included
================

Take a look at the inventory/ directory for all of the plugins offered.  

Most plugins can work by copying the inventory plugin out of the repo
along with the associated configuration file. Many plugins also respond to environment variables. Details are almost always mentioned
in the source code.

Where the plugin imports some code from "jeti.module_utils" in most cases the plugin can be edited to not need these, as much of this
is related to legacy python 2.X support, and we do not mind requiring python3.  Pull requests to remove imports to jeti.module_utils
(with sufficient testing of the module) will always be accepted!

Status
======

As the originating fork was a handful of years old, a few plugins may need and warrant changes to function, or may be in need of additions to 
surface newer features from some of the services.  Updates via pull request are very welcome and patches will be tended to quickly!

We want everything here to function at a high degree of quality, and if things are unsalveagable due to major
API changes, please let us know and these scripts can be retired.

Tested
======

We maintain a list of plugins tested so far:

* Digital Ocean
* Docker

If you validate that a plugin is working, let us know with a pull request or even just a GitHub ticket.  Plugins that get no users
after a year may be deleted.

Support and Development Guidelines
==================================

None of these plugins should be considered dead but they should be considered 'community maintained' as not all services therein
or features in those services are ones that the project leadership uses regularly.

Obviously we want inventories for systems such as AWS/EC2, GCE, etc, to function at a particularly high degree of quality.

Please be respectful and do not contact listed authors of older code
for help with forked jeti inventory scripts, names are left around for attribution and copyright reasons, not for support.

If you would like to port features over from inventory scripts that were made since Ansible 2.9, that is welcome, but make sure
any ports are well tested and has no dependencies on Ansible.

Note that because Jetporch supports a more liberal interpretation of the historical Ansible module format than Michael developed
in 2012, scripts in this repo (especially new ones) may diverge and not be loadable by classic Ansible. 
We are fine with this and that is not a development concern.

New inventory scripts do not need to accept '--host', as this is not used.  Pull requests to remove this feature
are also accepted.

Testing
=======

Follow the instructions on any inventory plugin.

Chmod +x the plugin, then execute it manually with "./plugin.py" or "python3 ./plugin.py"

You may need to install some dependencies, for instance "pip3 install requests".

You may need to have the configuration file for the module configured.  If so, copy the configure file and the script
out to another directory and edit the configuration file there.  Make sure the changes to configuration files do not
appear in any pull requests, such as to leak an API key!

Now execute the inventory script with jetp: "jetp show --inventory ./plugin.py --groups all" to see how Jet loaded the plugin.

You can now use the inventory plugin with "jetp ssh --inventory ./plugin.py --playbook playbook.yml"!

Authors
=======

Ansible was created by [Michael DeHaan](https://github.com/mpdehaan)
and has contributions from over thousands of users. We are thankful for every one
of their contributions here. [Ansible](https://www.ansible.com) is maintained by and
is a trademark of `Red Hat, Inc. <https://www.redhat.com>`_.

Future contributions to this repo (September 2023 and beyond) are made by
contributors of the Jetporch project.

License
=======

GNU General Public License v3.0 or later, see COPYING for details.


