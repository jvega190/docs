:is-up-to-date: True
:last-updated: 4.0.0

.. _crafter-deployer-api-target-deploy-all:

==================
Deploy All Targets
==================

Deploy all Crafter Deployer targets.

--------------------
Resource Information
--------------------

.. include:: /includes/deployer-api-url-prefix.rst

+----------------------------+-------------------------------------------------------------------+
|| HTTP Verb                 || POST                                                             |
+----------------------------+-------------------------------------------------------------------+
|| URL                       || ``/api/1/target/deploy-all``                                     |
+----------------------------+-------------------------------------------------------------------+
|| Response Formats          || ``JSON``                                                         |
+----------------------------+-------------------------------------------------------------------+

----------
Parameters
----------

.. list-table::
   :widths: 20 10 12 50
   :header-rows: 1

   * - Name
     - Type
     - Required
     - Description
   * - reprocess_all_files
     - Boolean
     -
     - If all files in all the target repos should be reprocessed.
   * - deployment_mode

       .. version_tag::
          :label: Since
          :version: 4.0.0

     - String
     -
     - The deployment mode to execute. Possible values: |br|
       ``PUBLISH``: All processors will run |br|
       ``SEARCH_INDEX``: Only the indexing processor will run

-------
Example
-------

^^^^^^^
Request
^^^^^^^

``POST .../api/1/target/deploy-all``

.. code-block:: json

  {
    "reprocess_all_files": false
  }

^^^^^^^^
Response
^^^^^^^^

``Status 202 OK``

---------
Responses
---------

+---------+----------------------------------+---------------------------------------------------+
|| Status || Location                        || Response Body                                    |
+=========+==================================+===================================================+
|| 202    ||                                 || See example above                                |
+---------+----------------------------------+---------------------------------------------------+
|| 500    ||                                 || ``{ "message" : "Internal server error" }``      |
+---------+----------------------------------+---------------------------------------------------+
