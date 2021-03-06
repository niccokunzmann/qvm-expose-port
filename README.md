# qvm-expose-port

Expose a qubes vm port to the public interfaces of the sys-net vm.

To expose port 8000 of the `work` VM, run

    user@dom0$ qvm-expose-port -a work 8000

E.g. you can run an http server in the `work` VM:

    user@work$ python3 -m http.server

Now, you can access the http server from the outside.

Installation
------------

You can install the script by downloading it.

    user@work$ wget https://raw.githubusercontent.com/niccokunzmann/qvm-expose-port/master/qvm-expose-port

Copy it to dom0 and make it executable.

    user@dom0$ qvm-run --pass-io work 'cat qvm-expose-port' > qvm-expose-port
    user@dom0$ chmod +x qvm-expose-port
    user@dom0$ sudo mv qvm-expose-port /usr/local/bin/

Contributing
------------

This script is not at all complete.
Please see if you can contribute and what is important to you.
You can use the [issue tracker][issues] to get into contact.

As this script can become a package, please see the [guidelines for
contributing packages](https://www.qubes-os.org/doc/package-contributions/) to help with this.
If you like to contribute code, [sign your
commits](https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work).

Development Setup
-----------------

You can clone the repository using git after you [forked][fork] it.
If you like to deploy it to dom0, run

    qvm-run --pass-io <vm-name> 'cat qvm-expose-port/qvm-expose-port' > /usr/local/bin/qvm-expose-port

If you have changed the script in dom0, run this to copy it back to the repository:

    cat /usr/local/bin/qvm-expose-port | qvm-run --pass-io <vm-name> 'cat > qvm-expose-port/qvm-expose-port'

Related Work
------------

- [The issue for this package](https://github.com/QubesOS/qubes-issues/issues/4028)
- [The documentation about the firewall][firewall-docs] was helpful to build this.
- [jpouellet/qvm-port-forward.sh](https://gist.github.com/jpouellet/d8cd0eb8589a5b9bf0c53a28fc530369)

[firewall-docs]: https://www.qubes-os.org/doc/firewall/
[issues]: https://github.com/niccokunzmann/qvm-expose-port/issues
[fork]: https://github.com/niccokunzmann/qvm-expose-port/fork
