========================================================================
Advantech USB-4704 Portable Data Acquisition Module C/C++ South plugin 
========================================================================

NOTE:

This plugin requires the Advantech BIODAQ library. This has no standard install
location, therefore you must set the environment variable BIODAQDIR to the location
in whch you installed this.

Build
-----
To build usb4704 plugin with given `requirements.sh <requirements.sh>`_ or the following commands:

.. code-block:: console

  $ export BIODAQDIR=...
  $ mkdir build
  $ cd build
  $ cmake ..
  $ make

- The environment variable BIODAQDIR should be pointed at the directory
  that has the libs and include subdirectoy from the USB-4704 SDK_driver
  downloaded from the Advantech support website.
  http://downloadt.advantech.com/download/downloadsr.aspx?File_Id=1-1N61WCN
  E.g. If you downloaded this file to yout home directory run
  export BIODAQDIR=~/DAQNavi_Linux/SDK_Drivers/linux_driver_source_3.2.8.0_64bit
- By default the Fledge develop package header files and libraries
  are expected to be located in /usr/include/fledge and /usr/lib/fledge
- If **FLEDGE_ROOT** env var is set and no -D options are set,
  the header files and libraries paths are pulled from the ones under the
  FLEDGE_ROOT directory.
  Please note that you must first run 'make' in the FLEDGE_ROOT directory.

You may also pass one or more of the following options to cmake to override 
this default behaviour:

- **FLEDGE_SRC** sets the path of a Fledge source tree
- **FLEDGE_INCLUDE** sets the path to Fledge header files
- **FLEDGE_LIB sets** the path to Fledge libraries
- **FLEDGE_INSTALL** sets the installation path of Random plugin

NOTE:
 - The **FLEDGE_INCLUDE** option should point to a location where all the Fledge 
   header files have been installed in a single directory.
 - The **FLEDGE_LIB** option should point to a location where all the Fledge
   libraries have been installed in a single directory.
 - 'make install' target is defined only when **FLEDGE_INSTALL** is set

Examples:

- no options

  $ cmake ..

- no options and FLEDGE_ROOT set

  $ export FLEDGE_ROOT=/some_fledge_setup

  $ cmake ..

- set FLEDGE_SRC

  $ cmake -DFLEDGE_SRC=/home/source/develop/Fledge  ..

- set FLEDGE_INCLUDE

  $ cmake -DFLEDGE_INCLUDE=/dev-package/include ..
- set FLEDGE_LIB

  $ cmake -DFLEDGE_LIB=/home/dev/package/lib ..
- set FLEDGE_INSTALL

  $ cmake -DFLEDGE_INSTALL=/home/source/develop/Fledge ..

  $ cmake -DFLEDGE_INSTALL=/usr/local/fledge ..
