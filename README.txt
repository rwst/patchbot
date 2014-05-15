The patchbot only needs a Sage install and is started with

    python patchbot.py [options]

Type --help for a list of options, though most configuration is done via an
optional JSON config file. This is what is invoked by sage --patchbot [...]

The server needs a Python with Flask and mongod installed.  Installing numpy
and PIL will allow multi-colored blurbs.  Start a monitoring loop with

    python run_server.py

Currently, the server is set up to run on port 21100, communicating with
a mongod instance running on 21002.

--------------------------------------------------------
This is a fork of the original patchbot by robertwb, version 2.1.1.1.
It has the following changes versus that version:

* scoring changes by vbraun
* use git:// URIs instead of http(s)://
* tickets with changes in src/doc no longer considered unsafe
* do not check tickets with open dependencies
* before make, make doc-clean
* --safe-only option to only test 'safe' tickets
* --keep-tmp option to not remove /tmp build directories
