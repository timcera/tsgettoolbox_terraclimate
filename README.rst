.. image:: https://img.shields.io/coveralls/github/timcera/tsgettoolbox_terraclimate
    :alt: Test Coverage
    :target: https://coveralls.io/r/timcera/tsgettoolbox_terraclimate?branch=master
    :height: 20

.. image:: https://img.shields.io/pypi/v/tsgettoolbox_terraclimate
    :alt: Latest release
    :target: https://pypi.python.org/pypi/tsgettoolbox_terraclimate/
    :height: 20

.. image:: https://img.shields.io/pypi/l/tsgettoolbox_terraclimate
    :alt: BSD-3 clause license
    :target: https://pypi.python.org/pypi/tsgettoolbox_terraclimate/
    :height: 20

.. image:: https://img.shields.io/pypi/pyversions/tsgettoolbox_terraclimate
    :alt: PyPI - Python Version
    :target: https://pypi.org/project/tsgettoolbox_terraclimate/
    :height: 20

tsgettoolbox_terraclimate - Quick Guide
=======================================
The 'tsgettoolbox_terraclimate' is a plugin-in for 'tsgettoolbox' that supplies
a command line interface and Python library to get time-series data from the
Terraclimate project.  The tsgettoolbox_terraclimate will work with
Python 3.10+.

Documentation
-------------
Reference documentation is at `tsgettoolbox_documentation`_.

Installation
------------
At the command line::

    $ pip install tsgettoolbox_terraclimate

    OR

    $ conda install -c conda-forge tsgettoolbox_terraclimate

Usage Summary - Command Line
----------------------------
Just run 'tsgettoolbox --help' to get a list of subcommands.  To get detailed
help for a particular sub-command, for instance 'terraclimate', type 'tsgettoolbox
terraclimate --help'.

+----------------------+---------+--------+---------+----------+-----------------------+
| Sub-command          | Spatial | Time   | Type    | Time     | Description           |
|                      | Extent  | Extent |         | Interval |                       |
+======================+=========+========+=========+==========+=======================+
| terraclimate         | global  | varies | grid    | M        | Monthly data from     |
|                      |         |        | 1/24deg |          | TerraClimate          |
+----------------------+---------+--------+---------+----------+-----------------------+
| terraclimate19812010 | global  | varies | grid    | M        | Monthly normals using |
|                      |         |        | 1/24deg |          | TerraClimate monthly  |
|                      |         |        |         |          | data from 1981 to     |
|                      |         |        |         |          | 2010                  |
+----------------------+---------+--------+---------+----------+-----------------------+
| terraclimate19912020 | global  | varies | grid    | M        | Monthly normals using |
|                      |         |        | 1/24deg |          | TerraClimate monthly  |
|                      |         |        |         |          | data from 1991 to     |
|                      |         |        |         |          | 2020                  |
+----------------------+---------+--------+---------+----------+-----------------------+

+-------------------+-------------+
| Time Interval     | Description |
| Code              |             |
+===================+=============+
| M                 | Monthly     |
+-------------------+-------------+

Usage Summary - Python Library
------------------------------
To use the tsgettoolbox in a project::

    from tsgettoolbox import tsgettoolbox
    df = tsgettoolbox.terraclimate(29.6, -82.3, variables=["tmin", "tmax", "ppt"])
    print(df.head())

Refer to the API Documentation at `tsgettoolbox_api`_.

Usage Summary - Command Line
----------------------------

    tsgettoolbox terraclimate19812010 \
        29.6 \
        -82.3 \
        --variables=["tmin", "srad"] > output.csv

Refer to the command line documentation at `tsgettoolbox_cli`_.

Development
~~~~~~~~~~~
Development is managed on bitbucket or github.
https://bitbucket.org/timcera/tsgettoolbox_terraclimate/overview.
https://github.com/timcera/tsgettoolbox_terraclimate

.. _tsgettoolbox_documentation: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/index.html
.. _tsgettoolbox_api: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/function_summary.html
.. _tsgettoolbox_cli: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/command_line.html
