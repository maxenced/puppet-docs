---
title: "PuppetDB » Known Issues"
layout: default
---


Bugs and Feature Requests
-----

[redmine]: http://projects.puppetlabs.com/projects/puppetdb/issues

PuppetDB's bugs and feature requests are managed in [Puppet Labs's issue tracker][redmine]. Search this database if you're having problems, and please report any new issues to us!

Broader Issues
-----

### Autorequire relationships are opaque

Puppet resource types can "autorequire" other resources when certain conditions are met, and we don't correctly model these relationships in PuppetDB. (For example, if you manage two file resources where one is a parent directory of the other, Puppet will automatically the parent a dependency of the child.) The problem is that these dependencies are not written to the catalog; puppet agent creates these relationships on the fly when it reads the catalog. Getting these relationships into PuppetDB will require a significant change to Puppet's core.
