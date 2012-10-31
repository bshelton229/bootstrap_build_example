## Custom Bootstrap

An example project demonstrating a way of creating a bustom bootstrap build from
your own .less files without modifying upstream bootstrap. Bootstrap is included
as a git submodule.

#### System Requirements:
  * Ruby (at least 1.8.7)
  * Ruby Bundler ( gem install bundler )

#### Installation:

You'll need to make sure you've fetched bootstrap as a submodule in this project

    $ git submodule init
    $ git submodule update

Install the bundled gems

    $ bundle

Now to compile your custom bootstrap from less/bootstrap-build.less, simply run the rake task.

    $ rake build

Optionally, start a watcher to automatically re-compile when you change .less files

    $ rake watch

#### Usage:

Simply edit less/bootstrap-build.less to include different bootstrap modules. This file was copied from bootstrap/less/bootstrap.less.
Edit less/variables.less to change bootstarp configuration variables. This file is a direct copy of bootstrap/less/variables.less.

#### Reporting Bugs

Walk down to Bryan's cubicle and yell at him.
