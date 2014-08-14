=======
ToxMail
=======

**HIGHLY EXPERIMENTAL - DON'T USE IT**

ToxMail is a prototype of a secure messaging system that can be used
to send and receive e-mails from your friends and family using your
usual e-mail desktop client and maybe your webmail.


Installation
------------

ToxMail is a server component that binds several sockets and needs
to run at all times to send and receive e-mails.

To install it, you need the latest Python 2, virtualenv, the Tox lib
and the Makefile tools.

To install the Tox library, you can refer to : https://github.com/irungentoo/toxcore/blob/master/INSTALL.md

Then a simple make call should do the trick::

    $ make build

Once all the dependencies are pulled and built, you can run
the server with **toxmail**::

    $ bin/toxmail --tox-data bob

Where **bob** is the Tox data file containing the generated private
and public key. **Do not let anyone get this file**

Your e-mails will be kept into the **bob.mails** directory.

Toxmail Dasbhoard
-----------------

Once Toxmail is running, visit http://localhost:8080, you should
see the dashboard with information about the configuration,
a list of friends and a form to add new friends.


Configuring your e-mail client
------------------------------

XXX

Inviting friends
----------------

XXX

How ToxMail works
-----------------

ToxMail is a special Tox node for the distributed Tox network - https://tox.im
that registers to the Tox DHT and runs:

- an SMTP service
- a Web Dashboard to manage the system
- a POP3 service

When you run a ToxMail node, you can exchange e-mails with your friends that also
have a ToxMail node running - using your regular e-mail application.

ToxMail stores your e-mail in a local Maildir.

