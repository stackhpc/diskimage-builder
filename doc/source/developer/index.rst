Developer Guide
===============

.. toctree::
   :maxdepth: 1

   design
   components
   invocation
   caches
   developing_elements
   dib_lint
   stable_interfaces
   vhd_creation
   Module index <api/modules>

This documentation explains how to get started with creating your own
disk-image-builder elements as well as some high level concepts for element
creation.

Quickstart
----------

To get started developing with ``diskimage-builder``, install to a
``virtualenv``::

 $ mkdir dib
 $ cd dib
 $ virtualenv env
 $ source env/bin/activate
 $ git clone https://opendev.org/openstack/diskimage-builder
 $ cd diskimage-builder
 $ pip install -e .

You can now simply use ``disk-image-create`` to start building images
and testing your changes.  When you are done editing, use ``git
review`` to submit changes to the upstream gerrit.


Python module documentation
---------------------------

For internal documentation on the DIB python components, see the
:ref:`modindex`.


Finding Work
------------

We maintain a list of low-hanging-fruit tags on launchpad:

* `https://bugs.launchpad.net/diskimage-builder/+bugs?field.tag=low-hanging-fruit
  <https://bugs.launchpad.net/diskimage-builder/+bugs?field.tag=low-hanging-fruit>`_
