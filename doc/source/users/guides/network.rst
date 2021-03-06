Using OpenStack Network
=======================

Before working with the Network service, you'll need to create a connection
to your OpenStack cloud by following the :doc:`connect` user guide. This will
provide you with the ``conn`` variable used in the examples below.

.. contents:: Table of Contents
   :local:

The primary resource of the Network service is the network.

List Networks
-------------

A **network** is an isolated `Layer 2 <https://en.wikipedia.org/wiki/Data_link_layer>`_
networking segment. There are two types of networks, project and provider networks.
Project networks are fully isolated and are not shared with other projects. Provider
networks map to existing physical networks in the data center and provide external
network access for servers. Only an OpenStack administrator can create provider
networks. Networks can be connected via routers.

.. literalinclude:: ../examples/network/list.py
   :pyobject: list_networks

Full example: `network resource list`_

List Subnets
------------

A **subnet** is a block of IP addresses and associated configuration state.
Subnets are used to allocate IP addresses when new ports are created on a
network.

.. literalinclude:: ../examples/network/list.py
   :pyobject: list_subnets

Full example: `network resource list`_

List Ports
----------

A **port** is a connection point for attaching a single device, such as the
`NIC <https://en.wikipedia.org/wiki/Network_interface_controller>`_
of a server, to a network. The port also describes the associated network
configuration, such as the `MAC <https://en.wikipedia.org/wiki/Media_access_control>`_
and IP addresses to be used on that port.

.. literalinclude:: ../examples/network/list.py
   :pyobject: list_ports

Full example: `network resource list`_

List Security Groups
--------------------

A **security group** acts as a virtual firewall for servers. It is a container
for security group rules which specify the type of network traffic and direction
that is allowed to pass through a port.

.. literalinclude:: ../examples/network/list.py
   :pyobject: list_security_groups

Full example: `network resource list`_

List Routers
------------

A **router** is a logical component that forwards data packets between networks.
It also provides `Layer 3 <https://en.wikipedia.org/wiki/Network_layer>`_ and
`NAT <https://en.wikipedia.org/wiki/Network_address_translation>`_ forwarding to
provide external network access for servers on project networks.

.. literalinclude:: ../examples/network/list.py
   :pyobject: list_routers

Full example: `network resource list`_

Create Network
--------------

Create a project network and subnet. This network can be used when creating
a server and allows the server to communicate with others servers on the
same project network.

.. literalinclude:: ../examples/network/create.py
   :pyobject: create_network

Full example: `network resource create`_

Delete Network
--------------

Delete a project network and its subnets.

.. literalinclude:: ../examples/network/delete.py
   :pyobject: delete_network

Full example: `network resource delete`_

.. _network resource create: http://git.openstack.org/cgit/openstack/python-openstacksdk/tree/examples/network/create.py
.. _network resource delete: http://git.openstack.org/cgit/openstack/python-openstacksdk/tree/examples/network/delete.py
.. _network resource list: http://git.openstack.org/cgit/openstack/python-openstacksdk/tree/examples/network/list.py