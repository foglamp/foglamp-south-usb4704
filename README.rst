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
- By default the FogLAMP develop package header files and libraries
  are expected to be located in /usr/include/foglamp and /usr/lib/foglamp
- If **FOGLAMP_ROOT** env var is set and no -D options are set,
  the header files and libraries paths are pulled from the ones under the
  FOGLAMP_ROOT directory.
  Please note that you must first run 'make' in the FOGLAMP_ROOT directory.

You may also pass one or more of the following options to cmake to override 
this default behaviour:

- **FOGLAMP_SRC** sets the path of a FogLAMP source tree
- **FOGLAMP_INCLUDE** sets the path to FogLAMP header files
- **FOGLAMP_LIB sets** the path to FogLAMP libraries
- **FOGLAMP_INSTALL** sets the installation path of Random plugin

NOTE:
 - The **FOGLAMP_INCLUDE** option should point to a location where all the FogLAMP 
   header files have been installed in a single directory.
 - The **FOGLAMP_LIB** option should point to a location where all the FogLAMP
   libraries have been installed in a single directory.
 - 'make install' target is defined only when **FOGLAMP_INSTALL** is set

Examples:

- no options

  $ cmake ..

- no options and FOGLAMP_ROOT set

  $ export FOGLAMP_ROOT=/some_foglamp_setup

  $ cmake ..

- set FOGLAMP_SRC

  $ cmake -DFOGLAMP_SRC=/home/source/develop/FogLAMP  ..

- set FOGLAMP_INCLUDE

  $ cmake -DFOGLAMP_INCLUDE=/dev-package/include ..
- set FOGLAMP_LIB

  $ cmake -DFOGLAMP_LIB=/home/dev/package/lib ..
- set FOGLAMP_INSTALL

  $ cmake -DFOGLAMP_INSTALL=/home/source/develop/FogLAMP ..

  $ cmake -DFOGLAMP_INSTALL=/usr/local/foglamp ..
