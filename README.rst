devpi buildout
==============

This buildout sets up `devpi-server`_.
It will run on ``http://localhost:8141``.

On OS X you can symlink ``etc/devpi-server.plist`` into ``~/Library/LaunchAgents/`` with::

  ln -s $(pwd)/etc/devpi-server.plist ~/Library/LaunchAgents/

and then use::

  launchctl load -w ~/Library/LaunchAgents/devpi-server.plist

to let it run automatically.

On systems with cron you can also use the line generated in ``etc/crontab.devpid``

.. _`devpi-server`: http://devpi.net

Install
-------

Create a ``buildout.cfg`` file with your configuration extended from
``devpi.cfg``::

    $ vim devpi.cfg
    [buildout]
    extends = devpi.cfg

    [devpi]
    data-dir = /dev/shm/devpi

Now you're ready to execute buildout::

    virtualenv .
    bin/python bootstrap.py
    bin/buildout

Run
---

You may run the whole server with supervisor, use::

    bin/devpid

to start and ``bin/devpictl`` to control the instance.

