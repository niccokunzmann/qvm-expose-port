# qvm-expose-port

Expose a qubes vm port to the public interfaces of the sys-net vm.

To expose port 8000 of the `work` VM, run

    user@dom0$ qvm-expose-port -a work 8000

E.g. you can run an http server in the `work` VM:

    user@work$ python3 -m http.server

Now, you can access the http server from the outside.

Contributing
------------

This script is not at all complete.
Please see if you can contribute and what is important to you.
You can use the [issue tracker][issues] to get into contact.

Related Work
------------

[The documentation about the firewall][firewall-docs] was helpful to build this.

[firewall-docs]: https://www.qubes-os.org/doc/firewall/
[issues]: https://github.com/niccokunzmann/qvm-expose-port/issues

