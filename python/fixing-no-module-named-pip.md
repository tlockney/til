# Fixing a `No module named: pip` error

Today I stumbled on something very odd. When trying to poke around in a virtualenv, I discovered that `pip` was non functional. When trying to run it, this is what I saw:

```sh
$ ./venv/bin/pip3
Traceback (most recent call last):
  File "./venv/bin/pip3", line 7, in <module>
    from pip import main
ModuleNotFoundError: No module named 'pip'
```

I was mystified since it was very clear that `pip` was available when investigating the `site_packages` folder. But apparently the install was broken somehow. Thankfully, there's a simple script out there for reinstalling `pip`. It can be run using the following command:

```sh
curl https://bootstrap.pypa.io/get-pip.py | python3
```