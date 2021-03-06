Introduction to yara-ctypes-python
**********************************

What's in yara-ctypes:

* A ctypes libyara wrapper module which exposes libyara's exports into the
  Python runtime (see: `yara-project's libyara v1.7`_).
* A thread safe Rules object with an interface that is compatible with the
  interface exposed in the yara-project CPython extension module.
* namespace management to allow easy loading of multiple YARA rules into a
  single Rules matching object. 
* Various Scanner class types to enable thread or process pool execution
  of matching requests over a Rules object.
* A feature rich command line interface that gives the user many options to
  control how they may wish to perform a scan.  


Why:

* ctypes releases the GIL on system function calls...  Run your PC to its
  true potential.
* It simplifies things a lot by keeping high order logic such as managing rules
  paths, filtering paths, controlling pooled execution, etc. inside of a
  language such as Python.
* No more building the PyC extension...  
* I found a few bugs and memory leaks and wanted to make my life simple.


As a reference and guide to yara-ctypes see: `yara-ctypes documentation`_


For additional tips / tricks with this wrapper feel free to post a question at 
the github `yara-ctypes/issues`_ page. 


Project hosting provided by `github.com`_.


[mjdorma+yara-ctypes@gmail.com]


Install and run
===============

Simply run the following::

    > python setup.py install
    > python setup.py test
    > yara-ctypes -h

or `PyPi`_:: 

    > pip install yara
    > yara-ctypes -h


.. note::

    If the package does not contain a pre-compiled libyara library for your
    platform you will need to build and install it. See `notes on building`_.


Compatability
=============

*yara-ctypes* is implemented to be compatible with Python 2.6+ and Python 3.x.
It has been tested against the following Python implementations:

Ubuntu 12.04:

 + CPython 2.7 (32bit, 64bit)
 + CPython 3.2 (32bit, 64bit)

Ubuntu 11.10 |build_status|:

 + CPython 2.6 (32bit)
 + CPython 2.7 (32bit)
 + CPython 3.2 (32bit)
 + CPython 3.3 (32bit) 

Windows 7:

 + CPython 2.6 (32bit, 64bit)
 + CPython 3.2 (32bit, 64bit)

OS X Mountain Lion

 + CPython 2.7 (64bit)


Continuous integration testing is provided by `Travis CI <http://travis-ci.org/>`_.


Issues
======

Source code for *yara-ctypes* is hosted on `GitHub <https://github.com/mjdorma/yara-ctypes>`_. 
Please file `bug reports <https://github.com/mjdorma/yara-ctypes/issues>`_
with GitHub's issues system.


Change log
==========

version 1.7.6 (26/10/2013)

* now using setuptools for distribution

version 1.7.5 (13/09/2013)

* added CLI status thread
* improved process and thread completion code

version 1.7.4 (12/09/2013)

* added yar preprocessor 
* fixed asynchronous counter bug
* solved the unyielded results issue

version 1.7.3 (28/04/2013)

* scan using a process pool or thread pool
* bug fixes and more testing

version 1.7.2 (19/04/2013)

* cli improvements
* bug fixes 

version 1.7.1 (17/04/2013)

* StdinScanner 
* overlap control for stream chunk enqueueing 

version 1.7.0 (15/04/2013)

* ships with builds of libyara-1.7 
* compatibility issues solves with yara-1.7's interface changes
* major change up and improvement to the scan command line interface. 
* a lot more testing

version 1.6.5 (12/04/2013)

* more tech in scan
* improved test
* bug fixes

version 1.6.4 (11/04/2013)

* supports py3.3 
* additional test
* improved scan interface 
* bug fixes

version 1.6.3 (08/03/2013)

* bug fix to yara.py (callback callable check)

version 1.6.2 (28/02/2013)

* support for OS X Mountain Lion

version 1.6.1 (06/09/2012)

* Support for 64bit Windows
* Bug fixes 
* Added documentation

version 1.6.0 (01/09/2012)

* Initial release


.. _github.com: https://github.com/mjdorma/yara-ctypes
.. _PyPi: http://pypi.python.org/pypi/yara
.. _yara-ctypes/issues: https://github.com/mjdorma/yara-ctypes/issues
.. _notes on building: http://packages.python.org/yara/howto/build.html
.. _yara-ctypes documentation: http://packages.python.org/yara/
.. _yara-project's libyara v1.7: http://code.google.com/p/yara-project
.. |build_status| image:: https://secure.travis-ci.org/mjdorma/yara-ctypes.png?branch=master
   :target: http://travis-ci.org/#!/mjorma/yara-ctypes
