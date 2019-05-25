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

building it on WINDOWS involved some more elaboration:

1. download python 3.7.3 from https://www.python.org/downloads/
2. install it wurg pip and add python path to environmen variables
3. install Cyphon with 'pip install Cyphon'
4. download https://visualstudio.microsoft.com/de/downloads/
4. download http://cmake.org
4. download https://sourceforge.net/projects/liblo/
5. go into the /build folder and readme.md
6. -> build the Visual Studio Code 17 projects
7. open liblo.sln
8. build the release.
9. download https://github.com/dsacre/pyliblo
10. -> when building the pyliblo its missing files can be found inside the downloaded liblo folder.
Also the setup.py file needs to be edited:

ext_modules = [
    Extension(
        'liblo',
        ['src/liblo.pyx'],
        extra_compile_args = [
            '-fno-strict-aliasing',
        ],
        extra_link_args = ['/LIBPATH:D:\\Users\\innovationlab-admin\\Downloads\\liblo-0.30.tar\\liblo-0.30\\cmake\\Release'],
        libraries = ['liblo']
    )
]
When in doubt, follow (more or less) these instructions: http://magic-smoke.blogspot.com/2012/07/building-pyliblo-on-windows-using.html
11. after building pyliblo you need to copy 
    pyliblo\\build\\bdist.win-amd64\\egg\\liblo.py
    pyliblo\\build\\bdist.win-amd64\\egg\\liblo.cp37-win_amd64.pyd

    and

    liblo\\\cmake\\liblo.dll

to this library.
    


it should be working on OSX, but if you want to use it with windows or linux you need to compile the library yourself.
