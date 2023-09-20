Configuration
=============

.. include:: ../note.rst

.. note::
  For the debian package, just edit the ``/etc/slidge/conf.d/common.conf`` and
  ``/etc/slidge/*.conf`` files, and use :ref:`Debian packages (systemd)` to
  launch slidge.

By default, slidge uses all config files found in ``/etc/slidge/conf.d/*``.
You can change this using the ``SLIDGE_CONF_DIR`` env var, eg
``SLIDGE_CONF_DIR=/path/dir1:/path/dir2:/path/dir3``.

It is recommended to use ``/etc/slidge/conf.d/`` to store configuration options
common to all slidge components (eg, attachment handling, logging options,
etc.), and to specify a plugin-specific file on startup, eg:

.. code-block:: bash

    slidge -c /etc/slidge/superduper.conf

Common config
-------------

.. argparse::
   :module: slidge.__main__
   :func: get_parser
   :prog: slidge
