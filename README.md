===============
cront
===============

cront is a library that can make the task apps like crontab.

Installation
============

Automatic installation::

   $ pip install cront

cront is listed in `PyPI <https://pypi.python.org/pypi/cront>`_ and can be installed with pip or easy_install.

Manual installation::

   $ git clone https://github.com/asmodius/cront.git
   $ cd cront
   $ python setup.py install

cront source code is `hosted on GitHub <https://github.com/asmodius/cront>`_

Usage
=====

Here is a simple app for Tornado::

   from __future__ import print_function
   import tornado.web
   import tornado.ioloop
   from cront import cron_task
    
   @cron_task("* * * * *")
   def hello_crontab(app):
       print("Hello, {0}".format(app))

   if __name__ == "__main__":
       app = tornado.web.Application()
       cron_task.start(app)
       tornado.ioloop.IOLoop.current().start()

Using
=====

* `Tornado <http://www.tornadoweb.org/>`_

License
=======

* cront license under the `MIT license <https://github.com/gaujin/tornado-crontab/blob/master/LICENSE>`_.
* `Tornado is licensed under the Apache license <https://github.com/tornadoweb/tornado/blob/master/LICENSE>`_.
