.. _ubuntu:

.. toctree::
 
Ubuntu 18.04 - Setup the FD.io Repository
==========================================

FD.io VPP is installed using Package Cloud. For a complete set of
instructuctions on how to install VPP with package cloud please refer
to `Package Cloud <https://packagecloud.io/fdio/release>`_

Choose one of the following releases to install. 

Update the OS
-----------------------

It is a good idea to first update and upgrade the OS before starting; run the
following command to update the OS:

.. code-block:: console

    apt-get update


Point to the Repository
-----------------------------------

Create a file **/etc/apt/sources.list.d/99fd.io.list** with contents that point to
the version needed. The contents needed are shown below.

.. _install_vpp:

VPP latest Release
^^^^^^^^^^^^^^^^^^^

Create the file **/etc/apt/sources.list.d/99fd.io.list** that contain the following contents:

.. code-block:: console

   deb [trusted=yes] https://packagecloud.io/fdio/release/ubuntu xenial main

Get the key:

.. code-block:: console

  curl -L https://packagecloud.io/fdio/release/gpgkey | sudo apt-key add -

VPP master Branch
^^^^^^^^^^^^^^^^^^^^

Create the file **/etc/apt/sources.list.d/99fd.io.list** that contain the following contents:

.. code-block:: console

   deb [trusted=yes] https://packagecloud.io/fdio/master/ubuntu xenial main

Get the key:

.. code-block:: console

  curl -L https://packagecloud.io/fdio/master/gpgkey | sudo apt-key add -


Install the Mandatory Packages
===============================

Install the mandatory packages by running the following commands:

.. code-block:: console

  sudo apt-get update
  sudo apt-get install vpp

  
Install the Optional Packages
==============================

Install the optional packages by running the following command:

For the release packages:

.. code-block:: console

  sudo apt-get install vpp-plugins vpp-api-java vpp-api-lua vpp-api-python vpp-dbg vpp-dev

For the master packages:

.. code-block:: console

  sudo apt-get install vpp-plugin-core vpp-api-python vpp-dbg vpp-dev vpp-plugin-dpdk

Uninstall the Packages
======================

Uninstall the  packages by running the following command:

.. code-block:: console

  sudo apt-get remove --purge vpp*
