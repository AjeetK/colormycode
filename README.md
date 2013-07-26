# colormycode

[colormycode](http://colormycode.herokuapp.com/) is a small webapp (fork of hilite.me) that converts your code
snippets into pretty-printed HTML format, easily embeddable into blog posts and
websites.

## Development

To set up development environment you need to install these dependencies:

* On FreeBSD: `portmaster textproc/py-pygments www/nginx www/py-flask`
* On Debian/Ubuntu: `aptitude install nginx python-flask python-pygments`

Edit your main `nginx.conf`:

    http {
        ...
        include /path/to/colormycode/nginx.conf;
    }

Update the project location in `colormycode/nginx.conf` and restart nginx.

Add this line to your `/etc/hosts`:

    127.0.0.1  colormycode

Type `make run` and go to <http://colormycode.herokuapp.com/>. If static files don't load make
sure nginx has rx permissions for the `colormycode/static` directory.
