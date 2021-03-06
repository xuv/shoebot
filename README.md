Shoebot
=======

Shoebot is a Python graphics robot: It takes a Python script as input, which describes a drawing process, and outputs a graphic in a common open standard format (SVG, PDF, PostScript, or PNG). It works through simple text files, and scripts can describe their own GUIs for controlling variables interactively. It can also be used as a Python module, a plugin for Python-scriptable tools such as Inkscape, and run from the command line. 

Shoebot is a port/rewrite of [Nodebox 1](http://nodebox.net/code/index.php/Home). It was also inspired by [DrawBot](http://drawbot.com) and [Shoes](http://shoesrb.com/). Thus, "Shoebot".

What you need
-------------

Shoebot runs on Python 2.7, which is most probably what you already have installed.

First thing is to install the appropriate dependencies. If this is your first time using Shoebot, you'll want to install all of them:

Debian/Ubuntu:

    sudo apt-get install libjpeg-dev python-cairo python-gtk2 python-gobject python-gtksourceview2 python-rsvg

Fedora:

    sudo yum install libjpeg-devel pycairo pygtk2 pygobject2 gnome-python2-rsvg

OSX:

With MacPorts (http://www.macports.org) and python2.5

    sudo port install py25-numpy -atlas
    sudo port install pango +quartz
    sudo port install librsvg py25-pil py25-cairo py25-gtk

MacPorts does not have the python-rsvg package, so svg output won't work.
TODO: probably installing py26 packages and gnome-python-desktop would fix the missing python-rsvg problem.

Installing Shoebot
------------------

For now, the only means of installing Shoebot is getting it from the source repository. Shoebot uses Git for version control. It's available on most major GNU/Linux distributions; fire up your terminal and type:

Ubuntu/Debian:

    sudo apt-get install git

Fedora:

    sudo yum install git

Gentoo:

    emerge git

OSX:

    sudo port install git-core

Make a temporary directory to download all source files into, and then get the source itself.

    mkdir ~/src
    cd ~/src
    git clone git@github.com:shoebot/shoebot.git

You should now see a new shoebot/ directory. The only remaining step is to install it proper:

    cd shoebot
    sudo python setup.py install

OSX:

    cd shoebot
    sudo /opt/local/bin/python2.5 setup.py install


Running Shoebot from the console
--------------------------------

Using the Shoebot console runner is straightforward:

    sbot inputfile.bot

This command will run the 'inputfile.bot' script, and create an output image
file (output.svg). You'll want to specify your own filename, which can be
done like so:

    sbot inputfile.bot -o image.png

The allowed extensions for the output filename are .svg, .ps, .pdf and .png.

You can find many example Shoebot scripts in `/usr/share/shoebot/examples`.

Shoebot can also run in a window, which is useful for quick previews, as well
as realtime manipulation of parameters. For this, just use the window flag:

    sbot -w inputfile.bot

For a list of extra options, type

    sbot -h


Documentation
-------------

You can find the current docs at [ReadTheDocs](http://shoebot.readthedocs.org/).

Shoebot documentation can also be generated locally using sphinx. First, install it::

    pip install sphinx

The following commands will output the HTML docs::
  
    cd doc
    make html 

The documentation should now be available in `doc/build`.


Further reading
---------------

For a great intro to the Nodebox/Shoebot language, be sure to check the Nodebox tutorials at http://nodebox.net/code/index.php/Tutorial .

The Shoebot documentation has quite a lot more information on what you can do with Shoebot, such as:

  * running Shoebot as a Python module
  * using the socketserver to have other programs control a Shoebot script
  * using Shoebot to generate images via a CGI script


Links
-----

  * Website:             http://shoebot.net
  * Documentation:       http://shoebot.readthedocs.org
  * Mailing lists:       http://tinkerhouse.net/shoebot/devel
  * Source browser:	     http://github.com/shoebot/shoebot
  * Bug tracker:         http://github.com/shoebot/shoebot/issues


License
-------

Copyright (C) 2007-2012 The Shoebot authors (Stuart Axon, Dave Crossland, Francesco Fantoni, Ricardo Lafuente, Sebastian Oliva)
Originally developed by Ricardo Lafuente with the support of the Piet Zwart Institute, Rotterdam.

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as
    published by the Free Software Foundation, either version 3 of the
    License, or (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.


