.. _installation:

Installation
============

.. sectionauthor:: Georg Richter <georg@mariadb.com>

Prerequisits
------------

- Python 3 (minimum supported version is 3.6)
- MariaDB Server 10.x or MySQL Server
- MariaDB Connector/C 3.1.5 or newer

:: _build-prerequisits:

Build prerequisits
^^^^^^^^^^^^^^^^^^

The build prerequisits are required if you MariaDB Connector/C will be
installed from source distribution package or github.

- C compiler
- Python development files (Usually they are installed with package **python-dev**).
- MariaDB Connector/C libraries and header files (Either from MariaDB server package or
  from MariaDB Connector/C package).
- For Posix systems: TLS libraries, e.g. GnuTLS or OpenSSL (default)

On Posix system make sure that the path environment variable contains the directory which
contains the mariadb_config utility.

Once everything is in place, run

.. code-block:: console

    $ pip3 install -pre mariadb

or if you downloaded the source package

.. code-block:: console

    $ python setup.py build
    $ python setup.py install

Binary installation
-------------------
MariaDB Connector/Python is also available from PyPi as wheel packages for Windows.
These binary packages are not intended for production use, since there might be several limitations
and bottlenecks, e.g.:

- Dynamic MariaDB plugins (e.g. authentication plugins) are not part of the package and must
  be installed separetly by installing MariaDB Connector/C or MariaDB Server package.

Make sure you have an up to date version of pip and install it with

.. code-block:: console

    $ pip3 install -pre mariadb

Test suite
----------

If you have installed the sources, after successful build you can run the test suite
from the source directory.

.. code-block:: console

    $ python -m unittest discover -v

You can configure the connection parameters by using the following environment variables

* TEST_USER (default root)
* TEST_PASSWORD
* TEST_DATABASE (default 'testp')
* TEST_HOST (default 'localhost')
* TEST_PORT (default 3306)
