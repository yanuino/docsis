Docsis utility
==============

This program encodes a DOCSIS binary configuration file from a human-readable text configuration file.

It is a fork of https://github.com/rlaager/docsis

This build is an experimental one and is based on a fork from the GitHub project. Please use this build on your own risk.

Changes
-------

### TODO
- Add copyright information
- Increment version

### 2024-11-06
- Merge branch "Add DigitMap keyword for intuitively inserting digit map (dial plan)" from [Richard Kung](https://github.com/richard-kung/docsis/)
- Add IETF hash option for encoding MTA file
- Fork from https://github.com/rlaager/docsis

Linux/Unix
----------

This was tested on Ubuntu 14.10, Fedora 21, openSUSE 13.2 (little endian) and Debian 7.5 Sparc64 (big endian) and it is known to work without issues.

Dependencies:

    Debian/Ubuntu:
    apt-get install automake libtool libsnmp-dev bison make gcc flex git libglib2.0-dev libfl-dev
    
    Fedore/RedHat/CentOS:
    yum install autoconf automake libtool glib2-devel bison flex net-snmp-devel
    
    openSUSE/SLES:
    zypper install autoconf automake libtool glib2-devel bison flex net-snmp-devel
    
    FreeBSD/OpenBSD/NetBSD
    pkg install automake autoconf bison flex gcc libtool glib net-snmp
    
Mac OS X
--------

Tested and working on OS X Mavericks. Dependencies should be installed using MacPorts:

    sudo port install autoconf automake libtool glib2-devel bison flex net-snmp

Windows
-------

Tested and working under Cygwin 2.0.2

Packages needed:

    automake libtool net-snmp-utils net-snmp-devel bison make gcc-g++ flex libglib2.0-devel
  

Installation steps
------------------

Follow the following steps to download and install the utility.

    git clone https://github.com/rlaager/docsis.git
    cd docsis
    ./autogen.sh
    ./configure
    make
    make install (optional)

Bug reporting
-------------

Please use the GitHub system to report feature request and bugs.

Known issues
------------

Quoting the hex strings will result in a crash. Known workaround is to not quote HEX definitions.  
  
There are compilation problems on old gcc variants, you should get an error similar to: docsis.c: multiple definition of `main'. Known workaround is to upgrade to a newer version of gcc.  

If you want to encode as string something similar to ""value"" you need to escape the extra characters. Config file value should look like "\"value\"".