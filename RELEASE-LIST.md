
# Release Checklist

This assumes that you are creating a release for an instance of Fedora
Connector installed in its normal place in the Omeka `plugins` directory.

1. export VERSION=42.0.13
1. git flow release start $VERSION
1. Update versions
   * `plugin.ini`
   * `package.json`
   * `bower.json`
1. git commit -a -m "Set version number to $VERSION."
1. npm install
1. bower install
1. PATH=$PATH:./node_modules/bin/
1. curl -sS https://getcomposer.org/installer | php
1. php composer.phar install
1. grunt
1. grunt compress
1. Check the `pkg` tarball.
1. git flow release finish "$VERSION"
1. git push --all
1. git push --tags

Upload!
