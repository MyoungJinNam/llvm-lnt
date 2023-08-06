LLVM "Nightly Test" Infrastructure
==================================

This directory and its subdirectories contain the LLVM nightly test
infrastructure. This is technically version "4.0" of the LLVM nightly test
architecture.

The infrastructure has the following layout:

 $ROOT/lnt - Top-level Python 'lnt' module

 $ROOT/lnt/server/db - Database schema, utilities, and examples of the LNT plist format.

 $ROOT/docs - Sphinx documentation for LNT.

 $ROOT/tests - Tests for the infrastructure.

For more information, see the web documentation, or docs/.

Testing
=======

Testing is done by running tox from the top-level directory. It runs the tests
for both Python 2 and Python 3, it also checks code style.

Installation/M1/MacOS
======================

- Check if pip, virtualenv are installed  
    currently used: /opt/homebrew/bin/virtualenv

- Install virtualenv, if not installed 
    pip install virtualenv
    NOTE: Use python in /opt/homebrew/opt/ blibli!

- Create sandbox. 
    virtualenv <path/to/sandbox>
    Currently path=~/tools/clangllvm/sandbox.lnt

- Checkout the LNT sources
    Currently ~/tools/clangllvm/LNT 

- Install LNT into the virtual environment:
    cd /path/to/sandbox &&
    source ./activate &&
    ./python -m pip install /relative/path/to/lnt 
    
    Note: error --> python ~/tools/clangllvm/LNT/setup.py develop
    ref: https://github.com/GNS3/gns3-server/issues/2013

- Test if lnt is install in sandbox.lnt
    /path/to/sandbox.lnt/bin/lnt runtest test_suite --help
