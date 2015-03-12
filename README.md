Laptop
======

Laptop is a script to set up an OS X laptop for web development.

It can be run multiple times on the same machine safely.
It installs, upgrades, or skips packages
based on what is already installed on the machine.

Requirements
------------

We support:

* [OS X Mavericks (10.9)](https://itunes.apple.com/us/app/os-x-mavericks/id675248567)
* [OS X Yosemite (10.10)](https://www.apple.com/osx/)

Older versions may work but aren't regularly tested. Bug reports for older
versions are welcome.

Install
-------

Download, review, then execute the script:

```sh
curl --remote-name https://raw.githubusercontent.com/ajmaddaford/laptop/master/mac
less mac
sh mac 2>&1 | tee ~/laptop.log
```

Debugging
---------

Your last Laptop run will be saved to `~/laptop.log`. Read through it to see if
you can debug the issue yourself. If not, copy the lines where the script
failed into a [new GitHub
Issue](https://github.com/thoughtbot/laptop/issues/new) for us. Or, attach the
whole log file as an attachment.

What it sets up
---------------

* [Homebrew] for managing operating system libraries
* [Rbenv] for managing versions of Ruby
* [RCM] for managing company and personal dotfiles
* [Ruby Build] for installing Rubies
* [Ruby] stable for writing general-purpose code
* [The Silver Searcher] for finding things in files
* [Tree] for listing directories in a tree-like format
* [Zsh] as your shell

[Homebrew]: http://brew.sh/
[Rbenv]: https://github.com/sstephenson/rbenv
[RCM]: https://github.com/thoughtbot/rcm
[Ruby Build]: https://github.com/sstephenson/ruby-build
[Ruby]: https://www.ruby-lang.org/en/
[The Silver Searcher]: https://github.com/ggreer/the_silver_searcher
[Tree]: http://mama.indstate.edu/users/ice/tree/
[Zsh]: http://www.zsh.org/

It should take less than 15 minutes to install (depends on your machine).

Customize in `~/.laptop.local`
------------------------------

Your `~/.laptop.local` is run at the end of the Laptop script.
Put your customizations there.
For example:

```sh
#!/bin/sh

brew_tap 'caskroom/cask'
brew_install_or_upgrade 'brew-cask'

brew cask install dropbox
brew cask install google-chrome
brew cask install rdio

gem_install_or_update 'parity'

brew_install_or_upgrade 'tree'
brew_install_or_upgrade 'watch'
```

Write your customizations such that they can be run safely more than once.
See the `mac` script for examples.

Laptop functions such as `fancy_echo`,
`brew_install_or_upgrade`, and
`gem_install_or_update`
can be used in your `~/.laptop.local`.

See the [wiki](https://github.com/thoughtbot/laptop/wiki)
for more customization examples.

Contributing
------------

Edit the `mac` file.
Document in the `README.md` file.
Follow shell style guidelines by using [ShellCheck] and [Syntastic].

```sh
brew install shellcheck
```

[ShellCheck]: http://www.shellcheck.net/about.html
[Syntastic]: https://github.com/scrooloose/syntastic

Thank you, [contributors]!

[contributors]: https://github.com/thoughtbot/laptop/graphs/contributors

License
-------

Laptop is © 2011-2015 thoughtbot, inc.
It is free software,
and may be redistributed under the terms specified in the [LICENSE] file.

[LICENSE]: LICENSE

About thoughtbot
----------------

![thoughtbot](https://thoughtbot.com/logo.png)

Laptop is maintained and funded by thoughtbot, inc.
The names and logos for thoughtbot are trademarks of thoughtbot, inc.

We are passionate about open source software.
See [our other projects][community].
We are [available for hire][hire].

[community]: https://thoughtbot.com/community?utm_source=github
[hire]: https://thoughtbot.com?utm_source=github
