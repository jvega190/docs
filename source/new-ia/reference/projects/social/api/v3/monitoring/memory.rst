:is-up-to-date: True
:nosearch:

.. _newIa-crafter-social-api-monitoring-memory:

================
Get Memory Stats
================

Returns the Crafter Social JVM memory details.

--------------------
Resource Information
--------------------

.. include:: /includes/social-api-url-prefix.rst

+----------------------------+-------------------------------------------------------------------+
|| HTTP Verb                 || GET                                                              |
+----------------------------+-------------------------------------------------------------------+
|| URL                       || ``/api/3/monitoring/memory``                                     |
+----------------------------+-------------------------------------------------------------------+
|| Response Formats          || ``JSON``                                                         |
+----------------------------+-------------------------------------------------------------------+

----------
Parameters
----------

+-------------------------+-------------+---------------+--------------------------------------+
|| Name                   || Type       || Required     || Description                         |
+=========================+=============+===============+======================================+
|| token                  || String     || |checkmark|  || The authorization token             |
+-------------------------+-------------+---------------+--------------------------------------+

-------
Example
-------

^^^^^^^
Request
^^^^^^^

``GET .../api/3/monitoring/memory.json?token=defaultManagementToken``

^^^^^^^^
Response
^^^^^^^^

``Status 200 OK``

.. code-block:: json
  :linenos:

  {
    "totalJvmMemory": 2017984512,
    "freeJvmMemory": 1113921056,
    "maxJvmMemory": 3817865216,
    "totalOsMemory": 17179869184,
    "freeOsMemory": 2669301760,
    "totalSwapMemory": 2147483648,
    "freeSwapMemory": 1026555904,
  }

---------
Responses
---------

+---------+------------------+--------------------------------------------------------------------+
|| Status || Location        || Response Body                                                     |
+=========+==================+====================================================================+
|| 200    ||                 || See example above.                                                |
+---------+------------------+--------------------------------------------------------------------+
|| 400    ||                 || {"error":"Required String parameter 'token' is not present",      |
||        ||                 ||  "message":"Required String parameter 'token' is not present"}    |
+---------+------------------+--------------------------------------------------------------------+
|| 401    ||                 || {"error":"Management authorization failed, invalid token.",       |
||        ||                 ||  "message":"Management authorization failed, invalid token."}     |
+---------+------------------+--------------------------------------------------------------------+
|| 500    ||                 || ``{ "message" : "Internal server error" }``                       |
+---------+------------------+--------------------------------------------------------------------+
