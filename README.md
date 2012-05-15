# Make your life easier with gemsets

We have all become familiar with the concept of gemsets. They
come in different shapes and sizes, and provide isolation
for project dependencies. Some of the libraries that
implement gemsets are [rip](https://github.com/defunkt/rip),
[RVM](https://rvm.beginrescueend.com/gemsets/) and
[rbenv-gemset](https://github.com/jamis/rbenv-gemset).

This library recreates the absolutely minimal feature set for creating
and using gemsets.

## Introductory screencast

If you want to see this workflow in action, [check the introductory
video](http://vimeo.com/soveran/gs). The other tool showcased in the
screencast is [dep](http://twpil.github.com/dep/), a dependency
tracker.

## Usage

This library provides a command line application called `gs`. These
are the available options:

### gs init

Creates the $PWD/.gs directory.

### gs help

Displays the documentation.

### gs [command]

When called with no arguments, it starts a shell session and
configures the variables GEM_HOME, GEM_PATH and PATH to point to the
$PWD/.gs directory. In addition, it sets the GS_NAME variable with the
name of the current gemset (useful for PS1).

When called with arguments other than init or help, it will execute
command in a gs shell session and return to the parent session once
finished.

## Getting started

First, grab the gem:

      $ gem install gs

Next, type `gs init` within your project and then just `gs` to start
the subshell. The environment variables used by RubyGems will now
point to the `.gs` directory, and every gem you install, every gem you
remove, will use that path.
