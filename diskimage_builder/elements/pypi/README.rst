====
pypi
====

====================
Inject a PyPI mirror
====================

Use a custom PyPI mirror to build images. The default is to bind mount one from
~/.cache/image-create/pypi/mirror into the build environment as mirror URL
file:///tmp/pypi. The element temporarily overwrites /root/.pip.conf to use it.

When online, the official pypi.python.org pypi index is supplied as an
extra-url, so uncached dependencies will still be available. When offline, only
the mirror is used - be warned that a stale mirror will cause build failures.
To disable the pypi.python.org index without using --offline (e.g. when working
behind a corporate firewall that prohibits pypi.python.org) set
DIB\_NO\_PYPI\_PIP to any non-empty value.

To use an arbitrary mirror set DIB\_PYPI\_MIRROR\_URL=http[s]://somevalue/

Additional mirrors can be added by exporting DIB\_PYPI\_MIRROR\_URL\_1=... etc.
NB: The sort order for these variables is a simple string sort - if you
have more than 9 additional mirrors, some care will be needed.

You can also set the number of retries that occur on failure by setting the
DIB\_PIP\_RETRIES environment variable. If setting fallback pip mirrors you
typically want to set this to 0 to prevent the need to fail multiple times
before falling back.

A typical use of this element is thus:
export DIB\_PYPI\_MIRROR\_URL=http://site/pypi/Ubuntu-13.10
export DIB\_PYPI\_MIRROR\_URL\_1=http://site/pypi/
export DIB\_PYPI\_MIRROR\_URL\_2=file:///tmp/pypi
export DIB\_PIP\_RETRIES=0

[devpi-server](https://pypi.python.org/pypi/devpi-server)
can be useful in making a partial PyPI mirror suitable for building images. For
instance:

 * pip install -U devpi

 * devpi-server quickstart

 * devpi use http://machinename:3141

* Re-export your variables to point at the new mirror:

    export DIB\_PYPI\_MIRROR\_URL=http://machinename:3141/
    unset DIB\_PYPI\__MIRROR\_URL\_1
    unset DIB\_PYPI\__MIRROR\_URL\_2

The next time packages are installed, they'll be cached on the local devpi
server; subsequent runs pointed at the same mirror will use the local cache if
the upstream can't be contacted.

Note that this process only has the server running temporarily; see
[Quickstart: Permanent install on
server/laptop](https://devpi.net/docs/devpi/devpi/latest/+d/quickstart-server.html)
guide from the devpi developers for more information on a more permanent setup.
