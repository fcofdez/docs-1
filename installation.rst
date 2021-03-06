.. _install:

Install
=======

To install the conan client you can use one of the provided installers, or run it
directly from source code 

Install the binaries
--------------------

Go to conan website and `download the installer for your platform <https://www.conan.io>`_!

Execute the installer. You don't need to install python.

Initial configuration
---------------------

Lets check that conan is correctly installed. Execute in your console:

.. code-block:: bash

   $ conan
   
You will see something similar to:

.. code-block:: bash

   It seems to be the first time you run conan
   Auto detecting your dev setup to initialize conan.conf
   Found Visual Studio 9
   Found Visual Studio 12
   Found Visual Studio 14
   Found gcc 4.8
   Found clang 3.7
   Default conan.conf settings
           os=Windows
           arch=x86_64
           compiler=Visual Studio
           compiler.version=14
           compiler.runtime=MD
           build_type=Release
   *** You can change them in ~/.conan/conan.conf ***
   *** Or override with -s compiler='other' -s ...s***

As it says, it does a basic detection of your installed tools and saves it in the **conan.conf**
file (under your user home directory **~/.conan/conan.conf**). This auto-detected settings are
just a convenience and act as a default for your conan commands. You can change them at any time in such file or
override them in your commands with new values. You can also delete them from **conan.conf**, so
you will have to fully specify them for new projects.


Install from source
-------------------

You can run conan directly from source code. First you need to install Python 2.7 and pip.

Clone (or download and unzip) the git repository and install its requirements:

.. code-block:: bash

    ~$/ git clone
    ~$/ cd conan
    ~$/ pip install -r requirements.txt

Create an script to execute conan and add it to your ``PATH``.

.. code-block:: text

    #!/usr/bin/env python

    import sys

    conan_repo_path = "/home/your_user/conan" # ABSOLUTE PATH TO CONAN REPOSITORY FOLDER

    sys.path.append(conan_repo_path)
    from packet.client.command import main
    main(sys.argv[1:])

Test your ``conan`` script.

.. code-block:: bash

    ~$/ conan

You should see the conan commands help