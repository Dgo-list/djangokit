DjangoKit is a framework that will take a [Django][1] application, and
turn it into a stand-alone MacOS application with a local database and
media files. It's more of a thought experiment than an effort at
producing a real application, but there are a couple of simple
[examples][2] and the [source code is available for download][3] from my
subversion repository. There are also downloadable binaries below.

DjangoKit depends on [Django][1] and [PyObjC][5], so first install them,
then install DjangoKit the usual way:

    python setup.py install

Currently your app will need a fairly specific folder layout to work,
use the layout in the examples as a base. Copy a [setup.py file from
the TODO example][4] and modify it to suit your app, then run

    python setup.py syncdb
    python setup.py py2app

This should produce a stand-alone .app in the local /dist directory. For
development, try

    python setup.py py2app -A

Which will produce a development-only app that symlinks your app into it,
so you can continue to edit the source files without having to rebuild
the app every time you save. You can even edit the templates while the
app is still running and see changes.


[1]: http://www.djangoproject.com/
[2]: https://jerakeen.org/svn/tomi/Projects/DjangoKit/examples/
[3]: https://jerakeen.org/svn/tomi/Projects/DjangoKit/
[4]: https://jerakeen.org/svn/tomi/Projects/DjangoKit/examples/todo/setup.py
[5]: http://pyobjc.sourceforge.net/
