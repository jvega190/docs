:is-up-to-date: True
:last-updated: 4.0.3

.. _crafter-studio-api-security-get-user-permissions:

====================
Get User Permissions
====================

Get user permissions for site and space (path).

--------------------
Resource Information
--------------------

.. include:: /includes/studio-api-url-prefix.rst

+--------------------------+---------------------------------------------------------------------+
|| HTTP Verb               || GET                                                                |
+--------------------------+---------------------------------------------------------------------+
|| URL                     || ``/api/1/services/api/1/security/get-user-permissions.json``       |
+--------------------------+---------------------------------------------------------------------+
|| Response Formats        || ``JSON``                                                           |
+--------------------------+---------------------------------------------------------------------+
|| Required Role           ||                                                                    |
+--------------------------+---------------------------------------------------------------------+

----------
Parameters
----------

+---------------+-------------+---------------+--------------------------------------------------+
|| Name         || Type       || Required     || Description                                     |
+===============+=============+===============+==================================================+
|| site_id      || String     ||              || Site to use                                     |
+---------------+-------------+---------------+--------------------------------------------------+
|| path         || String     ||              || Path of the content                             |
+---------------+-------------+---------------+--------------------------------------------------+

-------
Example
-------

.. code-block:: none

	GET .../api/1/services/api/1/security/get-user-permissions.json?site_id=mysite&path=/site/website/style/index.xml

.. code-block:: json
  :linenos:

  {
      "permissions":
          [
              "create folder",
              "webdav_write",
              "read",
              "webdav_read",
              "create content",
              "s3 read",
              "write",
              "s3 write",

          ]
  }

--------
Response
--------

+---------+-------------------------------------------+---------------------------------------------------+
|| Status || Location                                 || Response Body                                    |
+=========+===========================================+===================================================+
|| 200    ||                                          || See example above.                               |
+---------+-------------------------------------------+---------------------------------------------------+
