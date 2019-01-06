# AddOSC
OSC support in the viewport for Blender, see: http://www.jpfep.net/pages/addosc/

This fork is updated to work with blender 2.8

This Branch is using a different osc module than the master branch:

http://dsacre.github.io/pyliblo/doc/

it should be working on OSX, but if you want to use it with windows or linux you need to compile the library yourself.
 
It was hoped to get better performance from this library because it is C-based, but my tests didn't show the preformance gains that would weight against the advantage of a cross platform solution with the python-osc module.

it is here to be kept for the interested, but will not be further developed
