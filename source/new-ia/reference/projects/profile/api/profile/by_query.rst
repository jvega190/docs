:is-up-to-date: True
:nosearch:

.. _newIa-crafter-profile-api-profile-by_query:

=====================
Get Profiles By Query
=====================

Returns the profiles that match the specified query.

--------------------
Resource Information
--------------------

.. include:: /includes/profile-api-url-prefix.rst

+----------------------------+-------------------------------------------------------------------+
|| HTTP Verb                 || GET                                                              |
+----------------------------+-------------------------------------------------------------------+
|| URL                       || ``/api/1/profile/by_query``                                      |
+----------------------------+-------------------------------------------------------------------+
|| Response Formats          || ``JSON``                                                         |
+----------------------------+-------------------------------------------------------------------+

----------
Parameters
----------

+---------------------+---------+---------------+--------------------------------------------------+
|| Name               || Type   || Required     || Description                                     |
+=====================+=========+===============+==================================================+
|| accessTokenId      || String || |checkmark|  || The access token ID of the application          |
||                    ||        ||              || making the call                                 |
+---------------------+---------+---------------+--------------------------------------------------+
|| tenantName         || String || |checkmark|  || The tenant's name                               |
+---------------------+---------+---------------+--------------------------------------------------+
|| query              || String || |checkmark|  || The Mongo query used to search for the profiles |
+---------------------+---------+---------------+--------------------------------------------------+
|| sortBy             || String ||              || Profile attribute to sort the list by           |
+---------------------+---------+---------------+--------------------------------------------------+
|| sortOrder          || String ||              || The sort order (either ASC or DESC)             |
+---------------------+---------+---------------+--------------------------------------------------+
|| start              || String ||              || From the entire list of results, the position   |
||                    ||        ||              || where the actual results should start (useful   |
||                    ||        ||              || for pagination)                                 |
+---------------------+---------+---------------+--------------------------------------------------+
|| count              || String ||              || The number of profiles to return                |
+---------------------+---------+---------------+--------------------------------------------------+
|| attributesToReturn || String ||              || The name of the attributes to return            |
||                    ||        ||              || (don't specify to return all)                   |
+---------------------+---------+---------------+--------------------------------------------------+

.. WARNING::
  The query must not contain the ``$where`` operator, the tenant's name (already specified) or any non-readable attribute by the application

-------
Example
-------

^^^^^^^
Request
^^^^^^^

.. code-block:: none

  GET .../api/1/profile/by_query?accessTokenId=e8f5170c-877b-416f-b70f-4b09772f8e2d&tenantName=sample-tenant&query=%7B%20%22username%22%3A%20%22john.doe%22%20%7D

^^^^^^^^
Response
^^^^^^^^

``Status 200 OK``

.. code-block:: json
  :linenos:

  [
  	{
  		"username": "john.doe",
  		"email": "john.doe@example.com",
  		"verified": false,
  		"enabled": false,
  		"createdOn": 1495748091232,
  		"lastModified": 1495748091232,
  		"tenant": "sample-tenant",
  		"roles": [],
  		"attributes": {},
  		"id": "59274dfbd4c650e226b03b65"
  	}
  ]

---------
Responses
---------

+---------+--------------------------------+-----------------------------------------------------+
|| Status || Location                      || Response Body                                      |
+=========+================================+=====================================================+
|| 200    ||                               || See example above.                                 |
+---------+--------------------------------+-----------------------------------------------------+
|| 500    ||                               || ``{ "message" : "Internal server error" }``        |
+---------+--------------------------------+-----------------------------------------------------+
