---
layout: post
title: "A quick intro to Juju Resources"
date: 2016-04-19 15:58
comments: true
categories: juju
---

For all the fancy bits of technology in your infrastructure there are still
plenty of simple things that are useful and will probably never go away. One of
these is blobs. Blobs are useful, they can be workload payloads, binaries for
software, or whatever bits you need to deploy and manage.

Juju never had a way of knowing about blobs. Sure, you could plop something on
an http server and your charm could snag it. But then we're not really solving
any problems for you, you still need to deal with managing that blob, versioning
it, using a server to serve it to clients, etc.

Ideally, these blobs are accounted for, just like anything else in your
 infrastructure, so it makes sense that as of Juju 2.0 we can _model blobs as
part of a model_; we call it Juju Resources. That way we can track them, cache
them, acl them, and so on, just like everything else.

### Resources

A new concept has been introduced into Charms called
"resources". Resources are binary blobs that the charm can utilize, and
are declared in the metadata for the Charm. All resources declared will
have a version stored in the Charm store, however updates to these can
be uploaded from an admin's local machine to the controller.

#### Change to Metadata

A new clause has been added to `metadata.yaml` for resources. Resources
can be declared as follows:

    resources:
      name:
        type: file                         # the only type initially
        filename: filename.tgz
        description: "One line that is useful when operators need to push it."

#### New User Commands

Three new commands have been introduced:

1.  `juju list-resources`

    Pretty obvious, this command shows the resources required by and those in use by an
    existing service or unit in your model.

2.  `juju push-resource`

    This command uploads a file from your local disk to the juju
    controller to be used as a resource for a service.

3. `juju charm list-resources`

    `juju charm` is the the juju CLI equivalent of the "charm" command
    used by charm authors, though only applicable functionality is
    mirrored.

In addition, resources may be uploaded when deploying or upgrading
charms by specifying the resource option to the deploy command. Following
the resource option should be name=filepath pair.  This option may be
repeated more than once to upload more than one resource.

    juju deploy foo --resource bar=/some/file.tgz --resource baz=./docs/cfg.xml

or

    juju upgrade-charm foo --resource bar=/some/file.tgz --resource baz=./docs/cfg.xml

Where bar and baz are resources named in the metadata for the foo charm.

### Conclusion

 It's pretty simple. Put stuff in a place and be able to snag it later. People
can use resources for all sorts of things.

- Payloads for the service you're deploying.
- Software. Let's face it, when you look at the amount of enterprise software in the wild, you're not going to be able to `apt` eveything; you can now gate trusted binaries into resources to be used by charms.

Hope you enjoy it!
