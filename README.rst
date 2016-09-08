OXID eShop database migration integration
=========================================

Current component allows to execute and create database migration scripts.

The paths that will be used for migration scripts are provided by:
`eshop-migration_facts <https://github.com/OXID-eSales/eshop-migration_facts>`__

Current component provides the following scripts:

* ``oe-eshop-db_generate_migration`` - create new migration script;
* ``oe-eshop-db_migrate`` - execute migration process.

In order to execute the scripts above use them with
`eshop-facts <https://github.com/OXID-eSales/eshop-facts>`__, e.g.

``./vendor/bin/oe-eshop-facts oe-eshop-db_migrate``

OXID eShop database migration integration related facts
=======================================================

This component provides eShop database migration integration facts with the help
of `eshop-facts <https://github.com/OXID-eSales/eshop-facts>`__. Information
on how to use ``oe-eshop-db_migration_facts`` script together with
``oe-eshop-facts`` can be found in the following
`README <https://github.com/OXID-eSales/eshop-facts/blob/master/README.rst>`__.

Output
------

The following information is provided after executing the script:

* ``DOCTRINE_MIGRATION_WRAPPER_SUFFIX`` - Name of the doctrine migration wrapper
  component within composer vendor path, i.e.
  ``vendor/<oxid_esales_vendor>/<doctrine_migration_wrapper_suffix>/``.

Keep in mind that it's possible to override any variable from the list above
by providing it as an environment variable, e.g. to change the doctrine
migration wrapper suffix:

``DOCTRINE_MIGRATION_WRAPPER_SUFFIX=custom-doctrine-migration-wrapper ./vendor/bin/oe-eshop-facts oe-eshop-db_migration_facts``

Input
-----

The following environment variables are accepted:

* ``VERBOSE`` - Enables verbose mode which prints out all facts to ``STDOUT``;
* ``ESHOP_VERBOSE_DB_MIGRATION_FACTS`` - Enables verbose mode only for the
  current script.
