## Custom Bootstrap

An example project demonstrating a way of creating a bustom bootstrap build from
your own .less files without modifying upstream bootstrap. Bootstrap is included
as a git submodule.

#### System Requirements:
  * node.js
  * The less node.js module (installed via npm -g)
  * A moderately new version of Ruby, for the rake command

#### Installation:

You'll need to make sure you've fetched bootstrap as a submodule in this project

    $ git submodule init
    $ git submodule update

You'll need node.js and npm (included in recent node.js versions) installed. This command will install the node.js less package.

**NOTE**: This command may need to be run with sudo, depending on your set up.

    $ npm -g install less

Now to compile your custom bootstrap from less/bootstrap-build.less, simply run the rake task.

    $ rake build

#### Usage:

Simply edit less/bootstrap-build.less to include different bootstrap modules. This file was copied from bootstrap/less/bootstrap.less.
Edit less/variables.less to change bootstarp configuration variables. This file is a direct copy of bootstrap/less/variables.less.

#### Reporting Bugs

Walk down to Bryan's cubicle and yell at him.
