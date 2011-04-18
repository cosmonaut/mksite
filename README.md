mksite - static website generator
================================

mksite is a simple static website generator that uses markdown and a
linux directory structure to generate and maintain a website. It is
designed to be simple and convenient. The main idea is to be able to
build a website simply by creating directories and markdown files in
linux. Then the output can be easily deployed to the server. 

This code was originally copied from
[genosite](http://hg.suckless.org/genosite/) at suckless.org and uses
some of the ideas from
[poole](http://bitbucket.org/obensonne/poole/src). If you need a more
robust website generator consider [hyde](http://hyde.github.com/).

Quick Start
===========

Run initsite (project dir name)

This builds a new project directory. In this project directory you
will find a directory called input with some markdown files, a css
style file, and a subdirectory in it. Edit these (and add more) to
your liking. This is where you build your site; do all of your work
here (adding folders, files etc...). The site name and footer are
edited by changing config.conf in the project directory.

Now run mksite (project dir)

This will create a folder called output in the project directory. This
contains the actual website and auxiliary files and folders created in
input. If you want to create a "hidden" folder to keep images or data
files in then use the standard linux naming convention
(e.g. .hidden). The mksite program will not add these folders to the
site menu. Anytime you update the input folder run mksite <proj-dir>
to update the output folder. If you delete files in input they will be
removed from output because mksite uses rsync to create the output
folder.

New changes with version 0.5

There are two new options that come with mksite. These are --rebuild
and --clean. The --clean option will remove any html files in output
that don't correspond to a markdown file in input. A cache is now used
to track changed files in mksite and reduce the generation time for
large sites. Now only files that have been changed since last
generated will be regenerated. The --rebuild option forces
regeneration of all markdown files and also forces an output directory
cleaning.

TODO
====

* Add config variables for extra header stuff

Dependencies
============
* bash
* rsync
* python-markdown
* sed
* gawk

