mksite - static website generator
================================

mksite is a simple static website generator that uses markdown and a
linux directory structure to generate and maintain a website. It is
designed to be simple and convenient. The main idea is to be able to
build a website simply by creating directories and markdown files in
linux after which the output can be rsynced to the server. 

This code was originally copied from genosite at suckless.org (see:
http://hg.suckless.org/genosite/) and uses some of the ideas from
poole (see: http://bitbucket.org/obensonne/poole/src). If you need a
more robust website generator consider hyde (http://ringce.com/hyde).

Quick Start
===========

Run initsite <project dir> to build a new project directory. In this
project directory you will find a directory called input with some
markdown files, a css style file, and a subdirectory in it. Edit these
(and add more) to your liking. This is where you build your site; do
all of your work here (adding folders, files etc...). The site name
and footer are edited by changing config.conf in the project
directory.

Now run mksite <project dir>

This will create a folder called output in the project directory. This
contains the actual website and auxiliary files and folders created in
input. If you want to create a "hidden" folder to keep images or data
files in then use the standard linux naming convention
(e.g. .hidden). The mksite program will not add these folders to the
site menu. Anytime you update the input folder run mksite <proj-dir>
to update the output folder. If you delete files in input they will be
removed from output because mksite uses rsync to create the output
folder.

TODO
====

Add footer input...

At this point there is no easy way to edit the raw html page structure
without editing the mksite script. This isn't hard to do but it would
be nicer to use a method like poole which allows the user to edit some
basic html skeleton.

Dependencies
============
* bash
* rsync
* python-markdown
* sed
* gawk

