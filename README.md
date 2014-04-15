## Installation

As a feature, puppet module tool will use ~/.puppet/var/puppet-module/skeleton
as template for its `generate` command. The files provided here are
meant to be better templates for use with the puppet module tool.

As we don't want to have our .git files and this README in our skeleton, we export it like this:

    git clone https://github.com/cwebberOps/dm-puppet-skeleton
    cd dm-puppet-skeleton
    find skeleton -type f | git checkout-index --stdin --force --prefix="$HOME/.puppet/var/puppet-module/" --

## Usage

The just generate your new module structure like so:

    puppet module generate user-module

Once you have your module then install the development dependencies:

    cd user-module
    bundle install


Of particular interst should be:

* `bundle exec rake spec` - run unit tests
* `bundle exec rake lint` - checks against the puppet style guide
* `bundle exec rake syntax` - to check your have valid puppet and erb syntax

## Thanks

The trick used in the installation above, and a few other bits came from
another excellent module skeleton from [spiette](https://github.com/spiette/puppet-module-skeleton).

Additionally, the majority of the code boilerplate code was borrowed from [garethr](https://github.com/garethr/puppet-module-skeleton)
