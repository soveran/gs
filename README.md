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
video](http://vimeo.com/soveran/gs). Note that this tool was renamed
to `gemset`. The other tool showcased in the screencast is
[dep](http://twpil.github.com/dep/), a dependency tracker.

## Usage

This library provides a command line application called `gemset`. These
are the available options:

### gemset init

Creates the $PWD/.gs directory.

### gemset help

Displays the documentation.

### gemset [command]

When called with no arguments, it starts a shell session and
configures the variables GEM_HOME, GEM_PATH and PATH to point to the
$PWD/.gs directory. In addition, it sets the GS_NAME variable with the
name of the current gemset (useful for PS1).

When called with arguments other than init or help, it will execute
command in a gemset shell session and return to the parent session once
finished.

## Getting started

First, grab the gem:

      $ gem install gemset

Next, type `gemset init` within your project and then just `gemset` to start
the subshell. The environment variables used by RubyGems will now
point to the `.gs` directory, and every gem you install, every gem you
remove, will use that path.

### Alternatives

There are some tools that provide a similar functionality and can
be used as a drop in replacement for `gemset`. Here are two
outstanding alternatives:

#### [gst](https://github.com/tonchis/gst)

This is a bash implementation that modifies the existing
environment instead of creating a subshell.

#### [bs](https://github.com/educabilia/bs)

This is a manager for environment variables written in bash. It
takes a different and very interesting approach.
