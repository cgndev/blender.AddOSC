# AddOSC
OSC support in the viewport for Blender, see: http://www.jpfep.net/pages/addosc/

This fork is updated to work with blender 2.8

This branch is using a different osc module than the master branch:

This implementation gets better performance because the osc library is C-based, but that would weight against the advantage of a cross platform solution with the python-osc module.

http://dsacre.github.io/pyliblo/doc/
http://das.nasophon.de/pyliblo/

to install on OSX I needed to 

1. download python 3.7 via brew
2. install Cython via pip3.7

and then inside the downloaded pyliblo folder:

3. /usr/local/bin/python3.7 ./setup.py build
4. /usr/local/bin/python3.7 ./setup.py install

to get the egg folder under /usr/local/lib/python3.7/site-packages

which I then copied to this local blender script folder.

it should be working on OSX, but if you want to use it with windows or linux you need to compile the library yourself.
