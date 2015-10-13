# The README for the MCell Quick Reference Guide

## Overview

The MCell Quick Reference Guide located at http://mcell.org/documentation/qrg
is generated with Sphinx (http://sphinx-doc.org/index.html) from
reStructuredText files.

## Dependencies

We will be assuming that you are using Debian or Ubuntu, but most of the
instructions should be fairly similar for CentOS or other distros.

Although it's entirely possible to install all the dependencies manually at the
system level, we will be installing most of the Python libraries with
virtualenv. This will minimize possible version conflicts and simplify life
considerably.

First, you will want to install pip for Python3:

    sudo apt-get install python3-pip

Then install virtualenv:

    sudo pip3 install virtualenv

Create a new virtual environment in the cloned mcell_qrg directory:

    cd mcell_qrg
    virutalenv .

Activate it:

    source bin/activate

Install sphinx and other necessary python libraries:

    pip3 install -r requirements.txt

If you want to build the pdf, you'll want to install the following latex
utilities by typing this command:

    sudo apt-get install -y texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended

## Build the Guide

To build the html version, use this command:

    make html

To build the PDF version, use this command:

    make latexpdf
    
## Other Notes on Virtualenv

The virtual environment can be disabled like this:

    deactivate

It can later be reactivated by using the activate command as was done earlier:

    source bin/activate

## Learn More about Sphinx

Here are some instructions for new developers who want to contribute
to the QRG but are unfamiliar with ReST and Sphinx:

* Read this page to develop a basic understanding of ReST syntax:
  http://sphinx-doc.org/rest.html
    * The official "quick start" guide:
      http://docutils.sourceforge.net/docs/user/rst/quickstart.html
    * The official ReST reference guide:
      http://docutils.sourceforge.net/docs/user/rst/quickref.html
    * Sphinx specific syntax: http://sphinx-doc.org/markup/index.html
* Follow this tutorial, which will briefly explain how Sphinx projects work:
  http://sphinx-doc.org/tutorial.html
* The current implementation of the QRG uses a lot of grid tables which can be
  difficult to edit out of the box with some text editors. Here are some
  suggestions.
    * Vim
        * The vim-rst-tables plugin can be very useful, although it sometimes
          behaves oddly.
        * Consider setting one of the following options
            * set ve=block
            * set ve=all
